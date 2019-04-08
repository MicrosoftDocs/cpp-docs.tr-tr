---
title: Tür özellikleri için derleyici desteği (C + +/ CLI ve C + +/ CX)
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
ms.openlocfilehash: d068917a02fef0f1d4b7fd46fd6978da2d358872
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026892"
---
# <a name="compiler-support-for-type-traits-ccli-and-ccx"></a>Tür özellikleri için derleyici desteği (C + +/ CLI ve C + +/ CX)

Microsoft C++ derleyicisi destekleyen *türü nitelikler* C + +/ CLI ve C + +/ CX uzantılar, derleme zamanında bir tür çeşitli özelliklerini gösterir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="remarks"></a>Açıklamalar

Tür özellikleri kitaplıkları yazma programcıları için özellikle yararlıdır.

Aşağıdaki liste, derleyici tarafından desteklenen tür özellikleri içerir. Type all nitelikler dönüş **false** türü niteliğine adıyla belirtilen koşul karşılanmadığında.

(Aşağıdaki listede, kod örnekleri yalnızca C + yazılır +/ CLI. Ancak karşılık gelen türü niteliğine ayrıca C +'da desteklenen +/ CX aksi belirtilmediği sürece. Terim "platform türü" Windows çalışma zamanı türleri ya da ortak dil çalışma zamanı türleri ifade eder.)

- `__has_assign(` * türü* `)`

   Döndürür **true** kopya atama işleci bir platform veya yerel bir tür varsa.

    ```cpp
    ref struct R {
    void operator=(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_assign(R));
    }
    ```

- `__has_copy(` * türü* `)`

   Döndürür **true** platform veya yerel bir tür bir kopya Oluşturucusu varsa.

    ```cpp
    ref struct R {
    R(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_copy(R));
    }
    ```

- `__has_finalizer(` * türü* `)`

   (Not desteklenen C + +/ CX.) Döndürür **true** CLR türü bir sonlandırıcı varsa. Bkz: [yok ediciler ve sonlandırıcılar, nasıl yapılır: Sınıfları ve yapıları tanımlama ve kullanma (C + +/ CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) daha fazla bilgi için.

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

- `__has_nothrow_assign(` * türü* `)`

   Döndürür **true** kopya atama işleci bir boş özel durum belirtimi varsa.

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

- `__has_nothrow_constructor(` * türü* `)`

   Döndürür **true** varsayılan oluşturucu bir boş özel durum belirtimi varsa.

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

- `__has_nothrow_copy(` * türü* `)`

   Döndürür **true** kopya Oluşturucu boş bir özel durum belirtimi varsa.

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

- `__has_trivial_assign(` * türü* `)`

   Döndürür **true** Önemsiz, derleyici tarafından üretilen atama işleci türündeyse.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_assign(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_constructor(` * türü* `)`

   Döndürür **true** türü, önemsiz, derleyicinin ürettiği Oluşturucusu varsa.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_constructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_copy(` * türü* `)`

   Döndürür **true** türü, önemsiz, derleyicinin ürettiği kopyalama Oluşturucusu varsa.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_copy(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_destructor(` * türü* `)`

   Döndürür **true** türü bir basit, derleyicinin ürettiği yok Edicisi varsa.

    ``` cpp
    // has_trivial_destructor.cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_destructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_user_destructor(` * türü* `)`

   Döndürür **true** platform veya yerel bir tür bir kullanıcı olarak bildirilen yok Edicisi varsa.

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

- `__has_virtual_destructor(` * türü* `)`

   Döndürür **true** türü sanal bir yok Edicisi varsa.

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

- `__is_abstract(` * türü* `)`

   Döndürür **true** türü soyut bir tür ise. Yerel soyut türler hakkında daha fazla bilgi için bkz. [soyut sınıflar](../cpp/abstract-classes-cpp.md).

   `__is_abstract` platform türleri için de kullanılabilir. En az bir soyut üye bir başvuru türüyle en az bir üye arabirimiyle soyut bir tür olduğundan. Soyut platform türleri hakkında daha fazla bilgi için bkz. [soyut](abstract-cpp-component-extensions.md).

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

   Döndürür **true** ikinci türü temel bir sınıfı ilk türü ise if iki türü de aynıdır.

   `__is_base_of` platform türleri üzerinde de çalışır. Örneğin, döndürür **true** ilk türü ise bir [arabirim sınıfı](interface-class-cpp-component-extensions.md) ve ikinci tür arabirimini uygular.

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

- `__is_class(` * türü* `)`

   Döndürür **true** türü bir yerel sınıf veya yapı ise.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_class(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_convertible_to(` `from` `,`  `to` `)`

   Döndürür **true** ilk tür ikinci türe dönüştürülebilir ise.

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

- `__is_delegate(` * türü* `)`

   Döndürür **true** varsa `type` bir temsilci. Daha fazla bilgi için [temsilci (C + +/ CLI ve C + +/ CX)](delegate-cpp-component-extensions.md).

    ```cpp
    delegate void MyDel();
    int main() {
    System::Console::WriteLine(__is_delegate(MyDel));
    }
    ```

- `__is_empty(` * türü* `)`

   Döndürür **true** örnek veri üye türü varsa.

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

- `__is_enum(` * türü* `)`

   Döndürür **true** yerel bir numaralandırma türü ise.

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

- `__is_interface_class(` * türü* `)`

   Döndürür **true** platform Interface geçirilmiş. Daha fazla bilgi için [arabirim sınıfı](interface-class-cpp-component-extensions.md).

    ```cpp
    // is_interface_class.cpp

    using namespace System;
    interface class I {};
    int main() {
    Console::WriteLine(__is_interface_class(I));
    }
    ```

- `__is_pod(` * türü* `)`

   Döndürür **true** türü bir sınıf veya birleşim hiçbir oluşturucu veya özel veya korumalı statik olmayan üye, temel olmayan sınıflar ve sanal işlev yok ise. Pod'ları üzerinde C++ standardı bölümleri 8.5.1/1, 9/4 ve 3.9/10 daha fazla bilgi için bkz.

   `__is_pod` temel türler üzerinde false döndürür.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_pod(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_polymorphic(` * türü* `)`

   Döndürür **true** yerel bir tür sanal işlevler varsa.

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

- `__is_ref_array(` * türü* `)`

   Döndürür **true** platform dizi geçirilmiş. Daha fazla bilgi için [diziler](arrays-cpp-component-extensions.md).

    ```cpp
    using namespace System;
    int main() {
    array<int>^ x = gcnew array<int>(10);
    Console::WriteLine(__is_ref_array(array<int>));
    }
    ```

- `__is_ref_class(` * türü* `)`

   Döndürür **true** başvuru sınıfı geçirilmiş. Kullanıcı tarafından tanımlanan başvuru türleri hakkında daha fazla bilgi için bkz. [sınıfları ve yapıları](classes-and-structs-cpp-component-extensions.md).

    ```cpp
    using namespace System;
    ref class R {};
    int main() {
    Console::WriteLine(__is_ref_class(Buffer));
    Console::WriteLine(__is_ref_class(R));
    }
    ```

- `__is_sealed(` * türü* `)`

   Döndürür **true** bir platform veya yerel türü sealed olarak işaretlenmiş geçirilmiş. Daha fazla bilgi için [korumalı](sealed-cpp-component-extensions.md).

    ```cpp
    ref class R sealed{};
    int main() {
    System::Console::WriteLine(__is_sealed(R));
    }
    ```

- `__is_simple_value_class(` * türü* `)`

   Döndürür **true** atık olarak toplanmış yığınla başvuru içeren bir değer türü geçirilmiş. Kullanıcı tanımlı değer türleri hakkında daha fazla bilgi için bkz. [sınıfları ve yapıları](classes-and-structs-cpp-component-extensions.md).

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

- `__is_union(` * türü* `)`

   Döndürür **true** bir türü UNION ise.

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

- `__is_value_class(` * türü* `)`

   Döndürür **true** geçirilmiş bir değer türü. Kullanıcı tanımlı değer türleri hakkında daha fazla bilgi için bkz. [sınıfları ve yapıları](classes-and-structs-cpp-component-extensions.md).

    ```cpp
    value struct V {};

    int main() {
    System::Console::WriteLine(__is_value_class(V));
    }
    ```

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

`__has_finalizer(` *Türü* `)` türü niteliğine bu platform sonlandırıcılar desteklemediğinden desteklenmiyor.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

(Bu özelliğin platforma özel açıklaması yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

**Örnek**

Aşağıdaki kod örneği için bir derleme türü niteliğine kullanıma sunmak için bir sınıf şablonu kullanmayı gösterir. bir `/clr` derleme. Daha fazla bilgi için [Windows çalışma zamanı ve yönetilen şablonlar](windows-runtime-and-managed-templates-cpp-component-extensions.md).

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