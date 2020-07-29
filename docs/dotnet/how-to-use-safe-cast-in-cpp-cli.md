---
title: 'Nasıl yapılır: C++/CLI üzerinde safe_cast kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- safe_cast keyword [C++], upcasting
ms.assetid: 0fbc87d8-ecdf-4cd5-81f4-0d8cc18e2aff
ms.openlocfilehash: 56ac19871bcdc5162b959f6d60103387551ac2a8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225663"
---
# <a name="how-to-use-safe_cast-in-ccli"></a>Nasıl yapılır: C++/CLI üzerinde safe_cast kullanma

Bu makalede, C++/CLı uygulamalarında safe_cast nasıl kullanılacağı gösterilmektedir. C++/CX içindeki safe_cast hakkında bilgi için bkz. [safe_cast](../extensions/safe-cast-cpp-component-extensions.md).

## <a name="upcasting"></a>Yukarı atama

Bir upcast, türetilmiş bir türden temel sınıflarından birine bir tür dönüştürme işlemi olur. Bu atama güvenlidir ve açık bir atama gösterimi gerektirmez. Aşağıdaki örnek, ve olmadan bir upcast 'ın nasıl gerçekleştirileceğini gösterir `safe_cast` .

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

## <a name="downcasting"></a>Alta çevrim

Bir alta dönüştürme, temel sınıftan türetilmiş bir sınıfa bir taban sınıftan bir tür dönüştürme işlemi olur.  Yalnızca çalışma zamanında adreslenen nesne bir türetilmiş sınıf nesnesini ele alıyorsa, alta dönüştürme güvenlidir.  Aksine **`static_cast`** , `safe_cast` dinamik bir denetim gerçekleştirir ve <xref:System.InvalidCastException> dönüştürme başarısız olursa oluşturur.

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

## <a name="safe_cast-with-user-defined-conversions"></a>Kullanıcı tanımlı dönüşümlerle safe_cast

Sonraki örnek, `safe_cast` Kullanıcı tanımlı dönüştürmeleri çağırmak için nasıl kullanabileceğinizi gösterir.

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

## <a name="safe_cast-and-boxing-operations"></a>safe_cast ve paketleme işlemleri

### <a name="boxing"></a>Kutulama

Paketleme, derleyici eklenmiş, Kullanıcı tanımlı bir dönüştürme olarak tanımlanır.  Bu nedenle, `safe_cast` CLR yığınında bir değer kutusunu kullanabilirsiniz.

Aşağıdaki örnek, basit ve Kullanıcı tanımlı değer türleriyle kutulamayı gösterir.  Bir `safe_cast` kutu, atık toplanan yığında bir değişkene atanabilmesi için yerel yığında bulunan bir değer türü değişkenidir.

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

Sonraki örnek, kutulamayı bir işlemdeki Kullanıcı tanımlı dönüştürmeye göre öncelikte gösterir `safe_cast` .

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

### <a name="unboxing"></a>Çıkarma

Kutudan çıkarma, derleyici eklenmiş, Kullanıcı tanımlı bir dönüştürme olarak tanımlanır.  Bu nedenle, `safe_cast` CLR yığınında bir değeri kaldırmak için öğesini kullanabilirsiniz.

Kutudan çıkarma Kullanıcı tanımlı bir dönüştürmedir, ancak kutulamayı açık olmalıdır — yani, bir **`static_cast`** , C stili tür dönüştürme tarafından gerçekleştirilmesi gerekir, ya da `safe_cast` kutudan çıkarma örtük olarak gerçekleştirilemez.

```cpp
// safe_cast_unboxing.cpp
// compile with: /clr
int main() {
   System::Object ^ o = 42;
   int x = safe_cast<int>(o);
}
```

Aşağıdaki örnek, değer türleri ve ilkel türler ile kutudan çıkarma gösterir.

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

## <a name="safe_cast-and-generic-types"></a>safe_cast ve genel türler

Sonraki örnek, `safe_cast` genel bir tür ile alta dönüştürme gerçekleştirmek için nasıl kullanabileceğinizi gösterir.

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

[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)
