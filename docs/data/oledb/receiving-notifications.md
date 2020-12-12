---
description: 'Hakkında daha fazla bilgi edinin: bildirimler alınıyor'
title: Bildirimleri Alma
ms.date: 10/24/2018
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- receiving notifications in OLE DB
- events [C++], notifications in OLE DB
- notifications [C++], events
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB providers, notifications
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
ms.openlocfilehash: 1885223a7d2b3e932cf449312eab989ecf1d2554
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316888"
---
# <a name="receiving-notifications"></a>Bildirimleri Alma

OLE DB, olaylar gerçekleştiğinde bildirim almak için arabirimler sağlar. Bunlar, **OLE DB Programcı başvurusunda** [OLE DB nesne bildirimleri](/previous-versions/windows/desktop/ms725406(v=vs.85)) bölümünde açıklanmaktadır. Bu olayların kurulumu standart COM bağlantı noktası mekanizmasını kullanır. Örneğin, aracılığıyla olayları almak isteyen bir ATL nesnesi, `IRowsetNotify` `IRowsetNotify` `IRowsetNotify` sınıf tarafından türetilmiş listeye ekleyerek ve bunu bir COM_INTERFACE_ENTRY makrosu aracılığıyla açarak arabirimini uygular.

`IRowsetNotify` , çeşitli zamanlarda çağrılabilen üç yöntemi vardır. Bu yöntemlerin yalnızca birine yanıt vermek istiyorsanız, ilgilendiğiniz yöntemler için E_NOTIMPL döndüren [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) sınıfını kullanabilirsiniz.

Satır kümesini oluşturduğunuzda, sağlayıcıya döndürülen satır kümesi nesnesinin, `IConnectionPointContainer` bildirimi ayarlamak için gerekli olan ' nin desteklemesini istediğinizi bildirmeniz gerekir.

Aşağıdaki kod, bir ATL nesnesinden satır kümesinin nasıl açılacağını gösterir ve `AtlAdvise` bildirim havuzunu ayarlamak için işlevini kullanır. `AtlAdvise` ' i çağırdığınızda kullanılan bir tanımlama bilgisi döndürür `AtlUnadvise` .

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_IConnectionPointContainer, true);
```

Ardından, aşağıdaki kod tarafından kullanılır:

```cpp
product.Open(session, _T("Products"), &propset);

AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);
```

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri kullanma](../../data/oledb/using-accessors.md)
