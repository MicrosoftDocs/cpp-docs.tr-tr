---
title: ODBC temelleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC cursor library [ODBC], ODBC components
- ODBC components
- ODBC components, required components
- ODBC, about ODBC
- ODBC, components
ms.assetid: ec529702-0fb2-4754-b8de-d1efa8eca18f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 69b3694292171f00e03cdb941def27fd9e8ffc84
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="odbc-basics"></a>ODBC Temelleri
Bu konu, açık veritabanı bağlantısı (ODBC) temel bilgileri sağlar:  
  
-   [ODBC ile veritabanı sınıflarını nasıl çalışır?](../../data/odbc/odbc-and-the-database-classes.md)  
  
-   [ODBC sürücüleri kümelerle nasıl çalışır?](../../data/odbc/odbc-driver-requirements-for-dynasets.md)  
  
-   [Hangi ODBC bileşenlerini uygulamalarınızla yeniden dağıtmanız gerekir](../../data/odbc/redistributing-odbc-components-to-your-customers.md)  
  
 İlgili konu okuma isteyeceksiniz [ODBC: ODBC İmleç Kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
> [!NOTE]
>  ODBC veri kaynakları, MFC veri erişim nesnesi (DAO) sınıfları veya bu konu başlığı altında açıklandığı gibi MFC ODBC sınıfları üzerinden erişilebilir.  
  
> [!NOTE]
>  MFC ODBC sınıfları Unicode destekler ve çoklu iş parçacığı kullanımı. Çoklu iş parçacığı desteği hakkında daha fazla bilgi için bkz: [ODBC sınıfları ve iş parçacıkları](../../data/odbc/odbc-classes-and-threads.md)  
  
 ODBC uygulamaların var olduğu bir ODBC sürücüsü herhangi bir veritabanındaki verilere erişmesine izin veren bir çağrı düzeyi arabirimidir. ODBC kullanarak, son kullanıcı herhangi bir veritabanı için bir ODBC sürücüsüne sahip olduğu erişim ile veritabanı uygulamaları oluşturabilirsiniz. ODBC uygulamanızın kaynak veritabanı yönetim sistemi (DBMS) bağımsız olmasını sağlayan bir API sağlar.  
  
 ODBC veritabanı, Microsoft Windows açık hizmetler mimarisi (WOSA), her platform için uygulama yeniden yazma işlemi birden çok bilgisayar ortamlara bağlanacak şekilde Masaüstü uygulamaları Windows tabanlı bir arabirimi olan bölümüdür.  
  
 ODBC bileşenleri şunlardır:  
  
-   ODBC API  
  
     Bir kitaplık işlevinin çağrıları, bir dizi hata kodları ve standart bir [SQL](../../data/odbc/sql.md) DBMS verilerine erişmek için söz dizimi.  
  
-   ODBC Sürücü Yöneticisi  
  
     Bir uygulama adına ODBC veritabanı sürücülerini yükleyen bir dinamik bağlantı kitaplığı (Odbc32.dll). Bu DLL, uygulamanız için saydamdır.  
  
-   ODBC veritabanı sürücüleri  
  
     Belirli DBMS için ODBC işlev çağrılarını işleyen bir veya daha fazla dll dosyaları. Sağlanan sürücülerin bir listesi için bkz: [ODBC sürücü listesi](../../data/odbc/odbc-driver-list.md).  
  
-   [ODBC imleç kitaplığı](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
     ODBC Sürücü Yöneticisi ve sürücüleri arasında bulunan ve verilerine kaydırma işleyen bir dinamik bağlantı kitaplığı (Odbccr32.dll).  
  
-   [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md)  
  
     Bir uygulama için bir veri kaynağı olarak kullanılabilir hale getirmek için bir DBMS yapılandırmak için kullanılan araç.  
  
 Bir uygulama DBMS ile doğrudan çalışmak yerine, özellikle DBMS için yazılmış bir ODBC sürücüsü ile çalışma alanından DBMS bağımsızlığı erişir. Sürücü Geliştirici çalışma basitleştirme ve çok çeşitli veri kaynakları için kullanılabilir hale getirme kendi DBMS kullanabileceğiniz komutlar çağrılarını çevirir.  
  
 Veritabanı sınıfları ODBC sürücüsü olan herhangi bir veri kaynağını destekler. Bu örneğin, bir ilişkisel veritabanı, bir dizine sıralı erişim yöntemi (ISAM) veritabanı, Microsoft Excel elektronik tablosu veya bir metin dosyası içerebilir. ODBC sürücüleri veri kaynağı bağlantılarını yönetmek ve SQL veritabanından kayıtları seçmek için kullanılır.  
  
 Visual C++'ın bu sürümünde bulunan sürücülerin listesini ve ek sürücüler edinme hakkında bilgi için bkz: [ODBC sürücü listesi](../../data/odbc/odbc-driver-list.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)