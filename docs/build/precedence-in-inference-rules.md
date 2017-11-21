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
ms.openlocfilehash: d22db9de1fc1941798c73c3c1c05a8ccd8571525
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="precedence-in-inference-rules"></a>Çıkarsama Kurallarında Öncelik
NMAKE çıkarım kuralı birden çok kez tanımlanmış, en yüksek öncelik tanımı kullanır. Aşağıdaki liste yüksekten en düşüğe öncelik sırasını göstermektedir:  
  
1.  Derleme görevleri dosyası içinde tanımlanan bir çıkarım kuralı; sonraki tanımları önceliğe sahiptir.  
  
2.  Tools.ini içinde tanımlanan bir çıkarım kuralı; sonraki tanımları önceliğe sahiptir.  
  
3.  Önceden tanımlanmış çıkarım kuralı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıkarım kuralları](../build/inference-rules.md)