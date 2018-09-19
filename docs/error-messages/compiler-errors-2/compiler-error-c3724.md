---
title: Derleyici Hatası C3724 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3724
dev_langs:
- C++
helpviewer_keywords:
- C3724
ms.assetid: cab8aba7-14fc-406f-8cc6-32744c8f31c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7e633594b1f5467c3a8a664029691423db5bb63
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115989"
---
# <a name="compiler-error-c3724"></a>Derleyici Hatası C3724

gereken #include \<windows.h > kullanılacak olaylarda çoklu iş parçacığı

Kullanırsanız windows.h dosyası gereklidir olaylarda çoklu iş parçacığı. Bu hatayı düzeltmek için ekleme `#include <windows.h>` üst dosyanın hangi olay kaynakları ve Olay alıcıları tanımlanır.

```
// C3724.cpp
// uncomment the following line to resolve
// #include <windows.h>

[event_source(native), threading(apartment)]
class CEventSrc {
public:
   __event void event1();   // C3724
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