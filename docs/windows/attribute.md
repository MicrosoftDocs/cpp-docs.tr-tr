---
title: öznitelik | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.attribute
dev_langs:
- C++
helpviewer_keywords:
- __typeof keyword
- custom attributes, creating
- attribute attribute
- attributes [C++], custom
ms.assetid: 8cb3489f-65c4-44ea-b0aa-3c3c6b15741d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 69ec1c9e1b3e30e68bf7199f7a70cb7d329ee040
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603647"
---
# <a name="attribute"></a>özniteliği

Özel bir öznitelik oluşturmanıza olanak sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ attribute(
   AllowOn,
   AllowMultiple=boolean,
   Inherited=boolean
) ]
```

### <a name="parameters"></a>Parametreler

*AllowOn*  
Özel öznitelik uygulanabilir dil öğelerini belirtir. Varsayılan değer `System::AttributeTargets::All` (bkz [System::AttributeTargets](https://msdn.microsoft.com/library/system.attributetargets.aspx)).

*AttributeUsage*  
Özel öznitelik için bir yapı art arda uygulanabilir olup olmadığını belirtir. FALSE varsayılan değerdir.

*Devralınan*  
Öznitelik alt sınıflar tarafından devralınmaz olup olmadığını gösterir. Derleyici, bu işlev için hiçbir özel destek sağlar; öznitelik tüketici iş (`Reflection`, örneğin) bu bilgileri uygular. Varsa *devralınan* doğru ise, öznitelik devralınır. Varsa *AttributeUsage* doğru ise, öznitelik ise türetilen üyesinde; birikir *AttributeUsage* yanlış, öznitelik geçersiz kılma (Değiştir Devralmada veya). Varsa *devralınan* yanlış, öznitelik devralınmaz. Varsayılan değer True'dur.

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> **Özniteliği** özniteliği artık kullanım dışı.  Ortak dil çalışma zamanı özniteliğini kullan `System.Attribute` için doğrudan kullanıcı tanımlı attirbutes oluşturmak için. Daha fazla bilgi için [kullanıcı tanımlı öznitelikler](../windows/user-defined-attributes-cpp-component-extensions.md).

Tanımladığınız bir [özel öznitelik](../windows/custom-attributes-cpp.md) yerleştirerek **özniteliği** yönetilen bir sınıf veya yapı tanımı özniteliği. Sınıf özel öznitelik adıdır. Örneğin:

```cpp
[ attribute(Parameter) ]
public ref class MyAttr {};
```

adlı bir öznitelik tanımlar `MyAttr` işlev parametreleri için uygulanabilir. Sınıfı, öznitelik diğer derlemelerde kullanılacak yayınlanıyorsa ortak olmalıdır.

> [!NOTE]
> Ad çakışmalarını önlemek için tüm öznitelik adları örtük olarak "Özniteliği"; ile bitmelidir Bu örnekte, sınıf ve öznitelik adı gerçekte olduğu `MyAttrAttribute`, ancak `MyAttr` ve `MyAttrAttribute` birbirlerinin yerine kullanılabilir.

Sınıfın genel oluşturucular özniteliğin adlandırılmamış parametreleri tanımlayın. Aşağıdaki şekilde özel bir öznitelik tanımlandığı şekilde öznitelik belirtmemeye birçok yolu aşırı yüklü oluşturucular sağlar:

```cpp
// cpp_attr_ref_attribute.cpp
// compile with: /c /clr
using namespace System;
[ attribute(AttributeTargets::Class) ]   // apply attribute to classes
public ref class MyAttr {
public:
   MyAttr() {}   // Constructor with no parameters
   MyAttr(int arg1) {}   // Constructor with one parameter
};

[MyAttr]
ref class ClassA {};   // Attribute with no parameters

