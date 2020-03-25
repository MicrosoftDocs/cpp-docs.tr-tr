---
title: Bağımlı Türleri Ad Çözme
ms.date: 11/04/2016
ms.assetid: 34066bb4-0c79-4fd8-bda7-539a60a277ab
ms.openlocfilehash: e9954eab2793f9adf0de75775563df0ae6f063f3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161164"
---
# <a name="name-resolution-for-dependent-types"></a>Bağımlı Türleri Ad Çözme

Derleyiciye verilen nitelenmiş adın bir tür tanımladığından emin olmak için şablon tanımlarındaki nitelenmiş adlar için **TypeName** kullanın. Daha fazla bilgi için bkz. [TypeName](../cpp/typename.md).

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

Bağımlı adlar için ad arama, hem şablon tanımının bağlamlarından adları inceler — aşağıdaki örnekte, bu bağlam `myFunction(char)`ve şablon örneği oluşturma bağlamını bulur. Aşağıdaki örnekte, şablon Main içinde oluşturulur; Bu nedenle `MyNamespace::myFunction`, örnekleme noktasından görünür ve daha iyi eşleşme olarak çekilir. `MyNamespace::myFunction` yeniden adlandırılırsa, bunun yerine `myFunction(char)` çağrılır.

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

### <a name="output"></a>Çıktı

```Output
Int MyNamespace::myFunction
```

### <a name="template-disambiguation"></a>Şablon Kesinleştirme

Visual Studio 2012, "Template" anahtar sözcüğüyle Kesinleştirme için C++ 98/03/11 standart kurallarını uygular. Aşağıdaki örnekte, Visual Studio 2010, uyumlu olmayan satırları ve uygun satırları kabul eder.  Visual Studio 2012 yalnızca uyumlu satırları kabul eder.

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

## <a name="see-also"></a>Ayrıca bkz.

[Ad çözümlemesi](../cpp/templates-and-name-resolution.md)
