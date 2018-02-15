---
title: COMM | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COMM
dev_langs:
- C++
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6258a584d39f598b32c43affc0ef2569b77b2047
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="comm"></a>COMM
Belirtilen özniteliklerle müşterek bir değişken oluşturur `definition`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Her `definition` aşağıdaki biçime sahiptir:  
  
 [[*langtype*]] [[**NEAR** &#124; **Uzak**]] *etiket***:**`type`[[**:***sayısı*]]  
  
 *Etiket* değişkenin adıdır. `type` Hiçbir tür belirteci olabilir ([bayt](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md), vb.) veya bayt sayısını belirten bir tamsayı. *Sayısı* veri nesneleri (varsayılan biridir) sayısını belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)