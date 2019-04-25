---
title: Çoklu İş Parçacığı Kullanan Programlarda Sorun Alanlarından Kaçınma
ms.date: 11/04/2016
helpviewer_keywords:
- multithreading [C++], troubleshooting
- errors [C++], multithreaded programs
- threading [C++], troubleshooting
- troubleshooting [C++], multithreading
ms.assetid: 06cc231d-bb5a-409d-8bd3-676c9e2a8c5b
ms.openlocfilehash: 3ceae832599243ffa0aad2b6fa67148e7ea30510
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237070"
---
# <a name="avoiding-problem-areas-with-multithread-programs"></a>Çoklu İş Parçacığı Kullanan Programlarda Sorun Alanlarından Kaçınma

Oluşturma, bağlama veya çoklu iş parçacığı kullanan C programı yürütme karşılaşabileceğiniz bazı sorunlar vardır. Aşağıdaki tabloda bazı yaygın sorunlar açıklanmaktadır. (MFC açısından benzer bir tartışma için bkz: [çoklu iş parçacığı kullanımı: Programlama ipuçları](multithreading-programming-tips.md).)

|Sorun|Olası neden|
|-------------|--------------------|
|Programınızı koruma ihlaline neden olduğunu gösteren bir ileti kutusu sahip olursunuz.|Birçok Win32 programlama hatalarını koruma ihlallerine neden. Yaygın bir nedeni, koruma ihlalleri, null işaretçi veri dolaylı atamadır. Kendisine ait olmayan belleğe erişmeye çalışırken programınızı sonuçlanır olduğundan koruma ihlali verilir.<br /><br /> Koruma ihlalinin nedeni algılamak için kolay bir yolu, programınızın hata ayıklama bilgileri ile derleyin ve çalıştırın hata ayıklayıcıyla Visual C++ ortamında sağlamaktır. Koruma hatası oluştuğunda, Windows hata ayıklayıcısı için Denetim aktarır ve imleci soruna neden satırda konumlandırılır.|
|Programınız, çok sayıda derleme ve bağlama hataları oluşturur.|Derleyicinin uyarı düzeyi bir en yüksek değerleri ayarlama ve uyarı iletilerini önemseyerek birçok olası sorunları ortadan kaldırabilir. Düzey 4 uyarısı düzeyi seçenekleri ve Düzey 3'ı kullanarak yanlışlıkla veri dönüşümleri, eksik işlev prototipleri ve ANSI olmayan özelliklerinin kullanımını da algılayabilir.|

## <a name="see-also"></a>Ayrıca bkz.

[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](multithreading-with-c-and-win32.md)
