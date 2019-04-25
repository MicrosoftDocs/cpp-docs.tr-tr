---
title: işleç Türü^
ms.date: 12/30/2016
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
ms.openlocfilehash: 180efcac76b7f51291a47ee68508e7444a6c069c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161816"
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

## <a name="see-also"></a>Ayrıca bkz.

[Windows::UI::Xaml::Interop::TypeName işleci](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Platform::Type Sınıfı](../cppcx/platform-type-class.md)
