---
title: "Veri kaynağı (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC data sources, configuring
- CDatabase class, data source connections
- ODBC data sources
- configuring ODBC data sources
- ODBC data sources, represented by CDatabase
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e4276c997069e69d6e84dd4426af4b82c2a839b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="data-source-odbc"></a>Veri Kaynağı (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Veritabanı bağlamında bir özel veri kümesi, bu verileri ve veri kaynağı adı kullanılarak tanımlanabilir veri kaynağının konumunu erişmek için gerekli bilgileri bir veri kaynağıdır. Sınıfıyla çalışmak için [CDatabase](../../mfc/reference/cdatabase-class.md), veri kaynağı açık veritabanı bağlantısı (ODBC) Yöneticisi üzerinden yapılandırılmış olması gerekir. Yerel bir dizinde bir Microsoft Access dosyası ya da ağ üzerinden Microsoft SQL Server çalıştıran uzak bir veritabanı veri kaynakları örneklerindendir. Uygulamanızdan bir ODBC sürücüsü olan herhangi bir veri kaynağını erişebilir.  
  
 Bir veya daha fazla veri kaynakları aynı anda uygulamanızda etkin olabilir, her tarafından temsil edilen bir `CDatabase` nesnesi. Ayrıca, herhangi bir veri kaynağı için birden fazla eşzamanlı bağlantı olabilir. Uzak yanı yüklediğiniz sürücüleri ve ODBC sürücüleri özelliklerine bağlı olarak, yerel veri kaynaklarına bağlanabilirsiniz. Veri kaynakları ve ODBC Yöneticisi hakkında daha fazla bilgi için bkz: [ODBC](../../data/odbc/odbc-basics.md) ve [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md).  
  
 Aşağıdaki konularda, veri kaynakları hakkında daha fazla açıklanır:  
  
-   [Veri Kaynağı: Bağlantıları Yönetme (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)  
  
-   [Veri Kaynağı: Veri Kaynağının Şemasını Belirleme (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)