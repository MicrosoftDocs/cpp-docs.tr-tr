---
title: "Çıkarsama kurallarında öncelik | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f7374da0541fc66464947af5a7b2ea7ea7b5c1d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="precedence-in-inference-rules"></a>Çıkarsama Kurallarında Öncelik
NMAKE çıkarım kuralı birden çok kez tanımlanmış, en yüksek öncelik tanımı kullanır. Aşağıdaki liste yüksekten en düşüğe öncelik sırasını göstermektedir:  
  
1.  Derleme görevleri dosyası içinde tanımlanan bir çıkarım kuralı; sonraki tanımları önceliğe sahiptir.  
  
2.  Tools.ini içinde tanımlanan bir çıkarım kuralı; sonraki tanımları önceliğe sahiptir.  
  
3.  Önceden tanımlanmış çıkarım kuralı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıkarım Kuralları](../build/inference-rules.md)