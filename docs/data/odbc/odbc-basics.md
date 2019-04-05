---
title: ODBC Temelleri
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC cursor library [ODBC], ODBC components
- ODBC components
- ODBC components, required components
- ODBC, about ODBC
- ODBC, components
ms.assetid: ec529702-0fb2-4754-b8de-d1efa8eca18f
ms.openlocfilehash: e14f5d051b9684cd79a34f5fb50feeb785d2f927
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033248"
---
# <a name="odbc-basics"></a>ODBC Temelleri

Bu konu, açık veritabanı bağlantısı (ODBC) hakkındaki temel bilgileri sağlar:

- [ODBC veritabanı sınıfları ile nasıl çalışır?](../../data/odbc/odbc-and-the-database-classes.md)

- [ODBC sürücüleri kümelerle nasıl çalışır?](../../data/odbc/odbc-driver-requirements-for-dynasets.md)

- [Hangi ODBC bileşenleri ile uygulamalarınızı yeniden dağıtmanız gerekir](../../data/odbc/redistributing-odbc-components-to-your-customers.md)

İlgili konu okumak isteyeceksiniz [ODBC: ODBC İmleç Kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md).

> [!NOTE]
> ODBC veri kaynakları, veri erişim nesnesi (DAO) MFC sınıfları veya bu konuda açıklandığı gibi MFC ODBC sınıfları aracılığıyla erişilebilir.

> [!NOTE]
> MFC ODBC sınıfları Unicode desteği ve çoklu iş parçacığı kullanımı. Çoklu iş parçacığı desteği hakkında daha fazla bilgi için bkz. [ODBC sınıfları ve iş parçacıkları](../../data/odbc/odbc-classes-and-threads.md)

ODBC uygulamaları ODBC sürücüsü tüm veritabanı verilere erişmek izin veren bir çağrı düzeyi arabirimidir. ODBC kullanarak, son kullanıcınızın bir ODBC sürücüsüne sahip olan herhangi bir veritabanına erişim ile veritabanı uygulamaları oluşturabilirsiniz. ODBC, uygulamanızın kaynak veritabanı yönetim sistemi (DBMS) bağımsız olmasını sağlayan bir API sağlar.

ODBC veritabanı, Microsoft Windows açık Hizmetleri mimarisi (WOSA), her platform için uygulama yeniden yazma olmadan birden çok bilgi işlem ortamları için bağlanmak masaüstü uygulamalarının Windows tabanlı bir arabirimi olan bölümüdür.

ODBC bileşenleri şunlardır:

- ODBC API

   Bir işlev kitaplığının çağrıları, bir dizi hata kodları ve standart [SQL](../../data/odbc/sql.md) DBMS şirket verilerine erişmek için söz dizimi.

- ODBC Sürücü Yöneticisi

   ODBC veritabanı sürücülerini yükleyen bir uygulama adına bir dinamik bağlantı kitaplığı (Odbc32.dll). Bu DLL, uygulamanız için saydamdır.

- ODBC veritabanı sürücüleri

   Belirli DBMS için ODBC işlev çağrılarını işleyen bir veya daha fazla dll dosyaları. Sağlanan sürücülerin bir listesi için bkz. [ODBC sürücü listesi](../../data/odbc/odbc-driver-list.md).

- [ODBC imleç kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md)

   ODBC Sürücü Yöneticisi ve sürücüleri arasında bulunan ve verilerine kaydırma işleyen bir dinamik bağlantı kitaplığı (Odbccr32.dll).

- [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md)

   Bir uygulama için veri kaynağı olarak kullanılabilir hale getirmek için DBMS yapılandırmak için kullanılan araç.

Bir uygulama DBMS ile doğrudan çalışmak yerine, özellikle DBMS için yazılmış bir ODBC sürücüsü ile çalışma alanından DBMS bağımsızlığı elde eder. Sürücü Geliştirici iş basitleştirme ve çok çeşitli veri kaynakları için kullanılabilir hale getirme kendi DBMS kullanabilirsiniz komutları çağırıyor çevirir.

Veritabanı sınıfları için ODBC sürücüsü olan herhangi bir veri kaynağını destekler. Bu örneğin, bir ilişkisel veritabanı, dizinli sıralı erişim yöntemi (ISAM) veritabanı, Microsoft Excel elektronik tablosu veya bir metin dosyası içerebilir. ODBC sürücüleri veri kaynağı bağlantılarını yönetmek ve SQL veritabanından kayıtları seçmek için kullanılır.

Visual C++'ın bu sürümünde bulunan ODBC sürücülerinin listesini ve ek sürücüler hakkında bilgi için bkz: [ODBC sürücü listesi](../../data/odbc/odbc-driver-list.md).

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)