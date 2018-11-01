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
ms.openlocfilehash: 739c7d94e5df2d5edddc00bd3ae2703e07435c23
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641018"
---
# <a name="rowset-object-interfaces"></a>Satır Kümesi Nesnesi Arabirimleri

Aşağıdaki tabloda bir satır kümesi nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilir.

|Arabirim|Gerekli mi?|OLE DB Şablonları tarafından uygulanır?|
|---------------|---------------|--------------------------------------|
|[IAccessor](/previous-versions/windows/desktop/ms719672)|Zorunlu|Evet|
|[IColumnsInfo](/previous-versions/windows/desktop/ms724541)|Zorunlu|Evet|
|[IConvertType](/previous-versions/windows/desktop/ms715926)|Zorunlu|Evet|
|[IRowset](/previous-versions/windows/desktop/ms720986)|Zorunlu|Evet|
|[IRowsetInfo](/previous-versions/windows/desktop/ms724541)|Zorunlu|Evet|
|[IChapteredRowset](/previous-versions/windows/desktop/ms718180)|İsteğe Bağlı|Hayır|
|[IColumnsInfo2](/previous-versions/windows/desktop/ms712953)|İsteğe Bağlı|Hayır|
|[IColumnsRowset](/previous-versions/windows/desktop/ms722657)|İsteğe Bağlı|Hayır|
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|İsteğe Bağlı|Evet (ATL)|
|[IDBAsynchStatus](/previous-versions/windows/desktop/ms709832)|İsteğe Bağlı|Hayır|
|[IGetRow](/previous-versions/windows/desktop/ms718047)|İsteğe Bağlı|Hayır|
|[IRowsetChange](/previous-versions/windows/desktop/ms715790)|İsteğe Bağlı|Evet|
|[IRowsetChapterMember](/previous-versions/windows/desktop/ms725430)|İsteğe Bağlı|Hayır|
|[IRowsetCurrentIndex](/previous-versions/windows/desktop/ms709700)|İsteğe Bağlı|Hayır|
|[IRowsetFind](/previous-versions/windows/desktop/ms724221)|İsteğe Bağlı|Hayır|
|[IRowsetIdentity](/previous-versions/windows/desktop/ms715913)|İsteğe bağlı (ancak düzeyi 0 sağlayıcıları için gereklidir)|Evet|
|[IRowsetIndex](/previous-versions/windows/desktop/ms719604)|İsteğe Bağlı|Hayır|
|[IRowsetLocate](/previous-versions/windows/desktop/ms721190)|İsteğe Bağlı|Evet|
|[IRowsetRefresh](/previous-versions/windows/desktop/ms714892)|İsteğe Bağlı|Hayır|
|[IRowsetScroll](/previous-versions/windows/desktop/ms712984)|İsteğe Bağlı|Hayır|
|[IRowsetUpdate](/previous-versions/windows/desktop/ms714401)|İsteğe Bağlı|Evet|
|[IRowsetView](/previous-versions/windows/desktop/ms709755)|İsteğe Bağlı|Hayır|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816)|İsteğe Bağlı|Evet|
|[IRowsetBookmark](/previous-versions/windows/desktop/ms714246)|İsteğe Bağlı|Hayır|

Sihirbazın ürettiği satır kümesi nesnesi uygulayan `IAccessor`, `IRowset`, ve `IRowsetInfo` devralma yoluyla. `IAccessorImpl` Hem çıkış sütunları bağlar. `IRowset` Arabirimi öğesinden satır ve verileri işler. `IRowsetInfo` Arabirimi satır kümesi özellikleri işler.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
