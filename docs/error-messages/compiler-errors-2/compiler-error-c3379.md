---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3379'
title: Derleyici hatası C3379
ms.date: 11/04/2016
f1_keywords:
- C3379
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
ms.openlocfilehash: 622a1327eb84d83fa24d8a084e3266183c669120
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220740"
---
# <a name="compiler-error-c3379"></a>Derleyici hatası C3379

' class ': iç içe bir sınıfın bildiriminin bir parçası olarak bir derleme erişim belirticisi olamaz

Sınıf veya yapı gibi yönetilen bir türe uygulandığında, [ortak](../../cpp/public-cpp.md) ve [özel](../../cpp/private-cpp.md) anahtar sözcükler, sınıfın derleme meta verileri aracılığıyla gösterilip gösterilmeyeceğini belirtir. `public` ya da `private` kapsayan sınıfın derleme erişimini devralacak iç içe bir sınıfa uygulanamaz.

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
