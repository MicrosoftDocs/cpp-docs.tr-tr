---
title: Açıklama Blokları
ms.date: 11/04/2016
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
ms.openlocfilehash: 214963b5c3f633e8d029cee0500d4bd5fab6ed53
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490616"
---
# <a name="description-blocks"></a>Açıklama Blokları

Açıklama bloğu isteğe bağlı olarak bir komut bloğu tarafından izlenen bir bağımlılık satırı verilmiştir:

```
targets... : dependents...
    commands...
```

Bir veya daha fazla hedef ve sıfır veya daha fazla bağımlıları bir bağımlılık satırı belirtir. Bir hedef satır başında olması gerekir. İki nokta üst üste (:) tarafından bağımlılıklar ayrı hedeflerden; boşluk veya sekme izin verilir. Satır ayırmak için bir hedef veya bağımlı sonra ters eğik çizgi (\) kullanın. Bir hedef mevcut değilse bir bağımlı daha önceki bir zaman damgası yok veya bir [pseudotarget](../build/pseudotargets.md), NMAKE komutları yürütür. Bağımlı bir başka bir hedef olduğu ve mevcut değil ya da kendi bağımlıları göre güncel değil, geçerli bağımlılık güncelleştirmeden önce NMAKE bağımlı güncelleştirir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

[Hedefler](../build/targets.md)

[Bağımlılıklar](../build/dependents.md)

## <a name="see-also"></a>Ayrıca Bkz.

[NMAKE Başvurusu](../build/nmake-reference.md)