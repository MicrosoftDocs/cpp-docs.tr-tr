---
title: "Çıkarımı yapılan bağımlılıklar ve kurallar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 68b61a6aad55ef1f6b8b5807d857a4d7239ebb51
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="inferred-dependents-and-rules"></a>Çıkarsanan Bağımlılıklar ve Kurallar
Geçerli çıkarım kuralı varsa NMAKE bir oluşturulursa bağımlı bir hedef için varsayar. Bir kural geçerlidir:  
  
-   *toext* hedefin uzantısı ile eşleşir.  
  
-   *fromext* hedef temel ad ve sahip bir dosya uzantısı geçerli ya da belirtilen dizinde var. eşleşir.  
  
-   *fromext* yer [. SONEKLERİ](../build/dot-directives.md); başka *fromext* bir eşleşen kuralı daha yüksek olan **. SONEKLERİ** öncelik.  
  
-   Hiçbir açık bağımlı daha yüksek olan **. SONEKLERİ** öncelik.  
  
 Çıkarsanan bağımlılıklar beklenmeyen yan etkileri neden olabilir. Hedefin açıklama blok komutları içeriyorsa, NMAKE kuralında komutları yerine bu komutları yürütür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıkarım kuralları](../build/inference-rules.md)