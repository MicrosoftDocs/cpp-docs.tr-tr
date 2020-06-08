---
title: atan, atanf, atanl, atan2, atan2f, atan2l
ms.date: 6/5/2020
api_name:
- atan2f
- atan2l
- atan2
- atanf
- atan
- atanl
- _o_atan
- _o_atan2
- _o_atan2f
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 41007e08884da6ccac09c7dc98cef12381e4b45a
ms.sourcegitcommit: fe146adb3a02872538637196bb3c45aeeeaaf5c2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84506786"
---
# <a name="atan-atanf-atanl-atan2-atan2f-atan2l"></a>atan, atanf, atanl, atan2, atan2f, atan2l

**X** (**atan**, **atanf**, ve **atanl**) veya **y** / **x** 'in arktanjantını (**atan2**, **atan2f**ve **atan2l**) hesaplar.

## <a name="syntax"></a>Söz dizimi

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

**atan** ,-π/2 ile π/2 radyan aralığında *x* 'in ark tanjantını döndürür. **atan2** *y* / ,-π aralığında y*x* 'in ark tanjantını döndürür. *X* 0 ise, **atan** 0 döndürür. Her iki **atan2** parametresi 0 ise, işlev 0 döndürür. Tüm sonuçlar radyan cinsinden olur.

**atan2** , dönüş değerinin çeyreğine ilişkin her iki parametrenin işaretlerini kullanır.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|yok|**_DOMAIN**|

## <a name="remarks"></a>Açıklamalar

**Atan** işlevi, *x*'in arktanjantını (ters tanjant işlevi) hesaplar. **atan2** *y*x 'in ark tanjantını hesaplar / *x* ( *x* eşitse 0, **atan2** *, y* pozitifse,-π/2 ise y negatifse 0 veya *y* 0 *y* ise 0 olur.)

**atan** 'de Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulama vardır. SSE2 uygulamasını kullanma hakkında bilgi ve sınırlamalar için bkz. [_set_SSE2_enable](set-sse2-enable.md).

C++ aşırı yüklemeye izin verdiğinden, **float** veya **Long** **Double** bağımsız değişkenlerini alan **atan** ve **atan2** aşırı yüklerini çağırabilirsiniz. C programında, **atan** ve **atan2** her zaman **çift** bağımsız değişken alır ve bir **Double**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|-------------|---------------------|-|
|**atan**, **atan2**, **atanf**, **atan2f**, **atanl**, **atan2l**|\<math.h>|\<cmath> veya \<math.h>|

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

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[asin, asinf, asinl](asin-asinf-asinl.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
[_CIatan](../../c-runtime-library/ciatan.md)<br/>
[_CIatan2](../../c-runtime-library/ciatan2.md)<br/>
