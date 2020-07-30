---
title: dynamic_cast İşleci
description: C++ dili dynamic_cast işlecine genel bakış.
ms.date: 02/03/2020
f1_keywords:
- dynamic_cast_cpp
helpviewer_keywords:
- dynamic_cast keyword [C++]
ms.assetid: f380ada8-6a18-4547-93c9-63407f19856b
ms.openlocfilehash: 15609aeaef815ff89ca196876e1143090c65221b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221646"
---
# <a name="dynamic_cast-operator"></a>dynamic_cast İşleci

İşleneni `expression` türü bir nesneye dönüştürür `type-id` .

## <a name="syntax"></a>Syntax

```
dynamic_cast < type-id > ( expression )
```

## <a name="remarks"></a>Açıklamalar

`type-id`Bir işaretçi veya önceden tanımlanmış bir sınıf türüne başvuru ya da "void işaretçisine" olması gerekir. Türü bir işaretçisiyse `expression` `type-id` veya bir başvuru ise l değeri bir işaretçi olmalıdır `type-id` .

Statik ve dinamik atama dönüştürmeleri arasındaki farkın bir açıklaması için ve her birini kullanmak için uygun olduğunda bkz. [static_cast](../cpp/static-cast-operator.md) .

Yönetilen kodda davranışında iki Son değişiklik vardır **`dynamic_cast`** :

- **`dynamic_cast`** paketlenmiş bir numaralandırma için temeldeki türdeki bir işaretçiye, dönüştürülmüş işaretçi yerine 0 döndürüldüğünden çalışma zamanında başarısız olur.

- **`dynamic_cast`**`type-id`, bir değer türünün iç işaretçisi olduğunda bir özel durum oluşturmaz, bu atama çalışma zamanında başarısız olur.  Cast şimdi, oluşturmak yerine 0 işaretçi değerini döndürür.

`type-id`, Belirsiz erişilebilir doğrudan veya dolaylı taban sınıfına yönelik bir işaretçisiyse `expression` , türü benzersiz alt nesnesi işaretçisi oluşur `type-id` . Örneğin:

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

`type-id`Void * ise, gerçek türünü belirlemekte bir çalışma zamanı denetimi yapılır `expression` . Sonuç, tarafından işaret edilen tüm nesnenin bir işaretçisidir `expression` . Örneğin:

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

`type-id`Void * değilse, tarafından işaret edilen nesnenin tarafından `expression` işaret edilen türe dönüştürülüp dönüştürülebileceğini görmek için bir çalışma zamanı denetimi yapılır `type-id` .

Türünün türü `expression` bir temel sınıf ise `type-id` , `expression` gerçekten türünün tam bir nesnesine işaret edip ettiğini görmek için bir çalışma zamanı denetimi yapılır `type-id` . Bu true ise sonuç, türünün bir bütün nesnesinin bir işaretçisidir `type-id` . Örneğin:

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

CLR türleri için, **`dynamic_cast`** dönüştürme örtük olarak gerçekleştirilebileceği veya `isinst` dinamik bir denetim gerçekleştiren ve dönüştürme başarısız olursa döndüren bir MSIL yönergesi ile hiçbir işlem yapılmaz **`nullptr`** .

Aşağıdaki örnek, **`dynamic_cast`** bir sınıfın belirli türde bir örnek olup olmadığını belirlemede kullanır:

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

Türünde bir nesne için bir işaretçi `D` , güvenle veya ' A dönüşebilir `B` `C` . Ancak, `D` bir nesnesine işaret etmek için ayarlanırsa `A` , hangi örneği oluşur `A` ? Bu, belirsiz bir atama hatasına neden olur. Bu sorunu çözmek için iki benzersiz yayını gerçekleştirebilirsiniz. Örneğin:

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

Bu hiyerarşide `A` bir sanal temel sınıftır. Bir sınıf örneği ve alt nesnesine `E` bir işaretçi verildiğinde `A` , **`dynamic_cast`** belirsizlik nedeniyle bir işaretçisine bir işaretçi `B` başarısız olur. Önce, `E` doğru nesneye ulaşmak için, önce tüm nesneye geri dönüştürmelisiniz, sonra hiyerarşiyi geçici olarak bir şekilde yedeklemeniz gerekir `B` .

Aşağıdaki şekilde gösterilen sınıf hiyerarşisini göz önünde bulundurun.

![Yinelenen temel sınıfları gösteren sınıf hiyerarşisi](../cpp/media/vc39013.gif "Yinelenen temel sınıfları gösteren sınıf hiyerarşisi") <br/>
Yinelenen temel sınıfları gösteren sınıf hiyerarşisi

Türünde bir nesne ve alt nesnesine bir `E` işaretçi verildiğinde `D` , alt nesnesinden en sol alt nesne arasında gezinmek için `D` `A` üç dönüştürme yapılabilir. **`dynamic_cast`** İşaretçisinden bir işaretçiye dönüştürme işlemi gerçekleştirebilir `D` `E` , sonra bir dönüştürme ( **`dynamic_cast`** ya da örtük dönüştürme) `E` `B` , ve son olarak öğesinden öğesine örtülü bir dönüşüm yapabilirsiniz `B` `A` . Örneğin:

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

**`dynamic_cast`** İşleci, "çapraz dönüştürme" işlemi gerçekleştirmek için de kullanılabilir. Aynı sınıf hiyerarşisini kullanarak, örneğin, `B` `D` tam nesne türünde olduğu sürece, bir işaretçiyi alt nesneden alt nesne olarak dönüştürmek mümkündür `E` .

Çapraz yayınları göz önünde bulundurarak, bir işaretçiden `D` yalnızca iki adımda sol alt nesne işaretçisine dönüştürme yapmak gerçekten mümkündür `A` . ' Dan ' a bir çapraz atama `D` gerçekleştirebilir `B` ve öğesinden öğesine örtük bir dönüştürme `B` yapabilirsiniz `A` . Örneğin:

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

Null işaretçi değeri, hedef türün null işaretçi değerine dönüştürülür **`dynamic_cast`** .

`dynamic_cast < type-id > ( expression )`' I kullandığınızda, `expression` güvenli bir şekilde türüne dönüştürülemiyorsa `type-id` , çalışma zamanı denetimi dönüştürmenin başarısız olmasına neden olur. Örneğin:

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

Başarısız bir işaretçi türüne dönüştürme değeri null işaretçisidir. Başvuru türüne yapılan başarısız atama [bad_cast bir özel durum](../cpp/bad-cast-exception.md)oluşturur.   `expression`Geçerli bir nesneye işaret veya başvuru yapmaz, bir `__non_rtti_object` özel durum oluşturulur.

Özel [typeid](../cpp/typeid-operator.md) durumun açıklaması için bkz. TypeId `__non_rtti_object` .

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

[Atama Işleçleri](../cpp/casting-operators.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
