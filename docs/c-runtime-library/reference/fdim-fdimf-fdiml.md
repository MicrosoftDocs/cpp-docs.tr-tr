---
title: fdim, fdimf, fdiml | Microsoft Docs
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
- fdim
- fdimf
- fdiml
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
- fdim
- fdimf
- fdiml
- math/fdim
- math/fdimf
- math/fdiml
dev_langs:
- C++
helpviewer_keywords:
- fdim function
- fdimf function
- fdiml function
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 60e628f84dcadf7b1e214d526981191036428042
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fdim-fdimf-fdiml"></a>fdim, fdimf, fdiml
Pozitif değerler arasındaki farkın birinci ve ikinci belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double fdim(  
   double x,   
   double y  
);  
  
float fdim(  
   float x,   
   float y  
); //C++ only  
  
long double fdim(  
   long double x,   
   long double y  
); //C++ only  
  
float fdimf(  
   float x,   
   float y  
);  
  
long double fdiml(  
   long double x,   
   long double y  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `x`  
 İlk değer.  
  
 [in] `y`  
 İkinci değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Pozitif birbirinden döndürür `x` ve `y`:  
  
|Dönüş değeri|Senaryo|  
|------------------|--------------|  
|x-y|if x > y|  
|0|if x <= y|  
  
 Aksi takdirde, aşağıdaki hatalardan biri döndürebilir:  
  
|Sorun|Döndür|  
|-----------|------------|  
|taşma aralık hatası|+ HUGE_VAL + HUGE_VALF, veya + HUGE_VALL|  
|Underflow aralık hatası|(sonra yuvarlama) doğru değeri|  
|`x` veya `y` NaN olup|NaN|  
  
 Hataları raporlanır belirtilmiş [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz `fdim` alın ve float ve uzun çift türleri döndürür. Bir C programı `fdim` her zaman alır ve bir double döndürür.  
  
 NaN işleme dışında bu işlev eşdeğerdir `fmax(x - y, 0)`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|C üstbilgisi|C++ üstbilgi|  
|--------------|--------------|------------------|  
|`fdim`, `fdimf`, `fdiml`|\<Math.h >|\<cmath >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmax, fmaxf, fmaxl](../../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)   
 [abs, labs, llabs, _abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)