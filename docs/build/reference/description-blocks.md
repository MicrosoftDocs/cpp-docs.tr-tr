---
title: Açıklama Blokları
ms.date: 11/04/2016
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
ms.openlocfilehash: da9265d6b0026bb47496d3aa58847824b5d634d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293816"
---
# <a name="description-blocks"></a>Açıklama Blokları

Açıklama bloğu isteğe bağlı olarak bir komut bloğu tarafından izlenen bir bağımlılık satırı verilmiştir:

```
targets... : dependents...
    commands...
```

Bir veya daha fazla hedef ve sıfır veya daha fazla bağımlıları bir bağımlılık satırı belirtir. Bir hedef satır başında olması gerekir. İki nokta üst üste (:) tarafından bağımlılıklar ayrı hedeflerden; boşluk veya sekme izin verilir. Satır ayırmak için bir hedef veya bağımlı sonra ters eğik çizgi (\) kullanın. Bir hedef mevcut değilse bir bağımlı daha önceki bir zaman damgası yok veya bir [pseudotarget](pseudotargets.md), NMAKE komutları yürütür. Bağımlı bir başka bir hedef olduğu ve mevcut değil ya da kendi bağımlıları göre güncel değil, geçerli bağımlılık güncelleştirmeden önce NMAKE bağımlı güncelleştirir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

[Hedefler](targets.md)

[Bağımlılıklar](dependents.md)

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE Başvurusu](nmake-reference.md)
