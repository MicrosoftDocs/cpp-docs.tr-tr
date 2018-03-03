---
title: "Kapsam çözümü işleci::: | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69b52b3029271ffae3d4a7b3441c49a01270abb4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="scope-resolution-operator-"></a>Kapsam Çözümü İşleci: ::
Kapsam çözümü işleci `::` tanımlamak ve farklı kapsamlarda kullanılan tanımlayıcıları belirsizliğini ortadan kaldırmak için kullanılır. Kapsam hakkında daha fazla bilgi için bkz: [kapsam](../cpp/scope-visual-cpp.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
:: identifier  
class-name :: identifier  
namespace :: identifier  
enum class :: identifier  
enum struct :: identifier  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `identifier` Bir değişken, bir işlev veya bir numaralandırma değeri olabilir.  
  
## <a name="with-classes-and-namespaces"></a>Ad alanları ve sınıfları ile  
 Aşağıdaki örnek, kapsam çözümü işleci ad alanları ve sınıflar ile nasıl kullanıldığını gösterir:  
  
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
  
 Kapsam çözümü işleci bir kapsam niteleyicisi olmadan genel ad alanına başvuruyor.  
  
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
  
 Kapsam çözümü işleci bir ad alanının bir üyesi tanımlamak veya üyenin ad alanında kullanma yönergesi nominates bir ad alanı belirlemek için kullanabilirsiniz. Aşağıdaki örnekte, kullandığınız `NamespaceC` nitelemek için `ClassB`rağmen `ClassB` ad alanında bildirildi `NamespaceB`, çünkü `NamespaceB` içinde MVP `NamespaceC` bir kullanarak yönergesi.  
  
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
  
 Kapsam çözümü işleci zincirleri kullanabilirsiniz. Aşağıdaki örnekte, `NamespaceD::NamespaceD1` iç içe geçmiş ad alanını tanımlayan `NamespaceD1`, ve `NamespaceE::ClassE::ClassE1` iç içe geçmiş sınıf tanımlar `ClassE1`.  
  
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
  
## <a name="with-static-members"></a>İle statik üyeler  
 Kapsam çözümü işleci statik sınıf üyeleri çağırmak için kullanmanız gerekir.  
  
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
  
## <a name="with-scoped-enumerations"></a>İle kapsamlı numaralandırmaları  
 Kapsamlı çözümü işleci da kapsamlı bir numaralandırma değerleri ile kullanılan [numaralandırma bildirimleri](../cpp/enumerations-cpp.md), aşağıdaki örnekte olduğu gibi:  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Ad Alanları](../cpp/namespaces-cpp.md)   