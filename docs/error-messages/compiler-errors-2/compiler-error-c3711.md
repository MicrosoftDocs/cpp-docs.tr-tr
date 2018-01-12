---
title: "Derleyici Hatası C3711 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3711
dev_langs: C++
helpviewer_keywords: C3711
ms.assetid: 26d581cc-2153-4ee0-b814-a371184be3e1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 74b2f516bb727c1753a28de4dc676d293a0e1fd0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3711"></a>Derleyici Hatası C3711
'yöntemi': bir yönetilmeyen olay kaynağı yöntemi geçersiz kılma veya tamsayı türü döndürmesi gerekir  
  
 Bir yöntem void döndürmedi olay kaynağı veya tamsayı türü tanımlanmış. Bu hatayı düzeltmek için olay ve olay işleyicisi bir dönüş türüne sahip olun `void` veya tamsayı türü gibi `int` veya `long`.  
  
 Aşağıdaki örnek C3711 oluşturur:  
  
```  
// C3711.cpp  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[event_source(native)]  
class CEventSrc {  
public:  
   __event float event1();   // C3711  
   // try the following line instead  
   // __event int event1();  
   // also change the handler, below  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   float handler1() {         // change float to int  
      return 0.0;             // change 0.0 to 0  
   }  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
};  
  
int main() {  
}  
```