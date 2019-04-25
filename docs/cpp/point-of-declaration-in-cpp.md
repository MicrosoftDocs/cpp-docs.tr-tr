---
title: C++ bildirim noktası
ms.date: 11/04/2016
helpviewer_keywords:
- point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
ms.openlocfilehash: d6cb4c3813d88c8b29fbcb2e0827805f406e6c81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183407"
---
# <a name="point-of-declaration-in-c"></a>C++ bildirim noktası

Kendi bildirimci hemen sonra ancak (isteğe bağlı) başlatıcısı önce bildirilmesi için bir ad olarak kabul edilir. (Bildirimciler hakkında daha fazla bilgi için bkz. [bildirimlerinin ve tanımlarının](declarations-and-definitions-cpp.md).)

Bu örneği göz önünde bulundurun:

```cpp
// point_of_declaration1.cpp
// compile with: /W1
double dVar = 7.0;
int main()
{
   double dVar = dVar;   // C4700
}
```

Bildirim noktası olsaydı *sonra* başlatma ve ardından yerel `dVar` 7.0, genel değişkeninin değerini başlatılan `dVar`. Ancak, bu durumda olmadığından `dVar` tanımsız bir değerle başlatılır.

## <a name="see-also"></a>Ayrıca bkz.

[Kapsam](../cpp/scope-visual-cpp.md)