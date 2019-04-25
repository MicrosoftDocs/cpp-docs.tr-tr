---
title: Bağımlılık Yan Etkileri
ms.date: 11/04/2016
helpviewer_keywords:
- dependencies, side effects
- NMAKE program, dependents
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
ms.openlocfilehash: b89306b6e4d85e0e08729fb1d35fb041d69647e7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272119"
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

[Hedefler](targets.md)
