---
title: Derleyici Uyarısı (düzey 2) C4250
ms.date: 11/04/2016
f1_keywords:
- C4250
helpviewer_keywords:
- C4250
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
ms.openlocfilehash: 03826f10659cbdf6035cd4dedebecca3e3302e3a
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052110"
---
# <a name="compiler-warning-level-2-c4250"></a>Derleyici Uyarısı (düzey 2) C4250

' Class1 ': ' Class2:: Member ' öğesini baskınlık aracılığıyla devralır

İki veya daha fazla üye aynı ada sahip. `class2`, bu üyeyi içeren diğer sınıfların temel sınıfı olduğundan devralınır.

C4250 bastırmak için, [Uyarı](../../preprocessor/warning.md) pragmasını kullanın.

Bir sanal temel sınıf birden çok türetilmiş sınıf arasında paylaşıldığından, türetilmiş sınıftaki bir ad temel sınıftaki bir adı ayırır. Örneğin, aşağıdaki sınıf hiyerarşisi söz konusu olduğunda, elmas içinde devralınan iki işlev tanımı vardır: zayıf sınıf aracılığıyla vbc:: Func () örneği ve baskın sınıf ile baskın:: Func (). Bir Diamond Class nesnesi aracılığıyla () nitelenmemiş çağrısı, her zaman Dominate:: Func () örneğini çağırır.  Zayıf sınıf Func () öğesinin bir örneğini tanıtmak olsaydı, hiçbir tanım neden olmaz ve çağrı belirsiz olarak işaretlenir.

```cpp
// C4250.cpp
// compile with: /c /W2
#include <stdio.h>
struct vbc {
   virtual void func() { printf("vbc::func\n"); }
};

struct weak : public virtual vbc {};

struct dominant : public virtual vbc {
   void func() { printf("dominant::func\n"); }
};

struct diamond : public weak, public dominant {};

int main() {
   diamond d;
   d.func();   // C4250
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek C4250 oluşturur.

```cpp
// C4250_b.cpp
// compile with: /W2 /EHsc
#include <iostream>
using namespace std;
class A {
public:
   virtual operator int () {
      return 2;
   }
};

class B : virtual public A {
public:
   virtual operator int () {
      return 3;
   }
};

class C : virtual public A {};

class E : public B, public C {};   // C4250

int main() {
   E eObject;
   cout << eObject.operator int() << endl;
}
```

## <a name="example"></a>Örnek

Bu örnekte daha karmaşık bir durum gösterilmektedir. Aşağıdaki örnek C4250 oluşturur.

```cpp
// C4250_c.cpp
// compile with: /W2 /EHsc
#include <iostream>
using namespace std;

class V {
public:
   virtual int f() {
      return 1024;
   }
};

class B : virtual public V {
public:
   int b() {
      return f(); // B::b() calls V::f()
   }
};

class M : virtual public V {
public:
   int f() {
      return 7;
   }
};

// because of dominance, f() is M::f() inside D,
// changing the meaning of B::b's f() call inside a D
class D : public B, public M {};   // C4250

int main() {
   D d;
   cout << "value is: " << d.b();   // invokes M::f()
}
```