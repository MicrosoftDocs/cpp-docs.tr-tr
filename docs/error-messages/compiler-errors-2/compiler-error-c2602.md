---
title: Derleyici hatası C2602
ms.date: 11/04/2016
f1_keywords:
- C2602
helpviewer_keywords:
- C2602
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
ms.openlocfilehash: 4cac8bd8aca0a811e1e009a2fdf07cbc200634f2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737900"
---
# <a name="compiler-error-c2602"></a>Derleyici hatası C2602

' class:: Identifier ' bir ' class ' taban sınıfının üyesi değil

herhangi bir temel sınıftan devralınan üye olmadığından `Identifier` erişilemiyor.

Aşağıdaki örnek C2602 oluşturur:

```cpp
// C2602.cpp
// compile with: /c
struct X {
   int x;
};
struct A {
   int a;
};
struct B : public A {
   X::x;   // C2602 B is not derived from X
   A::a;   // OK
};
```
