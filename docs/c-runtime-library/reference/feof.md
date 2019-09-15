---
title: feof
ms.date: 11/04/2016
api_name:
- feof
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- feof
helpviewer_keywords:
- end of file, testing for
- feof function
ms.assetid: 09081eee-7c4b-4189-861f-2fad95d3ec6d
ms.openlocfilehash: cf6cfdb63689f5d69cc45dd407ecc6b08a7a7a73
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941144"
---
# <a name="feof"></a>feof

Akışta dosya sonu için testler.

## <a name="syntax"></a>Sözdizimi

```C
int feof(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bir okuma işlemi dosyanın sonundan sonra okumayı denediğinde **feof** işlevi sıfır dışında bir değer döndürür; Aksi takdirde 0 döndürür. Akış işaretçisi **null**ise, Işlev [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve **feof** 0 döndürür.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

Yordamın **Fede** (hem bir işlev olarak hem de bir makro olarak uygulanan) *akışın* sonunun geçtiğini belirler. Dosya sonu geçirildiğinde, akış kapatılıncaya kadar veya [geri sarma](rewind.md), **fsetpos**, [fseek](fseek-fseeki64.md)veya **clearerr** çağrılana kadar okuma işlemleri bir dosya sonu göstergesi döndürür.

Örneğin, bir dosya 10 bayt içeriyorsa ve dosyadan 10 bayt **okuduğunuzda, dosya** işaretçisi dosyanın sonunda olsa bile, son olarak okumayı Denememekle birlikte 0 döndürür. Yalnızca bir 11 baytını okumaya çalıştıktan **sonra, sıfır** dışında bir değer döndürerirsiniz.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**feof**|\<stdio. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_feof.c
// This program uses feof to indicate when
// it reaches the end of the file CRT_FEOF.TXT. It also
// checks for errors with ferror.
//

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int  count, total = 0;
   char buffer[100];
   FILE *stream;

   fopen_s( &stream, "crt_feof.txt", "r" );
   if( stream == NULL )
      exit( 1 );

   // Cycle until end of file reached:
   while( !feof( stream ) )
   {
      // Attempt to read in 100 bytes:
      count = fread( buffer, sizeof( char ), 100, stream );
      if( ferror( stream ) )      {
         perror( "Read error" );
         break;
      }

      // Total up actual bytes read
      total += count;
   }
   printf( "Number of bytes read = %d\n", total );
   fclose( stream );
}
```

## <a name="input-crt_feoftxt"></a>Giriş: crt_feof. txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıkış

```Output
Number of bytes read = 19
```

## <a name="see-also"></a>Ayrıca bkz.

[Hata İşleme](../../c-runtime-library/error-handling-crt.md)<br/>
[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[clearerr](clearerr.md)<br/>
[_eof](eof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
