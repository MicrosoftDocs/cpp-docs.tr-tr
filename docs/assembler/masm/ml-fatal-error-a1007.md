---
title: "ML önemli hatası A1007 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- A1007
dev_langs:
- C++
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1d1ef99cebab226a3af5e7e685acc5a5485872d1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ml-fatal-error-a1007"></a>ML Önemli Hatası A1007
**çok derin iç içe geçirme düzeyi**  
  
 Derleyici iç içe geçmiş sınırına ulaştı. Tersi belirtilmedikçe dışında 20 düzeyleri sınırlıdır.  
  
 Aşağıdakilerden biri çok fazla iç içe:  
  
-   Gibi üst düzey bir yönerge [. Eğer](../../assembler/masm/dot-if.md), [. Yineleme](../../assembler/masm/dot-repeat.md), veya [. SIRADA](../../assembler/masm/dot-while.md).  
  
-   Yapı tanımı.  
  
-   Koşullu derleme yönergesi.  
  
-   Bir yordamı tanımı.  
  
-   A [PUSHCONTEXT](../../assembler/masm/pushcontext.md) yönergesi (sınır: 10).  
  
-   Segment tanımı.  
  
-   Bir içerme dosyası.  
  
-   A macro.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ML Hata İletileri](../../assembler/masm/ml-error-messages.md)