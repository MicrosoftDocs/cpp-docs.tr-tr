---
title: Derleyici Hatası C3717 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3717
dev_langs:
- C++
helpviewer_keywords:
- C3717
ms.assetid: ae4fceb1-2583-4577-b2f1-40971a017055
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75c770ecfc914c033c1db71578cda137d632e363
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086703"
---
# <a name="compiler-error-c3717"></a>Derleyici Hatası C3717

'method': olay başlayan bir yöntem tanımlanamaz

Bir uygulama içeren bir olay yöntemi bildirdiğiniz. Bir [__event](../../cpp/event.md) yöntem bildiriminde bir tanıma sahip olamaz. Bu hatayı düzeltmek için hiçbir olay yöntem bildirimleri tanımlara sahip olun. Örneğin, aşağıdaki kod işlevi gövdeden kaldırın `event1` açıklamaları tarafından belirtildiği şekilde bildirimi.

Aşağıdaki örnek, C3717 oluşturur:

```
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