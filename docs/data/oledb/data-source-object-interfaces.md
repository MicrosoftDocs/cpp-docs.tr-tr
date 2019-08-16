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
ms.openlocfilehash: a615694a9db75cdaf3b187cf6d29248bd26ef978
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501398"
---
# <a name="data-source-object-interfaces"></a>Veri Kaynağı Nesne Arabirimleri

Aşağıdaki tabloda, bir veri kaynağı nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilmektedir.

|Arabirim|Gerekli mi?|OLE DB şablonlar tarafından uygulandı mu?|
|---------------|---------------|--------------------------------------|
|`IDBCreateSession`|Zorunlu|Evet|
|`IDBInitialize`|Zorunlu|Evet|
|`IDBProperties`|Zorunlu|Evet|
|[IPersist](/windows/win32/api/objidl/nn-objidl-ipersist)|Zorunlu|Evet|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|İsteğe Bağlı|Hayır|
|`IDBDataSourceAdmin`|İsteğe Bağlı|Hayır|
|`IDBInfo`|İsteğe Bağlı|Hayır|
|[IPersistFile](/windows/win32/api/objidl/nn-objidl-ipersistfile)|İsteğe Bağlı|Hayır|
|`ISupportErrorInfo`|İsteğe Bağlı|Hayır|

Veri kaynağı nesnesi devralma yoluyla `IDBProperties`, `IDBInitialize`, ve `IDBCreateSession` arabirimlerini uygular. Bu uygulama sınıflarından birinden devralma veya devralma yaparak ek işlevleri desteklemeyi tercih edebilirsiniz. `IDBDataSourceAdmin` Arabirimini desteklemek istiyorsanız `IDBDataSourceAdminImpl` sınıfından ' ı devralması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
