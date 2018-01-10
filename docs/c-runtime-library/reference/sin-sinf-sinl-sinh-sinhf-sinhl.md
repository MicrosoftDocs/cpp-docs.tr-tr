---
title: Sin, sinf, sinl, sinh, sinhf, sinhl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- sinl
- sinf
- sinhf
- sinh
- sin
- sinhl
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
- _sinl
- sinf
- sinhl
- sinl
- sin
- sinhf
- _sinhl
dev_langs: C++
helpviewer_keywords:
- sinh function
- _sinl function
- _sinhl function
- sinhf function
- sinl function
- calculating sines
- sin function
- trigonometric functions
- sinf function
- sinhl function
- hyperbolic functions
ms.assetid: 737de73e-3590-45f9-8257-dc1c0c489dfc
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: de4f4914589c5803733bdcd279b3d0a3fa00e360
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="sin-sinf-sinl-sinh-sinhf-sinhl"></a>sin, sinf, sinl, sinh, sinhf, sinhl
Sinüsü ve hiperbolik sinüsü hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double sin(  
   double x   
);  
float sin(  
   float x  
);  // C++ only  
long double sin(  
   long double x  
);  // C++ only  
float sinf(  
   float x   
);  
long double sinl(   long double x  
);  
double sinh(  
   double x   
);  
float sinh(  
   float x   
);  // C++ only  
long double sinh(  
   long double x  
);  // C++ only  
float sinhf(  
   float x  
);  
long double sinhl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `x`  
 Radyan cinsinden açı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `sin` İşlevleri sinüsünü Döndür `x`. Varsa `x` büyük veya 263 eşit veya daha az veya buna eşit -263, sonuç anlamlı kaybı oluşur.  
  
 `sinh` İşlevler hiperbolik sinüsünü döndürür `x`. Varsayılan olarak sonucu çok büyük ise, `sinh` ayarlar `errno` için `ERANGE` ve döndürür ±`HUGE_VAL`.  
  
|Giriş|SEH özel durumu|Matherr özel durumu|  
|-----------|-------------------|-----------------------|  
|± QNAN, UL|Yok.|_DOMAIN|  
|± ∞ (sin, sinf, sinl)|GEÇERSİZ|_DOMAIN|  
|&#124; x &#124; ≥ 7.104760e + 002 (sinh, sinhf, sinhl)|TAŞMA + FİLTRESİNİN|TAŞMA|  
  
 Dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz `sin` ve `sinh` alın ve dönüş `float` veya `long double` değerleri. Bir C programı `sin` ve `sinh` her zaman alın ve dönüş `double`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`sin`, `sinf`, `sinl`, `sinh`, `sinhf`, `sinhl`|\<Math.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_sincos.c  
// This program displays the sine, hyperbolic  
// sine, cosine, and hyperbolic cosine of pi / 2.  
//  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double pi = 3.1415926535;  
   double x, y;  
  
   x = pi / 2;  
   y = sin( x );  
   printf( "sin( %f ) = %f\n", x, y );  
   y = sinh( x );  
   printf( "sinh( %f ) = %f\n",x, y );  
   y = cos( x );  
   printf( "cos( %f ) = %f\n", x, y );  
   y = cosh( x );  
   printf( "cosh( %f ) = %f\n",x, y );  
}  
```  
  
```Output  
sin( 1.570796 ) = 1.000000  
sinh( 1.570796 ) = 2.301299  
cos( 1.570796 ) = 0.000000  
cosh( 1.570796 ) = 2.509178  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [ACOS, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [Tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [_CIsin](../../c-runtime-library/cisin.md)