---
title: asinh, asinhf, asinhl
ms.date: 04/05/2018
api_name:
- asinh
- asinhf
- asinhl
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- asinhf
- asinhl
- asinh
helpviewer_keywords:
- asinh function
- asinhl function
- asinhf function
ms.assetid: 4488babe-1a7e-44ca-8b7b-c2db0a70084f
ms.openlocfilehash: f4d93f121c0124293a5bdff9041d0adfaab5d83c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939649"
---
# <a name="asinh-asinhf-asinhl"></a>asinh, asinhf, asinhl

Ters hiperbolik sinüsü hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double asinh( double x );
float asinhf( float x );
long double asinhl( long double x );
```

```cpp
float asinh( float x );  // C++ only
long double asinh( long double x );  // C++ only
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**ASİNH** işlevleri, *x*'in ters hyberbolik sinüsü (Ark hiperbolik sinüs) döndürür. Bu işlev, kayan nokta etki alanı üzerinde geçerlidir. *X* sessiz bir NaN, sonsuz veya sonsuz ise, aynı değer döndürülür.

|Giriş|SEH özel durumu|**_matherr** Duruma|
|-----------|-------------------|--------------------------|
|± QNAN, IND, INF|yok|yok|

## <a name="remarks"></a>Açıklamalar

Kullandığınızda C++, **ASİNH** 'nin **float** veya **Long** **Double** değerleri alıp döndüren aşırı yüklerini çağırabilirsiniz. C programında, **ASİNH** her zaman **Double**alır ve döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli C üstbilgisi|Gerekli C++ üst bilgi|
|--------------|--------------|------------------|
|**ASİNH**, **asınhf**, **asinhl**|\<Math. h >|\<cmath > veya \<Math. h <|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_asinh.c
// Compile by using: cl /W4 crt_asinh.c
// This program displays the hyperbolic sine of pi / 4
// and the arc hyperbolic sine of the result.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x, y;

   x = sinh( pi / 4 );
   y = asinh( x );
   printf( "sinh( %f ) = %f\n", pi/4, x );
   printf( "asinh( %f ) = %f\n", x, y );
}
```

```Output
sinh( 0.785398 ) = 0.868671
asinh( 0.868671 ) = 0.785398
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[cosh, coshf, coshl](cosh-coshf-coshl.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
