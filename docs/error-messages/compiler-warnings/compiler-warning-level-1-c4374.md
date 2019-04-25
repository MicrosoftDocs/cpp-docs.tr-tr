---
title: Derleyici Uyarısı (düzey 1) C4374
ms.date: 11/04/2016
f1_keywords:
- C4374
helpviewer_keywords:
- C4374
ms.assetid: 4ac9aaec-d815-4b6e-825f-fa872092dd3b
ms.openlocfilehash: 5cf18a3dcd94f59ce1ae8feb675f251bea5715a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302247"
---
# <a name="compiler-warning-level-1-c4374"></a>Derleyici Uyarısı (düzey 1) C4374

'function1': arabirim yöntemi sanal olmayan 'function2' yöntemi tarafından uygulanmayacak

Derleyici bekleniyordu [sanal](../../cpp/virtual-specifier.md) anahtar sözcüğü, bir yöntem tanımı.

Aşağıdaki örnek, C4374 oluşturur:

```
// C4374.cpp
// compile with: /clr /W1 /c /WX
public interface class I {
   void f();
};

public ref struct B {
   void f() {
      System::Console::WriteLine("B::f()");
   }
};

public ref struct C {
   virtual void f() {
      System::Console::WriteLine("C::f()");
   }
};

public ref struct D : B, I {};   // C4374
public ref struct E : C, I {};   // OK
```