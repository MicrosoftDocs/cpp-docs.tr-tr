---
title: Veri Kaynağı Nesne Arabirimleri
ms.date: 10/24/2018
helpviewer_keywords:
- data source objects [C++], interfaces
- data source objects [C++]
- interfaces [C++], OLE DB
- interfaces [C++], list of
- OLE DB provider templates [C++], object interfaces
- OLE DB [C++], interfaces
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
ms.openlocfilehash: fc8d2f5edf854766dcb5dcc8ed6d57a849b8f2a0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033196"
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

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
