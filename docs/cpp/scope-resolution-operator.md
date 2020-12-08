---
title: 'Kapsam çözümleme işleci: `::`'
description: Kapsam çözümleme işlecinin `::` Standart C++ ' da nasıl çalıştığını öğrenin.
ms.date: 12/06/2020
f1_keywords:
- '::'
helpviewer_keywords:
- scope, scope resolution operator
- operators [C++], scope resolution
- scope resolution operator
- ':: operator'
ms.openlocfilehash: ff774d9fcca9f68cb2925af82c55ef438ab4d71a
ms.sourcegitcommit: 7b131db4ed39bddb4a456ebea402f47c5cbd69d3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2020
ms.locfileid: "96776537"
---
# <a name="scope-resolution-operator-"></a>Kapsam çözümleme işleci: `::`

Kapsam çözümleme işleci, **`::`** Farklı kapsamlarda kullanılan tanımlayıcıları tanımlamak ve belirsizliğini belirlemek için kullanılır. Kapsam hakkında daha fazla bilgi için bkz. [scope](../cpp/scope-visual-cpp.md).

## <a name="syntax"></a>Syntax

> *`qualified-id`*:\
> &emsp;*`nested-name-specifier`***`template`** <sub>opt</sub>*`unqualified-id`*

> *`nested-name-specifier`*:\
> &emsp;**`::`**\
> &emsp;*`type-name`* **`::`**\
> &emsp;*`namespace-name`* **`::`**\
> &emsp;*`decltype-specifier`* **`::`**\
> &emsp;*`nested-name-specifier`* *`identifier`* **`::`**\
> &emsp;*`nested-name-specifier`***`template`** <sub>opt</sub> opt *`simple-template-id`***`::`**

> *`unqualified-id`*:\
> &emsp;*`identifier`*\
> &emsp;*`operator-function-id`*\
> &emsp;*`conversion-function-id`*\
> &emsp;*`literal-operator-id`*\
> &emsp;**`~`** *`type-name`*\
> &emsp;**`~`** *`decltype-specifier`*\
> &emsp;*`template-id`*

## <a name="remarks"></a>Açıklamalar

`identifier`Bir değişken, bir işlev veya bir numaralandırma değeri olabilir.

## <a name="use--for-classes-and-namespaces"></a>`::`Sınıflar ve ad alanları için kullanın

Aşağıdaki örnek, kapsam çözümleme işlecinin ad alanları ve sınıflarla nasıl kullanıldığını göstermektedir:

```cpp
namespace NamespaceA{
    int x;
    class ClassA {
    public:
        int x;
    };
}

int main() {

    // A namespace name used to disambiguate
    NamespaceA::x = 1;

    // A class name used to disambiguate
    NamespaceA::ClassA a1;
    a1.x = 2;
}
```

Kapsam niteleyicisi olmayan bir kapsam çözümleme işleci, genel ad alanına başvurur.

```cpp
namespace NamespaceA{
    int x;
}

int x;

int main() {
    int x;

    // the x in main()
    x = 0;
    // The x in the global namespace
    ::x = 1;

    // The x in the A namespace
    NamespaceA::x = 2;
}
```

Bir öğesinin üyesini tanımlamak **`namespace`** veya bir yönergede üyenin ad alanını gösteren bir ad alanını tanımlamak için kapsam çözümleme işlecini kullanabilirsiniz **`using`** . Aşağıdaki örnekte, `NamespaceC` `ClassB` `ClassB` `NamespaceB` `NamespaceB` `NamespaceC` bir yönergesi tarafından aday olduğundan, ad alanı içinde bildirildiği halde nitelendirmek için kullanabilirsiniz **`using`** .

```cpp
namespace NamespaceB {
    class ClassB {
    public:
        int x;
    };
}

namespace NamespaceC{
    using namespace NamespaceB;
}

int main() {
    NamespaceB::ClassB b_b;
    NamespaceC::ClassB c_b;

    b_b.x = 3;
    c_b.x = 4;
}
```

Kapsam çözümleme işleçlerinin zincirlerini kullanabilirsiniz. Aşağıdaki örnekte, `NamespaceD::NamespaceD1` iç içe geçmiş ad alanını tanımlar `NamespaceD1` ve `NamespaceE::ClassE::ClassE1` iç içe yerleştirilmiş sınıfı tanımlar `ClassE1` .

```cpp
namespace NamespaceD{
    namespace NamespaceD1{
        int x;
    }
}

namespace NamespaceE{
    class ClassE{
    public:
        class ClassE1{
        public:
            int x;
        };
    };
}

int main() {
    NamespaceD:: NamespaceD1::x = 6;
    NamespaceE::ClassE::ClassE1 e1;
    e1.x = 7  ;
}
```

## <a name="use--for-static-members"></a>`::`Statik üyeler için kullanın

Sınıfların statik üyelerini çağırmak için kapsam çözümleme işlecini kullanmanız gerekir.

```cpp
class ClassG {
public:
    static int get_x() { return x;}
    static int x;
};

int ClassG::x = 6;

int main() {

    int gx1 = ClassG::x;
    int gx2 = ClassG::get_x();
}
```

## <a name="use--for-scoped-enumerations"></a>`::`Kapsamlı Numaralandırmalar için kullanın

Kapsamlı çözümleme işleci, aşağıdaki örnekte olduğu gibi kapsamlı numaralandırma [Listeleme bildirimlerinin](../cpp/enumerations-cpp.md)değerleriyle de kullanılır:

```cpp
enum class EnumA{
    First,
    Second,
    Third
};

int main() {
    EnumA enum_value = EnumA::First;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ yerleşik işleçleri, önceliği ve ilişkilendirilebilirlik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Ad Alanları](../cpp/namespaces-cpp.md)
