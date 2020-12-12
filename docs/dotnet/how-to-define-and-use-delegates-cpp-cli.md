---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: temsilcileri tanımlama ve kullanma (C++/CLı)'
title: 'Nasıl yapılır: Temsilcileri Tanımlama ve Kullanma (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- delegates
ms.assetid: 1cdf3420-89c1-47c0-b796-aa984020e0f8
ms.openlocfilehash: 4229af2015db3a9a77722e9e4cc24b80aa05a49b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175761"
---
# <a name="how-to-define-and-use-delegates-ccli"></a>Nasıl yapılır: Temsilcileri Tanımlama ve Kullanma (C++/CLI)

Bu makalede, C++/CLIENDE temsilcilerin nasıl tanımlanacağı ve kullanılacağı gösterilir.

.NET Framework bir dizi temsilci sağlasa da, bazen yeni temsilciler tanımlamanız gerekebilir.

Aşağıdaki kod örneği adlı bir temsilciyi tanımlar `MyCallback` . Olay işleme kodu — bu yeni temsilci tetiklendiğinde çağrılan işlev; bir dönüş türüne sahip olmalı **`void`** ve bir <xref:System.String> başvuru almalıdır.

Main işlevi, temsilci oluşturmak için tarafından tanımlanan statik bir yöntem kullanır `SomeClass` `MyCallback` . Temsilci, temsilci nesnesine "single" dizesini göndererek gösterildiği gibi, bu işlevi çağırmak için alternatif bir yöntem haline gelir. Daha sonra, ek örnekleri `MyCallback` birlikte bağlanır ve sonra temsilci nesnesine bir çağrı tarafından yürütülür.

```cpp
// use_delegate.cpp
// compile with: /clr
using namespace System;

ref class SomeClass
{
public:
   static void Func(String^ str)
   {
      Console::WriteLine("static SomeClass::Func - {0}", str);
   }
};

ref class OtherClass
{
public:
   OtherClass( Int32 n )
   {
      num = n;
   }

   void Method(String^ str)
   {
      Console::WriteLine("OtherClass::Method - {0}, num = {1}",
         str, num);
   }

   Int32 num;
};

delegate void MyCallback(String^ str);

int main( )
{
   MyCallback^ callback = gcnew MyCallback(SomeClass::Func);
   callback("single");

   callback += gcnew MyCallback(SomeClass::Func);

   OtherClass^ f = gcnew OtherClass(99);
   callback += gcnew MyCallback(f, &OtherClass::Method);

   f = gcnew OtherClass(100);
   callback += gcnew MyCallback(f, &OtherClass::Method);

   callback("chained");

   return 0;
}
```

```Output
static SomeClass::Func - single
static SomeClass::Func - chained
static SomeClass::Func - chained
OtherClass::Method - chained, num = 99
OtherClass::Method - chained, num = 100
```

Sonraki kod örneği, bir temsilcinin bir değer sınıfının üyesi ile nasıl ilişkilendirileceğini gösterir.

```cpp
// mcppv2_del_mem_value_class.cpp
// compile with: /clr
using namespace System;
public delegate void MyDel();

value class A {
public:
   void func1() {
      Console::WriteLine("test");
   }
};

int main() {
   A a;
   A^ ah = a;
   MyDel^ f = gcnew MyDel(a, &A::func1);   // implicit box of a
   f();
   MyDel^ f2 = gcnew MyDel(ah, &A::func1);
   f2();
}
```

```Output
test
test
```

## <a name="how-to-compose-delegates"></a>Temsilcileri oluşturma

`-`Bir bileşen temsilcisini oluşturulmuş bir temsilciden kaldırmak için "" işlecini kullanabilirsiniz.

```cpp
// mcppv2_compose_delegates.cpp
// compile with: /clr
using namespace System;

delegate void MyDelegate(String ^ s);

ref class MyClass {
public:
   static void Hello(String ^ s) {
      Console::WriteLine("Hello, {0}!", s);
   }

   static void Goodbye(String ^ s) {
      Console::WriteLine("  Goodbye, {0}!", s);
   }
};

int main() {

   MyDelegate ^ a = gcnew MyDelegate(MyClass::Hello);
   MyDelegate ^ b = gcnew MyDelegate(MyClass::Goodbye);
   MyDelegate ^ c = a + b;
   MyDelegate ^ d = c - a;

   Console::WriteLine("Invoking delegate a:");
   a("A");
   Console::WriteLine("Invoking delegate b:");
   b("B");
   Console::WriteLine("Invoking delegate c:");
   c("C");
   Console::WriteLine("Invoking delegate d:");
   d("D");
}
```

**Çıktı**

```Output
Invoking delegate a:
Hello, A!
Invoking delegate b:
  Goodbye, B!
Invoking delegate c:
Hello, C!
  Goodbye, C!
Invoking delegate d:
  Goodbye, D!
```

## <a name="pass-a-delegate-to-a-native-function-that-expects-a-function-pointer"></a>Bir temsilciyi, bir işlev işaretçisi bekleyen yerel bir işleve geçirme

