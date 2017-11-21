---
title: "ML önemli hatası A1011 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A1011
dev_langs: C++
helpviewer_keywords: A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 686ae83c4316caee243750a6ed1c28303c9de0ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
-   [. ELSE](../../assembler/masm/dot-else.md) aşağıdaki`.ELSE`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ML hata iletileri](../../assembler/masm/ml-error-messages.md)