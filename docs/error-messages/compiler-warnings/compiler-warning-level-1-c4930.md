---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4930'
title: Derleyici Uyarısı (düzey 1) C4930
ms.date: 11/04/2016
f1_keywords:
- C4930
helpviewer_keywords:
- C4930
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
ms.openlocfilehash: 9111b87ee2b281c7781e7115330634daefb14cc4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328070"
---
# <a name="compiler-warning-level-1-c4930"></a>Derleyici Uyarısı (düzey 1) C4930

' Prototype ': prototipi oluşturulmuş işlev çağrılmadı (bir değişken tanımmıdır?)

Derleyici kullanılmamış bir işlev prototipi algıladı. Prototip bir değişken bildirimi olarak tasarlanmışsa, açma/kapatma parantezleri kaldırın.

Aşağıdaki örnek C4930 oluşturur:

```cpp
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

C4930, derleyici bir işlev prototipi bildirimi ve bir işlev çağrısı arasında ayrım yapmadığından da oluşabilir.

Aşağıdaki örnek C4930 oluşturur:

```cpp
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

Yukarıdaki örnekte, sıfır bağımsız değişken alan bir yöntemin sonucu, adlandırılmamış bir yerel sınıf değişkeninin oluşturucusuna bağımsız değişken olarak geçirilir. Bu çağrı, yerel değişkeni adlandırarak veya yöntem çağrısının uygun işaretçiden üyeye işleciyle birlikte bir nesne örneğiyle önek olarak nitelenebilir.
