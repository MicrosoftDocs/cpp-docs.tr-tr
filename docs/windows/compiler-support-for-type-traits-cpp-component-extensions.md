---
title: Tür özellikleri (C++ bileşen uzantıları) için derleyici desteği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- __is_simple_value_class
- __has_trivial_destructor
- __has_assign
- __is_union
- __is_class
- __is_abstract
- __has_trivial_assign
- __has_virtual_destructor
- __is_ref_array
- __is_base_of
- __has_copy
- __is_polymorphic
- __has_nothrow_constructor
- __is_ref_class
- __is_delegate
- __is_convertible_to
- __is_value_class
- __is_interface_class
- __has_nothrow_copy
- __is_sealed
- __has_trivial_constructor
- __has_trivial_copy
- __is_enum
- __has_nothrow_assign
- __has_finalizer
- __is_empty
- __is_pod
- __has_user_destructor
dev_langs:
- C++
helpviewer_keywords:
- __is_class keyword [C++]
- __is_pod keyword [C++]
- __is_delegate keyword [C++]
- __is_value_class keyword [C++]
- __has_copy keyword [C++]
- __has_nothrow_copy keyword [C++]
- __is_interface_class keyword [C++]
- __is_sealed keyword [C++]
- __is_convertible_to keyword [C++]
- __is_ref_class keyword [C++]
- __has_trivial_copy keyword [C++]
- __has_user_destructor keyword [C++]
- __is_abstract keyword [C++]
- __is_empty keyword [C++]
- __has_trivial_assign keyword [C++]
- __has_nothrow_constructor keyword [C++]
- __is_ref_array keyword [C++]
- __is_base_of keyword [C++]
- __has_nothrow_assign keyword [C++]
- __has_virtual_destructor keyword [C++]
- __has_finalizer keyword [C++]
- __is_union keyword [C++]
- __has_assign keyword [C++]
- __has_trivial_destructor keyword [C++]
- __is_polymorphic keyword [C++]
- __is_enum keyword [C++]
- __is_simple_value_class keyword [C++]
- __has_trivial_constructor keyword [C++]
ms.assetid: cd440630-0394-48c0-a16b-1580b6ef5844
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fe1173b122e64f9b75af2f8186bf52b50003e5ab
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463622"
---
# <a name="compiler-support-for-type-traits-c-component-extensions"></a>Tür Özellikleri için Derleyici Desteği (C++ Bileşen Uzantıları)
Derleyici destekler *türü nitelikler*, derleme zamanında bir tür çeşitli özelliklerini gösterir.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 **Açıklamalar**  
  
 Tür özellikleri kitaplıkları yazma programcıları için özellikle yararlıdır.  
  
 Aşağıdaki liste, derleyici tarafından desteklenen tür özellikleri içerir. Type all nitelikler dönüş **false** türü niteliğine adıyla belirtilen koşul karşılanmadığında.  
  
 (Aşağıdaki listede, kod örnekleri yalnızca C + yazılır +/ CLI. Karşılık gelen türü niteliğine da desteklenir, ancak [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] aksi belirtilmediği sürece. Terim "platform türü" Windows çalışma zamanı türleri ya da ortak dil çalışma zamanı türleri ifade eder.)  
  
-   `__has_assign(` `type` `)`  
  
     Kopya atama işleci bir platform veya yerel türe sahipse true değerini döndürür.  
  
    ```  
    ref struct R {  
    void operator=(R% r) {}  
    };  
  
    int main() {  
    System::Console::WriteLine(__has_assign(R));  
    }  
    ```  
  
-   `__has_copy(` `type` `)`  
  
     Bir kopya Oluşturucu platform veya yerel türe sahipse true değerini döndürür.  
  
    ```  
    ref struct R {  
    R(R% r) {}  
    };  
  
    int main() {  
    System::Console::WriteLine(__has_copy(R));  
    }  
    ```  
  
-   `__has_finalizer(` `type` `)`  
  
     (Desteklenmez [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)].) CLR türü bir sonlandırıcı sahipse true değerini döndürür. Bkz: [yok ediciler ve sonlandırıcılar, nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C + +/ CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) daha fazla bilgi için.  
  
    ```  
    using namespace System;  
    ref struct R {  
    ~R() {}  
    protected:  
    !R() {}  
    };  
  
    int main() {  
    Console::WriteLine(__has_finalizer(R));  
    }  
    ```  
  
