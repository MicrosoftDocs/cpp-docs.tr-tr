---
title: "Derleyici Hatası C3741 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3741
dev_langs: C++
helpviewer_keywords: C3741
ms.assetid: ed311315-cc32-49c9-97fa-01b293d81526
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: edbdc98c4591b565edcbd0ff5eb484a115bff16e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3741"></a>Derleyici Hatası C3741
'class': bir coclass'ı olmalıdır, event_receiver 'layout_dependent' parametresinin = true  
  
 Zaman `layout_dependent=true` için bir [event_receiver](../../windows/event-receiver.md) sınıfı, ardından sınıf de olmalıdır [coclass](../../windows/coclass.md) özniteliği.  
  
 Aşağıdaki örnek C3741 oluşturur  
  
```  
// C3741.cpp  
// compile with: /c  
// C3741 expected  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
[module(name="xx")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface I{ HRESULT f(); };  
  
// Delete the following line to resolve.  
[ event_receiver(com, layout_dependent=true)]  
  
// class or struct must be declared with coclass  
// Uncomment the following line to resolve.  
// [ event_receiver(com, layout_dependent=true), coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct R : I {  
   HRESULT f(){ return 0; }  
   R(){}  
   R(I* a){ __hook(I, a); }  
};  
```