---
title: atan, atanf, atanl, atan2, atan2f, atan2l
ms.date: 4/2/2020
api_name:
- atan2f
- atan2l
- atan2
- atanf
- atan
- atanl
- _o_atan
- _o_atan2
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
- atan
- atan2l
- atan2
- atanl
- atanf
- atan2f
helpviewer_keywords:
- atan function
- atanf function
- atanl function
- atan2 function
- atan2l function
- arctangent function
- trigonometric functions
- atan2f function
ms.assetid: 7a87a18e-c94d-4727-9cb1-1bb5c2725ae4
ms.openlocfilehash: 3b8411f9839022477dff3100792e271e2f0b572b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81334114"
---
# <a name="atan-atanf-atanl-atan2-atan2f-atan2l"></a>atan, atanf, atanl, atan2, atan2f, atan2l

**X** **(atan**, **atanf**, ve **atanl)** veya **y**/**x** **(atan2**, **atan2f**, ve **atan2l)** arctant'ını hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double atan( double x );
float atanf( float x );
long double atanl( long double x );

double atan2( double y, double x );
float atan2f( float y, float x );
long double atan2l( long double y, long double x );
```

```cpp
float atan( float x );  // C++ only
long double atan( long double x );  // C++ only

float atan2( float y, float x );  // C++ only
long double atan2( long double y, long double x );  // C++ only
```

### <a name="parameters"></a>Parametreler

*x*, *y*<br/>
Herhangi bir sayı.

## <a name="return-value"></a>Dönüş Değeri

**atan** *x'in* -π/2 aralığındaki arkantını π/2 radanlara döndürür. **atan2,** π radyanlara -π *aralığındaki y*/*x'in* arctant'ını döndürür. *x* 0 ise **atan** 0 döndürür. **Atan2'nin** her iki parametresi de 0 ise, işlev 0 döndürür. Tüm sonuçlar radyanlarda.

**atan2,** iade değerinin çeyreğini belirlemek için her iki parametrenin işaretlerini kullanır.

|Girdi|SEH Özel Durumu|Matherr İstisnası|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|yok|**_DOMAIN**|

## <a name="remarks"></a>Açıklamalar

**Atan** işlevi *x'in*arctant (ters teğet fonksiyonu) değerini hesaplar. **atan2** *y*/*x'in* arctant'ını hesaplar *(x* 0'a eşitse, *atan2* pozitifse π/2 döndürür, *-π/2* y negatifse, *0* ise 0.) **atan2**

**atan,** Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulaması vardır. SSE2 uygulamasını kullanma yla ilgili bilgi ve kısıtlamalar için [_set_SSE2_enable](set-sse2-enable.md)bkz.

C++ aşırı yüklemeye izin verdiğinden, **float** veya **uzun** **çift** bağımsız değişkenler alan aşırı **atan** ve **atan2** yükleri arayabilirsiniz. Bir C programında, **atan** ve **atan2** her zaman **çift** argümanlar almak ve bir **çift**dönmek .

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üstbilgi (C)|Gerekli üstbilgi (C++)|
|-------------|---------------------|-|
|**atan**, **atan2**, **atanf**, **atan2f**, **atanl**, **atan2l**|\<math.h>|\<cmath> \<veya math.h>|

## <a name="example"></a>Örnek

```C
// crt_atan.c
// arguments: 5 0.5
#include <math.h>
#include <stdio.h>
#include <errno.h>

int main( int ac, char* av[] )
{
   double x, y, theta;
   if( ac != 3 ){
      fprintf( stderr, "Usage: %s <x> <y>\n", av[0] );
      return 1;
   }
   x = atof( av[1] );
   theta = atan( x );
   printf( "Arctangent of %f: %f\n", x, theta );
   y = atof( av[2] );
   theta = atan2( y, x );
   printf( "Arctangent of %f / %f: %f\n", y, x, theta );
   return 0;
}
```

```Output
Arctangent of 5.000000: 1.373401
Arctangent of 0.500000 / 5.000000: 0.099669
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[asin, asinf, asinl](asin-asinf-asinl.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
[_CIatan](../../c-runtime-library/ciatan.md)<br/>
[_CIatan2](../../c-runtime-library/ciatan2.md)<br/>
