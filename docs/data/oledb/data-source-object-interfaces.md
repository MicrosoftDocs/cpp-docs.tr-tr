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
ms.openlocfilehash: aaa9e90996750b0518999803487fcb39729c76f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519658"
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

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
