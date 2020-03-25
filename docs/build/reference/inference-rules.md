---
title: Çıkarsama Kuralları
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- NMAKE program, inference rules
ms.assetid: caff320f-fb07-4eea-80c3-a6a2133a8492
ms.openlocfilehash: d3d7ca41d96d3845237b445edefff05044dacdc2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170520"
---
# <a name="inference-rules"></a>Çıkarsama Kuralları

Çıkarım kuralları hedefleri güncelleştirmek ve hedeflere yönelik bağımlıları çıkarmayı sağlamak için komutlar sağlar. Bir çıkarım kuralındaki uzantılar tek bir hedefle ve aynı temel ada sahip bağımlı ile eşleşiyor. Çıkarım kuralları Kullanıcı tanımlı veya önceden tanımlanmış. önceden tanımlanmış kurallar yeniden tanımlanabilir.

Güncel olmayan bağımlılıkta bir komut yoksa ve varsa [. SONEKLER](dot-directives.md) bağımlı bileşenin uzantısını içerir, NMAKE, uzantıları hedefle eşleşen bir kural ve geçerli ya da belirtilen dizinde var olan bir dosya kullanıyor. Birden çok kural var olan dosyalarla eşleşiyorsa, **. SONEK** listesi hangisinin kullanılacağını belirler; öncelik alt öğelerinden soldan sağa listeleyin. Bağımlı bir dosya mevcut değilse ve başka bir açıklama bloğunda bir hedef olarak listelenmiyorsa, bir çıkarım kuralı aynı temel ada sahip başka bir dosyadan bağlı eksik bir değer oluşturabilir. Bir açıklama bloğunun hedefine bağımlılar veya komutlar yoksa, bir çıkarım kuralı hedefi güncelleştirebilir. Çıkarım kuralları, açıklama bloğu mevcut olmasa bile bir komut satırı hedefi oluşturabilir. NMAKE, açık bir bağımlı belirtilmiş olsa bile, gösterilen bir bağımlı için bir kural çağırabilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

[Kural tanımlama](defining-a-rule.md)

[Toplu işlem modu kuralları](batch-mode-rules.md)

[Önceden tanımlanmış kurallar](predefined-rules.md)

[Gösterilen etkilenenler ve kurallar](inferred-dependents-and-rules.md)

[Çıkarım kurallarında öncelik](precedence-in-inference-rules.md)

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE Başvurusu](nmake-reference.md)
