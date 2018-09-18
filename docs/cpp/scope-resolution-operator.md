---
title: 'Kapsam çözümü işleci::: | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '::'
dev_langs:
- C++
helpviewer_keywords:
- scope, scope resolution operator
- operators [C++], scope resolution
- scope resolution operator
- ':: operator'
ms.assetid: fd5de9d3-c716-4e12-bae9-03a16fd79a50
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 430cac01ba8cc8f6bf18df14715cab4959a3708b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075988"
---
# <a name="scope-resolution-operator-"></a>Kapsam Çözümü İşleci: ::

Kapsam çözümleme işleci **::** belirlemek ve farklı kapsamlarda kullanılan tanımlayıcıları ayırt etmek için kullanılır. Kapsamı hakkında daha fazla bilgi için bkz. [kapsam](../cpp/scope-visual-cpp.md).

## <a name="syntax"></a>Sözdizimi

```
:: identifier
class-name :: identifier
namespace :: identifier
enum class :: identifier
enum struct :: identifier
```

## <a name="remarks"></a>Açıklamalar

`identifier` Bir değişken, işlev veya bir sabit listesi değeri olabilir.

## <a name="with-classes-and-namespaces"></a>Ad alanlarını ve sınıfları ile

Aşağıdaki örnek, kapsam çözümleme işleci ad alanlarını ve sınıfları ile nasıl kullanıldığını gösterir:

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

Kapsam niteleyicisi olmayan bir kapsam çözümleme işleci genel isim uzayına başvuruyor.

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

Kapsam çözümleme işleci bir isim uzayı üyesi tanımlamak veya üyenin ad alanı kullanarak yönergesinde nominates bir ad alanı tanımlamak için kullanabilirsiniz. Aşağıdaki örnekte, kullandığınız `NamespaceC` nitelemek için `ClassB`rağmen `ClassB` ad alanında bildirilen `NamespaceB`, çünkü `NamespaceB` , aday `NamespaceC` bir kullanarak yönergesi.

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

Kapsam çözümleme işleci zincirleri kullanabilirsiniz. Aşağıdaki örnekte, `NamespaceD::NamespaceD1` iç içe geçmiş ad alanını tanımlayan `NamespaceD1`, ve `NamespaceE::ClassE::ClassE1` iç içe geçmiş sınıf tanımlar `ClassE1`.

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

## <a name="with-static-members"></a>Statik üyeleri ile

Statik sınıf üyeleri çağırmak için kapsam çözünürlük işlecini kullanmanız gerekir.

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

## <a name="with-scoped-enumerations"></a>Kapsamlı numaralandırmalar ile

Kapsamlı çözümleme işleci ayrıca kapsamlı numaralandırma değerlerinin kullanılan [numaralandırma bildirimleri](../cpp/enumerations-cpp.md), aşağıdaki örnekte olduğu gibi:

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