---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2819'
title: Derleyici hatası C2819
ms.date: 11/04/2016
f1_keywords:
- C2819
helpviewer_keywords:
- C2819
ms.assetid: fcc7762d-cb82-4bb1-a715-0d82da832edf
ms.openlocfilehash: fa30432399913c6bdd00bb2728931d213c14064c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194754"
---
# <a name="compiler-error-c2819"></a>Derleyici hatası C2819

' Type ' türünün aşırı yüklenmiş bir ' operator-> ' üyesi yok

`operator->()`Bu işaretçi işlemini kullanmak için tanımlamanız gerekir.

Aşağıdaki örnek C2819 oluşturur:

```cpp
// C2819.cpp
// compile with: /c
class A {
   public:
      int i;
};

class B {};

void C(B j) {
   j->i;   // C2819
}

class D {
   A* pA;

   public:
      A* operator->() {
         return pA;
      }
};

void F(D j) {
   j->i;
}
```

C2819, [başvuru türleri için C++ yığın semantiği](../../dotnet/cpp-stack-semantics-for-reference-types.md)kullanılırken de oluşabilir. Aşağıdaki örnek C2819 oluşturur:

```cpp
// C2819_b.cpp
// compile with: /clr
ref struct R {
   void Test() {}
};

int main() {
   R r;
   r->Test();   // C2819
   r.Test();   // OK
}
```
