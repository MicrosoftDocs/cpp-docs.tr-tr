---
title: Tür Özellikleri için Derleyici Desteği (C++/CLI ve C++/CX)
ms.date: 10/12/2018
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
ms.openlocfilehash: 16c79e05c6ba6f50a3e6c0d6dd5f48963be40fa8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219787"
---
# <a name="compiler-support-for-type-traits-ccli-and-ccx"></a>Tür Özellikleri için Derleyici Desteği (C++/CLI ve C++/CX)

Microsoft C++ derleyicisi, derleme zamanında bir türün çeşitli özelliklerini gösteren C++/CLı ve C++/CX uzantıları için *tür nitelikleri* destekler.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="remarks"></a>Açıklamalar

Tür nitelikleri özellikle kitaplıkları yazan programcılar için yararlıdır.

Aşağıdaki liste, derleyici tarafından desteklenen tür nitelikleri içerir. **`false`** Nitelik türünün adı tarafından belirtilen koşul karşılanmazsa, tüm tür nitelikleri döndürülür.

(Aşağıdaki listede, kod örnekleri yalnızca C++/cliendilinde yazılmıştır. Ancak, aksi belirtilmedikçe, karşılık gelen nitelik türü C++/CX içinde de desteklenir. "Platform türü" terimi Windows Çalışma Zamanı türler veya ortak dil çalışma zamanı türleri anlamına gelir.)

- `__has_assign(`*tür*`)`

   **`true`** Platform veya yerel türün bir kopya atama işleci varsa döndürür.

    ```cpp
    ref struct R {
    void operator=(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_assign(R));
    }
    ```

- `__has_copy(`*tür*`)`

   **`true`** Platform veya yerel türün bir kopya Oluşturucusu olup olmadığını döndürür.

    ```cpp
    ref struct R {
    R(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_copy(R));
    }
    ```

