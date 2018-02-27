---
title: _fpclass, _fpclassf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _fpclass
- _fpclassf
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
- fpclass
- _fpclass
- _fpclassf
- math/_fpclass
- float/_fpclass
- math/_fpclassf
dev_langs:
- C++
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a13abc84cf3e28f6282bf5c160d118d019334cfd
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fpclass-fpclassf"></a>_fpclass, _fpclassf
Kayan nokta sınıflandırma bağımsız değişkenin belirten bir değer döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _fpclass(   
   double x   
);  
  
int _fpclassf(   
   float x   
); /* x64 only */  
```  
  
#### <a name="parameters"></a>Parametreler  
 `x`  
 Test etmek için kayan nokta değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_fpclass` Ve `_fpclassf` işlevleri bağımsız değişkenin kayan nokta sınıflandırma belirten bir tamsayı değeri döndürmek `x`. Sınıflandırma tanımlanan aşağıdaki değerlerden birine sahip \<float.h >.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`_FPCLASS_SNAN`|NaN sinyali|  
|`_FPCLASS_QNAN`|Sessiz NaN|  
|`_FPCLASS_NINF`|Negatif sonsuz (-INF)|  
|`_FPCLASS_NN`|Sıfır olmayan negatif normalleştirilmiş|  
|`_FPCLASS_ND`|Normal dışı negatif|  
|`_FPCLASS_NZ`|Negatif sıfır (- 0)|  
|`_FPCLASS_PZ`|Pozitif 0 (+ 0)|  
|`_FPCLASS_PD`|Normal dışı pozitif|  
|`_FPCLASS_PN`|Sıfır olmayan pozitif normalleştirilmiş|  
|`_FPCLASS_PINF`|Pozitif sonsuzluk (+ INF)|  
  
## <a name="remarks"></a>Açıklamalar  
 `_fpclass` Ve `_fpclassf` Microsoft belirli işlevlerdir. Benzer şekilde [fpclassify](../../c-runtime-library/reference/fpclassify.md), ancak bağımsız değişken ilgili ayrıntılı bilgileri döndürür. `_fpclassf` İşlevi için x64 derlendiğinde kullanılabilir yalnızca platform.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`_fpclass`|\<float.h >|  
  
 Daha fazla uyumluluk ve uyum için bilgi [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [isNaN, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [fpclassify](../../c-runtime-library/reference/fpclassify.md)