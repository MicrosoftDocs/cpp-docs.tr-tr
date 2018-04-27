---
title: atan, atanf, atanl, atan2, atan2f, atan2l | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1c17693a5f73ed7e755c69b5b2157d5de792c76
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="atan-atanf-atanl-atan2-atan2f-atan2l"></a>atan, atanf, atanl, atan2, atan2f, atan2l

Tanjantını hesaplar **x** (**atan**, **atanf**, ve **atanl**) veya arktanjantını **y** / **x** (**atan2**, **atan2f**, ve **atan2l**).

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

**atan** arktanjantını döndürür *x* π/2 radyan için aralığı - π/2. **ATAN2** arktanjantını döndürür *y*/*x* π radyan için bir aralığı - π içinde. Varsa *x* 0 ' dır **atan** 0 döndürür. Varsa, her iki parametre **atan2** 0, 0 işlevi döndürür. Tüm sonuçlar radyan cinsinden olur.

**ATAN2** parametrelerinin her ikisini de belirtileri dönüş değeri çeyreğinde belirlemek için kullanır.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± **QNAN**, **UL**|yok|**_DOMAIN**|

## <a name="remarks"></a>Açıklamalar

**Atan** işlevi hesaplar arktanjantını (Ters Tanjant işlevi) *x*. **ATAN2** arktanjantını hesaplar *y*/*x* (varsa *x* eşittir 0, **atan2** π/2 döndürür *y* pozitifse - π/2 IF *y* negatif veya 0 ise *y* 0'dır.)

**atan** Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulamaya sahip. Bilgi ve kısıtlamaları SSE2 uygulama kullanımı hakkında bkz [_set_SSE2_enable](set-sse2-enable.md).

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **atan** ve **atan2** Süren **float** veya **uzun** **çift**  bağımsız değişkenler. Bir C programı **atan** ve **atan2** her zaman **çift** bağımsız değişkenleri ve dönüş bir **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üstbilgisi (C)|Gerekli üstbilgisi (C++)|
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
[Sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[Bronz, tanf, tanl](tan-tanf-tanl.md)<br/>
[_CIatan](../../c-runtime-library/ciatan.md)<br/>
[_CIatan2](../../c-runtime-library/ciatan2.md)<br/>