-   `__has_nothrow_assign(` `type` `)`  
  
     Kopya atama işleci bir boş özel durum belirtimi sahipse true değerini döndürür.  
  
    ```  
    #include <stdio.h>  
    struct S {  
    void operator=(S& r) throw() {}  
    };  
  
    int main() {  
    __has_nothrow_assign(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__has_nothrow_constructor(` `type` `)`  
  
     Varsayılan Oluşturucu bir boş özel durum belirtimi sahipse true değerini döndürür.  
  
    ```  
    #include <stdio.h>  
    struct S {  
    S() throw() {}  
    };  
  
    int main() {  
    __has_nothrow_constructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__has_nothrow_copy(` `type` `)`  
  
     Kopya Oluşturucu boş bir özel durum belirtimi sahipse true değerini döndürür.  
  
    ```  
    #include <stdio.h>  
    struct S {  
    S(S& r) throw() {}  
    };  
  
    int main() {  
    __has_nothrow_copy(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__has_trivial_assign(` `type` `)`  
  
     Türü bir basit, derleyici tarafından üretilen atama işleci sahipse true değerini döndürür.  
  
    ```  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_assign(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__has_trivial_constructor(` `type` `)`  
  
     Önemsiz, derleyici tarafından oluşturulan bir oluşturucu türüne sahipse true değerini döndürür.  
  
    ```  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_constructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__has_trivial_copy(` `type` `)`  
  
     Önemsiz, derleyici tarafından oluşturulan kopya Oluşturucu türüne sahipse true değerini döndürür.  
  
    ```  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_copy(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__has_trivial_destructor(` `type` `)`  
  
     Türü bir basit, derleyicinin ürettiği yok Edicisi varsa true değerini döndürür.  
  
    ``` cpp 
    // has_trivial_destructor.cpp  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_destructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__has_user_destructor(` `type` `)`  
  
     Bir platform veya yerel bir tür bir kullanıcı olarak bildirilen yok Edicisi varsa true değerini döndürür.  
  
    ```cpp
    // has_user_destructor.cpp  
  
    using namespace System;  
    ref class R {  
    ~R() {}  
    };  
  
    int main() {  
    Console::WriteLine(__has_user_destructor(R));  
    }  
    ```  
  
-   `__has_virtual_destructor(` `type` `)`  
  
     Türü sanal bir yok Edicisi varsa true değerini döndürür.  
  
     `__has_virtual_destructor` Ayrıca platform türleri ve herhangi bir platform türü kullanıcı tanımlı yıkıcı üzerinde çalışır, sanal bir yıkıcı olur.  
  
    ```cpp  
    // has_virtual_destructor.cpp  
    #include <stdio.h>  
    struct S {  
    virtual ~S() {}  
    };  
  
    int main() {  
    __has_virtual_destructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__is_abstract(` `type` `)`  
  
     Türü soyut bir tür ise true döndürür. Yerel soyut türler hakkında daha fazla bilgi için bkz. [soyut](../windows/abstract-cpp-component-extensions.md).  
  
     `__is_abstract` platform türleri için de kullanılabilir. En az bir soyut üye bir başvuru türüyle en az bir üye arabirimiyle soyut bir tür olduğundan. Soyut platform türleri hakkında daha fazla bilgi için bkz. [soyut sınıflar](../cpp/abstract-classes-cpp.md)  
  
    ```cpp  
    // is_abstract.cpp  
    #include <stdio.h>  
    struct S {  
    virtual void Test() = 0;  
    };  
  
    int main() {  
    __is_abstract(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__is_base_of(` `base` `,` `derived` `)`  
  
     Her iki türü de aynıysa, ilk türü bir temel sınıf ikinci türü ise true döndürür.  
  
     `__is_base_of` platform türleri üzerinde de çalışır. Örneğin, ilk türü ise true döndürür bir [arabirim sınıfı](../windows/interface-class-cpp-component-extensions.md) ve ikinci tür arabirimini uygular.  
  
    ```cpp
    // is_base_of.cpp  
    #include <stdio.h>  
    struct S {};  
    struct T : public S {};  
  
    int main() {  
    __is_base_of(S, T) == true ?  
    printf("true\n") : printf("false\n");  
  
    __is_base_of(S, S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__is_class(` `type` `)`  
  
     Bir yerel sınıf veya yapı türü ise, true döndürür.  
  
    ```
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __is_class(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__is_convertible_to(` `from` `,`  `to` `)`  
  
     İlk tür ikinci türe dönüştürülebilir ise true döndürür.  
  
    ```  
    #include <stdio.h>  
    struct S {};  
    struct T : public S {};  
  
    int main() {  
    S * s = new S;  
    T * t = new T;  
    s = t;  
    __is_convertible_to(T, S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__is_delegate(` `type` `)`  
  
     Gerekirse true döndürür `type` bir temsilci. Daha fazla bilgi için [temsilci (C++ bileşen uzantıları)](../windows/delegate-cpp-component-extensions.md).  
  
    ```  
    delegate void MyDel();  
    int main() {  
    System::Console::WriteLine(__is_delegate(MyDel));  
    }  
    ```  
  
-   `__is_empty(` `type` `)`  
  
     Örnek veri üye türü sahipse true değerini döndürür.  
  
    ```  
    #include <stdio.h>  
    struct S {  
    int Test() {}  
    static int i;  
    };  
    int main() {  
    __is_empty(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__is_enum(` `type` `)`  
  
     Yerel bir numaralandırma türü ise true, aksi durumda değeri döndürür.  
  
    ```cpp
    // is_enum.cpp  
    #include <stdio.h>  
    enum E { a, b };  
  
    struct S {  
    enum E2 { c, d };  
    };  
  
    int main() {  
    __is_enum(E) == true ?  
    printf("true\n") : printf("false\n");  
  
    __is_enum(S::E2) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__is_interface_class(` `type` `)`  
  
     Bir platform arabirimi aktarılırsa true döndürür. Daha fazla bilgi için [arabirim sınıfı](../windows/interface-class-cpp-component-extensions.md).  
  
    ```cpp
    // is_interface_class.cpp  
  
    using namespace System;  
    interface class I {};  
    int main() {  
    Console::WriteLine(__is_interface_class(I));  
    }  
    ```  
  