[MyAttr(123)]
ref class ClassB {};   // Attribute with one parameter
```

Sınıfın ortak veri üyeleri ve özellikleri özniteliğin isteğe bağlı adlandırılmış parametreler şunlardır:

```cpp
// cpp_attr_ref_attribute_2.cpp
// compile with: /c /clr
using namespace System;
[ attribute(AttributeTargets::Class) ]
ref class MyAttr {
public:
   // Property Priority becomes attribute's named parameter Priority
    property int Priority {
       void set(int value) {}
       int get() { return 0;}
   }
   // Data member Version becomes attribute's named parameter Version
   int Version;
   MyAttr() {}   // constructor with no parameters
   MyAttr(int arg1) {}   // constructor with one parameter
};

[MyAttr(123, Version=2)]
ref class ClassC {};
```

Olası öznitelik parametre türleri listesi için bkz. [özel öznitelikler](../windows/custom-attributes-cpp.md).

Bkz: [kullanıcı tanımlı öznitelikler](../windows/user-defined-attributes-cpp-component-extensions.md) öznitelik hedefleri hakkındaki bir tartışmaya.

**Özniteliği** özniteliğine sahip bir *AttributeUsage* özel özniteliği tek kullanılıp kullanılmadığını belirten bir parametre veya multiuse (görünebilir birden çok kez aynı varlığa).

```cpp
// cpp_attr_ref_attribute_3.cpp
// compile with: /c /clr
using namespace System;
[ attribute(AttributeTargets::Class, AllowMultiple = true) ]
ref struct MyAttr {
   MyAttr(){}
};   // MyAttr is a multiuse attribute

[MyAttr, MyAttr()]
ref class ClassA {};
```

Özel öznitelik sınıfları türetilir doğrudan veya dolaylı olarak <xref:System.ComponentModel.AttributeCollection.%23ctor%2A>, hızlı ve kolay meta veri özniteliği tanımlarını tanımlayan hale getirir. **Özniteliği** özniteliği gelir içinden devralma `System::Attribute`, açık türetme gerekli değildir:

```cpp
[ attribute(Class) ]
ref class MyAttr
```

eşdeğerdir

```cpp
[ attribute(Class) ]
ref class MyAttr : System::Attribute   // OK, but redundant.
```

**öznitelik** için bir diğer addır <xref:System.AttributeUsageAttribute?displayProperty=fullName> (değil AttributeAttribute; özniteliği adlandırma kuralı için bir özel durum budur).

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**başvuru sınıfı**, **ref struct**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_attribute_4.cpp
// compile with: /c /clr
using namespace System;
[attribute(AttributeTargets::Class)]
ref struct ABC {
   ABC(Type ^) {}
};

[ABC(String::typeid)]   // typeid operator yields System::Type ^
ref class MyClass {};
```

## <a name="example"></a>Örnek

`Inherited` Adlandırılmış bağımsız değişken, bir taban sınıfa uygulanan özel bir öznitelik türetilmiş bir sınıfın yansıma görünür olup olmadığını belirtir.

```cpp
// cpp_attr_ref_attribute_5.cpp
// compile with: /clr
using namespace System;
using namespace System::Reflection;

[attribute( AttributeTargets::Method, Inherited=false )]
ref class BaseOnlyAttribute { };

[attribute( AttributeTargets::Method, Inherited=true )]
ref class DerivedTooAttribute { };

ref struct IBase {
public:
   [BaseOnly, DerivedToo]
   virtual void meth() {}
};

// Reflection on Derived::meth will show DerivedTooAttribute
// but not BaseOnlyAttribute.
ref class Derived : public IBase {
public:
   virtual void meth() override {}
};

int main() {
   IBase ^ pIB = gcnew Derived;

   MemberInfo ^ pMI = pIB->GetType( )->GetMethod( "meth" );
   array<Object ^> ^ pObjs = pMI->GetCustomAttributes( true );
   Console::WriteLine( pObjs->Length ) ;
}
```

```Output
2
```

## <a name="see-also"></a>Ayrıca Bkz.

[Öznitelikler Alfabetik Başvurusu](../windows/attributes-alphabetical-reference.md)  
[Özel öznitelikler](http://msdn.microsoft.com/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)