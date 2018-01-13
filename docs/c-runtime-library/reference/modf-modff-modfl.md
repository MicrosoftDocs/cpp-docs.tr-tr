---
title: modf, modff, modfl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- modff
- modf
- modfl
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
- modff
- _modfl
- modf
- modfl
- math/modf
- math/modff
- math/modfl
dev_langs: C++
helpviewer_keywords:
- modf function
- modff function
- modfl function
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a75cc474d66a42f3faeb7444f3168c7cc3283514
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="modf-modff-modfl"></a>modf, modff, modfl
Bir kayan nokta değeri kesirli ve tamsayı bölümleri böler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double modf(  
   double x,  
   double * intptr   
);  
float modf(  
   float x,  
   float * intptr  
);  // C++ only  
long double modf(  
   long double x,  
   long double * intptr  
);  // C++ only  
float modff(  
   float x,  
   float * intptr   
);  
long double modfl(  
   long double x,  
   long double * intptr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *x*  
 Kayan nokta değeri.  
  
 `intptr`  
 Saklı tamsayı bölümü işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlev imzalı kesirli kısmını döndürür *x*. Döndürülen hata yoktur.  
  
## <a name="remarks"></a>Açıklamalar  
 `modf` İşlevleri bölün kayan nokta değeri `x` kesirli içine ve her birinin olan aynı işarete tamsayı bölümleri `x`. İmzalı kesirli kısmı `x` döndürülür. Tamsayı bölümü bir kayan nokta değeri olarak depolanır`intptr.`  
  
 `modf`Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulama vardır. Bkz: [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md) ilgili bilgileri ve SSE2 uygulama kullanılmasındaki kısıtlamalar.  
  
 C++ verir aşırı yüklemesi, aşırı çağırması `modf` alın ve dönüş `float` veya `long double` parametreleri. Bir C programı `modf` her zaman iki çift değerlerini alır ve bir double değeri döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`modf`, `modff`, `modfl`|C: \<math.h ><br /><br /> C++:, \<cmath > veya \<math.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_modf.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y, n;  
  
   x = -14.87654321;      /* Divide x into its fractional */  
   y = modf( x, &n );     /* and integer parts            */  
  
   printf( "For %f, the fraction is %f and the integer is %.f\n",   
           x, y, n );  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
For -14.876543, the fraction is -0.876543 and the integer is -14  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)