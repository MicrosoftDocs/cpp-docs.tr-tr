---
title: ATL bağlantı noktası sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- CFirePropNotifyEvent class, connection point classes
- connection points [C++], ATL classes
- ATL, connection points
- CComDynamicUnkArray class, connection point classes
- CFirePropNotifyEvent class
- CComUnkArray class, connection point classes
ms.assetid: 9582ba71-7ace-4df4-9c9b-1b0636953efc
ms.openlocfilehash: f3794b5c9e4f6297cca6611929c75d0b0133557e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252236"
---
# <a name="atl-connection-point-classes"></a>ATL bağlantı noktası sınıfları

ATL bağlantı noktaları desteklemek için aşağıdaki sınıfları kullanır:

- [Iconnectionpointımpl](../atl/reference/iconnectionpointimpl-class.md) bir bağlantı noktası uygular. IID temsil ettiği giden arabiriminin, bir şablon parametresi geçirilir.

- [Iconnectionpointcontainerımpl](../atl/reference/iconnectionpointcontainerimpl-class.md) bağlantı noktası kapsayıcısını uygular ve listesini yönetir `IConnectionPointImpl` nesneleri.

- [Ipropertynotifysinkcp](../atl/reference/ipropertynotifysinkcp-class.md) uygulayan bir bağlantı noktasını temsil eden [Ipropertynotifysink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimi.

- [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) bağlantı bağlantı noktası ve onun havuzlar arasında rastgele bir sayıdan yönetir.

- [CComUnkArray](../atl/reference/ccomunkarray-class.md) önceden tanımlanmış birkaç şablon parametresi tarafından belirtilen bağlantıları yönetir.

- [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) , bir nesnenin özelliği değiştirildi veya değiştirilmek istemcinin havuzu bildirir.

- [Idispeventımpl](../atl/reference/idispeventimpl-class.md) ATL COM nesnesi için bağlantı noktaları için destek sağlar. Bu bağlantı noktaları, COM nesnesi tarafından sağlanan bir olay havuzu Haritası ile eşlenir.

- [Idispeventsimpleımpl](../atl/reference/idispeventsimpleimpl-class.md) sınıfınızdaki uygun işleyici işlevi rota olayları için olay havuz eşlemesi ile birlikte çalışır.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantı noktası](../atl/atl-connection-points.md)
