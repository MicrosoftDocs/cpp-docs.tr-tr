---
title: _eof
ms.date: 4/2/2020
api_name:
- _eof
- _o__eof
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
- _eof
helpviewer_keywords:
- eof function
- end of file, testing for
- _eof function
- files [C++], end of
- testing, for end-of-file
- end of file
ms.assetid: 265703f4-d07e-4005-abf3-b1d0cdd9e0b0
ms.openlocfilehash: 3218969c603e771ee6d2cdbf9baeed1728934be6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347928"
---
# <a name="_eof"></a>_eof

Dosya sonu (EOF) için testler.

## <a name="syntax"></a>Sözdizimi

```C
int _eof(
   int fd
);
```

### <a name="parameters"></a>Parametreler

*Fd*<br/>
Açık dosyaya atıfta bulunan dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

**_eof** geçerli konum dosyanın sonu ysa 1, değilse 0 döndürür. -1'in geri dönüş değeri bir hatayı gösterir; Bu durumda, geçersiz parametre işleyicisi, [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, **errno** **EBADF**olarak ayarlanır, hangi geçersiz bir dosya tanımlayıcıgösterir.

## <a name="remarks"></a>Açıklamalar

**_eof** işlevi *fd* ile ilişkili dosyanın sonuna ulaşılıp ulaşılmadığını belirler.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|
|--------------|---------------------|---------------------|
|**_eof**|\<io.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_eof.c
// This program reads data from a file
// ten bytes at a time until the end of the
// file is reached or an error is encountered.
//
#include <io.h>
#include <fcntl.h>
#include <stdio.h>
#include <stdlib.h>
#include <share.h>

int main( void )
{
   int  fh, count, total = 0;
   char buf[10];
   if( _sopen_s( &fh, "crt_eof.txt", _O_RDONLY, _SH_DENYNO, 0 ) )
   {
        perror( "Open failed");
        exit( 1 );
   }
   // Cycle until end of file reached:
   while( !_eof( fh ) )
   {
      // Attempt to read in 10 bytes:
      if( (count = _read( fh, buf, 10 )) == -1 )
      {
         perror( "Read error" );
         break;
      }
      // Total actual bytes read
      total += count;
   }
   printf( "Number of bytes read = %d\n", total );
   _close( fh );
}
```

### <a name="input-crt_eoftxt"></a>Giriş: crt_eof.txt

```Input
This file contains some text.
```

### <a name="output"></a>Çıktı

```Output
Number of bytes read = 29
```

## <a name="see-also"></a>Ayrıca bkz.

[Hata İşleme](../../c-runtime-library/error-handling-crt.md)<br/>
[Düşük Seviyeli G/Ç](../../c-runtime-library/low-level-i-o.md)<br/>
[clearerr](clearerr.md)<br/>
[feof](feof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
