---
title: "Bir veri kaynağına bağlanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- database connections [C++], ODBC
- ODBC connections [C++], using
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ea788921b72d06deb44ed67ecdfa49c5efe43ed2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="connecting-to-a-data-source"></a>Veri Kaynağına Bağlanma
ODBC veri kaynağını veri, bu verileri ve veri kaynağı adı kullanılarak tanımlanabilir veri kaynağının konumunu erişmek için gerekli bilgileri belirli bir kümesidir. Programınızın açısından bakıldığında, verileri, DBMS, ağ (varsa) ve ODBC veri kaynağını içerir.  
  
 Bir veri kaynağı tarafından sağlanan verilere erişmek için program ilk veri kaynağına bağlantı oluşturmanız gerekir. Tüm veri erişimi Bu bağlantı üzerinden yönetilir.  
  
 Veri kaynağı bağlantıları sınıfı tarafından kapsüllenmiş [CDatabase](../../mfc/reference/cdatabase-class.md). Zaman bir `CDatabase` nesne bir veri kaynağına bağlı olduğundan, aşağıdakileri yapabilirsiniz:  
  
-   Oluşturmak [kayıt kümeleri](../../mfc/reference/crecordset-class.md), tablo veya sorgu kayıtları seçin.  
  
-   Yönetme [işlemleri](../../data/odbc/transaction-odbc.md), toplu güncelleştirmeler için tüm veri kaynağına kaydedilmiş aynı anda (veya tüm işlem geri veri kaynağına bağlanacak şekilde alınır) — veri kaynağı gerekli işlem düzeyini destekliyorsa.  
  
-   Doğrudan yürütme [SQL](../../data/odbc/sql.md) deyimleri.  
  
 Veri kaynağı bağlantısı ile çalışmayı bitirdiğinizde, kapatmak `CDatabase` nesne ve onu yok veya yeni bir bağlantı için yeniden kullanabilirsiniz. Veri kaynağı bağlantıları hakkında daha fazla bilgi için bkz: [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ODBC ve MFC](../../data/odbc/odbc-and-mfc.md)