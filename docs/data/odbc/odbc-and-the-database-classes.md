---
title: "ODBC ve veritabanı sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8cf4d5dae14a59cc8b4c6d17ff118cdde59c28af
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="odbc-and-the-database-classes"></a>ODBC ve Veritabanı Sınıfları
MFC ODBC veritabanı sınıfları normalde yaptığınız kendiniz üye işlevlerini ODBC API işlev çağrılarını kapsüller [CDatabase](../../mfc/reference/cdatabase-class.md) ve [CRecordset](../../mfc/reference/crecordset-class.md) sınıfları. Örneğin, karmaşık ODBC çağrı sıraları, depolama konumları, hata koşullarını işleme ve diğer işlemler için döndürülen kayıtların bağlama sizin için veritabanı sınıfları tarafından yönetilir. Sonuç olarak, bir kayıt kümesi nesnesi kayıtlarda işlemek için önemli ölçüde daha basit bir sınıf arabirimi kullanın.  
  
> [!NOTE]
>  ODBC veri kaynakları, MFC veri erişim nesnesi (DAO) sınıfları veya bu konu başlığı altında açıklandığı gibi MFC ODBC sınıfları üzerinden erişilebilir.  
  
 Veritabanı sınıfları ODBC işlevleri kapsülleyen rağmen bire bir eşleme ODBC API işlevleri sağlamaz. Veritabanı sınıfları veri erişim nesneleri Microsoft Access ve Microsoft Visual Basic'te bulunduktan sonra Modellenen soyutlama, daha yüksek düzeyde sağlar. Daha fazla bilgi için bkz: [ODBC ve MFC](../../data/odbc/odbc-and-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ODBC temelleri](../../data/odbc/odbc-basics.md)