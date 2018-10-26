---
title: Bildirimleri destekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 984f1bf9e716c94885df62d91f670627e89b7aab
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075014"
---
# <a name="supporting-notifications"></a>Bildirimleri Destekleme

## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>Bağlantı noktası arabirimleri sağlayıcısı ve tüketici uygulama

Bildirimleri uygulamak için bir sağlayıcı sınıfı devralmalıdır [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) ve [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md).

`IRowsetNotifyCP` Sağlayıcı sitesi için bağlantı noktası arabirimi uygulayan [IRowsetNotify](/previous-versions/windows/desktop/ms712959). `IRowsetNotifyCP` uygular bağlantı noktası üzerinde dinleyici bildirmek için işlevleri yayın `IID_IRowsetNotify` değişiklik kümesi içeriği.

Ayrıca uygulama ve kaydetme gerekir unutmayın `IRowsetNotify` Tüketici (havuz olarak da bilinir) kullanarak [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) tüketici bildirimleri işleyebilmeniz. Bağlantı noktası arabirimi tüketiciye uygulama hakkında daha fazla bilgi için bkz: [bildirimleri alma](../../data/oledb/receiving-notifications.md).

Ayrıca, sınıfı tanımlayan bağlantı noktası girişi, böyle bir harita içermelidir:

```cpp
BEGIN_CONNECTION_POINT_MAP
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)
END_CONNECTION_POINT_MAP
```

## <a name="adding-irowsetnotify"></a>IRowsetNotify ekleme

Eklenecek `IRowsetNotify`, eklemenize gerek `IConnectionPointContainerImpl<rowset-name>` ve `IRowsetNotifyCP<rowset-name>` , devralma zincirini için.

Örneğin, devralma zincirinde işte `RUpdateRowset` içinde [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV):

> [!NOTE]
> Örnek kod, ne burada listelenen öğesinden farklı olabilir; Örnek kod daha güncel bir sürüm olarak göz önüne almalısınız.

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

### <a name="setting-com-map-entries"></a>COM eşleme girişleri ayarlama

Ayrıca, satır kümesi içindeki COM eşlemesine aşağıdaki eklemeniz gerekir:

```cpp
COM_INTERFACE_ENTRY(IConnectionPointContainer)
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)
```

Bu makrolar herkesin çağırma izin `QueryInterface` bağlantı noktası kapsayıcınızın (temel `IRowsetNotify`) istenen arabirim sağlayıcıdaki bulmak için. KULLANILACAĞINA örnek ve öğretici bağlantı noktalarını kullanma örneği için bkz.

### <a name="setting-connection-point-map-entries"></a>Bağlantı noktası eşleme girişleri ayarlama

Ayrıca bir bağlantı noktası eşlemesi eklemeniz gerekir. Şunun gibi görünmelidir:

```cpp
BEGIN_CONNECTION_POINT_MAP(rowset-name)
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))
END_CONNECTION_POINT_MAP()
```

Bu bağlantı noktası eşlemesi aramak bir bileşen sağlayan `IRowsetNotify` sağlayıcınızda bulmak için arabirim.

### <a name="setting-properties"></a>Özellikleri ayarlama

Sağlayıcınız için şu özellikleri eklemeniz gerekir. Yalnızca destek arabirimlere dayalı özellikleri eklemeniz gerekir.

|Özellik|Destekliyorsanız ekleyin|
|--------------|------------------------|
|`DBPROP_IConnectionPointContainer`|Her zaman|
|`DBPROP_NOTIFICATIONGRANULARITY`|Her zaman|
|`DBPROP_NOTIFICATIONPHASES`|Her zaman|
|`DBPROP_NOTIFYCOLUMNSET`|`IRowsetChange`|
|`DBPROP_NOTIFYROWDELETE`|`IRowsetChange`|
|`DBPROP_NOTIFYROWINSERT`|`IRowsetChange`|
|`DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE`|Her zaman|
|`DBPROP_NOTIFYROWFIRSTCHANGE`|`IRowsetUpdate`|
|`DBPROP_NOTIFYROWSETRELEASE`|Her zaman|
|`DBPROP_NOTIFYROWUNDOCHANGE`|`IRowsetUpdate`|
|`DBPROP_NOTIFYROWUNDODELETE`|`IRowsetUpdate`|
|`DBPROP_NOTIFYROWUNDOINSERT`|`IRowsetUpdate`|
|`DBPROP_NOTIFYROWUPDATE`|`IRowsetUpdate`|

Çoğu uygulama bildirimleri için OLE DB sağlayıcı şablonları içinde zaten ekli. Değil eklerseniz `IRowsetNotifyCP` devralma zincirinizi derleyici Bu kod böylece kodunuzun boyutunu küçülterek, derleme akışından kaldırır.

## <a name="see-also"></a>Ayrıca Bkz.

[Gelişmiş Sağlayıcı Teknikleri](../../data/oledb/advanced-provider-techniques.md)