---
description: ': TypeId hakkında daha fazla bilgi edinin (C++/CLı ve C++/CX)'
title: typeid (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- typeid keyword [C++]
ms.assetid: e9706cae-e7c4-4d6d-b474-646d73df3e70
ms.openlocfilehash: 0452de57b93eb5d55bed34fc1f9745280a6b6184
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185667"
---
# <a name="typeid--ccli-and-ccx"></a>typeid (C++/CLI ve C++/CX)

Bir nesnenin türünü gösteren bir değer alır.

> [!NOTE]
> Bu konu, typeid 'nin C++ Bileşen Uzantıları sürümüne başvurur. Bu anahtar sözcüğünün ISO C++ sürümü için bkz. [TypeId işleci](../cpp/typeid-operator.md).

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="syntax"></a>Sözdizimi

```cpp
T::typeid
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Bir tür adı.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="syntax"></a>Sözdizimi

```cpp
Platform::Type^ type = T::typeid;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Bir tür adı.

### <a name="remarks"></a>Açıklamalar

C++/CX ' te TypeId, çalışma zamanı türü bilgilerden oluşturulan [Platform:: Type](../cppcx/platform-type-class.md) öğesini döndürür.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="syntax"></a>Sözdizimi

```
type::typeid
```

### <a name="parameters"></a>Parametreler

*türüyle*<br/>
Nesnesini istediğiniz bir türün (soyut bildirimci) adı `System::Type` .

### <a name="remarks"></a>Açıklamalar

**`typeid`** , <xref:System.Type> derleme zamanında bir türü almak için kullanılır.

**`typeid`** , `System::Type` veya kullanarak çalışma zamanında bir türü almaya benzer <xref:System.Type.GetType%2A> <xref:System.Object.GetType%2A> . Ancak, **`typeid`** bir tür adını yalnızca parametre olarak kabul eder.  Adını almak için bir türün bir örneğini kullanmak istiyorsanız `System::Type` kullanın `GetType` .

**`typeid`** derleme zamanında bir tür adı (türü) değerlendirebilmelidir, ancak GetType türü çalışma zamanında döndürülecek şekilde değerlendirir.

**`typeid`** Yerel tür adı için yerel bir tür adı veya ortak dil çalışma zamanı diğer adı alabilir; daha fazla bilgi için bkz. [C++ yerel türlerine .NET Framework eşdeğerleri (c++/CLI)](../dotnet/managed-types-cpp-cli.md#dotnet) .

**`typeid`** Yerel türlerle de çalışır, ancak yine de döndürür `System::Type` .  Type_info yapısını almak için [ `typeid` işleci](../cpp/typeid-operator.md)kullanın.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek, TypeId anahtar sözcüğünü üye ile karşılaştırır `GetType()` .

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

Aşağıdaki örnek, bir tür üzerinde öznitelikleri almak için System:: Type türünde bir değişkenin kullanılabileceğini gösterir.  Ayrıca, bazı türler için kullanmak üzere bir typedef oluşturmanız gerektiğini gösterir **`typeid`** .

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
