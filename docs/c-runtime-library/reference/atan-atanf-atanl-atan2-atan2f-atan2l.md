---
title: atan, atanf, atanl, atan2, atan2f, atan2l
ms.date: 04/05/2018
apiname:
- atan2f
- atan2l
- atan2
- atanf
- atan
- atanl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 59a67b0d213a11630f551fd7582b44aab60e314f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541732"
---
# <a name="atan-atanf-atanl-atan2-atan2f-atan2l"></a>atan, atanf, atanl, atan2, atan2f, atan2l

Ark tanjantını hesaplar **x** (**atan**, **atanf**, ve **atanl**) veya ark tanjantını **y** / **x** (**atan2**, **atan2f**, ve **atan2l**).

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

**atan** arktanjantını döndürür *x* π/2 radyan için aralığı - π/2. **ATAN2** arktanjantını döndürür *y*/*x* de aralık - π π radyan için. Varsa *x* 0 ' dır **atan** 0 döndürür. Varsa, her iki parametre **atan2** 0, işlev 0 döndürür. Tüm sonuçlar radyan cinsinden olur.

**ATAN2** işaretlerini her iki parametre dönüş değerinin quadrant belirlemek için kullanır.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± **QNAN**, **ONRAKİNİ BUL**|yok|**_ETKİ ALANI**|

## <a name="remarks"></a>Açıklamalar

**Atan** işlevi hesaplar ark tanjantını (Ters Tanjant işlevi) *x*. **ATAN2** ark tanjantını hesaplar *y*/*x* (varsa *x* eşittir 0, **atan2** π/2 döndürür *y* pozitif ise - π/2 ise *y* negatif veya 0 ise *y* 0'dır.)

**atan** , Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulamaya sahiptir. Bilgi ve SSE2 uygulamasını kullanmayla ilgili kısıtlamalar için bkz. [_set_SSE2_enable](set-sse2-enable.md).

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **atan** ve **atan2** Süren **float** veya **uzun** **çift**  bağımsız değişkenler. C programında **atan** ve **atan2** her zaman **çift** bağımsız değişkenler ve dönüş bir **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık (C)|Gerekli başlık (C++)|
|-------------|---------------------|-|
|**atan**, **atan2**, **atanf**, **atan2f**, **atanl**, **atan2l**|\<Math.h >|\<cmath > veya \<math.h >|

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
