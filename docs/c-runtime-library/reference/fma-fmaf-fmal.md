---
title: FMA, fmaf, fmal | Microsoft Docs
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
- fma
- fmaf
- fmal
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
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
dev_langs:
- C++
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 21eab7d0adc6cf1952f6f26cdda23c885c63a3b3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fma-fmaf-fmal"></a>fma, fmaf, fmal
İki değerin birbirine çarpar, üçüncü değer ekler ve ardından sonucu Ara yuvarlama nedeniyle herhangi duyarlık kaybetmeden yuvarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double fma(  
   double x,   
   double y,   
   double z  
);  
  
float fma(  
   float  x,   
   float  y,   
   float z  
); //C++ only  
  
long double fma(  
   long double  x,   
   long double  y,   
   long double z  
); //C++ only  
  
float fmaf(  
   float  x,   
   float  y,   
   float z  
);  
  
long double fmal(  
   long double  x,   
   long double  y,   
   long double z  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `x`  
 Çarp ilk değeri.  
  
 [in] `y`  
 Çarp ikinci değer.  
  
 [in] `z`  
 Eklenecek değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür `(x * y) + z`. Dönüş değeri geçerli yuvarlama biçimini kullanarak yuvarlanır.  
  
 Aksi takdirde, aşağıdaki değerlerden birini döndürebilir:  
  
|Sorun|Döndür|  
|-----------|------------|  
|`x` = SONSUZ, `y` = 0 veya<br /><br /> `x` = 0, `y` = INFINITY|NaN|  
|`x` veya `y` = tam ± SONSUZ, `z` SONSUZ = ters işaretli|NaN|  
|`x` veya `y` NaN =|NaN|  
|değil (`x` = 0, `y`belirsiz =) ve `z` NaN =<br /><br /> değil (`x`belirsiz = `y`= 0) ve `z` NaN =|NaN|  
|taşma aralık hatası|±HUGE_VAL, ±HUGE_VALF veya ±HUGE_VALL|  
|Underflow aralık hatası|Yuvarlama sonra doğru değeri.|  
  
 Hataları raporlanır belirtilmiş [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz `fma` alın ve dönüş **float** ve **uzun çift** türleri. Bir C programı `fma` her zaman alan ve döndüren bir **çift**.  
  
 Bu işlev sonsuz duyarlık gerçekleştirilen ve son sonucu yuvarlar gibi sorgulamanıza değeri hesaplar.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|C üstbilgisi|C++ üstbilgi|  
|--------------|--------------|------------------|  
|`fma`, `fmaf`, `fmal`|\<Math.h >|\<cmath >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [kalan, remainderf, remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)   
 [remquo, remquof, remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)