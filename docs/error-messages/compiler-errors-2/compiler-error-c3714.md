---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3714'
title: Derleyici hatası C3714
ms.date: 11/04/2016
f1_keywords:
- C3714
helpviewer_keywords:
- C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
ms.openlocfilehash: a01544558a156b746c16e731584e30bab7a77825
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241631"
---
# <a name="compiler-error-c3714"></a>Derleyici hatası C3714

' Method ': olay işleyicisi yöntemi kaynak ' Yöntem ' ile aynı çağırma kuralına sahip olmalıdır

Kaynak olay yöntemiyle aynı çağırma kuralını kullanmayan bir olay işleyicisi yöntemi tanımladınız. Bu hatayı onarmak için, olay işleyicisi yöntemine kaynak olay yöntemi ile aynı çağırma kuralları verin. Örneğin, aşağıdaki kodda çağırma kurallarını yapın `handler1` ve `event1` eşleştirin ([__cdecl](../../cpp/cdecl.md) veya [__stdcall](../../cpp/stdcall.md) veya diğerleri). Her iki bildirime çağrı kuralı anahtar sözcüklerini kaldırmak, sorunu da çözerek `event1` `handler1` [thiscall](../../cpp/thiscall.md) çağırma kuralına ve varsayılan olarak neden olur. Daha fazla bilgi için bkz. [çağırma kuralları](../../cpp/calling-conventions.md) .

Aşağıdaki örnek C3714 oluşturur:

```cpp
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
