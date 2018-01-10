---
title: "dynamic_cast işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: dynamic_cast_cpp
dev_langs: C++
helpviewer_keywords: dynamic_cast keyword [C++]
ms.assetid: f380ada8-6a18-4547-93c9-63407f19856b
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 29add795c7adeca67fc85c7cf3b1b90d17f804fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dynamiccast-operator"></a>dynamic_cast İşleci
İşlenen dönüştürür `expression` türünde bir nesneye `type-id`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dynamic_cast < type-id > ( expression )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `type-id` Bir işaretçi veya önceden tanımlanmış sınıf türü için bir başvuru ya da "için bir işaretçi void" olması gerekir. Türü `expression` bir işaretçi olmalıdır `type-id` bir işaretçi ya da bir l-değeri ise `type-id` başvurudur.  
  
 Bkz: [static_cast](../cpp/static-cast-operator.md) statik ve dinamik atama dönüşümleri arasında ve her kullanmak, uygun olduğunda fark açıklaması için.  
  
 İçinde davranışını iki önemli değişiklikler olduğu `dynamic_cast` yönetilen kod:  
  
-   `dynamic_cast`paketlenmiş bir enum temel alınan türü için bir işaretçi dönüştürülen işaretçi yerine 0 döndürme zamanında başarısız olur.  
  
-   `dynamic_cast`artık bir özel durum oluşturur, `type-id` bir değer türüyle çalışma zamanında başarısız cast iç bir işaretçidir.  Cast şimdi atma yerine 0 İşaretçi değeri döndürür.  
  
 Varsa `type-id` gösteren bir işaretçidir bir anlaşılır erişilebilir doğrudan veya dolaylı olarak temel sınıfını `expression`, benzersiz alt nesne türü için bir işaretçi `type-id` sonucudur. Örneğin:  
  
```  
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
  
 Öğesinden türetilmiş bir sınıf için türetilen bir sınıftan bir işaretçi bir sınıf hiyerarşisi taşıdığı için bu tür dönüştürme "yukarı çevrim" adı verilir. Bir yukarı çevrim örtük bir dönüştürme ' dir.  
  
 Varsa `type-id` void * olan bir çalışma zamanı denetimi gerçek türünü belirleme yapılan `expression`. Sonucu gösteren bir işaretçidir gösterdiği tam nesne `expression`. Örneğin:  
  
```  
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
  
 Varsa `type-id` void * değil nesne gösterdiği olmadığını görmek için bir çalışma zamanı denetimi yapılan `expression` gösterdiği türüne dönüştürülebilir `type-id`.  
  
 Varsa türünü `expression` türüne ilişkin bir taban sınıf `type-id`, bir çalışma zamanı denetimi olmadığını görmek için yapılan `expression` gerçekte, türünün tam bir nesneye işaret `type-id`. True ise, tam bir nesne türüne ilişkin bir işaretçi sonucudur `type-id`. Örneğin:  
  
```  
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
  
 Bu tür dönüştürme adlı bir "alta" bir işaretçi bir sınıf için belirli bir sınıfın bir sınıf hiyerarşisinden aşağı taşıdığı için ondan türetilmiş.  
  
 Birden çok devralma durumlarda belirsizlik olasılıklarını sunulur. Aşağıdaki çizimde gösterilen sınıf hiyerarşisi göz önünde bulundurun.  
  
 CLR türleri için `dynamic_cast` sonuçları bir no-dönüştürme örtük olarak gerçekleştirilebiliyorsa op ya da bir MSIL içinde `isinst` dinamik denetimi gerçekleştirir ve döndüren yönerge `nullptr` dönüştürme başarısız olursa.  
  
 Aşağıdaki örnek kullanır `dynamic_cast` bir sınıf belirli türünün bir örneği olup olmadığını belirlemek için:  
  
```  
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
  
 ![Sınıf gösteren birden çok devralma hiyerarşisi](../cpp/media/vc39011.gif "vc39011")  
