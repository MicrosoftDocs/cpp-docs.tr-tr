---
title: "Derleyici Hatası C2352 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2352
dev_langs: C++
helpviewer_keywords: C2352
ms.assetid: 0efad8cb-659f-4b3e-8f6f-9f8ec44d345c
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2f41907647f11a5f7ca47c272b735f2eeca0f452
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2352"></a>Derleyici Hatası C2352
'class::function': geçersiz bir statik olmayan üye işlevi çağrısı  
  
 A `static` üye işlevi statik olmayan üye işlevi çağrılır. Ya da statik işlev olarak sınıf dışında bir statik olmayan üye fonksiyonu çağırıldığı.  
  
 Aşağıdaki örnek C2352 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2352.cpp  
// compile with: /c  
class CMyClass {  
public:  
   static void func1();  
   void func2();  
   static void func3() {  
      func2();   // C2352 calls nonstatic func2  
      func1();   // OK calls static func1  
   }  
};  
```  
  
 Aşağıdaki örnek C2352 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2352b.cpp  
class MyClass {  
public:  
   void MyFunc() {}  
   static void MyFunc2() {}  
};  
  
int main() {  
   MyClass::MyFunc();   // C2352  
   MyClass::MyFunc2();   // OK  
}  
```