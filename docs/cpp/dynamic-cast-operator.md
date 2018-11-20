---
title: dynamic_cast İşleci
ms.date: 11/19/2018
f1_keywords:
- dynamic_cast_cpp
helpviewer_keywords:
- dynamic_cast keyword [C++]
ms.assetid: f380ada8-6a18-4547-93c9-63407f19856b
ms.openlocfilehash: 3b359885eb72f9272fb1efe14afe9a6cbe6ddb30
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176971"
---
# <a name="dynamiccast-operator"></a>dynamic_cast İşleci

İşlenen dönüştürür `expression` türünde bir nesne için `type-id`.

## <a name="syntax"></a>Sözdizimi

```
dynamic_cast < type-id > ( expression )
```

## <a name="remarks"></a>Açıklamalar

`type-id` Bir işaretçi veya önceden tanımlanmış sınıf türüne yapılan başvuru ya da "işaretçisi void" olmalıdır. Türünü `expression` bir işaretçi olmalıdır `type-id` bir işaretçi ya da bir l-değeri ise `type-id` bir başvurudur.

Bkz: [static_cast](../cpp/static-cast-operator.md) ve statik ve dinamik atama dönüştürmelerinin arasındaki her kullanmak, uygun olduğunda fark açıklaması için.

Davranış iki önemli değişiklikler vardır **dynamic_cast** yönetilen kodda:

- **dynamic_cast** paketlenmiş bir sabit listesinin temel alınan türü bir işaretçi döndüren işaretçiyi dönüştürülmüş yerine 0 zamanında başarısız olur.

- **dynamic_cast** artık bir özel durum oluşturur, `type-id` çalışma zamanında başarısız atama ile bir değer türü iç işaretçidir.  Cast artık atma yerine 0 İşaretçi değeri döndürür.

Varsa `type-id` bir benzersiz erişilebilir doğrudan veya dolaylı taban sınıfının işaretçisidir `expression`, benzersiz bir alt nesne türünün işaretçisi `type-id` sonucudur. Örneğin:

```cpp
// dynamic_cast_1.cpp
// compile with: /c
class B { };
class C : public B { };
class D : public C { };

void f(D* pd) {
   C* pc = dynamic_cast<C*>(pd);   // ok: C is a direct base class
                                   // pc points to C subobject of pd
   B* pb = dynamic_cast<B*>(pd);   // ok: B is an indirect base class
                                   // pb points to B subobject of pd
}
```

Öğesinden türetilen bir sınıf için türetilmiş bir sınıftan bir işaretçiyi bir sınıf hiyerarşisi yukarı taşır çünkü bu tür bir dönüştürme "yukarı"çevrim çağrılır. Yukarı çevrim örtük bir dönüştürmedir.

Varsa `type-id` olan void * gerçek türünü belirlemek için bir çalışma zamanı denetimi yapılmaz `expression`. İşaret ettiği tam nesne işaretçisi sonucudur `expression`. Örneğin:

```cpp
// dynamic_cast_2.cpp
// compile with: /c /GR
class A {virtual void f();};
class B {virtual void f();};

void f() {
   A* pa = new A;
   B* pb = new B;
   void* pv = dynamic_cast<void*>(pa);
   // pv now points to an object of type A

   pv = dynamic_cast<void*>(pb);
   // pv now points to an object of type B
}
```

Varsa `type-id` void * değil nesneyi işaret ettiği olmadığını görmek için bir çalışma zamanı denetimi yapılmaz `expression` işaret ettiği türüne dönüştürülebilir `type-id`.

Varsa türünü `expression` bir temel sınıf türünün `type-id`, olmadığını görmek için bir çalışma zamanı denetimi yapılmaz `expression` aslında, türünün tam bir nesneyi işaret `type-id`. True ise, tam bir nesne türünün işaretçisi sonucudur `type-id`. Örneğin:

```cpp
// dynamic_cast_3.cpp
// compile with: /c /GR
class B {virtual void f();};
class D : public B {virtual void f();};

void f() {
   B* pb = new D;   // unclear but ok
   B* pb2 = new B;

   D* pd = dynamic_cast<D*>(pb);   // ok: pb actually points to a D
   D* pd2 = dynamic_cast<D*>(pb2);   // pb2 points to a B not a D
}
```

