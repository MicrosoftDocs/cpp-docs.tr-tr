---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: çizim aracını kullanma'
title: 'Nasıl yapılır: çizim aracını kullanma'
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
ms.openlocfilehash: 9415b81eb520b626186fe321184bd1d7d7391b61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283270"
---
# <a name="how-to-use-a-drawing-tool"></a>Nasıl yapılır: çizim aracını kullanma

**Görüntü Düzenleyicisi** , hepsi aynı şekilde çalışan serbest çizim ve silme araçlarına sahiptir. Aracı seçersiniz ve gerekirse, [ön plan ve arka plan renkleri](./image-editor-for-icons.md) ve boyut ve şekil seçeneklerini belirleyin. Sonra işaretçiyi görüntüye taşıyın ve çizim ve silme için tıklayın veya sürükleyin.

## <a name="drawing-tools"></a>Çizim araçları

**Resim Düzenleyicisi** araç çubuğundan veya **görüntü** menüsünden Çizim Araçları ' nı seçebilirsiniz. **Silgi** aracını, **fırça** aracını veya **püskürtme** aracını seçtiğinizde, seçenek Seçicisi bu aracın seçeneklerini görüntüler.

> [!TIP]
> İmleci [Görüntü Düzenleyicisi araç çubuğundaki](./image-editor-for-icons.md)düğmelerin üzerine getirdiğinizde araç ipuçları görüntülenir. Bu ipuçları burada bahsedilen belirli düğmeleri belirlemenize yardımcı olur.

### <a name="to-select-and-use-a-drawing-tool-from-the-image-editor-toolbar"></a>Görüntü Düzenleyici araç çubuğundan bir çizim aracı seçme ve kullanma

1. **Görüntü Düzenleyicisi** araç çubuğunda bir düğme seçin.

   - **Silgi** Aracı, sol fare düğmesine bastığınızda geçerli arka plan rengiyle görüntüyü boyar.

      > [!TIP]
      > **Silgi** aracını kullanmak yerine, çizim araçlarından biriyle arka plan rengine daha kolay bir şekilde çizim yapabilirsiniz.

   - **Kurşun kalem** Aracı, tek bir pikselin sabit genişliğinde FreeHand çizer.

   - **Fırça** aracında çeşitli şekiller ve boyutlar vardır.

   - **Püskürtme** Aracı, renk piksellerini fırçanın ortasına rastgele dağıtır.

1. Gerekirse renkleri ve fırçayı seçin:

   - [Renkler paletinde](./image-editor-for-icons.md), arka plan rengi seçmek için bir ön plan rengi veya sağ fare düğmesini seçmek üzere sol fare düğmesini seçin.

   - [Seçenekler Seçicisi](./image-editor-for-icons.md)' nde, kullanmak istediğiniz fırçayı temsil eden bir şekil seçin.

1. Görüntüde çizim veya boyamayı başlatmak istediğiniz yeri işaret edin. İşaretçi şekli seçtiğiniz araca göre değiştirir.

1. Sol fare düğmesine (ön plan rengi için) veya sağ fare düğmesine (arka plan rengi için) basın ve çizerken basılı tutun.

### <a name="to-select-and-use-a-drawing-tool-from-the-image-menu"></a>Görüntü menüsünden bir çizim aracı seçme ve kullanma

1. Menü **resmi**  >  **araçları**' na gidin.

1. Basamaklı alt menüde kullanmak istediğiniz aracı seçin.

## <a name="lines-or-closed-figures"></a>Çizgiler veya kapalı rakamlar

Satırları ve kapalı rakamları çizmek için **görüntü düzenleyici** araçları aynı şekilde çalışır: ekleme noktasını bir noktaya yerleştirip başka bir yere sürükleyebilirsiniz. Satırlar için bu noktalar uç noktalardır. Kapalı rakamlar için, bu noktaları, şekle göre sınırlayıcı bir dikdörtgenin zıt köşelerinden oluşur.

Çizgiler geçerli fırça seçimine göre belirlenen bir genişliğe göre çizilir ve çerçeveli rakamlar, geçerli genişlik seçimine göre belirlenen bir genişliğe göre çizilir. Hem çerçeveli hem de doldurulmuş tüm rakamlar, sol fare düğmesine basarsanız veya sağ fare düğmesine basarsanız geçerli arka plan renginde geçerli ön plan rengine çizilir.

### <a name="to-draw-a-line"></a>Bir çizgi çizmek için

