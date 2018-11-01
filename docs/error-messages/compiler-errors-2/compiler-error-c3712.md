---
title: Derleyici Hatası C3712
ms.date: 11/04/2016
f1_keywords:
- C3712
helpviewer_keywords:
- C3712
ms.assetid: 65b1fcaf-be89-4c55-9e40-25ec03457253
ms.openlocfilehash: 0b84f4562dcc0dd5dcc3ecb647316772efab6b38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492683"
---
# <a name="compiler-error-c3712"></a>Derleyici Hatası C3712

'method': olay işleyicisi yöntemi 'method' kaynağı aynı türü döndürmelidir

Kaynak olay yöntemi aynı türü döndürmedi bir olay işleyicisi yönteminde tanımlanmış. Bu hatayı düzeltmek için olay işleyicisi yöntemi aynı dönüş türü, kaynak olay yöntemi olarak verin.

Aşağıdaki örnek, C3712 oluşturur:

```
// C3712.cpp
// compile with: /c
[event_source(native)]
class CEventSrc {
public:
   __event void event1();
};

[event_receiver(native)]
class CEventRec {
public:
   int handler1() { return 0; }
   // try the following line instead
   // void handler1() {}

   void HookEvents(CEventSrc* pSrc) {
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712
   }
   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712
   }
};
```