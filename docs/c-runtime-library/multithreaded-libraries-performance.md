---
title: Çok İş Parçacıklı Kitaplık Performansı
ms.date: 11/04/2016
helpviewer_keywords:
- threading [C++], performance
- libraries, multithreaded
- performance, multithreading
- multithreaded libraries
ms.assetid: faa5d808-087c-463d-8f0d-8c478d137296
ms.openlocfilehash: f73aa99d1800fc81408b739e556bc7845b348a80
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587570"
---
# <a name="multithreaded-libraries-performance"></a>Çok İş Parçacıklı Kitaplık Performansı

Tek iş parçacıklı CRT artık kullanılamıyor. Bu konuda, çok iş parçacıklı kitaplıklarından en yüksek performansı elde anlatılmaktadır.

## <a name="maximizing-performance"></a>Performansı en üst düzeye çıkarma

Çok iş parçacıklı kitaplık performansı geliştirildi ve artık ortadan tek iş parçacıklı kitaplık performansı yakın. Bu durumlar için daha yüksek performans gerektiğinde çeşitli yeni özellikler mevcuttur.

- Bağımsız stream kilitleme sayesinde bir akış kilitleyin ve ardından [_nolock işlevleri](../c-runtime-library/nolock-functions.md) doğrudan akış erişim. Bu, kritik döngüler dışında hoisted kilit kullanımına izin verir.

- İş parçacığı başına yerel ayar çok iş parçacıklı senaryoları için yerel ayar erişim maliyetini azaltır (bkz [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)).

- Yerel ayara bağlı işlevler (adlarla _l içinde biten), yerel ayar önemli ölçüde kaldırarak bir parametre olarak alır (örneğin, [printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)).

- Ortak kod sayfaları için iyileştirme, pek çok kısa işlemlerinin maliyetini azaltın.

- Tanımlama [_crt_dısable_perfcrıt_locks](../c-runtime-library/crt-disable-perfcrit-locks.md) tek iş parçacıklı bir g/ç modeli varsayar ve işlevlerin _nolock forms kullanmak için tüm g/ç işlemleri zorlar. Bu, daha iyi performans elde etmek tek iş parçacıklı uygulamalar yüksek oranda miyim/O tabanlı sağlar.

- CRT yığın tanıtıcısı riskini Windows Düşük Parçalanma Yığın (LFH) için yüksek oranda ölçeklendirilmiş senaryolarda performansı önemli ölçüde iyileştirebilen CRT yığın etkinleştirmenize olanak sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)