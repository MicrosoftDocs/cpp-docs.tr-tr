---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2884'
title: Derleyici hatası C2884
ms.date: 11/04/2016
f1_keywords:
- C2884
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
ms.openlocfilehash: 008c72ba24bdea260fffc4a49145ecf67c610b15
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332327"
---
# <a name="compiler-error-c2884"></a>Derleyici hatası C2884

' name ': WITH bildirimi kullanılarak tanıtılan ' function ' yerel işleviyle çakışıyor

Bir işlevi birden çok kez tanımlamaya çalıştınız. İlk tanım, yerel bir tanımdır. İkincisi, bildirimi olan bir ad alanıdır **`using`** .

Aşağıdaki örnek C2884 oluşturur:

```cpp
// C2884.cpp
namespace A {
   void z(int);
}

void f() {
   void z(int);
   using A::z;   // C2884 z is already defined
}
```
