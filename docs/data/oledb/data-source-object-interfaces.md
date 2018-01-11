---
title: "Veri kaynağı nesne arabirimleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data source objects [C++], interfaces
- data source objects [C++]
- interfaces [C++], OLE DB
- interfaces [C++], list of
- OLE DB provider templates [C++], object interfaces
- OLE DB [C++], interfaces
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b15ff70c505496fa6375ef01091e0826ec08d98d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="data-source-object-interfaces"></a>Veri Kaynağı Nesne Arabirimleri
Aşağıdaki tabloda, bir veri kaynağı nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilir.  
  
|Arabirim|Gerekli mi?|OLE DB Şablonları tarafından uygulanır?|  
|---------------|---------------|--------------------------------------|  
|`IDBCreateSession`|Zorunlu|Evet|  
|`IDBInitialize`|Zorunlu|Evet|  
|`IDBProperties`|Zorunlu|Evet|  
|[IPersist](http://msdn.microsoft.com/library/windows/desktop/ms688695)|Zorunlu|Evet|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|İsteğe Bağlı|Hayır|  
|`IDBDataSourceAdmin`|İsteğe Bağlı|Hayır|  
|`IDBInfo`|İsteğe Bağlı|Hayır|  
|[IPersistFile](http://msdn.microsoft.com/library/windows/desktop/ms687223)|İsteğe Bağlı|Hayır|  
|`ISupportErrorInfo`|İsteğe Bağlı|Hayır|  
  
 Veri kaynağı nesnesi uygular `IDBProperties`, `IDBInitialize`, ve `IDBCreateSession` devralma yoluyla arabirimleri. Devralarak veya bu uygulama sınıflarından birinden devralarak ek işlevleri desteklemek seçebilirsiniz. Desteklemek istiyorsanız `IDBDataSourceAdmin` arabirimi, öğesinden devralmalıdır `IDBDataSourceAdminImpl` sınıfı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)