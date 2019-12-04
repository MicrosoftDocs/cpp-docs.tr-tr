---
title: Derleyici hatası C3714
ms.date: 11/04/2016
f1_keywords:
- C3714
helpviewer_keywords:
- C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
ms.openlocfilehash: 1078bf8a97f6cb7afeaf7046489fe262c0bb0199
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753334"
---
# <a name="compiler-error-c3714"></a>Derleyici hatası C3714

' Method ': olay işleyicisi yöntemi kaynak ' Yöntem ' ile aynı çağırma kuralına sahip olmalıdır

Kaynak olay yöntemiyle aynı çağırma kuralını kullanmayan bir olay işleyicisi yöntemi tanımladınız. Bu hatayı onarmak için, olay işleyicisi yöntemine kaynak olay yöntemi ile aynı çağırma kuralları verin. Örneğin, aşağıdaki kodda `handler1` ve `event1` eşleşmesi ([__cdecl](../../cpp/cdecl.md) ya da [__stdcall](../../cpp/stdcall.md) veya diğerleri) için çağırma kuralları oluşturun. Her iki bildirime çağrı kuralı anahtar sözcüklerini kaldırmak de sorunu çözerek `event1` ve `handler1` varsayılan olarak [thiscall](../../cpp/thiscall.md) çağırma kuralına neden olur. Daha fazla bilgi için bkz. [çağırma kuralları](../../cpp/calling-conventions.md) .

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
