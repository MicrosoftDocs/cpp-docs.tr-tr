---
title: "Günlük, logf, log10, log10f | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- log10f
- logf
- log10
- log
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
- logf
- _log10l
- log
- _logl
- log10f
- log10
dev_langs:
- C++
helpviewer_keywords:
- calculating logarithms
- log10f function
- log10 function
- log function
- logf function
- logarithms
ms.assetid: 7adc77c2-04f7-4245-a980-21215563cfae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5e18cd4c602940884eec13a3b1650afe738acd66
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="log-logf-log10-log10f"></a>log, logf, log10, log10f
Logaritma hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      double log(  
   double x   
);  
float log(  
   float x  
);  // C++ only  
long double log(  
   long double x  
);  // C++ only  
float logf(  
   float x   
);  
double log10(  
   double x  
);  
float log10(  
   float x  
);  // C++ only  
long double log10(  
   long double x  
);  // C++ only  
float log10f (  
   float x  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *x*  
 Logaritmasını bulunacak değerdir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **Günlük** işlevler (e tabanında) doğal logaritmasını döndürür *x* başarılı olursa. Log10 işlevler 10 tabanında logaritmasını döndürür. Varsa *x* olan negatif, bu işlevler bir belirsiz, varsayılan olarak döndürür. Varsa *x* 0 olduğundan, bunlar INF (sonsuz) döndürür.  
  
|Giriş|SEH özel durumu|Matherr özel durumu|  
|-----------|-------------------|-----------------------|  
|± QNAN, UL|yok|_DOMAIN|  
|± 0|ZERODIVIDE|_SING|  
|x < 0|GEÇERSİZ|_DOMAIN|  
  
 **Günlük** ve `log10` Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulamaya sahip. Bkz: [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md) ilgili bilgileri ve SSE2 uygulama kullanılmasındaki kısıtlamalar.  
  
## <a name="remarks"></a>Açıklamalar  
 C++ verir aşırı yüklemesi, aşırı çağırması **günlük** ve `log10`. Bir C programı **günlük** ve `log10` her zaman almak ve bir double döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|**log**, `logf`, `log10`, `log10f`|\<Math.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_log.c  
/* This program uses log and log10  
 * to calculate the natural logarithm and  
 * the base-10 logarithm of 9,000.  
 */  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 9000.0;  
   double y;  
  
   y = log( x );  
   printf( "log( %.2f ) = %f\n", x, y );  
   y = log10( x );  
   printf( "log10( %.2f ) = %f\n", x, y );  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
log( 9000.00 ) = 9.104980  
log10( 9000.00 ) = 3.954243  
```  
  
 Logaritma diğer temelleri için oluşturmak için matematiksel ilişkisi kullanın: temel b oturum bir (a) doğal günlük == / doğal (b) oturum açın.  
  
```  
// logbase.cpp  
#include <math.h>  
#include <stdio.h>  
  
double logbase(double a, double base)  
{  
   return log(a) / log(base);  
}  
  
int main()  
{  
   double x = 65536;  
   double result;  
  
   result = logbase(x, 2);  
   printf("Log base 2 of %lf is %lf\n", x, result);  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
Log base 2 of 65536.000000 is 16.000000  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [exp, expf, expl](../../c-runtime-library/reference/exp-expf.md)   
 [_matherr](../../c-runtime-library/reference/matherr.md)   
 [POW, powf, powl](../../c-runtime-library/reference/pow-powf-powl.md)   
 [_CIlog](../../c-runtime-library/cilog.md)   
 [_CIlog10](../../c-runtime-library/cilog10.md)