- `__has_finalizer(`*tür*`)`

   (C++/CX'DE desteklenmez.) **`true`** CLR türünün sonlandırıcısı varsa döndürür. Daha fazla bilgi için bkz. [nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C++/CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) .

    ```cpp
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

- `__has_nothrow_assign(`*tür*`)`

   **`true`** Bir kopya atama işlecinin boş bir özel durum belirtimine sahip olup olmadığını döndürür.

    ```cpp
    #include <stdio.h>
    struct S {
    void operator=(S& r) throw() {}
    };

    int main() {
    __has_nothrow_assign(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_nothrow_constructor(`*tür*`)`

   **`true`** Varsayılan oluşturucunun boş bir özel durum belirtimine sahip olup olmadığını döndürür.

    ```cpp
    #include <stdio.h>
    struct S {
    S() throw() {}
    };

    int main() {
    __has_nothrow_constructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_nothrow_copy(`*tür*`)`

   **`true`** Kopya oluşturucusunun boş bir özel durum belirtimi olup olmadığını döndürür.

    ```cpp
    #include <stdio.h>
    struct S {
    S(S& r) throw() {}
    };

    int main() {
    __has_nothrow_copy(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_assign(`*tür*`)`

   **`true`** Türün önemsiz, derleyici tarafından oluşturulan bir atama işleci varsa döndürür.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_assign(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_constructor(`*tür*`)`

   **`true`** Türün önemsiz, derleyici tarafından oluşturulan bir oluşturucuya sahip olup olmadığını döndürür.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_constructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_copy(`*tür*`)`

   **`true`** Türün önemsiz, derleyici tarafından oluşturulan bir kopya oluşturucusuna sahip olup olmadığını döndürür.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_copy(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_destructor(`*tür*`)`

   **`true`** Türün önemsiz, derleyici tarafından oluşturulan bir yıkıcıya sahip olup olmadığını döndürür.

    ``` cpp
    // has_trivial_destructor.cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_destructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_user_destructor(`*tür*`)`

   **`true`** Platform veya yerel türün Kullanıcı tarafından tanımlanmış bir yıkıcıya sahip olup olmadığını döndürür.

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

- `__has_virtual_destructor(`*tür*`)`

   **`true`** Türün bir sanal yok ediciye sahip olup olmadığını döndürür.

   `__has_virtual_destructor`Ayrıca platform türlerinde ve bir platform türündeki Kullanıcı tanımlı yok edicinin sanal bir yıkıcıdır.

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

- `__is_abstract(`*tür*`)`

   **`true`** Türün soyut bir tür olup olmadığını döndürür. Yerel soyut türler hakkında daha fazla bilgi için bkz. [soyut sınıflar](../cpp/abstract-classes-cpp.md).

   `__is_abstract`Platform türleri için de geçerlidir. En az bir üyesi olan bir arabirim, en az bir soyut üyeye sahip bir başvuru türü olan bir soyut türdür. Soyut platform türleri hakkında daha fazla bilgi için bkz. [abstract](abstract-cpp-component-extensions.md).

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

- `__is_base_of(` `base` `,` `derived` `)`

   **`true`** Her iki tür de aynı ise, ilk türün ikinci türün temel sınıfı olup olmadığını döndürür.

   `__is_base_of`Platform türleri üzerinde de kullanılabilir. Örneğin, **`true`** ilk tür bir [arabirim sınıfı](interface-class-cpp-component-extensions.md) ise ve ikinci tür arabirimi uygularsa bu döndürülür.

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

- `__is_class(`*tür*`)`

   **`true`** Türün bir yerel sınıf veya yapı birimi olup olmadığını döndürür.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_class(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_convertible_to(` `from` `,`  `to` `)`

   **`true`** İlk türün ikinci türe dönüştürülebileceğinden, döndürür.

    ```cpp
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

- `__is_delegate(`*tür*`)`

   **`true`** `type` Bir Temsilciyse döndürür. Daha fazla bilgi için bkz. [Temsilci (c++/CLI ve c++/cx)](delegate-cpp-component-extensions.md).

    ```cpp
    delegate void MyDel();
    int main() {
    System::Console::WriteLine(__is_delegate(MyDel));
    }
    ```

- `__is_empty(`*tür*`)`

   **`true`** Türün örnek veri üyelerine sahip olup olmadığını döndürür.

    ```cpp
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

- `__is_enum(`*tür*`)`

   **`true`** Türün yerel bir sabit listesi olup olmadığını döndürür.

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

- `__is_interface_class(`*tür*`)`

   **`true`** Platform arabirimi geçirilmezse döndürür. Daha fazla bilgi için bkz. [interface class](interface-class-cpp-component-extensions.md).

    ```cpp
    // is_interface_class.cpp

    using namespace System;
    interface class I {};
    int main() {
    Console::WriteLine(__is_interface_class(I));
    }
    ```

- `__is_pod(`*tür*`)`

   **`true`** Tür, Oluşturucu ya da özel veya korumalı statik olmayan üyeler, temel sınıf ve sanal işlev olmadan bir sınıf veya birleşim ise döndürür. PODs hakkında daha fazla bilgi için bkz. C++ Standard, sections 8.5.1/1, 9/4 ve 3.9/10.

   `__is_pod`, temel türlerde false döndürür.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_pod(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_polymorphic(`*tür*`)`

   **`true`** Yerel bir türün sanal işlevlere sahip olup olmadığını döndürür.

    ```cpp
    #include <stdio.h>
    struct S {
    virtual void Test(){}
    };

    int main() {
    __is_polymorphic(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_ref_array(`*tür*`)`

   **`true`** Platform dizisi geçmişse döndürür. Daha fazla bilgi için bkz. [diziler](arrays-cpp-component-extensions.md).

    ```cpp
    using namespace System;
    int main() {
    array<int>^ x = gcnew array<int>(10);
    Console::WriteLine(__is_ref_array(array<int>));
    }
    ```

- `__is_ref_class(`*tür*`)`

   **`true`** Başvuru sınıfı geçirilirse döndürür. Kullanıcı tanımlı başvuru türleri hakkında daha fazla bilgi için bkz. [sınıflar ve yapılar](classes-and-structs-cpp-component-extensions.md).

    ```cpp
    using namespace System;
    ref class R {};
    int main() {
    Console::WriteLine(__is_ref_class(Buffer));
    Console::WriteLine(__is_ref_class(R));
    }
    ```

- `__is_sealed(`*tür*`)`

   **`true`** Platform veya yerel tür Sealed olarak işaretlenmiş olarak geçirilirse döndürür. Daha fazla bilgi için bkz. [Sealed](sealed-cpp-component-extensions.md).

    ```cpp
    ref class R sealed{};
    int main() {
    System::Console::WriteLine(__is_sealed(R));
    }
    ```

- `__is_simple_value_class(`*tür*`)`

   **`true`** Atık toplanmış yığına başvuru içermeyen bir değer türü geçirilmezse döndürür. Kullanıcı tanımlı değer türleri hakkında daha fazla bilgi için bkz. [sınıflar ve yapılar](classes-and-structs-cpp-component-extensions.md).

    ```cpp
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

- `__is_union(`*tür*`)`

   **`true`** Bir türün birleşim olup olmadığını döndürür.

    ```cpp
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

- `__is_value_class(`*tür*`)`

   **`true`** Değer türü geçirilmezse döndürür. Kullanıcı tanımlı değer türleri hakkında daha fazla bilgi için bkz. [sınıflar ve yapılar](classes-and-structs-cpp-component-extensions.md).

    ```cpp
    value struct V {};

    int main() {
    System::Console::WriteLine(__is_value_class(V));
    }
    ```

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

`__has_finalizer(` *type* `)` Bu platform sonlandırıcıları desteklemediğinden nitelik tür türü desteklenmiyor.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

(Bu özellik için platforma özgü bir açıklama yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/clr`

### <a name="examples"></a>Örnekler

**Örnek**

Aşağıdaki kod örneği, bir derleme için nitelik derleyici türü göstermek için bir sınıf şablonunun nasıl kullanılacağını gösterir `/clr` . Daha fazla bilgi için bkz. [Windows çalışma zamanı ve yönetilen şablonlar](windows-runtime-and-managed-templates-cpp-component-extensions.md).

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

```Output
R is a ref class
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)
