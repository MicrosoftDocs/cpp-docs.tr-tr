---
title: Bağımlılık Yan Etkileri
ms.date: 11/04/2016
helpviewer_keywords:
- dependencies, side effects
- NMAKE program, dependents
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
ms.openlocfilehash: 1479fac4defa45545ffd06ab30fd53ae0c2506af
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422643"
---
# <a name="dependency-side-effects"></a>Bağımlılık Yan Etkileri

Bir hedef bir iki nokta üst üste (:) farklı konumlarda iki bağımlılık satırlarında belirtilir ve komut satırları yalnızca biri sonra belirir, NMAKE bağımlılıkları bitişik veya toplam gibi yorumlar. Hiçbir komut, ancak bunun yerine bağımlılıklar için bir açıklama bloğu ait ve diğer bağımlılık ile belirtilen komutları yürütür varsayar bağımlılık için bir çıkarma kuralı çağrılmaz. Örneğin, bu kuralları ayarlayın:

```Output
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
```

şunun gibi değerlendirilir:

```Output
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

Bu etkiyi bir çift iki nokta üst üste gerçekleşmez (`::`) kullanılır. Örneğin, bu kuralları ayarlayın:

```Output
bounce.exe :: jump.obj
   echo Building bounce.exe...

bounce.exe :: up.obj
```

şunun gibi değerlendirilir:

```Output
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
# invokes an inference rule
```

## <a name="see-also"></a>Ayrıca bkz.

[Hedefler](../build/targets.md)
