---
title: Derleyici Hatası C3711 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3711
dev_langs:
- C++
helpviewer_keywords:
- C3711
ms.assetid: 26d581cc-2153-4ee0-b814-a371184be3e1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95b788e9ecb2aa8bd1bcf5865cf9ded0c925bf49
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116749"
---
# <a name="compiler-error-c3711"></a>Derleyici Hatası C3711

'method': yönetilmeyen bir olay kaynağı yöntemi void veya integral türü döndürmelidir

Bir yöntemi void döndürmedi olay kaynağı ya da integral türünde tanımlanan. Bu hatayı düzeltmek için olay ve olay işleyicisi bir dönüş türüne sahip olun `void` veya bir tamsayı türü gibi `int` veya `long`.

Aşağıdaki örnek, C3711 oluşturur:

```
// C3711.cpp
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[event_source(native)]
class CEventSrc {
public:
   __event float event1();   // C3711
   // try the following line instead
   // __event int event1();
   // also change the handler, below
};

[event_receiver(native)]
class CEventRec {
public:
   float handler1() {         // change float to int
      return 0.0;             // change 0.0 to 0
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