---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2452'
title: Derleyici hatası C2452
ms.date: 11/04/2016
f1_keywords:
- C2452
helpviewer_keywords:
- C2452
ms.assetid: a4ec7642-6660-4c7a-9866-853d1cc67daf
ms.openlocfilehash: 8d3915e9b249b53ca1cd193247ca1cf742fa7ffe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332396"
---
# <a name="compiler-error-c2452"></a>Derleyici hatası C2452

' Type ': safe_cast için geçersiz kaynak türü

[Safe_cast](../../extensions/safe-cast-cpp-component-extensions.md) için kaynak türü geçerli değil.  Örneğin, bir işlemdeki tüm türlerin `safe_cast` clr türleri olması gerekir.

Aşağıdaki örnek C2452 oluşturur:

```cpp
// C2452.cpp
// compile with: /clr

struct A {};
struct B : public A {};

ref struct C {};
ref struct D : public C{};

int main() {
   A a;
   safe_cast<B*>(&a);   // C2452

   // OK
   C ^ c = gcnew C;
   safe_cast<D^>(c);
}
```
