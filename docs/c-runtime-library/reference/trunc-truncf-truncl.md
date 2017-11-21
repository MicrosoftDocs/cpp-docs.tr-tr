---
title: trunc, truncf, truncl | Microsoft Docs
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
- trunc
- truncf
- truncl
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
- trunc
- truncf
- truncl
- math/trunc
- math/truncf
- math/truncl
dev_langs: C++
helpviewer_keywords:
- trunc function
- truncf function
- truncl function
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b2a78deabb758a7d8fe8b0da61899bf7ad11dd8f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="trunc-truncf-truncl"></a>trunc, truncf, truncl
Küçük veya bu değere eşit belirtilen kayan nokta en yakın tamsayıya belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double trunc(  
   double x  
);  
  
float trunc(  
   float x  
); //C++ only  
  
long double trunc(  
   long double x  
); //C++ only  
  
float trunc(  
   float x  
); //C++ only  
  
long double truncl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`x`  
 Kesmek için değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, tamsayı değerini döndürür `x`, yuvarlak sıfır bulunun.  
  
 Aksi takdirde, aşağıdakilerden birini döndürebilir:  
  
|Sorun|Döndür|  
|-----------|------------|  
|`x`±INFINITY =|x|  
|`x` =  ±0|x|  
|`x`= NaN|NaN|  
  
 Hataları raporlanır belirtilmiş [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz `trunc` alın ve float ve uzun çift türleri döndürür. Bir C programı `trunc` her zaman alır ve bir double döndürür.  
  
 En büyük kayan nokta değerlerine tam tamsayılar olduğundan, bu işlev, kendi taşma değil. Ancak, işlevi tamsayı türde bir değer döndürerek taşmasına neden olabilir.  
  
 Ayrıca örtük olarak kayan nokta için tam sayı dönüştürerek yuvarlamak; Ancak, bunun nedenle hedef türü depolanan değerlerin sınırlıdır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|C üstbilgisi|C++ üstbilgi|  
|--------------|--------------|------------------|  
|`trunc`,                `truncf`,  `truncl`|\<Math.h >|\<cmath >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)