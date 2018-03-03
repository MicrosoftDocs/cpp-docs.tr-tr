---
title: "Derleyici Hatası C3714 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3714
dev_langs:
- C++
helpviewer_keywords:
- C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69f3f5c90524b02cad8a36babaceeb32544e7aff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3714"></a>Derleyici Hatası C3714
'yöntemi': 'yöntemi' olay işleyicisi yöntemi aynı çağırma kaynağı olarak olmalıdır  
  
 Aynı çağırma kaynak olay yöntemi olarak kullanmayan bir olay işleyicisi yöntemi tanımlı. Bu hatayı düzeltmek için bu kaynak olay yönteminin aynı çağırma kuralları olay işleyicisi yöntemi verin. Örneğin, aşağıdaki kodu çağırma kuralları olun `handler1` ve `event1` eşleşen ([__cdecl](../../cpp/cdecl.md) veya [__stdcall](../../cpp/stdcall.md) veya diğerleri). Kaldırma hem bildirimleri kuralı anahtar sözcükleri çağırma de sorunu çözmek ve neden `event1` ve `handler1` varsayılan olarak [thiscall](../../cpp/thiscall.md) çağırma. Bkz: [çağırma kuralları](../../cpp/calling-conventions.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C3714 oluşturur:  
  
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