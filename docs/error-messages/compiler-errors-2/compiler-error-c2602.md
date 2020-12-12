---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2602'
title: Derleyici hatası C2602
ms.date: 11/04/2016
f1_keywords:
- C2602
helpviewer_keywords:
- C2602
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
ms.openlocfilehash: 2922ee0d35dd5820e1df23d9bc812c0650501b35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312031"
---
# <a name="compiler-error-c2602"></a>Derleyici hatası C2602

' class:: Identifier ' bir ' class ' taban sınıfının üyesi değil

`Identifier` herhangi bir temel sınıftan devralınan üye olmadığından erişilemiyor.

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
