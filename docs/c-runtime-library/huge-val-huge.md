---
title: HUGE_VAL, _HUGE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _HUGE
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _HUGE
- HUGE_VAL
dev_langs:
- C++
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c2d763b8c5379223ddacb8077c463efa0b91acfa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="hugeval-huge"></a>HUGE_VAL, _HUGE
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <math.h>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `HUGE_VAL` en büyük gösterilebilir çift değerdir. Hata oluştuğunda, bu değer birçok çalışma zamanı matematik işlevleri tarafından döndürülür. Bazı işlevler için-`HUGE_VAL` döndürülür. `HUGE_VAL` olarak tanımlanan `_HUGE`, ancak çalışma zamanında matematik işlevleri döndürür `HUGE_VAL`. Ayrıca kullanması gereken `HUGE_VAL` kodunuzda tutarlılık için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Global Sabitler](../c-runtime-library/global-constants.md)