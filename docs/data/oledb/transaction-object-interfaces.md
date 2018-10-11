---
title: İşlem nesnesi arabirimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- interfaces, OLE DB
- transaction object interfaces
- OLE DB, interfaces
- OLE DB providers, transaction support
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: caf57ab85b7a37b8e43230dc9bcf1caf031f7a78
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083794"
---
# <a name="transaction-object-interfaces"></a>İşlem Nesnesi Arabirimleri

İşlem nesnesi, bir veri kaynağında atomik bir iş birimi tanımlar ve bu iş birimleri birbirleriyle nasıl ilişki kuracağını belirler. Bu nesne OLE DB sağlayıcı şablonları tarafından doğrudan desteklenmiyor (diğer bir deyişle, kendi nesne oluşturmalısınız).  
  
Aşağıdaki tabloda, bir işlem nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilir.  
  
|Arabirim|Gerekli mi?|OLE DB Şablonları tarafından uygulanır?|  
|---------------|---------------|--------------------------------------|  
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Zorunlu|Hayır|  
|[ITransaction](/previous-versions/windows/desktop/ms723053)|Zorunlu|Hayır|  
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816)|İsteğe Bağlı|Hayır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)