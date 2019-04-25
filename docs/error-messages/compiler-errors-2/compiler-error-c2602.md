---
title: Derleyici Hatası C2602
ms.date: 11/04/2016
f1_keywords:
- C2602
helpviewer_keywords:
- C2602
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
ms.openlocfilehash: da38600ea099c9b0d73e929a100a8c338bd3388f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62215535"
---
# <a name="compiler-error-c2602"></a>Derleyici Hatası C2602

'class::Identifier' bir 'class' temel sınıfının üyesi değil

`Identifier` herhangi bir temel sınıftan devralınan üyeyi olmadığından erişilemez.

Aşağıdaki örnek, C2602 oluşturur:

```
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