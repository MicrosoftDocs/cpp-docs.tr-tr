---
title: Birikmeli Bağımlılıklar
ms.date: 11/04/2016
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
ms.openlocfilehash: c31740b830993c91568aea6d167fd3113b04fc57
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460287"
---
# <a name="cumulative-dependencies"></a>Birikmeli Bağımlılıklar

Bir hedef yinelenen bir açıklama bloğu içinde toplu bağımlılıkları vardır.

Örneğin, bu kuralları ayarlamak,

```Output
bounce.exe : jump.obj
bounce.exe : up.obj
   echo Building bounce.exe...
```

şunun gibi değerlendirilir:

```Output
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

Birden çok hedefi tek bir açıklama bloğunda birden çok bağımlılık satırlarında, her bir ayrı açıklama bloğu içinde belirtilmiş, ancak son bağımlılık satırında olmayan hedefleri komutları blok kullanmayın yokmuş gibi değerlendirilir. NMAKE çıkarım kuralı kullanmak için tür hedeflerle dener.

Örneğin, bu kuralları ayarlamak,

```Output
leap.exe bounce.exe : jump.obj
bounce.exe climb.exe : up.obj
   echo Building bounce.exe...
```

şunun gibi değerlendirilir:

```Output

leap.exe : jump.obj
# invokes an inference rule
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
climb.exe : up.obj
   echo Building bounce.exe...
```

## <a name="see-also"></a>Ayrıca Bkz.

[Hedefler](../build/targets.md)