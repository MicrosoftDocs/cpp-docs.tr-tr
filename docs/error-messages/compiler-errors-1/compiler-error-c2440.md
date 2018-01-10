---
title: "Derleyici Hatası C2440 | Microsoft Docs"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2440
dev_langs: C++
helpviewer_keywords: C2440
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 62a83da358738f7892fd5db06fbe775ff0b7d7da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2440"></a>Derleyici Hatası C2440
'dönüştürme': 'type1' 'type2' dönüştürülemiyor  
  
Derleyici gelen atanamaz `type1` için `type2`.  
  
## <a name="example"></a>Örnek  
Const olmayan başlatmaya çalışırsanız C2440 neden olabilir `char*` (veya `wchar_t*`) kullanarak C++ kodda bir dize olduğunda derleyici Uyumluluğu seçeneği [/ZC: strictstrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) ayarlanır. C, bir dize dizisi türüdür `char`, ancak C++'da, dizi `const char`. Bu örnek C2440 oluşturur:  
  
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
 Void * üyesine bir işaretçi Dönüştür çalışırsanız C2440 da neden olabilir. Sonraki örnek C2440 oluşturur:  
  
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
 Yalnızca ileri bildirilen ancak tanımlanmamış bir tür cast çalışırsanız C2440 da neden olabilir. Bu örnek C2440 oluşturur:  
  
```cpp  
// c2440a.cpp   
struct Base { }; // Defined  
  
struct Derived; // Forward declaration, not defined  
  
Base * func(Derived * d) {  
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'  
}  
  
```  
  
## <a name="example"></a>Örnek  
 15 ve 16 sonraki örnek satırlarındaki C2440 hataları ile tam `Incompatible calling conventions for UDT return value` ileti. A *UDT* bir sınıf, yapı veya birleşim gibi kullanıcı tanımlı bir türde. UDT çağırma kuralının gerçek çağırma UDT ve bir işlev işaretçisi söz konusu olduğunda ileriye dönük bildirimi çakışıyor dönüş türü olarak belirtildiğinde bu tür uyumsuzluğu hatalara neden olur.  
  
 Örnekte, ilk iletme bildirimleri yapı ve yapı döndüren bir işlev için; yok Derleyici yapısı çağırma C++ kullanan varsaymaktadır. Sonraki varsayılan olarak, C kullanır, yapı tanımı çağırma olduğu. Derleyici dönüş türünü yapıda için çağırma kuralı yapının bir tamamını okuma sonlanana kadar çağırma yapı bilmediğinden `get_c2` de C++ olduğu varsayılır.  
  
 Yapı yapısı döndüren başka bir işlev bildirimi tarafından izlenir, ancak bu noktada, derleyici yapının çağırma C++ olduğunu bilir. Benzer şekilde, böylece yapısı çağırma C++ kullandığını derleyici bilir yapısı döndüren işlev işaretçisi sonra yapı tanımı tanımlanır.  
  
 Uyumsuz çağırma kuralları nedeniyle oluşan C2440 çözümlemek için bir UDT sonra UDT tanımı döndüren işlevler bildirin.  
  
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
 İç işaretçi sıfıra atarsanız C2440 da oluşabilir:  
  
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
 C2440 için yanlış bir kullanıcı tanımlı bir dönüştürme kullanımını da oluşabilir. Örneğin, ne zaman bir dönüşüm işleci tanımlandı olarak `explicit`, derleyici örtük bir dönüştürme kullanamazsınız. Kullanıcı tanımlı dönüşümler hakkında daha fazla bilgi için bkz: [kullanıcı tanımlı Dönüşümler (C + +/ CLI)](../../dotnet/user-defined-conversions-cpp-cli.md)). Bu örnek C2440 oluşturur:  
  
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
 C2440 da gerçekleşebilir, türü olan bir Visual C++ dizi örneği oluşturmayı denerseniz bir <xref:System.Array>.  Daha fazla bilgi için bkz: [diziler](../../windows/arrays-cpp-component-extensions.md).  Sonraki örnek C2440 oluşturur:  
  
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
 C2440 öznitelikler özelliği'daki değişiklikler nedeniyle de oluşabilir.  Aşağıdaki örnek C2440 oluşturur.  
  
```cpp  
// c2440f.cpp  
// compile with: /LD  
[ module(name="PropDemoLib", version=1.0) ];   // C2440  
// try the following line instead  
// [ module(name="PropDemoLib", version="1.0") ];  
```  
  
## <a name="example"></a>Örnek  
 Artık Visual C++ derleyicisi tanır [const_cast işleci](../../cpp/const-cast-operator.md) aşağı dönüştürmek için kaynak kullanan kodu **/CLR** programlama derlenmiştir.  
  
 Bu C2440 gidermek için doğru atama işleci kullanın. Daha fazla bilgi için bkz: [atama işleçleri](../../cpp/casting-operators.md).  
  
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
C2440, Visual Studio 2015 güncelleştirme 3'te derleyici uyumluluğu değişiklikler nedeniyle oluşabilir. Daha önce derleyici yanlış belirli farklı ifadeler aynı türü için bir şablon eşleşme tanımlarken kabul bir `static_cast` işlemi. Derleyici türleri doğru ayırır ve kod artık, dayanıyordu önceki üzerinde `static_cast` davranışı bozulur. Bu sorunu gidermek için şablon parametre türüyle eşleşmiyor veya kullanmak için şablon bağımsız değişken değiştirme bir `reinterpret_cast` veya C tarzı atama.
  
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
### <a name="copy-list-initialization"></a>Kopya listesi başlatma

Visual Studio 2017 ve sonraki nesne oluşturma, Visual Studio 2015'te yakalanan değil ve çökme (Crash) için yol açabilecek Başlatıcı Listeleri kullanarak ilgili derleyici hataları doğru şekilde yükseltmek veya tanımsız çalışma zamanı davranışı. C ++ 17 kopyalama-listesi-başlatma, derleyici aşırı yükleme çözünürlüğü için açık bir oluşturucu göz önüne almanız gerekli değildir, ancak bu aşırı gerçekte seçilirse hatayla yükseltmeniz gerekir.

Aşağıdaki örnek, Visual Studio 2015'te ancak Visual Studio 2017'de derler.

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
### <a name="cv-qualifiers-in-class-construction"></a>MS-niteleyicileri içinde sınıfı oluşturma

Visual Studio 2015'te derleyici bazen yanlış Oluşturucusu aramasıyla sınıf nesnesi oluşturulurken MS-niteleyici yoksayar. Bu büyük olasılıkla bir kilitlenme veya beklenmeyen çalışma zamanı davranışını neden olabilir. Aşağıdaki örnek, Visual Studio 2015'te derler ancak Visual Studio 2017 ve daha sonra derleyici hatası oluşturur:

```cpp
struct S 
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

Hatayı düzeltmek için işleci Int() const olarak bildirin.
