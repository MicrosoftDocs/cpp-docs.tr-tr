---
title: Derleyici hatası C3724
ms.date: 11/04/2016
f1_keywords:
- C3724
helpviewer_keywords:
- C3724
ms.assetid: cab8aba7-14fc-406f-8cc6-32744c8f31c1
ms.openlocfilehash: b107137652c4efde43fdfe9c991240767eb5ced7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752983"
---
# <a name="compiler-error-c3724"></a>Derleyici hatası C3724

olaylarla çoklu iş parçacığı kullanmak için \<Windows. h > #include gerekir

Olaylar ile çoklu iş parçacığı kullanıyorsanız, Windows. h dosyası gereklidir. Bu hatayı onarmak için, olay kaynakları ve olay alıcılarının tanımlandığı dosyanın üst kısmına `#include <windows.h>` ekleyin.

```cpp
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
