---
title: Derleyici Hatası C3709 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3709
dev_langs:
- C++
helpviewer_keywords:
- C3709
ms.assetid: d5576b04-2f93-420a-8f3e-8b8e987e8dab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e0e64a07257cf55df028383cd5347ad64eb702f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091731"
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