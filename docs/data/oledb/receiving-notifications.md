---
title: Bildirim alma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- receiving notifications in OLE DB
- events [C++], notifications in OLE DB
- notifications [C++], events
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB providers, notifications
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: edf4b2bd69947730caba6db5d31b1e5da15f3759
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465823"
---
# <a name="receiving-notifications"></a>Bildirimleri Alma
OLE DB, olaylar meydana geldiğinde bildirim almak için arabirim sağlar. Bunlar [OLE DB Nesne bildirimleri](/previous-versions/windows/desktop/ms725406\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*. Kurulum bu olayların standart COM bağlantı noktası mekanizmasını kullanır. Örneğin, olayları aracılığıyla almayı isteyen bir ATL nesnesi `IRowsetNotify` uygulayan `IRowsetNotify` ekleyerek arabirimi `IRowsetNotify` türetilmiş sınıf listesi ve COM_INTERFACE_ENTRY makrosu aracılığıyla gösterme.  
  
 `IRowsetNotify` çeşitli zamanlarda çağrılabilir üç yöntem vardır. Bu yöntemlerden yalnızca biri için yanıt vermesini istiyorsanız kullanabileceğiniz [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) ilgilendiğiniz olmayan yöntemler için E_NOTIMPL döndüren sınıfı.  
  
 Satır kümesi oluşturduğunuzda, istediğiniz desteklemek için döndürülen satır kümesi nesnesi sağlayıcı söylemelisiniz `IConnectionPointContainer`, bildirimi ayarlamak için gerekli.  
  
 Aşağıdaki kod bir ATL nesneden satır kümesi açmak ve kullanmak nasıl gösterir `AtlAdvise` bildirim havuzunu'kurmak için işlevi. `AtlAdvise` çağırdığınızda, kullanılan tanımlama bilgisi döndürür `AtlUnadvise`.  
  
```cpp  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_IConnectionPointContainer, true);  
  
product.Open(session, _T("Products"), &propset);  
  
AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri Kullanma](../../data/oledb/using-accessors.md)