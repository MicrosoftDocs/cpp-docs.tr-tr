---
title: Öznitelik hedefleri (C + +/ CLI ve C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- custom attributes, targets
ms.assetid: b4e6e224-da77-4520-b6e6-b96846e0ebc1
ms.openlocfilehash: 502f5ba2e5bbb5bd5a5fcceca16acaa3987db4bc
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026684"
---
# <a name="attribute-targets-ccli-and-ccx"></a>Öznitelik hedefleri (C + +/ CLI ve C + +/ CX)

Öznitelik kullanımı tanımlayıcıları öznitelik hedefleri belirtmenizi sağlar.  Her öznitelik için belirli dil öğelerini uygulamak için tanımlanır. Örneğin, yalnızca sınıflar ve yapılar için uygulanacak bir öznitelik tanımlanabilir.  Aşağıdaki liste, özel bir öznitelik kullanılabilir olası söz dizimi öğeleri gösterir. Bu değerleri birleşimlerini (kullanarak mantıksal veya) kullanılabilir.

Öznitelik hedefi, bir veya daha fazla geçirilecek belirtmek için <xref:System.AttributeTargets> numaralandırıcılar için <xref:System.AttributeUsageAttribute> öznitelik tanımlarken.

Geçerli bir öznitelik hedefleri listesi verilmiştir:

- `All` (tüm yapıları için geçerlidir)

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::All)]
    ref class Attr : public Attribute {};

    [assembly:Attr];
    ```

- `Assembly` (derleme bir bütün olarak geçerlidir)

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Assembly)]
    ref class Attr : public Attribute {};

    [assembly:Attr];
    ```

- `Module` (bir modül için bir bütün olarak uygular)

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Module)]
    ref class Attr : public Attribute {};

    [module:Attr];
    ```

- `Class`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Class)]
    ref class Attr : public System::Attribute {};

    [Attr]   // same as [class:Attr]
    ref class MyClass {};
    ```

- `Struct`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Struct)]
    ref class Attr : public Attribute {};

    [Attr]   // same as [struct:Attr]
    value struct MyStruct{};
    ```

- `enum`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Enum)]
    ref class Attr : public Attribute {};

    [Attr]   // same as [enum:Attr]
    enum struct MyEnum{e, d};
    ```

- `Constructor`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Constructor)]
    ref class Attr : public Attribute {};

    ref struct MyStruct{
    [Attr] MyStruct(){}   // same as [constructor:Attr]
    };
    ```

- `Method`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Method)]
    ref class Attr : public Attribute {};

    ref struct MyStruct{
    [Attr] void Test(){}   // same as [method:Attr]
    };
    ```

- `Property`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Property)]
    ref class Attr : public Attribute {};

    ref struct MyStruct{
    [Attr] property int Test;   // same as [property:Attr]
    };
    ```

- `Field`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Field)]
    ref class Attr : public Attribute {};

    ref struct MyStruct{
    [Attr] int Test;   // same as [field:Attr]
    };
    ```

- `Event`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Event)]
    ref class Attr : public Attribute {};

    delegate void ClickEventHandler(int, double);

    ref struct MyStruct{
    [Attr] event ClickEventHandler^ OnClick;   // same as [event:Attr]
    };
    ```

- `Interface`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Interface)]
    ref class Attr : public Attribute {};

    [Attr]   // same as [event:Attr]
    interface struct MyStruct{};
    ```

- `Parameter`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Parameter)]
    ref class Attr : public Attribute {};

    ref struct MyStruct{
    void Test([Attr] int i);
    void Test2([parameter:Attr] int i);
    };
    ```

- `Delegate`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Delegate)]
    ref class Attr : public Attribute {};

    [Attr] delegate void Test();
    [delegate:Attr] delegate void Test2();
    ```

- `ReturnValue`

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::ReturnValue)]
    ref class Attr : public Attribute {};

    ref struct MyStruct {
    // Note required specifier
    [returnvalue:Attr] int Test() { return 0; }
    };
    ```

Genellikle, bir öznitelik doğrudan uygulandığı dil öğesi önce gelir. Bazı durumlarda, ancak bir öznitelik konumu özniteliğin hedef belirlemek yeterli değil. Bu örneği göz önünde bulundurun:

```cpp
[Attr] int MyFn(double x)...
```

Sözdizimi, öznitelik yönteme ve yöntemin dönüş değerini uygulamak için tasarlanmıştır, anlaşılır bir yolu yoktur (Bu durumda, yönteme Varsayılanları). Bu gibi durumlarda, bir öznitelik kullanım tanımlayıcısı kullanılabilir. Örneğin, dönüş değeri için geçerli öznitelik yapmak için kullanın `returnvalue` aşağıdaki gibi belirticisi:

```cpp
[returnvalue:Attr] int MyFn(double x)... // applies to return value
```

Öznitelik kullanımı tanımlayıcıları aşağıdaki durumlarda gereklidir:

- Bir derleme veya modül düzeyi özniteliğini belirtmek için.

- Bir öznitelik, bir yöntemin dönüş değeri için yöntem geçerli olduğunu belirtmek için:

    ```cpp
    [method:Attr] int MyFn(double x)...     // Attr applies to method
    [returnvalue:Attr] int MyFn(double x)...// Attr applies to return value
    [Attr] int MyFn(double x)...            // default: method
    ```

- Öznitelik bir özelliğin erişimci özelliği için geçerli olduğunu belirtmek için:

    ```cpp
    [method:MyAttr(123)] property int Property()
    [property:MyAttr(123)] property int Property()
    [MyAttr(123)] property int get_MyPropy() // default: property
    ```

- Bir öznitelik olay olay erişimcisi için geçerli olduğunu belirtmek için:

    ```cpp
    delegate void MyDel();
    ref struct X {
       [field:MyAttr(123)] event MyDel* MyEvent;   //field
       [event:MyAttr(123)] event MyDel* MyEvent;   //event
       [MyAttr(123)] event MyDel* MyEvent;   // default: event
    }
    ```

Hemen takip eden özniteliği bir öznitelik kullanım belirticisi geçerlidir; Yani

```cpp
[returnvalue:Attr1, Attr2]
```

farklıdır

```cpp
[returnvalue:Attr1, returnvalue:Attr2]
```

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Bu örnek, birden çok hedef belirtmek gösterilmektedir.

### <a name="code"></a>Kod

```cpp
using namespace System;
[AttributeUsage(AttributeTargets::Class | AttributeTargets::Struct, AllowMultiple = true )]
ref struct Attr : public Attribute {
   Attr(bool i){}
   Attr(){}
};

[Attr]
ref class MyClass {};

[Attr]
[Attr(true)]
value struct MyStruct {};
```

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı Tanımlı Öznitelikler](user-defined-attributes-cpp-component-extensions.md)