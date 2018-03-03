---
title: "Bağımlı türleri için ad çözümlemesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 34066bb4-0c79-4fd8-bda7-539a60a277ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d8978e38745f088884bbf28ffb0ab98cfb87895
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="name-resolution-for-dependent-types"></a>Bağımlı Türleri Ad Çözme
Kullanım **typename** verilen tam adı bir türü tanımlar derleyici bildirmek için şablon tanımlarında nitelenmiş adlar için. Daha fazla bilgi için bkz: [typename](../cpp/typename.md).  
  
```cpp  
// template_name_resolution1.cpp  
#include <stdio.h>  
template <class T> class X  
{  
public:  
   void f(typename T::myType* mt) {}  
};  
  
class Yarg  
{  
public:  
   struct myType { };  
};  
  
int main()  
{  
   X<Yarg> x;  
   x.f(new Yarg::myType());  
   printf("Name resolved by using typename keyword.");  
}  
```  
  
```Output  
Name resolved by using typename keyword.  
```  
  
 Bağımlı adlar için ad arama inceler bağlamı şablon tanımının adlarından — aşağıdaki örnekte, bu bağlamda bulur `myFunction(char)`— ve şablonu örneklemesi bağlamı. Aşağıdaki örnekte, ana şablon örneği; Bu nedenle, `MyNamespace::myFunction` örneklemesi noktasından görünür ve daha iyi eşleşme olarak çekilir. `MyNamespace::myFunction` yeniden adlandırılırsa, bunun yerine `myFunction(char)` çağrılır.  
  
 Tüm adlar, bağımsız adlar gibi çözümlenir. Bununla birlikte, olası bir çakışma varsa tam adlar kullanmanızı öneririz.  
  
```cpp  
// template_name_resolution2.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
void myFunction(char)  
{  
   cout << "Char myFunction" << endl;  
}  
  
template <class T> class Class1  
{  
public:  
   Class1(T i)  
   {  
      // If replaced with myFunction(1), myFunction(char)  
      // will be called  
      myFunction(i);  
}  
};  
  
namespace MyNamespace  
{  
   void myFunction(int)  
   {  
      cout << "Int MyNamespace::myFunction" << endl;  
   }  
};  
  
using namespace MyNamespace;  
  
int main()  
{  
   Class1<int>* c1 = new Class1<int>(100);  
}  
```  
  
### <a name="output"></a>Çıkış  
  
```  
Int MyNamespace::myFunction  
```  
  
### <a name="template-disambiguation"></a>Şablon Kesinleştirme  
 [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)], "şablon" anahtar sözcüğü ile kesinleştirme için C ++ 98/03/11 standart kurallarını uygular. Aşağıdaki örnekte, Visual C++ 2010 uyumsuz satırları ve uyumlu satırları kabul eder.  [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)]yalnızca uyumlu satırları kabul eder.  
  
```cpp  
#include <iostream>  
#include <ostream>  
#include <typeinfo>  
using namespace std;  
  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    #if defined(NONCONFORMANT)  
        typedef typename AY::Rebind<X>::Other AX; // nonconformant  
    #elif defined(CONFORMANT)  
        typedef typename AY::template Rebind<X>::Other AX; // conformant  
    #else  
        #error Define NONCONFORMANT or CONFORMANT.  
    #endif  
};  
  
int main() {  
    cout << typeid(Container<int, Allocator<float>>::AX).name() << endl;  
}  
```  
  
 C++ varsayılan olarak `AY::Rebind`'ın bir şablon olmadığını varsaydığı ve dolayısıyla aşağıdaki "`<`" öğesini az olarak yorumladığı için kesinleştirme kurallarına uyum sağlanması gerekir. "`Rebind`" öğesini bir açılı ayraç olarak ayrıştırabilmesi için `<`'ın bir şablon olduğunu bilmesi gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ad çözümlemesi](../cpp/templates-and-name-resolution.md)