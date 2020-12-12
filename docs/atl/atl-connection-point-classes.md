---
description: 'Daha fazla bilgi edinin: ATL bağlantı noktası sınıfları'
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
ms.openlocfilehash: af3b52715d7aeca13a711557bdba2c9428d4bff5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165855"
---
# <a name="atl-connection-point-classes"></a>ATL bağlantı noktası sınıfları

ATL bağlantı noktalarını desteklemek için aşağıdaki sınıfları kullanır:

- [Inewctionpointımpl](../atl/reference/iconnectionpointimpl-class.md) bir bağlantı noktası uygular. Temsil ettiği giden arabirimin IID 'si bir şablon parametresi olarak geçirilir.

- [Inewctionpointcontainerımpl](../atl/reference/iconnectionpointcontainerimpl-class.md) bağlantı noktası kapsayıcısını uygular ve nesne listesini yönetir `IConnectionPointImpl` .

- [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) , [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimini temsil eden bir bağlantı noktası uygular.

- [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) bağlantı noktası ve havuzları arasında rastgele sayıda bağlantı yönetir.

- [CComUnkArray](../atl/reference/ccomunkarray-class.md) , şablon parametresi tarafından belirtilen önceden tanımlanmış sayıda bağlantıyı yönetir.

- [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) , bir istemcinin havuzuna nesnenin özelliğinin değiştiğini veya değiştirmek üzere olduğunu bildirir.

- [IDispEventImpl](../atl/reference/idispeventimpl-class.md) , atl com nesnesine yönelik bağlantı noktaları için destek sağlar. Bu bağlantı noktaları, COM nesneniz tarafından sağlanmış olan bir olay havuzu haritası ile eşleştirilir.

- [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) , olayları uygun işleyici işlevine yönlendirmek için sınıfınızdaki olay havuzu eşlemesiyle birlikte çalışır.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantı noktası](../atl/atl-connection-points.md)
