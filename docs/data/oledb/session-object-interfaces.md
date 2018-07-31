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
ms.openlocfilehash: 01d08fb35a1e954aad07153f63ad3ed34282570d
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337852"
---
# <a name="session-object-interfaces"></a>Oturum Nesnesi Arabirimleri
Aşağıdaki tabloda, bir oturum nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilir.  
  
|Arabirim|Gerekli mi?|OLE DB Şablonları tarafından uygulanır?|  
|---------------|---------------|--------------------------------------|  
|[IGetDataSource](https://msdn.microsoft.com/library/ms709721.aspx)|Zorunlu|Evet|  
|[IOpenRowset](https://msdn.microsoft.com/library/ms716946.aspx)|Zorunlu|Evet|  
|[ISessionProperties](https://msdn.microsoft.com/library/ms713721.aspx)|Zorunlu|Evet|  
|[IAlterIndex](https://msdn.microsoft.com/library/ms714943.aspx)|İsteğe Bağlı|Hayır|  
|[IAlterTable](https://msdn.microsoft.com/library/ms719764.aspx)|İsteğe Bağlı|Hayır|  
|[IBindResource](https://msdn.microsoft.com/library/ms714936.aspx)|İsteğe Bağlı|Hayır|  
|[ICreateRow](https://msdn.microsoft.com/library/ms716832.aspx)|İsteğe Bağlı|Hayır|  
|[IDBCreateCommand](https://msdn.microsoft.com/library/ms711625.aspx)|İsteğe Bağlı|Evet|  
|[IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx)|İsteğe Bağlı|Evet|  
|[IIndexDefinition](https://msdn.microsoft.com/library/ms711593.aspx)|İsteğe Bağlı|Hayır|  
|[ISupportErrorInfo](https://msdn.microsoft.com/library/ms715816.aspx)|İsteğe Bağlı|Evet|  
|[ITableCreation](https://msdn.microsoft.com/library/ms713639.aspx)|İsteğe Bağlı|Hayır|  
|[ITableDefinition](https://msdn.microsoft.com/library/ms714277.aspx)|İsteğe Bağlı|Hayır|  
|[ITableDefinitionWithConstraints](https://msdn.microsoft.com/library/ms720947.aspx)|İsteğe Bağlı|Hayır|  
|[ITransaction](https://msdn.microsoft.com/library/ms723053.aspx)|İsteğe Bağlı|Hayır|  
|[ITransactionJoin](https://msdn.microsoft.com/library/ms718071.aspx)|İsteğe Bağlı|Hayır|  
|[ITransactionLocal](https://msdn.microsoft.com/library/ms714893.aspx)|İsteğe Bağlı|Hayır|  
|[ITransactionObject](https://msdn.microsoft.com/library/ms713659.aspx)|İsteğe Bağlı|Hayır|  
  
 Oturum nesnesi bir satır kümesi nesnesi oluşturur. Oturum Sağlayıcı komutları destekliyorsa, ayrıca bir komut nesnesi oluşturur. (`CCommand`, OLE DB uygulama `TCommand`). Komut nesnesi uygulayan `ICommand` arabirimi ve kullanımları `ICommand::Execute` satır kümesinde, aşağıdaki resimde gösterildiği gibi komutları yürütmek için yöntemi.  
  
 ![Sağlayıcı kavramsal diyagram](../../data/oledb/media/vc4u551.gif "vc4u551")  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)