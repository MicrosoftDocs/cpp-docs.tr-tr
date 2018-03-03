---
title: "Derleyici Hatası C2668 | Microsoft Docs"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2668
dev_langs:
- C++
helpviewer_keywords:
- C2668
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e45bff3173013e7a26f9682bb10ec4cc1fda9364
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2668"></a>Derleyici Hatası C2668
'function': aşırı yüklenmiş işlevi belirsiz çağrısı  
  
 Belirtilen aşırı yüklenmiş işlev çağrısı çözümlenemiyor. Bir veya daha fazla gerçek parametresini açıkça cast isteyebilirsiniz.  
  
 Ayrıca, şablonu kullanarak bu hatayı alabilirsiniz. Normal üye işlevini ve aynı imzayla şablonlu üye işlevi aynı sınıfta, varsa, şablonlu bir ilk gelmesi gerekir. Visual C++ geçerli uyarlamasını kısıtlamasıdır.  
  
 İşlev şablonlarının kısmi sıralanması Bilgi Bankası makalesi Q240869 daha fazla bilgi için bkz.  
  
 COM destekleyen nesne içeren bir ATL projesi oluşturma, `ISupportErrorInfo`, Q243298 Bilgi Bankası makalesine bakın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2668 oluşturur:  
  
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
 Bu hatayı gidermek için başka bir yolu bir [bildirimi kullanarak](../../cpp/using-declaration.md):  
  
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
 Bu hata için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucunda da oluşturulabilir: sabit 0 cast belirsiz dönüştürme.  
  
 İnt, long ve void * bir dönüştürme hem gerektirdiğinden sabit 0 kullanarak bir cast dönüştürme belirsiz. Bu hatayı gidermek için 0 hiçbir Dönüşümleri (Bu kodu Visual C++, Visual Studio .NET 2003 ve Visual Studio .NET sürümlerinde geçerli olur) gerçekleşmesi gerekir böylece için kullanılan işlev parametresi tam türüne dönüştürün.  
  
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
 CRT float ve tüm matematik işlevleri çift biçimlerinin şimdi olduğundan bu hata oluşabilir.  
  
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
 Pow (int, int) CRT'deki math.h kaldırıldığından, bu hata oluşabilir.  
  
```  
// C2668e.cpp  
#include <math.h>  
int main() {  
   pow(9,9);   // C2668  
   pow((double)9,9);   // OK  
}  
```

## <a name="example"></a>Örnek  
Bu kod, Visual Studio 2015'te başarılı ancak Visual Studio 2017 ve daha sonra C2668 başarısız olur. Visual Studio 2015'te derleyici yanlışlıkla kopyalama listesi başlatma Normal kopyalama başlatma aynı şekilde ele; yalnızca oluşturucuları aşırı yükleme çözünürlüğü için dönüştürme kabul. 

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