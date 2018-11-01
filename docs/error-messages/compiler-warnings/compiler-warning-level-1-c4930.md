---
title: Derleyici Uyarısı (düzey 1) C4930
ms.date: 11/04/2016
f1_keywords:
- C4930
helpviewer_keywords:
- C4930
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
ms.openlocfilehash: 15cd1ed61c747e2c9168b9fc0fee03dca8403a24
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560179"
---
# <a name="compiler-warning-level-1-c4930"></a>Derleyici Uyarısı (düzey 1) C4930

'prototip': prototipli işlev çağrılmadı (değişken bir tanım hedeflenen oldu mu?)

Derleyici bir kullanılmayan işlev prototipi algıladı. Prototip bir Değişken bildiriminde hedeflediyseniz, açma/kapama parantezleri kaldırın.

Aşağıdaki örnek, C4930 oluşturur:

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

Derleyici, bir işlev prototipi bildirimi ve bir işlev çağrısı arasında ayrım yapamaz C4930 da meydana gelebilir.

Aşağıdaki örnek, C4930 oluşturur:

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

Yukarıdaki örnekte, sıfır bağımsız değişken alan bir yöntemin sonucu yerel adsız sınıf değişkeni oluşturucusuna bağımsız değişken olarak geçirilir. Çağrı, yöntem çağrısının uygun işaretçi-üye işleci ile birlikte bir nesne örneği ile önek veya yerel değişken adlandırma disambiguated.