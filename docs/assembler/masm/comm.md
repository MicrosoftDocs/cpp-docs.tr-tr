---
title: COMM | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- COMM
dev_langs:
- C++
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 111dac47089fea13febe787e5b73557b287beea8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="comm"></a>COMM
Belirtilen özniteliklerle müşterek bir değişken oluşturur `definition`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Her `definition` aşağıdaki biçime sahiptir:  
  
 [[*langtype*]] [[**NEAR** &#124; **uzak**]] *etiket ***:**`type`[[**:*** Count*]]  
  
 *Etiket* değişkenin adıdır. `type` Hiçbir tür belirteci olabilir ([bayt](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md), vb.) veya bayt sayısını belirten bir tamsayı. *Sayısı* veri nesneleri (varsayılan biridir) sayısını belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)