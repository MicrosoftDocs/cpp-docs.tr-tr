---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3717'
title: Derleyici hatası C3717
ms.date: 11/04/2016
f1_keywords:
- C3717
helpviewer_keywords:
- C3717
ms.assetid: ae4fceb1-2583-4577-b2f1-40971a017055
ms.openlocfilehash: fecd417af1eceb40ef8b8e48fda40b3ec5e5b36a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189437"
---
# <a name="compiler-error-c3717"></a>Derleyici hatası C3717

' Method ': olayları harekete uygulayan bir yöntem tanımlanamaz

Uygulama içeren bir olay yöntemi bildirdiniz. [__Event](../../cpp/event.md) yöntemi bildiriminin tanımı olamaz. Bu hatayı düzeltemedi, hiçbir olay yöntemi bildiriminin tanımlara sahip olmadığından emin olun. Örneğin, aşağıdaki kodda, `event1` Açıklama ile gösterildiği gibi, işlev gövdesini bildirimden kaldırın.

Aşağıdaki örnek C3717 oluşturur:

```cpp
// C3717.cpp
[event_source(native)]
class CEventSrc {
public:
   __event void event1() {   // C3717
   }

   // remove definition for event1 and substitute following declaration
   // __event void event1();
};

[event_receiver(native)]
class CEventRec {
public:
   void handler1() {
   }

   void HookEvents(CEventSrc* pSrc) {
      __hook(CEventSrc::event1, pSrc, CEventRec::handler1);
   }

   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(CEventSrc::event1, pSrc, CEventRec::handler1);
   }
};

int main() {
}
```
