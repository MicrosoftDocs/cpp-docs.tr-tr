---
title: Bağımlılık Yan Etkileri
ms.date: 11/04/2016
helpviewer_keywords:
- dependencies, side effects
- NMAKE program, dependents
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
ms.openlocfilehash: 4ce32a55e89d78d45bc74ce3f7dd45ff2f99af31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530058"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Hedefler](../build/targets.md)