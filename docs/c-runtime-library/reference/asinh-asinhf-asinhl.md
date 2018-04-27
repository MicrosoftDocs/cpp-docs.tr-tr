---
title: ASİNH, asinhf, asinhl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- asinh
- asinhf
- asinhl
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
- asinhf
- asinhl
- asinh
dev_langs:
- C++
helpviewer_keywords:
- asinh function
- asinhl function
- asinhf function
ms.assetid: 4488babe-1a7e-44ca-8b7b-c2db0a70084f
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 50cd387f2c943d407dd11fe2e191457314f5cba9
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="asinh-asinhf-asinhl"></a>asinh, asinhf, asinhl

Ters hiperbolik sinüsünü hesaplar.

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

**Asinh** işlevler (Ark hiperbolik sinüsü) ters hyberbolic sinüsünü döndürür *x*. Bu işlev kayan nokta etki alanı üzerinde geçerli değil. Varsa *x* sessiz NaN, belirsiz, ya da sonsuz, aynı değeri döndürülür.

|Giriş|SEH özel durumu|**_matherr** özel durumu|
|-----------|-------------------|--------------------------|
|± QNAN, UL, INF|yok|yok|

## <a name="remarks"></a>Açıklamalar

C++ kullandığınızda, aşırı çağırabilirsiniz **asinh** alın ve dönüş **float** veya **uzun** **çift** değerleri. Bir C programı **asinh** her zaman alan ve döndüren **çift**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|
|--------------|--------------|------------------|
|**ASİNH**, **asinhf**, **asinhl**|\<Math.h >|\<cmath > veya \<math.h <|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
[COSH, coshf, coshl](cosh-coshf-coshl.md)<br/>
[SİNH, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[TANH, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
