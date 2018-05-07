---
title: ODBC ve MFC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC [C++], MFC
- connections [C++], databases
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- MFC [C++], ODBC and
- database connections [C++], MFC ODBC classes
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f9ab063bb44d9390442cbf5ad23a60f44f60b3c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="odbc-and-mfc"></a>ODBC ve MFC
> [!NOTE]
>  MFC veritabanı sınıfları kullanmak için veri kaynağınız için uygun ODBC sürücüsünü olması gerekir. SQL Server için en son Microsoft ODBC sürücüsü [SQL Server için Microsoft ODBC sürücüsü 13](https://www.microsoft.com/en-us/download/details.aspx?id=50420). Çoğu veritabanı satıcısı Windows için ODBC sürücüsü sağlayın. 
  
 Bu konu Microsoft Foundation sınıfları (MFC) kitaplığının ODBC tabanlı veritabanı sınıflarını ana kavramları tanıtır ve sınıfları birlikte nasıl çalıştığını genel bir bakış sağlar. ODBC ve MFC hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Veri Kaynağına Bağlanma](connecting-to-a-data-source.md)  
  
-   [Kayıtları Seçme ve Düzenleme](selecting-and-manipulating-records.md)  
  
-   [Formdaki Verileri Görüntüleme ve Düzenleme](displaying-and-manipulating-data-in-a-form.md)  
  
-   [Belgeler ve görünümler ile çalışma](working-with-documents-and-views.md)  
  
-   [ODBC'ye ve SQL'e Erişim](access-to-odbc-and-sql.md)  
  
-   [MFC ODBC Sınıfları Hakkında Daha Fazla Okuma](further-reading-about-the-mfc-odbc-classes.md)  
  
 ODBC tabanlı MFC veritabanı sınıfları ODBC sürücüsü kullanılabilir herhangi bir veritabanına erişim sağlamak için tasarlanmıştır. ODBC sınıfları kullanması için uygulamanızın birçok farklı veri biçimleri ve farklı yerel/uzak yapılandırmaları olan verilere erişebilir. Farklı veritabanı yönetim sistemi (DBMS) işlemek için özel durum kod yazmak zorunda değildir. Kullanıcılarınızın erişim sağlamak istediğiniz veriler için uygun bir ODBC sürücüsüne sahip olduğu sürece, depolanan tablolardaki verileri işlemek için programınızı kullanabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık Veritabanı Bağlantısı (ODBC)](open-database-connectivity-odbc.md)