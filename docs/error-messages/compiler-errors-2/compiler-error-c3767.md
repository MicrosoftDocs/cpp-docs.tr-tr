---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3767'
title: Derleyici hatası C3767
ms.date: 11/04/2016
f1_keywords:
- C3767
helpviewer_keywords:
- C3767
ms.assetid: 5247cdcd-639c-4527-bd37-37e74c4e8fab
ms.openlocfilehash: 6d8780dde6ba6d831b1e47c174ef3609086c46ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291850"
---
# <a name="compiler-error-c3767"></a>Derleyici hatası C3767

' function ' aday işlevleri erişilebilir değil

Bir sınıfta tanımlanan arkadaş işlevinin, genel ad alanı kapsamında tanımlandıkları ve bildirildiği gibi değerlendirilmeyeceği varsayılır. Ancak, bağımsız değişkene bağlı arama ile bulunabilir.

Ayrıca, C3767 bir önemli değişiklik yüzünden olabilir: yerel türler artık **/clr** derlemesinde varsayılan olarak özeldir; daha fazla bilgi için bkz. [tür görünürlüğü](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3767 oluşturur:

```cpp
// C3767a.cpp
// compile with: /clr
using namespace System;
public delegate void TestDel();

public ref class MyClass {
public:
   static event TestDel^ MyClass_Event;
};

public ref class MyClass2 : public MyClass {
public:
   void Test() {
      MyClass^ patient = gcnew MyClass;
      patient->MyClass_Event();
    }
};

int main() {
   MyClass^ x = gcnew MyClass;
   x->MyClass_Event();   // C3767

   // OK
   MyClass2^ y = gcnew MyClass2();
   y->Test();
};
```

Aşağıdaki örnek C3767 oluşturur:

```cpp
// C3767c.cpp
// compile with: /clr /c

ref class Base  {
protected:
   void Method() {
      System::Console::WriteLine("protected");
   }
};

ref class Der : public Base {
   void Method() {
      ((Base^)this)->Method();   // C3767
      // try the following line instead
      // Base::Method();
   }
};
```
