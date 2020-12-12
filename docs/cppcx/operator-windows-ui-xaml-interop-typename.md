---
description: 'Daha fazla bilgi edinin: operator Windows:: UI:: XAML:: Interop:: TypeName'
title: işleç Windows::UI::Xaml::Interop::TypeName
ms.date: 12/30/2016
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
ms.openlocfilehash: 3c4c856fcf93214959f75f861b035dbdee9b94a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145723"
---
# <a name="operator-windowsuixamlinteroptypename"></a>işleç Windows::UI::Xaml::Interop::TypeName

Dönüşümünü `Platform::Type` [Windows:: UI:: XAML:: Interop:: TypeName](/uwp/api/windows.ui.xaml.interop.typename)'e sağlar.

## <a name="syntax"></a>Syntax

```cpp
Operator TypeName(Platform::Type^ type);
```

### <a name="return-value"></a>Dönüş Değeri

Verildiğinde bir [Windows:: UI:: XAML:: Interop:: TypeName](/uwp/api/windows.ui.xaml.interop.typename) döndürür `Platform::Type^` .

### <a name="remarks"></a>Açıklamalar

`TypeName` , tür bilgilerini temsil etmek için dilden bağımsız Windows Çalışma Zamanı struct. [Platform:: Type](../cppcx/platform-type-class.md) C++ için özeldir ve uygulama ikili ARABIRIMINE (ABI) geçirilememelidir. Aşağıda `TypeName` , [gezinme](/uwp/api/windows.ui.xaml.controls.frame.navigate) işlevinde bir kullanımı aşağıda verilmiştir:

```cpp
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>Örnek

Sonraki örnekte, ve arasında nasıl dönüştürme yapılacağı `TypeName` gösterilmektedir `Type` .

```cpp
// Convert from Type to TypeName
Windows::UI::Xaml::Interop::TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri

`TypeName` [System. Type](/dotnet/api/system.type)olarak programlar projesi .NET Framework.

### <a name="requirements"></a>Gereksinimler

## <a name="see-also"></a>Ayrıca bkz.

[işleç Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Platform:: Type sınıfı](../cppcx/platform-type-class.md)
