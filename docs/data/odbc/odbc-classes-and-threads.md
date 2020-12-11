---
description: 'Daha fazla bilgi edinin: ODBC sınıfları ve Iş parçacıkları'
title: ODBC Sınıfları ve İş Parçacıkları
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
ms.openlocfilehash: bff5ef5a53543b2e0ffa7888f469ed4ce1e54a37
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161085"
---
# <a name="odbc-classes-and-threads"></a>ODBC Sınıfları ve İş Parçacıkları

MFC 4,2 ' den başlayarak MFC ODBC sınıfları için çoklu iş parçacıklı destek vardır. Ancak, MFC 'nin DAO sınıfları için çoklu iş parçacıklı destek sağlamayacağını unutmayın.

ODBC sınıfları için çoklu iş parçacığı desteğinin bazı sınırlamaları vardır. Bu sınıflar ODBC API 'sini sardığı için, bunların derlendikleri bileşenlerin çoklu iş parçacıklı desteğiyle kısıtlıdır. Örneğin, birçok ODBC sürücüsü iş parçacığı açısından güvenli değildir; Bu nedenle, MFC ODBC sınıfları bu sürücülerden biriyle kullanıyorsanız iş parçacığı güvenli değildir. Belirli sürücünüzün iş parçacığı açısından güvenli olup olmadığını doğrulamanız gerekir.

Çok iş parçacıklı bir uygulama oluştururken, aynı nesneyi işlemek için birden çok iş parçacığı kullanırken çok dikkatli olmanız gerekir. Örneğin, `CRecordset` iki iş parçacığında aynı nesnenin kullanılması veri alınırken sorunlara neden olabilir; bir iş parçacığında bir getirme işlemi, diğer iş parçacığında getirilen verilerin üzerine yazabilir. MFC ODBC sınıflarının ayrı iş parçacıklarında daha yaygın bir şekilde kullanılması, `CDatabase` her iş parçacığında ayrı bir nesne ile aynı ODBC bağlantısını kullanmak üzere iş parçacıkları arasında açık bir nesne paylaşmaktır `CRecordset` . Açık olmayan bir `CDatabase` nesneyi `CRecordset` başka bir iş parçacığındaki bir nesneye geçirmemelisiniz.

> [!NOTE]
> Aynı nesneyi işleyen birden çok iş parçacığı varsa, kritik bölümler gibi uygun eşitleme mekanizmalarını uygulamanız gerekir. Gibi bazı işlemlerin korunmuyor olduğunu unutmayın `Open` . Bu işlemlerin ayrı iş parçacıklarında aynı anda çağrılmayacak olduğundan emin olmanız gerekir.

Çoklu iş parçacıklı uygulamalar oluşturma hakkında daha fazla bilgi için bkz. [Çoklu kullanım konuları](../../parallel/multithreading-support-for-older-code-visual-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Açık veritabanı bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Veri erişim programlama (MFC/ATL)](../../data/data-access-programming-mfc-atl.md)
