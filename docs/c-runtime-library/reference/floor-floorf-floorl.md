---
title: floor, floorf, floorl
ms.date: 4/2/2020
api_name:
- floorf
- floorl
- floor
- _o_floor
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
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- floor
- floorl
- _floorl
- floorf
helpviewer_keywords:
- floor function
- floorf function
- calculating floors of values
- floorl function
ms.assetid: e9955f70-d659-414f-8050-132e13c8ff36
ms.openlocfilehash: 67902c61cd6e6cebd1be5182601baedfa1639ea7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346667"
---
# <a name="floor-floorf-floorl"></a>floor, floorf, floorl

Bir değerin zeminini hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double floor(
   double x
);
float floor(
   float x
); // C++ only
long double floor(
   long double x
); // C++ only
float floorf(
   float x
);
long double floorl(
   long double x
);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**Kat** fonksiyonları, *x'ten*küçük veya eşit olan en büyük tamsayıyı temsil eden kayan nokta değerini döndürer. Hata iadesi yok.

|Girdi|SEH Özel Durumu|Matherr İstisnası|
|-----------|-------------------|-----------------------|
|± QNAN,IND|yok|_DOMAIN|

**katta** Streaming SIMD Uzantıları 2 (SSE2) kullanan bir uygulama vardır. SSE2 uygulamasını kullanma yla ilgili bilgi ve kısıtlamalar için [_set_SSE2_enable](set-sse2-enable.md)bkz.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verir, böylece **float** ve **uzun** **çift** değerleri alan ve **döndüren** aşırı kat yüklerini arayabilirsiniz. Bir C programında, **zemin** her zaman alır ve bir **çift**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**zemin**, **floorf**, **floorl**|\<math.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_floor.c
// This example displays the largest integers
// less than or equal to the floating-point values 2.8
// and -2.8. It then shows the smallest integers greater
// than or equal to 2.8 and -2.8.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double y;

   y = floor( 2.8 );
   printf( "The floor of 2.8 is %f\n", y );
   y = floor( -2.8 );
   printf( "The floor of -2.8 is %f\n", y );

   y = ceil( 2.8 );
   printf( "The ceil of 2.8 is %f\n", y );
   y = ceil( -2.8 );
   printf( "The ceil of -2.8 is %f\n", y );
}
```

```Output
The floor of 2.8 is 2.000000
The floor of -2.8 is -3.000000
The ceil of 2.8 is 3.000000
The ceil of -2.8 is -2.000000
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[round, roundf, roundl](round-roundf-roundl.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
