---
title: "Çıkarım kuralları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- NMAKE program, inference rules
ms.assetid: caff320f-fb07-4eea-80c3-a6a2133a8492
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 932aad860cd2b78208857ca7b028e35cd96d481e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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