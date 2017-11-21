---
title: "Derleyici Hatası C3713 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3713
dev_langs: C++
helpviewer_keywords: C3713
ms.assetid: 75c6b9b6-955b-49bd-9bc8-ced88b496a1f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 13387629ab4dda3965bc8b835e2e092ef29ef880
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3713"></a>Derleyici Hatası C3713
'yöntemi': 'yöntemi' olay işleyicisi yöntemi aynı işlev parametreleri kaynak olarak olmalıdır  
  
 Aynı parametrelere kaynak olay yöntemi olarak kullanmayan bir olay işleyicisi yöntemi tanımlı. Bu hatayı düzeltmek için bu kaynak olay yönteminin aynı parametreleri olay işleyicisi yöntemi verin.  
  
 Aşağıdaki örnek C3713 oluşturur:  
  
```  
// C3713.cpp  
// compile with: /c  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void event1(int nValue);  
   // try the following line instead  
   // __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3713  
   }  
  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3713  
   }  
};  
```