Birden çok devralma gösteren sınıf hiyerarşisi  
  
 Bir nesne türü için bir işaretçi `D` güvenle atanabilecek `B` veya `C`. Ancak, varsa `D` işaret edecek şekilde cast bir `A` nesnesi, hangi örneğinin `A` neden olur? Bu belirsiz atama hataya neden olur. Bu sorunla karşılaşmamak için iki anlaşılır atamaları gerçekleştirebilirsiniz. Örneğin:  
  
```  
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
  
 Sanal Taban sınıflar kullandığınızda başka belirsizlikleri tanıtılabilir. Aşağıdaki çizimde gösterilen sınıf hiyerarşisi göz önünde bulundurun.  
  
 ![Sanal Taban sınıflar gösterir hiyerarşi sınıf](../cpp/media/vc39012.gif "vc39012")  
Sanal Taban sınıflar gösteren sınıf hiyerarşisi  
  
 Bu hiyerarşide `A` sanal bir temel sınıftır. Sınıfının bir örneği verilen `E` gösteren bir işaretçi `A` alt nesne, bir `dynamic_cast` gösteren bir işaretçi için `B` belirsizlik nedeniyle başarısız olur. İlk olarak geri tam atamalısınız `E` nesne sonra yolunuzu hiyerarşi yedekleme doğru ulaşmak için anlaşılır biçimde, iş `B` nesnesi.  
  
 Aşağıdaki çizimde gösterilen sınıf hiyerarşisi göz önünde bulundurun.  
  
 ![Sınıf yinelenen temel sınıfları göstermektedir hiyerarşi](../cpp/media/vc39013.gif "vc39013")  
Yinelenen temel sınıfları gösteren sınıf hiyerarşisi  
  
 Türünde bir nesne verilen `E` gösteren bir işaretçi `D` gelen gitmek için alt nesne, `D` sol en alt nesne `A` alt nesne, üç dönüştürme yapılabilir. Gerçekleştirebileceğiniz bir `dynamic_cast` dönüştürme `D` işaretçi bir `E` işaretçi sonra dönüştürme (ya da `dynamic_cast` ya da örtük bir dönüştürme) gelen `E` için `B`ve son olarak örtük bir dönüştürme `B` için `A`. Örneğin:  
  
```  
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
  
 `dynamic_cast` İşleci de kullanılabilir bir "çapraz cast." gerçekleştirmek için Aynı sınıf hiyerarşisi kullanarak, gelen örnek için bir işaretçi yayınlanamıyor mümkündür `B` için alt nesne `D` tam nesne türü olduğu sürece, alt nesne `E`.  
  
 Atamaları düşünüldüğünde, bir işaretçi bir dönüştürme yapmak gerçekten mümkündür `D` en solundaki gösteren bir işaretçi için `A` yalnızca iki adımda alt nesne. Gelen cast arası gerçekleştirebilirsiniz `D` için `B`, ardından örtük bir dönüştürme `B` için `A`. Örneğin:  
  
```  
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
  
 Hedef türü tarafından null işaretçinin değeri boş işaretçi değeri dönüştürülür `dynamic_cast`.  
  
 Kullandığınızda `dynamic_cast < type-id > ( expression )`, `expression` güvenle türüne dönüştürülemez `type-id`, çalışma zamanı onay dönüştürme başarısız olmasına neden olur. Örneğin:  
  
```  
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
  
 Başarısız bir işaretçi türüne dönüştürme null işaretçinin değeri. Türü atar başvurmak için başarısız bir cast bir [bad_cast özel durumu](../cpp/bad-cast-exception.md).   Varsa `expression` işaret ya da geçerli bir nesne başvurusu bir `__non_rtti_object` özel durumu oluşur.  
  
 Bkz: [TypeID](../cpp/typeid-operator.md) bir açıklaması için `__non_rtti_object` özel durum.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek taban sınıf (yapı A) işaretçisine bir nesne (yapı C) oluşturur.  Bu artı olgu var. sanal işlevler, çalışma zamanı çok biçimlilik sağlar.  
  
 Örnek sanal olmayan bir işlev hiyerarşi içinde de çağırır.  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama İşleçleri](../cpp/casting-operators.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)