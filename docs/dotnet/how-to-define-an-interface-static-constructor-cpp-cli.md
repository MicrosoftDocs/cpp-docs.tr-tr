---
title: 'Nasıl yapılır: Arabirim statik oluşturucusunu tanımlama (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- constructors [C++]
- static constructors, interface
- interface static constructor
ms.assetid: 1f031cb2-e94f-43dc-819b-44cf2faaaa49
ms.openlocfilehash: 326b315e1e6c4defbef3ab6e487c78635e0aa50f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378988"
---
# <a name="how-to-define-an-interface-static-constructor-ccli"></a>Nasıl yapılır: Arabirim statik oluşturucusunu tanımlama (C++/CLI)

Bir arabirim statik veri üyeleri başlatmak için kullanılan bir statik Oluşturucu olabilir.  Statik Oluşturucu en fazla bir kez çağrılır ve bir statik arabirim üyesini erişilen ilk önce çağrılır.

## <a name="example"></a>Örnek

```
// mcppv2_interface_class2.cpp
// compile with: /clr
using namespace System;

interface struct MyInterface {
   static int i;
   static void Test() {
      Console::WriteLine(i);
   }

   static MyInterface() {
      Console::WriteLine("in MyInterface static constructor");
      i = 99;
   }
};

ref class MyClass : public MyInterface {};

int main() {
   MyInterface::Test();
   MyClass::MyInterface::Test();

   MyInterface ^ mi = gcnew MyClass;
   mi->Test();
}
```

```Output
in MyInterface static constructor
99
99
99
```

## <a name="see-also"></a>Ayrıca bkz.

[arabirim sınıfı](../extensions/interface-class-cpp-component-extensions.md)
