---
title: 'Nasıl yapılır: Çizim aracı kullanma'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.image.drawing
helpviewer_keywords:
- Image editor [C++], selecting drawing tools
- Image editor [C++], toolbar
- drawing tools
- Image editor [C++], drawing lines
- shapes, drawing
- colors [C++], brush
- brushes, colors
- brushes, creating custom
- images [C++], creating custom brushes
- graphics [C++], custom brushes
- custom brushes
ms.assetid: 1f8c6eef-7760-45a9-a5cb-9e15c6f91245
ms.openlocfilehash: bde951a2915bf980e09d94c16edc1a9b462c662e
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57563335"
---
# <a name="how-to-use-a-drawing-tool"></a>Nasıl yapılır: Çizim aracı kullanma

**Resim Düzenleyicisi** serbest çizim ve tümünü aynı şekilde çalıştığını silme araçlara sahiptir. Aracı'nı seçin ve gerekirse [ön plan ve arka plan renklerini seçin](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) , boyutu ve şekli seçenekleri. Ardından görüntüyü işaretçiyi ve tıklar veya çizmek ve silmek için sürükleyin.

## <a name="drawing-tools"></a>Çizim Araçları

Çizim araçlarından herhangi birinden seçebilirsiniz **Resim Düzenleyicisi** araç veya **görüntü** menüsü. Seçtiğinizde, **Silgi** aracı **fırça** aracı veya **kabı** aracı, seçenek belirleyici, Aracı'nın seçenekleri görüntüler.

> [!TIP]
>  Araç ipuçları, üzerinde düğmelerin üzerine imleci fareyle geldiğinizde görünür [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md). Bu ipuçlarını burada bahsedilen belirli düğmelerin belirlemenize yardımcı olur.

### <a name="to-select-and-use-a-drawing-tool-from-the-image-editor-toolbar"></a>Seçin ve Resim Düzenleyicisi araç çubuğundan bir çizim aracı kullanma

1. Bir düğme seçin **Resim Düzenleyicisi** araç çubuğu.

   - **Silgi** aracı paints geçerli arka plan rengiyle görüntü üzerinden farenin sol düğmesine bastığınızda.

      > [!TIP]
      > Yerine **Silgi** aracı bulduğunuz, çizim araçlarından birini arka plan rengiyle çizme daha kolay.

   - **Kalem** aracı bir piksel cinsinden bir sabit genişliği freehand çizer.

   - **Fırça** çeşitli şekillerdeki ve boyutlardaki araç vardır.

   - **Kabı** aracı fırçanın merkezi etrafındaki renk piksel rastgele dağıtır.

1. Gerekirse, renk ve fırça seçin:

   - İçinde [renkler paleti](../windows/colors-window-image-editor-for-icons.md), ön plan rengi seçmesini farenin sol düğmesine veya arka plan rengi seçmek için sağ fare düğmesini seçin.

   - İçinde [seçenekleri Seçici](../windows/toolbar-image-editor-for-icons.md), kullanmak istediğiniz fırça temsil eden bir şekil seçin.

1. Çizim başlamak istediğiniz görüntüyü veya boyama konumunda gelin. İşaretçi şekli seçtiğiniz aracı göre değişir.

1. Farenin sol düğmesine (için ön plan rengini) veya (için arka plan rengi) sağ fare düğmesine basın ve bu gibi çizim basılı tutun.

### <a name="to-select-and-use-a-drawing-tool-from-the-image-menu"></a>Seçin ve Görüntü menüsü'nden bir çizim aracı kullanma

1. Menü Git **görüntü** > **Araçları**.

1. Basamaklı alt menüsünde kullanmak istediğiniz aracı seçin.

## <a name="lines-or-closed-figures"></a>Çizgi veya kapalı şekiller

**Resim Düzenleyicisi** tüm satırları ve kapalı şekiller çizmek için Araçlar aynı şekilde çalışır: bir noktada ekleme noktasını yerleştirin ve diğerine sürükleyin. Satırlar için bu uç noktalardır. Kapalı şekiller için bu, Şekil sınırlayıcı bir dikdörtgen zıt köşe noktalarıdır.

Geçerli fırça seçim tarafından belirlenen bir genişliği çizgileri çizilir ve Çerçeveli rakamları genişliği seçilen tarafından belirlenen bir genişliği çizilir. Sağ fare düğmesine basarsanız satırları ve Çerçeveli hem doludur ve tüm şekilleri, farenin sol düğmesine basarsanız geçerli ön plan rengini veya arka plan rengi geçerli çizilir.

