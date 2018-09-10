---
title: Platform::type sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Type::GetTypeCode
- VCCORLIB/Platform::Type::FullName
dev_langs:
- C++
helpviewer_keywords:
- Platform::Type Class
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea0723d1dfa3c278ab385e393cd0f3b0d9f633f0
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44109064"
---
# <a name="platformtype-class"></a>Platform::type sınıfı

Çalışma zamanı türü bilgilerini içerir — özellikle, bir dize adı ve typecode'u işlenemiyor. Çağırılarak [Object::GetType](../cppcx/platform-object-class.md#gettype) herhangi bir nesne üzerinde veya bu adı kullanıyor [TypeID](../windows/typeid-cpp-component-extensions.md) operatörü bir sınıfın veya yapının adı.

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class Platform::Type :
    Platform::Object, Platform::Details::IEquatable,
    Platform::Details::IPrintable
```

### <a name="remarks"></a>Açıklamalar

`Type` Sınıfı, işleme kullanarak yönlendirmelisiniz uygulamalarda kullanışlıdır bir `if` veya `switch` dallar, bir nesnenin çalışma zamanı türüne göre deyimi. Kategori türü tanımlayan türü kodu kullanılarak alınır [Type::GetTypeCode](#gettypecode) üye işlevi.

## <a name="public-methods"></a>Genel yöntemler

|||
|-|-|
|[Type::GetTypeCode yöntemi](#gettypecode)|Döndürür bir [Platform::TypeCode numaralandırması](../cppcx/platform-typecode-enumeration.md) nesne değeri.|
|[Type::ToString yöntemi](#tostring)|Belirtilen meta tür adını döndürür.|

## <a name="public-properties"></a>Genel Özellikler

|||
|-|-|
|[Type::FullName](#fullname)|Döndürür bir [Platform::String sınıfı](../cppcx/platform-string-class.md)^ türünün tam adını temsil eder ve kullanır. (bir ayırıcısı nokta) değil:: (çift virgül) — Örneğin, `MyNamespace.MyClass`.|

## <a name="conversion-operators"></a>Dönüştürme işleçleri

|||
|-|-|
|[işleç türü ^](../cppcx/operator-type-hat.md)|Dönüştürme sağlayan `Windows::UI::Xaml::Interop::TypeName` için `Platform::Type`.|
|[Windows::UI::Xaml::Interop::TypeName işleci](../cppcx/operator-windows-ui-xaml-interop-typename.md)|Dönüştürme sağlayan `Platform::Type` için `Windows::UI::Xaml::Interop::TypeName`.|

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** platformu

**Meta veri:** platform.winmd

## <a name="fullname"></a> Type::FullName özelliği

Biçiminde geçerli türünün tam adını alır. `Namespace.Type`.

### <a name="syntax"></a>Sözdizimi

```cpp
String^ FullName();
```

### <a name="return-value"></a>Dönüş Değeri

Tür adı.
### <a name="example"></a>Örnek

```

//  namespace is TestApp
MainPage::MainPage()
{
    InitializeComponent();
    Type^ t = this->GetType();
    auto s = t->FullName; // returns "TestApp.MainPage"
    auto s2 = t->ToString(); //also returns "TestApp.MainPage"
}
```

## <a name="gettypecode"></a> Type::GetTypeCode yöntemi

Yerleşik türler sayısal türü kategorisini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
Platform::TypeCode GetTypeCode();
```

### <a name="return-value"></a>Dönüş Değeri

Platform::TypeCode birini numaralandırılmış değerlerinin.

### <a name="remarks"></a>Açıklamalar

GetTypeCode() üye yöntemi eşdeğerdir `typeid` özelliği.

## <a name="tostring"></a> Type::ToString yöntemi

Alır bir türün adı.

### <a name="syntax"></a>Sözdizimi

```cpp
Platform::String^ ToString();
```

### <a name="return-value"></a>Dönüş Değeri

Belirtilen meta tür adı.

## <a name="see-also"></a>Ayrıca Bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)