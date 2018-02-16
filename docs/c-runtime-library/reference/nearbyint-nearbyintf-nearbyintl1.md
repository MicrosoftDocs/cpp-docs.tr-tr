---
title: nearbyint, nearbyintf, nearbyintl | Microsoft Docs
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
- nearbyint
- nearbyintf
- nerabyintl
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
- nearbyint
- nearbyintf
- nearbyintl
- math/nearbyint
- math/narbyintf
- math/narbyintl
dev_langs:
- C++
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6c4cce9fb5d95da5e65a064d622da22e4d0f0a8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint, nearbyintf, nearbyintl
Belirtilen kayan nokta değeri tamsayıya yuvarlar ve bu değer bir kayan nokta biçiminde döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
double nearbyint(  
   double x  
);  
  
float nearbyint(  
   float x  
); //C++ only  
  
long double nearbyint(  
   long double x  
); //C++ only  
  
float nearbyintf(  
   float x  
);  
  
long double nearbyintl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `x`  
 Yuvarlanacak değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `x`, fegetround tarafından tanımlanan geçerli yuvarlama biçimini kullanarak en yakın tamsayıya yuvarlanır. Aksi takdirde işlevi aşağıdaki değerlerden birini döndürebilir:  
  
|Sorun|Döndür|  
|-----------|------------|  
|`x` = ±INFINITY|Değiştirilmemiş ±INFINITY|  
|`x` = ±0|değiştirilmemiş ±0|  
|`x` = NaN|NaN|  
  
 Hataları bildirilmedi aracılığıyla [_matherr](../../c-runtime-library/reference/matherr.md); özellikle, bu işlev FE_INEXACT özel durumlar bildirmiyor.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev arasındaki birincil fark ve `rint` olduğundan bu işlevi kesin olmayan kayan nokta özel durumu oluşturmaz.  
  
 En fazla kayan nokta değerlerine tam tamsayılar olduğundan, bu işlev hiçbir zaman tek başına taşması; Bunun yerine, çıkışı işlevi sürümüne bağlı olarak, kullandığınız dönüş değeri taşma.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|C üstbilgisi|C++ üstbilgi|  
|--------------|--------------|------------------|  
|`nearbyint`,                `nearbyintf`,  `nearbyintl`|\<Math.h >|\<cmath >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik İşlev Başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)