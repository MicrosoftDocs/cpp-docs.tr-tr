---
title: "Derleyici Uyarısı (düzey 1) C4930 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4930
dev_langs: C++
helpviewer_keywords: C4930
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7a09baa7f7918bfe861bea1b3d67744e87098a26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4930"></a>Derleyici Uyarısı (düzey 1) C4930
'prototip': çağrılmaz örneklenmiş işlevi (yönelik bir değişken tanımını oldu mu?)  
  
 Derleyici kullanılmayan işlev prototipi algıladı. Prototip bir değişken bildirimi amaçlanıyorsa, açık/kapalı parantez kaldırın.  
  
 Aşağıdaki örnek C4930 oluşturur:  
  
```  
// C4930.cpp  
// compile with: /W1  
class Lock {  
public:  
   int i;  
};  
  
void f() {  
   Lock theLock();   // C4930  
   // try the following line instead  
   // Lock theLock;  
}  
  
int main() {  
}  
```  
  
 Bir işlev prototipi bildirimi ve bir işlev çağrısı derleyici ayırt edemediğinde C4930 da oluşabilir.  
  
 Aşağıdaki örnek C4930 oluşturur:  
  
```  
// C4930b.cpp  
// compile with: /EHsc /W1  
  
class BooleanException  
{  
   bool _result;  
  
public:  
   BooleanException(bool result)  
      : _result(result)  
   {  
   }  
  
   bool GetResult() const  
   {  
      return _result;  
   }  
};  
  
template<class T = BooleanException>  
class IfFailedThrow  
{  
public:  
   IfFailedThrow(bool result)  
   {  
      if (!result)  
      {  
         throw T(result);  
      }  
   }  
};  
  
class MyClass  
{  
public:  
   bool MyFunc()  
   {  
      try  
      {  
         IfFailedThrow<>(MyMethod()); // C4930  
  
         // try one of the following lines instead  
         // IfFailedThrow<> ift(MyMethod());  
         // IfFailedThrow<>(this->MyMethod());  
         // IfFailedThrow<>((*this).MyMethod());  
  
         return true;  
      }  
      catch (BooleanException e)  
      {  
         return e.GetResult();  
      }  
   }  
  
private:  
   bool MyMethod()  
   {  
      return true;  
   }  
};  
  
int main()  
{  
   MyClass myClass;  
   myClass.MyFunc();  
}  
```  
  
 Yukarıdaki örnekte, sıfır bağımsız değişken alan bir yöntemin sonucu, adlandırılmamış yerel sınıf değişkeni oluşturucuya bağımsız değişken olarak geçirilir. Çağrı yerel değişken adlandırma ya da yöntem çağrısı uygun işaretçi-üye işleci birlikte bir nesne örneği ile önek tarafından disambiguated.