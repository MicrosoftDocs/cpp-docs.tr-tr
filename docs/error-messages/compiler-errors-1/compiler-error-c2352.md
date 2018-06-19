---
title: Derleyici Hatası C2352 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2352
dev_langs:
- C++
helpviewer_keywords:
- C2352
ms.assetid: 0efad8cb-659f-4b3e-8f6f-9f8ec44d345c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a0ed1942051929b4f1ba3391be0ceead7a75586
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196172"
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