### <a name="to-draw-a-line"></a>Bir çizgi çizmek için

1. Kullanım [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md) veya menüsüne gidin **görüntü**> **Araçları** ve **satırı** aracı.

1. Gerekirse, renk ve fırça seçin:

   - İçinde [renkler paleti](../windows/colors-window-image-editor-for-icons.md), ön plan rengi seçmesini farenin sol düğmesine veya arka plan rengi seçmek için sağ fare düğmesini seçin.

   - İçinde [seçenekleri Seçici](../windows/toolbar-image-editor-for-icons.md), kullanmak istediğiniz fırça temsil eden bir şekil seçin.

1. İşaretçiyi çizginin başlangıç noktasına yerleştirin.

1. Çizginin bitiş noktasına sürükleyin.

### <a name="to-draw-a-closed-figure"></a>Kapalı şekle çizmek için

1. Kullanım **Resim Düzenleyicisi** araç ya da menü **görüntü** > **Araçları** seçip bir **kapalı şekil çizme** aracı.

   **Kapalı şekil çizme** araçları ilgili kendi düğmelerini belirtildiği gibi şekiller oluşturun.

1. Gerekirse, renk ve çizgi genişliği seçin.

1. İşaretçiyi bir şekil Çiz istediğiniz Dikdörtgen alanı köşeye taşıyın.

1. Çapraz zıt köşe için işaretçiyi sürükleyin.

## <a name="custom-brushes"></a>Özel Fırçalar

Özel fırça almak ve biri gibi kullanabileceğiniz görüntünün dikdörtgen kısmıdır **Resim Düzenleyicisi**'s hazır Fırçalar. Seçime göre gerçekleştirebileceğiniz tüm işlemler bir özel fırça üzerinde gerçekleştirebilirsiniz.

### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>Bir görüntüyü bölümünden özel Fırça oluşturma

1. Fırça için kullanmak istediğiniz görüntüyü bölümünü seçin.

1. Basılı **Shift** aşağı anahtar, seçimdeki seçin ve görüntünün arasında sürükleyin veya menüsüne gidin **görüntü** > **fırça olarak kullanma seçimi**.

   Seçimdeki renkleri arasında görüntüyü dağıtır özel bir fırça seçiminizi olur. Seçimin bir kopyasını sürükleyerek yol boyunca bırakılır. Daha yavaş sürükleyin, kopya yapılmaz.

   > [!NOTE]
   > Seçme **seçimi bir fırça olarak kullanma** olmadan önce görüntünün bir kısmı seçerek görüntünün tamamını fırça olarak kullanır. Özel fırça kullanarak sonucu olup, seçtiğiniz üzerinde de bağlıdır bir [opak veya saydam arka plan](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

Özel fırça geçerli arka plan rengiyle uyuşan piksellerde normalde saydam: var olan görüntünün üzerine boyama yok. Mevcut görüntü arka plan rengi piksel boyama bu davranışı değiştirebilirsiniz.

Özel fırça bir damga ya da bir şablon gibi farklı özel efektler oluşturmak için kullanabilirsiniz.

### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>Arka plan rengi özel fırça şekiller çizmek için

1. Donuk veya saydam bir arka plan seçin.

1. Arka plan rengi, çizmek istediğiniz renge ayarlayın.

1. Özel fırça çizmek istediğiniz yere getirin.

1. Sağ fare düğmesini seçin. Arka plan rengi özel fırça donuk tüm bölümlerinin çekilir.

### <a name="to-double-or-halve-the-custom-brush-size"></a>Özel fırça boyutunu edilmesiyle yarıya ya da çift

Basın **artı** (**+**) fırça boyutunu çift anahtarı veya **eksi işareti** (**-**), edilmesiyle yarıya için anahtarı .

### <a name="to-cancel-the-custom-brush"></a>Özel fırça iptal etmek için

Tuşuna **Esc** veya başka bir çizim Aracı'nı seçin.

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca Bkz.

[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)<br/>
[Nasıl yapılır: Simge veya Başka Görüntü Oluşturma](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[Nasıl yapılır: Görüntü Kopyalama](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[Nasıl yapılır: Renklerle Çalışma](../windows/working-with-color-image-editor-for-icons.md)<br/>
[Hızlandırıcı Tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>