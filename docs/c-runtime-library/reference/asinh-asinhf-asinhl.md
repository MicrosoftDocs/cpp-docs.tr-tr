---
title: "ASİNH, asinhf, asinhl | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- asinh function
- asinhl function
- asinhf function
ms.assetid: 4488babe-1a7e-44ca-8b7b-c2db0a70084f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cd9e19a9729f53aae9f3a4fd32787a9ae02eae7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="asinh-asinhf-asinhl"></a>asinh, asinhf, asinhl
Ters hiperbolik sinüsünü hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double asinh(  
   double x   
);  
float asinh(  
   float x   
);  // C++ only  
long double asinh(  
   long double x  
);  // C++ only  
float asinhf(  
   float x   
);  
long double asinhl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `x`  
 Kayan nokta değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `asinh` İşlevler (Ark hiperbolik sinüsü) ters hyberbolic sinüsünü döndürür `x`. Bu işlev kayan nokta etki alanı üzerinde geçerli değil. Varsa `x` sessiz NaN, belirsiz, ya da sonsuz, aynı değeri döndürülür.  
  
|Giriş|SEH özel durumu|`_matherr`Özel durumu|  
|-----------|-------------------|--------------------------|  
|± QNAN, UL, INF|yok|yok|  
  
## <a name="remarks"></a>Açıklamalar  
 C++ kullandığınızda, aşırı çağırabilirsiniz `asinh` alın ve dönüş `float` veya `long double` değerleri. Bir C programı `asinh` her zaman alan ve döndüren `double`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|C üstbilgisi|C++ üstbilgi|  
|--------------|--------------|------------------|  
|`asinh`, `asinhf`, `asinhl`|\<Math.h >|\<cmath >|  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [ACOSH, acoshf, acoshl](../../c-runtime-library/reference/acosh-acoshf-acoshl.md)   
 [Sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [Tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [ATANH, atanhf, atanhl](../../c-runtime-library/reference/atanh-atanhf-atanhl.md)   
 [_CItan](../../c-runtime-library/citan.md)