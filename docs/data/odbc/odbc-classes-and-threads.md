---
title: ODBC sınıfları ve iş parçacıkları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0a7b78284b1fc0bd952928952c24c61423396eb2
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39341055"
---
# <a name="odbc-classes-and-threads"></a>ODBC Sınıfları ve İş Parçacıkları
MFC 4.2 ile başlayarak, MFC ODBC sınıfları için çoklu iş parçacığı desteği yoktur. Ancak, MFC DAO sınıflarını çoklu iş parçacığı destek sağlamaz unutmayın.  
  
 ODBC sınıfları için çoklu iş parçacığı destek bazı sınırlamaları vardır. ODBC API bu sınıfları sarmalamak çünkü bunlar yerleşik olan bileşenlerin çoklu iş parçacığı destek sınırlıdır. Örneğin, birçok ODBC sürücüleri iş parçacığı açısından güvenli değildir; MFC ODBC sınıfları bu nedenle, bunları bu sürücüleri birini kullanırsanız iş parçacığı açısından güvenli değildir. Belirli bir sürücüyü iş parçacığı açısından güvenli olup olmadığını doğrulamalısınız.  
  
 Çok iş parçacıklı bir uygulama oluştururken, aynı nesneyi işlemek için birden çok iş parçacığı kullanan çok dikkatli olmanız gerekir. Örneğin, aynı kullanarak `CRecordset` verileri alırken, iki iş parçacığı nesnesi sorunlara neden; bir iş parçacığındaki bir getirme işlemi diğer iş parçacığında getirilen verilerin üzerine yazılmasına neden olabilir. Ayrı iş parçacıklarındaki MFC ODBC sınıfları için daha yaygın bir kullanım açık paylaşmaktır `CDatabase` aynı ODBC bağlantısı, ayrı bir iş parçacığı arasında nesne `CRecordset` her iş parçacığı nesnesi. Bir açılmamış geçirmeniz değil olduğunu unutmayın `CDatabase` nesnesini bir `CRecordset` başka bir iş parçacığı nesnesi.  
  
> [!NOTE]
>  Birden çok iş parçacığı aynı nesne işlemek görüntülenmesi gerekiyorsa, kritik bölüm gibi uygun eşitleme mekanizmaları uygulamalıdır. Unutmayın, belirli işlemleri gibi `Open`, korumalı olmayan. Bu işlemler aynı anda farklı iş parçacıklarından çağrılmayacak emin olmanız gerekir.  
  
 Çok iş parçacıklı uygulamalar oluşturma hakkında daha fazla bilgi için bkz. [çoklu iş parçacığı kullanımı konuları](../../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık veritabanı bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Veri erişim programlama (MFC/ATL)](../../data/data-access-programming-mfc-atl.md)