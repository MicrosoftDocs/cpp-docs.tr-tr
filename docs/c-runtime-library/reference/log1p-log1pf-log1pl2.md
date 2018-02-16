---
title: log1p, log1pf, log1pl2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- log1p
- log1pf
- log1pl
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
- log1p
- log1pf
- log1pl
- math/log1p
- math/log1pf
- math/log1pl
helpviewer_keywords:
- log1p function
- log1pf function
- log1pl function
ms.assetid: a40d965d-b4f6-42f4-ba27-2395546f7c12
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f99c09efd055cc60162e88e52e938df690929a1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="log1p-log1pf-log1pl"></a>log1p, log1pf, log1pl
1 artı belirtilen değere doğal logaritmasını hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double log1p(  
   double x  
);  
  
float log1p(  
   float x  
); //C++ only  
  
long double log1p(  
   long double x  
); //C++ only  
  
float log1pf(  
   float x  
);  
  
long double log1pl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `x`  
 Kayan nokta bağımsız değişken.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, doğal (e tabanında) günlüğü döndürür (`x`+ 1).  
  
 Aksi takdirde, aşağıdaki değerlerden birini döndürebilir:  
  
|Giriş|Sonuç|SEH özel durumu|errno|  
|-----------|------------|-------------------|-----------|  
|+ INF|+ INF|||  
|Denormals|Aynı giriş|UNDERFLOW||  
|±0|Aynı giriş|||  
|-1|-INF|DIVBYZERO|ERANGE|  
|< -1|NaN|GEÇERSİZ|EDOM|  
|-INF|NaN|GEÇERSİZ|EDOM|  
|±SNaN|Aynı giriş|GEÇERSİZ||  
|±QNaN belirsiz|Aynı giriş|||  
  
 `errno` Değer ayarlanmışsa ERANGE için `x` = -1. `errno` Değer ayarlanmışsa EDOM için `x` < -1.  
  
## <a name="remarks"></a>Açıklamalar  
 `log1p` İşlevleri günlük kullanmaktan daha doğru (`x`+ 1) x 0 olduğunda.  
  
 Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz `log1p` alın ve float ve uzun çift türleri döndürür. Bir C programı `log1p` her zaman alır ve bir double döndürür.  
  
 Varsa `x` doğal sayı, bu işlev çarpımını logaritmasını döndürür (`x`-1).  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|C üstbilgisi|C++ üstbilgi|  
|--------------|--------------|------------------|  
|`log1p`,                `log1pf`,  `log1pl`|\<Math.h >|\<cmath >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log2, log2f, log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)