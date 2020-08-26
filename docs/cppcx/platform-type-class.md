---
title: 'Platform:: Type sınıfı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Type::GetTypeCode
- VCCORLIB/Platform::Type::FullName
helpviewer_keywords:
- Platform::Type Class
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
ms.openlocfilehash: f94e1b37cf198f92d49efc793753892c1b138d69
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846569"
---
# <a name="platformtype-class"></a>Platform:: Type sınıfı

Özellikle bir dize adı ve bir tür bilgisi ile ilgili çalışma zamanı bilgilerini içerir. Herhangi bir nesnede [nesne:: GetType](../cppcx/platform-object-class.md#gettype) çağırarak veya bir sınıf ya da yapı adı üzerinde [TypeId](../extensions/typeid-cpp-component-extensions.md) işleci kullanılarak elde edilir.

## <a name="syntax"></a>Syntax

```cpp
public ref class Platform::Type :
    Platform::Object, Platform::Details::IEquatable,
    Platform::Details::IPrintable
```

### <a name="remarks"></a>Açıklamalar

`Type`Sınıfı, **`if`** **`switch`** bir nesnenin çalışma zamanı türüne göre dalların bir veya bir ifadesini kullanarak işlemesini doğrudan işlemek gereken uygulamalarda yararlıdır. Bir türün kategorisini açıklayan tür kodu, [Type:: GetTypeCode](#gettypecode) üye işlevi kullanılarak alınır.

## <a name="public-methods"></a>Ortak Yöntemler

| Ad | Açıklama |
|--|--|
| [Type:: GetTypeCode yöntemi](#gettypecode) | Nesne için bir [Platform:: TypeCode numaralandırma](../cppcx/platform-typecode-enumeration.md) değeri döndürür. |
| [Type:: ToString yöntemi](#tostring) | Meta verilerinde belirtilen türün adını döndürür. |

## <a name="public-properties"></a>Ortak özellikler

| Ad | Açıklama |
|--|--|
| [Tür:: FullName](#fullname) | Türün tam adını temsil eden ve kullanan bir [Platform:: String sınıfı](../cppcx/platform-string-class.md)^ döndürür. (nokta) ayırıcı olarak, değil:: (çift noktalı virgül) — Örneğin, `MyNamespace.MyClass` . |

## <a name="conversion-operators"></a>Dönüştürme işleçleri

| Ad | Açıklama |
|--|--|
| [işleç türü ^](../cppcx/operator-type-hat.md) | Dönüşümünü sağlar `Windows::UI::Xaml::Interop::TypeName` `Platform::Type` . |
| [işleç Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md) | Dönüşümünü sağlar `Platform::Type` `Windows::UI::Xaml::Interop::TypeName` . |

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Meta veri:** platform. winmd

## <a name="typefullname-property"></a><a name="fullname"></a> Type:: FullName özelliği

Formdaki geçerli türün tam adını alır `Namespace.Type` .

### <a name="syntax"></a>Syntax

```cpp
String^ FullName();
```

### <a name="return-value"></a>Dönüş Değeri

Türün adı.

### <a name="example"></a>Örnek

```cpp
//  namespace is TestApp
MainPage::MainPage()
{
    InitializeComponent();
    Type^ t = this->GetType();
    auto s = t->FullName; // returns "TestApp.MainPage"
    auto s2 = t->ToString(); //also returns "TestApp.MainPage"
}
```

## <a name="typegettypecode-method"></a><a name="gettypecode"></a> Type:: GetTypeCode yöntemi

Yerleşik türler sayısal tür kategorisini alır.

### <a name="syntax"></a>Syntax

```cpp
Platform::TypeCode GetTypeCode();
```

### <a name="return-value"></a>Dönüş Değeri

Platform:: TypeCode numaralandırılydeğerlerinden biri.

### <a name="remarks"></a>Açıklamalar

GetTypeCode () üye yönteminin eşdeğeri **`typeid`** özelliktir.

## <a name="typetostring-method"></a><a name="tostring"></a> Type:: ToString yöntemi

Türün adını alır.

### <a name="syntax"></a>Syntax

```cpp
Platform::String^ ToString();
```

### <a name="return-value"></a>Dönüş Değeri

Meta verilerinde belirtilen tür adı.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
