---
title: 'Öğretici: Windows Performans Çözümleyicisi temelleri'
description: Windows Performans Çözümleyicisi 'nde temel işlemleri tamamlamaya yönelik öğretici.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 75f45244b9e9b38b7dc65b604940199acafa0ede
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922224"
---
# <a name="tutorial-windows-performance-analyzer-basics"></a>Öğretici: Windows Performans Çözümleyicisi temelleri

::: moniker range="<=msvc-150"

C++ derleme öngörüleri araçları Visual Studio 2019 'de bulunabilir. Bu sürümün belgelerini görmek için bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range="msvc-160"

C++ derleme öngörülerini etkin bir şekilde kullanmak için bazı Windows Performans Çözümleyicisi (WPA) bilgisi gerekir. Bu makale, genel WPA işlemleriyle ilgili bilgi sahibi olmanıza yardımcı olur. WPA 'yı kullanma hakkında daha fazla bilgi için bkz. [Windows Performans Çözümleyicisi](/windows-hardware/test/wpt/windows-performance-analyzer) belgeleri.

## <a name="change-the-view-mode"></a>Görünüm modunu değiştirme

WPA, izlemelerinizi keşfetmenize yönelik iki temel görünüm modu sunar:

- grafik modu ve
- Tablo modu.

Görünüm bölmesinin en üstündeki görünüm modu simgelerini kullanarak bunlar arasında geçiş yapabilirsiniz:

![Grafik modu ve tablo modu arasında geçiş yapma.](media/wpa-switching-view-mode.gif)

## <a name="select-presets"></a>Önayarları seçin

Çoğu C++ derleme öngörüleri WPA görünümlerinin arasından seçim yapabileceğiniz birden çok ön ayar vardır. Görünüm bölmesinin en üstündeki açılan menüyü kullanarak istediğiniz önayarı seçebilirsiniz:

![Önayar seçme.](media/wpa-presets.png)

## <a name="zoom-in-and-out"></a>Yakınlaştırma ve uzaklaştırma

Bazı derleme izlemeleri büyük bir deyişle ayrıntıları oluşturmak zordur. İlgilendiğiniz bir alanı yakınlaştırmak için grafiğe sağ tıklayıp **Yakınlaştır** ' ı seçin. **Geri al yakınlaştırmasını** seçerek her zaman önceki ayara gidebilirsiniz. Bu görüntüde, grafiğin bir bölümünde yakınlaştırmak için bir seçimi ve **Yakınlaştırma** komutunu kullanmayla ilgili bir örnek gösterilmektedir:

![Grafik üzerinde yakınlaştırmanın gösterildiği kısa video.](media/wpa-zooming.gif)

## <a name="group-by-different-columns"></a>Farklı sütunlara göre Gruplandır

İzlemenin görüntülenme şeklini özelleştirebilirsiniz. Görünüm bölmesinin en üstündeki dişli simgesine tıklayın ve Yapı Gezgini görünüm düzenleyicisinde sütunları yeniden düzenleyin. Bu iletişim kutusundaki sarı çizginin üzerinde bulunan sütunlar, veri satırlarınızın tarafından gruplandırıldıklarıdır. Sarı çizginin üzerinde sağ üstteki sütun özeldir: grafik görünümünde, renkli çubuklar üzerinde görüntülenir.

Bu görüntüde, bir bağlantı çağrısının örnek çubuk grafiği gösterilmektedir. Yapı Gezgini Görünüm Düzenleyicisi iletişim kutusunu açmak için dişli simgesini kullanıyoruz. Ardından, bileşen ve ad sütun girdilerini sarı çizginin üzerine sürükliyoruz. Yapılandırma, ayrıntı düzeyini artıracak şekilde değiştirilir ve bağlayıcı içinde gerçekten ne olduğunu görmek için:

![Farklı sütunlara göre nasıl gruplandırkullanabileceğinizi gösteren kısa bir video.](media/wpa-grouping.gif)

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici: vcperf ve Windows Performans Çözümleyicisi](vcperf-and-wpa.md)\
[Reference: vcperf komutları](../reference/vcperf-commands.md)\
[Başvuru: Windows Performans Çözümleyici görünümleri](../reference/wpa-views.md)\
[Windows Performans Çözümleyicisi](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
