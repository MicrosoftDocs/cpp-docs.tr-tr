---
title: Birden çok hedef | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- makefiles, targets
- multiple targets in NMAKE
- targets, multiple in NMAKE
- NMAKE program, targets
ms.assetid: b609a179-0b9f-4b08-9930-998047588ae0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66849bdbe28ac2bd965714de56f962df98ced133
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703670"
---
# <a name="multiple-targets"></a>Birden Çok Hedef

NMAKE içindeki tek bir bağımlılık birden çok hedef her bir ayrı açıklama bloğu içinde belirtilmiş olarak değerlendirir.

Örneğin, bu...

```Output
bounce.exe leap.exe : jump.obj
   echo Building...
```

.. belirtiminde olarak değerlendirilir:

```Output
bounce.exe : jump.obj
   echo Building...
leap.exe : jump.obj
   echo Building...
```

## <a name="see-also"></a>Ayrıca Bkz.

[Hedefler](../build/targets.md)