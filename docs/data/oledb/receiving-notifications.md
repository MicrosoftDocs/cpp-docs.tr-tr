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
ms.openlocfilehash: b35c1d3d6ff7d5d74493e843575f7448c4df8d8f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62283838"
---
# <a name="receiving-notifications"></a>Bildirimleri Alma

OLE DB, olaylar meydana geldiğinde bildirim almak için arabirim sağlar. Bunlar [OLE DB Nesne bildirimleri](/previous-versions/windows/desktop/ms725406(v=vs.85)) içinde **OLE DB Programcının Başvurusu**. Kurulum bu olayların standart COM bağlantı noktası mekanizmasını kullanır. Örneğin, olayları aracılığıyla almayı isteyen bir ATL nesnesi `IRowsetNotify` uygulayan `IRowsetNotify` ekleyerek arabirimi `IRowsetNotify` türetilmiş sınıf listesi ve COM_INTERFACE_ENTRY makrosu aracılığıyla gösterme.

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

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)