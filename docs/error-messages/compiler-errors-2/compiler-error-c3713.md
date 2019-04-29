---
title: Derleyici Hatası C3713
ms.date: 11/04/2016
f1_keywords:
- C3713
helpviewer_keywords:
- C3713
ms.assetid: 75c6b9b6-955b-49bd-9bc8-ced88b496a1f
ms.openlocfilehash: 8c8c3b5e6016c7f4af471a163463c91d478fea91
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328386"
---
# <a name="compiler-error-c3713"></a>Derleyici Hatası C3713

'method': olay işleyicisi yöntemi, aynı işlev parametrelerine kaynağı olarak 'method' olması gerekir

Kaynak olay yöntemi olarak aynı parametreleri kullanmayan olay işleyicisi yöntemi tanımladığınız. Bu hatayı düzeltmek için olay işleyicisi yöntemi kaynak olay yöntemi, aynı parametreleri verin.

Aşağıdaki örnek, C3713 oluşturur:

```
// C3713.cpp
// compile with: /c
[event_source(native)]
class CEventSrc {
public:
   __event void event1(int nValue);
   // try the following line instead
   // __event void event1();
};

[event_receiver(native)]
class CEventRec {
public:
   void handler1() {}

   void HookEvents(CEventSrc* pSrc) {
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3713
   }

   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3713
   }
};
```