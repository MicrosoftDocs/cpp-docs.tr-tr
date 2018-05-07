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
ms.openlocfilehash: dedd1f03bf14e0513f9f76a1e292b9180e4d60db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="odbc-classes-and-threads"></a>ODBC Sınıfları ve İş Parçacıkları
MFC 4.2 ile başlayarak, MFC ODBC sınıfları için çoklu iş parçacığı desteği yoktur. Ancak, MFC DAO sınıflarını çoklu iş parçacığı destek sağlamaz unutmayın.  
  
 ODBC sınıfları için çoklu iş parçacığı destek bazı sınırlamaları vardır. Bu sınıfların ODBC API sarmalamak çünkü bunlar yerleşik olan bileşenleri çoklu iş parçacığı destek sınırlıdır. Örneğin, birçok ODBC sürücüsü iş parçacığı açısından güvenli değildir; Bu nedenle, MFC ODBC sınıfları, bunları bu sürücüleri biri ile kullanıyorsanız, iş parçacığı açısından güvenli değildir. Belirli sürücünüzün iş parçacığı açısından güvenli olup olmadığını doğrulamalıdır.  
  
 Birden çok iş parçacıklı bir uygulama oluştururken, aynı nesneyi işlemek için birden çok iş parçacığı kullanırken çok dikkatli olmalıdır. Örneğin, aynı kullanarak `CRecordset` verileri alırken, iki iş parçacığı nesnesinde sorunlara neden; bir iş parçacığında getirme işlemi içinde başka bir iş parçacığı alınan verilerin üzerine yazılmasına neden olabilir. Açık bir paylaşmak için ayrı iş parçacıklarındaki MFC ODBC sınıfları daha yaygın bir kullanımdır `CDatabase` nesne aynı ODBC bağlantısı ayrı bir iş parçacığı boyunca `CRecordset` her bir iş parçacığı nesnesi. Açılmamış bir geçirdiğiniz değil, Not `CDatabase` nesnesine bir `CRecordset` başka bir iş parçacığı nesne.  
  
> [!NOTE]
>  Birden çok iş parçacığı aynı nesneyi işlemek görüntülenmesi gerekiyorsa, kritik bölümler gibi uygun eşitleme mekanizmaları uygulamanız gerekir. Unutmayın, bazı işlemleri gibi **açık**, korumalı olmayan. Bu işlemler aynı anda ayrı iş parçacığı tarafından çağrılmaz emin olmanız gerekir.  
  
 Birden çok iş parçacıklı uygulamalar oluşturma hakkında daha fazla bilgi için bkz: [çoklu iş parçacığı kullanımı konuları](../../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık veritabanı bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Veri erişimi (MFC/ATL) programlama](../../data/data-access-programming-mfc-atl.md)