1. [Görüntü Düzenleyicisi araç çubuğunu](./image-editor-for-icons.md) kullanın veya menü **görüntüsü** >  **araçları** ' na gidip **çizgi** aracını seçin.

1. Gerekirse renkleri ve fırçayı seçin:

   - [Renkler paletinde](./image-editor-for-icons.md), arka plan rengi seçmek için bir ön plan rengi veya sağ fare düğmesini seçmek üzere sol fare düğmesini seçin.

   - [Seçenekler Seçicisi](./image-editor-for-icons.md)' nde, kullanmak istediğiniz fırçayı temsil eden bir şekil seçin.

1. İşaretçiyi çizginin başlangıç noktasına yerleştirin.

1. Çizginin uç noktasına sürükleyin.

### <a name="to-draw-a-closed-figure"></a>Kapalı bir şekil çizmek için

1. **Görüntü Düzenleyicisi** araç çubuğunu kullanın veya menü **görüntüsü**  >  **araçları** ' na gidip bir **kapalı şekil çizim** aracı seçin.

   **Kapalı şekil çizim** araçları, ilgili düğmelerinde gösterilen şekilde şekiller oluşturur.

1. Gerekirse, renkler ve çizgi kalınlığı ' nı seçin.

1. İşaretçiyi, şekli çizmek istediğiniz dikdörtgen alanın bir köşesine taşıyın.

1. İşaretçiyi çapraz eksende ters köşeye sürükleyin.

## <a name="custom-brushes"></a>Özel fırçalar

Özel fırça, seçtiğiniz bir görüntünün dikdörtgen bir kısmıdır ve **Görüntü Düzenleyicisi**'nin kullanıma açılan fırçalarından biri gibi kullanılır. Seçim üzerinde gerçekleştirebileceğiniz tüm işlemler, özel bir fırça üzerinde de gerçekleştirebilirsiniz.

### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>Görüntünün bir kısmından özel bir fırça oluşturmak için

1. Bir fırça için kullanmak istediğiniz görüntünün bölümünü seçin.

1. **SHIFT** tuşunu basılı tutun, seçimde seçim yapın ve görüntünün üzerine sürükleyin ya da menü **görüntüsüne** giderek  >  **seçimi fırça olarak kullanın**.

   Seçiminiz, seçimdeki renkleri görüntüde dağıtan özel bir fırça haline gelir. Seçimin kopyaları sürükleme yolu üzerinde bırakılır. Ne kadar yavaş sürüklediğiniz, daha fazla kopya yapılır.

   > [!NOTE]
   > Önce görüntünün bir kısmını seçmeden **bir seçimi fırça olarak kullan** seçeneğinin belirlenmesi, tüm görüntüyü fırça olarak kullanır. Özel bir fırça kullanmanın sonucu da [donuk veya saydam bir arka plan](./image-editor-for-icons.md)seçmiş olup olmadığına bağlıdır.

Geçerli arka plan rengiyle eşleşen bir özel fırçayla birlikte normal olarak saydam olan pikseller, varolan görüntünün üzerine boyamazlar. Bu davranışı, arka plan rengi piksellerinin mevcut görüntünün üzerine boyamasını sağlayacak şekilde değiştirebilirsiniz.

Farklı özel etkiler oluşturmak için bir damga veya bir şablon gibi özel fırçayı kullanabilirsiniz.

### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>Arka plan rengine özel fırça şekilleri çizmek için

1. Donuk veya saydam bir arka plan seçin.

1. Arka plan rengini, çizmek istediğiniz renge ayarlayın.

1. Özel fırçayı çizmek istediğiniz yere konumlandırın.

1. Sağ fare düğmesini seçin. Özel fırçanın donuk bölgeleri arka plan rengine çizilir.

### <a name="to-double-or-halve-the-custom-brush-size"></a>Özel fırça boyutunu Double veya halmek için

Fırça boyutunu açmak için **artı işareti** ( **+** ) tuşuna veya yarıya bırakmak için **eksi işareti** () tuşuna basın **-** .

### <a name="to-cancel-the-custom-brush"></a>Özel fırçayı iptal etmek için

**ESC** tuşuna basın veya başka bir çizim aracı seçin.

## <a name="requirements"></a>Gereksinimler

Yok

## <a name="see-also"></a>Ayrıca bkz.

[Simgeler için görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)<br/>
[Nasıl yapılır: simge veya başka görüntü oluşturma](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[Nasıl yapılır: görüntü düzenleme](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[Nasıl yapılır: renklerle çalışma](../windows/working-with-color-image-editor-for-icons.md)<br/>
[Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
