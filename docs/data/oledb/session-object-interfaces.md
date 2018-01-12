---
title: Oturum nesnesi arabirimleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: abb869becff4f2a4af9d489736c21b66674cc112
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="session-object-interfaces"></a>Oturum Nesnesi Arabirimleri
Aşağıdaki tabloda, bir oturum nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilir.  
  
|Arabirim|Gerekli mi?|OLE DB Şablonları tarafından uygulanır?|  
|---------------|---------------|--------------------------------------|  
|[IGetDataSource](https://msdn.microsoft.com/en-us/library/ms709721.aspx)|Zorunlu|Evet|  
|[IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx)|Zorunlu|Evet|  
|[ISessionProperties](https://msdn.microsoft.com/en-us/library/ms713721.aspx)|Zorunlu|Evet|  
|[IAlterIndex](https://msdn.microsoft.com/en-us/library/ms714943.aspx)|İsteğe Bağlı|Hayır|  
|[IAlterTable](https://msdn.microsoft.com/en-us/library/ms719764.aspx)|İsteğe Bağlı|Hayır|  
|[IBindResource](https://msdn.microsoft.com/en-us/library/ms714936.aspx)|İsteğe Bağlı|Hayır|  
|[ICreateRow](https://msdn.microsoft.com/en-us/library/ms716832.aspx)|İsteğe Bağlı|Hayır|  
|[IDBCreateCommand](https://msdn.microsoft.com/en-us/library/ms711625.aspx)|İsteğe Bağlı|Evet|  
|[IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)|İsteğe Bağlı|Evet|  
|[IIndexDefinition](https://msdn.microsoft.com/en-us/library/ms711593.aspx)|İsteğe Bağlı|Hayır|  
|[ISupportErrorInfo](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|İsteğe Bağlı|Evet|  
|[ITableCreation](https://msdn.microsoft.com/en-us/library/ms713639.aspx)|İsteğe Bağlı|Hayır|  
|[ITableDefinition](https://msdn.microsoft.com/en-us/library/ms714277.aspx)|İsteğe Bağlı|Hayır|  
|[ITableDefinitionWithConstraints](https://msdn.microsoft.com/en-us/library/ms720947.aspx)|İsteğe Bağlı|Hayır|  
|[ITransaction](https://msdn.microsoft.com/en-us/library/ms723053.aspx)|İsteğe Bağlı|Hayır|  
|[ITransactionJoin'i](https://msdn.microsoft.com/en-us/library/ms718071.aspx)|İsteğe Bağlı|Hayır|  
|[ITransactionLocal](https://msdn.microsoft.com/en-us/library/ms714893.aspx)|İsteğe Bağlı|Hayır|  
|[ITransactionObject](https://msdn.microsoft.com/en-us/library/ms713659.aspx)|İsteğe Bağlı|Hayır|  
  
 Oturum nesnesi bir satır kümesi nesnesi oluşturur. Sağlayıcı komutları destekliyorsa, oturum ayrıca komut nesnesi oluşturur (`CCommand`, OLE DB uygulama **TCommand**). Komut nesnesi uygular `ICommand` arabirimi ve kullandığı `ICommand::Execute` yöntemi aşağıdaki resimde gösterildiği gibi satır kümesi üzerinde komutları yürütün.  
  
 ![Sağlayıcı kavramsal diyagram](../../data/oledb/media/vc4u551.gif "vc4u551")  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)