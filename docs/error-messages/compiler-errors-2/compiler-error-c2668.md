---
title: Derleyici hatası C2668
ms.date: 03/28/2017
f1_keywords:
- C2668
helpviewer_keywords:
- C2668
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
ms.openlocfilehash: f59cb33bed15847ed1a7a2dbe99ea030babf3337
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177163"
---
# <a name="compiler-error-c2668"></a>Derleyici hatası C2668

' function ': aşırı yüklenmiş işleve belirsiz çağrı

Belirtilen aşırı yüklenmiş işlev çağrısı çözümlenemedi. Bir veya daha fazla gerçek parametreyi açıkça dönüştürmek isteyebilirsiniz.

Bu hatayı şablon kullanımı aracılığıyla da alabilirsiniz. Aynı sınıfta, aynı imzaya sahip bir normal üye işleviniz ve şablonlu bir üye işleviniz varsa, öncelikle şablonlu bir tane gelmelidir. Bu, geçerli görsel C++uygulamasının bir kısıtlamasıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2668 oluşturur:

```cpp
// C2668.cpp
struct A {};
struct B : A {};
struct X {};
struct D : B, X {};

void func( X, X ){}
void func( A, B ){}
D d;
int main() {
   func( d, d );   // C2668 D has an A, B, and X
   func( (X)d, (X)d );   // OK, uses func( X, X )
}
```

## <a name="example"></a>Örnek

Bu hatayı çözmek için bir diğer yol ise [using bildirimiyle](../../cpp/using-declaration.md)birlikte:

```cpp
// C2668b.cpp
// compile with: /EHsc /c
// C2668 expected
#include <iostream>
class TypeA {
public:
   TypeA(int value) {}
};

class TypeB {
   TypeB(int intValue);
   TypeB(double dbValue);
};

class TestCase {
public:
   void AssertEqual(long expected, long actual, std::string
                    conditionExpression = "");
};

class AppTestCase : public TestCase {
public:
   // Uncomment the following line to resolve.
   // using TestCase::AssertEqual;
   void AssertEqual(const TypeA expected, const TypeA actual,
                    std::string conditionExpression = "");
   void AssertEqual(const TypeB expected, const TypeB actual,
                    std::string conditionExpression = "");
};

class MyTestCase : public AppTestCase {
   void TestSomething() {
      int actual = 0;
      AssertEqual(0, actual, "Value");
   }
};
```

## <a name="example"></a>Örnek

Bu hata, Visual Studio .NET 2003 için yapılan derleyici uygunluk işinin bir sonucu olarak da oluşturulabilir: 0 sabiti dönüştürmesinde belirsiz dönüştürme.

İnt 'in hem Long hem de void * olarak dönüştürülmesi gerektiğinden, sabit 0 kullanan bir cast üzerinde dönüştürme belirsizdir. Bu hatayı çözmek için 0 ' ı, bir dönüştürme gerçekleşmeyecek şekilde, için kullanıldığı işlev parametresinin tam türüne atayın (Bu kod Visual Studio .NET 2003 ve Visual Studio .NET sürümlerinde geçerli olur C++).

```cpp
// C2668c.cpp
#include "stdio.h"
void f(long) {
   printf_s("in f(long)\n");
}
void f(void*) {
   printf_s("in f(void*)\n");
}
int main() {
   f((int)0);   // C2668

   // OK
   f((long)0);
   f((void*)0);
}
```

## <a name="example"></a>Örnek

Bu hata, CRT 'nin artık tüm matematik işlevlerinin float ve Double biçimleri içerdiğinden meydana gelebilir.

```cpp
// C2668d.cpp
#include <math.h>
int main() {
   int i = 0;
   float f;
   f = cos(i);   // C2668
   f = cos((float)i);   // OK
}
```

## <a name="example"></a>Örnek

POW (int, int), CRT içindeki Math. h öğesinden kaldırıldığı için bu hata ortaya çıkabilir.

```cpp
// C2668e.cpp
#include <math.h>
int main() {
   pow(9,9);   // C2668
   pow((double)9,9);   // OK
}
```

## <a name="example"></a>Örnek

Bu kod Visual Studio 2015 ' de başarılı olur, ancak Visual Studio 2017 ve sonraki sürümlerinde C2668 ile başarısız olur. Visual Studio 2015 ' de, derleyici yanlışlıkla kopyalama-liste başlatmasını düzenli kopya başlatma ile aynı şekilde kabul ediyor; yalnızca aşırı yükleme çözümlemesi için Oluşturucu dönüştürmekte sayılır.

```cpp
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```
