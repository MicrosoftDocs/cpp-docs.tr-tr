---
title: Bağımlılık yan etkileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dependencies, side effects
- NMAKE program, dependents
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a70df679434b187bc2eee4eb4aad5881db0da1c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716548"
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