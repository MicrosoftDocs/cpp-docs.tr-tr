---
title: "ML önemli hatası A1007 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A1007
dev_langs: C++
helpviewer_keywords: A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bb4b55ce7a16620cd501fa8e687339f1bc48e3b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
-   Makro.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ML hata iletileri](../../assembler/masm/ml-error-messages.md)