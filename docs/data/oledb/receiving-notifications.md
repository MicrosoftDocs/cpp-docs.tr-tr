---
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
ms.openlocfilehash: 20572fa444f585d231bc5374bebac4dbb71166a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647778"
---
# <a name="receiving-notifications"></a>Bildirimleri Alma

OLE DB, olaylar meydana geldiğinde bildirim almak için arabirim sağlar. Bunlar [OLE DB Nesne bildirimleri](/previous-versions/windows/desktop/ms725406) içinde **OLE DB Programcının Başvurusu**. Kurulum bu olayların standart COM bağlantı noktası mekanizmasını kullanır. Örneğin, olayları aracılığıyla almayı isteyen bir ATL nesnesi `IRowsetNotify` uygulayan `IRowsetNotify` ekleyerek arabirimi `IRowsetNotify` türetilmiş sınıf listesi ve COM_INTERFACE_ENTRY makrosu aracılığıyla gösterme.

`IRowsetNotify` çeşitli zamanlarda çağrılabilir üç yöntem vardır. Bu yöntemlerden yalnızca biri için yanıt vermesini istiyorsanız kullanabileceğiniz [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) ilginizi olmayan yöntemler için E_NOTIMPL döndüren sınıfı.

Satır kümesi oluşturduğunuzda, istediğiniz desteklemek için döndürülen satır kümesi nesnesi sağlayıcı söylemelisiniz `IConnectionPointContainer`, bildirimi ayarlamak için gerekli.

Aşağıdaki kod bir ATL nesneden satır kümesi açmak ve kullanmak nasıl gösterir `AtlAdvise` bildirim havuzunu'kurmak için işlevi. `AtlAdvise` çağırdığınızda, kullanılan tanımlama bilgisi döndürür `AtlUnadvise`.

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_IConnectionPointContainer, true);
```

Ardından, aşağıdaki kod tarafından kullanılır:

```cpp
product.Open(session, _T("Products"), &propset);

AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);
```

## <a name="see-also"></a>Ayrıca Bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)