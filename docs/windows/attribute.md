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
ms.openlocfilehash: 9826b689e2b8a640efe66e8625b97b3cec347acf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862068"
---
# <a name="attribute"></a>özniteliği
Özel bir öznitelik oluşturmanıza olanak sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ attribute(  
   AllowOn,  
   AllowMultiple=boolean,  
   Inherited=boolean  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *AllowOn*  
 Özel öznitelik uygulanabilir dil öğeleri belirtir. Varsayılan değer **System::AttributeTargets::All** (bkz [System::AttributeTargets](https://msdn.microsoft.com/en-us/library/system.attributetargets.aspx)).  
  
 `AllowMultiple`  
 Özel öznitelik için bir yapı art arda uygulanabilir olup olmadığını belirtir. Varsayılan değer **FALSE**.  
  
 `Inherited`  
 Öznitelik alt sınıflar tarafından devralınır olup olmadığını gösterir. Derleyici hiçbir özel destek için bu işlevsellik sağlar; Bu bilgileri dikkate almanız özniteliği tüketicileri (örneğin, yansıma) iş değil. Varsa `Inherited` olan **doğru**, öznitelik devralınır. Varsa `AllowMultiple` olan **TRUE**, öznitelik varsa türetilmiş üyesinde; toplanacaktır `AllowMultiple` olan **FALSE**, öznitelik geçersiz kılma (Değiştir devralma veya). Varsa `Inherited` olan **yanlış**, öznitelik devralınmaz. Varsayılan değer **doğru**.  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  `attribute` Özniteliği artık kullanım dışı.  Ortak dil çalışma zamanı özniteliği System.Attribute'un doğrudan kullanıcı tanımlı attirbutes oluşturmak için kullanın.  Daha fazla bilgi için bkz: [kullanıcı tanımlı öznitelikler](../windows/user-defined-attributes-cpp-component-extensions.md).  
  
 Tanımladığınız bir [özel öznitelik](../windows/custom-attributes-cpp.md) yerleştirerek `attribute` bir yönetilen sınıf veya yapı tanımı özniteliği. Özel öznitelik sınıfı adıdır. Örneğin:  
  
```  
[ attribute(Parameter) ]  
public ref class MyAttr {};  
```  
  
 işlev parametreleri için uygulanabilir MyAttr adlı bir öznitelik tanımlar. Sınıf özniteliği diğer derlemelerde kullanılacak edecekse ortak olmalıdır.  
  
> [!NOTE]
>  Ad çakışmaları önlemek için tüm öznitelik adları dolaylı olarak "Özniteliği ile"; bitiş Bu örnekte, sınıf ve öznitelik gerçekten MyAttrAttribute adıdır, ancak MyAttr ve MyAttrAttribute birbirinin yerine kullanılabilir.  
  
 Sınıfın ortak oluşturucu özniteliğin adlandırılmamış parametrelerini tanımlayın. Aşırı yüklenmiş oluşturucular özel bir öznitelik aşağıdaki şekilde tanımlandığı şekilde öznitelik belirtmemeye birkaç yolu izin ver:  
  
```  
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
  
 Sınıfın genel veri üyelerini ve Özellikler özniteliğin isteğe bağlı adlandırılmış parametreler şunlardır:  
  
```  
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
  
 Olası öznitelik parametre türleri listesi için bkz: [özel öznitelikleri](../windows/custom-attributes-cpp.md).  
  
 Bkz: [kullanıcı tanımlı öznitelikler](../windows/user-defined-attributes-cpp-component-extensions.md) özniteliği hedeflerde bir tartışma için.  
  
 `attribute` Özniteliğine sahip bir `AllowMultiple` özel öznitelik tek kullanılıp kullanılmadığını belirten parametre veya multiuse (görünebilir birden çok kez aynı varlık üzerinde).  
  
```  
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
  
 Özel öznitelik sınıfları türetilir doğrudan veya dolaylı olarak <xref:System.ComponentModel.AttributeCollection.%23ctor%2A>, hızlı ve kolay meta verilerde özniteliği tanımlarını tanımlayan hangi yapar. `attribute` Özniteliği gelir System::Attribute, devralmadan açık türetme gerekli değildir:  
  
```  
[ attribute(Class) ]  
ref class MyAttr  
```  
  
 eşdeğerdir  
  
```  
[ attribute(Class) ]  
ref class MyAttr : System::Attribute   // OK, but redundant.  
```  
  
 `attribute` bir diğer adı için <xref:System.AttributeUsageAttribute?displayProperty=fullName> (değil AttributeAttribute; özniteliği adlandırma kuralı için bir özel durum budur).  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|`ref` **sınıf**, **ref yapısı**|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="example"></a>Örnek  
  
```  
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
 `Inherited` Adlandırılmış bağımsız değişkeni bir temel sınıf üzerinde uygulanan özel bir öznitelik türetilmiş bir sınıf yansıma üzerinde görünür olup olmadığını belirtir.  
  
```  
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
 [Öznitelikler alfabetik başvurusu](../windows/attributes-alphabetical-reference.md)   
 [Özel öznitelikler](http://msdn.microsoft.com/en-us/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)