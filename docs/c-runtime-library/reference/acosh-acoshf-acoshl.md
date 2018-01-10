---
title: ACOSH, acoshf, acoshl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- acoshf
- acosh
- acoshl
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
- acosh
- acoshf
- acoshl
- math/acosh
- math/acoshf
- math/acoshl
dev_langs: C++
helpviewer_keywords:
- acoshf function
- acosh function
- acoshl function
ms.assetid: 6985c4d7-9e2a-44ce-9a9b-5a43015f15f7
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 44872bc2ad2ef2be8e9a91403852574c9047a051
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="acosh-acoshf-acoshl"></a>acosh, acoshf, acoshl
Ters hiperbolik kosinüsünü hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double acosh(  
   double x   
);  
float acosh(  
   float x   
);  // C++ only  
long double acosh(  
   long double x  
);  // C++ only  
float acoshf(  
   float x   
);  
long double acoshl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `x`  
 Kayan nokta değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `acosh` İşlevler (Ark hiperbolik kosinüsü) ters hyberbolic kosinüsünü döndürür `x`. Bu işlevler etki alanı üzerinde geçerli `x` ≥ 1. Varsa `x` 1'den, küçük `errno` ayarlanır `EDOM` ve sessiz NaN sonucudur. Varsa `x` sessiz NaN, belirsiz, ya da sonsuz, aynı değeri döndürülür.  
  
|Giriş|SEH özel durumu|`_matherr`Özel durumu|  
|-----------|-------------------|--------------------------|  
|± QNAN, UL, INF|yok|yok|  
|< 1 x|yok|yok|  
  
## <a name="remarks"></a>Açıklamalar  
 C++ kullandığınızda, aşırı çağırabilirsiniz `acosh` alın ve dönüş `float` veya `long double` değerleri. Bir C programı `acosh` her zaman alan ve döndüren `double`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|C üstbilgisi|C++ üstbilgi|  
|--------------|--------------|------------------|  
|`acosh`, `acoshf`, `acoshl`|\<Math.h >|\<cmath >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```C  
// crt_acosh.c  
// Compile by using: cl /W4 crt_acosh.c  
// This program displays the hyperbolic cosine of pi / 4  
// and the arc hyperbolic cosine of the result.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double pi = 3.1415926535;  
   double x, y;  
  
   x = cosh( pi / 4 );  
   y = acosh( x );  
   printf( "cosh( %f ) = %f\n", pi/4, x );  
   printf( "acosh( %f ) = %f\n", x, y );  
}  
```  
  
```Output  
cosh( 0.785398 ) = 1.324609  
acosh( 1.324609 ) = 0.785398  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [Sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [ASİNH, asinhf, asinhl](../../c-runtime-library/reference/asinh-asinhf-asinhl.md)   
 [Tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [ATANH, atanhf, atanhl](../../c-runtime-library/reference/atanh-atanhf-atanhl.md)   
 [_CItan](../../c-runtime-library/citan.md)