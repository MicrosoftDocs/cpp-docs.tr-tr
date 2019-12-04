---
title: Derleyici hatası C2886
ms.date: 11/04/2016
f1_keywords:
- C2886
helpviewer_keywords:
- C2886
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
ms.openlocfilehash: a64457c84a48c73ad6714da01e48d41f3cc92efb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748729"
---
# <a name="compiler-error-c2886"></a>Derleyici hatası C2886

' class:: Identifier ': simge bir üye bildirimi kullanılarak kullanılamaz

`using` bildirimi, bir ad alanı adı gibi bir simge kullanır. `using` bildirimi, temel sınıf üyelerini bildirmek içindir.

Aşağıdaki örnek C2886 oluşturur:

```cpp
// C2886.cpp
// compile with: /c
namespace Z {
    int i;
}

class B {
protected:
    int i;
};

class D : public B {
    // Error: Z is a namespace
    using Z::i;   // C2886

    // OK: B is a base class
    using B::i;
};
```
