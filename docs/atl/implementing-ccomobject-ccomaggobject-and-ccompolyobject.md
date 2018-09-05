---
title: CComObject, CComAggObject ve CComPolyObject uygulama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CComPolyObject
- CComAggObject
- CComObject
dev_langs:
- C++
helpviewer_keywords:
- CComPolyObject class, implementing
- CreateInstance method
- CComAggObject class
- CComObject class, implementing
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 815edfa733e828169404258694133ffa0031917a
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755582"
---
# <a name="implementing-ccomobject-ccomaggobject-and-ccompolyobject"></a>CComObject, CComAggObject ve CComPolyObject uygulama

Şablon sınıfları [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), ve [CComPolyObject](../atl/reference/ccompolyobject-class.md) devralma zincirini en çok türetilen sınıflarda her zaman denetlersiniz. Tüm yöntemlere sorumluluğu olan `IUnknown`: `QueryInterface`, `AddRef`, ve `Release`. Ayrıca, `CComAggObject` ve `CComPolyObject` (toplanmış nesneler için kullanıldığında) özel başvuru sayımı sağlar ve `QueryInterface` semantiği iç bilinmeyen için gereklidir.

Olmadığını `CComObject`, `CComAggObject`, veya `CComPolyObject` kullanılır olup aşağıdaki makroları bir (veya hiçbiri) bildirdiğiniz üzerinde bağlıdır:

|Makrosu|Efekt|
|-----------|------------|
|DECLARE_NOT_AGGREGATABLE|Her zaman kullanan `CComObject`.|
|DECLARE_AGGREGATABLE|Kullanan `CComAggObject` nesne toplanırsa ve `CComObject` değilse. `CComCoClass` Bu makro içeren bunu DECLARE_ hiçbiri * _AGGREGATABLE makroları, bu varsayılan olur Sınıfınız içinde bildirilir.|
|DECLARE_ONLY_AGGREGATABLE|Her zaman kullanan `CComAggObject`. Nesne değil toplanırsa, bir hata döndürür.|
|DECLARE_POLY_AGGREGATABLE|ATL bir örneğini oluşturur **CComPolyObject\<CYourClass >** olduğunda `IClassFactory::CreateInstance` çağrılır. Oluşturma sırasında dış bilinmeyen değerini denetlenir. NULL ise `IUnknown` toplanmayan bir nesne için uygulanır. Dış bilinmeyen NULL değilse `IUnknown` toplanan nesne için uygulanır.|

Kullanmanın avantajı `CComAggObject` ve `CComObject` uygulaması olan `IUnknown` oluşturulan nesne türü için optimize edilmiştir. Örneği için hem iç bilinmeyen başvuru sayısını hem de dış bilinmeyen bir işaretçiye toplanan nesne gereksinimlerini toplanmayan bir nesnenin yalnızca bir başvuru sayısı gerekiyor.

Kullanmanın avantajı `CComPolyObject` ikisinin önlemek olan `CComAggObject` ve `CComObject` toplanmış ve toplanmayan durumlarında, modüldeki. Tek bir `CComPolyObject` nesnesi, her iki durumda işler. Bu işlevler bir kopyasını ve yalnızca bir kopyasını vtable modülünüzde mevcut anlamına gelir. Vtable büyükse, bu, modül boyutu önemli ölçüde düşürebilir. Ancak, vtable küçükse kullanarak `CComPolyObject` bir toplanmış veya toplanmayan nesnesi için iyileştirilmediğinden biraz daha büyük bir modül boyutu sonuçlanabilir olarak `CComAggObject` ve `CComObject`.

## <a name="see-also"></a>Ayrıca Bkz.

[ATL COM nesnelerinin temelleri](../atl/fundamentals-of-atl-com-objects.md)   
[Toplama ve Sınıf Üreticisi Makroları](../atl/reference/aggregation-and-class-factory-macros.md)

