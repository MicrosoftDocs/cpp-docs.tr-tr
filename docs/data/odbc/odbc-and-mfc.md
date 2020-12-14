---
description: 'Daha fazla bilgi edinin: ODBC ve MFC'
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
ms.openlocfilehash: 32cc3f9a023a4b965e8872fde27291bf8df3f1a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195105"
---
# <a name="odbc-and-mfc"></a>ODBC ve MFC

> [!NOTE]
> MFC veritabanı sınıflarını kullanmak için, veri kaynağınız için uygun ODBC sürücüsüne sahip olmanız gerekir. SQL Server için olan son Microsoft ODBC sürücüsü, [SQL Server için Microsoft ODBC sürücüsü 13](https://www.microsoft.com/download/details.aspx?id=50420)' dir. Çoğu veritabanı satıcısı, Windows için bir ODBC sürücüsü sağlar.

Bu konu, Microsoft Foundation Sınıfları (MFC) kitaplığının ODBC tabanlı veritabanı sınıflarının ana kavramlarını tanıtır ve sınıfların birlikte nasıl çalışabileceğine ilişkin bir genel bakış sağlar. ODBC ve MFC hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [Bir veri kaynağına bağlanma](connecting-to-a-data-source.md)

- [Kayıtları seçme ve düzenleme](selecting-and-manipulating-records.md)

- [Formdaki verileri görüntüleme ve düzenleme](displaying-and-manipulating-data-in-a-form.md)

- [Belgeler ve görünümler ile çalışma](working-with-documents-and-views.md)

- [ODBC'ye ve SQL'e Erişim](access-to-odbc-and-sql.md)

- [MFC ODBC sınıfları hakkında daha fazla okuma](further-reading-about-the-mfc-odbc-classes.md)

ODBC tabanlı MFC veritabanı sınıfları, ODBC sürücüsünün kullanılabildiği herhangi bir veritabanına erişim sağlamak için tasarlanmıştır. Sınıflar ODBC kullandığından, uygulamanız birçok farklı veri biçiminde ve farklı yerel/uzak yapılandırmalarda verilere erişebilir. Farklı veritabanı yönetim sistemlerini (DBMS) işlemek için özel durum kodu yazmanız gerekmez. Kullanıcılarınız erişmek istedikleri veriler için uygun bir ODBC sürücüsüne sahip olduğu sürece, burada depolanan tablolardaki verileri işlemek için programınızı kullanabilirler.

## <a name="see-also"></a>Ayrıca bkz.

[Açık veritabanı bağlantısı (ODBC)](open-database-connectivity-odbc.md)
