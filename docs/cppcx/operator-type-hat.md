---
description: 'Daha fazla bilgi edinin: işleç türü ^'
title: işleç Türü^
ms.date: 12/30/2016
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
ms.openlocfilehash: 6258da5f276313d28f56fe470849c929cc057a47
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276809"
---
# <a name="operator-type"></a>işleç Türü^

[Windows:: UI:: XAML:: Interop:: TypeName](/uwp/api/windows.ui.xaml.interop.typename) öğesine dönüştürmeyi sağlar `Platform::Type` .

## <a name="syntax"></a>Syntax

```cpp
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName);
```

### <a name="return-value"></a>Dönüş Değeri

Bir `Platform::Type` [Windows:: UI:: XAML:: Interop:: TypeName](/uwp/api/windows.ui.xaml.interop.typename)verildiğinde bir döndürür.

### <a name="remarks"></a>Açıklamalar

`TypeName` , tür bilgilerini temsil etmek için dilden bağımsız Windows Çalışma Zamanı struct. [Platform:: Type](../cppcx/platform-type-class.md) C++ için özeldir ve uygulama ikili ARABIRIMINE (ABI) geçirilememelidir. Aşağıda `TypeName` , [gezinme](/uwp/api/windows.ui.xaml.controls.frame.navigate) işlevinde bir kullanımı aşağıda verilmiştir:

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>Örnek

Sonraki örnekte, ve arasında nasıl dönüştürme yapılacağı `TypeName` gösterilmektedir `Type` .

```

// Convert from Type to TypeName
TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri

Programlar projesini `TypeName` farklı .NET Framework <xref:System.Type>

### <a name="requirements"></a>Gereksinimler

## <a name="see-also"></a>Ayrıca bkz.

[işleç Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Platform:: Type sınıfı](../cppcx/platform-type-class.md)