Yönetilen bir bileşenden, yerel işlevin yönetilen bileşen temsilcisinin üye işlevini çağırabileceği işlev işaretçisi parametreleriyle yerel bir işlevi çağırabilirsiniz.

Bu örnek, yerel işlevi dışarı aktaran. dll dosyasını oluşturur:

```cpp
// delegate_to_native_function.cpp
// compile with: /LD
#include < windows.h >
extern "C" {
   __declspec(dllexport)
   void nativeFunction(void (CALLBACK *mgdFunc)(const char* str)) {
      mgdFunc("Call to Managed Function");
   }
}
```

Sonraki örnek. dll kullanır ve bir işlev işaretçisi bekleyen yerel işleve bir temsilci tanıtıcısı geçirir.

```cpp
// delegate_to_native_function_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

delegate void Del(String ^s);
public ref class A {
public:
   void delMember(String ^s) {
      Console::WriteLine(s);
   }
};

[DllImportAttribute("delegate_to_native_function", CharSet=CharSet::Ansi)]
extern "C" void nativeFunction(Del ^d);

int main() {
   A ^a = gcnew A;
   Del ^d = gcnew Del(a, &A::delMember);
   nativeFunction(d);   // Call to native function
}
```

**Çıktı**

```Output
Call to Managed Function
```

## <a name="to-associate-delegates-with-unmanaged-functions"></a>Temsilcileri yönetilmeyen işlevlerle ilişkilendirmek için

Bir temsilciyi yerel bir işlevle ilişkilendirmek için, yerel işlevi yönetilen bir tür içinde sarmanız ve aracılığıyla çağrılacak işlevi bildirmeniz gerekir `PInvoke` .

```cpp
// mcppv2_del_to_umnangd_func.cpp
// compile with: /clr
#pragma unmanaged
extern "C" void printf(const char*, ...);
class A {
public:
   static void func(char* s) {
      printf(s);
   }
};

#pragma managed
public delegate void func(char*);

ref class B {
   A* ap;

public:
   B(A* ap):ap(ap) {}
   void func(char* s) {
      ap->func(s);
   }
};

int main() {
   A* a = new A;
   B^ b = gcnew B(a);
   func^ f = gcnew func(b, &B::func);
   f("hello");
   delete a;
}
```

**Çıktı**

```Output
hello
```

## <a name="to-use-unbound-delegates"></a>İlişkisiz temsilcileri kullanmak için

Bağımsız bir temsilciyi, işlevi bir temsilci çağrıldığında çağırmak istediğiniz bir türün bir örneğini geçirmek için kullanabilirsiniz.

İlişkisiz temsilciler özellikle bir koleksiyondaki nesneler arasında yinelemek istiyorsanız — [her biri için,](../dotnet/for-each-in.md) anahtar kelimelerinde, ve her örnekte bir üye işlevi çağırarak yararlıdır.

Bağlı ve ilişkisiz temsilcileri bildirmek, örneklemek ve çağırmak için şu adımları uygulayın:

|Eylem|Bağlantılı temsilciler|İlişkisiz Temsilciler|
|------------|---------------------|-----------------------|
|Bildirileceğini|Temsilci imzasının, temsilci aracılığıyla çağırmak istediğiniz işlevin imzasıyla eşleşmesi gerekir.|Temsilci imzasının ilk parametresi, **`this`** çağırmak istediğiniz nesnenin türüdür.<br /><br /> İlk parametreden sonra, temsilci imzasının, temsilci aracılığıyla çağırmak istediğiniz işlevin imzasıyla eşleşmesi gerekir.|
|Leyebilirsiniz|Bir bağlantılı temsilciyi örneklediğinizde, bir örnek işlevi veya bir genel veya statik üye işlevi belirtebilirsiniz.<br /><br /> Bir örnek işlevi belirtmek için ilk parametre, üye işlevi çağırmak istediğiniz türün bir örneğidir ve ikinci parametre çağırmak istediğiniz işlevin adresidir.<br /><br /> Genel veya statik bir üye işlevi çağırmak isterseniz, bir genel işlevin veya statik üye işlevinin adını geçirin.|İlişkisiz bir temsilciyi örneklediğinizde, çağırmak istediğiniz işlevin adresini iletmeniz yeterlidir.|
|Call|Bir bağlantılı temsilciyi çağırdığınızda, temsilci imzası için gereken parametreleri geçirmeniz yeterlidir.|Bağlanan bir temsilciyle aynıdır, ancak ilk parametrenin çağırmak istediğiniz işlevi içeren nesnenin bir örneği olması gerektiğini unutmayın.|

Bu örnekte, ilişkisiz temsilcilerin nasıl bildirildiği, örneklendirileceğini ve çağrılacağını gösterilmektedir:

