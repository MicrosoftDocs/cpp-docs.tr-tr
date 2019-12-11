---
title: Derleyici Uyarısı (düzey 4) C4487
ms.date: 11/04/2016
f1_keywords:
- C4487
helpviewer_keywords:
- C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
ms.openlocfilehash: b83b3b33727db300367156e10f902aaa6ff4bfdb
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990778"
---
# <a name="compiler-warning-level-4-c4487"></a>Derleyici Uyarısı (düzey 4) C4487

' derived_class_function ': devralınan ' base_class_function ' sanal olmayan yöntemiyle eşleşiyor ancak açıkça ' New ' olarak işaretlenmemiş

Türetilmiş sınıftaki bir işlev, sanal olmayan bir taban sınıf işleviyle aynı imzaya sahip. C4487, türetilmiş sınıf işlevinin temel sınıf işlevini geçersiz kılmayacağını hatırlatır. Bu uyarıyı çözmek için türetilmiş sınıf işlevini açıkça `new` olarak işaretleyin.

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
