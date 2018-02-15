---
title: _finite, _finitef | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _finite
- _finitef
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
- finite
- _finite
- _finitef
- math/_finite
- math/_finitef
- float/_finite
dev_langs:
- C++
helpviewer_keywords:
- finite function
- _finite function
- _finitef function
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eb904e04e8a99bff242d520f6c0ca3d404a74e89
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="finite-finitef"></a>_finite, _finitef
Kayan noktalı bir sayıyı sınırlı olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _finite(   
   double x   
);  
  
int _finitef(   
   float x   
); /* x64 and ARM/ARM64 only */  
```  
  
#### <a name="parameters"></a>Parametreler  
 `x`  
 Test etmek için kayan nokta değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Her ikisi de `_finite` ve `_finitef` sıfır olmayan bir değer döndürür bağımsız değişkeni *x* olduğu sınırlı; olduğundan, -INF < `x` < + INF. Bağımsız değişken sonsuz ise 0 veya bir NaN değerini döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_finite` Ve `_finitef` Microsoft belirli işlevlerdir. `_finitef` İşlevi, yalnızca kullanılabilir platformları ARM veya ARM64 x86 için derlenmiş.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli üstbilgisi (C)|Gerekli üstbilgisi (C++)|  
|--------------|---------------------------|-------------------------------|  
|`_finite`|\<float.h > veya \<math.h >|\<float.h >, \<math.h >, \<cfloat >, veya \<cmath >|  
|`_finitef`|\<Math.h >|\<Math.h > veya \<cmath >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [isNaN, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [_fpclass, _fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)