---
title: 'Nasıl Kullanılır: Çizim Aracı Kullanın'
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
ms.openlocfilehash: b0041124c35414a0c1c998642b5321319602c872
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359847"
---
# <a name="how-to-use-a-drawing-tool"></a>Nasıl Kullanılır: Çizim Aracı Kullanın

**Görüntü** Düzenleyicisi, tüm bunların aynı şekilde çalıştığı serbest çizim ve silen araçlara sahiptir. Aracı seçin ve gerekirse ön plan ve arka plan renkleri ile boyut ve şekil seçeneklerini [seçin.](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) Daha sonra işaretçiyi resme taşıyın ve çizmek ve silmek için tıklatın veya sürükleyin.

## <a name="drawing-tools"></a>Çizim Araçları

Çizim araçlarını **Resim Düzenleyicisi** araç çubuğundan veya **Resim** menüsünden seçebilirsiniz. **Silgi** aracını, **Fırça** aracını veya **Airbrush** aracını seçtiğinizde, seçenek seçici o aracın seçeneklerini görüntüler.

> [!TIP]
> Araç ipuçları, imlecinizi Görüntü Düzenleyicisi araç [çubuğundaki](../windows/toolbar-image-editor-for-icons.md)düğmelerin üzerinde gezindiğinizde görünür. Bu ipuçları, burada belirtilen belirli düğmeleri belirlemenize yardımcı olacaktır.

### <a name="to-select-and-use-a-drawing-tool-from-the-image-editor-toolbar"></a>Resim Düzenleyicisi araç çubuğundan bir çizim aracı seçmek ve kullanmak için

1. **Resim Düzenleyicisi** araç çubuğunda bir düğme seçin.

   - **Silgi** aracı, sol fare düğmesine bastığında geçerli arka plan rengiyle görüntünün üzerine boyalar.

      > [!TIP]
      > **Silgi** aracını kullanmak yerine, çizim araçlarından biriyle arka plan rengini çizmeyi daha uygun bulabilirsiniz.

   - **Kalem** aracı, bir pikselin sabit genişliğinde serbest çesitli çizer.

   - **Fırça** aracının çeşitli şekil ve boyutları vardır.

   - **Airbrush** aracı, fırçanın ortasına renk piksellerini rasgele dağıtır.

1. Gerekirse renkleri ve fırçayı seçin:

   - Renkler [paletinde,](../windows/colors-window-image-editor-for-icons.md)ön plan rengini seçmek için sol fare düğmesini veya arka plan rengini seçmek için sağ fare düğmesini seçin.

   - Seçenekler [seçicide,](../windows/toolbar-image-editor-for-icons.md)kullanmak istediğiniz fırçayı temsil eden bir şekil seçin.

1. Resim yapmaya veya boyamaya başlamak istediğiniz resme işaret edin. İşaretçi seçtiğiniz araca göre şekli değiştirir.

1. Sol fare düğmesine (ön plan rengi için) veya sağ fare düğmesine (arka plan rengi için) basın ve çizerken basılı tutun.

### <a name="to-select-and-use-a-drawing-tool-from-the-image-menu"></a>Resim menüsünden bir çizim aracı seçmek ve kullanmak için

1. Menüye gidin **Resim** > **Araçları**.

1. Basamaklı alt menüde kullanmak istediğiniz aracı seçin.

## <a name="lines-or-closed-figures"></a>Satırlar veya Kapalı Şekiller

Çizgilerve kapalı şekiller çizmek için **Görüntü Düzenleyicisi** araçları nın tümü aynı şekilde çalışır: ekleme noktasını bir noktaya yerleştirir ve başka bir noktaya sürüklersiniz. Satırlar için bu noktalar uç noktalardır. Kapalı rakamlar için bu noktalar, figürü sınırlayan bir dikdörtgenin zıt köşeleridir.

Çizgiler geçerli fırça seçimi tarafından belirlenen bir genişlikte çizilir ve çerçeveli şekiller geçerli genişlik seçimi tarafından belirlenen bir genişlikte çizilir. Sol fare düğmesine bastığınızda, hem çerçeveli hem de doldurulmuş çizgiler ve tüm şekiller, geçerli ön plan renginde veya sağ fare düğmesine bastığınızda geçerli arka plan renginde çizilir.

### <a name="to-draw-a-line"></a>Bir çizgi çizmek için

