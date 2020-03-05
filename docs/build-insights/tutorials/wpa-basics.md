---
title: 'Öğretici: Windows Performans Çözümleyicisi temelleri'
description: Windows Performans Çözümleyicisi 'nde temel işlemleri tamamlamaya yönelik öğretici.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f197e7dfd852cd66039f7279f90e42b0cf75fd86
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332231"
---
# <a name="tutorial-windows-performance-analyzer-basics"></a>Öğretici: Windows Performans Çözümleyicisi temelleri

::: moniker range="<=vs-2017"

Visual C++ Studio 2019 ' de derleme öngörüleri araçları mevcuttur. Bu sürümün belgelerini görmek için bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range="vs-2019"

Derleme C++ öngörülerini etkin bir şekilde kullanmak Için Windows Performans Çözümleyicisi 'nın (WPA) bazı bilgileri gerekir. Bu makale, genel WPA işlemleriyle ilgili bilgi sahibi olmanıza yardımcı olur. WPA 'yı kullanma hakkında daha fazla bilgi için bkz. [Windows Performans Çözümleyicisi](/windows-hardware/test/wpt/windows-performance-analyzer) belgeleri.

## <a name="change-the-view-mode"></a>Görünüm modunu değiştirme

WPA, izlemelerinizi keşfetmenize yönelik iki temel görünüm modu sunar:

- grafik modu ve
- Tablo modu.

Görünüm bölmesinin en üstündeki görünüm modu simgelerini kullanarak bunlar arasında geçiş yapabilirsiniz:

![Grafik modu ve tablo modu arasında geçiş yapma.](media/wpa-switching-view-mode.gif)

## <a name="select-presets"></a>Önayarları seçin

Çoğu C++ derleme ÖNGÖRÜLERI WPA görünümü, aralarından seçim yapabileceğiniz birden fazla önayar vardır. Görünüm bölmesinin en üstündeki açılan menüyü kullanarak istediğiniz önayarı seçebilirsiniz:

![Önayar seçme.](media/wpa-presets.png)

## <a name="zoom-in-and-out"></a>Yakınlaştırın ve uzaklaştırın

Bazı derleme izlemeleri büyük bir deyişle ayrıntıları oluşturmak zordur. İlgilendiğiniz bir alanı yakınlaştırmak için grafiğe sağ tıklayıp **Yakınlaştır**' ı seçin. **Geri al yakınlaştırmasını**seçerek her zaman önceki ayara gidebilirsiniz. Bu görüntüde, grafiğin bir bölümünde yakınlaştırmak için bir seçimi ve **Yakınlaştırma** komutunu kullanmayla ilgili bir örnek gösterilmektedir:

![Grafik üzerinde yakınlaştırma.](media/wpa-zooming.gif)

## <a name="group-by-different-columns"></a>Farklı sütunlara göre Gruplandır

İzlemenin görüntülenme şeklini özelleştirebilirsiniz. Görünüm bölmesinin en üstündeki dişli simgesine tıklayın ve Yapı Gezgini görünüm düzenleyicisinde sütunları yeniden düzenleyin. Bu iletişim kutusundaki sarı çizginin üzerinde bulunan sütunlar, veri satırlarınızın tarafından gruplandırıldıklarıdır. Sarı çizginin üzerinde sağ üstteki sütun özeldir: grafik görünümünde, renkli çubuklar üzerinde görüntülenir.

Bu görüntüde, bir bağlantı çağrısının örnek çubuk grafiği gösterilmektedir. Yapı Gezgini Görünüm Düzenleyicisi iletişim kutusunu açmak için dişli simgesini kullanıyoruz. Ardından, bileşen ve ad sütun girdilerini sarı çizginin üzerine sürükliyoruz. Yapılandırma, ayrıntı düzeyini artıracak şekilde değiştirilir ve bağlayıcı içinde gerçekten ne olduğunu görmek için:

![Grafik üzerinde yakınlaştırma.](media/wpa-grouping.gif)

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici: vcperf ve Windows performans çözümleyicisi](vcperf-and-wpa.md)\
[Reference: vcperf komutları](/cpp/build-insights/reference/vcperf-commands)\
[Başvuru: Windows Performans Çözümleyici görünümleri](/cpp/build-insights/reference/wpa-views)\
[Windows Performans Çözümleyicisi](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
