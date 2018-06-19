---
title: Bir veri kaynağına bağlanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- database connections [C++], ODBC
- ODBC connections [C++], using
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b6a33f1e2421c56f89184d26185903b4ec7859e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33088397"
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