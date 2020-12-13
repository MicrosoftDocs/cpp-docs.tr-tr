---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: hızlı erişim araç çubuğunu özelleştirme'
title: 'Nasıl yapılır: Hızlı Erişim Araç Çubuğunu Özelleştirme'
ms.date: 09/07/2019
helpviewer_keywords:
- quick access toolbar [MFC], customization
ms.assetid: 2554099b-0c89-4605-9249-31bf9cbcefe0
ms.openlocfilehash: cb7935f9e340734f8af0e7ec9197e139c30af894
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330230"
---
# <a name="how-to-customize-the-quick-access-toolbar"></a>Nasıl yapılır: Hızlı Erişim Araç Çubuğunu Özelleştirme

Hızlı erişim araç çubuğu (QAT), uygulama düğmesinin yanında veya kategori sekmelerinde görüntülenen bir komutlar kümesi içeren özelleştirilebilir bir araç çubuğudur. Aşağıdaki çizimde tipik bir hızlı erişim araç çubuğu gösterilmektedir.

![MFC Şeridi hızlı erişim araç çubuğu](../mfc/media/quick_access_toolbar.png "MFC Şeridi hızlı erişim araç çubuğu")

Hızlı erişim araç çubuğunu özelleştirmek için, **Özellikler** penceresinde açın, komutlarını değiştirin ve ardından şerit denetimini önizleyin.

### <a name="to-open-the-quick-access-toolbar-in-the-properties-window"></a>Özellikler penceresi hızlı erişim araç çubuğunu açmak için

1. Visual Studio 'da, **Görünüm** menüsünde **kaynak görünümü**' a tıklayın.

1. **Kaynak görünümü**, şerit kaynağına çift tıklayarak tasarım yüzeyinde görüntüleyin.

1. Tasarım yüzeyinde, hızlı erişim araç çubuğu menüsüne sağ tıklayıp **Özellikler**' e tıklayın.

## <a name="quick-access-toolbar-properties"></a>Hızlı erişim araç çubuğu özellikleri

Aşağıdaki tablo, hızlı erişim araç çubuğunun özelliklerini tanımlar.

|Özellik|Tanım|
|--------------|----------------|
|QAT konumu|Uygulama başladığında hızlı erişim araç çubuğunun konumunu belirtir. Konum, şerit denetiminin **üzerinde** ya da **altında** olabilir.|
|QAT öğeleri|Hızlı erişim araç çubuğu için kullanılabilen komutları belirtir.|

#### <a name="to-add-or-remove-commands-on-the-quick-access-toolbar"></a>Hızlı erişim araç çubuğuna komut eklemek veya kaldırmak için

1. **Özellikler** penceresinde **qat öğeleri**' ne ve ardından üç nokta düğmesini **(...)** tıklayın.

1. **Qat öğeleri Düzenleyicisi** iletişim kutusunda, hızlı erişim araç çubuğundaki komutların listesini değiştirmek için **Ekle** ve **Kaldır** düğmelerini kullanın.

1. Bir komutun hem hızlı erişim araç çubuğunda hem de hızlı erişim araç çubuğu menüsünde görünmesini istiyorsanız komutun yanındaki kutuyu seçin. Komutun yalnızca menüde görünmesini istiyorsanız, kutuyu temizleyin.

## <a name="previewing-the-ribbon"></a>Şeridin önizlemesi

Hızlı erişim araç çubuğu komutları tasarım yüzeyinde görünmez. Bunları görüntülemek için, Şeriti önizlemeniz veya uygulamayı çalıştırmanız gerekir.

#### <a name="to-preview-the-ribbon-control"></a>Şerit denetimini önizlemek için

- **Şerit Düzenleyicisi araç çubuğunda**, **test şeridi**' ne tıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Şerit Tasarımcısı (MFC)](ribbon-designer-mfc.md)
