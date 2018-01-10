---
title: "Derleyici Hatası C2775 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2775
dev_langs: C++
helpviewer_keywords: C2775
ms.assetid: 9c488508-ade0-48f1-b94f-d538d15f807a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 77462b90a0e24084426a8186912631cf6a323cb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2775"></a>Derleyici Hatası C2775
'tanımlayıcısı': Bu özellik ile ilişkili 'get' yöntemi yok  
  
 İle bir veri üyesi bildirilen [özelliği](../../cpp/property-cpp.md) genişletilmiş özniteliğine sahip olmayan bir `get` işlevi belirtildi, ancak bir ifadenin değerini almaya çalışır.  
  
 Aşağıdaki örnek C2775 oluşturur:  
  
```  
// C2775.cpp  
struct A {  
   __declspec(property(put=PutProp2, get=GetProp2)) int prop2;  
   int GetProp2(){return 0;}  
   void PutProp2(int){}  
  
   __declspec(property(put=PutProp)) int prop;  
   int PutProp(void){}  
  
};  
  
int main() {  
   A* pa = new A;  
   int x;  
   x = pa->prop;   // C2775  
   x = pa->prop2;  
}  
```