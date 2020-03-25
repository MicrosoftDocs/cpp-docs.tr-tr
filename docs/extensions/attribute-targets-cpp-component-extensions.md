---
title: Öznitelik hedefleri (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- custom attributes, targets
ms.assetid: b4e6e224-da77-4520-b6e6-b96846e0ebc1
ms.openlocfilehash: fe2c1d27042b51300d01ba70b951b7601d87701e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172626"
---
# <a name="attribute-targets-ccli-and-ccx"></a>Öznitelik hedefleri (C++/CLI ve C++/CX)

Öznitelik kullanım belirticileri, öznitelik hedeflerini belirtmenizi sağlar.  Her öznitelik belirli dil öğelerine uygulamak için tanımlanır. Örneğin, bir öznitelik yalnızca sınıflar ve yapılar için uygulanacak şekilde tanımlanabilir.  Aşağıdaki liste, özel bir özniteliğin kullanılabileceği olası sözdizimsel öğeleri gösterir. Bu değerlerin birleşimleri (mantıksal OR kullanılarak) kullanılabilir.

Öznitelik hedefini belirtmek için, özniteliği tanımlarken bir veya daha fazla <xref:System.AttributeTargets> numaralandırıcıyı <xref:System.AttributeUsageAttribute> geçirin.

Geçerli öznitelik hedeflerinin listesi aşağıda verilmiştir:

- `All` (tüm yapılar için geçerlidir)

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::All)]
    ref class Attr : public Attribute {};

    [assembly:Attr];
    ```

- `Assembly` (bir derleme için bir bütün olarak geçerlidir)

    ```cpp
    using namespace System;
    [AttributeUsage(AttributeTargets::Assembly)]
    ref class Attr : public Attribute {};

    [assembly:Attr];
    ```

- `Module` (bir modül için bir bütün olarak geçerlidir)

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

Genellikle, bir öznitelik, uygulandığı dil öğesinden hemen önce gelir. Ancak bazı durumlarda, bir özniteliğin konumu özniteliğin hedeflenen hedefini belirlemede yeterli değildir. Şu örneği göz önünde bulundurun:

```cpp
[Attr] int MyFn(double x)...
```

Sözdizimsel olarak, özniteliğin yönteme veya metodun dönüş değerine uygulanması amaçlandığını söylemek için bir yol yoktur (Bu durumda, varsayılan olarak yöntemine ayarlanır). Böyle durumlarda, bir öznitelik kullanım belirleyicisi kullanılabilir. Örneğin, özniteliği dönüş değeri için uygulanabilir yapmak için, `returnvalue` belirticisini aşağıdaki gibi kullanın:

```cpp
[returnvalue:Attr] int MyFn(double x)... // applies to return value
```

Aşağıdaki durumlarda öznitelik kullanım belirticileri gereklidir:

- Bütünleştirilmiş kod veya modül düzeyi bir öznitelik belirtmek için.

- Bir özniteliğin yöntemin dönüş değerine uygulanacağını belirtmek için, yöntemi değil:

    ```cpp
    [method:Attr] int MyFn(double x)...     // Attr applies to method
    [returnvalue:Attr] int MyFn(double x)...// Attr applies to return value
    [Attr] int MyFn(double x)...            // default: method
    ```

- Bir özniteliğin özelliği değil, özelliğin erişimcisine uygulanacağını belirtmek için:

    ```cpp
    [method:MyAttr(123)] property int Property()
    [property:MyAttr(123)] property int Property()
    [MyAttr(123)] property int get_MyPropy() // default: property
    ```

- Bir özniteliğin olaya değil, bir olayın erişimcisine uygulanacağını belirtmek için:

    ```cpp
    delegate void MyDel();
    ref struct X {
       [field:MyAttr(123)] event MyDel* MyEvent;   //field
       [event:MyAttr(123)] event MyDel* MyEvent;   //event
       [MyAttr(123)] event MyDel* MyEvent;   // default: event
    }
    ```

Öznitelik kullanım belirticisi yalnızca hemen takip eden özniteliği için geçerlidir; Yani

```cpp
[returnvalue:Attr1, Attr2]
```

farklı

```cpp
[returnvalue:Attr1, returnvalue:Attr2]
```

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Bu örnek, birden çok hedefin nasıl belirtilmeyeceğini gösterir.

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
