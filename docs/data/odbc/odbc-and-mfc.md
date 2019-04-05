---
title: ODBC ve MFC
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC [C++], MFC
- connections [C++], databases
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- MFC [C++], ODBC and
- database connections [C++], MFC ODBC classes
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
ms.openlocfilehash: 9b7d04e2eb8bbb1adf96e05282861ef33e20434a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031186"
---
# <a name="odbc-and-mfc"></a>ODBC ve MFC

> [!NOTE]
>  MFC veritabanı sınıflarını kullanmak için uygun ODBC sürücüsünü ve veri kaynağı olmalıdır. SQL Server için en son Microsoft ODBC sürücüsü [SQL Server için Microsoft ODBC sürücüsü 13](https://www.microsoft.com/download/details.aspx?id=50420). Çoğu veritabanı satıcıları, Windows için ODBC sürücüsü sağlar.

Bu konu, Microsoft Foundation Classes (MFC) Kitaplığı'nızın ODBC tabanlı veritabanı sınıflarını temel konseptlerini tanıtan ve sınıfları birlikte nasıl çalıştığını genel bir bakış sağlar. ODBC ve MFC hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [Veri Kaynağına Bağlanma](connecting-to-a-data-source.md)

- [Kayıtları Seçme ve Düzenleme](selecting-and-manipulating-records.md)

- [Formdaki Verileri Görüntüleme ve Düzenleme](displaying-and-manipulating-data-in-a-form.md)

- [Belgeler ve görünümler ile çalışma](working-with-documents-and-views.md)

- [ODBC'ye ve SQL'e Erişim](access-to-odbc-and-sql.md)

- [MFC ODBC Sınıfları Hakkında Daha Fazla Okuma](further-reading-about-the-mfc-odbc-classes.md)

ODBC tabanlı MFC veritabanı sınıfları, ODBC sürücüsü kullanılabilir herhangi bir veritabanına erişim sağlamak için tasarlanmıştır. ODBC sınıfları kullanması için uygulama birçok farklı veri biçimlerini ve farklı yerel/uzak yapılandırmaları olan verilere erişebilir. Farklı veritabanı yönetim sistemi (DBMS) işlemek için özel durum kod yazmanız gerekmez. Kullanıcılarınızın erişmek istediğiniz veriler için uygun bir ODBC sürücüsüne sahip olduğu sürece, tablolarda depolanan verileri işlemek için programınızı kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](open-database-connectivity-odbc.md)