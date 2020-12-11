---
description: 'Daha fazla bilgi edinin: ODBC temelleri'
title: ODBC Temelleri
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC cursor library [ODBC], ODBC components
- ODBC components
- ODBC components, required components
- ODBC, about ODBC
- ODBC, components
ms.assetid: ec529702-0fb2-4754-b8de-d1efa8eca18f
ms.openlocfilehash: 94482abd046645e445ffae7f85f192514f4fff78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161188"
---
# <a name="odbc-basics"></a>ODBC Temelleri

Bu konu, açık veritabanı bağlantısı (ODBC) hakkında temel bilgileri sağlar:

- [ODBC 'nin veritabanı sınıflarıyla nasıl çalıştığı](../../data/odbc/odbc-and-the-database-classes.md)

- [ODBC sürücüleri dinamik kümeler ile nasıl çalışır?](../../data/odbc/odbc-driver-requirements-for-dynasets.md)

- [Uygulamalarınızla birlikte dağıtmanız gereken ODBC bileşenleri](../../data/odbc/redistributing-odbc-components-to-your-customers.md)

Ayrıca, ODBC [Imleç kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md)olan ilişkili konu başlığını da okumak isteyeceksiniz.

> [!NOTE]
> ODBC veri kaynaklarına, bu konuda açıklandığı gibi MFC ODBC sınıfları aracılığıyla veya MFC veri erişim nesnesi (DAO) sınıfları aracılığıyla erişilebilir.

> [!NOTE]
> MFC ODBC sınıfları Unicode ve çoklu iş parçacığı oluşturmayı destekler. Çoklu iş parçacığı desteği hakkında daha fazla bilgi için bkz. [ODBC sınıfları ve Iş parçacıkları](../../data/odbc/odbc-classes-and-threads.md)

ODBC, uygulamaların bir ODBC sürücüsü olan herhangi bir veritabanındaki verilere erişmesine olanak tanıyan bir çağrı düzeyi arabirimidir. ODBC kullanarak, son kullanıcılarınızın bir ODBC sürücüsüne sahip olduğu herhangi bir veritabanına erişimi olan veritabanı uygulamaları oluşturabilirsiniz. ODBC, uygulamanızın kaynak veritabanı yönetim sistemi 'nden (DBMS) bağımsız olmasını sağlayan bir API sağlar.

ODBC, Windows tabanlı masaüstü uygulamalarının her platform için uygulamayı yeniden yazmadan birden çok bilgi işlem ortamına bağlanmasına izin veren bir arabirim olan Microsoft Windows açık hizmetler mimarisinin (WOSA) veritabanı bölümüdür.

ODBC bileşenleri aşağıda verilmiştir:

- ODBC APı 'SI

   İşlev çağrılarının bir kitaplığı, bir hata kodları kümesi ve DBMS 'ler üzerindeki verilere erişmek için standart bir [SQL](../../data/odbc/sql.md) söz dizimi.

- ODBC Sürücü Yöneticisi

   ODBC veritabanı sürücülerini uygulama adına yükleyen bir dinamik bağlantı kitaplığı (Odbc32.dll). Bu DLL, uygulamanız için saydamdır.

- ODBC veritabanı sürücüleri

   Belirli DBMS 'Ler için ODBC işlev çağrılarını işleyen bir veya daha fazla dll. Sağlanan sürücülerin listesi için bkz. [ODBC sürücü listesi](../../data/odbc/odbc-driver-list.md).

- [ODBC Imleç kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md)

   ODBC Sürücü Yöneticisi ile sürücüler arasında bulunan dinamik bağlantı kitaplığı (Odbccr32.dll) ve veriler arasında kaydırma gerçekleştirir.

- [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md)

   Bir uygulama için veri kaynağı olarak kullanılabilir hale getirmek üzere bir DBMS yapılandırmak için kullanılan bir araç.

Uygulama, doğrudan DBMS ile çalışmak yerine DBMS için yazılmış bir ODBC sürücüsü üzerinden çalışarak, DBMS 'lerden bağımsız bir şekilde erişir. Sürücü, DBMS 'nin kullanabileceği komutlara çağrı yapar, geliştirici işini basitleştirir ve çok çeşitli veri kaynakları için kullanılabilir hale getirir.

Veritabanı sınıfları, ODBC sürücünüze sahip olduğunuz tüm veri kaynaklarını destekler. Bu, örneğin, ilişkisel bir veritabanı, dizinli sıralı erişim yöntemi (ISAM) veritabanı, Microsoft Excel elektronik tablosu veya metin dosyası içerebilir. ODBC sürücüleri veri kaynağıyla bağlantıları yönetir ve SQL, veritabanından kayıtları seçmek için kullanılır.

Bu Visual C++ sürümünde yer alan ODBC sürücülerinin bir listesi ve ek sürücü alma hakkında bilgi için bkz. [ODBC sürücü listesi](../../data/odbc/odbc-driver-list.md).

## <a name="see-also"></a>Ayrıca bkz.

[Açık veritabanı bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
