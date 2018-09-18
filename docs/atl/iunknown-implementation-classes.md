---
title: Bilinmeyen uygulama sınıfları (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.Iunknown
dev_langs:
- C++
helpviewer_keywords:
- IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42c42b43fdc04978fabe36b0ea64f39b9a5d333f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098491"
---
# <a name="iunknown-implementation-classes"></a>Bilinmeyen uygulama sınıfları

Aşağıdaki sınıflar uygulama `IUnknown` ve ilgili yöntemler:

- [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) başvuru sayımı toplanmış ve toplanmayan nesnelerini yönetir. Bir iş parçacığı modeli belirtmenizi sağlar.

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) başvuru sayımı toplanmış ve toplanmayan nesnelerini yönetir. İş parçacığı modeli sunucusunun varsayılan kullanır.

- [CComAggObject](../atl/reference/ccomaggobject-class.md) uygular `IUnknown` toplanan nesne için.

- [CComObject](../atl/reference/ccomobject-class.md) uygular `IUnknown` toplanmayan bir nesne.

- [CComPolyObject](../atl/reference/ccompolyobject-class.md) uygular `IUnknown` toplanmış ve toplanmayan nesneler için. Kullanarak `CComPolyObject` hem zorunluluğunu ortadan `CComAggObject` ve `CComObject` , modüldeki. Tek bir `CComPolyObject` nesne toplanmış ve toplanmayan durumları işler.

- [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) uygular `IUnknown` modülün kilit sayacını değiştirmeden toplanmayan bir nesne için.

- [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) uygular `IUnknown` bölünmüş arabirim.

- [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) uygular `IUnknown` "önbelleğe alınan" bir bölünmüş arabirim.

- [CComContainedObject](../atl/reference/ccomcontainedobject-class.md) uygular `IUnknown` bir toplama veya bir bölünmüş arabirim iç nesne.

- [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) modülü nesnenizin emin olmak için bir başvuru sayısını olmaz silinmesi yönetir.

- [CComObjectStack](../atl/reference/ccomobjectstack-class.md) bir iskelet uygulamasını kullanarak geçici bir COM nesnesi oluşturur `IUnknown`.

## <a name="related-articles"></a>İlgili Makaleler

[ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../atl/atl-class-overview.md)<br/>
[Toplama ve Sınıf Üreticisi Makroları](../atl/reference/aggregation-and-class-factory-macros.md)<br/>
[COM Eşleme Makroları](../atl/reference/com-map-macros.md)<br/>
[COM Eşlemesi Genel İşlevleri](../atl/reference/com-map-global-functions.md)

