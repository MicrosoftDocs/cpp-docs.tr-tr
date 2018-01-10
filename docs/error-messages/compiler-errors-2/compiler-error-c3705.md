---
title: "Derleyici Hatası C3705 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3705
dev_langs: C++
helpviewer_keywords: C3705
ms.assetid: 8361017d-5782-4214-a9d7-e9825fd29bc8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e1d7a1df32d8ba78adffe5ebafb6a7cb13a876cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3705"></a>Derleyici Hatası C3705
'function': olay arabirimi bulunamıyor  
  
 COM olayları kullanmak için bir olay arabirimi tanımlamanız gerekir. Unutmayın `#include` COM olayları kullanmak için örnekte gösterildiği ATL üstbilgi dosyaları satırlık gereklidir. Bu hatayı düzeltmek için tanımını açıklamadan çıkarın `IEvents` örnek kodda arabirimi.  
  
 Aşağıdaki örnek C3705 oluşturur:  
  
```  
// C3705.cpp  
// compile with: /c  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];  
  
// Uncomment the following 4 lines to resolve.  
// [object, uuid("00000000-0000-0000-0000-000000000003")]  
// __interface IEvents : IUnknown {  
//    HRESULT event1([in] int i);  
// };  
  
[dual, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IBase {  
   HRESULT fireEvents();  
};  
  
[coclass, event_source(com), uuid("00000000-0000-0000-0000-000000000002")]  
class CEventSrc : public IBase {  
public:  
   __event __interface IEvents;   // C3705 uncomment IEvents to resolve  
   HRESULT fireEvents() {  
      HRESULT hr = IEvents_event1(123);  
      return hr;  
   }  
};  
```