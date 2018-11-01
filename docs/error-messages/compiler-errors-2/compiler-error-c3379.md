---
title: Derleyici Hatası C3379
ms.date: 11/04/2016
f1_keywords:
- C3379
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
ms.openlocfilehash: 2d6b2cb15cfaa0b72b946c0edb3b451737b51772
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553510"
---
# <a name="compiler-error-c3379"></a>Derleyici Hatası C3379

'class': iç içe geçmiş sınıf bildiriminin bir parçası bir derleme erişim belirticisi olamaz

Sınıf veya yapı, gibi bir yönetilen türü uygulandığında [genel](../../cpp/public-cpp.md) ve [özel](../../cpp/private-cpp.md) anahtar sözcükleri sınıfı derleme meta verileri kullanıma sunulacak olup olmadığını gösterir. `public` veya `private` derleme erişimi kapsayan sınıfın devralacak bir iç içe geçmiş sınıf uygulanamaz.

İle kullanıldığında [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), `ref` ve `value` anahtar sözcükleri belirten bir sınıf yönetilir (bkz [sınıfları ve yapıları](../../windows/classes-and-structs-cpp-component-extensions.md)).

Aşağıdaki örnek, C3379 oluşturur:

```
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
