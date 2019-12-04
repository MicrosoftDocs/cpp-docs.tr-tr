---
title: Derleyici hatası C2881
ms.date: 11/04/2016
f1_keywords:
- C2881
helpviewer_keywords:
- C2881
ms.assetid: b49c63c2-b064-4d4b-a75e-ddd2af947522
ms.openlocfilehash: 9c171fd529943bb07a6c512e4ac97f64f13f959d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736288"
---
# <a name="compiler-error-c2881"></a>Derleyici hatası C2881

' Namespace1 ': ' Namespace2 ' için bir diğer ad olarak zaten kullanılıyor

İki ad alanı için bir diğer ad olarak aynı adı kullanamazsınız.

Aşağıdaki örnek C2881 oluşturur:

```cpp
// C2881.cpp
// compile with: /c
namespace A {
   int k;
}

namespace B {
   int i;
}

namespace C = A;
namespace C = B;   // C2881 C is already an alias for A
```
