---
title: dynamic_cast İşleci
description: C++ Dil dynamic_cast işlecine genel bakış.
ms.date: 02/03/2020
f1_keywords:
- dynamic_cast_cpp
helpviewer_keywords:
- dynamic_cast keyword [C++]
ms.assetid: f380ada8-6a18-4547-93c9-63407f19856b
ms.openlocfilehash: d12b338b4b52d81b01097a1e1f5c83ec10eac774
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189500"
---
# <a name="dynamic_cast-operator"></a>dynamic_cast İşleci

İşleneni `expression` `type-id`türündeki bir nesneye dönüştürür.

## <a name="syntax"></a>Sözdizimi

```
dynamic_cast < type-id > ( expression )
```

## <a name="remarks"></a>Açıklamalar

`type-id`, bir işaretçi veya önceden tanımlanmış bir sınıf türüne veya "void işaretçisine" bir başvuru olmalıdır. `expression` türü, `type-id` bir işaretçisiyse veya `type-id` bir başvuru ise bir l değeri olduğunda bir işaretçi olmalıdır.

Statik ve dinamik atama dönüştürmeleri arasındaki farkın bir açıklaması için ve her birini kullanmak için uygun olduğunda bkz. [static_cast](../cpp/static-cast-operator.md) .

Yönetilen koddaki **dynamic_cast** davranışında iki Son değişiklik vardır:

- paketlenmiş bir numaralandırma için temeldeki türdeki bir işaretçiye **dynamic_cast** , dönüştürülmüş işaretçi yerine 0 döndüren çalışma zamanında başarısız olur.

- **dynamic_cast** , bir değer türüne yönelik iç işaretçisiyse çalışma zamanında başarısız olacak şekilde `type-id` bir özel durum oluşturmaz.  Cast şimdi, oluşturmak yerine 0 işaretçi değerini döndürür.

`type-id`, belirsiz şekilde erişilebilen doğrudan veya dolaylı temel sınıf `expression`işaretçisiyse, `type-id` türünde benzersiz alt nesnenin bir işaretçisi oluşur. Örneğin:

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

Bir işaretçiyi türetilmiş bir sınıftan türetilmiş bir sınıfa bir sınıf hiyerarşisi yukarı taşıdığından, bu tür dönüştürme "upcast" olarak adlandırılır. Bir upcast örtük bir dönüştürmedir.

`type-id` void ise, `expression`gerçek türünü belirlemekte bir çalışma zamanı denetimi yapılır. Sonuç, `expression`tarafından işaret edilen tüm nesne işaretçisidir. Örneğin:

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

`type-id` void * değilse, `expression` tarafından işaret edilen nesnenin `type-id`tarafından işaret edilen türe dönüştürülebileceğini görmek için bir çalışma zamanı denetimi yapılır.

`expression` türü `type-id`türünün temel sınıfını ise, `expression` gerçekten `type-id`türünün tam bir nesnesine işaret ettiğini görmek için bir çalışma zamanı denetimi yapılır. Bu true ise sonuç, `type-id`türünün bir bütün nesnesinin bir işaretçisidir. Örneğin:

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

Bu tür dönüştürmeye "alta dönüştürme" denir çünkü bir işaretçiyi bir sınıf hiyerarşisine, belirli bir sınıftan türetilmiş bir sınıfa ait bir sınıfa kaydırır.

Birden çok devralma durumunda belirsizlik için olanaklar ortaya çıkartılır. Aşağıdaki şekilde gösterilen sınıf hiyerarşisini göz önünde bulundurun.

CLR türleri için, dönüştürme örtük olarak gerçekleştirilebileceği veya bir MSIL `isinst` yönergesinin, dinamik bir denetim gerçekleştiren ve dönüştürme başarısız olursa **nullptr** döndüren **dynamic_cast** bir işlem olmadan sonuçlanır.

Aşağıdaki örnek, bir sınıfın belirli türde bir örnek olup olmadığını anlamak için **dynamic_cast** kullanır:

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

![Birden çok devralmayı gösteren sınıf hiyerarşisi](../cpp/media/vc39011.gif "Birden çok devralmayı gösteren sınıf hiyerarşisi") <br/>
Birden çok devralmayı gösteren sınıf hiyerarşisi

`D` türünde bir nesne işaretçisi, `B` veya `C`güvenli bir şekilde dönüşebilir. Ancak `D`, bir `A` nesnesine işaret etmek için ayarlanırsa, bu `A` örneği neden olur? Bu, belirsiz bir atama hatasına neden olur. Bu sorunu çözmek için iki benzersiz yayını gerçekleştirebilirsiniz. Örneğin:

