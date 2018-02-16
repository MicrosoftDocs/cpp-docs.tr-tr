---
title: Bildirimleri destekleme | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- events [C++], notifications in OLE DB
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB provider templates, notifications
- OLE DB providers, notifications
ms.assetid: 76e875fd-2bfd-4e4e-9f43-dbe5a3fa7382
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cbdb3b7faaec99f9893df29e8d368fd05c8fd111
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="supporting-notifications"></a>Bildirimleri Destekleme
## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>Sağlayıcı ve tüketici bağlantı noktası arabirimler uygulama  
 Bildirimleri uygulamak için bir sağlayıcı sınıfı öğesinden devralmalıdır [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) ve [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md).  
  
 `IRowsetNotifyCP` Sağlayıcı site bağlantı noktası arabirimi uygulayan [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx). `IRowsetNotifyCP` Implements yayın dinleyicileri bağlantı noktasında bildirmek amacıyla işlevleri **IID_IRowsetNotify** satır içeriğini değişiklikler.  
  
 Ayrıca uygulama ve kaydetmeniz gerekir unutmayın `IRowsetNotify` kullanarak tüketici (havuz olarak da bilinir) üzerinde [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) böylece tüketici bildirimleri işleyebilir. Tüketici üzerinde bağlantı noktası arabirimi uygulama hakkında daha fazla bilgi için bkz: [bildirimleri alma](../../data/oledb/receiving-notifications.md).  
  
 Ayrıca, sınıf de bağlantı noktası girişini şöyle tanımlayan bir harita içermelidir:  
  
```  
BEGIN_CONNECTION_POINT_MAP  
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)  
END_CONNECTION_POINT_MAP  
```  
  
## <a name="adding-irowsetnotify"></a>IRowsetNotify ekleme  
 Eklemek için `IRowsetNotify`, eklemenize gerek `IConnectionPointContainerImpl<rowset-name>` ve `IRowsetNotifyCP<rowset-name>` devralma zincirini için.  
  
 Örneğin, için devralma zincirini işte `RUpdateRowset` içinde [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f):  
  
> [!NOTE]
>  Örnek kod, ne burada listelenen alanından farklı olabilir; Örnek kod daha güncel bir sürüm olarak göz önüne almalısınız.  
  
```cpp
///////////////////////////////////////////////////////////////////////////  
// class RUpdateRowset (in rowset.h)  
  
class RUpdateRowset :   
public CRowsetImpl< RUpdateRowset, CAgentMan, CUpdateCommand,   
         CAtlArray< CAgentMan, CAtlArray<CAgentMan>>, CSimpleRow,   
         IRowsetScrollImpl< RUpdateRowset, IRowsetScroll >>,  
      public IRowsetUpdateImpl< RUpdateRowset, CAgentMan >,  
      public IConnectionPointContainerImpl<RUpdateRowset>,  
      public IRowsetNotifyCP<RUpdateRowset>  
```  
  
### <a name="setting-com-map-entries"></a>COM eşleme girişlerini ayarlama  
 Ayrıca, satır kümesi COM eşlemesinde aşağıdaki eklemeniz gerekir:  
  
```  
COM_INTERFACE_ENTRY(IConnectionPointContainer)  
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)  
```  
  
 Bu makroları herkesin çağırma izin `QueryInterface` için bağlantı noktası kapsayıcısına (temeli `IRowsetNotify`) sağlayıcıdaki istenen arabirimi bulmak için. Bağlantı noktaları kullanma örneği için bkz: KULLANILACAĞINA örnek ve öğretici.  
  
### <a name="setting-connection-point-map-entries"></a>Bağlantı noktası eşleme girişlerini ayarlama  
 Ayrıca bir bağlantı noktası eşlemesi eklemeniz gerekir. Gibi görünmelidir:  
  
```  
BEGIN_CONNECTION_POINT_MAP(rowset-name)  
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))  
END_CONNECTION_POINT_MAP()  
```  
  
 Bu bağlantı noktası eşlemesi aramakta bir bileşen sağlar `IRowsetNotify` sağlayıcınızda bulmak için arabirim.  
  
### <a name="setting-properties"></a>Özellikleri ayarlama  
 Aynı zamanda aşağıdaki özellikleri sağlayıcınıza eklemeniz gerekir. Yalnızca desteklediğiniz arabirimlere dayalı özellikler eklemeniz gerekir.  
  
|Özellik|Destekliyorsanız ekleyin|  
|--------------|------------------------|  
|**DBPROP_IConnectionPointContainer**|Her zaman|  
|**DBPROP_NOTIFICATIONGRANULARITY**|Her zaman|  
|**DBPROP_NOTIFICATIONPHASES**|Her zaman|  
|**DBPROP_NOTIFYCOLUMNSET**|`IRowsetChange`|  
|**DBPROP_NOTIFYROWDELETE**|`IRowsetChange`|  
|**DBPROP_NOTIFYROWINSERT**|`IRowsetChange`|  
|**DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE**|Her zaman|  
|**DBPROP_NOTIFYROWFIRSTCHANGE**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWSETRELEASE**|Her zaman|  
|**DBPROP_NOTIFYROWUNDOCHANGE**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWUNDODELETE**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWUNDOINSERT**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWUPDATE**|`IRowsetUpdate`|  
  
 Bildirimler için uygulamalarının çoğu OLE DB sağlayıcı şablonları içinde zaten ekli. Değil eklerseniz, `IRowsetNotifyCP` devralma zinciri derleyici bu kodu dolayısıyla kodunuzun boyutunu küçülterek, derleme akışından kaldırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş Sağlayıcı Teknikleri](../../data/oledb/advanced-provider-techniques.md)