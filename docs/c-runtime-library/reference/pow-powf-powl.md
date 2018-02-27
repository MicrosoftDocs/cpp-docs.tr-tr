---
title: POW, powf, powl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- powl
- pow
- powf
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
- powl
- pow
- _powl
- powf
dev_langs:
- C++
helpviewer_keywords:
- exponential calculations
- powl function
- _powl function
- exponentiation
- powers, calculating
- calculating exponentials
- powf function
- pow function
ms.assetid: e75c33ed-2e59-48b1-be40-81da917324f1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 09b618e557fffadd3bfffb431fc7e89458c4f420
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="pow-powf-powl"></a>pow, powf, powl
Hesaplar `x` üssünü `y`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double pow(  
   double x,  
   double y   
);  
double pow(  
   double x,  
   int y  
);  // C++ only  
float pow(  
   float x,  
   float y   
);  // C++ only  
float pow(  
   float x,  
   int y  
);  // C++ only  
long double pow(  
   long double x,  
   long double y  
);  // C++ only  
long double pow(  
   long double x,  
   int y  
);  // C++ only  
float powf(  
   float x,  
   float y   
);  
long double powl(  
   long double x,  
   long double y  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `x`  
 Tabanı.  
  
 `y`  
 Üs.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Değerini döndürür `x` <sup>y</sup>. Hata iletisi taşması veya underflow yazdırılır.  
  
|X değerleri ve y|Pow dönüş değeri|  
|-----------------------|-------------------------|  
|`x` \< > 0 ve `y` 0,0 =|1.|  
|`x` 0,0 = ve `y` 0,0 =|1.|  
|`x` 0,0 = ve `y` < 0|INF|  
  
## <a name="remarks"></a>Açıklamalar  
 `pow` 2'den büyük tam sayı kayan nokta değerlerine tanımıyor<sup>64</sup> (örneğin, `1.0E100`).  
  
 `pow` Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulama vardır. Bilgi ve kısıtlamaları SSE2 uygulama kullanımı hakkında bkz [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
 Aşırı yükleme C++ izin verdiğinden, çeşitli aşırı hiçbirini çağırabilirsiniz `pow`. Bir C programı `pow` her zaman iki çift değerlerini alır ve bir double değeri döndürür.  
  
 `pow(int, int)` Aşırı kullanılabilir artık. Bu aşırı kullanırsanız, derleyici C2668 yayabilir. Bu sorunu önlemek için ilk parametre olarak cast `double`, `float`, veya `long double`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`pow`, `powf`, `powl`|\<Math.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_pow.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.0, y = 3.0, z;  
  
   z = pow( x, y );  
   printf( "%.1f to the power of %.1f is %.1f\n", x, y, z );  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
2.0 to the power of 3.0 is 8.0  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [exp, expf, expl](../../c-runtime-library/reference/exp-expf.md)   
 [Günlük, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [sqrt, sqrtf, sqrtl](../../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)   
 [_CIpow](../../c-runtime-library/cipow.md)