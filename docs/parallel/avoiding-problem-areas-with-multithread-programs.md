---
title: "Çoklu iş parçacığı kullanan programlarda sorun alanlarından kaçınma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- multithreading [C++], troubleshooting
- errors [C++], multithreaded programs
- threading [C++], troubleshooting
- troubleshooting [C++], multithreading
ms.assetid: 06cc231d-bb5a-409d-8bd3-676c9e2a8c5b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9a6722e2cea4141a44bee43a162a73176ce35fea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="avoiding-problem-areas-with-multithread-programs"></a>Çoklu İş Parçacığı Kullanan Programlarda Sorun Alanlarından Kaçınma
Oluşturma, bağlama veya çoklu iş parçacığı kullanan C programı yürütme karşılaşabileceğiniz bazı sorunlar vardır. Aşağıdaki tabloda bazı yaygın sorunlar açıklanmaktadır. (MFC açısından benzer hakkında bilgi için bkz [çoklu iş parçacığı kullanımı: programlama ipuçları](../parallel/multithreading-programming-tips.md).)  
  
|Sorun|Olası neden|  
|-------------|--------------------|  
|Programınızın koruma ihlaline neden gösteren bir ileti kutusu alın.|Çoğu Win32 programlama hataları koruma ihlallerine yol açar. Bir ortak koruma ihlalleri veri null işaretçilere dolaylı atama nedenidir. Bu, kendisine ait değil belleğe erişmeye programınızdaki edildiğinden, koruma ihlali verilir.<br /><br /> Hata ayıklama bilgilerini programınızla derlemek ve ardından çalıştırın, Visual C++ ortamına hata ayıklayıcıda aracılığıyla koruma ihlali neden algılamak için kolay bir yoludur.. Koruma hatası oluştuğunda Windows denetimi hata ayıklayıcıya geçirir ve imleç soruna neden satırda konumlandırıldı.|  
|Programınızı çok sayıda derleme ve bağlama hataları oluşturur.|Derleyicinin uyarı düzeyini, en yüksek değerler birine ayarlama ve uyarı iletilerini önemseyerek birçok olası sorunları ortadan kaldırabilirsiniz. Düzey 3 veya 4 düzey uyarı düzeyi seçenekleri kullanarak, yanlışlıkla veri dönüşümleri, eksik işlev prototipleri ve ANSI olmayan özellikleri kullanımını algılayabilir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C ve Win32 ile çoklu iş parçacığı kullanımı](../parallel/multithreading-with-c-and-win32.md)