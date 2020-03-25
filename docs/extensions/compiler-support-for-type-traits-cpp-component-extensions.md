---
title: Tür nitelikleri için derleyici desteği (C++/CLI ve C++/CX)
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
ms.openlocfilehash: 1bfb4308dc76e3393eceddf8dedd6d11e73adc17
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172536"
---
# <a name="compiler-support-for-type-traits-ccli-and-ccx"></a>Tür nitelikleri için derleyici desteği (C++/CLI ve C++/CX)

Microsoft C++ derleyicisi, bir türün derleme zamanında C++çeşitli özelliklerini gösteren/CLI ve C++/CX uzantıları için *tür nitelikleri* destekler.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="remarks"></a>Açıklamalar

Tür nitelikleri özellikle kitaplıkları yazan programcılar için yararlıdır.

Aşağıdaki liste, derleyici tarafından desteklenen tür nitelikleri içerir. Nitelik türünün adı tarafından belirtilen koşul karşılanmazsa, tüm tür nitelikleri **false** döndürür.

(Aşağıdaki listede, kod örnekleri yalnızca/Cli'de C++yazılmıştır. Ancak, aksi belirtilmedikçe, karşılık gelen nitelik türü C++/CX içinde de desteklenir. "Platform türü" terimi Windows Çalışma Zamanı türler veya ortak dil çalışma zamanı türleri anlamına gelir.)

- `__has_assign(` *türü* `)`

   Platform veya yerel türün bir kopya atama işleci varsa, **true** döndürür.

    ```cpp
    ref struct R {
    void operator=(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_assign(R));
    }
    ```

- `__has_copy(` *türü* `)`

   Platform veya yerel türün bir kopya Oluşturucusu varsa, **true** döndürür.

    ```cpp
    ref struct R {
    R(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_copy(R));
    }
    ```

- `__has_finalizer(` *türü* `)`

   (/Cx'de C++desteklenmez.) CLR türünün bir sonlandırıcısı varsa, **true** döndürür. Daha fazla bilgi için bkz. [nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C++/CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) .

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

- `__has_nothrow_assign(` *türü* `)`

   Bir kopya atama işlecinin boş bir özel durum belirtimi varsa **true** değerini döndürür.

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

- `__has_nothrow_constructor(` *türü* `)`

   Varsayılan oluşturucunun boş bir özel durum belirtimi varsa **true** değerini döndürür.

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

- `__has_nothrow_copy(` *türü* `)`

   Kopya oluşturucunun boş bir özel durum belirtimi varsa **true** değerini döndürür.

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

- `__has_trivial_assign(` *türü* `)`

   Türün önemsiz, derleyici tarafından oluşturulan bir atama işleci varsa **true** değerini döndürür.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_assign(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_constructor(` *türü* `)`

   Türün önemsiz, derleyici tarafından üretilmiş bir Oluşturucusu varsa **true** değerini döndürür.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_constructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_copy(` *türü* `)`

   Türün önemsiz, derleyici tarafından oluşturulan bir kopya Oluşturucusu varsa **true** değerini döndürür.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_copy(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_destructor(` *türü* `)`

   Türün önemsiz, derleyici tarafından oluşturulan bir yıkıcı varsa **true** döndürür.

    ``` cpp
    // has_trivial_destructor.cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_destructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_user_destructor(` *türü* `)`

   Platform veya yerel türün Kullanıcı tarafından belirtilen yıkıcı varsa, **true** döndürür.

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

- `__has_virtual_destructor(` *türü* `)`

   Türün bir sanal yıkıcısı varsa, **true** döndürür.

   `__has_virtual_destructor` Ayrıca platform türlerinde da kullanılabilir ve bir platform türündeki Kullanıcı tanımlı yıkıcının sanal bir yıkıcıdır.

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

- `__is_abstract(` *türü* `)`

   Tür soyut bir tür ise, **true** döndürür. Yerel soyut türler hakkında daha fazla bilgi için bkz. [soyut sınıflar](../cpp/abstract-classes-cpp.md).

   `__is_abstract` platform türleri için de geçerlidir. En az bir üyesi olan bir arabirim, en az bir soyut üyeye sahip bir başvuru türü olan bir soyut türdür. Soyut platform türleri hakkında daha fazla bilgi için bkz. [abstract](abstract-cpp-component-extensions.md).

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

   Her iki tür de aynı ise, birinci tür ikinci türün temel sınıfı ise **true** döndürür.

   `__is_base_of` Ayrıca platform türleri üzerinde de kullanılabilir. Örneğin, ilk tür bir [arabirim sınıfı](interface-class-cpp-component-extensions.md) ise ve ikinci tür arabirimini uyguluyorsa, **true** döndürür.

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

- `__is_class(` *türü* `)`

   Tür yerel bir sınıf veya yapı ise, **true** döndürür.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_class(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_convertible_to(` `from` `,``to` `)`

   İlk tür ikinci türe dönüştürülebiliyorsa, **true** döndürür.

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

- `__is_delegate(` *türü* `)`

   `type` bir Temsilciyse, **true** döndürür. Daha fazla bilgi için bkz. [temsilciC++(/CLI C++ve/CX)](delegate-cpp-component-extensions.md).

    ```cpp
    delegate void MyDel();
    int main() {
    System::Console::WriteLine(__is_delegate(MyDel));
    }
    ```

- `__is_empty(` *türü* `)`

   Türün örnek veri üyeleri yoksa, **true** döndürür.

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

- `__is_enum(` *türü* `)`

   Tür yerel bir sabit listesi ise, **true** döndürür.

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

- `__is_interface_class(` *türü* `)`

   Platform arabirimi geçirilirse **true** döndürür. Daha fazla bilgi için bkz. [interface class](interface-class-cpp-component-extensions.md).

    ```cpp
    // is_interface_class.cpp

    using namespace System;
    interface class I {};
    int main() {
    Console::WriteLine(__is_interface_class(I));
    }
    ```

- `__is_pod(` *türü* `)`

   Tür, Oluşturucu veya özel veya korumalı statik olmayan üyeler, temel sınıf ve sanal işlev olmadan bir sınıf veya birleşim ise **true** döndürür. PODs C++ hakkında daha fazla bilgi için bkz. Standart, Bölüm 8.5.1/1, 9/4 ve 3.9/10.

   `__is_pod`, temel türlerde false döndürür.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_pod(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_polymorphic(` *türü* `)`

   Yerel türde sanal işlevler varsa, **true** döndürür.

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

- `__is_ref_array(` *türü* `)`

   Platform dizisi geçirildiğinde **true** döndürür. Daha fazla bilgi için bkz. [diziler](arrays-cpp-component-extensions.md).

    ```cpp
    using namespace System;
    int main() {
    array<int>^ x = gcnew array<int>(10);
    Console::WriteLine(__is_ref_array(array<int>));
    }
    ```

- `__is_ref_class(` *türü* `)`

   Başvuru sınıfı geçirilirse **true** döndürür. Kullanıcı tanımlı başvuru türleri hakkında daha fazla bilgi için bkz. [sınıflar ve yapılar](classes-and-structs-cpp-component-extensions.md).

    ```cpp
    using namespace System;
    ref class R {};
    int main() {
    Console::WriteLine(__is_ref_class(Buffer));
    Console::WriteLine(__is_ref_class(R));
    }
    ```

- `__is_sealed(` *türü* `)`

   Korumalı olarak işaretlenmiş bir platform veya yerel tür geçmişse **true** döndürür. Daha fazla bilgi için bkz. [Sealed](sealed-cpp-component-extensions.md).

    ```cpp
    ref class R sealed{};
    int main() {
    System::Console::WriteLine(__is_sealed(R));
    }
    ```

- `__is_simple_value_class(` *türü* `)`

   Atık toplanmış yığına başvuru içermeyen bir değer türü geçirtiyse **true** döndürür. Kullanıcı tanımlı değer türleri hakkında daha fazla bilgi için bkz. [sınıflar ve yapılar](classes-and-structs-cpp-component-extensions.md).

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

- `__is_union(` *türü* `)`

   Bir tür birleşimse **true** döndürür.

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

- `__is_value_class(` *türü* `)`

   Değer türü geçirildiğinde **true** döndürür. Kullanıcı tanımlı değer türleri hakkında daha fazla bilgi için bkz. [sınıflar ve yapılar](classes-and-structs-cpp-component-extensions.md).

    ```cpp
    value struct V {};

    int main() {
    System::Console::WriteLine(__is_value_class(V));
    }
    ```

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

Bu platform sonlandırıcıları desteklemediğinden `__has_finalizer(`*türü*`)` türü nitelik desteklenmiyor.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

(Bu özellik için platforma özgü bir açıklama yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

**Örnek**

Aşağıdaki kod örneği, bir `/clr` derlemesi için bir derleyici türü nitelik göstermek için bir sınıf şablonunun nasıl kullanılacağını gösterir. Daha fazla bilgi için bkz. [Windows çalışma zamanı ve yönetilen şablonlar](windows-runtime-and-managed-templates-cpp-component-extensions.md).

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

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)
