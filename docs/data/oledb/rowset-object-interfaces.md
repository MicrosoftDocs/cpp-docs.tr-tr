---
title: Satır kümesi nesnesi arabirimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 177f3110b2bc782093a91ee9dfaa560843791b5c
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465279"
---
# <a name="rowset-object-interfaces"></a>Satır Kümesi Nesnesi Arabirimleri
Aşağıdaki tabloda bir satır kümesi nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilir.  
  
|Arabirim|Gerekli mi?|OLE DB Şablonları tarafından uygulanır?|  
|---------------|---------------|--------------------------------------|  
|[IAccessor](/previous-versions/windows/desktop/ms719672\(v=vs.85\))|Zorunlu|Evet|  
|[IColumnsInfo](/previous-versions/windows/desktop/ms724541\(v=vs.85\))|Zorunlu|Evet|  
|[IConvertType](/previous-versions/windows/desktop/ms715926\(v=vs.85\))|Zorunlu|Evet|  
|[IRowset](/previous-versions/windows/desktop/ms720986\(v=vs.85\))|Zorunlu|Evet|  
|[IRowsetInfo](/previous-versions/windows/desktop/ms724541\(v=vs.85\))|Zorunlu|Evet|  
|[IChapteredRowset](/previous-versions/windows/desktop/ms718180\(v=vs.85\))|İsteğe Bağlı|Hayır|  
|[IColumnsInfo2](/previous-versions/windows/desktop/ms712953\(v=vs.85\))|İsteğe Bağlı|Hayır|  
|[IColumnsRowset](/previous-versions/windows/desktop/ms722657\(v=vs.85\))|İsteğe Bağlı|Hayır|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|İsteğe Bağlı|Evet (ATL)|  
|[IDBAsynchStatus](/previous-versions/windows/desktop/ms709832\(v=vs.85\))|İsteğe Bağlı|Hayır|  
|[IGetRow](/previous-versions/windows/desktop/ms718047\(v=vs.85\))|İsteğe Bağlı|Hayır|  
|[IRowsetChange](/previous-versions/windows/desktop/ms715790\(v=vs.85\))|İsteğe Bağlı|Evet|  
|[IRowsetChapterMember](/previous-versions/windows/desktop/ms725430\(v=vs.85\))|İsteğe Bağlı|Hayır|  
|[IRowsetCurrentIndex](/previous-versions/windows/desktop/ms709700\(v=vs.85\))|İsteğe Bağlı|Hayır|  
|[IRowsetFind](/previous-versions/windows/desktop/ms724221\(v=vs.85\))|İsteğe Bağlı|Hayır|  
|[IRowsetIdentity](/previous-versions/windows/desktop/ms715913\(v=vs.85\))|İsteğe bağlı (ancak düzeyi 0 sağlayıcıları için gereklidir)|Evet|  
|[IRowsetIndex](/previous-versions/windows/desktop/ms719604\(v=vs.85\))|İsteğe Bağlı|Hayır|  
|[IRowsetLocate](/previous-versions/windows/desktop/ms721190\(v=vs.85\))|İsteğe Bağlı|Evet|  
|[IRowsetRefresh](/previous-versions/windows/desktop/ms714892\(v=vs.85\))|İsteğe Bağlı|Hayır|  
|[IRowsetScroll](/previous-versions/windows/desktop/ms712984\(v=vs.85\))|İsteğe Bağlı|Hayır|  
|[IRowsetUpdate](/previous-versions/windows/desktop/ms714401\(v=vs.85\))|İsteğe Bağlı|Evet|  
|[IRowsetView](/previous-versions/windows/desktop/ms709755\(v=vs.85\))|İsteğe Bağlı|Hayır|  
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816\(v=vs.85\))|İsteğe Bağlı|Evet|  
|[IRowsetBookmark](/previous-versions/windows/desktop/ms714246\(v=vs.85\))|İsteğe Bağlı|Hayır|  
  
 Sihirbazın ürettiği satır kümesi nesnesi uygulayan `IAccessor`, `IRowset`, ve `IRowsetInfo` devralma yoluyla. `IAccessorImpl` Hem çıkış sütunları bağlar. `IRowset` Arabirimi öğesinden satır ve verileri işler. `IRowsetInfo` Arabirimi satır kümesi özellikleri işler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)