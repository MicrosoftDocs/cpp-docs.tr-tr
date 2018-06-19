---
title: işleç Windows::UI::Xaml::Interop::TypeName | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 714d39a70b19998a5daddceadc2c91df65312122
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34256319"
---
# <a name="operator-windowsuixamlinteroptypename"></a>işleç Windows::UI::Xaml::Interop::TypeName
Dönüştürme işlemini etkinleştirir `Platform::Type` için [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
Operator TypeName(Platform::Type^ type)  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) verildiğinde bir `Platform::Type^`.  
  
### <a name="remarks"></a>Açıklamalar  
 `TypeName` tür bilgilerini temsil eden için dilden Windows çalışma zamanı yapısı olur. [Platform::type](../cppcx/platform-type-class.md) C++'a özeldir ve uygulama ikili arabirimi (ABI) arasında geçirilemez. Bir işte `TypeName`, [Bul](http://msdn.microsoft.com/library/windows/apps/hh702394.aspx) işlevi:  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
### <a name="example"></a>Örnek  
 Sonraki örnek arasında dönüştürme gösterilmektedir `TypeName` ve `Type`.  
  
```  
  
// Convert from Type to TypeName  
Windows::UI::Xaml::Interop::TypeName tn = TypeName(MainPage::typeid);  
  
// Convert back from TypeName to Type  
Type^ tx2 = (Type^)(tn);  
  
```  
  
## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri  
 .NET framework programları proje `TypeName` olarak [System.Type](assetId:///System.Type?qualifyHint=False&autoUpgrade=True).  
  
### <a name="requirements"></a>Gereksinimler  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows::UI::Xaml::Interop::TypeName işleci](../cppcx/operator-windows-ui-xaml-interop-typename.md)   
 [Platform::Type Sınıfı](../cppcx/platform-type-class.md)