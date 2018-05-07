---
title: 'Nasıl yapılır: safe_cast kullanma C + +/ CLI | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- safe_cast keyword [C++], upcasting
ms.assetid: 0fbc87d8-ecdf-4cd5-81f4-0d8cc18e2aff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0f695c45d5202f376a4ce4daf14c37a7fd9a1904
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-safecast-in-ccli"></a>Nasıl yapılır: C++/CLI üzerinde safe_cast kullanma
Bu makalede safe_cast C + kullanmayı gösterir +/ CLI uygulamalar. Safe_cast içinde hakkında bilgi için [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)], bkz: [safe_cast](../windows/safe-cast-cpp-component-extensions.md).  
  
## <a name="upcasting"></a>Üst türe çevirme  
 Bir türetilmiş bir tür dönüştürme temel sınıflarından biri için bir yukarı çevrim olur. Bu atama güvenlidir ve açık atama gösterimi gerektirmez. Aşağıdaki örnek, bir yukarı çevrim ile gerçekleştirmek gösterilmiştir `safe_cast` ve olmadan.  
  
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
  
## <a name="downcasting"></a>Alt türe çevirme  
 Bir alta temel sınıfından türetilmiş bir sınıf için bir taban sınıftan bir cast ' dir.  Bir alta çalışma zamanında ele nesne türetilmiş sınıf nesnesi gerçekte yalnızca adresleme, güvenli değildir.  Farklı `static_cast`, `safe_cast` dinamik denetimi gerçekleştirir ve oluşturur <xref:System.InvalidCastException> dönüştürme başarısız olursa.  
  
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
 Sonraki örnek nasıl kullanabileceğinizi gösterir `safe_cast` kullanıcı tanımlı dönüşümler çağırmak için.  
  
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
  
 Kutulama derleyici tarafından eklenen, kullanıcı tanımlı bir dönüştürme olarak tanımlanır.  Bu nedenle, kullanabileceğiniz `safe_cast` CLR yığınındaki bir değer kutusuna için.  
  
 Aşağıdaki örnek, basit ve kullanıcı tanımlı değeri türleri kutulama gösterir.  A `safe_cast` yerel yığında böylece atık toplanan yığında bir değişkene atanabilir olan bir değer türü değişkeni kutuları.  
  
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
  
 Kutulama kullanıcı tanımlı bir dönüştürmede üzerinden önceliğine sahip sonraki örnek göstermektedir bir `safe_cast` işlemi.  
  
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
  
 Kutudan çıkarma derleyici tarafından eklenen, kullanıcı tanımlı bir dönüştürme olarak tanımlanır.  Bu nedenle, kullanabileceğiniz `safe_cast` değerin CLR yığınındaki için.  
  
 Kutudan çıkarma kullanıcı tanımlı bir dönüştürme olmakla birlikte, kutudan çıkarma kutulama aksine, gerekir açık olması — diğer bir deyişle, onu tarafından gerçekleştirilmesi gereken bir `static_cast`, C tarzı cast, veya `safe_cast`; kutudan çıkarma gerçekleştirilemiyor örtük olarak.  
  
```cpp  
// safe_cast_unboxing.cpp  
// compile with: /clr  
int main() {  
   System::Object ^ o = 42;  
   int x = safe_cast<int>(o);  
}  
```  
  
 Değer türleri ve ilkel türler ile kutudan çıkarma aşağıdaki örnek gösterilmektedir.  
  
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
 Sonraki örnek nasıl kullanabileceğinizi gösterir `safe_cast` genel bir tür ile alta dönüştürme gerçekleştirmek için.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [safe_cast](../windows/safe-cast-cpp-component-extensions.md)