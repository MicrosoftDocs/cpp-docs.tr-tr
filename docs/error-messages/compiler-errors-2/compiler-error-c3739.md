---
title: Derleyici Hatası C3739 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3739
dev_langs:
- C++
helpviewer_keywords:
- C3739
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0cc0bbe61f807ccd6b2f2f1404fb8e5cc724107
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069891"
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