Bu tür bir dönüştürme adlı bir "alt türe çevirme" bir işaretçiyi bir sınıf için belirli bir sınıftaki bir sınıf hiyerarşisi aşağı taşır çünkü bu türden türetilmiş.

Birden çok devralma durumlarda belirsizlik olasılıklarını kullanıma sunulmuştur. Aşağıdaki şekilde gösterilen sınıf hiyerarşisini inceleyin.

CLR türleri için **dynamic_cast** sonuçları bir dönüştürme örtük olarak gerçekleştirilemiyorsa İşlemsiz bir MSIL şirket içinde veya `isinst` dinamik bir denetimi gerçekleştirir ve döndürür, yönerge **nullptr** varsa dönüştürme başarısız olur.

Aşağıdaki örnek kullanımları **dynamic_cast** bir sınıfın belirli bir türün bir örneğini olup olmadığını belirlemek için:

```cpp
// dynamic_cast_clr.cpp
// compile with: /clr
using namespace System;

void PrintObjectType( Object^o ) {
   if( dynamic_cast<String^>(o) )
      Console::WriteLine("Object is a String");
   else if( dynamic_cast<int^>(o) )
      Console::WriteLine("Object is an int");
}

int main() {
   Object^o1 = "hello";
   Object^o2 = 10;

   PrintObjectType(o1);
   PrintObjectType(o2);
}
```

![Sınıf gösteren birden çok devralma hiyerarşisi](../cpp/media/vc39011.gif "sınıfı gösteren birden çok devralma hiyerarşisi") <br/>
Birden çok devralma gösteren sınıf hiyerarşisi

Türü bir nesneye bir işaretçi `D` için güvenli bir şekilde dönüştürülebilen `B` veya `C`. Ancak, varsa `D` işaret edecek şekilde cast bir `A` nesnesi, hangi örneğinin `A` neden olur? Bu, bir belirsiz atama hataya neden olur. Bu sorunla karşılaşmamak için iki anlaşılır yayınları gerçekleştirebilirsiniz. Örneğin:

```cpp
// dynamic_cast_4.cpp
// compile with: /c /GR
class A {virtual void f();};
class B {virtual void f();};
class D : public B {virtual void f();};

void f() {
   D* pd = new D;
   B* pb = dynamic_cast<B*>(pd);   // first cast to B
   A* pa2 = dynamic_cast<A*>(pb);   // ok: unambiguous
}
```

Sanal temel sınıflar kullandığınızda, daha fazla belirsizlikleri tanıtılabilir. Aşağıdaki şekilde gösterilen sınıf hiyerarşisini inceleyin.

![Sınıf sanal temel sınıflar gösteren hiyerarşi](../cpp/media/vc39012.gif "sınıf sanal temel sınıflar gösteren hiyerarşisi") <br/>
Sanal temel sınıflar gösteren sınıf hiyerarşisi

Bu hiyerarşide `A` sanal bir temel sınıf. Sınıfının bir örneğini belirtilen `E` ve işaretçi `A` alt nesneye, bir **dynamic_cast** işaretçisi `B` belirsizlik nedeniyle başarısız olur. İlk olarak geri tam dönüştürmelisiniz `E` nesnesi ve ardından doğru ulaşmak için anlaşılır biçimde, hiyerarşi yedeklemek istediğiniz şekilde iş `B` nesne.

Aşağıdaki şekilde gösterilen sınıf hiyerarşisini inceleyin.

![Yinelenen temel sınıflar gösteren hiyerarşi sınıfı](../cpp/media/vc39013.gif "sınıfı gösteren yinelenen temel sınıf hiyerarşisi") <br/>
Yinelenen temel sınıflar gösteren sınıf hiyerarşisi

Belirtilen türde bir nesne `E` ve işaretçi `D` gitmek alt nesneye `D` en soldaki alt nesneye `A` alt nesneye, üç dönüştürme yapılabilir. Gerçekleştirebileceğiniz bir **dynamic_cast** dönüştürme `D` işaretçi bir `E` işaretçi ve dönüştürme (ya da **dynamic_cast** ya da örtük bir dönüştürme) gelen`E`için `B`ve son olarak örtük bir dönüştürme `B` için `A`. Örneğin:

