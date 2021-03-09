---
title: Çok İş Parçacıklı Kitaplık Performansı
description: Microsoft C çalışma zamanı çok iş parçacıklı kitaplıklarından en iyi performansı alma konusuna genel bakış.
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- threading [C++], performance
- libraries, multithreaded
- performance, multithreading
- multithreaded libraries
ms.assetid: faa5d808-087c-463d-8f0d-8c478d137296
ms.openlocfilehash: 39d77d52dbc8ac2e725cf46c98c5462df701e3eb
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514674"
---
# <a name="multithreaded-libraries-performance"></a>Çok İş Parçacıklı Kitaplık Performansı

Tek iş parçacıklı CRT artık kullanılamaz. Bu konuda, çok iş parçacıklı kitaplıklardan maksimum performansı nasıl alacağınız ele alınmaktadır.

## <a name="maximizing-performance"></a>Performansı en üst düzeye çıkarma

Çok iş parçacıklı kitaplıkların performansı geliştirilmiştir ve bu, şu anda kaldırılan tek iş parçacıklı kitaplıkların performansına yakın bir performans sağlar. Daha yüksek performans gerektiren bu durumlar için, birkaç yeni özellik vardır.

- Bağımsız akış kilitleme, bir akışı kilitlemenize ve sonra doğrudan akışa erişen [_nolock işlevlerini](../c-runtime-library/nolock-functions.md) kullanmanıza olanak tanır. Bu, kilit kullanımının kritik döngülerin dışında barındırılanalmasına izin verir.

- İş parçacığı başına yerel ayar, çok iş parçacıklı senaryolar için yerel ayar erişiminin maliyetini azaltır (bkz. [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)).

- Yerel ayara bağımlı işlevler (_l ile biten adlarla) yerel ayarı bir parametre olarak alır. Bu, önemli maliyetli (örneğin, [printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)) kaldırılır.

- Yaygın codepages iyileştirmeleri, birçok kısa işlemin maliyetini azaltır.

- [_CRT_DISABLE_PERFCRIT_LOCKS](../c-runtime-library/crt-disable-perfcrit-locks.md) tanımlama, tüm g/ç işlemlerini tek iş parçacıklı g/ç modeli varsay ve işlevlerin _nolock biçimlerini kullanacak şekilde zorlar. Bu, yüksek g/ç tabanlı tek iş parçacıklı uygulamalara daha iyi performans sağlamak için izin verir.

- CRT yığın tanıtıcısının pozlaması, CRT yığını için Windows düşük parçalanma yığınını (LFH) etkinleştirmenizi sağlar ve bu da yüksek düzeyde ölçeklendirilen senaryolarda performansı önemli ölçüde iyileştirebilir.

## <a name="see-also"></a>Ayrıca bkz.

[C çalışma zamanı (CRT) ve C++ standart kitaplığı (STL) `.lib` dosyaları](../c-runtime-library/crt-library-features.md)
