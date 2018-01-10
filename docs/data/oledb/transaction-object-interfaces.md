---
title: "İşlem nesnesi arabirimleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interfaces, OLE DB
- transaction object interfaces
- OLE DB, interfaces
- OLE DB providers, transaction support
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bcb0c6abf7eac09f3cb3ea260a3a5bbe76410847
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="transaction-object-interfaces"></a>İşlem Nesnesi Arabirimleri
İşlem nesnesi bir veri kaynağında iş atomik bir ölçü tanımlar ve bu iş birimlerinin birbirleriyle nasıl ilişkili olduğunu belirler. Bu nesne OLE DB sağlayıcı şablonları tarafından doğrudan desteklenmeyen (diğer bir deyişle, kendi nesnesi oluşturmanız gerekir).  
  
 Aşağıdaki tabloda bir işlem nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilir.  
  
|Arabirim|Gerekli mi?|OLE DB Şablonları tarafından uygulanır?|  
|---------------|---------------|--------------------------------------|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Zorunlu|Hayır|  
|[ITransaction](https://msdn.microsoft.com/en-us/library/ms723053.aspx)|Zorunlu|Hayır|  
|[ISupportErrorInfo](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|İsteğe Bağlı|Hayır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)