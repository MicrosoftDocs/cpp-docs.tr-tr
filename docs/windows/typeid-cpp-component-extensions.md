---
title: TypeId (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- typeid keyword [C++]
ms.assetid: e9706cae-e7c4-4d6d-b474-646d73df3e70
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db1efac0a38aaa11238452e418277f78dbcd6d9d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888373"
---
# <a name="typeid--c-component-extensions"></a>typeid (C++ Bileşen Uzantıları)
Bir nesne türünü belirten bir değer alır.  
  
> [!WARNING]
>  Bu konuda TypeID C++ bileşen uzantıları sürümüne başvuruyor. Bu anahtar sözcük ISO C++ sürümü için bkz: [typeid işleci](../cpp/typeid-operator.md).  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
T::typeid  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Tür adı.  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
Platform::Type^ type = T::typeid;  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Tür adı.  
  
### <a name="remarks"></a>Açıklamalar  
 C + +/ CX, TypeID döndüren bir [Platform::Type](../cppcx/platform-type-class.md) çalışma zamanı tür bilgilerini yapılandırılmıştır.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Sözdizimi**  
  
```  
  
type::typeid  
```  
  
 **Parametreler**  
  
 *Türü*  
 System::Type nesne istediğiniz bir türü (soyut bildirimcisi) adı.  
  
 **Açıklamalar**  
  
 `typeid` almak için kullanılan <xref:System.Type> derleme zamanında bir tür için.  
  
 `typeid` çalışma zamanı kullanarak bir tür için System::Type alma için benzer <xref:System.Type.GetType%2A> veya <xref:System.Object.GetType%2A>. Ancak, TypeID yalnızca bir tür adı bir parametre olarak kabul eder.  GetType System::Type adını almak için bir türünün bir örneği kullanmak istiyorsanız kullanın.  
  
 `typeid` GetType çalışma zamanında döndürülecek tür değerlendirir ancak derleme zamanında tür adı (tür) değerlendirebilir olmalıdır.  
  
 `typeid` yerel tür adı veya yerel tür adı için ortak dil çalışma zamanı diğer adı alabilir; bkz: [C++ yerel türlerinin .NET Framework eşdeğerleri (C + +/ CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md) daha fazla bilgi için.  
  
 `typeid` Ayrıca bir System::Type hala döndürülecek rağmen yerel türleri ile çalışır.  Type_info yapısı almak için [typeid işleci](../cpp/typeid-operator.md).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki örnek GetType() üyesine typeid anahtar sözcüğü karşılaştırır.  
  
```  
// keyword__typeid.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   Type ^ pType = pG->GetType();  
   Type ^ pType2 = G::typeid;  
  
   if (pType == pType2)  
      Console::WriteLine("typeid and GetType returned the same System::Type");  
   Console::WriteLine(G::typeid);  
  
   typedef float* FloatPtr;  
   Console::WriteLine(FloatPtr::typeid);  
}  
```  
  
 **Output**  
  
```Output  
typeid and GetType returned the same System::Type  
G  
  
System.Single*  
  
```  
  
 **Örnek**  
  
 Aşağıdaki örnek System::Type bir türde öznitelikleri almak için kullanılan türünde bir değişken gösterir.  Ayrıca bazı türleri için kullanmak için bir typedef oluşturmak zorunda kalacaksınız olduğunu gösterir `typeid`.  
  
```  
// keyword__typeid_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Security;  
using namespace System::Security::Permissions;  
  
typedef int ^ handle_to_int;  
typedef int * pointer_to_int;  
  
public ref class MyClass {};  
  
class MyClass2 {};  
  
[attribute(AttributeTargets::All)]  
ref class AtClass {  
public:  
   AtClass(Type ^) {  
      Console::WriteLine("in AtClass Type ^ constructor");  
   }  
};  
  
[attribute(AttributeTargets::All)]  
ref class AtClass2 {  
public:  
   AtClass2() {  
      Console::WriteLine("in AtClass2 constructor");  
   }  
};  
  
// Apply the AtClass and AtClass2 attributes to class B  
[AtClass(MyClass::typeid), AtClass2]     
[AttributeUsage(AttributeTargets::All)]  
ref class B : Attribute {};  
  
int main() {  
   Type ^ MyType = B::typeid;  
  
   Console::WriteLine(MyType->IsClass);  
  
   array<Object^>^ MyArray = MyType -> GetCustomAttributes(true);  
   for (int i = 0 ; i < MyArray->Length ; i++ )  
      Console::WriteLine(MyArray[i]);  
  
   if (int::typeid != pointer_to_int::typeid)  
      Console::WriteLine("int::typeid != pointer_to_int::typeid, as expected");  
  
   if (int::typeid == handle_to_int::typeid)  
      Console::WriteLine("int::typeid == handle_to_int::typeid, as expected");  
}  
```  
  
 **Output**  
  
```Output  
True  
  
in AtClass2 constructor  
  
in AtClass Type ^ constructor  
  
AtClass2  
  
System.AttributeUsageAttribute  
  
AtClass  
  
int::typeid != pointer_to_int::typeid, as expected  
  
int::typeid == handle_to_int::typeid, as expected  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)