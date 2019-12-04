---
title: Derleyici hatası C3379
ms.date: 11/04/2016
f1_keywords:
- C3379
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
ms.openlocfilehash: 9d99214f3ad7e7db1edc215d94c98e9cf9ec4ca2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742905"
---
# <a name="compiler-error-c3379"></a>Derleyici hatası C3379

' class ': iç içe bir sınıfın bildiriminin bir parçası olarak bir derleme erişim belirticisi olamaz

Sınıf veya yapı gibi yönetilen bir türe uygulandığında, [ortak](../../cpp/public-cpp.md) ve [özel](../../cpp/private-cpp.md) anahtar sözcükler, sınıfın derleme meta verileri aracılığıyla gösterilip gösterilmeyeceğini belirtir. `public` veya `private`, kapsayan sınıfa ait derleme erişimini devralacak olan iç içe bir sınıfa uygulanamaz.

[/Clr](../../build/reference/clr-common-language-runtime-compilation.md)ile kullanıldığında, `ref` ve `value` anahtar sözcükleri bir sınıfın yönetildiğini belirtir (bkz. [sınıflar ve yapılar](../../extensions/classes-and-structs-cpp-component-extensions.md)).

Aşağıdaki örnek C3379 oluşturur:

```cpp
// C3379a.cpp
// compile with: /clr
using namespace System;

public ref class A {
public:
   static int i = 9;

   public ref class BA {   // C3379
   // try the following line instead
   // ref class BA {
   public:
      static int ii = 8;
   };
};

int main() {

   A^ myA = gcnew A;
   Console::WriteLine(myA->i);

   A::BA^ myBA = gcnew A::BA;
   Console::WriteLine(myBA->ii);
}
```
