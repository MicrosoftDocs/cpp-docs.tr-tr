---
title: Derleyici Hatası C3379 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3379
dev_langs:
- C++
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f90a4ccc17e63c21d4b6fb26e607450849f27b48
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109333"
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
