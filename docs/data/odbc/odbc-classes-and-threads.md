---
title: ODBC Sınıfları ve İş Parçacıkları
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
ms.openlocfilehash: aaf54a3a1d616cde5742dad45955bd415f612d60
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368696"
---
# <a name="odbc-classes-and-threads"></a>ODBC Sınıfları ve İş Parçacıkları

MFC 4.2 ile başlayarak, MFC ODBC sınıfları için çok iş parçacığı desteği vardır. Ancak, MFC'nin DAO sınıfları için çok iş parçacığı desteği sağlamadığını unutmayın.

ODBC sınıfları için çok iş parçacığı desteği bazı sınırlamalar vardır. Bu sınıflar ODBC API'sini sardığından, üzerinde üretildikleri bileşenlerin çok iş parçacığı desteğiyle sınırlıdır. Örneğin, birçok ODBC sürücüsü iş parçacığı için güvenli değildir; bu nedenle, bu sürücülerden biriyle kullanırsanız MFC ODBC sınıfları iş parçacığı için güvenli değildir. Belirli bir sürücünün iş parçacığı için güvenli olup olmadığını doğrulamanız gerekir.

Çok iş parçacığı uygulaması oluştururken, aynı nesneyi işlemek için birden çok iş parçacığı kullanırken çok dikkatli olmalısınız. Örneğin, iki iş `CRecordset` parçacığı aynı nesnenin kullanılması veri alırken sorunlara neden olabilir; bir iş parçacığı bir getir işlemi diğer iş parçacığı getirilen verileri üzerine yazabilirsiniz. MFC ODBC sınıflarının ayrı iş parçacıklarında daha yaygın `CDatabase` kullanımı, her iş parçacığında ayrı `CRecordset` bir nesneyle aynı ODBC bağlantısını kullanmak için açık bir nesneyi iş parçacıkları arasında paylaşmaktır. Açılmamış `CDatabase` bir nesneyi başka bir `CRecordset` iş parçacığındaki bir nesneye geçirmemeniz gerektiğini unutmayın.

> [!NOTE]
> Aynı nesneyi birden çok iş parçacığının işlemesi gerekiyorsa, kritik bölümler gibi uygun eşitleme mekanizmalarını uygulamanız gerekir. Belirli işlemlerin `Open`korunmadığını unutmayın. Bu işlemlerin aynı anda ayrı iş parçacıklarından çağrılmadığından emin olmalısınız.

Çok iş parçacığı uygulamaları oluşturma hakkında daha fazla bilgi için, [Multithreading Konular](../../parallel/multithreading-support-for-older-code-visual-cpp.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Veri Erişim Programlama (MFC/ATL)](../../data/data-access-programming-mfc-atl.md)
