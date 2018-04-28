---
title: ML önemli hatası A1011 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1011
dev_langs:
- C++
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 843d676cba61e0da5f917a48408e56e79abb9efd
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="ml-fatal-error-a1011"></a>ML Önemli Hatası A1011
**yönergesi denetim bloğunda olmalıdır**  
  
 Derleyici bir değil beklenirken üst düzey bir yönergesi bulundu. Aşağıdaki yönergeleri birini bulundu:  
  
-   [. ELSE](../../assembler/masm/dot-else.md) olmadan [. EĞER](../../assembler/masm/dot-if.md)  
  
-   [. ENDIF](../../assembler/masm/dot-endif.md) olmadan [. EĞER](../../assembler/masm/dot-if.md)  
  
-   [. ENDW](../../assembler/masm/dot-endw.md) olmadan [. WHILE](../../assembler/masm/dot-while.md)  
  
-   [. UNTILCXZ](../../assembler/masm/dot-untilcxz.md) olmadan [. YİNELE](../../assembler/masm/dot-repeat.md)  
  
-   [. Devam](../../assembler/masm/dot-continue.md) olmadan [. SIRADA](../../assembler/masm/dot-while.md) veya [. YİNELE](../../assembler/masm/dot-repeat.md)  
  
-   [. BREAK](../../assembler/masm/dot-break.md) olmadan [. SIRADA](../../assembler/masm/dot-while.md) veya [. YİNELE](../../assembler/masm/dot-repeat.md)  
  
-   [. ELSE](../../assembler/masm/dot-else.md) aşağıdaki `.ELSE`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ML Hata İletileri](../../assembler/masm/ml-error-messages.md)