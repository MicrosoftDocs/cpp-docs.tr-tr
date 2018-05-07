---
title: ODBC ve veritabanı sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: abbb20b76f8e24a9b0f20961728dd8e428733654
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="odbc-and-the-database-classes"></a>ODBC ve Veritabanı Sınıfları
MFC ODBC veritabanı sınıfları normalde yaptığınız kendiniz üye işlevlerini ODBC API işlev çağrılarını kapsüller [CDatabase](../../mfc/reference/cdatabase-class.md) ve [CRecordset](../../mfc/reference/crecordset-class.md) sınıfları. Örneğin, karmaşık ODBC çağrı sıraları, depolama konumları, hata koşullarını işleme ve diğer işlemler için döndürülen kayıtların bağlama sizin için veritabanı sınıfları tarafından yönetilir. Sonuç olarak, bir kayıt kümesi nesnesi kayıtlarda işlemek için önemli ölçüde daha basit bir sınıf arabirimi kullanın.  
  
> [!NOTE]
>  ODBC veri kaynakları, MFC veri erişim nesnesi (DAO) sınıfları veya bu konu başlığı altında açıklandığı gibi MFC ODBC sınıfları üzerinden erişilebilir.  
  
 Veritabanı sınıfları ODBC işlevleri kapsülleyen rağmen bire bir eşleme ODBC API işlevleri sağlamaz. Veritabanı sınıfları veri erişim nesneleri Microsoft Access ve Microsoft Visual Basic'te bulunduktan sonra Modellenen soyutlama, daha yüksek düzeyde sağlar. Daha fazla bilgi için bkz: [ODBC ve MFC](../../data/odbc/odbc-and-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ODBC Temelleri](../../data/odbc/odbc-basics.md)