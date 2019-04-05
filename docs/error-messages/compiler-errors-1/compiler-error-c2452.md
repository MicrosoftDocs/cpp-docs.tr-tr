---
title: Derleyici Hatası C2452
ms.date: 11/04/2016
f1_keywords:
- C2452
helpviewer_keywords:
- C2452
ms.assetid: a4ec7642-6660-4c7a-9866-853d1cc67daf
ms.openlocfilehash: 3e2d583efa2b634cf49d8588fa398bd81f24c607
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781113"
---
# <a name="compiler-error-c2452"></a>Derleyici Hatası C2452

'type': safe_cast için geçersiz kaynak türü

Kaynak türü [safe_cast](../../extensions/safe-cast-cpp-component-extensions.md) geçerli değildi.  Örneğin, tüm türlerin bir `safe_cast` işlemi CLR Türleri olması gerekir.

Aşağıdaki örnek, C2452 oluşturur:

```
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