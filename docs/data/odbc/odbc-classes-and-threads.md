---
title: ODBC Sınıfları ve İş Parçacıkları
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
ms.openlocfilehash: 8cb5df605bef31e177e976798f975bb4ca14ced7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213205"
---
# <a name="odbc-classes-and-threads"></a>ODBC Sınıfları ve İş Parçacıkları

MFC 4,2 ' den başlayarak MFC ODBC sınıfları için çoklu iş parçacıklı destek vardır. Ancak, MFC 'nin DAO sınıfları için çoklu iş parçacıklı destek sağlamayacağını unutmayın.

ODBC sınıfları için çoklu iş parçacığı desteğinin bazı sınırlamaları vardır. Bu sınıflar ODBC API 'sini sardığı için, bunların derlendikleri bileşenlerin çoklu iş parçacıklı desteğiyle kısıtlıdır. Örneğin, birçok ODBC sürücüsü iş parçacığı açısından güvenli değildir; Bu nedenle, MFC ODBC sınıfları bu sürücülerden biriyle kullanıyorsanız iş parçacığı güvenli değildir. Belirli sürücünüzün iş parçacığı açısından güvenli olup olmadığını doğrulamanız gerekir.

Çok iş parçacıklı bir uygulama oluştururken, aynı nesneyi işlemek için birden çok iş parçacığı kullanırken çok dikkatli olmanız gerekir. Örneğin, iki iş parçacığında aynı `CRecordset` nesnesinin kullanılması, verilerin alınması sırasında sorunlara neden olabilir; bir iş parçacığında getirme işlemi, diğer iş parçacığında getirilen verilerin üzerine yazabilir. Ayrı iş parçacıklarında MFC ODBC sınıflarının daha yaygın bir şekilde kullanılması, her iş parçacığında ayrı bir `CRecordset` nesnesi ile aynı ODBC bağlantısını kullanmak için iş parçacıkları arasında açık bir `CDatabase` nesnesini paylaşmaktır. Açılmamış bir `CDatabase` nesnesini başka bir iş parçacığında `CRecordset` nesnesine geçirmemelisiniz.

> [!NOTE]
>  Aynı nesneyi işleyen birden çok iş parçacığı varsa, kritik bölümler gibi uygun eşitleme mekanizmalarını uygulamanız gerekir. `Open`gibi bazı işlemlerin korunmuyor olduğunu unutmayın. Bu işlemlerin ayrı iş parçacıklarında aynı anda çağrılmayacak olduğundan emin olmanız gerekir.

Çoklu iş parçacıklı uygulamalar oluşturma hakkında daha fazla bilgi için bkz. [Çoklu kullanım konuları](../../parallel/multithreading-support-for-older-code-visual-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Veri erişim programlama (MFC/ATL)](../../data/data-access-programming-mfc-atl.md)
