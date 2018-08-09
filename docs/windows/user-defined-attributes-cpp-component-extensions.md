---
title: Kullanıcı tanımlı öznitelikler (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- metadata, extending
- custom attributes, extending metadata
ms.assetid: 98b29048-a3ea-4698-8441-f149cdaec9fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e09d3c285c64f049cc8e1bb8aea1c5debe88932
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644134"
---
# <a name="user-defined-attributes--c-component-extensions"></a>Kullanıcı Tanımlı Öznitelikler (C++ Bileşen Uzantıları)
Özel öznitelik meta verileri bir arabirimi, sınıf veya yapı, yöntemi, parametre veya sabit listesi genişletmenizi sağlar.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 Tüm çalışma zamanları, özel öznitelikler destekler.  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 C + +/ CX öznitelikleri yalnızca özellikleri destekler, ancak oluşturucular veya yöntemleri öznitelik değil.  
  
### <a name="remarks"></a>Açıklamalar  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: `/ZW`  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı  
 Özel öznitelikler, bir yönetilen öğenin meta verileri genişletme sağlar. Daha fazla bilgi için [öznitelikleri](/dotnet/standard/attributes/index).  
  
### <a name="remarks"></a>Açıklamalar  
 İçinde sunulan bilgileri değiştirmek için bu konuda gösterilen sözdizimi ve bilgi yöneliktir [özniteliği](../windows/attribute.md).  
  
 Özel bir öznitelik türü tanımlama ve yaparak tanımlayabilirsiniz <xref:System.Attribute> bir temel sınıf türü için ve isteğe bağlı olarak uygulama <xref:System.AttributeUsageAttribute> özniteliği.  
  
 Örneğin, içinde Microsoft işlem sunucusu (MTS) 1.0, işlemler, eşitleme ile ilgili davranışı Yük Dengeleme ve benzeri ODL özel özniteliğini kullanarak tür kitaplığına eklenen özel GUID'leri aracılığıyla belirtildi. Bu nedenle, bir istemci bir MTS sunucusunun, tür kitaplığı okuyarak özelliklerini belirleyebilir. .NET Framework tür kitaplığının analog meta verileri ve analog ODL özel özniteliğinin özel öznitelikler. Ayrıca, tür kitaplığı okuma, yansıma türlerini kullanarak benzerdir.  
  
 Daha fazla bilgi için bkz:  
  
-   [Öznitelik hedefleri](../windows/attribute-targets-cpp-component-extensions.md)  
  
-   [Öznitelik parametre türleri](../windows/attribute-parameter-types-cpp-component-extensions.md)  
  
 Visual C++'ta imzalama derlemeler hakkında daha fazla bilgi için bkz. [tanımlayıcı ad derlemeleri (derleme imzalama) (C + +/ CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: `/clr`  
  
### <a name="examples"></a>Örnekler  
  
 Aşağıdaki örnek, özel bir öznitelik tanımlayın işlemi gösterilmektedir.  
  
```cpp  
// user_defined_attributes.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All)]  
ref struct Attr : public Attribute {  
   Attr(bool i){}  
   Attr(){}  
};  
  
[Attr]  
ref class MyClass {};  
```  
  
 Aşağıdaki örnekte, özel öznitelikler önemli özelliklerinden bazıları gösterilmektedir. Örneğin, bu örnek özel özniteliklerin bir ortak kullanımı gösterilmektedir: tam olarak kendini istemcilere açıklamak bir sunucu örneği.  
  
```cpp  
// extending_metadata_b.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
  
public enum class Access { Read, Write, Execute };  
  
// Defining the Job attribute:  
[AttributeUsage(AttributeTargets::Class, AllowMultiple=true )]  
public ref class Job : Attribute {  
public:  
   property int Priority {  
      void set( int value ) { m_Priority = value; }  
      int get() { return m_Priority; }  
   }  
  
   // You can overload constructors to specify Job attribute in different ways  
   Job() { m_Access = Access::Read; }  
   Job( Access a ) { m_Access = a; }  
   Access m_Access;  
  
protected:  
   int m_Priority;  
};  
  
interface struct IService {  
   void Run();  
};  
  
   // Using the Job attribute:  
   // Here we specify that QueryService is to be read only with a priority of 2.  
   // To prevent namespace collisions, all custom attributes implicitly   
   // end with "Attribute".   
  
[Job( Access::Read, Priority=2 )]  
ref struct QueryService : public IService {  
   virtual void Run() {}  
};  
  
// Because we said AllowMultiple=true, we can add multiple attributes   
[Job(Access::Read, Priority=1)]  
[Job(Access::Write, Priority=3)]  
ref struct StatsGenerator : public IService {  
   virtual void Run( ) {}  
};  
  
int main() {  
   IService ^ pIS;  
   QueryService ^ pQS = gcnew QueryService;  
   StatsGenerator ^ pSG = gcnew StatsGenerator;  
  
   //  use QueryService  
   pIS = safe_cast<IService ^>( pQS );  
  
   // use StatsGenerator  
   pIS = safe_cast<IService ^>( pSG );  
  
   // Reflection  
   MemberInfo ^ pMI = pIS->GetType();  
   array <Object ^ > ^ pObjs = pMI->GetCustomAttributes(false);  
  
   // We can now quickly and easily view custom attributes for an   
   // Object through Reflection */  
   for( int i = 0; i < pObjs->Length; i++ ) {  
      Console::Write("Service Priority = ");  
      Console::WriteLine(static_cast<Job^>(pObjs[i])->Priority);  
      Console::Write("Service Access = ");  
      Console::WriteLine(static_cast<Job^>(pObjs[i])->m_Access);  
   }  
}  
```  
  
 **Output**  
  
```Output  
Service Priority = 0  
  
Service Access = Write  
  
Service Priority = 3  
  
Service Access = Write  
  
Service Priority = 1  
  
Service Access = Read  
```  
  
 `Object^` Tür değişken veri türü yerine geçer. Aşağıdaki örnek, bir dizi alan özel bir öznitelik tanımlar `Object^` parametre olarak.  
  
 Öznitelik bağımsız değişkenleri derleme zamanı sabit olması gerekir; Çoğu durumda, bunlar sabit değişmez değerleri olmalıdır.  
  
 Bkz: [TypeID](../windows/typeid-cpp-component-extensions.md) özel öznitelik bloğundan System::Type değerini döndürmek hakkında bilgi için.  
  
```cpp  
// extending_metadata_e.cpp  
// compile with: /clr /c  
using namespace System;  
[AttributeUsage(AttributeTargets::Class | AttributeTargets::Method)]  
public ref class AnotherAttr : public Attribute {  
public:  
   AnotherAttr(array<Object^>^) {}  
   array<Object^>^ var1;  
};  
  
// applying the attribute  
[ AnotherAttr( gcnew array<Object ^> { 3.14159, "pi" }, var1 = gcnew array<Object ^> { "a", "b" } ) ]  
public ref class SomeClass {};  
```  
  
 Çalışma zamanı özel öznitelik sınıfı ortak bölümünü seri hale getirilebilir olması gerekir.  Özel öznitelikler yazma, derleme zamanı sabitleri, özel öznitelik adlandırılmış bağımsız değişkenler sınırlıdır.  (Bunu meta sınıf düzeninizi eklenen BITS öğesinin bir dizisi olarak düşünün.)  
  
```cpp  
// extending_metadata_f.cpp  
// compile with: /clr /c  
using namespace System;  
ref struct abc {};  
  
[AttributeUsage( AttributeTargets::All )]  
ref struct A : Attribute {  
   A( Type^ ) {}  
   A( String ^ ) {}  
   A( int ) {}  
};  
  
[A( abc::typeid )]  
ref struct B {};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)