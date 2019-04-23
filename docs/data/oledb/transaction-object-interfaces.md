---
title: İşlem Nesnesi Arabirimleri
ms.date: 10/24/2018
helpviewer_keywords:
- interfaces, OLE DB
- transaction object interfaces
- OLE DB, interfaces
- OLE DB providers, transaction support
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
ms.openlocfilehash: 0caecc797a3175d5769f98e181e1d99ef6b1ad16
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034040"
---
# <a name="transaction-object-interfaces"></a>İşlem Nesnesi Arabirimleri

İşlem nesnesi, bir veri kaynağında atomik bir iş birimi tanımlar ve bu iş birimleri birbirleriyle nasıl ilişki kuracağını belirler. Bu nesne OLE DB sağlayıcı şablonları tarafından doğrudan desteklenmiyor (diğer bir deyişle, kendi nesne oluşturmalısınız).

Aşağıdaki tabloda, bir işlem nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilir.

|Arabirim|Gerekli mi?|OLE DB Şablonları tarafından uygulanır?|
|---------------|---------------|--------------------------------------|
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Zorunlu|Hayır|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|Zorunlu|Hayır|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|İsteğe Bağlı|Hayır|

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
