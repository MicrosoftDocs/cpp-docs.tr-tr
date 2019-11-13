---
title: Derleyici Uyarısı (düzey 1) C4803
ms.date: 11/04/2016
f1_keywords:
- C4803
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
ms.openlocfilehash: ebf7b3baec3519a142c7a1835aa15a980974bb48
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052343"
---
# <a name="compiler-warning-level-1-c4803"></a>Derleyici Uyarısı (düzey 1) C4803

' Method ': Raise yönteminin, ' Event ' olayından farklı bir depolama sınıfı vardır

Olay yöntemlerinin, olay bildirimiyle aynı depolama sınıfına sahip olması gerekir. Derleyici, olay yöntemlerini, depolama sınıflarının aynısını aynı olacak şekilde ayarlar.

Bu uyarı, bir arabirimden bir olay uygulayan bir sınıfınız varsa oluşabilir. Derleyici, arabirimdeki bir olay için örtük olarak bir Raise yöntemi oluşturmaz. Bu arabirimi bir sınıfta uyguladığınızda, derleyici örtük olarak bir Raise yöntemi oluşturur ve bu yöntem sanal olmaz ve bu nedenle uyarı görüntülenir. Olaylar hakkında daha fazla bilgi için bkz. [Event](../../extensions/event-cpp-component-extensions.md).

Bir uyarının nasıl kapatılacağı hakkında bilgi için bkz. [Warning](../../preprocessor/warning.md) pragma.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4803 oluşturur.

```cpp
// C4803.cpp
// compile with: /clr /W1
using namespace System;

public delegate void Del();

ref struct E {
   Del ^ _pd1;
   event Del ^ E1 {
      void add (Del ^ pd1) {
         _pd1 = dynamic_cast<Del ^>(Delegate::Combine(_pd1, pd1));
      }

      void remove(Del^ pd1) {
         _pd1 = dynamic_cast<Del^> (Delegate::Remove(_pd1, pd1));
      }

      virtual void raise() {   // C4803 warning (remove virtual)
         if (_pd1)
            _pd1();
      }
   }

   void func() {
      Console::WriteLine("In E::func()");
   }
};

int main() {
   E ^ ep = gcnew E;
   ep->E1 += gcnew Del(ep, &E::func);
   ep->E1();
   ep->E1 -= gcnew Del(ep, &E::func);
   ep->E1();
}
```
