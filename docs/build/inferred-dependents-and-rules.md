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
ms.workload: cplusplus
ms.openlocfilehash: fe7c49607f466d8fd1d333883414b24d7837432b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="inferred-dependents-and-rules"></a>Çıkarsanan Bağımlılıklar ve Kurallar
Geçerli çıkarım kuralı varsa NMAKE bir oluşturulursa bağımlı bir hedef için varsayar. Bir kural geçerlidir:  
  
-   *toext* hedefin uzantısı ile eşleşir.  
  
-   *fromext* hedef temel ad ve sahip bir dosya uzantısı geçerli ya da belirtilen dizinde var. eşleşir.  
  
-   *fromext* yer [. SONEKLERİ](../build/dot-directives.md); başka *fromext* bir eşleşen kuralı daha yüksek olan **. SONEKLERİ** öncelik.  
  
-   Hiçbir açık bağımlı daha yüksek olan **. SONEKLERİ** öncelik.  
  
 Çıkarsanan bağımlılıklar beklenmeyen yan etkileri neden olabilir. Hedefin açıklama blok komutları içeriyorsa, NMAKE kuralında komutları yerine bu komutları yürütür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıkarım Kuralları](../build/inference-rules.md)