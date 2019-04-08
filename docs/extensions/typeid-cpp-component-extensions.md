---
title: typeid (C + +/ CLI ve C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- typeid keyword [C++]
ms.assetid: e9706cae-e7c4-4d6d-b474-646d73df3e70
ms.openlocfilehash: ec64388d5f71cff01207129e337cf20bb151db1a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031517"
---
# <a name="typeid--ccli-and-ccx"></a>typeid (C + +/ CLI ve C + +/ CX)

Bir nesne türünü gösteren bir değer alır.

> [!NOTE]
> Bu konuda TypeID C++ bileşen uzantıları sürümünü gösterir. Bu anahtar sözcük ISO C++ sürümü için bkz: [typeid işleci](../cpp/typeid-operator.md).

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="syntax"></a>Sözdizimi

```cpp
T::typeid
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Tür adı.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="syntax"></a>Sözdizimi

```cpp
Platform::Type^ type = T::typeid;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Tür adı.

### <a name="remarks"></a>Açıklamalar

C + +/ CX, typeid döndürür bir [Platform::Type](../cppcx/platform-type-class.md) çalışma zamanı türü bilgileri oluşturulur.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="syntax"></a>Sözdizimi

```
type::typeid
```

### <a name="parameters"></a>Parametreler

* türü*<br/>
İstediğiniz bir türün (soyut bildirimci) adını `System::Type` nesne.

### <a name="remarks"></a>Açıklamalar

`typeid` almak için kullanılan <xref:System.Type> için derleme zamanında bir tür.

`typeid` çalışma zamanı'nı kullanarak bir tür System::Type edinilmesi benzer <xref:System.Type.GetType%2A> veya <xref:System.Object.GetType%2A>. Ancak, typeid yalnızca bir tür adı bir parametre olarak kabul eder.  GetType System::Type adını almak için bir türün bir örneğini kullanmak istiyorsanız, kullanın.

`typeid` GetType çalışma zamanında döndürülecek tür değerlendirir ise, bir tür adı (tür) derleme zamanında değerlendirilmesi mümkün olması gerekir.

`typeid` bir yerel tür adı veya yerel bir tür adı için ortak dil çalışma zamanı diğer adı alabilir; bkz: [C++ yerel türlerinin .NET Framework eşdeğerleri (C + +/ CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md) daha fazla bilgi için.

`typeid` hala bir System::Type döndürür ancak yerel türler ile de çalışır.  Type_info yapısı almak için kullanın [typeid işleci](../cpp/typeid-operator.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek typeid anahtar karşılaştırır `GetType()` üyesi.

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

Aşağıdaki örnek, türü System::Type türe göre öznitelikleri almak için kullanılan bir değişken gösterir.  Ayrıca bazı türleri için kullanmak için bir typedef oluşturmak olacağını gösterir `typeid`.

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

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)