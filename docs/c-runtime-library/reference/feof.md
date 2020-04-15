---
title: feof
ms.date: 4/2/2020
api_name:
- feof
- _o_feof
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
- feof
helpviewer_keywords:
- end of file, testing for
- feof function
ms.assetid: 09081eee-7c4b-4189-861f-2fad95d3ec6d
ms.openlocfilehash: 9ee085624be3c5613ac4b5e87965d47324727778
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347377"
---
# <a name="feof"></a>feof

Bir akışta dosya sonu için testler.

## <a name="syntax"></a>Sözdizimi

```C
int feof(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bir okuma işlemi dosyanın sonundan önce okumaya **çalıştıysa, feof** işlevi sıfır olmayan bir değer döndürür; aksi takdirde 0 döndürür. Akış işaretçisi **NULL**ise, işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve **feof** döner 0.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

## <a name="remarks"></a>Açıklamalar

**Feof** yordamı (hem işlev olarak hem de makro olarak uygulanan) *akışın* sonunun geçirilip geçirilmediğini belirler. Dosyanın sonu geçirildiğinde, okuma işlemleri akış kapanana kadar veya [geri sarma](rewind.md), **fsetpos**, [fseek](fseek-fseeki64.md), veya **daha net** bir şekilde buna karşı çağrılana kadar dosya sonu göstergesi döndürün.

Örneğin, bir dosya 10 bayt içeriyorsa ve dosyadan 10 bayt okursanız, dosya işaretçisi dosyanın sonunda olmasına rağmen, sonuna kadar okumaya denemediğiniz için **feof** 0 döndürecektir. Sadece 11. **feof**

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**feof**|\<stdio.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

## <a name="input-crt_feoftxt"></a>Giriş: crt_feof.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıktı

```Output
Number of bytes read = 19
```

## <a name="see-also"></a>Ayrıca bkz.

[Hata İşleme](../../c-runtime-library/error-handling-crt.md)<br/>
[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[clearerr](clearerr.md)<br/>
[_eof](eof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
