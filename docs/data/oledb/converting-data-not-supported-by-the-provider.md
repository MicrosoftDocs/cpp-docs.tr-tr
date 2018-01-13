---
title: "Sağlayıcı tarafından desteklenmeyen veriyi dönüştürme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 438d75ad3a36c82c4f9389d4c9b65d677603f6c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="converting-data-not-supported-by-the-provider"></a>Sağlayıcı Tarafından Desteklenmeyen Veriyi Dönüştürme
Tüketici sağlayıcı tarafından desteklenmeyen bir veri türü istediğinde, OLE DB sağlayıcı şablonu için kodunu `IRowsetImpl::GetData` veri türüne dönüştürmek için Msdadc.dll çağırır.  
  
 Gibi bir arabirim uygularsanız `IRowsetChange` veri dönüştürme gerektiren, dönüştürme yapmak için Msdaenum.dll çağırabilirsiniz. Kullanım `GetData`, örnek olarak Atldb.h tanımlı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)