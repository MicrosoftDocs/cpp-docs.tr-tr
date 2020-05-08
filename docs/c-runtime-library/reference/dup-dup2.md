---
title: _dup, _dup2
ms.date: 4/2/2020
api_name:
- _dup
- _dup2
- _o__dup
- _o__dup2
api_location:
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _dup2
- _dup
helpviewer_keywords:
- _dup2 function
- dup function
- file handles [C++], duplicating
- file handles [C++], reassigning
- dup2 function
- _dup function
ms.assetid: 4d07e92c-0d76-4832-a770-dfec0e7a0cfa
ms.openlocfilehash: 6c635930fdbc8da550a2a32ea614e150fbeb08a8
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82915211"
---
# <a name="_dup-_dup2"></a>_dup, _dup2

Açık dosya (**_dup**) için ikinci bir dosya tanımlayıcısı oluşturur veya bir dosya tanımlayıcısını yeniden atar (**_dup2**).

## <a name="syntax"></a>Sözdizimi

```C
int _dup( int fd );
int _dup2( int fd1, int fd2 );
```

### <a name="parameters"></a>Parametreler

*FD*, *FD1*<br/>
Açık dosyaya başvuran dosya tanımlayıcıları.

*fd2*<br/>
Herhangi bir dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

**_dup** yeni bir dosya tanımlayıcısı döndürür. **_dup2** başarıyı göstermek için 0 döndürür. Bir hata oluşursa, her işlev-1 döndürür ve daha fazla dosya tanımlayıcısı yoksa, dosya tanımlayıcısı geçersizse veya **Emfile** için **errno** , **EBADF** olarak ayarlanır. Geçersiz bir dosya tanımlayıcısı söz konusu olduğunda, işlev [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini de çağırır.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Dup** ve **_dup2** işlevleri, bir ikinci dosya tanımlayıcısını Şu anda açık olan bir dosya ile ilişkilendirir. Bu işlevler, **stdout**gibi önceden tanımlanmış bir dosya tanımlayıcısını farklı bir dosyayla ilişkilendirmek için kullanılabilir. Dosyadaki işlemler, herhangi bir dosya tanımlayıcısı kullanılarak gerçekleştirilebilir. Dosya için izin verilen erişim türü, yeni bir tanımlayıcının oluşturulmasından etkilenmez. **_dup** , belirtilen dosya için bir sonraki kullanılabilir dosya tanımlayıcısını döndürür. **_dup2** *fd2* , *FD1*ile aynı dosyaya başvurmaya zorlar. *Fd2* , çağrı sırasında açık bir dosya ile ilişkiliyse, bu dosya kapatılır.

Hem **_dup** hem de **_dup2** dosya tanımlayıcılarını parametre olarak kabul eder. Bu işlevlerden birine bir Stream`FILE *`() geçirmek için [_fileno](fileno.md)kullanın. **Fileno** yordamı, belirtilen akış ile Şu anda ilişkili dosya tanımlayıcısını döndürür. Aşağıdaki örnek, **stderr** 'In (stdio. h 'de `FILE *` olarak tanımlanır) bir dosya tanımlayıcısıyla nasıl ilişkilendirileceğini gösterir:

```C
int cstderr = _dup( _fileno( stderr ));
```

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_dup**|\<GÇ. h>|
|**_dup2**|\<GÇ. h>|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Console, **STDIN**, **stdout**ve **stderr**Ile ilişkili standart akış TUTAMAÇLARı, C çalışma zamanı işlevlerinin UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Alt düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
