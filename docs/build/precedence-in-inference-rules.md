---
title: Çıkarsama kurallarında öncelik | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36d462d4222cbfc143dd7487d4cb6b1b8bb3ba3b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368492"
---
# <a name="precedence-in-inference-rules"></a>Çıkarsama Kurallarında Öncelik
NMAKE çıkarım kuralı birden çok kez tanımlanmış, en yüksek öncelik tanımı kullanır. Aşağıdaki liste yüksekten en düşüğe öncelik sırasını göstermektedir:  
  
1.  Derleme görevleri dosyası içinde tanımlanan bir çıkarım kuralı; sonraki tanımları önceliğe sahiptir.  
  
2.  Tools.ini içinde tanımlanan bir çıkarım kuralı; sonraki tanımları önceliğe sahiptir.  
  
3.  Önceden tanımlanmış çıkarım kuralı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıkarım Kuralları](../build/inference-rules.md)