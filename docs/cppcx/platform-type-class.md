---
title: Platform::Type Sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Type::GetTypeCode
- VCCORLIB/Platform::Type::FullName
helpviewer_keywords:
- Platform::Type Class
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
ms.openlocfilehash: 7463a2518e6ec5cc84f59db05cfaf60e43eb9fde
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322088"
---
# <a name="platformtype-class"></a>Platform::Type Sınıfı

Bir tür hakkında çalışma zamanı bilgileri içerir-özellikle, bir dize adı ve bir yazı kodu. [Nesne::GetType](../cppcx/platform-object-class.md#gettype) herhangi bir nesne üzerinde veya bir sınıf veya yapı adı [üzerinde typeid](../extensions/typeid-cpp-component-extensions.md) işleci kullanarak elde edilir.

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class Platform::Type :
    Platform::Object, Platform::Details::IEquatable,
    Platform::Details::IPrintable
```

### <a name="remarks"></a>Açıklamalar

Sınıf, `Type` bir nesnenin çalışma zamanı türüne `if` `switch` göre dalları olan bir veya deyim kullanarak işlemeyi yönlendirmesi gereken uygulamalarda yararlıdır. Bir türün kategorisini açıklayan tür [kodu, Type::GetTypeCode](#gettypecode) üye işlevi kullanılarak alınır.

## <a name="public-methods"></a>Genel yöntemler

|||
|-|-|
|[Türü::GetTypeCode Yöntemi](#gettypecode)|Bir [Platform döndürür::Nesne için TypeCode Numaralandırma](../cppcx/platform-typecode-enumeration.md) değeri.|
|[Türü::ToString Yöntemi](#tostring)|Meta verilerinde belirtilen türün adını verir.|

## <a name="public-properties"></a>Genel özellikler

|||
|-|-|
|[Türü::FullName](#fullname)|Bir [Platform döndürür::String Class](../cppcx/platform-string-class.md)^ türünün tam nitelikli adını temsil eder ve kullanır. (nokta) bir ayırıcı olarak değil:: (çift kolon)—örneğin, `MyNamespace.MyClass`.|

## <a name="conversion-operators"></a>Dönüşüm operatörleri

|||
|-|-|
|[operatör Türü^](../cppcx/operator-type-hat.md)|'den `Windows::UI::Xaml::Interop::TypeName` 'e `Platform::Type`dönüştürmeyi sağlar|
|[işleç Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)|'den `Platform::Type` 'e `Windows::UI::Xaml::Interop::TypeName`dönüştürmeyi sağlar|

### <a name="requirements"></a>Gereksinimler

**Minimum desteklenen istemci:** Windows 8

**Minimum desteklenen sunucu:** Windows Server 2012

**Ad alanı:** Platform

**Meta veriler:** platform.winmd

## <a name="typefullname-property"></a><a name="fullname"></a>Türü::FullName Özelliği

Formda `Namespace.Type`geçerli türün tam nitelikli adını alır.

### <a name="syntax"></a>Sözdizimi

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

## <a name="typegettypecode-method"></a><a name="gettypecode"></a>Türü::GetTypeCode Yöntemi

Yerleşik bir sayısal tür kategorisi alır.

### <a name="syntax"></a>Sözdizimi

```cpp
Platform::TypeCode GetTypeCode();
```

### <a name="return-value"></a>Dönüş Değeri

Platform::TypeCode numaralandırılmış değerler.

### <a name="remarks"></a>Açıklamalar

GetTypeCode() üye yönteminin eşdeğeri `typeid` özelliktir.

## <a name="typetostring-method"></a><a name="tostring"></a>Türü::ToString Yöntemi

Türünün adını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
Platform::String^ ToString();
```

### <a name="return-value"></a>Dönüş Değeri

Meta verilerinde belirtildiği gibi türün adı.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
