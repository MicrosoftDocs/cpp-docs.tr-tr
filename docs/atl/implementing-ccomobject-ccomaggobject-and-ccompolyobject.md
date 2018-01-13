---
title: CComObject, CComAggObject ve CComPolyObject uygulama | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CComPolyObject
- CComAggObject
- CComObject
dev_langs: C++
helpviewer_keywords:
- CComPolyObject class, implementing
- CreateInstance method
- CComAggObject class
- CComObject class, implementing
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 54f237a629c4af9ea7ae30aeca21c03786abcd97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-ccomobject-ccomaggobject-and-ccompolyobject"></a>CComObject, CComAggObject ve CComPolyObject uygulama
Şablon sınıfları [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), ve [CComPolyObject](../atl/reference/ccompolyobject-class.md) her zaman en çok türetilen devralma zincirinde sınıflarıdır. Tüm yöntemlere işlemeye sorumluluğu olan **IUnknown**: `QueryInterface`, `AddRef`, ve **sürüm**. Ayrıca, `CComAggObject` ve `CComPolyObject` (toplanmış nesneler için kullanıldığında) özel başvuru sayımı sağlamak ve `QueryInterface` semantiği iç bilinmeyen için gereklidir.  
  
 Olup olmadığını `CComObject`, `CComAggObject`, veya `CComPolyObject` kullanılan olup aşağıdaki makroları bir (veya hiçbiri) bildirdiğiniz üzerinde bağlıdır:  
  
|Makrosu|Efekt|  
|-----------|------------|  
|`DECLARE_NOT_AGGREGATABLE`|Her zaman kullanır `CComObject`.|  
|`DECLARE_AGGREGATABLE`|Kullanan `CComAggObject` nesne toplanır varsa ve `CComObject` değilse. `CComCoClass`Bu makrosu içeren bunu hiçbiri **DECLARE_\*_AGGREGATABLE** makroları bildirildiğinden sınıfınızda, bu varsayılan olur.|  
|`DECLARE_ONLY_AGGREGATABLE`|Her zaman kullanır `CComAggObject`. Nesne olmayan toplanır durumunda bir hata döndürür.|  
|`DECLARE_POLY_AGGREGATABLE`|ATL bir örneğini oluşturur **CComPolyObject\<CYourClass >** zaman **IClassFactory::CreateInstance** olarak adlandırılır. Oluşturma sırasında dış bilinmeyen değerini denetlenir. Eğer öyleyse **NULL**, **IUnknown** toplanmayan bir nesne için uygulanır. Dış bilinmeyen değilse **NULL**, **IUnknown** toplanmış olan bir nesne için uygulanır.|  
  
 Kullanmanın avantajı `CComAggObject` ve `CComObject` , uygulamasıdır **IUnknown** oluşturulan nesne türü için optimize edilmiştir. Örneği için hem iç bilinmeyen için bir başvuru sayımı hem de dış bilinmeyen bir işaretçi bir toplanmış nesnenin gerekiyor ancak toplanmayan bir nesnenin yalnızca bir başvuru sayısı gerekiyor.  
  
 Kullanmanın avantajı `CComPolyObject` her ikisi de zorunda kalmamak olan `CComAggObject` ve `CComObject` toplanmış ve toplanmayan durumlarında, modüldeki. Tek bir `CComPolyObject` nesnesini işleme her iki durumda. Bu, yalnızca bir kopyasını vtable ve işlevlerin bir kopya, modülünde mevcut anlamına gelir. Vtable büyükse, bu modül boyutu önemli ölçüde düşürebilir. Ancak, vtable küçükse kullanarak `CComPolyObject` bir toplanmış veya toplanmayan nesne için iyileştirilmediğinden biraz daha büyük bir modül boyutu sonuçlanabilir olarak `CComAggObject` ve `CComObject`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM nesneleri temelleri](../atl/fundamentals-of-atl-com-objects.md)   
 [Toplama ve Sınıf Üreticisi Makroları](../atl/reference/aggregation-and-class-factory-macros.md)

