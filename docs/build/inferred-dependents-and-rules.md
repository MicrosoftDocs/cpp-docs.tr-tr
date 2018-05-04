---
title: Çıkarımı yapılan bağımlılıklar ve kurallar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aae09fd756e0eb4eab3031beb5b4cba8c4d35a40
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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