---
title: Derleyici Hatası C3714
ms.date: 11/04/2016
f1_keywords:
- C3714
helpviewer_keywords:
- C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
ms.openlocfilehash: 9bfdf8b26ab599ef1a28483af7ebc28f0dbc1912
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441879"
---
# <a name="compiler-error-c3714"></a>Derleyici Hatası C3714

'method': olay işleyicisi yöntemi, aynı çağrı kuralına kaynağı 'method' sahip olmalıdır

Aynı çağrı kuralına kaynak olay yöntemi olarak kullanmayan olay işleyicisi yöntemi tanımladığınız. Bu hatayı düzeltmek için olay işleyicisi yöntemi kaynak olay yöntemi olarak aynı çağırma kuralları verin. Örneğin, aşağıdaki kod, çağırma kuralları olun `handler1` ve `event1` eşleşen ([__cdecl](../../cpp/cdecl.md) veya [__stdcall](../../cpp/stdcall.md) veya diğerleri). Kaldırma kuralı anahtar sözcükleri hem bildirimlerinden farklıdır çağırma ayrıca sorunu ve neden `event1` ve `handler1` varsayılan [thiscall](../../cpp/thiscall.md) çağırma kuralı. Bkz: [çağırma kuralları](../../cpp/calling-conventions.md) daha fazla bilgi için.

Aşağıdaki örnek, C3714 oluşturur:

```
// C3714.cpp
// compile with: /c
// processor: x86
[event_source(native)]
class CEventSrc {
public:
   __event void __cdecl event1();
   // try the following line instead
   // __event void __stdcall event1();
};

[event_receiver(native)]
class CEventRec {
public:
   void __stdcall handler1() {}

   void HookEvents(CEventSrc* pSrc) {
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3714
   }

   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3714
   }
};
```