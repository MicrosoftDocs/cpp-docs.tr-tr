---
description: Daha fazla bilgi için bkz. IUnknown uygulama sınıfları
title: IUnknown uygulama sınıfları (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
ms.openlocfilehash: a28bd14be86501fd6566b8038b73a51efcc1c18d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147660"
---
# <a name="iunknown-implementation-classes"></a>IUnknown uygulama sınıfları

Aşağıdaki sınıflar `IUnknown` ve ilgili yöntemleri uygular:

- [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) Hem toplanmış hem de toplanmış nesneler için başvuru sayımını yönetir. Bir iş parçacığı modeli belirtmenize izin verir.

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) Hem toplanmış hem de toplanmış nesneler için başvuru sayımını yönetir. , Sunucunun varsayılan iş parçacığı modelini kullanır.

- [CComAggObject](../atl/reference/ccomaggobject-class.md) `IUnknown` Toplanmış bir nesne için uygular.

- [CComObject](../atl/reference/ccomobject-class.md) `IUnknown` Toplanmayan bir nesne için uygular.

- [CComPolyObject](../atl/reference/ccompolyobject-class.md) `IUnknown` Toplanmış ve toplanmış nesneler için uygular. Kullanarak `CComPolyObject` modülünüzü hem hem de kullanmaktan kaçınır `CComAggObject` `CComObject` . Tek bir `CComPolyObject` nesne hem toplanmış hem de toplu olmayan durumları işler.

- [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) `IUnknown` , Modül kilit sayısını değiştirmeden toplanmayan bir nesne için uygular.

- [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) `IUnknown` Bir yırma arabirimi için uygular.

- [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) `IUnknown` "Önbelleğe alınmış" bir yırma arabirimi için uygular.

- [Ccomkirinedobject](../atl/reference/ccomcontainedobject-class.md) `IUnknown` Bir toplama ya da bir yırma arabiriminin iç nesnesi için uygular.

- [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) , Nesnenizin silinmemesini sağlamak için modüldeki bir başvuru sayısını yönetir.

- [CComObjectStack](../atl/reference/ccomobjectstack-class.md) Öğesinin iskelet uygulamasını kullanarak geçici bir COM nesnesi oluşturur `IUnknown` .

## <a name="related-articles"></a>İlgili Makaleler

[ATL COM nesnelerinin temelleri](../atl/fundamentals-of-atl-com-objects.md)

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../atl/atl-class-overview.md)<br/>
[Toplama ve sınıf fabrikası makroları](../atl/reference/aggregation-and-class-factory-macros.md)<br/>
[COM eşleme makroları](../atl/reference/com-map-macros.md)<br/>
[COM eşlemesi genel Işlevleri](../atl/reference/com-map-global-functions.md)
