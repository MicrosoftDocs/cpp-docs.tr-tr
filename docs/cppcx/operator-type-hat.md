---
title: işleç Türü^
ms.date: 12/30/2016
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
ms.openlocfilehash: fca53abb9dc17588695591d496b7db2a76e319f6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553666"
---
# <a name="operator-type"></a>işleç Türü^

Dönüştürme sağlayan [Windows::UI::Xaml::Interop::TypeName](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) için `Platform::Type`.

## <a name="syntax"></a>Sözdizimi

```cpp
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName);
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `Platform::Type` verildiğinde bir [Windows::UI::Xaml::Interop::TypeName](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx).

### <a name="remarks"></a>Açıklamalar

`TypeName` tür bilgilerini temsil eden dilden Windows çalışma zamanı struct ' dir. [Platform::type](../cppcx/platform-type-class.md) C++ için özeldir ve uygulama ikili arabiriminde (ABI) geçirilemez. Bir işte `TypeName`, [Navigate](https://msdn.microsoft.com/library/windows/apps/hh702394.aspx) işlevi:

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