---
title: Satır Kümesi Nesnesi Arabirimleri
ms.date: 10/24/2018
helpviewer_keywords:
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
ms.openlocfilehash: d9c2c61714a98d9de09d8657352a14f296e35a58
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501285"
---
# <a name="rowset-object-interfaces"></a>Satır Kümesi Nesnesi Arabirimleri

Aşağıdaki tabloda, bir satır kümesi nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilmektedir.

|Arabirim|Gerekli mi?|OLE DB şablonlar tarafından uygulandı mu?|
|---------------|---------------|--------------------------------------|
|[IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85))|Zorunlu|Evet|
|[IColumnsInfo](/previous-versions/windows/desktop/ms724541(v=vs.85))|Zorunlu|Evet|
|[Iverttype](/previous-versions/windows/desktop/ms715926(v=vs.85))|Zorunlu|Evet|
|[IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85))|Zorunlu|Evet|
|[IRowsetInfo](/previous-versions/windows/desktop/ms724541(v=vs.85))|Zorunlu|Evet|
|[IChapteredRowset](/previous-versions/windows/desktop/ms718180(v=vs.85))|İsteğe Bağlı|Hayır|
|[IColumnsInfo2](/previous-versions/windows/desktop/ms712953(v=vs.85))|İsteğe Bağlı|Hayır|
|[Iolumnsrowset](/previous-versions/windows/desktop/ms722657(v=vs.85))|İsteğe Bağlı|Hayır|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|İsteğe Bağlı|Evet (ATL aracılığıyla)|
|[Idbasenkronizasyon durumu](/previous-versions/windows/desktop/ms709832(v=vs.85))|İsteğe Bağlı|Hayır|
|[Iigetrow](/previous-versions/windows/desktop/ms718047(v=vs.85))|İsteğe Bağlı|Hayır|
|[IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))|İsteğe Bağlı|Evet|
|[Irowsetbölütermember](/previous-versions/windows/desktop/ms725430(v=vs.85))|İsteğe Bağlı|Hayır|
|[Irowsetcurrentındex](/previous-versions/windows/desktop/ms709700(v=vs.85))|İsteğe Bağlı|Hayır|
|[IRowsetFind bul](/previous-versions/windows/desktop/ms724221(v=vs.85))|İsteğe Bağlı|Hayır|
|[IRowsetIdentity](/previous-versions/windows/desktop/ms715913(v=vs.85))|İsteğe bağlı (ancak düzey 0 sağlayıcılar için gereklidir)|Evet|
|[IRowsetIndex](/previous-versions/windows/desktop/ms719604(v=vs.85))|İsteğe Bağlı|Hayır|
|[IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85))|İsteğe Bağlı|Evet|
|[IRowsetRefresh](/previous-versions/windows/desktop/ms714892(v=vs.85))|İsteğe Bağlı|Hayır|
|[IRowsetScroll](/previous-versions/windows/desktop/ms712984(v=vs.85))|İsteğe Bağlı|Hayır|
|[IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85))|İsteğe Bağlı|Evet|
|[Irowsetview](/previous-versions/windows/desktop/ms709755(v=vs.85))|İsteğe Bağlı|Hayır|
|[Iupporterrorınfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|İsteğe Bağlı|Evet|
|[IRowsetBookmark](/previous-versions/windows/desktop/ms714246(v=vs.85))|İsteğe Bağlı|Hayır|

Sihirbaz tarafından oluşturulan satır kümesi nesnesi, `IAccessor`devralma `IRowset`yoluyla, `IRowsetInfo` ve uygular. Her `IAccessorImpl` iki çıkış sütununu da bağlar. Arabirim `IRowset` , satırları ve verileri getirir. `IRowsetInfo` Arabirim satır kümesi özelliklerini işler.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
