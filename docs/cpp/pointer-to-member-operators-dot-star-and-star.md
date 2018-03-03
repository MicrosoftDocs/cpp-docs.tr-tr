---
title: "Üye işaretçileri işleçleri:. * ve -&gt;* | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- .*
- ->*
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], pointer
- pointer-to-member operators [C++]
- .* operator
- expressions [C++], operators
- ->* operator
ms.assetid: 2632be3f-1c81-4523-b56c-982a92a68688
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6db7b7190a1374564071775ce2ea6c0777bdf567
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="pointer-to-member-operators--and--gt"></a>Üye işaretçileri işleçleri:. * ve -&gt;*
## <a name="syntax"></a>Sözdizimi  
  
```  
expression .* expression  
expression ->* expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İşaretçi-üye işleçleri. * ve ->\*, belirli bir sınıf üyesi ifadesinin sol tarafta belirtilen nesne değerini döndürür.  Sağ tarafta sınıfın bir üyesi belirtilmelidir.  Aşağıdaki örnekte, bu işleçlerin nasıl kullanılacağı gösterilmektedir.  
  
```  
// expre_Expressions_with_Pointer_Member_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
class Testpm {  
public:  
   void m_func1() { cout << "m_func1\n"; }  
   int m_num;  
};  
  
// Define derived types pmfn and pmd.  
// These types are pointers to members m_func1() and  
// m_num, respectively.  
void (Testpm::*pmfn)() = &Testpm::m_func1;  
int Testpm::*pmd = &Testpm::m_num;  
  
int main() {  
   Testpm ATestpm;  
   Testpm *pTestpm = new Testpm;  
  
// Access the member function  
   (ATestpm.*pmfn)();  
   (pTestpm->*pmfn)();   // Parentheses required since * binds  
                        // less tightly than the function call.  
  
// Access the member data  
   ATestpm.*pmd = 1;  
   pTestpm->*pmd = 2;  
  
   cout  << ATestpm.*pmd << endl  
         << pTestpm->*pmd << endl;  
   delete pTestpm;  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
m_func1  
m_func1  
1  
2  
```  
  
 Yukarıdaki örnekte bir üye işaretçisi olan `pmfn`, `m_func1` üye işlevini çağırmak için kullanılır. Diğer bir üye işaretçisi olan `pmd`, `m_num` üyesine erişmek için kullanılır.  
  
 . * ikili işleci, sınıf türünden bir nesne olması gereken ilk işlenenini, üye işleci türünde olması gereken ikinci işleneniyle birleştirir.  
  
 İkili işleç -> * sınıfı türünde bir nesne için bir işaretçi olması gereken kendi ilk işleneni, bir işaretçi-üye türü olmalıdır, ikinci işlenen ile birleştirir.  
  
 .* işlecini içeren bir ifadede, ilk işlenen ikinci işlenende belirtilen üyenin işaretçisinin sınıf türünde olmalı ve bu işaretçi tarafından erişilebilmelidir veya bu sınıftan belirsiz bir şekilde yürütülen ve bu sınıf tarafından erişilebilen bir türde olmalıdır.  
  
 -> İçeren bir ifadede * işleci, ikinci işlenen ilk işlenen türü türü "sınıf türü işaretçi" belirtilmesi gerekir ya da, türü kesin bir şekilde bu sınıftan türetilmiş olmalıdır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki sınıfları ve program parçasını göz önünde bulundurun:  
  
```  
// expre_Expressions_with_Pointer_Member_Operators2.cpp  
// C2440 expected  
class BaseClass {  
public:  
   BaseClass(); // Base class constructor.  
   void Func1();  
};  
  
// Declare a pointer to member function Func1.  
void (BaseClass::*pmfnFunc1)() = &BaseClass::Func1;  
  
class Derived : public BaseClass {  
public:  
   Derived();  // Derived class constructor.  
   void Func2();  
};  
  
// Declare a pointer to member function Func2.  
void (Derived::*pmfnFunc2)() = &Derived::Func2;  
  
int main() {  
   BaseClass ABase;  
   Derived ADerived;  
  
   (ABase.*pmfnFunc1)();   // OK: defined for BaseClass.  
   (ABase.*pmfnFunc2)();   // Error: cannot use base class to  
                           // access pointers to members of  
                           // derived classes.   
  
   (ADerived.*pmfnFunc1)();   // OK: Derived is unambiguously  
                              // derived from BaseClass.   
   (ADerived.*pmfnFunc2)();   // OK: defined for Derived.  
}  
```  
  
 Sonucunu. * veya ->\* işaretçi-üye işleçleri olduğu nesne veya işlev işaretçiden üyeye bildiriminde belirtilen türde. Bu nedenle, yukarıdaki örnekte `ADerived.*pmfnFunc1()` ifadesinin sonucu void döndüren bir işlev işaretçisidir. Bu, ikinci işlenen l değerindeyse bir l değeridir.  
  
> [!NOTE]
>  Üye işleçleri işaretçilerinden birinin sonucu işlevse, sonuç yalnızca işlev çağrısı işlecinin işleneni olarak kullanılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)

