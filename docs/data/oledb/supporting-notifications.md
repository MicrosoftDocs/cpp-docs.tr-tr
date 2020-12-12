---
description: 'Hakkında daha fazla bilgi edinin: destekleyici bildirimler'
title: Bildirimleri Destekleme
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- events [C++], notifications in OLE DB
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB provider templates, notifications
- OLE DB providers, notifications
ms.assetid: 76e875fd-2bfd-4e4e-9f43-dbe5a3fa7382
ms.openlocfilehash: 3f03ded9b900a8691c256e6cde8eaf1a2f4fb5cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316680"
---
# <a name="supporting-notifications"></a>Bildirimleri Destekleme

## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>Sağlayıcı ve tüketici üzerinde bağlantı noktası arabirimlerini uygulama

Bildirimleri uygulamak için, bir sağlayıcı sınıfının [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) ve [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md)öğesinden devralması gerekir.

`IRowsetNotifyCP` bağlantı noktası arabirimi [ırowsetnotıfy](/previous-versions/windows/desktop/ms712959(v=vs.85))için sağlayıcı sitesini uygular. `IRowsetNotifyCP``IID_IRowsetNotify`, satır kümesinin içeriğinde yapılan değişikliklerin bağlantı noktasındaki dinleyicileri bildirmek için yayın işlevlerini uygular.

Ayrıca, `IRowsetNotify` tüketicinin bildirimleri işleyebilmesi Için [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) kullanarak tüketiciyi (havuz olarak da bilinir) uygulamanız ve kaydettirmeniz gerekir. Tüketici üzerinde bağlantı noktası arabirimini uygulama hakkında daha fazla bilgi için bkz. [bildirimleri alma](../../data/oledb/receiving-notifications.md).

Ayrıca, sınıfının şu şekilde bağlantı noktası girişini tanımlayan bir eşlemesi olmalıdır:

```cpp
BEGIN_CONNECTION_POINT_MAP
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)
END_CONNECTION_POINT_MAP
```

## <a name="adding-irowsetnotify"></a>IRowsetNotify ekleme

Eklemek için `IRowsetNotify` , `IConnectionPointContainerImpl<rowset-name>` Devralma zincirinize ve ekleme yapmanız gerekir `IRowsetNotifyCP<rowset-name>` .

Örneğin, UpdatePV 'deki devralma zinciri aşağıda verilmiştir `RUpdateRowset` : [](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)

> [!NOTE]
> Örnek kod, burada listelenenden farklı bir durum içerebilir; örnek kodu daha güncel sürüme göre görmeniz gerekir.

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

Ayrıca, satır satırlarınızın COM eşlemesine aşağıdakileri eklemeniz gerekir:

```cpp
COM_INTERFACE_ENTRY(IConnectionPointContainer)
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)
```

Bu makrolar `QueryInterface` , bağlantı noktası kapsayıcınızı (öğesinin temelini) çağıran herkesin `IRowsetNotify` , sağlayıcınızda istenen arabirimi bulmasını sağlar. Bağlantı noktalarının nasıl kullanılacağına ilişkin bir örnek için bkz. ATL çokgen örneği ve öğreticisi.

### <a name="setting-connection-point-map-entries"></a>Bağlantı noktası eşleme girişlerini ayarlama

Ayrıca bir bağlantı noktası eşlemesi de eklemeniz gerekir. Şunun gibi görünmelidir:

```cpp
BEGIN_CONNECTION_POINT_MAP(rowset-name)
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))
END_CONNECTION_POINT_MAP()
```

Bu bağlantı noktası eşlemesi, `IRowsetNotify` arayüzde onu bulmak için arabirimi arayan bir bileşene izin verir.

### <a name="setting-properties"></a>Ayar özellikleri

Ayrıca, sağlayıcınıza aşağıdaki özellikleri eklemeniz gerekir. Yalnızca, destekettiğiniz arabirimlere göre özellikler eklemeniz gerekir.

|Özellik|Destekliyorsa ekleyin|
|--------------|------------------------|
|DBPROP_IConnectionPointContainer|Her zaman|
|DBPROP_NOTIFICATIONGRANULARITY|Her zaman|
|DBPROP_NOTIFICATIONPHASES|Her zaman|
|DBPROP_NOTIFYCOLUMNSET|`IRowsetChange`|
|DBPROP_NOTIFYROWDELETE|`IRowsetChange`|
|DBPROP_NOTIFYROWINSERT|`IRowsetChange`|
|DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE|Her zaman|
|DBPROP_NOTIFYROWFIRSTCHANGE|`IRowsetUpdate`|
|DBPROP_NOTIFYROWSETRELEASE|Her zaman|
|DBPROP_NOTIFYROWUNDOCHANGE|`IRowsetUpdate`|
|DBPROP_NOTIFYROWUNDODELETE|`IRowsetUpdate`|
|DBPROP_NOTIFYROWUNDOINSERT|`IRowsetUpdate`|
|DBPROP_NOTIFYROWUPDATE|`IRowsetUpdate`|

Bildirimler için uygulamanın büyük bir çoğunluğu OLE DB sağlayıcı şablonlarına zaten katıştırılır. `IRowsetNotifyCP`Devralma zincirinize eklememeniz halinde derleyici, derleme akışınızdan tüm kodu kaldırır, böylece kod boyutunuzu küçültün.

## <a name="see-also"></a>Ayrıca bkz.

[Gelişmiş sağlayıcı teknikleri](../../data/oledb/advanced-provider-techniques.md)
