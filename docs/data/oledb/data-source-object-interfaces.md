---
title: Veri kaynağı nesne arabirimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data source objects [C++], interfaces
- data source objects [C++]
- interfaces [C++], OLE DB
- interfaces [C++], list of
- OLE DB provider templates [C++], object interfaces
- OLE DB [C++], interfaces
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1c8aaed0a9f50e20dba5938b9b37425f4caa2bb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101883"
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