---
title: Derleyici Hatası C3739
ms.date: 11/04/2016
f1_keywords:
- C3739
helpviewer_keywords:
- C3739
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
ms.openlocfilehash: 34f035c089b183670e87a23eb62f995b2af23c9b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208675"
---
# <a name="compiler-error-c3739"></a>Derleyici Hatası C3739

'class': sözdizimi yalnızca event_receiver'ın 'layout_dependent' parametresi true olduğunda desteklenir

Olayların bir arabirimin tamamı kanca denedi ancak `layout_dependent` üzerinde [event_receiver](../../windows/event-receiver.md) özniteliği true değil; bir kerede tek bir olay bağlama.

Aşağıdaki örnek, C3739 oluşturur:

```
// C3739.cpp
struct A
{
   __event void e();
};

// event_receiver is implied
// [ event_receiver(layout_dependent=false)]

// use the following line instead
// [event_receiver(com, layout_dependent=true), coclass ]
struct B
{
   void f();
   B(A* a)
   {
      __hook(A, a, &B::f);   // C3739
      // use the following line instead to hook a single event
      // __hook(&A::e, a, &B::f);
   }
};

int main()
{
}
```