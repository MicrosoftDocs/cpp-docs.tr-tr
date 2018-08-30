---
title: _dup, _dup2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _dup
- _dup2
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _dup2
- _dup
dev_langs:
- C++
helpviewer_keywords:
- _dup2 function
- dup function
- file handles [C++], duplicating
- file handles [C++], reassigning
- dup2 function
- _dup function
ms.assetid: 4d07e92c-0d76-4832-a770-dfec0e7a0cfa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 820172e1e6ab4ad007c89b2b40f03512134f0f0d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215959"
---
# <a name="dup-dup2"></a>_dup, _dup2

Açık bir dosya için ikinci bir dosya tanımlayıcısı oluşturur (**_dup**), veya bir dosya tanımlayıcısını yeniden atar (**_dup2**).

## <a name="syntax"></a>Sözdizimi

```C
int _dup( int fd );
int _dup2( int fd1, int fd2 );
```

### <a name="parameters"></a>Parametreler

*FD*, *fd1*<br/>
Dosyayı açmak için başvuran dosya tanımlayıcıları.

*fd2*<br/>
Herhangi bir dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

**_dup** yeni dosya tanımlayıcısını döndürür. **_dup2** başarılı olduğunu belirtmek için 0 değerini döndürür. Bir hata oluşursa, her bir işlev -1 döndürür ve kümeleri **errno** için **EBADF** dosya tanımlayıcısı geçersizse veya için **EMFILE** hiçbir daha fazla dosya tanımlayıcısı kullanılabilir değilse. Geçersiz dosya tanımlayıcısı olması durumunda, işlev de geçersiz parametre işleyicisi açıklandığı gibi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md).

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Dup** ve **_dup2** işlevleri ikinci bir dosya tanımlayıcısı şu anda açık bir dosya ile ilişkilendirin. Bu işlevler için olan gibi bir önceden tanımlanmış dosya tanımlayıcısını ilişkilendirmek için kullanılabilir **stdout**, farklı bir dosya ile. Dosya üzerindeki işlemler iki dosya tanımlayıcısı kullanılarak gerçekleştirilen kullanılabilir. Dosya için izin verilen erişim türünü yeni bir tanımlayıcı oluşturulmasını tarafından etkilenmez. **_dup** verilen dosyaya sonraki kullanılabilir dosya tanımlayıcısını döndürür. **_dup2** zorlar *fd2* aynı dosyaya başvurmak için *fd1*. Varsa *fd2* ilişkili aramanın zaman bir açık dosya ile bu dosya kapatılır.

Her ikisi de **_dup** ve **_dup2** dosya tanımlayıcılarını parametre olarak kabul edin. Bir akışa geçirmek için (`FILE *`) kullanın ya da bu işlevler için [_fileno](fileno.md). **Fileno** yordamı belirtilen akış ile şu anda ilişkili dosya tanımlayıcısını döndürür. Aşağıdaki örnek nasıl ilişkilendirildiğini gösterir **stderr** (olarak tanımlanan `FILE *` Stdio.h içinde) ile bir dosya tanımlayıcısı:

```C
int cstderr = _dup( _fileno( stderr ));
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_dup**|\<io.h >|
|**_dup2**|\<io.h >|

Konsolu, Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsolları ile ilişkili standart akış işleyicileri **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri bunları UWP uygulamalarında kullanmadan önce yeniden yönlendirilmesi gerekiyor . Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_dup.c
// This program uses the variable old to save
// the original stdout. It then opens a new file named
// DataFile and forces stdout to refer to it. Finally, it
// restores stdout to its original state.

#include <io.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int old;
   FILE *DataFile;

   old = _dup( 1 );   // "old" now refers to "stdout"
                      // Note:  file descriptor 1 == "stdout"
   if( old == -1 )
   {
      perror( "_dup( 1 ) failure" );
      exit( 1 );
   }
   _write( old, "This goes to stdout first\n", 26 );
   if( fopen_s( &DataFile, "data", "w" ) != 0 )
   {
      puts( "Can't open file 'data'\n" );
      exit( 1 );
   }

   // stdout now refers to file "data"
   if( -1 == _dup2( _fileno( DataFile ), 1 ) )
   {
      perror( "Can't _dup2 stdout" );
      exit( 1 );
   }
   puts( "This goes to file 'data'\n" );

   // Flush stdout stream buffer so it goes to correct file
   fflush( stdout );
   fclose( DataFile );

   // Restore original stdout
   _dup2( old, 1 );
   puts( "This goes to stdout\n" );
   puts( "The file 'data' contains:" );
   _flushall();
   system( "type data" );
}
```

```Output
This goes to stdout first
This goes to stdout

The file 'data' contains:
This goes to file 'data'
```

## <a name="see-also"></a>Ayrıca bkz.

[Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
