---
title: Derleyici Hatası C2668 | Microsoft Docs
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2668
dev_langs:
- C++
helpviewer_keywords:
- C2668
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3b318c663bb036629086d0bca9a67641e3c4c4e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093759"
---
# <a name="compiler-error-c2668"></a>Derleyici Hatası C2668

'function': aşırı yüklenmiş işleve belirsiz çağrı

Belirtilen aşırı yüklenmiş işlev çağrısı çözümlenemedi. Açıkça bir veya daha fazla gerçek parametre dönüştürme yapmak isteyebilirsiniz.

Ayrıca, şablonu kullanarak bu hatayı alabilirsiniz. Aynı sınıf içinde normal üye işlevini ve bir şablonlu üye işlevini ve aynı imzaya sahip, şablonlu bir ilk sırada olması gerekir. Bu, Visual C++'ın geçerli uygulama kısıtlamasıdır.

İşlev şablonlarının kısmi sıralanması Bilgi Bankası makalesi Q240869 daha fazla bilgi için bkz.

Destekleyen COM nesnesi içeren bir ATL projesi oluşturuyorsanız, `ISupportErrorInfo`, Q243298 Bilgi Bankası makalesine bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2668 oluşturur:

```
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

Bu hatayı gidermek için başka bir yöntem, bir [using bildirimi](../../cpp/using-declaration.md):

```
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

Bu hata için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucu olarak da oluşturulabilir: 0 sabiti, tür dönüştürme belirsiz dönüştürme.

İnt, uzun ve void * için dönüştürme hem gerektirdiğinden sabit 0'ı kullanarak bir yayın dönüştürme belirsiz. Bu hatayı gidermek için 0 hiçbir dönüştürmeler (Bu kod Visual C++ Visual Studio .NET 2003 ve Visual Studio sürümlerinde geçerli olacaktır) gerçekleşmesi gerekir böylece için kullanıldığını işlev parametresi tam türüne dönüştürün.

```
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

Kayan ve tüm matematik işlevlerinin çift forms CRT artık sahip olduğundan, bu hata oluşabilir.

```
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

Pow (int, int) CRT'deki math.h kaldırıldı çünkü bu hata oluşabilir.

```
// C2668e.cpp
#include <math.h>
int main() {
   pow(9,9);   // C2668
   pow((double)9,9);   // OK
}
```

## <a name="example"></a>Örnek

Bu kod, Visual Studio 2015'te başarılı olur ancak Visual Studio 2017 ve sonraki C2668 başarısız olur. Visual Studio 2015'te derleyici deneyebileceğinizi kopya listesi başlatması normal kopya başlatma aynı şekilde ele; yalnızca oluşturucu aşırı yükleme çözümlemesi için dönüştürme kabul.

```
C++
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