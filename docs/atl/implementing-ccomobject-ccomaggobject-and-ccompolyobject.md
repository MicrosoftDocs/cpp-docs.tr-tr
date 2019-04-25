---
title: CComObject, CComAggObject ve CComPolyObject uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- CComPolyObject class, implementing
- CreateInstance method
- CComAggObject class
- CComObject class, implementing
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
ms.openlocfilehash: e2413c8fb9f5722f0245883c947067387838e57f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261793"
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

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)<br/>
[Toplama ve Sınıf Üreticisi Makroları](../atl/reference/aggregation-and-class-factory-macros.md)
