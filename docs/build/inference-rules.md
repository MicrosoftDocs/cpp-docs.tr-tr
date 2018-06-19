---
title: Çıkarım kuralları | Microsoft Docs
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
- NMAKE program, inference rules
ms.assetid: caff320f-fb07-4eea-80c3-a6a2133a8492
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2baa4bdd749e7553d052600cc9efe524ec09910d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368427"
---
# <a name="inference-rules"></a>Çıkarsama Kuralları
Çıkarım kuralları komutları hedefleri güncelleştirmek ve hedefler için bağımlılıklar anlamak için sağlayın. Aynı taban adına sahip bağımlı ve tek bir hedefi bir çıkarım kuralı uzantılarında eşleşmiyor. Çıkarım kuralları, kullanıcı tanımlı veya önceden tanımlanmış; önceden tanımlanmış kurallar tanımlanabilir.  
  
 Güncel olmayan bir bağımlılık hiçbir komut varsa ve [. SONEKLERİ](../build/dot-directives.md) bağımlı öğenin uzantısı, NMAKE kullanır, uzantıları eşleşen hedef ve var olan bir kural geçerli ya da belirtilen dizinde dosya içeriyor. Birden çok kural mevcut dosyaları eşleşirse **. SONEKLERİ** listesi kullanılacak belirler; listesi öncelik terri soldan sağa doğru. Bağımlı dosya mevcut değil ve başka bir açıklama bloğundaki hedefi olarak listelenmediğinden, çıkarım kuralı eksik bağımlı aynı taban adına sahip başka bir dosya oluşturabilirsiniz. Çıkarım kuralı, bir açıklama bloğun hedef hiçbir bağımlılıklar veya komutları varsa, hedef güncelleştirebilirsiniz. Herhangi bir açıklama engelleme varsa bile bir komut satırı hedef çıkarım kuralları oluşturabilirsiniz. Açık bir bağımlı belirtilmiş olsa bile NMAKE oluşturulursa bağımlı için bir kural çağırabilir.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
 [Kural tanımlama](../build/defining-a-rule.md)  
  
 [Toplu iş modu kuralları](../build/batch-mode-rules.md)  
  
 [Önceden tanımlanmış kurallar](../build/predefined-rules.md)  
  
 [Çıkarsanan bağımlılıklar ve kurallar](../build/inferred-dependents-and-rules.md)  
  
 [Çıkarsama kurallarında öncelik](../build/precedence-in-inference-rules.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE Başvurusu](../build/nmake-reference.md)