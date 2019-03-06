---
title: işleç Türü^
ms.date: 12/30/2016
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
ms.openlocfilehash: 5b2c0b83533af62aa96fdc4b53f5762c6ca748a4
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422175"
---
# <a name="operator-type"></a>işleç Türü^

Dönüştürme sağlayan [Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename) için `Platform::Type`.

## <a name="syntax"></a>Sözdizimi

```cpp
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName);
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `Platform::Type` verildiğinde bir [Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename).

### <a name="remarks"></a>Açıklamalar

`TypeName` tür bilgilerini temsil eden dilden Windows çalışma zamanı struct ' dir. [Platform::type](../cppcx/platform-type-class.md) C++ için özeldir ve uygulama ikili arabiriminde (ABI) geçirilemez. Bir işte `TypeName`, [Navigate](/uwp/api/windows.ui.xaml.controls.frame.navigate) işlevi:

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>Örnek

Sonraki örnek arasında nasıl dönüştürme yapılacağını gösterir `TypeName` ve `Type`.

```

// Convert from Type to TypeName
TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri

.NET framework programlar proje `TypeName` olarak <xref:System.Type>

### <a name="requirements"></a>Gereksinimler

## <a name="see-also"></a>Ayrıca Bkz.

[Windows::UI::Xaml::Interop::TypeName işleci](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Platform::Type Sınıfı](../cppcx/platform-type-class.md)