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
ms.openlocfilehash: e1e64d5f41950492c3c7076160e6d134f7eb62cf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099659"
---
# <a name="data-source-object-interfaces"></a>Veri Kaynağı Nesne Arabirimleri

Aşağıdaki tabloda, bir veri kaynağı nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilir.  
  
|Arabirim|Gerekli mi?|OLE DB Şablonları tarafından uygulanır?|  
|---------------|---------------|--------------------------------------|  
|`IDBCreateSession`|Zorunlu|Evet|  
|`IDBInitialize`|Zorunlu|Evet|  
|`IDBProperties`|Zorunlu|Evet|  
|[IPersist](/windows/desktop/api/objidl/nn-objidl-ipersist)|Zorunlu|Evet|  
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|İsteğe Bağlı|Hayır|  
|`IDBDataSourceAdmin`|İsteğe Bağlı|Hayır|  
|`IDBInfo`|İsteğe Bağlı|Hayır|  
|[IPersistFile](/windows/desktop/api/objidl/nn-objidl-ipersistfile)|İsteğe Bağlı|Hayır|  
|`ISupportErrorInfo`|İsteğe Bağlı|Hayır|  
  
Veri kaynağı nesnesi uygulayan `IDBProperties`, `IDBInitialize`, ve `IDBCreateSession` devralma yoluyla arabirimleri. Bu uygulama sınıflarının birinden devralan değil ya da ek işlevleri destekleyen seçebilirsiniz. Desteklemek istiyorsanız `IDBDataSourceAdmin` arabirimi, devralmalıdır `IDBDataSourceAdminImpl` sınıfı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)