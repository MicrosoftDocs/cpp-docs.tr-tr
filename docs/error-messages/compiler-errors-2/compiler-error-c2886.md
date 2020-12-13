---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2886'
title: Derleyici hatası C2886
ms.date: 11/04/2016
f1_keywords:
- C2886
helpviewer_keywords:
- C2886
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
ms.openlocfilehash: 0a2591a18fc7113b77f90e689860906d35fa9460
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337476"
---
# <a name="compiler-error-c2886"></a>Derleyici hatası C2886

' class:: Identifier ': simge bir üye bildirimi kullanılarak kullanılamaz

Bir **`using`** bildirim, ad alanı adı gibi bir simge kullanır. **`using`** Bildirim, temel sınıf üyelerini bildirmek içindir.

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
