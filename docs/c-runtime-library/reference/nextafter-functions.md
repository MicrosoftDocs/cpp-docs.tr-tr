---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
dev_langs: C++
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 798e39624c617d8178a7598e74451ca2851cfe12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="nextafter-nextafterf-nextafterl-nextafter-nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
Sonraki gösterilebilir kayan nokta değeri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double nextafter(  
   double x,  
   double y   
);  
  
float nextafter(  
   float x,  
   float y   
); /* C++ only, requires <cmath> */  
  
long double nextafter(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nextafterf(  
   float x,  
   float y   
);   
  
long double nextafterl(  
   long double x,  
   long double y   
);  
  
double _nextafter(  
   double x,  
   double y   
);  
  
float _nextafterf(  
   float x,  
   float y   
); /* x64 only */  
  
double nexttoward(  
   double x,  
   long double y   
);  
  
float nexttoward(  
   float x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
long double nexttoward(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nexttowardf(  
   float x,  
   long double y   
);   
  
long double nexttowardl(  
   long double x,  
   long double y   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `x`  
 Başlamak için kayan nokta değeri.  
  
 `y`  
 Doğru gitmek için kayan nokta değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dönüş türü sonra sonraki gösterilebilir kayan nokta değerini döndürür `x` yönünde `y`. Varsa `x` = `y`, işlevi döndürür `y`, dönüş türüyle tetiklenen durum dönüştürülür. Varsa `x` eşit değil `y`ve sonucu bir denormal veya sıfır olan, FE_UNDERFLOW ve FE_INEXACT kayan nokta özel durumlarını ayarlayın ve doğru bir sonuç döndürdü. Her iki `x` veya `y` dönüş değeri giriş NaN biri bir NAN olduğundan. Varsa `x` sınırlıdır ve sonucu sonsuz veya türünde gösterilebilir değil, doğru şekilde imzalanmış sonsuz veya NAN döndürülür, FE_OVERFLOW ve FE_INEXACT kayan nokta özel durumları olarak ayarlanır, ve `errno` ERANGE için ayarlanır.  
  
## <a name="remarks"></a>Açıklamalar  
 `nextafter` Ve `nexttoward` işlevi aileleri dışında parametre türü eşdeğer `y`. Varsa `x` ve `y` döndürülen değer eşit olan `y` dönüş türüne dönüştürülemiyor.  
  
 Aşırı yüklemesi, C++ dahil ederseniz izin verdiğinden \<cmath > aşırı çağırabilirsiniz `nextafter` ve `nexttoward` bu iade `float` ve `long double` türleri. Bir C programı `nextafter` ve `nexttoward` her zaman geri `double`.  
  
 `_nextafter` Ve `_nextafterf` Microsoft belirli işlevlerdir. `_nextafterf` İşlevi yalnızca kullanılabilir x64 için derlerken.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli üstbilgisi (C)|Gerekli üstbilgisi (C++)|  
|-------------|---------------------------|-------------------------------|  
|`nextafter`, `nextafterf`, `nextafterl`, `_nextafterf`, `nexttoward`, `nexttowardf`, `nexttowardl`|\<Math.h >|\<Math.h > veya \<cmath >|  
|`_nextafter`|\<float.h >|\<float.h > veya \<cfloat >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)