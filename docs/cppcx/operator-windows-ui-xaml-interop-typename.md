---
title: işleç Windows::UI::Xaml::Interop::TypeName | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0cf5041e6e3faa8c495d52c31d86ff25c903a174
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600726"
---
# <a name="operator-windowsuixamlinteroptypename"></a>işleç Windows::UI::Xaml::Interop::TypeName
Dönüştürme sağlayan `Platform::Type` için [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
Operator TypeName(Platform::Type^ type)  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) verildiğinde bir `Platform::Type^`.  
  
### <a name="remarks"></a>Açıklamalar  
 `TypeName` tür bilgilerini temsil eden dilden Windows çalışma zamanı struct ' dir. [Platform::type](../cppcx/platform-type-class.md) C++ için özeldir ve uygulama ikili arabiriminde (ABI) geçirilemez. Bir işte `TypeName`, [Navigate](http://msdn.microsoft.com/library/windows/apps/hh702394.aspx) işlevi:  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows::UI::Xaml::Interop::TypeName işleci](../cppcx/operator-windows-ui-xaml-interop-typename.md)   
 [Platform::Type Sınıfı](../cppcx/platform-type-class.md)