```cpp
// dynamic_cast_4.cpp
// compile with: /c /GR
class A {virtual void f();};
class B : public A {virtual void f();};
class C : public A {virtual void f();};
class D : public B, public C {virtual void f();};

void f() {
   D* pd = new D;
   A* pa = dynamic_cast<A*>(pd);   // C4540, ambiguous cast fails at runtime
   B* pb = dynamic_cast<B*>(pd);   // first cast to B
   A* pa2 = dynamic_cast<A*>(pb);   // ok: unambiguous
}
```

Sanal temel sınıflar kullandığınızda daha fazla belirsizlikleri eklenebilir. Aşağıdaki şekilde gösterilen sınıf hiyerarşisini göz önünde bulundurun.

![Sanal temel sınıfları gösteren sınıf hiyerarşisi](../cpp/media/vc39012.gif "Sanal temel sınıfları gösteren sınıf hiyerarşisi") <br/>
Sanal temel sınıfları gösteren sınıf hiyerarşisi

Bu hiyerarşide, `A` bir sanal taban sınıftır. Sınıf `E` örneği ve `A` alt nesnesi işaretçisi verildiğinde, belirsizlik nedeniyle `B` işaretçisine bir **dynamic_cast** başarısız olur. Önce tüm `E` nesnesine dönüştürmeniz gerekir, sonra doğru `B` nesnesine ulaşmak için, hiyerarşiyi tamamen bir şekilde yedeklemeniz gerekir.

Aşağıdaki şekilde gösterilen sınıf hiyerarşisini göz önünde bulundurun.

![Yinelenen temel sınıfları gösteren sınıf hiyerarşisi](../cpp/media/vc39013.gif "Yinelenen temel sınıfları gösteren sınıf hiyerarşisi") <br/>
Yinelenen temel sınıfları gösteren sınıf hiyerarşisi

`E` türünde bir nesne ve `D` alt nesnesine bir işaretçi verildiğinde, `D` alt nesnesinden en sol `A` alt nesne arasında gezinmek için üç dönüştürme yapılabilir. `D` işaretçisinden bir `E` işaretçisine **dynamic_cast** dönüştürmeyi, `E` 'den `B`'ye dönüştürme ( **dynamic_cast** veya örtük dönüştürme) ve son olarak `B` 'den `A`'e örtük bir dönüştürme yapabilirsiniz. Örneğin:

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

**Dynamic_cast** işleci, "çapraz dönüştürme" işlemi gerçekleştirmek için de kullanılabilir. Aynı sınıf hiyerarşisini kullanarak, örneğin, tam nesne `E`türünde olduğu sürece, örneğin, `B` alt nesnesinden `D` alt nesnesine bir işaretçi dönüştürmek mümkündür.

Çapraz yayınları göz önünde bulundurarak, yalnızca iki adımda, en çok `A` alt nesnesine bir işaretçiye `D` işaretçiden dönüştürme yapmak gerçekten mümkündür. `D` bir çapraz dönüştürme işlemini `B`, sonra da `B` 'den `A`'e örtülü bir dönüştürme yapabilirsiniz. Örneğin:

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

Null işaretçi değeri, **dynamic_cast**tarafından hedef türün null işaretçi değerine dönüştürülür.

`dynamic_cast < type-id > ( expression )`kullandığınızda, `expression` güvenli bir şekilde `type-id`türüne dönüştürülemiyorsa, çalışma zamanı denetimi dönüştürmenin başarısız olmasına neden olur. Örneğin:

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

Başarısız bir işaretçi türüne dönüştürme değeri null işaretçisidir. Başvuru türüne yapılan başarısız atama [bad_cast bir özel durum](../cpp/bad-cast-exception.md)oluşturur.   `expression` geçerli bir nesneye işaret veya başvuru yapmaz, bir `__non_rtti_object` özel durumu oluşturulur.

`__non_rtti_object` özel durumunun açıklaması için bkz. [TypeId](../cpp/typeid-operator.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek, temel sınıf (struct A) işaretçisini bir nesnesine (struct C) oluşturur.  Bunun yanı sıra sanal işlevlerin olması, çalışma zamanının çok biçimlilik kullanmasına izin verebilir.

Örnek ayrıca hiyerarşide sanal olmayan bir işlev çağırır.

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
