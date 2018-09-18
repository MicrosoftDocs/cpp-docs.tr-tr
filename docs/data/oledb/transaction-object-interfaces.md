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
ms.openlocfilehash: 88b6884ff8543b3aa6ec329330563fbe1ad27b8e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071594"
---
# <a name="transaction-object-interfaces"></a>İşlem Nesnesi Arabirimleri

İşlem nesnesi, bir veri kaynağında atomik bir iş birimi tanımlar ve bu iş birimleri birbirleriyle nasıl ilişki kuracağını belirler. Bu nesne OLE DB sağlayıcı şablonları tarafından doğrudan desteklenmiyor (diğer bir deyişle, kendi nesne oluşturmalısınız).  
  
Aşağıdaki tabloda, bir işlem nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilir.  
  
|Arabirim|Gerekli mi?|OLE DB Şablonları tarafından uygulanır?|  
|---------------|---------------|--------------------------------------|  
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Zorunlu|Hayır|  
|[ITransaction](/previous-versions/windows/desktop/ms723053\(v=vs.85\))|Zorunlu|Hayır|  
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816\(v=vs.85\))|İsteğe Bağlı|Hayır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)