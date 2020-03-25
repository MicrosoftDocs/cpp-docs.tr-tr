---
title: TypeId (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- typeid keyword [C++]
ms.assetid: e9706cae-e7c4-4d6d-b474-646d73df3e70
ms.openlocfilehash: 8b22481fecb4b7de5106921fec1c3a43fab81a48
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181752"
---
# <a name="typeid--ccli-and-ccx"></a>TypeId (C++/CLI ve C++/CX)

Bir nesnenin türünü gösteren bir değer alır.

> [!NOTE]
> Bu konu, C++ typeid 'Nin bileşen uzantıları sürümüne başvurur. Bu anahtar sözcüğünün C++ ISO sürümü için bkz. [TypeId işleci](../cpp/typeid-operator.md).

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="syntax"></a>Sözdizimi

```cpp
T::typeid
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Bir tür adı.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="syntax"></a>Sözdizimi

```cpp
Platform::Type^ type = T::typeid;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Bir tür adı.

### <a name="remarks"></a>Açıklamalar

/CX C++içinde TypeId, çalışma zamanı türü bilgilerden oluşturulan bir [Platform:: Type](../cppcx/platform-type-class.md) döndürür.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="syntax"></a>Sözdizimi

```
type::typeid
```

### <a name="parameters"></a>Parametreler

*type*<br/>
`System::Type` nesnesini istediğiniz bir türün (soyut bildirimci) adı.

### <a name="remarks"></a>Açıklamalar

`typeid`, derleme zamanında bir tür için <xref:System.Type> almak için kullanılır.

`typeid`, <xref:System.Type.GetType%2A> veya <xref:System.Object.GetType%2A>kullanarak çalışma zamanında bir tür için System:: Type almaya benzer. Ancak TypeId yalnızca bir parametre olarak bir tür adı kabul eder.  Sistem:: tür adını almak için bir türün örneğini kullanmak istiyorsanız, GetType kullanın.

`typeid`, derleme zamanında bir tür adı değerlendirebilmelidir, ancak GetType türü çalışma zamanında döndürülecek şekilde değerlendirir.

`typeid` yerel tür adı için yerel bir tür adı veya ortak dil çalışma zamanı diğer adı alabilir; daha fazla bilgi için bkz. [ C++ yerelC++türlere .NET Framework eşdeğerleri (/CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md) .

`typeid`, yerel türlerle de çalışır, ancak yine de bir System:: Type döndürür.  Type_info yapısı almak için [TypeId işleci](../cpp/typeid-operator.md)kullanın.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek, TypeId anahtar sözcüğünü `GetType()` üyesine karşılaştırır.

```cpp
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

```Output
typeid and GetType returned the same System::Type
G

System.Single*
```

Aşağıdaki örnek, bir tür üzerinde öznitelikleri almak için System:: Type türünde bir değişkenin kullanılabileceğini gösterir.  Ayrıca, bazı türler için `typeid`kullanmak için bir typedef oluşturmanız gerektiğini gösterir.

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)
