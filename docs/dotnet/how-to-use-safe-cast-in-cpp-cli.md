---
title: 'Nasıl yapılır: Üzerinde safe_cast kullanma C + +/ CLI'
ms.date: 11/04/2016
helpviewer_keywords:
- safe_cast keyword [C++], upcasting
ms.assetid: 0fbc87d8-ecdf-4cd5-81f4-0d8cc18e2aff
ms.openlocfilehash: 1fd1b2d698af44ab841aeb6e205b750beb30ae0d
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57739352"
---
# <a name="how-to-use-safecast-in-ccli"></a>Nasıl yapılır: Üzerinde safe_cast kullanma C + +/ CLI

Bu makale safe_cast kullanma C + +/ CLI uygulamalarında. Bilgileri safe_cast C + +/ CX, bakın [safe_cast](../windows/safe-cast-cpp-component-extensions.md).

## <a name="upcasting"></a>Yukarı çevrim

Yukarı çevrim türetilmiş bir tür değerinden bool değerine atama için temel sınıflarının biri olur. Bu tür dönüştürme güvenlidir ve açık tür dönüştürme gösterimi gerektirmez. Aşağıdaki örnek, bir yukarı çevrim ile yapma işlemi açıklanır `safe_cast` ve olmadan.

```cpp
// safe_upcast.cpp
// compile with: /clr
using namespace System;
interface class A {
   void Test();
};

ref struct B : public A {
   virtual void Test() {
      Console::WriteLine("in B::Test");
   }

   void Test2() {
      Console::WriteLine("in B::Test2");
   }
};

ref struct C : public B {
   virtual void Test() override {
      Console::WriteLine("in C::Test");
   };
};

int main() {
   C ^ c = gcnew C;

   // implicit upcast
   B ^ b = c;
   b->Test();
   b->Test2();

   // upcast with safe_cast
   b = nullptr;
   b = safe_cast<B^>(c);
   b->Test();
   b->Test2();
}
```

```Output
in C::Test
in B::Test2
in C::Test
in B::Test2
```

## <a name="downcasting"></a>Alta dönüştürme işlemi

Alta bir temel sınıftan türetilmiş bir sınıf bir temel sınıftan bir atamanın olur.  Bir alta dönüştürme işlemi yalnızca çalışma zamanında ele nesne aslında bir türetilmiş sınıf nesnesinde ele alıyor mu, güvenli değildir.  Farklı `static_cast`, `safe_cast` dinamik denetimi gerçekleştirir ve oluşturur <xref:System.InvalidCastException> dönüştürme başarısız olursa.

```cpp
// safe_downcast.cpp
// compile with: /clr
using namespace System;

interface class A { void Test(); };

ref struct B : public A {
   virtual void Test() {
      Console::WriteLine("in B::Test()");
   }

   void Test2() {
      Console::WriteLine("in B::Test2()");
   }
};

ref struct C : public B {
   virtual void Test() override {
      Console::WriteLine("in C::Test()");
   }
};

interface class I {};

value struct V : public I {};

int main() {
   A^ a = gcnew C();
   a->Test();
   B^ b = safe_cast<B^>(a);
   b->Test();
   b->Test2();

   V v;
   I^ i = v;   // i boxes V
   V^ refv = safe_cast<V^>(i);

   Object^ o = gcnew B;
   A^ a2= safe_cast<A^>(o);
}
```

```Output
in C::Test()
in C::Test()
in B::Test2()
```

## <a name="safecast-with-user-defined-conversions"></a>safe_cast ile kullanıcı tanımlı dönüşümler

Sonraki örnek nasıl kullanılacağını göstermektedir `safe_cast` kullanıcı tanımlı dönüşümler çağırmak için.

```cpp
// safe_cast_udc.cpp
// compile with: /clr
using namespace System;
value struct V;

ref struct R {
   int x;
   R() {
      x = 1;
   }

   R(int argx) {
      x = argx;
   }

   static operator R::V^(R^ r);
};

value struct V {
   int x;
   static operator R^(V& v) {
      Console::WriteLine("in operator R^(V& v)");
      R^ r = gcnew R();
      r->x = v.x;
      return r;
   }

   V(int argx) {
      x = argx;
   }
};

   R::operator V^(R^ r) {
      Console::WriteLine("in operator V^(R^ r)");
      return gcnew V(r->x);
   }

int main() {
   bool fReturnVal = false;
   V v(2);
   R^ r = safe_cast<R^>(v);   // should invoke UDC
   V^ v2 = safe_cast<V^>(r);   // should invoke UDC
}
```

