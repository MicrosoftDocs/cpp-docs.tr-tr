---
title: "Derleyici Hatası C3703 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3703
dev_langs: C++
helpviewer_keywords: C3703
ms.assetid: 7e3677d9-f2be-4c26-998f-423564e9023c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e6ef53628f3a24dd3e6f7f387491fc959d70aa04
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3703"></a>Derleyici Hatası C3703
'olay işleyicisi': 'event' kaynağı olarak bir olay işleyicisi yöntemi aynı depolama sınıfı olması gerekir  
  
 Bir [olay](../../cpp/event-handling.md) farklı depolama sınıfı bu sayfaya olay işleyicisi daha vardır. Örneğin, olay işleyicisi statik üye işlevidir ve olay statik değilse bu hata oluşur. Bu hatayı düzeltmek için olay ve olay işleyicisi aynı depolama sınıfı sağlar.  
  
 Aşağıdaki örnek C3703 oluşturur:  
  
```  
// C3703.cpp  
// C3703 expected  
#include <stdio.h>  
  
[event_source(type=native)]  
class CEventSrc {  
public:  
   __event static void MyEvent();  
};  
  
[event_receiver(type=native)]  
class CEventHandler {  
public:  
   // delete the following line to resolve  
   void MyHandler() {}  
  
   // try the following line instead  
   // static void MyHandler() {}  
  
   void HookIt(CEventSrc* pSource) {  
      __hook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);  
   }  
  
   void UnhookIt(CEventSrc* pSource) {  
      __unhook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);  
   }  
};  
  
int main() {  
   CEventSrc src;  
   CEventHandler hnd;  
  
   hnd.HookIt(&src);  
   __raise src.MyEvent();  
   hnd.UnhookIt(&src);  
}  
```