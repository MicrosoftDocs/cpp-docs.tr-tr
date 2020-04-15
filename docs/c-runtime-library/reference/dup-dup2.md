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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 239f857bb40c9609cb6f7ff373295a7a1f8523a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348110"
---
# <a name="_dup-_dup2"></a>_dup, _dup2

Açık bir dosya **(_dup)** için ikinci bir dosya tanımlayıcısı oluşturur veya dosya tanımlayıcıyı **(_dup2)** yeniden atar.

## <a name="syntax"></a>Sözdizimi

```C
int _dup( int fd );
int _dup2( int fd1, int fd2 );
```

### <a name="parameters"></a>Parametreler

*fd*, *fd1*<br/>
Dosya tanımlayıcıları açık dosyaya atıfta bulunarak.

*fd2*<br/>
Herhangi bir dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

**_dup** yeni bir dosya tanımlayıcısı döndürür. **_dup2** başarıyı belirtmek için 0 döndürür. Bir hata oluşursa, her işlev -1 döndürür ve dosya tanımlayıcısı geçersizse **EBADF'a** veya başka dosya tanımlayıcısı yoksa **EMFILE'ye** **errno** ayarlar. Geçersiz bir dosya tanımlayıcısı durumunda, işlev, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini de çağırır.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**_dup** ve **_dup2** işlevleri, ikinci bir dosya tanımlayıcısını şu anda açık olan bir dosyayla ilişkilendirer. Bu işlevler, **stdout**için farklı bir dosya ile önceden tanımlanmış bir dosya tanımlayıcısı, ilişkilendirmek için kullanılabilir. Dosya üzerindeki işlemler her iki dosya tanımlayıcısı kullanılarak gerçekleştirilebilir. Dosya için izin verilen erişim türü, yeni bir tanımlayıcının oluşturulmasından etkilenmez. **_dup,** verilen dosyaiçin kullanılabilir bir sonraki dosya tanımlayıcısını döndürür. **_dup2** *fd2'yi* *fd1*ile aynı dosyaya göndermeyapmaya zorlar. *FD2* arama sırasında açık bir dosyaile ilişkiliyse, bu dosya kapatılır.

Hem **_dup** hem de **_dup2** dosya tanımlayıcılarını parametre olarak kabul eder. Bu işlevlerden`FILE *`herhangi birine bir akış ( ) geçmek için [_fileno](fileno.md)kullanın. **Fileno** yordamı, şu anda verilen akışla ilişkili dosya tanımlayıcısını döndürür. Aşağıdaki örnek, **stderr** 'in (Stdio.h'de tanımlandığı gibi) `FILE *` bir dosya tanımlayıcısıyla nasıl ilişkilendirilir:

```C
int cstderr = _dup( _fileno( stderr ));
```

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_dup**|\<io.h>|
|**_dup2**|\<io.h>|

Konsol, Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Konsol, **stdin,** **stdout**ve **stderr**ile ilişkili standart akış kolları, C çalışma zamanı işlevleri UWP uygulamalarında bunları kullanamadan önce yönlendirilmelidir. Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Düşük Seviyeli G/Ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
