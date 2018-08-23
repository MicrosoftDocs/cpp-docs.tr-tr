---
title: işleç türü ^ | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c0bca9d1f60820b7ceeba633eead0aa9e572be5
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612916"
---
# <a name="operator-type"></a>işleç Türü^
Dönüştürme sağlayan [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) için `Platform::Type`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName)  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `Platform::Type` verildiğinde bir [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx).  
  
### <a name="remarks"></a>Açıklamalar  
 `TypeName` tür bilgilerini temsil eden dilden Windows çalışma zamanı struct ' dir. [Platform::type](../cppcx/platform-type-class.md) C++ için özeldir ve uygulama ikili arabiriminde (ABI) geçirilemez. Bir işte `TypeName`, [Navigate](http://msdn.microsoft.com/library/windows/apps/hh702394.aspx) işlevi:  
  
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
 .NET framework programlar proje `TypeName` olarak [System.Type](assetId:///System.Type?qualifyHint=False&autoUpgrade=True).  
  
### <a name="requirements"></a>Gereksinimler  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows::UI::Xaml::Interop::TypeName işleci](../cppcx/operator-windows-ui-xaml-interop-typename.md)   
 [Platform::Type Sınıfı](../cppcx/platform-type-class.md)