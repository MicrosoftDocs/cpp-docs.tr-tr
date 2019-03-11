---
title: işleç Windows::UI::Xaml::Interop::TypeName
ms.date: 12/30/2016
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
ms.openlocfilehash: 5acf17b7c87a71259dba6579d8ee69e0eea86fa5
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738433"
---
# <a name="operator-windowsuixamlinteroptypename"></a>işleç Windows::UI::Xaml::Interop::TypeName

Dönüştürme sağlayan `Platform::Type` için [Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename).

## <a name="syntax"></a>Sözdizimi

```cpp
Operator TypeName(Platform::Type^ type);
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir [Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename) verildiğinde bir `Platform::Type^`.

### <a name="remarks"></a>Açıklamalar

`TypeName` tür bilgilerini temsil eden dilden Windows çalışma zamanı struct ' dir. [Platform::type](../cppcx/platform-type-class.md) C++ için özeldir ve uygulama ikili arabiriminde (ABI) geçirilemez. Bir işte `TypeName`, [Navigate](/uwp/api/windows.ui.xaml.controls.frame.navigate) işlevi:

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>Örnek

Sonraki örnek arasında nasıl dönüştürme yapılacağını gösterir `TypeName` ve `Type`.

```

// Convert from Type to TypeName
Windows::UI::Xaml::Interop::TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri

.NET framework programlar proje `TypeName` olarak [System.Type](assetId:///System.Type?qualifyHint=False&autoUpgrade=True).

### <a name="requirements"></a>Gereksinimler

## <a name="see-also"></a>Ayrıca bkz.

[Windows::UI::Xaml::Interop::TypeName işleci](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Platform::Type Sınıfı](../cppcx/platform-type-class.md)
