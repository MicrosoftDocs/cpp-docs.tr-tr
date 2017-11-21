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
ms.openlocfilehash: 3dff3b8a7041c24f5becedb207b1aa9a9193afbf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="converting-data-not-supported-by-the-provider"></a>Sağlayıcı Tarafından Desteklenmeyen Veriyi Dönüştürme
Tüketici sağlayıcı tarafından desteklenmeyen bir veri türü istediğinde, OLE DB sağlayıcı şablonu için kodunu `IRowsetImpl::GetData` veri türüne dönüştürmek için Msdadc.dll çağırır.  
  
 Gibi bir arabirim uygularsanız `IRowsetChange` veri dönüştürme gerektiren, dönüştürme yapmak için Msdaenum.dll çağırabilirsiniz. Kullanım `GetData`, örnek olarak Atldb.h tanımlı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)