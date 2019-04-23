---
title: Kullanıcı tanımlı öznitelikler (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- metadata, extending
- custom attributes, extending metadata
ms.assetid: 98b29048-a3ea-4698-8441-f149cdaec9fb
ms.openlocfilehash: 6d200c36946e7bc7d441c2c4db1bdfe96d4aeef9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041302"
---
# <a name="user-defined-attributes--ccli-and-ccx"></a>Kullanıcı tanımlı öznitelikler (C++/CLI ve C++/CX)

C++/ CLI ve C++/CX bir arabirimi, sınıf veya yapı, yöntemi, parametre veya sabit listesi meta verileri genişletme platforma özel öznitelikler oluşturmak etkinleştirin. Bu öznitelikler kodundan [standart C++ öznitelikleri](../cpp/attributes.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

C + uygulayabileceğiniz +/ CX öznitelikleri özellikleri, ancak oluşturucular veya yöntemleri.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

İçinde sunulan bilgileri değiştirmek için bu konuda gösterilen sözdizimi ve bilgi yöneliktir [özniteliği](../windows/attributes/attribute.md).

Özel bir öznitelik türü tanımlama ve yaparak tanımlayabilirsiniz <xref:System.Attribute> bir temel sınıf türü için ve isteğe bağlı olarak uygulama <xref:System.AttributeUsageAttribute> özniteliği.

Daha fazla bilgi için bkz.:

- [Öznitelik Hedefleri](attribute-targets-cpp-component-extensions.md)

- [Öznitelik Parametre Türleri](attribute-parameter-types-cpp-component-extensions.md)

Görselde derlemeleri imzalama hakkında daha fazla bilgi için C++, bkz: [tanımlayıcı ad derlemeleri (derleme imzalama) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

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

Bkz: [TypeID](typeid-cpp-component-extensions.md) özel öznitelik bloğundan System::Type değerini döndürmek hakkında bilgi için.

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

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)