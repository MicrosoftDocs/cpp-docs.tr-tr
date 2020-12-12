---
description: 'Hakkında daha fazla bilgi: yerel olarak belirtilen adlar için ad çözümlemesi'
title: Yerel Bildirimli Adlar için Ad Çözümü
ms.date: 11/04/2016
ms.assetid: 743b88f3-de11-48f4-ae83-931449ea3886
ms.openlocfilehash: 14530aae65940830db15f7e6fc0ec2c33935afe3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313781"
---
# <a name="name-resolution-for-locally-declared-names"></a>Yerel Bildirimli Adlar için Ad Çözümü

Şablon adının kendisi, şablon bağımsız değişkenleri ile veya onlar olmadan belirtilebilir. Sınıf şablonu kapsamında, adın kendisi şablonu belirtir. Şablonu uzmanlığı veya kısmi uzmanlık kapsamında, uzmanlığı veya kısmi uzmanlığı tek başına ad belirtir. Uygun şablon değişkenleri ile, başka şablon uzmanlıkları veya kısmi uzmanlıkları da belirtilebilir.

## <a name="example-specialization-versus-partial-specialization"></a>Örnek: uzmanlık ve kısmi özelleşme karşılaştırması

Aşağıdaki kod, sınıf şablonun adının (A) uzmanlaşma veya kısmi uzmanlaşma kapsamında farklı yorumlandığını gösterir.

```cpp
// template_name_resolution3.cpp
// compile with: /c
template <class T> class A {
   A* a1;   // A refers to A<T>
   A<int>* a2;  // A<int> refers to a specialization of A.
   A<T*>* a3;   // A<T*> refers to the partial specialization A<T*>.
};

template <class T> class A<T*> {
   A* a4; // A refers to A<T*>.
};

template<> class A<int> {
   A* a5; // A refers to A<int>.
};
```

## <a name="example-name-conflict-between-template-parameter-and-object"></a>Örnek: şablon parametresi ve nesnesi arasında ad çakışması

Bir şablon parametresi ile başka bir nesne arasında ad çakışması söz konusu olduğunda, şablon parametresi gizlenebilir de gizlenemeyebilir de. Aşağıdaki kurallar önceliği belirlemenize yardımcı olur.

Şablon parametresi ilk göründüğü noktadan sınıfın veya işlev şablonunun sonuna kadar kapsamdadır. Ad, şablon bağımsız değişken listesinde veya temel sınıflar listesinde yeniden görünürse, aynı türe başvurur. Standart C++'da, şablon parametresi ile aynı başka hiçbir ad aynı kapsam içinde bildirilemez. Bir Microsoft uzantısı, şablon parametresinin şablonu kapsamında yeniden tanımlanmasını sağlar. Aşağıdaki örnekte, bir sınıf şablonunun temel belirtiminde şablon parametresinin kullanımı gösterilmektedir.

```cpp
// template_name_resolution4.cpp
// compile with: /EHsc
template <class T>
class Base1 {};

template <class T>
class Derived1 : Base1<T> {};

int main() {
   // Derived1<int> d;
}
```

## <a name="example-define-member-function-outside-class-template"></a>Örnek: sınıf şablonunun dışında üye işlevini tanımlayın

Sınıf şablonu dışındaki bir şablona ait üye işlevlerini tanımlarken, farklı bir şablon parametresi adı kullanılabilir. Şablon üye işlev tanımı, şablon parametresi için bildirimden farklı bir ad kullanırsa ve tanımda kullanılan ad bildirimin başka bir üyesiyle çakışırsa, şablon bildirimindeki üye öncelik kazanır.

```cpp
// template_name_resolution5.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

template <class T> class C {
public:
   struct Z {
      Z() { cout << "Z::Z()" << endl; }
   };
   void f();
};

template <class Z>
void C<Z>::f() {
   // Z refers to the struct Z, not to the template arg;
   // Therefore, the constructor for struct Z will be called.
   Z z;
}

int main() {
   C<int> c;
   c.f();
}
```

```Output
Z::Z()
```

## <a name="example-define-template-or-member-function-outside-namespace"></a>Örnek: ad alanı dışında şablon veya üye işlevi tanımlayın

Şablonun bildirildiği ad alanı dışındaki bir şablon işlevi veya üye işlev tanımlanırken, şablon bağımsız değişkeni ad alanının diğer üyelerinin adları üzerinde önceliğe sahiptir.

```cpp
// template_name_resolution6.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

namespace NS {
   void g() { cout << "NS::g" << endl; }

   template <class T> struct C {
      void f();
      void g() { cout << "C<T>::g" << endl; }
   };
};

template <class T>
void NS::C<T>::f() {
   g(); // C<T>::g, not NS::g
};

int main() {
   NS::C<int> c;
   c.f();
}
```

```Output
C<T>::g
```

## <a name="example-base-class-or-member-name-hides-template-argument"></a>Örnek: temel sınıf veya üye adı şablon bağımsız değişkenini gizliyor

Şablon sınıf bildirimi dışındaki tanımlarda, bir şablon sınıfının, şablon bağımsız değişkenine bağımlı olmayan temel bir sınıfı varsa ve temel sınıf ya da üyelerinden biri şablon bağımsız değişkeniyle aynı ada sahipse, temel sınıf veya üye adı, şablon bağımsız değişkenini gizler.

```cpp
// template_name_resolution7.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

struct B {
   int i;
   void print() { cout << "Base" << endl; }
};

template <class T, int i> struct C : public B {
   void f();
};

template <class B, int i>
void C<B, i>::f() {
   B b;   // Base class b, not template argument.
   b.print();
   i = 1; // Set base class's i to 1.
}

int main() {
   C<int, 1> c;
   c.f();
   cout << c.i << endl;
}
```

```Output
Base
1
```

## <a name="see-also"></a>Ayrıca bkz.

[Ad çözümlemesi](../cpp/templates-and-name-resolution.md)