1. Görüntü [Düzenleyicisi araç çubuğunu](../windows/toolbar-image-editor-for-icons.md) kullanın veya **Görüntü**> **Araçları** menüsüne gidin ve **Line** aracını seçin.

1. Gerekirse renkleri ve fırçayı seçin:

   - Renkler [paletinde,](../windows/colors-window-image-editor-for-icons.md)ön plan rengini seçmek için sol fare düğmesini veya arka plan rengini seçmek için sağ fare düğmesini seçin.

   - Seçenekler [seçicide,](../windows/toolbar-image-editor-for-icons.md)kullanmak istediğiniz fırçayı temsil eden bir şekil seçin.

1. İşaretçiyi çizginin başlangıç noktasına yerleştirin.

1. Çizginin bitiş noktasına sürükleyin.

### <a name="to-draw-a-closed-figure"></a>Kapalı bir rakam çizmek için

1. Resim **Düzenleyicisi** araç çubuğunu kullanın veya **Görüntü** > **Araçları** menüsüne gidin ve Kapalı **Şekil Çizim** aracını seçin.

   **Kapalı Şekil çizim** araçları, ilgili düğmelerinde belirtildiği gibi şekiller oluşturur.

1. Gerekirse, renkleri ve çizgi genişliğini seçin.

1. İşaretçiyi, figürü çizmek istediğiniz dikdörtgen alanın bir köşesine taşıyın.

1. İşaretçiyi çapraz olarak zıt köşeye sürükleyin.

## <a name="custom-brushes"></a>Özel Fırçalar

Özel fırça, Görüntü Düzenleyicisi'nin hazır fırçalarından biri gibi aldığınız **Image Editor**ve kullandığınız görüntünün dikdörtgen bir kısmıdır. Bir seçim de gerçekleştirebilirsiniz tüm işlemleri, özel bir fırça üzerinde de gerçekleştirebilirsiniz.

### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>Görüntünün bir bölümünden özel bir fırça oluşturmak için

1. Görüntünün fırça için kullanmak istediğiniz bölümünü seçin.

1. **Shift** tuşunu basılı tutun, seçimi seçin ve görüntü boyunca sürükleyin veya Fırça olarak **Görüntü** > **Kullanımı Seçimi**menüsüne gidin.

   Seçiminiz, seçimdeki renkleri görüntüye dağıtan özel bir fırça olur. Seçimin kopyaları sürükleme yolu boyunca bırakılır. Ne kadar yavaş sürüklerseniz, o kadar çok kopya yapılır.

   > [!NOTE]
   > Görüntünün bir bölümünü seçmeden **Fırça Olarak Seç'i** seçmek, görüntünün tamamını fırça olarak kullanır. Özel bir fırça kullanmanın sonucu da [opak veya Saydam bir arka plan](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)seçip seçmediğinize bağlıdır.

Geçerli arka plan rengiyle eşleşen özel bir fırçadaki pikseller normalde saydamdır: varolan görüntünün üzerine resim yapmazlar. Bu davranışı, arka plan rengi piksellerin varolan görüntünün üzerine boyanacağı şekilde değiştirebilirsiniz.

Farklı özel efektler oluşturmak için özel fırçayı damga veya şablon gibi kullanabilirsiniz.

### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>Arka plan renginde özel fırça şekilleri çizmek için

1. Opak veya saydam bir arka plan seçin.

1. Arka plan rengini çizmek istediğiniz renge ayarlayın.

1. Çizmek istediğiniz yere özel fırça yerleştirin.

1. Sağ fare düğmesini seçin. Özel fırçanın opak bölgeleri arka plan renginde çizilir.

### <a name="to-double-or-halve-the-custom-brush-size"></a>Özel fırça boyutunu iki katına veya yarıya indirmek için

Fırça boyutunu iki**+** katına çıkarmak için **Artı İşareti** (**-**) tuşuna veya eksi **işaretine** () basın ve yarıya indirin.

### <a name="to-cancel-the-custom-brush"></a>Özel fırçayı iptal etmek için

**Esc tuşuna** basın veya başka bir çizim aracı seçin.

## <a name="requirements"></a>Gereksinimler

None

## <a name="see-also"></a>Ayrıca bkz.

[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)<br/>
[Nasıl yapılır: Simge veya Diğer Resim Oluşturma](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[Nasıl yapılı: Görüntüyü Edin](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[Nasıl yapılır: Renkle Çalışma](../windows/working-with-color-image-editor-for-icons.md)<br/>
[Hızlandırıcı Tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
