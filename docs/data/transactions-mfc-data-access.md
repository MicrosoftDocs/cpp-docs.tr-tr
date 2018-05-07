---
title: İşlemler (MFC veri erişimi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- transactions [C++], support for
- transactions [C++]
- databases [C++], transactions
ms.assetid: f80afbfe-1517-4fec-8870-9ffc70a58b05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9dd531aee6ac8014f2ce47ddee7fc5f82e35a63
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="transactions--mfc-data-access"></a>İşlemler (MFC veri erişimi)
Bir işlemin kavramı, veritabanı sonuç durumuna işlemleri, bir dizi toplam başarı bağlıdır durumları işlemek için geliştirilmiştir. Art arda işlemleri önceki işlemlerinin sonuçlarını değiştirme çünkü bu gelebilir. Herhangi bir işlem başarısız olursa, bu gibi durumlarda, sonuçta elde edilen durumu belirsiz olabilir.  
  
 Bu sorunu çözmek için işlemleri gibi işlemlerde bir dizi Grup nihai sonucu bütünlüğünü garanti şekilde. Tüm işlemlerin başarılı ve ardından (veritabanına yazılan) kaydedilmiş ya da işlemin tamamı başarısız olur. İşlemin iptaline geri alma denir. Geri alma değişikliklerden bir kurtarma sağlar ve veritabanı işlem öncesi durumuna döndürür.  
  
 Örneğin, bir otomatik bankacılık işlemde hesap B A hesabından para aktarırsanız, hem fon doğru şekilde işlemek için bir ve banka hesabından b başarılı olması gerekir veya tüm işlem başarısız olmalıdır.  
  
 Bir işlem, aşağıdakiler için bekleme ACID özellikleri olması gerekir:  
  
-   **Kararlılık** bir işlem atomik bir iş birimidir ve tam bir kez yürütülür; tüm iş yapılır veya hiçbiri.  
  
-   **Tutarlılık** bir işlem başka bir tutarlı bir duruma verilerin tutarlı bir duruma veri dönüştürme veri tutarlılığını korur. Bir işlem tarafından veriye anlamsal olarak korunmalıdır.  
  
-   **Yalıtım** bir işlem yalıtım birimidir ve her ayrı ayrı ve eşzamanlı işlemler bağımsız olarak gerçekleşir. Bir işlem hiçbir zaman başka bir işlem Ara aşamalarını görmeniz gerekir.  
  
-   **Dayanıklılık** bir işlem kurtarma birimidir. Bir işlem başarılı olursa, sistem kilitlenmesine veya kapatılır olsa bile, güncelleştirmelerinin kalır. Bir işlem başarısız olursa, sistem işlemi yapmadan durumda kalır.  
  
 OLE DB'de işlemleri destekleyebilir (bkz [OLE DB'de işlemleri destekleme](../data/oledb/supporting-transactions-in-ole-db.md)) ya da ODBC'yi (bkz [işlem (ODBC)](../data/odbc/transaction-odbc.md)).  
  
 Dağıtılmış işlem Dağıtılmış veri, diğer bir deyişle, verileri birden çok ağa bağlı bilgisayar sisteminde güncelleştiren bir işlemdir. Dağıtılmış bir sistemde işlemleri desteklemek istiyorsanız, OLE DB işlem desteği yerine ADO.NET kullanmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri erişimi (MFC/ATL) programlama](../data/data-access-programming-mfc-atl.md)