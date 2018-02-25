---
title: Bildirimleri alma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 50911440acbc7514b091a439d42bf73ee60353f9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="receiving-notifications"></a>Bildirimleri Alma
OLE DB olaylar meydana geldiğinde bildirim almak için arabirim sağlar. Bunlar [OLE DB Nesne bildirimleri](https://msdn.microsoft.com/en-us/library/ms725406.aspx) içinde *OLE DB Programcının Başvurusu*. Bu olayların Kurulumu standart COM bağlantı noktası mekanizması kullanır. Örneğin, aracılığıyla olaylarını almak istediği bir ATL nesnesi `IRowsetNotify` uygulayan `IRowsetNotify` ekleyerek arabirimi `IRowsetNotify` türetilmiş sınıf listesi ve üzerinden gösterme bir **COM_INTERFACE_ENTRY** makrosu.  
  
 `IRowsetNotify` çeşitli zamanlarda çağrılabilen üç yöntem vardır. Bu yöntemlerden sadece birini kullanmak için yanıt vermek istiyorsanız, kullanabileceğiniz [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) sınıfı, döndüren **E_NOTIMPL** ilgilendiğiniz değil yöntemleri için.  
  
 Satır kümesi oluşturduğunuzda, desteklemek için döndürülen satır kümesi nesnesi istediğiniz sağlayıcı söylemelisiniz **IConnectionPointContainer**, bildirimi ayarlamak için gerekli.  
  
 Aşağıdaki kod bir ATL nesnesinden satır açmak ve kullanmak nasıl gösterir `AtlAdvise` bildirim havuzunu kurmak için işlev. `AtlAdvise` çağırdığınızda, kullanılan bir tanımlama bilgisi döndürür `AtlUnadvise`.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_IConnectionPointContainer, true);  
  

product.Open(session, _T("Products"), &propset);  
  

AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri Kullanma](../../data/oledb/using-accessors.md)