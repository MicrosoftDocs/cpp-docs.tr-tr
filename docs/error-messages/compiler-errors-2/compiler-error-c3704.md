---
title: "Derleyici Hatası C3704 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3704
dev_langs:
- C++
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 720af3b0ae1fa0727041e03e1573fbba4dccfae5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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