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
ms.openlocfilehash: 38a625c73a17ecae4d8adc61e8c56bc4bdda67f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320079"
---
# <a name="odbc-and-mfc"></a>ODBC ve MFC

> [!NOTE]
> MFC veritabanı sınıflarını kullanmak için, veri kaynağınız için uygun ODBC sürücüsüne sahip olmalısınız. SQL Server için en son Microsoft ODBC sürücüsü [SQL Server için Microsoft ODBC Driver 13'tur.](https://www.microsoft.com/download/details.aspx?id=50420) Çoğu veritabanı satıcısı Windows için bir ODBC sürücüsü sağlar.

Bu konu, Microsoft Hazırlık Sınıfları (MFC) kitaplığınodbc tabanlı veritabanı sınıflarının ana kavramlarını tanıtır ve sınıfların birlikte nasıl çalıştığına genel bir bakış sağlar. ODBC ve MFC hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [Veri Kaynağına Bağlanma](connecting-to-a-data-source.md)

- [Kayıtları Seçme ve Düzenleme](selecting-and-manipulating-records.md)

- [Formdaki Verileri Görüntüleme ve Düzenleme](displaying-and-manipulating-data-in-a-form.md)

- [Belgeler ve görünümlerle çalışma](working-with-documents-and-views.md)

- [ODBC'ye ve SQL'e Erişim](access-to-odbc-and-sql.md)

- [MFC ODBC Sınıfları Hakkında Daha Fazla Okuma](further-reading-about-the-mfc-odbc-classes.md)

ODBC'yi temel alan MFC veritabanı sınıfları, ODBC sürücüsünün kullanılabildiği herhangi bir veritabanına erişim sağlamak üzere tasarlanmıştır. Sınıflar ODBC kullandığından, uygulamanız birçok farklı veri biçiminde ve farklı yerel/uzak yapılandırmalarda verilere erişebilir. Farklı veritabanı yönetim sistemlerini (DBMSs) işlemek için özel durum kodu yazmanız gerekmez. Kullanıcılarınız erişmek istedikleri veriler için uygun bir ODBC sürücüsüne sahip oldukları sürece, programınızı burada depolanan tablolardaki verileri işlemek için kullanabilirler.

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](open-database-connectivity-odbc.md)
