---
title: 'Öğretici: Windows Performans Çözümleyicisi temelleri'
description: Windows Performans Çözümleyicisi'nde temel işlemlerin nasıl tamamlanılabiliriz hakkında öğretici.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ae1050b9389527a12f5bdbea6d695c0f20510127
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323395"
---
# <a name="tutorial-windows-performance-analyzer-basics"></a>Öğretici: Windows Performans Çözümleyicisi temelleri

::: moniker range="<=vs-2017"

C++ Build Insights araçları Visual Studio 2019'da mevcuttur. Bu sürümün belgelerini görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range="vs-2019"

C++ Build Insights'ın etkin bir şekilde kullanılması için Windows Performans Çözümleyicisi (WPA) hakkında bilgi gerekir. Bu makale, ortak WPA işlemleri hakkında bilgi edinmenize yardımcı olur. WPA'nın nasıl kullanılacağı hakkında daha fazla bilgi için [Windows Performans Çözümleyicisi](/windows-hardware/test/wpt/windows-performance-analyzer) belgelerine bakın.

## <a name="change-the-view-mode"></a>Görünüm modunu değiştirme

WPA, izlerinizi keşfetmeniz için iki temel görünüm modu sunar:

- grafik modu ve
- tablo modu.

Görünüm bölmesinin üst kısmındaki görünüm modu simgelerini kullanarak aralarında geçiş yapabilirsiniz:

![Grafik modu ve tablo modu arasında geçiş yapma.](media/wpa-switching-view-mode.gif)

## <a name="select-presets"></a>Hazır ayarları seçin

Çoğu C++ Build Insights WPA görüntülemesi arasından seçim yapabileceğiniz birden çok hazır asete sahiptir. Görünüm bölmesinin üst kısmındaki açılır menüyü kullanarak istediğiniz ön ayarı seçebilirsiniz:

![Önceden ayarlanmış bir ayar seçme.](media/wpa-presets.png)

## <a name="zoom-in-and-out"></a>Yakınlaştırma ve uzaklaştırma

Bazı yapı izleri o kadar büyük ki detayları anlamak zor. İlginizi çeken bir alanı yakınlaştırmak için grafiğe sağ tıklayın ve **Yakınlaştırma'yı**seçin. Her zaman **Geri Lekt'i**seçerek önceki ayara geri dönebilirsiniz. Bu resim, grafiğin bir bölümünü yakınlaştırmak için bir seçim ve **Yakınlaştırma** komutunu kullanma örneğini gösterir:

![Bir grafiği yakınlaştırma.](media/wpa-zooming.gif)

## <a name="group-by-different-columns"></a>Farklı sütunlara göre gruplandırma

İzlemenizin görüntülenme şeklini özelleştirebilirsiniz. Görünüm bölmesinin üst kısmındaki dişli simgesine tıklayın ve Yapı Gezgini Görünümü Düzenleyicisi'ndeki sütunları yeniden düzenleyin. Bu iletişim kutusundaki sarı çizginin üzerinde bulunan sütunlar, veri satırlarınızın gruplandırılan sütunlardır. Sarı çizginin hemen üstündeki sütun özeldir: grafik görünümünde renkli çubuklar üzerinde görüntülenir.

Bu resim, bir bağlantı çağırma örnek çubuk grafiği ni gösterir. Explorer Görünüm Düzenleyicisi oluştur iletişim kutusunu açmak için dişli simgesini kullanırız. Daha sonra Bileşen ve Ad sütun girişlerini sarı çizginin üzerine sürüklüyoruz. Yapılandırma, ayrıntı düzeyini artırmak ve bağlayıcıiçinde gerçekte ne olduğunu görmek için değiştirilir:

![Bir grafiği yakınlaştırma.](media/wpa-grouping.gif)

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici: vcperf ve Windows Performans Analizörü](vcperf-and-wpa.md)\
[Referans: vcperf komutları](/cpp/build-insights/reference/vcperf-commands)\
[Başvuru: Windows Performans Çözümleyicisi görünümleri](/cpp/build-insights/reference/wpa-views)\
[Windows Performans Analizörü](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
