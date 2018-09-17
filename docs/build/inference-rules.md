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
ms.openlocfilehash: ed45e5ad61ea1cc50172cd86716b357baa64fa39
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724392"
---
# <a name="inference-rules"></a>Çıkarsama Kuralları

Çıkarım kuralları komutları hedefleri güncelleştir ve hedefler için bağımlılıklar çıkarsanacak sağlayın. Çıkarım kuralı uzantılarında eşleşen tek bir hedefi ve bağımlı, aynı temel ada sahip. Çıkarım kuralları, kullanıcı tanımlı veya önceden tanımlanmış; önceden tanımlanmış kurallar tanımlanabilir.

Güncel olmayan bir bağımlılık hiçbir komut varsa ve [. SONEKLERİ](../build/dot-directives.md) içeriyor bağımlı öğenin uzantısı, bir kuralı, uzantıları uyan hedef ve var olan bir dosya geçerli ya da belirtilen dizinde NMAKE kullanır. Var olan dosyaları, birden fazla kuralın eşleşmesi durumunda **. SONEKLERİ** listesi kullanılacağı belirler; liste öncelik soldan sağa iner. Bağımlı dosya mevcut değil ve başka bir açıklama bloğundaki hedefi olarak listelenmiyorsa, çıkarım kuralı eksik bağımlı aynı temel ada sahip başka bir dosya oluşturabilirsiniz. Çıkarım kuralı, bir açıklama bloğun hedef bağımlılıklar ya da komutları varsa, hedef güncelleştirebilirsiniz. Açıklama Engellemesiz bulunuyor olsa bile komut satırı hedef çıkarım kuralları oluşturabilirsiniz. Açık bir bağımlı belirtilmiş olsa bile NMAKE çıkarsanan bir bağımlı için bir kural çağırabilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

[Kural tanımlama](../build/defining-a-rule.md)

[Toplu iş modu kuralları](../build/batch-mode-rules.md)

[Önceden tanımlanmış kurallar](../build/predefined-rules.md)

[Çıkarsanan bağımlılıklar ve kurallar](../build/inferred-dependents-and-rules.md)

[Çıkarsama kurallarında öncelik](../build/precedence-in-inference-rules.md)

## <a name="see-also"></a>Ayrıca Bkz.

[NMAKE Başvurusu](../build/nmake-reference.md)