---
title: Derleyici Uyarısı (düzey 4) C4487
ms.date: 11/04/2016
f1_keywords:
- C4487
helpviewer_keywords:
- C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
ms.openlocfilehash: 743069c0ed3103a2ed8d459def65083146b971e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497046"
---
# <a name="compiler-warning-level-4-c4487"></a>Derleyici Uyarısı (düzey 4) C4487

'derived_class_function': 'base_class_function' devralınan sanal olmayan yöntemiyle eşleşiyor ancak açıkça 'new' işaretli değil

Türetilen bir sınıfta bir işleve, sanal olmayan temel sınıf işlevi aynı imzaya sahiptir. C4487 türetilmiş sınıf işlev temel sınıf işlevini geçersiz kılmaz anımsatır. Türetilmiş sınıf işlevi açıkça işaretleyin `new` bu uyarıyı çözmek için.

Daha fazla bilgi için [yeni (vtable'da yeni yuva)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4487 oluşturur.

```
// C4487.cpp
// compile with: /W4 /clr
using namespace System;
public ref struct B {
   void f() { Console::WriteLine("in B::f"); }
   void g() { Console::WriteLine("in B::g"); }
};

public ref struct D : B {
   void f() { Console::WriteLine("in D::f"); }   // C4487
   void g() new { Console::WriteLine("in D::g"); }   // OK
};

int main() {
   B ^ a = gcnew D;
   // will call base class functions
   a->f();
   a->g();
}
```