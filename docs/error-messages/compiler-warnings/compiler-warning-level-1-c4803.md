---
title: Derleyici Uyarısı (düzey 1) C4803
ms.date: 11/04/2016
f1_keywords:
- C4803
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
ms.openlocfilehash: 3915307ac2bcc6a923c93382cfefa618ce01fe52
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563221"
---
# <a name="compiler-warning-level-1-c4803"></a>Derleyici Uyarısı (düzey 1) C4803

'method': yükseltme yönteminde olayın bir farklı depolama sınıfı olan 'event'

Olay yöntemleri olay bildirimiyle aynı depolama sınıfına sahip olmalıdır. Depolama sınıfları aynı olacak şekilde derleyici olay yöntemleri ayarlar.

Bu uyarı, bir olaydan bir arabirimi uygulayan bir sınıf varsa ortaya çıkabilir. Derleyici örtük olarak bir arabirimde bir olayın bir raise yöntemi oluşturmaz. Bir sınıfta arabirimi uyguladığınızda, derleyici bir raise yöntemi örtük bir şekilde oluşturmaya ve bu yöntem bu nedenle sanal olmayacak uyarı. Olaylar hakkında daha fazla bilgi için bkz. [olay](../../windows/event-cpp-component-extensions.md).

Bkz: [uyarı](../../preprocessor/warning.md) pragma bir uyarı kapatmak hakkında bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4803 oluşturur.

```
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
