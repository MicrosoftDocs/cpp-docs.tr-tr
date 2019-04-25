---
title: Birikmeli Bağımlılıklar
ms.date: 11/04/2016
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
ms.openlocfilehash: de0a9649be8f0dae58f45d8980d2df610ff2febe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294089"
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

## <a name="see-also"></a>Ayrıca bkz.

[Hedefler](targets.md)
