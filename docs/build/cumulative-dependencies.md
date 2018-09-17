---
title: Birikmeli bağımlılıklar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a66b153a52da06cca14845b9a58fcef0f42676d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725718"
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