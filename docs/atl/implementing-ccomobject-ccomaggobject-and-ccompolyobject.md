---
title: CComObject, CComAggObject ve CComPolyObject uygulama
ms.date: 11/04/2016
f1_keywords:
- CComPolyObject
- CComAggObject
- CComObject
helpviewer_keywords:
- CComPolyObject class, implementing
- CreateInstance method
- CComAggObject class
- CComObject class, implementing
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
ms.openlocfilehash: 6e9e1a22ebe23f9fec6e553713a5701315cdac96
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508985"
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

[ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)<br/>
[Toplama ve Sınıf Üreticisi Makroları](../atl/reference/aggregation-and-class-factory-macros.md)

