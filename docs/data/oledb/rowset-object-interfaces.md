---
title: "Satır kümesi nesnesi arabirimleri | Microsoft Docs"
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
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 211fb5bbd0a950eff5f954d1c23b3dc993badb0d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="rowset-object-interfaces"></a>Satır Kümesi Nesnesi Arabirimleri
Aşağıdaki tabloda satır kümesi nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilir.  
  
|Arabirim|Gerekli mi?|OLE DB Şablonları tarafından uygulanır?|  
|---------------|---------------|--------------------------------------|  
|[IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx)|Zorunlu|Evet|  
|[IColumnsInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx)|Zorunlu|Evet|  
|[IConvertType](https://msdn.microsoft.com/en-us/library/ms715926.aspx)|Zorunlu|Evet|  
|[IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx)|Zorunlu|Evet|  
|[IRowsetInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx)|Zorunlu|Evet|  
|[IChapteredRowset](https://msdn.microsoft.com/en-us/library/ms718180.aspx)|İsteğe Bağlı|Hayır|  
|[IColumnsInfo2](https://msdn.microsoft.com/en-us/library/ms712953.aspx)|İsteğe Bağlı|Hayır|  
|[IColumnsRowset](https://msdn.microsoft.com/en-us/library/ms722657.aspx)|İsteğe Bağlı|Hayır|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|İsteğe Bağlı|Evet (ATL)|  
|[IDBAsynchStatus](https://msdn.microsoft.com/en-us/library/ms709832.aspx)|İsteğe Bağlı|Hayır|  
|[IGetRow](https://msdn.microsoft.com/en-us/library/ms718047.aspx)|İsteğe Bağlı|Hayır|  
|[IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx)|İsteğe Bağlı|Evet|  
|[IRowsetChapterMember](https://msdn.microsoft.com/en-us/library/ms725430.aspx)|İsteğe Bağlı|Hayır|  
|[IRowsetCurrentIndex](https://msdn.microsoft.com/en-us/library/ms709700.aspx)|İsteğe Bağlı|Hayır|  
|[IRowsetFind](https://msdn.microsoft.com/en-us/library/ms724221.aspx)|İsteğe Bağlı|Hayır|  
|[IRowsetIdentity](https://msdn.microsoft.com/en-us/library/ms715913.aspx)|İsteğe bağlı (ancak 0 düzey sağlayıcılar için gereklidir)|Evet|  
|[IRowsetIndex](https://msdn.microsoft.com/en-us/library/ms719604.aspx)|İsteğe Bağlı|Hayır|  
|[IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx)|İsteğe Bağlı|Evet|  
|[IRowsetRefresh](https://msdn.microsoft.com/en-us/library/ms714892.aspx)|İsteğe Bağlı|Hayır|  
|[IRowsetScroll](https://msdn.microsoft.com/en-us/library/ms712984.aspx)|İsteğe Bağlı|Hayır|  
|[IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx)|İsteğe Bağlı|Evet|  
|[IRowsetView](https://msdn.microsoft.com/en-us/library/ms709755.aspx)|İsteğe Bağlı|Hayır|  
|[ISupportErrorInfo](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|İsteğe Bağlı|Evet|  
|[IRowsetBookmark](https://msdn.microsoft.com/en-us/library/ms714246.aspx)|İsteğe Bağlı|Hayır|  
  
 Sihirbaz tarafından oluşturulan satır kümesi nesnesi uygulayan `IAccessor`, `IRowset`, ve `IRowsetInfo` devralma yoluyla. `IAccessorImpl` İki çıktı sütununu bağlar. `IRowset` Arabirimi öğesinden satır ve verileri işler. `IRowsetInfo` Arabirimi satır kümesi özelliklerini işler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)