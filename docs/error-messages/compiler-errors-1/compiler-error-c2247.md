---
title: Derleyici Hatası C2247
ms.date: 11/04/2016
f1_keywords:
- C2247
helpviewer_keywords:
- C2247
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
ms.openlocfilehash: ab1f83e2075128441cbffd2d939e3b99b45be4c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596438"
---
# <a name="compiler-error-c2247"></a>Derleyici Hatası C2247

'identifier' 'class', ' sınıfından ' için 'belirticisi' kullandığından erişilemiyor

`identifier` Özel veya korumalı erişimle bildirilen bir sınıftan devralınır.

Aşağıdaki örnek, C2247 oluşturur:

```
// C2247.cpp
class A {
public:
   int i;
};
class B : private A {};    // B inherits a private A
class C : public B {} c;   // so even though C's B is public
int j = c.i;               // C2247, i not accessible
```

Bu hata için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucu olarak da oluşturulabilir: erişim denetimi ile korumalı üyeler. Korumalı bir üye (n), yalnızca bir üye işlevi, (n) üyesi olduğu sınıfından (A) devralan bir sınıfın (B) üzerinden erişilebilir.

Visual Studio .NET 2003 ve Visual Studio .NET Visual C++ sürümü geçerli kod üyesinin bir arkadaş türü bildirin. Genel devralma de kullanılabilir.

```
// C2247b.cpp
// compile with: /c
// C2247 expected
class A {
public:
   void f();
   int n;
};

class B: protected A {
   // Uncomment the following line to resolve.
   // friend void A::f();
};

void A::f() {
   B b;
   b.n;
}
```

C2247 da oluşturulabilir için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucu: özel temel erişilemez sınıfların artık. Özel bir temel sınıf türüne bir sınıf (A) (C) B bir taban sınıfı olarak kullanan bir türü için erişilebilir olmamalıdır (B).

Visual Studio .NET 2003 ve Visual Studio .NET Visual C++ sürümü geçerli kod kapsamı işlecini kullanın.

```
// C2247c.cpp
// compile with: /c
struct A {};

struct B: private A {};

struct C : B {
   void f() {
      A *p1 = (A*) this;   // C2247
      // try the following line instead
      // ::A *p2 = (::A*) this;
   }
};
```