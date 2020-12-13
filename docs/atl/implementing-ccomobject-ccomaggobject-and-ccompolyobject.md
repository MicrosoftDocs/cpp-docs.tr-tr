---
description: 'Hakkında daha fazla bilgi edinin: CComObject, CComAggObject ve CComPolyObject uygulama'
title: CComObject, CComAggObject ve CComPolyObject uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- CComPolyObject class, implementing
- CreateInstance method
- CComAggObject class
- CComObject class, implementing
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
ms.openlocfilehash: e0cc8a6b65ec9d85249cd47e2f43cf1bec2b8ce2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147777"
---
# <a name="implementing-ccomobject-ccomaggobject-and-ccompolyobject"></a>CComObject, CComAggObject ve CComPolyObject uygulama

[CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md)ve [CComPolyObject](../atl/reference/ccompolyobject-class.md) şablon sınıfları, her zaman devralma zincirindeki en türetilmiş sınıflardır. `IUnknown`:, Ve içindeki tüm yöntemleri işlemek kendi sorumluluğundadır `QueryInterface` `AddRef` `Release` . Ayrıca, `CComAggObject` ve `CComPolyObject` (toplanmış nesneler için kullanıldığında), iç bilinmiyor için gereken özel başvuru saylarını ve `QueryInterface` semantiğini sağlar.

`CComObject`, Veya kullanılıp kullanılmadığını, `CComAggObject` `CComPolyObject` aşağıdaki makroların bir kısmını (veya hiçbirini) bildirdiğinize bağlıdır:

|Makroya|Etki|
|-----------|------------|
|DECLARE_NOT_AGGREGATABLE|Her zaman kullanır `CComObject` .|
|DECLARE_AGGREGATABLE|`CComAggObject`Nesne toplanırsa ve yoksa kullanır `CComObject` . `CComCoClass` Bu makroyu içerir, bu nedenle DECLARE_ * _AGGREGATABLE makrolarından hiçbiri sınıfınıza bildirilmez, bu varsayılan değer olacaktır.|
|DECLARE_ONLY_AGGREGATABLE|Her zaman kullanır `CComAggObject` . Nesne toplanmayan bir hata döndürür.|
|DECLARE_POLY_AGGREGATABLE|ATL çağrıldığında **CComPolyObject \<CYourClass>** örneği oluşturur `IClassFactory::CreateInstance` . Oluşturma sırasında, bilinmeyen dıştaki değeri denetlenir. NULL ise, `IUnknown` toplanmayan bir nesne için uygulanır. Bilinmeyen dış değer NULL değilse, `IUnknown` toplanmış bir nesne için uygulanır.|

Ve kullanmanın avantajı, `CComAggObject` uygulamasının `CComObject` `IUnknown` oluşturulduğu nesnenin türü için iyileştirilmesidir. Örneğin, toplanmayan bir nesne yalnızca bir başvuru sayısına ihtiyaç duyurken, toplanmış bir nesne hem iç bilinmiyor hem de dış bilinmeyen bir işaretçi için başvuru sayısına ihtiyaç duyuyor.

Kullanmanın avantajı, `CComPolyObject` `CComAggObject` `CComObject` toplu ve toplu olmayan durumları işlemek için modülünüzün her ikisine de sahip olmasını önlemenize olanak sağlar. Tek bir `CComPolyObject` nesne her iki durumu da işler. Bu, bir vtable 'ın yalnızca bir kopyasının ve modülünüzün bir kopyasının mevcut olduğu anlamına gelir. Vtable 'niz büyükse bu, modül boyutunuzu önemli ölçüde azaltabilir. Ancak, vtable 'niz küçükse,, `CComPolyObject` ve gibi toplanmış veya toplanmayan bir nesne için en iyi duruma getirilmediğinden, kullanmak biraz daha büyük bir modül boyutuna neden olabilir `CComAggObject` `CComObject` .

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM nesnelerinin temelleri](../atl/fundamentals-of-atl-com-objects.md)<br/>
[Toplama ve sınıf fabrikası makroları](../atl/reference/aggregation-and-class-factory-macros.md)
