---
title: Derleyici hatası C2440
ms.date: 03/28/2017
f1_keywords:
- C2440
helpviewer_keywords:
- C2440
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
ms.openlocfilehash: 75b2ba62182a33137b433c836b4acf7c9e1fc231
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87207985"
---
# <a name="compiler-error-c2440"></a>Derleyici hatası C2440

' dönüştürme ': ' type1 ' iken ' type2 ' olarak dönüştürülemez

Derleyici öğesinden `type1` öğesine atanamaz `type2` .

## <a name="example"></a>Örnek

C2440 **`char*`** `wchar_t*` , derleyici uyumluluk seçeneği [/Zc: strictStrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) ayarlandığında, C++ kodunda bir dize sabiti kullanarak const olmayan bir (veya) başlatmaya çalıştığınızda olabilir. C 'de, dize sabit değerinin türü dizidir **`char`** , ancak C++ ' da dizidir `const char` . Bu örnek C2440 oluşturur:

```cpp
// C2440s.cpp
// Build: cl /Zc:strictStrings /W3 C2440s.cpp
// When built, the compiler emits:
// error C2440: 'initializing' : cannot convert from 'const char [5]'
// to 'char *'
//        Conversion from string literal loses const qualifier (see
// /Zc:strictStrings)

int main() {
   char* s1 = "test"; // C2440
   const char* s2 = "tests"; // OK
}
```

## <a name="example"></a>Örnek

C2440, bir işaretçiyi bir üyeye void * öğesine dönüştürmeye çalıştığınızda da oluşabilir. Sonraki örnek C2440 oluşturur:

```cpp
// C2440.cpp
class B {
public:
   void  f(){;}

   typedef void (B::*pf)();

   void f2(pf pf) {
       (this->*pf)();
       void* pp = (void*)pf;   // C2440
   }

   void f3() {
      f2(f);
   }
};
```

## <a name="example"></a>Örnek

C2440, yalnızca iletme yapılmış ancak tanımlanmamış bir türden atama yapmaya çalıştığınızda da oluşabilir. Bu örnek C2440 oluşturur:

```cpp
// c2440a.cpp
struct Base { }; // Defined

struct Derived; // Forward declaration, not defined

Base * func(Derived * d) {
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'
}
```

## <a name="example"></a>Örnek

15. satırlardaki C2440 hataları ve sonraki örnek 16, iletiyle nitelenir `Incompatible calling conventions for UDT return value` . *Udt* , sınıf, yapı veya birleşim gibi Kullanıcı tanımlı bir türdür. Bu tür uyumsuzluk hataları, bir iletme bildiriminin dönüş türünde belirtilen bir UDT çağırma kuralı, UDT 'nin gerçek çağırma kuralıyla ve bir işlev işaretçisi dahil edildiğinde çakışırsa oluşur.

Örnekte, önce bir struct ve struct döndüren bir işlev için ileri bildirimler vardır; Derleyici, yapının C++ çağırma kuralını kullandığını varsayar. Next, varsayılan olarak C çağırma kuralını kullanan yapı tanımıdır. Derleyici, yapının tamamını okumayı tamamlayana kadar yapının çağırma kuralını bilmez çünkü, dönüş türü içindeki yapının çağırma kuralı `get_c2` da C++ olarak kabul edilir.

Yapısına, yapısını döndüren başka bir işlev bildirimi gelir, ancak bu noktada, derleyici yapının çağırma kuralının C++ olduğunu bilir. Benzer şekilde, yapısını döndüren işlev işaretçisi yapı tanımından sonra tanımlanır, böylece derleyici yapının C++ çağırma kuralını kullandığını bilir.

Uyumsuz çağırma kuralları nedeniyle oluşan C2440 çözümlemek için, UDT tanımından sonra UDT döndüren işlevleri bildirin.

```cpp
// C2440b.cpp
struct MyStruct;

MyStruct get_c1();

struct MyStruct {
   int i;
   static MyStruct get_C2();
};

MyStruct get_C3();

typedef MyStruct (*FC)();

FC fc1 = &get_c1;   // C2440, line 15
FC fc2 = &MyStruct::get_C2;   // C2440, line 16
FC fc3 = &get_C3;

class CMyClass {
public:
   explicit CMyClass( int iBar)
      throw()   {
   }

   static CMyClass get_c2();
};

int main() {
   CMyClass myclass = 2;   // C2440
   // try one of the following
   // CMyClass myclass{2};
   // CMyClass myclass(2);

   int *i;
   float j;
   j = (float)i;   // C2440, cannot cast from pointer to int to float
}
```

## <a name="example"></a>Örnek

C2440, iç işaretçiye sıfır atarsanız da gerçekleşebilir:

```cpp
// C2440c.cpp
// compile with: /clr
int main() {
   array<int>^ arr = gcnew array<int>(100);
   interior_ptr<int> ipi = &arr[0];
   ipi = 0;   // C2440
   ipi = nullptr;   // OK
}
```

## <a name="example"></a>Örnek

C2440, Kullanıcı tanımlı dönüştürmenin yanlış kullanımı için de oluşabilir. Örneğin, bir dönüştürme işleci olarak tanımlandığında **`explicit`** , derleyici onu örtük bir dönüşümde kullanamaz. Kullanıcı tanımlı dönüştürmeler hakkında daha fazla bilgi için bkz. [Kullanıcı tanımlı dönüşümler (C++/CLI)](../../dotnet/user-defined-conversions-cpp-cli.md)). Bu örnek C2440 oluşturur:

```cpp
// C2440d.cpp
// compile with: /clr
value struct MyDouble {
   double d;
   // convert MyDouble to Int32
   static explicit operator System::Int32 ( MyDouble val ) {
      return (int)val.d;
   }
};

int main() {
   MyDouble d;
   int i;
   i = d;   // C2440
   // Uncomment the following line to resolve.
   // i = static_cast<int>(d);
}
```

## <a name="example"></a>Örnek

C2440, türü bir olan Visual C++ dizisinin bir örneğini oluşturmayı denerseniz da oluşabilir <xref:System.Array> .  Daha fazla bilgi için bkz. [diziler](../../extensions/arrays-cpp-component-extensions.md).  Sonraki örnek C2440 oluşturur:

```cpp
// C2440e.cpp
// compile with: /clr
using namespace System;
int main() {
   array<int>^ intArray = Array::CreateInstance(__typeof(int), 1);   // C2440
   // try the following line instead
   // array<int>^ intArray = safe_cast<array<int> ^>(Array::CreateInstance(__typeof(int), 1));
}
```

## <a name="example"></a>Örnek

C2440, öznitelikler özelliğindeki değişiklikler nedeniyle de oluşabilir.  Aşağıdaki örnek C2440 oluşturur.

```cpp
// c2440f.cpp
// compile with: /LD
[ module(name="PropDemoLib", version=1.0) ];   // C2440
// try the following line instead
// [ module(name="PropDemoLib", version="1.0") ];
```

## <a name="example"></a>Örnek

Microsoft C++ derleyicisi artık **/clr** programlama kullanan kaynak kodu derlendiğinde [const_cast işlecinin](../../cpp/const-cast-operator.md) , dönüştürmeyi açmasına izin vermez.

Bu C2440 çözümlemek için doğru atama işlecini kullanın. Daha fazla bilgi için bkz. [atama işleçleri](../../cpp/casting-operators.md).

Bu örnek C2440 oluşturur:

```cpp
// c2440g.cpp
// compile with: /clr
ref class Base {};
ref class Derived : public Base {};
int main() {
   Derived ^d = gcnew Derived;
   Base ^b = d;
   d = const_cast<Derived^>(b);   // C2440
   d = dynamic_cast<Derived^>(b);   // OK
}
```

## <a name="example"></a>Örnek

C2440, Visual Studio 2015 güncelleştirme 3 ' te derleyicinin uyumluluk değişiklikleri nedeniyle oluşabilir. Daha önce, derleyici bir işlem için bir şablon eşleşmesi tanımlarken aynı tür olarak belirli farklı ifadeleri yanlış olarak ele ıyordu **`static_cast`** . Artık derleyici, türleri doğru şekilde ayırır ve önceki davranışa bağlı olan kod **`static_cast`** bozulur. Bu sorunu onarmak için, şablon bağımsız değişkenini şablon parametre türüyle eşleşecek şekilde değiştirin ya da **`reinterpret_cast`** ya da C stili bir tür dönüştürme kullanın.

Bu örnek C2440 oluşturur:

```cpp
// c2440h.cpp

template<int *a>
struct S1 {};

int g;
struct S2 : S1<&g> {
};

int main()
{
    S2 s;
    static_cast<S1<&*&g>>(s); // C2440 in VS 2015 Update 3
    // This compiles correctly:
    // static_cast<S1<&g>>(s);
}

This error can appear in ATL code that uses the SINK_ENTRY_INFO macro defined in <atlcom.h>.
```

## <a name="example"></a>Örnek

### <a name="copy-list-initialization"></a>Kopya listesini başlatma

Visual Studio 2017 ve üzeri, Visual Studio 2015 ' de yakalanmayan başlatıcı listeleri kullanarak nesne oluşturmayla ilgili derleyici hatalarını doğru şekilde yükseltir ve kilitlenmelere veya tanımsız çalışma zamanı davranışına neden olabilir. C++ 17 Copy-List-Initialization sürümünde, derleyici aşırı yükleme çözümlemesi için açık bir Oluşturucu kabul etmek zorundadır, ancak aşırı yükleme gerçekten seçilirse bir hata oluşturması gerekir.

Aşağıdaki örnek Visual Studio 2015 ' de derlenir ancak Visual Studio 2017 ' de değildir.

```cpp
// C2440j.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot
                         // convert from 'int' to 'const A &'
}
```

Hatayı düzeltmek için, doğrudan başlatma kullanın:

```cpp
// C2440k.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    const A& a2{ 1 };
}
```

## <a name="example"></a>Örnek

### <a name="cv-qualifiers-in-class-construction"></a>sınıf yapııncv niteleyicileri

Visual Studio 2015 ' de, derleyici bazen bir Oluşturucu çağrısı aracılığıyla bir sınıf nesnesi oluştururken CV niteleyicisi yanlış yoksayar. Bu, kilitlenme veya beklenmeyen çalışma zamanı davranışına neden olabilir. Aşağıdaki örnek Visual Studio 2015 ' de derlenir ancak Visual Studio 2017 ve sonraki sürümlerde bir derleyici hatası oluşturur:

```cpp
struct S
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

Hatayı düzeltmek için int () işlecini const olarak bildirin.