```Output
in operator R^(V& v
in operator V^(R^ r)
```

## <a name="safecast-and-boxing-operations"></a>safe_cast ve kutulamayı işlemleri

### <a name="boxing"></a>Kutulama

Kutulama, derleyici tarafından eklenen, kullanıcı tanımlı dönüştürme olarak tanımlanır.  Bu nedenle, kullanabileceğiniz `safe_cast` box'ta CLR yığındaki bir değer.

Aşağıdaki örnek, basit ve kullanıcı tanımlı değer türleri ile kutulama gösterir.  A `safe_cast` yerel yığında olan ve böylece atık olarak toplanmış yığındaki bir değişkene atanabilir bir değer türü değişkeni kutular.

```cpp
// safe_cast_boxing.cpp
// compile with: /clr
using namespace System;

interface struct I {};

value struct V : public I {
   int m_x;

   V(int i) : m_x(i) {}
};

int main() {
   // box a value type
   V v(100);
   I^ i = safe_cast<I^>(v);

   int x = 100;
   V^ refv = safe_cast<V^>(v);
   int^ refi = safe_cast<int^>(x);
}
```

Sonraki örnek kutulama, bir kullanıcı tanımlı dönüştürme üzerinden öncelikli olduğunu gösterir bir `safe_cast` işlemi.

```cpp
// safe_cast_boxing_2.cpp
// compile with: /clr
static bool fRetval = true;

interface struct I {};
value struct V : public I {
   int x;

   V(int argx) {
      x = argx;
   }

   static operator I^(V v) {
      fRetval = false;
      I^ pi = v;
      return pi;
   }
};

ref struct R {
   R() {}
   R(V^ pv) {}
};

int main() {
   V v(10);
   I^ pv = safe_cast<I^>(v);   // boxing will occur, not UDC "operator I^"
}
```

### <a name="unboxing"></a>Kutudan çıkarma

Kutudan çıkarma derleyici tarafından eklenen, kullanıcı tanımlı dönüştürme olarak tanımlanır.  Bu nedenle, kullanabileceğiniz `safe_cast` CLR yığındaki bir değerin için.

Kutudan çıkarma, bir kullanıcı tanımlı dönüştürme olduğu halde kutulama aksine, kutudan çıkarma gerekir açık olması — diğer bir deyişle, tarafından gerçekleştirilmesi gereken bir `static_cast`, C stili tür dönüştürme; veya `safe_cast`; kutudan çıkarma gerçekleştirilemez örtük olarak.

```cpp
// safe_cast_unboxing.cpp
// compile with: /clr
int main() {
   System::Object ^ o = 42;
   int x = safe_cast<int>(o);
}
```

Aşağıdaki örnek ile değer türleri ve basit türler kutudan çıkarma gösterilmektedir.

```cpp
// safe_cast_unboxing_2.cpp
// compile with: /clr
using namespace System;

interface struct I {};

value struct VI : public I {};

void test1() {
   Object^ o = 5;
   int x = safe_cast<Int32>(o);
}

value struct V {
   int x;
   String^ s;
};

void test2() {
   V localv;
   Object^ o = localv;
   V unboxv = safe_cast<V>(o);
}

void test3() {
   V localv;
   V^ o2 = localv;
   V unboxv2 = safe_cast<V>(o2);
}

void test4() {
   I^ refi = VI();
   VI vi  = safe_cast<VI>(refi);
}

int main() {
   test1();
   test2();
   test3();
   test4();
}
```

## <a name="safecast-and-generic-types"></a>safe_cast ve genel türler

Sonraki örnek nasıl kullanılacağını göstermektedir `safe_cast` ile bir genel tür alta dönüştürme gerçekleştirmek için.

```cpp
// safe_cast_generic_types.cpp
// compile with: /clr
interface struct I {};

generic<class T> where T:I
ref struct Base {
   T t;
   void test1() {}
};

generic<class T> where T:I
ref struct Derived:public Base <T> {};

ref struct R:public I {};

typedef Base<R^> GBase_R;
typedef Derived<R^> GDerived_R;

int main() {
   GBase_R^ br = gcnew GDerived_R();
   GDerived_R^ dr = safe_cast<GDerived_R^>(br);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[safe_cast](../windows/safe-cast-cpp-component-extensions.md)
