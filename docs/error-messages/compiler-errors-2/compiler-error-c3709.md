---
title: Derleyici Hatası C3709
ms.date: 11/04/2016
f1_keywords:
- C3709
helpviewer_keywords:
- C3709
ms.assetid: d5576b04-2f93-420a-8f3e-8b8e987e8dab
ms.openlocfilehash: 3eb2963916cbbcbd925f755f9162ce59e9bff569
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432770"
---
# <a name="compiler-error-c3709"></a>Derleyici Hatası C3709

'function': __hook içinde olay belirtmek için hatalı sözdizimi /\__unhook

Bir olay kaynağı ile belirttiğinizde [__hook](../../cpp/hook.md) veya [__unhook](../../cpp/unhook.md), ilk parametresi, geçerli olay yöntemi olmalıdır ve ikinci parametresi, geçerli olay kaynağı nesnesi (yöntem değil) olmalıdır.

Aşağıdaki örnek, C3709 oluşturur:

```
// C3709.cpp
// compile with: /LD
[event_source(native)]
class CEventSrc
{
public:
   __event void event1();
};

[event_receiver(native)]
class CEventRec
{
public:
   void handler1()
   {
   }

   void HookEvents(CEventSrc* pSrc)
   {
      __hook(bad, pSrc, CEventRec::handler1);   // C3709
      // Try the following line instead:
      // __hook(&CEventSrc::event1, pSrc, CEventRec::handler1);
   }

   void UnhookEvents(CEventSrc* pSrc)
   {
      __unhook(&CEventSrc::event1, pSrc, CEventRec::handler1);
   }
};
```