---
title: "Birden çok iş parçacıklı kitaplık performansı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- threading [C++], performance
- libraries, multithreaded
- performance, multithreading
- multithreaded libraries
ms.assetid: faa5d808-087c-463d-8f0d-8c478d137296
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8eeadc61c41d37247b08bdc8e3806da6d6200e4a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="multithreaded-libraries-performance"></a>Çok İş Parçacıklı Kitaplık Performansı
Tek iş parçacıklı CRT artık kullanılamıyor. Bu konuda en yüksek performans birden çok iş parçacıklı kitaplıklarından alma anlatılmaktadır.  
  
## <a name="maximizing-performance"></a>Performansı en üst düzeye çıkarma  
 Çok iş parçacıklı kitaplık performansı geliştirilmiştir ve şimdi ortadan tek iş parçacıklı kitaplıklar performansı yakın. Bu durumlar için daha yüksek performans gerektiğinde birkaç yeni özellikler vardır.  
  
-   Bağımsız akış kilitleme bir akış kilitlemek ve sonra da olanak tanır [_nolock işlevleri](../c-runtime-library/nolock-functions.md) doğrudan akış erişim. Bu kritik döngüler dışında hoisted kilit kullanımına izin verir.  
  
-   İş parçacığı başına yerel ayar birden çok iş parçacıklı senaryoları için yerel erişim maliyetini azaltır (bkz [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)).  
  
-   Yerel ayara bağımlı işlevleriyle (ad) içinde _l bitiş önemli maliyet kaldırma bir parametre olarak yerel olması (örneğin, [printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)).  
  
-   İyileştirmeler ortak kod sayfaları için çok kısa işlemlerinin maliyetini azaltır.  
  
-   Tanımlama [_crt_dısable_perfcrıt_locks](../c-runtime-library/crt-disable-perfcrit-locks.md) bir tek iş parçacıklı g/ç modeli varsayar ve işlevlerin _nolock forms kullanmak için tüm g/ç işlemleri zorlar. Bu, daha iyi performans almak üzere tek iş parçacıklı uygulamalar yüksek oranda g/Ç tabanlı sağlar.  
  
-   CRT yığın tanıtıcısı riskini Windows Düşük Parçalanma Yığın (LFH) yüksek oranda ölçeklendirilmiş senaryolarda performansı önemli ölçüde artırabilir CRT öbek için etkinleştirmenize olanak sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md)