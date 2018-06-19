---
title: Derleyici Hatası C2064 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2064
dev_langs:
- C++
helpviewer_keywords:
- C2064
ms.assetid: 6cda05da-f437-4f50-9813-ae69538713a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b3e5e21d7c33c84bb531b53c08aefbfce9dc7fd8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167287"
---
# <a name="compiler-error-c2064"></a>Derleyici Hatası C2064
Terim N bağımsız değişken almama bir işleve değerlendirmez  
  
 İfade üzerinden işlevi için bir çağrı yapılır. Deyim, belirtilen sayıda bağımsız değişken isteyen bir işlevi için bir işaretçi değerlendirmez.  
  
 Bu örnekte, kod arama işlevleri olmayan işlev olarak çalışır. Aşağıdaki örnek C2064 oluşturur:  
  
```  
// C2064.cpp  
int i, j;  
char* p;  
void func() {  
   j = i();    // C2064, i is not a function  
   p();        // C2064, p doesn't point to a function  
}  
```  
  
 Statik olmayan üye işlevleri işaretçileri nesne örneği bağlamında çağırmanız gerekir. Aşağıdaki örnek C2064 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2064b.cpp  
struct C {  
   void func1(){}  
   void func2(){}  
};  
  
typedef void (C::*pFunc)();  
  
int main() {  
   C c;  
   pFunc funcArray[2] = {&C::func1, &C::func2};  
   (funcArray[0])();    // C2064   
   (c.*funcArray[0])(); // OK - function called in instance context  
}  
  
```  
  
 Bir sınıf içinde üye işlev işaretçileri arama nesne bağlamı da belirtmeniz gerekir. Aşağıdaki örnek C2064 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2064d.cpp  
// Compile by using: cl /c /W4 C2064d.cpp  
struct C {  
   typedef void (C::*pFunc)();  
   pFunc funcArray[2];  
   void func1(){}  
   void func2(){}  
   C() {  
      funcArray[0] = &C::func1;  
      funcArray[1] = &C::func2;  
   }  
   void func3() {  
      (funcArray[0])();   // C2064  
      (this->*funcArray[0])(); // OK - called in this instance context  
   }  
};  
```