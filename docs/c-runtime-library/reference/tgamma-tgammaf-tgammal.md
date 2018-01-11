---
title: tgamma, tgammaf, tgammal | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- tgamma
- tgammaf
- tgammal
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
- tgamma
- tgammaf
- tgammal
- math/tgamma
- math/tgammaf
- math/tgammal
dev_langs: C++
helpviewer_keywords:
- tgamma function
- tgammaf function
- tgammal function
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fefaaaf6dd6e660c4cda53d28194d6052d1d8bf4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma, tgammaf, tgammal
Belirtilen değer Gama işlevinin belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double tgamma(  
   double x  
);  
  
float tgamma(  
   float x  
); //C++ only  
  
long double tgamma(  
   long double x  
); //C++ only  
  
float tgammaf(  
   float x  
);  
  
long double tgammal(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`x`  
 Gama, bulunacak değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, gama döndürür `x`.  
  
 Bir aralık hata oluşabilir büyüklüğünü `x` çok büyük ya da veri türü için çok küçük. Bir etki alanı hatası ya da aralık hatası ortaya çıkabilir `x` < = 0.  
  
|Sorun|Döndür|  
|-----------|------------|  
|x ±0 =|±INFINITY|  
|x = negatif tamsayı|NaN|  
|x = - SONSUZ|NaN|  
|x = + SONSUZ|+ SONSUZ|  
|x NaN =|NaN|  
|etki alanı hatası|NaN|  
|kutbu'na hata|±HUGE_VAL, ±HUGE_VALF veya ±HUGE_VALL|  
|taşma aralık hatası|±HUGE_VAL, ±HUGE_VALF veya ±HUGE_VALL|  
|Underflow aralık hatası|doğru değeri, yuvarlama sonra.|  
  
 Hataları raporlanır belirtilmiş [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Aşırı yükleme C++ izin verdiğinden, yapan ve float ve uzun çift türleri dönüş tgamma aşırı çağırabilirsiniz. Bir C programı tgamma her zaman alır ve bir double döndürür.  
  
 X doğal sayı ise, bu işlevi (x-1) çarpımını döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|C üstbilgisi|C++ üstbilgi|  
|--------------|--------------|------------------|  
|`tgamma`,                `tgammaf`,  `tgammal`|\<Math.h >|\<cmath >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [lgamma, lgammaf, lgammal](../../c-runtime-library/reference/lgamma-lgammaf-lgammal.md)