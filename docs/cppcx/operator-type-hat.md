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
ms.openlocfilehash: 8abccf48219b70040ce728ba0dff9fa02b57bfc0
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688471"
---
# <a name="operator-type"></a>işleç Türü^
Dönüştürme sağlayan [Windows::UI::Xaml::Interop::TypeName](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) için `Platform::Type`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName)  
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
 [Windows::UI::Xaml::Interop::TypeName işleci](../cppcx/operator-windows-ui-xaml-interop-typename.md)   
 [Platform::Type Sınıfı](../cppcx/platform-type-class.md)