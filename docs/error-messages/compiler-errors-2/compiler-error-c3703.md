---
title: Derleyici Hatası C3703
ms.date: 11/04/2016
f1_keywords:
- C3703
helpviewer_keywords:
- C3703
ms.assetid: 7e3677d9-f2be-4c26-998f-423564e9023c
ms.openlocfilehash: 0b34760bc3f5b23148ce84cf590685efad2008df
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428086"
---
# <a name="compiler-error-c3703"></a>Derleyici Hatası C3703

'olay işleyicisi': olay işleyicisi yöntemi 'event' kaynağı olarak aynı depolama sınıfına sahip olmalıdır

Bir [olay](../../cpp/event-handling.md) bunu kancalandı olay işleyicisi daha farklı bir depolama sınıfı vardır. Örneğin, bir statik üye işlevi olay işleyicisidir ve olay statik değilse bu hata oluşur. Bu hatayı düzeltmek için olay ve aynı depolama sınıfına olay işleyicisi verir.

Aşağıdaki örnek, C3703 oluşturur:

```
// C3703.cpp
// C3703 expected
#include <stdio.h>

[event_source(type=native)]
class CEventSrc {
public:
   __event static void MyEvent();
};

[event_receiver(type=native)]
class CEventHandler {
public:
   // delete the following line to resolve
   void MyHandler() {}

   // try the following line instead
   // static void MyHandler() {}

   void HookIt(CEventSrc* pSource) {
      __hook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);
   }

   void UnhookIt(CEventSrc* pSource) {
      __unhook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);
   }
};

int main() {
   CEventSrc src;
   CEventHandler hnd;

   hnd.HookIt(&src);
   __raise src.MyEvent();
   hnd.UnhookIt(&src);
}
```