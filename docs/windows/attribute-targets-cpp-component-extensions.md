---
title: "Öznitelik hedefleri (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- custom attributes, targets
ms.assetid: b4e6e224-da77-4520-b6e6-b96846e0ebc1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bdf54706673a3679582b93448f420d4a63680dee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="attribute-targets-c-component-extensions"></a>Öznitelik Hedefleri (C++ Bileşen Uzantıları)
Öznitelik kullanım tanımlayıcıları öznitelik hedefleri belirtmenizi sağlar.  Her öznitelik belirli dil öğelerine uygulamak için tanımlanır. Örneğin, bir öznitelik yalnızca sınıflar ve yapılar uygulamak için tanımlanabilir.  Aşağıdaki liste, özel bir öznitelik kullanılabilmesi için olası söz dizimi öğeleri gösterir. Bu değerleri birleşimlerini (mantıksal kullanarak veya) kullanılabilir.  
  
 Bir veya daha fazla geçirmek için öznitelik hedef belirtmek için <xref:System.AttributeTargets> numaralandırmalar için <xref:System.AttributeUsageAttribute> öznitelik tanımlarken.  
  
 Geçerli öznitelik hedefleri listesi aşağıdadır:  
  
-   `All`(tüm yapıları için geçerlidir)  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::All)]  
    ref class Attr : public Attribute {};  
  
    [assembly:Attr];  
  
    ```  
  
-   `Assembly`(derleme bir bütün olarak uygulanır)  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Assembly)]  
    ref class Attr : public Attribute {};  
  
    [assembly:Attr];  
  
    ```  
  
-   `Module`(bir modül için bir bütün olarak uygulanır)  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Module)]  
    ref class Attr : public Attribute {};  
  
    [module:Attr];  
  
    ```  
  
-   `Class`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Class)]  
    ref class Attr : public System::Attribute {};  
  
    [Attr]   // same as [class:Attr]  
    ref class MyClass {};  
  
    ```  
  
-   `Struct`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Struct)]  
    ref class Attr : public Attribute {};  
  
    [Attr]   // same as [struct:Attr]  
    value struct MyStruct{};  
  
    ```  
  
-   `enum`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Enum)]  
    ref class Attr : public Attribute {};  
  
    [Attr]   // same as [enum:Attr]  
    enum struct MyEnum{e, d};  
  
    ```  
  
-   `Constructor`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Constructor)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] MyStruct(){}   // same as [constructor:Attr]  
    };  
  
    ```  
  
-   `Method`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Method)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] void Test(){}   // same as [method:Attr]  
    };  
  
    ```  
  
-   `Property`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Property)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] property int Test;   // same as [property:Attr]  
    };  
  
    ```  
  
-   `Field`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Field)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] int Test;   // same as [field:Attr]  
    };  
  
    ```  
  
-   `Event`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Event)]  
    ref class Attr : public Attribute {};  
  
    delegate void ClickEventHandler(int, double);  
  
    ref struct MyStruct{  
    [Attr] event ClickEventHandler^ OnClick;   // same as [event:Attr]  
    };  
  
    ```  
  
-   `Interface`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Interface)]  
    ref class Attr : public Attribute {};  
  
    [Attr]   // same as [event:Attr]  
    interface struct MyStruct{};  
  
    ```  
  
-   `Parameter`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Parameter)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    void Test([Attr] int i);  
    void Test2([parameter:Attr] int i);  
    };  
  
    ```  
  
-   `Delegate`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Delegate)]  
    ref class Attr : public Attribute {};  
  
    [Attr] delegate void Test();  
    [delegate:Attr] delegate void Test2();  
  
    ```  
  
-   `ReturnValue`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::ReturnValue)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct {  
    // Note required specifier  
    [returnvalue:Attr] int Test() { return 0; }  
    };  
  
    ```  
  
 Genellikle, bir öznitelik doğrudan geçerli olduğu language öğesi önce gelir. Bazı durumlarda, ancak özniteliğin konumunu özniteliğin hedef belirlemek yeterli değil. Bu örneği göz önünde bulundurun:  
  
```  
[Attr] int MyFn(double x)...  
```  
  
 Sözdizimsel olarak, öznitelik yöntemi veya yöntemin dönüş değeri uygulamak için tasarlanmıştır olmadığını bildirmek için bir yolu yoktur (Bu durumda, bu yönteme varsayılan olarak). Böyle durumlarda, bir öznitelik kullanım belirticisi kullanılabilir. Örneğin, dönüş değeri için geçerli özniteliği yapmak için kullanın `returnvalue` şekilde tanımlayıcısı:  
  
```  
[returnvalue:Attr] int MyFn(double x)... // applies to return value  
```  
  
 Öznitelik kullanım tanımlayıcıları aşağıdaki durumlarda gereklidir:  
  
-   Bir derleme veya modül düzeyi özniteliği belirtmek için.  
  
-   Öznitelik bir yöntemin dönüş değerini, yöntemi geçerli olduğunu belirtmek için:  
  
    ```  
    [method:Attr] int MyFn(double x)...     // Attr applies to method  
    [returnvalue:Attr] int MyFn(double x)...// Attr applies to return value  
    [Attr] int MyFn(double x)...            // default: method  
    ```  
  
-   Bir öznitelik özelliği bir özellik erişimcisi için geçerli olduğunu belirtmek için:  
  
    ```  
    [method:MyAttr(123)] property int Property()    
    [property:MyAttr(123)] property int Property()  
    [MyAttr(123)] property int get_MyPropy() // default: property  
    ```  
  
-   Bir öznitelik olay olay erişimcisi için geçerli olduğunu belirtmek için:  
  
    ```  
    delegate void MyDel();  
    ref struct X {  
       [field:MyAttr(123)] event MyDel* MyEvent;   //field  
       [event:MyAttr(123)] event MyDel* MyEvent;   //event  
       [MyAttr(123)] event MyDel* MyEvent;   // default: event  
    }  
    ```  
  
 Bir öznitelik kullanım belirticisi hemen aşağıdaki öznitelik uygulanır; Yani  
  
```  
[returnvalue:Attr1, Attr2]  
```  
  
 farklıdır  
  
```  
[returnvalue:Attr1, returnvalue:Attr2]  
```  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Bu örnek, birden çok hedefi belirtin gösterilmektedir.  
  
### <a name="code"></a>Kod  
  
```  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı tanımlı öznitelikler](../windows/user-defined-attributes-cpp-component-extensions.md)