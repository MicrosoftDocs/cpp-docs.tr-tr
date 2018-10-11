---
title: Oturum nesnesi arabirimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 957fe69b413496af46aa8e19afd45ee41e58b490
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49081779"
---
# <a name="session-object-interfaces"></a>Oturum Nesnesi Arabirimleri

Aşağıdaki tabloda, bir oturum nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilir.  
  
|Arabirim|Gerekli mi?|OLE DB Şablonları tarafından uygulanır?|  
|---------------|---------------|--------------------------------------|  
|[IGetDataSource](/previous-versions/windows/desktop/ms709721)|Zorunlu|Evet|  
|[IOpenRowset](/previous-versions/windows/desktop/ms716946)|Zorunlu|Evet|  
|[ISessionProperties](/previous-versions/windows/desktop/ms713721)|Zorunlu|Evet|  
|[IAlterIndex](/previous-versions/windows/desktop/ms714943)|İsteğe Bağlı|Hayır|  
|[IAlterTable](/previous-versions/windows/desktop/ms719764)|İsteğe Bağlı|Hayır|  
|[IBindResource](/previous-versions/windows/desktop/ms714936)|İsteğe Bağlı|Hayır|  
|[ICreateRow](/previous-versions/windows/desktop/ms716832)|İsteğe Bağlı|Hayır|  
|[IDBCreateCommand](/previous-versions/windows/desktop/ms711625)|İsteğe Bağlı|Evet|  
|[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686)|İsteğe Bağlı|Evet|  
|[IIndexDefinition](/previous-versions/windows/desktop/ms711593)|İsteğe Bağlı|Hayır|  
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816)|İsteğe Bağlı|Evet|  
|[ITableCreation](/previous-versions/windows/desktop/ms713639)|İsteğe Bağlı|Hayır|  
|[ITableDefinition](/previous-versions/windows/desktop/ms714277)|İsteğe Bağlı|Hayır|  
|[ITableDefinitionWithConstraints](/previous-versions/windows/desktop/ms720947)|İsteğe Bağlı|Hayır|  
|[ITransaction](/previous-versions/windows/desktop/ms723053)|İsteğe Bağlı|Hayır|  
|[ITransactionJoin](/previous-versions/windows/desktop/ms718071)|İsteğe Bağlı|Hayır|  
|[ITransactionLocal](/previous-versions/windows/desktop/ms714893)|İsteğe Bağlı|Hayır|  
|[ITransactionObject](/previous-versions/windows/desktop/ms713659)|İsteğe Bağlı|Hayır|  
  
Oturum nesnesi bir satır kümesi nesnesi oluşturur. Oturum Sağlayıcı komutları destekliyorsa, ayrıca bir komut nesnesi oluşturur. (`CCommand`, OLE DB uygulama `TCommand`). Komut nesnesi uygulayan `ICommand` arabirimi ve kullanımları `ICommand::Execute` satır kümesinde, aşağıdaki resimde gösterildiği gibi komutları yürütmek için yöntemi.  
  
![Sağlayıcı kavramsal diyagram](../../data/oledb/media/vc4u551.gif "vc4u551")  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)