-   `__is_pod(` `type` `)`  
  
     Tür bir sınıf veya birleşim hiçbir oluşturucu veya özel veya korumalı statik olmayan üye, temel olmayan sınıflar ve sanal işlev yok ise true döndürür. Pod'ları üzerinde C++ standardı bölümleri 8.5.1/1, 9/4 ve 3.9/10 daha fazla bilgi için bkz.  
  
     `__is_pod` temel türler üzerinde false döndürür.  
  
    ```  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __is_pod(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__is_polymorphic(` `type` `)`  
  
     Yerel bir tür sanal işleve sahipse true değerini döndürür.  
  
    ```  
    #include <stdio.h>  
    struct S {  
    virtual void Test(){}  
    };  
  
    int main() {  
    __is_polymorphic(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__is_ref_array(` `type` `)`  
  
     Bir platform dizi aktarılırsa true döndürür. Daha fazla bilgi için [diziler](../windows/arrays-cpp-component-extensions.md).  
  
    ```  
    using namespace System;  
    int main() {  
    array<int>^ x = gcnew array<int>(10);  
    Console::WriteLine(__is_ref_array(array<int>));  
    }  
    ```  
  
-   `__is_ref_class(` `type` `)`  
  
     Başvuru sınıfı aktarılırsa true döndürür. Kullanıcı tarafından tanımlanan başvuru türleri hakkında daha fazla bilgi için bkz. [sınıfları ve yapıları](../windows/classes-and-structs-cpp-component-extensions.md).  
  
    ```  
    using namespace System;  
    ref class R {};  
    int main() {  
    Console::WriteLine(__is_ref_class(Buffer));  
    Console::WriteLine(__is_ref_class(R));  
    }  
    ```  
  
-   `__is_sealed(` `type` `)`  
  
     Bir platform veya yerel tür geçirilen true değeri döndürür, korumalı olarak işaretlenmiş. Daha fazla bilgi için [korumalı](../windows/sealed-cpp-component-extensions.md).  
  
    ```  
    ref class R sealed{};  
    int main() {  
    System::Console::WriteLine(__is_sealed(R));  
    }  
    ```  
  
-   `__is_simple_value_class(` `type` `)`  
  
     Atık olarak toplanmış yığınla başvuru içeren bir değer türüne geçirilen true değerini döndürür. Kullanıcı tanımlı değer türleri hakkında daha fazla bilgi için bkz. [sınıfları ve yapıları](../windows/classes-and-structs-cpp-component-extensions.md).  
  
    ```  
    using namespace System;  
    ref class R {};  
    value struct V {};  
    value struct V2 {  
    R ^ r;   // not a simnple value type  
    };  
  
    int main() {  
    Console::WriteLine(__is_simple_value_class(V));  
    Console::WriteLine(__is_simple_value_class(V2));  
    }  
    ```  
  
-   `__is_union(` `type` `)`  
  
     Bir birleşim türü ise true, aksi durumda değeri döndürür.  
  
    ```  
    #include <stdio.h>  
    union A {  
    int i;  
    float f;  
    };  
  
    int main() {  
    __is_union(A) == true ?  
    printf("true\n") : printf("false\n");  
    }  
    ```  
  
-   `__is_value_class(` `type` `)`  
  
     Bir değer türüne geçirilen true değerini döndürür. Kullanıcı tanımlı değer türleri hakkında daha fazla bilgi için bkz. [sınıfları ve yapıları](../windows/classes-and-structs-cpp-component-extensions.md).  
  
    ```  
    value struct V {};  
  
    int main() {  
    System::Console::WriteLine(__is_value_class(V));  
    }  
    ```  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 **Açıklamalar**  
  
 `__has_finalizer(` *Türü* `)` türü niteliğine bu platform sonlandırıcılar desteklemediğinden desteklenmiyor.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Açıklamalar**  
  
 (Bu özelliğin platforma özel açıklaması yoktur.)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki kod örneği için bir derleme türü niteliğine kullanıma sunmak için bir sınıf şablonu kullanmayı gösterir. bir **/CLR** derleme. Daha fazla bilgi için [Windows çalışma zamanı ve yönetilen şablonlar](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md).  
  
```cpp  
// compiler_type_traits.cpp  
// compile with: /clr  
using namespace System;  
  
template <class T>  
ref struct is_class {  
   literal bool value = __is_ref_class(T);  
};  
  
ref class R {};  
  
int main () {  
   if (is_class<R>::value)  
      Console::WriteLine("R is a ref class");  
   else  
      Console::WriteLine("R is not a ref class");  
}  
```  
  
 **Output**  
  
```Output  
R is a ref class  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)