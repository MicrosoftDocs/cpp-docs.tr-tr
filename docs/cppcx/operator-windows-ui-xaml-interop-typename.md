---
title: işleç Windows::UI::Xaml::Interop::TypeName
ms.date: 12/30/2016
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
ms.openlocfilehash: d35056ca1a4e7f06c9f91fe86998a676a12395f2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337008"
---
# <a name="operator-windowsuixamlinteroptypename"></a>işleç Windows::UI::Xaml::Interop::TypeName

Windows'dan `Platform::Type` Windows'a dönüştürmeyi [sağlar::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename).

## <a name="syntax"></a>Sözdizimi

```cpp
Operator TypeName(Platform::Type^ type);
```

### <a name="return-value"></a>Dönüş Değeri

Windows'u döndürür::UI::Xaml::Interop::TypeName verildiğinde . [Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename) `Platform::Type^`

### <a name="remarks"></a>Açıklamalar

`TypeName`tür bilgilerini temsil etmek için dilden bağımsız Windows Runtime struct'dur. [Platform::Tür](../cppcx/platform-type-class.md) C++'a özgüdür ve uygulama ikili arabirimi (ABI) üzerinden geçirilemez. Burada, Gezinme işlevinde bir kullanım: [Navigate](/uwp/api/windows.ui.xaml.controls.frame.navigate) `TypeName`

```cpp
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>Örnek

Sonraki örnek, ile `TypeName` `Type`'nin arasında nasıl dönüştürülür'

```cpp
// Convert from Type to TypeName
Windows::UI::Xaml::Interop::TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri

.NET Framework `TypeName` programları [Sistem olarak proje.Tip](/dotnet/api/system.type).

### <a name="requirements"></a>Gereksinimler

## <a name="see-also"></a>Ayrıca bkz.

[işleç Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Platform::Type Sınıfı](../cppcx/platform-type-class.md)
