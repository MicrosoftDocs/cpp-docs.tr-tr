---
title: hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _hypotf
- hypot
- hypotf
- _hypot
- _hypotl
- hypotl
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
- hypotf
- hypotl
- _hypotl
- hypot
- _hypot
- _hypotf
dev_langs: C++
helpviewer_keywords:
- hypotenuse calculation
- hypot function
- hypotf function
- triangles, calculating hypotenuse
- hypotl function
- calculating hypotenuses
- _hypot function
ms.assetid: 6a13887f-bd53-43fc-9d77-5b42d6e49925
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 99cf5168eba3ed03b4e91571cd50a3c6c4bf9afe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="hypot-hypotf-hypotl-hypot-hypotf-hypotl"></a>hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl
Hipotenüsü hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double hypot(   
   double x,  
   double y   
);  
float hypotf(   
   float x,  
   float y   
);  
long double hypotl(  
   long double x,  
   long double y  
);  
double _hypot(   
   double x,  
   double y   
);  
float _hypotf(   
   float x,  
   float y   
);  
long double _hypotl(  
   long double x,  
   long double y  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `x`, `y`  
 Kayan nokta değerleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, `hypot` hipotenüsü; taşmaya uzunluğunu döndürür `hypot` INF (sonsuz) döndürür ve `errno` değişken ayarlandığında `ERANGE`. Kullanabileceğiniz `_matherr` hata işleme değiştirmek için.  
  
 Dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `hypot` İşlevler hesapla iki kenara uzunluğu belirtilen bir sağ üçgen hipotenüsü uzunluğu `x` ve `y` (diğer bir deyişle, kare kökünü `x` <sup>2</sup>  +  `y` <sup>2</sup>).  
  
 Önde gelen alt çizgi olan işlevler sürümleri önceki standartları ile uyumluluk için sağlanır. Davranışlarını başında alt çizgi sahip olmayan sürümleri için aynıdır. Önde gelen alt çizgi olmadan sürümleri için yeni kod kullanmanızı öneririz.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`hypot`, `hypotf`, `hypotl`, `_hypot`, `_hypotf`, `_hypotl`|\<Math.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_hypot.c  
// This program prints the hypotenuse of a right triangle.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 3.0, y = 4.0;  
  
   printf( "If a right triangle has sides %2.1f and %2.1f, "  
           "its hypotenuse is %2.1f\n", x, y, _hypot( x, y ) );  
}  
```  
  
```Output  
If a right triangle has sides 3.0 and 4.0, its hypotenuse is 5.0  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [_cabs](../../c-runtime-library/reference/cabs.md)   
 [_matherr](../../c-runtime-library/reference/matherr.md)