---
title: Derleyici hatası C3703
ms.date: 11/04/2016
f1_keywords:
- C3703
helpviewer_keywords:
- C3703
ms.assetid: 7e3677d9-f2be-4c26-998f-423564e9023c
ms.openlocfilehash: 1071623c8dbaef52a6a391d8858e7502de9c74b4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758001"
---
# <a name="compiler-error-c3703"></a>Derleyici hatası C3703

' olay işleyicisi ': olay işleyicisi yöntemi, ' Event ' kaynağı ile aynı depolama sınıfına sahip olmalıdır

Bir [olayın](../../cpp/event-handling.md) , bağlandığı olay işleyicisinden farklı bir depolama sınıfı vardır. Örneğin, olay işleyicisi statik bir üye işlevse ve olay statik değilse bu hata oluşur. Bu hatayı onarmak için olaya ve olay işleyicisine aynı depolama sınıfına sahip olmanız gerekir.

Aşağıdaki örnek C3703 oluşturur:

```cpp
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
