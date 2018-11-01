---
title: Bağımlı Türleri Ad Çözme
ms.date: 11/04/2016
ms.assetid: 34066bb4-0c79-4fd8-bda7-539a60a277ab
ms.openlocfilehash: 04db4b0efc5e58dbd3de6fc9979c3a3cdd44d84e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563164"
---
# <a name="name-resolution-for-dependent-types"></a>Bağımlı Türleri Ad Çözme

Kullanım **typename** derleyiciye belirtilen tam adın bir türü tanımladığını bildirmek üzere şablon tanımlarında tam adlar için. Daha fazla bilgi için [typename](../cpp/typename.md).

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

Bağımlı adlara yönelik ad araması, adları hem şablon tanımının bağlamı denetler — aşağıdaki örnekte, bu bağlamda bulacağından `myFunction(char)`— ve Şablon örneğinin bağlamı. Aşağıdaki örnekte, ana şablon örneği; Bu nedenle, `MyNamespace::myFunction` örnek oluşturma noktasında görülebilir ve daha iyi bir eşleşme olarak seçilir. `MyNamespace::myFunction` yeniden adlandırılırsa, bunun yerine `myFunction(char)` çağrılır.

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

```Output
Int MyNamespace::myFunction
```

### <a name="template-disambiguation"></a>Şablon Kesinleştirme

Visual Studio 2012, C ++ 98/03/11 standart kurallarını "Şablon" anahtar sözcüğü ile Kesinleştirme için zorlar. Aşağıdaki örnekte, Visual C++ 2010 hem uyumsuz satırları hem de uyumlu satırları kabul eder.  Visual Studio 2012, yalnızca uyumlu satırları kabul eder.

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