```cpp
// dynamic_cast_5.cpp
// compile with: /c /GR
class A {virtual void f();};
class B : public A {virtual void f();};
class C : public A { };
class D {virtual void f();};
class E : public B, public C, public D {virtual void f();};

void f(D* pd) {
   E* pe = dynamic_cast<E*>(pd);
   B* pb = pe;   // upcast, implicit conversion
   A* pa = pb;   // upcast, implicit conversion
}
```

**Dynamic_cast** işleci ayrıca bir "çapraz yayın" gerçekleştirmek için kullanılabilir Aynı sınıf hiyerarşisi kullanarak gelen örnek için bir işaretçi dönüştürme yapmak mümkündür `B` için alt nesneye `D` tam nesne türü olduğu sürece, alt nesneye `E`.

Platformlar arası yayınları göz önüne alındığında, bir işaretçiye dönüştürme yapmak gerçekten mümkündür `D` en soldaki işaretçisi `A` yalnızca iki adımda alt nesne. Öğesinden dönüştürme çapraz gerçekleştirebileceğiniz `D` için `B`, ardından örtük bir dönüştürme `B` için `A`. Örneğin:

```cpp
// dynamic_cast_6.cpp
// compile with: /c /GR
class A {virtual void f();};
class B : public A {virtual void f();};
class C : public A { };
class D {virtual void f();};
class E : public B, public C, public D {virtual void f();};

void f(D* pd) {
   B* pb = dynamic_cast<B*>(pd);   // cross cast
   A* pa = pb;   // upcast, implicit conversion
}
```

Bir null işaretçi değeri tarafından hedef türünün boş işaretçi değerini dönüştürülür **dynamic_cast**.

Kullanırken `dynamic_cast < type-id > ( expression )`, `expression` güvenli bir şekilde türüne dönüştürülemez `type-id`, çalışma zamanı denetimi dönüştürme başarısız olmasına neden olur. Örneğin:

```cpp
// dynamic_cast_7.cpp
// compile with: /c /GR
class A {virtual void f();};
class B {virtual void f();};

void f() {
   A* pa = new A;
   B* pb = dynamic_cast<B*>(pa);   // fails at runtime, not safe;
   // B not derived from A
}
```

İşaretçi türüne yapılan başarısız atamanın null işaretçi değeridir. Türü atar başvurmak için başarısız atamanın bir [bad_cast özel durumu](../cpp/bad-cast-exception.md).   Varsa `expression` etmez üzerine gelin veya geçerli bir nesne başvurusu bir `__non_rtti_object` özel durumu oluşturulur.

Bkz: [TypeID](../cpp/typeid-operator.md) açıklaması için `__non_rtti_object` özel durum.

## <a name="example"></a>Örnek

Aşağıdaki örnek, temel sınıf (yapı A), bir nesneye yönelik işaretçi (struct C) oluşturur.  Bu ayrıca olgu var. sanal işlevler, çalışma zamanı çok biçimlilik sağlar.

Örnek, sanal olmayan bir işlev hiyerarşide de çağırır.

```cpp
// dynamic_cast_8.cpp
// compile with: /GR /EHsc
#include <stdio.h>
#include <iostream>

struct A {
    virtual void test() {
        printf_s("in A\n");
   }
};

struct B : A {
    virtual void test() {
        printf_s("in B\n");
    }

    void test2() {
        printf_s("test2 in B\n");
    }
};

struct C : B {
    virtual void test() {
        printf_s("in C\n");
    }

    void test2() {
        printf_s("test2 in C\n");
    }
};

void Globaltest(A& a) {
    try {
        C &c = dynamic_cast<C&>(a);
        printf_s("in GlobalTest\n");
    }
    catch(std::bad_cast) {
        printf_s("Can't cast to C\n");
    }
}

int main() {
    A *pa = new C;
    A *pa2 = new B;

    pa->test();

    B * pb = dynamic_cast<B *>(pa);
    if (pb)
        pb->test2();

    C * pc = dynamic_cast<C *>(pa2);
    if (pc)
        pc->test2();

    C ConStack;
    Globaltest(ConStack);

   // will fail because B knows nothing about C
    B BonStack;
    Globaltest(BonStack);
}
```

```Output
in C
test2 in B
in GlobalTest
Can't cast to C
```

## <a name="see-also"></a>Ayrıca bkz.

[Atama İşleçleri](../cpp/casting-operators.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)