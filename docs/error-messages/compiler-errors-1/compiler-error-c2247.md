---
title: Derleyici hatası C2247
ms.date: 11/04/2016
f1_keywords:
- C2247
helpviewer_keywords:
- C2247
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
ms.openlocfilehash: e82b406b20d77a824b62207b1766fec55ac65c5c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758911"
---
# <a name="compiler-error-c2247"></a>Derleyici hatası C2247

' class ', ' class ' öğesinden devralacak şekilde ' Identifier ' kullandığından ' tanımlayıcı ' erişilebilir değil

`identifier`, özel veya korumalı erişimle belirtilen bir sınıftan devralınır.

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

Visual Studio .NET 2003 ve Visual Studio .NET sürümlerinde geçerli olan kod için C++, üyeyi türün bir arkadaşınız olarak bildirin. Genel devralma de kullanılabilir.

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

Visual Studio .NET 2003 ve Visual Studio .NET sürümlerinde C++geçerli olan kod için kapsam işlecini kullanın.

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
