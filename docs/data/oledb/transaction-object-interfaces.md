---
description: 'Daha fazla bilgi edinin: Işlem nesnesi arabirimleri'
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
ms.openlocfilehash: bc8eec6ca5a962e825eafa12255d8a47a8a463f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272649"
---
# <a name="transaction-object-interfaces"></a>İşlem Nesnesi Arabirimleri

İşlem nesnesi bir veri kaynağında atomik bir iş birimi tanımlar ve bu iş birimlerinin birbirleriyle nasıl ilgili olduğunu belirler. Bu nesne OLE DB sağlayıcı şablonları tarafından doğrudan desteklenmez (yani, kendi nesneniz oluşturmanız gerekir).

Aşağıdaki tabloda, bir işlem nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilmektedir.

|Arabirim|Gerekli mi?|OLE DB şablonlar tarafından uygulandı mu?|
|---------------|---------------|--------------------------------------|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Zorunlu|Hayır|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|Zorunlu|Hayır|
|[Iupporterrorınfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|İsteğe Bağlı|Hayır|

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
