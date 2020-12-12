---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4487'
title: Derleyici Uyarısı (düzey 4) C4487
ms.date: 11/04/2016
f1_keywords:
- C4487
helpviewer_keywords:
- C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
ms.openlocfilehash: a750152e6920f9e012f3a1b7d093b68749e6fe8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203477"
---
# <a name="compiler-warning-level-4-c4487"></a>Derleyici Uyarısı (düzey 4) C4487

' derived_class_function ': devralınan ' base_class_function ' sanal olmayan yöntemiyle eşleşiyor ancak açıkça ' New ' olarak işaretlenmemiş

Türetilmiş sınıftaki bir işlev, sanal olmayan bir taban sınıf işleviyle aynı imzaya sahip. C4487, türetilmiş sınıf işlevinin temel sınıf işlevini geçersiz kılmayacağını hatırlatır. Bu uyarıyı çözmek için türetilmiş sınıf işlevini açıkça işaretleyin **`new`** .

Daha fazla bilgi için bkz. [Yeni (vtable 'da yeni yuva)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4487 oluşturur.

```cpp
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
