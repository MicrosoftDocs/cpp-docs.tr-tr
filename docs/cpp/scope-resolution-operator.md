---
title: 'Kapsam Çözümü İşleci: ::'
ms.date: 11/04/2016
f1_keywords:
- '::'
helpviewer_keywords:
- scope, scope resolution operator
- operators [C++], scope resolution
- scope resolution operator
- ':: operator'
ms.assetid: fd5de9d3-c716-4e12-bae9-03a16fd79a50
ms.openlocfilehash: 07c2884ed0ba114c22a0c71bbaf7268d6f6931a4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178892"
---
# <a name="scope-resolution-operator-"></a>Kapsam Çözümü İşleci: ::

Kapsam çözümleme işleci **::** farklı kapsamlarda kullanılan tanımlayıcıları tanımlamak ve belirsizliğini belirlemek için kullanılır. Kapsam hakkında daha fazla bilgi için bkz. [scope](../cpp/scope-visual-cpp.md).

## <a name="syntax"></a>Sözdizimi

```
:: identifier
class-name :: identifier
namespace :: identifier
enum class :: identifier
enum struct :: identifier
```

## <a name="remarks"></a>Açıklamalar

`identifier` bir değişken, bir işlev veya bir numaralandırma değeri olabilir.

## <a name="with-classes-and-namespaces"></a>Sınıflar ve ad alanları

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

Bir ad alanının üyesini tanımlamak veya bir using yönergesinde üyenin ad alanını gösteren bir ad alanını tanımlamak için kapsam çözümleme işlecini kullanabilirsiniz. Aşağıdaki örnekte, `NamespaceB`, bir using yönergesi tarafından `NamespaceC` aday olduğundan, `ClassB` ad alanı `NamespaceB`içinde bildirildiği halde `ClassB`nitelemek için `NamespaceC` kullanabilirsiniz.

```cpp
namespace NamespaceB {
    class ClassB {
    public:
        int x;
    };
}

namespace NamespaceC{
    using namespace B;
}
int main() {
    NamespaceB::ClassB c_b;
    NamespaceC::ClassB c_c;

    c_b.x = 3;
    c_c.x = 4;
}
```

Kapsam çözümleme işleçlerinin zincirlerini kullanabilirsiniz. Aşağıdaki örnekte, `NamespaceD::NamespaceD1` iç içe geçmiş ad alanını `NamespaceD1`tanımlar ve `NamespaceE::ClassE::ClassE1` iç içe sınıf `ClassE1`tanımlar.

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

## <a name="with-static-members"></a>Statik üyelere sahip

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

## <a name="with-scoped-enumerations"></a>Kapsamlı numaralandırmalar

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

[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Ad Alanları](../cpp/namespaces-cpp.md)