```cpp
// unbound_delegates.cpp
// compile with: /clr
ref struct A {
   A(){}
   A(int i) : m_i(i) {}
   void Print(int i) { System::Console::WriteLine(m_i + i);}

private:
   int m_i;
};

value struct V {
   void Print() { System::Console::WriteLine(m_i);}
   int m_i;
};

delegate void Delegate1(A^, int i);
delegate void Delegate2(A%, int i);

delegate void Delegate3(interior_ptr<V>);
delegate void Delegate4(V%);

delegate void Delegate5(int i);
delegate void Delegate6();

int main() {
   A^ a1 = gcnew A(1);
   A% a2 = *gcnew A(2);

   Delegate1 ^ Unbound_Delegate1 = gcnew Delegate1(&A::Print);
   // delegate takes a handle
   Unbound_Delegate1(a1, 1);
   Unbound_Delegate1(%a2, 1);

   Delegate2 ^ Unbound_Delegate2 = gcnew Delegate2(&A::Print);
   // delegate takes a tracking reference (must deference the handle)
   Unbound_Delegate2(*a1, 1);
   Unbound_Delegate2(a2, 1);

   // instantiate a bound delegate to an instance member function
   Delegate5 ^ Bound_Del = gcnew Delegate5(a1, &A::Print);
   Bound_Del(1);

   // instantiate value types
   V v1 = {7};
   V v2 = {8};

   Delegate3 ^ Unbound_Delegate3 = gcnew Delegate3(&V::Print);
   Unbound_Delegate3(&v1);
   Unbound_Delegate3(&v2);

   Delegate4 ^ Unbound_Delegate4 = gcnew Delegate4(&V::Print);
   Unbound_Delegate4(v1);
   Unbound_Delegate4(v2);

   Delegate6 ^ Bound_Delegate3 = gcnew Delegate6(v1, &V::Print);
   Bound_Delegate3();
}
```

**Çıktı**

```Output
2
3
2
3
2
7
8
7
8
7
```

Sonraki örnek, bir koleksiyondaki nesneler arasında yineleme yapmak ve her bir örnekteki üye işlevini çağırmak için, anahtar kelimelerinde ilişkisiz temsilcilerin ve [for each](../dotnet/for-each-in.md) 'ın nasıl kullanılacağını gösterir.

```cpp
// unbound_delegates_2.cpp
// compile with: /clr
using namespace System;

ref class RefClass {
   String^ _Str;

public:
   RefClass( String^ str ) : _Str( str ) {}
   void Print() { Console::Write( _Str ); }
};

delegate void PrintDelegate( RefClass^ );

int main() {
   PrintDelegate^ d = gcnew PrintDelegate( &RefClass::Print );

   array< RefClass^ >^ a = gcnew array<RefClass^>( 10 );

   for ( int i = 0; i < a->Length; ++i )
      a[i] = gcnew RefClass( i.ToString() );

   for each ( RefClass^ R in a )
      d( R );

   Console::WriteLine();
}
```

Bu örnek, bir özelliğin erişimci işlevlerine ilişkisiz bir temsilci oluşturur:

```cpp
// unbound_delegates_3.cpp
// compile with: /clr
ref struct B {
   property int P1 {
      int get() { return m_i; }
      void set(int i) { m_i = i; }
   }

private:
   int m_i;
};

delegate void DelBSet(B^, int);
delegate int DelBGet(B^);

int main() {
   B^ b = gcnew B;

   DelBSet^ delBSet = gcnew DelBSet(&B::P1::set);
   delBSet(b, 11);

   DelBGet^ delBGet = gcnew DelBGet(&B::P1::get);
   System::Console::WriteLine(delBGet(b));
}
```

**Çıktı**

```Output
11
```

Aşağıdaki örnek, bir örneğin bağlı olduğu ve bir örneğin ilişkisiz olduğu çok noktaya yayın temsilcisinin nasıl çağıralınacağını göstermektedir.

```cpp
// unbound_delegates_4.cpp
// compile with: /clr
ref class R {
public:
   R(int i) : m_i(i) {}

   void f(R ^ r) {
      System::Console::WriteLine("in f(R ^ r)");
   }

   void f() {
      System::Console::WriteLine("in f()");
   }

private:
   int m_i;
};

delegate void Del(R ^);

int main() {
   R ^r1 = gcnew R(11);
   R ^r2 = gcnew R(12);

   Del^ d = gcnew Del(r1, &R::f);
   d += gcnew Del(&R::f);
   d(r2);
};
```

**Çıktı**

```Output
in f(R ^ r)
in f()
```

Sonraki örnek, ilişkisiz genel bir temsilcinin nasıl oluşturulacağını ve çağrılacağını gösterir.

```cpp
// unbound_delegates_5.cpp
// compile with: /clr
ref struct R {
   R(int i) : m_i(i) {}

   int f(R ^) { return 999; }
   int f() { return m_i + 5; }

   int m_i;
};

value struct V {
   int f(V%) { return 999; }
   int f() { return m_i + 5; }

   int m_i;
};

generic <typename T>
delegate int Del(T t);

generic <typename T>
delegate int DelV(T% t);

int main() {
   R^ hr = gcnew R(7);
   System::Console::WriteLine((gcnew Del<R^>(&R::f))(hr));

   V v;
   v.m_i = 9;
   System::Console::WriteLine((gcnew DelV<V >(&V::f))(v) );
}
```

**Çıktı**

```Output
12
14
```

## <a name="see-also"></a>Ayrıca bkz.

[temsilci (C++ Bileşen Uzantıları)](../extensions/delegate-cpp-component-extensions.md)
