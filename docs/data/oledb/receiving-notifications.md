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
ms.openlocfilehash: 4b630a9728770a5e35e6d6300cf465b90238350c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209815"
---
# <a name="receiving-notifications"></a>Bildirimleri Alma

OLE DB, olaylar gerçekleştiğinde bildirim almak için arabirimler sağlar. Bunlar, **OLE DB Programcı başvurusunda** [OLE DB nesne bildirimleri](/previous-versions/windows/desktop/ms725406(v=vs.85)) bölümünde açıklanmaktadır. Bu olayların kurulumu standart COM bağlantı noktası mekanizmasını kullanır. Örneğin, `IRowsetNotify` aracılığıyla olayları almak isteyen bir ATL nesnesi, sınıf tarafından türetilen listeye `IRowsetNotify` ekleyerek ve bir COM_INTERFACE_ENTRY makrosu aracılığıyla ortaya çıkaran `IRowsetNotify` arabirimini uygular.

`IRowsetNotify`, çeşitli zamanlarda çağrılabilen üç yöntemi vardır. Bu yöntemlerin yalnızca birine yanıt vermek istiyorsanız, ilgilendiğiniz yöntemler için E_NOTIMPL döndüren [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) sınıfını kullanabilirsiniz.

Satır kümesini oluştururken, sağlayıcıya döndürülen satır kümesi nesnesinin bildirimi ayarlamak için gereken `IConnectionPointContainer`desteklemesini istediğinizi söylemeniz gerekir.

Aşağıdaki kod, bir ATL nesnesinden satır kümesinin nasıl açılacağını gösterir ve bildirim havuzunu ayarlamak için `AtlAdvise` işlevini kullanır. `AtlAdvise`, `AtlUnadvise`çağırdığınızda kullanılan bir tanımlama bilgisi döndürür.

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
