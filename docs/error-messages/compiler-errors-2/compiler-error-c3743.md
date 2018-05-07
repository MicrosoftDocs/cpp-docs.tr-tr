---
title: Derleyici Hatası C3743 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3743
dev_langs:
- C++
helpviewer_keywords:
- C3743
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc9a0bab67bb4fb15627dde42b1d538a0ecce9d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3743"></a>Derleyici Hatası C3743
yalnızca kanca/tüm arabirim event_receiver 'layout_dependent' parametresi true olduğunda unhook  
  
 [__Unhook](../../cpp/unhook.md) işlevi değişir geçirilen değere göre sürdüğünü parametre sayısının `layout_dependent` parametresinde [event_receiver](../../windows/event-receiver.md) sınıfı.  
  
 Aşağıdaki örnek C3743 oluşturur:  
  
```  
// C3743.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
[module(name="xx")];  
[object] __interface I { HRESULT f(); };  
  
[event_receiver(com, layout_dependent=true), coclass]  
struct R : I {  
        HRESULT f() {  
      return 0;  
   }  
        R() {  
   }  
  
   R(I* a) {  
      __hook(I, a, &R::f);   // C3743  
      // The following line resolves the error.  
      // __hook(I, a);  
   }  
};  
```