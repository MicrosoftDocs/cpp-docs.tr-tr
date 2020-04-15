---
title: _gcvt
ms.date: 4/2/2020
api_name:
- _gcvt
- _o__gcvt
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _gcvt
helpviewer_keywords:
- _gcvt function
- _CVTBUFSIZE
- gcvt function
- floating-point functions, converting number to string
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 5761411e-c06b-409a-912f-810fe7f4bcb5
ms.openlocfilehash: f161256c6dc86a045f49111cde3651bea08ead11
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345315"
---
# <a name="_gcvt"></a>_gcvt

Kayan nokta değerini arabellekte depoladığı bir dizeye dönüştürür. Bu işlevin daha güvenli bir sürümü mevcuttur; [bkz. _gcvt_s.](gcvt-s.md)

## <a name="syntax"></a>Sözdizimi

```C
char *_gcvt(
   double value,
   int digits,
   char *buffer
);
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Dönüştürülecek değer.

*rakamlar*<br/>
Depolanan önemli basamak sayısı.

*Arabellek*<br/>
Sonuç için depolama konumu.

## <a name="return-value"></a>Dönüş Değeri

**_gcvt** bir işaretçiyi basamak dizesine döndürür.

## <a name="remarks"></a>Açıklamalar

**_gcvt** işlevi kayan nokta *değerini* bir karakter dizesine dönüştürür (ondalık sayı ve olası bir işaret baytını içerir) ve dizeyi *arabellekte*depolar. *Arabellek* dönüştürülen değeri artı otomatik olarak eklenen bir sonlandırıcı null karakter, karşılamak için yeterince büyük olmalıdır. *Basamak* + 1 arabellek boyutu kullanılırsa, işlev arabelleğenin sonuna yazar. Bunun nedeni, dönüştürülen dize ondalık bir nokta içerir ve imza ve üs bilgileri içerebilir. Taşma için bir hüküm yoktur. **_gcvt** ondalık biçimde *basamak* ları oluşturmaya çalışır. Yapamıyorsa, üstel biçimde *basamak basamakları* üretir. Sondaki sıfırlar dönüştürmede bastırılabilir.

Herhangi bir kayan nokta değeri için uzunluk **_CVTBUFSIZE** *arabelleği* yeterlidir.

Bu işlev parametrelerini doğrular. *Arabellek* **NULL**ise, geçersiz parametre işleyicisi, [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlev **EINVAL** **için errno** ayarlar ve **NULL**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_gcvt**|\<stdlib.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_gcvt.c
// compile with: /W3
#include <stdlib.h>
#include <stdio.h>
#include <string.h>

int main( void )
{
   char buffer[_CVTBUFSIZE];
   double value = -1234567890.123;
   printf( "The following numbers were converted by _gcvt(value,12,buffer):\n" );
   _gcvt( value, 12, buffer ); // C4996
   // Note: _gcvt is deprecated; consider using _gcvt_s instead
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value *= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value *= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value *= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );

   printf( "\n" );
   value = -12.34567890123;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value /= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value /= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value /= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
}
```

```Output
The following numbers were converted by _gcvt(value,12,buffer):
buffer: '-1234567890.12' (14 chars)
buffer: '-12345678901.2' (14 chars)
buffer: '-123456789012' (13 chars)
buffer: '-1.23456789012e+012' (19 chars)

buffer: '-12.3456789012' (14 chars)
buffer: '-1.23456789012' (14 chars)
buffer: '-0.123456789012' (15 chars)
buffer: '-1.23456789012e-002' (19 chars)
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>
