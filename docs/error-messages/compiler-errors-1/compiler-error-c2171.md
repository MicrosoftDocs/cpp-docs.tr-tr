---
title: "Derleyici Hatası C2171 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2171
dev_langs: C++
helpviewer_keywords: C2171
ms.assetid: a80343b5-ab3f-4413-b6f1-3ce9d7e519e5
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8dffa2f0302e80e4bfa702ec3beec71296fdcddc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2171"></a>Derleyici Hatası C2171
'işleci': 'type' türündeki işlenenler üzerinde geçersiz  
  
 Birli işleç geçersiz işlenen türü ile kullanılır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2171 oluşturur.  
  
```  
// C2171.cpp  
int main() {  
   double d, d1;  
   d = ~d1;   // C2171  
  
   // OK  
   int d2 = 0, d3 = 0;  
   d2 = ~d3;  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2171 oluşturur.  
  
```  
// C2171_b.cpp  
// compile with: /c  
class A {  
public:  
   A() { STF( &A::D ); }  
  
   void D() {}  
   void DTF() {  
      (*TF)();   // C2171  
      (this->*TF)();   // OK  
   }  
  
   void STF(void (A::*fnc)()) {  
      TF = fnc;  
   }  
  
private:  
   void (A::*TF)();  
};  
```