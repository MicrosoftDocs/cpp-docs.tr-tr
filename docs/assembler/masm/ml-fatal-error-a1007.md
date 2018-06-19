---
title: ML önemli hatası A1007 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1007
dev_langs:
- C++
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10b883fad01943cd8cff71b3da9dee66407ccc93
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32055735"
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
 [ML Hata İletileri](../../assembler/masm/ml-error-messages.md)