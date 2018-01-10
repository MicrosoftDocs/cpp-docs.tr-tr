---
title: "Derleyici Hatası C3719 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3719
dev_langs: C++
helpviewer_keywords: C3719
ms.assetid: d0d59d4e-babb-4480-9ef7-70cf1a28165c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1e6f1f4ad2757d94ebff9c7f0906192944d9f5c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3719"></a>Derleyici Hatası C3719
'arabirimi': bir arabirim tabanlı olay kaynağı yalnızca COM olayları için kullanılabilir  
  
 Bir arabirim COM olmayan bağlamda bildirildi.  
  
 Aşağıdaki örnek C3719 oluşturur:  
  
```  
// C3719a.cpp  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];  
  
[object]  
__interface I {  
   HRESULT func1();  
};  
  
[event_source(native), coclass]  
struct A {  
   __event __interface I;   // C3719  
  
   // try the following line instead  
   // __event func2();  
};  
  
int main() {  
}  
```  
  
 Bu hatayı düzeltmek için uygulamanız [nesne](../../windows/object-cpp.md), [coclass](../../windows/coclass.md), [event_source](../../windows/event-source.md), ve [event_receiver](../../windows/event-receiver.md) yapmak için uygun öznitelikleri COM arabirimi sınıflarını kullandığınız sınıflar. Örneğin:  
  
```  
// C3719b.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[module(name="xx")];  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface I {  
   HRESULT f();  
};  
  
[coclass, event_source(com) , uuid("00000000-0000-0000-0000-000000000002")]  
struct MyStruct {  
   __event __interface I;  
};  
  
[event_receiver(com)]  
struct MyStruct2 {  
   void f() {  
   }  
   MyStruct2(I* pB) {  
      __hook(&I::f, pB, &MyStruct2::f);  
   }  
};  
  
int main()  
{  
}  
```