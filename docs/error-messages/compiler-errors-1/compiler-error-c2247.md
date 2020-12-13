---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2247'
title: Derleyici hatası C2247
ms.date: 11/04/2016
f1_keywords:
- C2247
helpviewer_keywords:
- C2247
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
ms.openlocfilehash: 480d3862a1f96517ecce11be5c695e106eb58d7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177945"
---
# <a name="compiler-error-c2247"></a>Derleyici hatası C2247

' class ', ' class ' öğesinden devralacak şekilde ' Identifier ' kullandığından ' tanımlayıcı ' erişilebilir değil

`identifier` , özel veya korumalı erişimle belirtilen bir sınıftan devralınır.

Aşağıdaki örnek C2247 oluşturur:

```cpp
// C2247.cpp
class A {
public:
   int i;
};
class B : private A {};    // B inherits a private A
class C : public B {} c;   // so even though C's B is public
int j = c.i;               // C2247, i not accessible
```

Bu hata, Visual Studio .NET 2003: korumalı üyelerle erişim denetimi için yapılan derleyici uygunluk işinin sonucu olarak da oluşturulabilir. Korunan bir üyeye (n) yalnızca, (n) öğesinin üyesi olduğu sınıftan (A) devralan bir sınıfın (B) üye işlevi üzerinden erişilebilir.

Hem Visual Studio .NET 2003 hem de Visual C++ Visual Studio .NET sürümlerinde geçerli olan kod için, üyeyi türün bir arkadaşınız olarak bildirin. Genel devralma de kullanılabilir.

```cpp
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

C2247, Visual Studio .NET 2003 için yapılan derleyici uygunluk işinin sonucu olarak da oluşturulabilir: özel temel sınıflar artık erişilemez durumda. Bir türe (B) özel temel sınıf olan bir sınıf (A), B 'yi temel sınıf olarak kullanan bir tür (C) için erişilebilir olmamalıdır.

Hem Visual Studio .NET 2003 hem de Visual C++ Visual Studio .NET sürümlerinde geçerli olan kod için scope işlecini kullanın.

```cpp
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
