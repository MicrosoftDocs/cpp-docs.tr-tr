---
title: Derleyici Hatası C2440 | Microsoft Docs
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2440
dev_langs:
- C++
helpviewer_keywords:
- C2440
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80107f3adf4b460fd2563026a1b7ff6ab6394167
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091224"
---
# <a name="compiler-error-c2440"></a>Derleyici Hatası C2440

'conversion': 'type1' 'type2' olarak dönüştürülemez

Derleyici türüne dönüştürülemiyor `type1` için `type2`.

## <a name="example"></a>Örnek

C2440, sabit olmayan başlatmaya çalışıyorsanız oluşabilir `char*` (veya `wchar_t*`) C++ kodunda bir dize kullanarak, derleyici Uyumluluğu seçeneği [/ZC: strictstrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) ayarlanır. C'de, dize sabit değeri türünü dizisi olan `char`, ancak C++'da dizisidir `const char`. Bu örnek C2440 oluşturur:

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

Void * üyesine bir işaretçi dönüştürme yapmayı denediğinizde c2440 öğesine de neden. Sonraki örnek C2440 oluşturur:

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

Sadece ileri bildirimli ancak tanımlanmamış bir türden atama yapmayı denediğinizde c2440 öğesine de neden. Bu örnek C2440 oluşturur:

```cpp
// c2440a.cpp
struct Base { }; // Defined

struct Derived; // Forward declaration, not defined

Base * func(Derived * d) {
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'
}

```

## <a name="example"></a>Örnek

15 ve 16 sonraki örneğin satırlarındaki C2440 hataları nitelenmiştir `Incompatible calling conventions for UDT return value` ileti. A *UDT* bir sınıf, yapı veya birleşim gibi kullanıcı tanımlı bir tür. Bir UDT çağırma kuralı, bir iletme bildirimiyle çakışıyor gerçek çağırma kuralı işlevi işaretçisi olduğunda ve UDT dönüş türü belirtildiğinde, bu tür uyumsuzluk hataları neden olur.

Örnekte, ilk vardır ve yapı döndüren bir işlev için bir yapı bildirimleri; Derleyici yapının C++ çağırma kuralını kullandığını varsayar. Ardından, varsayılan olarak, C kullanır yapı tanımının çağrı kuralı. Derleyici, dönüş türünde struct çağırma kuralının yapının bir tamamını okumayı bitirmeden struct çağırma kuralını bilmediğinden `get_c2` da C++ olduğu varsayılır.

Yapı, yapı döndüren başka bir işlev bildirimi gelir, ancak bu noktada derleyici yapının çağırma kuralının C++ olduğunu bilir. Benzer şekilde, yapı döndüren işlev işaretçisi, derleyici yapının C++ çağırma kuralı kullandığını bilebilmesi için yapı tanımından sonra tanımlanır.

Uyumsuz çağırma kuralları nedeniyle oluşan c2440 hatası düzeltmek için UDT tanımından sonra UDT döndüren işlevleri bildirin.

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

C2440, iç işaretçiye sıfır atarsanız da oluşabilir:

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

C2440, kullanıcı tanımlı bir dönüştürmenin yanlış kullanımı için de oluşabilir. Örneğin, ne zaman bir dönüştürme operatörünün tanımlanmış olarak `explicit`, derleyici örtük bir dönüştürme kullanamazsınız. Kullanıcı tanımlı dönüştürmeler hakkında daha fazla bilgi için bkz. [kullanıcı tanımlı Dönüşümler (C + +/ CLI)](../../dotnet/user-defined-conversions-cpp-cli.md)). Bu örnek C2440 oluşturur:

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

C2440, türü olan bir Visual C++ dizi örneği oluşturmayı denerseniz de oluşabilir bir <xref:System.Array>.  Daha fazla bilgi için [diziler](../../windows/arrays-cpp-component-extensions.md).  Sonraki örnek C2440 oluşturur:

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

C2440 öznitelik özelliğinde yapılan değişiklikler nedeniyle de oluşabilir.  Aşağıdaki örnek C2440 oluşturur.

```cpp
// c2440f.cpp
// compile with: /LD
[ module(name="PropDemoLib", version=1.0) ];   // C2440
// try the following line instead
// [ module(name="PropDemoLib", version="1.0") ];
```

## <a name="example"></a>Örnek

Visual C++ derleyicisi artık sağlayan [const_cast işleci](../../cpp/const-cast-operator.md) alta dönüştürmesine için kullanan kaynak kodu **/CLR** programlama derlenmiştir.

Bu c2440 hatasını düzeltmek için doğru atama işlecini kullanın. Daha fazla bilgi için [atama işleçleri](../../cpp/casting-operators.md).

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

C2440, derleyici Visual Studio 2015 güncelleştirme 3'te uyumluluk değişiklikleri nedeniyle oluşabilir. Daha önce derleyici yanlış belirli farklı ifadeler aynı türü olarak tanımlamak için bir şablon eşleşme ele bir `static_cast` işlemi. Derleyici türleri doğru ayırır ve kod şimdi, yararlandı önceki `static_cast` davranışı bozulur. Bu sorunu gidermek için şablonu parametre türüyle eşleşmiyor veya kullanmak için şablon bağımsız değişkeni değiştirmek bir `reinterpret_cast` veya C stili tür dönüştürme.

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

### <a name="copy-list-initialization"></a>Kopya listesi başlatması

Visual Studio 2017 ve üzeri için kilitlenmelere neden olabilir ve Visual Studio 2015'te yakalanan olmayan Başlatıcı Listeleri kullanarak nesne oluşturma ilgili derleyici hataları doğru şekilde yükseltmek veya çalışma zamanı davranışı tanımsız. C ++ 17 kopya listesi başlatması, derleyicinin açık bir oluşturucu aşırı yükleme çözümlemesi için göz önünde bulundurmanız gerekir, ancak aşırı yükleyen gerçekten seçilirse hata yükseltmeniz gerekir.

Aşağıdaki örnek, Visual Studio 2015'te ancak Visual Studio 2017 derler.

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

Hatayı düzeltmek için doğrudan başlatma kullanın:

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

### <a name="cv-qualifiers-in-class-construction"></a>sınıf oluşturma CV niteleyicileri

Visual Studio 2015'te derleyici bazen yanlışlıkla bir sınıf nesnesi bir oluşturucu çağrısı aracılığıyla oluştururken cv niteleyici yoksayar. Bu durum bir kilitlenme veya beklenmeyen çalışma zamanı davranışına neden olabilir. Aşağıdaki örnek, Visual Studio 2015'te derler ancak Visual Studio 2017 ve sonraki sürümlerinde bir derleyici hatası oluşturur:

```cpp
struct S
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

Hatayı düzeltmek için işleci Int() const olarak bildirin.
