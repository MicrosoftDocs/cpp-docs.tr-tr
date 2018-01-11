---
title: "ML önemli hatası A1010 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A1010
dev_langs: C++
helpviewer_keywords: A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b495fc2b8bd0e667dd7dae7e23347f6971ec4d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ml-fatal-error-a1010"></a>ML Önemli Hatası A1010
**eşleşmeyen blok iç içe geçme:**  
  
 Blok başlayan bir eşleşen son sahip değilse veya bir blok uç eşleşen başlayan bir sahip değil. Aşağıdakilerden birini dahil:  
  
-   Gibi üst düzey bir yönerge [. Eğer](../../assembler/masm/dot-if.md), [. Yineleme](../../assembler/masm/dot-repeat.md), veya [. SIRADA](../../assembler/masm/dot-while.md).  
  
-   Koşullu derleme yönergesi gibi [IF](../../assembler/masm/if-masm.md), [YİNELEYİN](../../assembler/masm/repeat.md), veya **sırada**.  
  
-   Yapı veya birlik tanımı.  
  
-   Bir yordamı tanımı.  
  
-   Segment tanımı.  
  
-   A [POPCONTEXT](../../assembler/masm/popcontext.md) yönergesi.  
  
-   Koşullu derleme yönergesi gibi bir [ELSE](../../assembler/masm/else-masm.md), [ELSEIF](../../assembler/masm/elseif-masm.md), veya **ENDIF** eşleşen bir olmadan [IF](../../assembler/masm/if-masm.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ML Hata İletileri](../../assembler/masm/ml-error-messages.md)