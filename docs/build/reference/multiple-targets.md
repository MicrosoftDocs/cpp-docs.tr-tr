---
title: Birden Çok Hedef
ms.date: 11/04/2016
helpviewer_keywords:
- makefiles, targets
- multiple targets in NMAKE
- targets, multiple in NMAKE
- NMAKE program, targets
ms.assetid: b609a179-0b9f-4b08-9930-998047588ae0
ms.openlocfilehash: 43e5216d5e11e89aff9b6f0c69ff4e76a8cc9da8
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823492"
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

## <a name="see-also"></a>Ayrıca bkz.

[Hedefler](targets.md)
