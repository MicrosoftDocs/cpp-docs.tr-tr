---
title: "Derleyici Hatası C3704 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3704
dev_langs: C++
helpviewer_keywords: C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ae48bc886aab0211063cc7a9c2e73f3c7bbdd368
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3704"></a>Derleyici Hatası C3704
'function': vararg yöntemi olayları yangın olamaz  
  
 Kullanmaya çalıştığınız [__event](../../cpp/event.md) vararg yöntemi. Bu hatayı düzeltmek için yerini `fireEvent(int i, ...)` çağıran `fireEvent(int i)` aşağıdaki kod örneğinde gösterildiği şekilde çağırın.  
  
 Aşağıdaki örnek C3704 oluşturur:  
  
```  
// C3704.cpp  
[ event_source(native) ]  
class CEventSrc {  
   public:  
      __event void fireEvent(int i, ...);   // C3704  
      // try the following line instead:  
      // __event void fireEvent(int i);  
};  
  
int main() {  
}  
```