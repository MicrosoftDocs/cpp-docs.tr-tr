---
description: 'Daha fazla bilgi edinin: veri kaynağı nesne arabirimleri'
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
ms.openlocfilehash: ecc37ca4286e288939ccd15bdcd073379c27f7c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287625"
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

Veri kaynağı nesnesi `IDBProperties` Devralma yoluyla,, `IDBInitialize` ve `IDBCreateSession` arabirimlerini uygular. Bu uygulama sınıflarından birinden devralma veya devralma yaparak ek işlevleri desteklemeyi tercih edebilirsiniz. Arabirimini desteklemek istiyorsanız `IDBDataSourceAdmin` sınıfından ' ı devralması gerekir `IDBDataSourceAdminImpl` .

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
