---
title: 'Nasıl yapılır: Renklerle Çalışma'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.image.color
- vc.editors.customcolorselector
- vc.editors.loadcolorpalette
- vc.editors.colorswindow
helpviewer_keywords:
- images [C++], background colors
- Image editor [C++], Colors Palette
- colors [C++], image
- Colors Palette, Image editor
- palettes, Image editor colors
- foreground colors [C++], Image editor
- colors [C++]
- Image editor [C++], colors
- colors [C++], Image editor
- colors [C++], image
- images [C++], colors
- Image editor [C++], colors
- Fill tool
- colors [C++], image
- images [C++], colors
- colors [C++], selection tools
- Image editor [C++], colors
- Select Color tool
- dithered color, Image editor
- Custom Color Selector dialog box [C++]
- Image editor [C++], Colors Palette
- colors [C++], image
- bitmaps [C++], colors
- images [C++], colors
- HSL values
- Colors Palette, Image editor
- RGB color values
- Adjust Colors command [C++]
- Image editor [C++], dithered color
- Image editor [C++], Colors Palette
- Colors Palette, Image editor
- colors [C++], inverting
- colors [C++]
- Color Indicator
- colors [C++], Colors window
- Colors window, hiding colors
- Show Colors Window command
- Colors window, displaying colors
- color palettes [C++]
- palettes
- palettes, Image editor
- colors [C++], Image editor
- Image editor [C++], palettes
- color palettes
- Load Palette Colors dialog box [C++]
- opaque backgrounds [C++]
- colors [C++], image
- Image editor [C++], transparent or opague backgrounds
- images [C++], transparency
- images [C++], opaque background
- colors [C++], image
- Image editor [C++], color inversion
- images [C++], colors
- colors [C++], inverting
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
ms.openlocfilehash: e91767083f54df0b1b30833337cfed603dc331ff
ms.sourcegitcommit: 24592ba0a38c7c996ffd3d55fe1024231a59ccc2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/18/2019
ms.locfileid: "56336650"
---
# <a name="how-to-work-with-color"></a>Nasıl yapılır: Renklerle Çalışma

**Resim Düzenleyicisi** özellikle işleyen ve renk özelleştirme birçok özellik içerir. Bir ön plan veya arka plan rengini ayarlamak, sınırlanmış alanları rengi ile doldurmak veya bir rengi geçerli bir ön plan veya arka plan rengi olarak kullanılacak bir görüntü seçin. Araçlarını kullanabileceğiniz [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md) renk paletindeki açık griyi birlikte **renkleri** görüntüleri oluşturmak için pencere.

Tek renkli ve 16 renk görüntülerini tüm renkleri gösterilen **renkleri** palette **renkleri** penceresi. 16 standart renkler yanı sıra, kendi özel renkler oluşturabilirsiniz. Herhangi bir palet renkleri değiştirme, görüntü içinde karşılık gelen renk hemen değişir.

256-renk simgesi ve imleç görüntü ile çalışırken **renkleri** özelliğinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window) kullanılır. Daha fazla bilgi için [256-renk simgesi veya imleci oluşturma](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md).

> [!NOTE]
> Kullanarak **Resim Düzenleyicisi**, 32 bitlik resimleri görüntüleyebilirsiniz, ancak onları düzenleyemezsiniz.

TRUE-Renk görüntülerini de oluşturulabilir. Ancak gerçek renk örnekleri tam palette görünmez **renkleri** penceresi; bunlar yalnızca ön plan veya arka plan renk göstergesi alanında görüntülenir. Doğru renk kullanılarak oluşturulur [Özel Renk Seçici iletişim kutusu](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md).

Disk üzerinde özelleştirilmiş renk paletlerini kaydetme ve bunları gerektiği şekilde yeniden yükleyin. En son kullanılan renk paletini kayıt defterine kaydedilen ve Visual Studio'yu yeniden başlattığınızda otomatik olarak yüklenir.

**Renkleri** penceresinde iki bölümü vardır:

- **Renkler paleti**, kullanabileceğiniz renkleri temsil eden renkli örnekleri dizisi. Grafik araçları kullanırken ön ve arka plan renkleri seçmek için örnekleri seçebilirsiniz.

- **Renk göstergesi**, ön ve arka plan renkleri ve ekran ve ters renk seçicileri gösterir.

   ![Renkler penceresini](../windows/media/vccolorswindow.gif "vcColorsWindow")<br/>
   Renkler Penceresi

> [!NOTE]
> **Ekran rengi** ve **ters renk** araçlardır yalnızca simgeler ve İmleçler için kullanılabilir.

Kullanabileceğiniz **renkleri** penceresiyle [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md).

- Görüntülenecek **renkleri** penceresinde sağ tıklatın bir **görüntü Düzenleyicisi** bölmesinde seçin **renkler penceresini göster**, ya da seçin **renkler penceresini göster**üzerinde [Görüntü menüsü](../windows/image-menu-image-editor-for-icons.md).

- Gizlemek için **renkleri** penceresinde (Bu eylem sağlayacaktır pencereyi otomatik gizle kullanımda olmadığında) pencereyi sabitleme veya **Kapat** düğmesi.

**Renkleri** paleti 16 standart renkler başlangıçta görüntüler. Görüntülenen renklerle kendi özel renkler de oluşturabilirsiniz. Ardından, kaydedin ve özelleştirilmiş renk paleti yükleyin.

**Özel renk seçici** iletişim kutusu, görüntünüzü kullanmak renkleri özelleştirmek tanır. Dahil edilen aşağıdaki özellikler şunlardır:

|Özellik|Açıklama|
|--------------------------|--------------------------|
|**Gradyan renk görüntüleme**|Seçili renk değerlerini değiştirir. Değiştirmek istediğiniz konumu artı işaretinin rengi. Ardından kaydırıcıyı parlaklık veya rengin RGB değerleri yukarı veya aşağı değişiklik taşıyın.|
|**Parlaklık Çubuğu**|Seçtiğiniz renk parlaklığını ayarlar **gradyan renkli görüntüyü** kutusu. Büyük parlaklık için çıtayı yukarı beyaz oku sürükleyin ya da daha az aşağı. **Renk** kutusu seçtiğiniz rengi ve ayarladığınız parlaklık etkisini gösterir.|
|**Renk**|Tanımlama renk tonunu (renk tekerleği değer) listeler. Burada 0 kırmızı, 60 sarı, 120 yeşil, mavi 180 olduğundan, 200 Eflatun ve 240 mavi 240 değerler aralığı 0.|
|**Hue**|Tanımlama renk tonunu (renk tekerleği değer) listeler. Burada 0 kırmızı, 60 sarı, 120 yeşil, mavi 180 olduğundan, 200 Eflatun ve 240 mavi 240 değerler aralığı 0.|
|**CTS**|Tanımlama renk doygunluğu değerini belirtir. Doygunluk belirtilen bir renk tonu rengi miktarıdır. Değerler aralığı 0-240.|
|**Par**|Tanımlama renk parlaklığını (Parlaklık) listeler. Değerler aralığı 0-240.|
|**Kırmızı**|Kırmızı, tanımlayacağınız renk değerini belirtir. Değerler aralığı 0-255.|
|**Yeşil**|Yeşil, tanımlayacağınız renk değerini belirtir. Değerler aralığı 0-255.|
|**Mavi**|Tanımlama rengini Mavi değerini belirtir. Değerler aralığı 0-255.|

Kaydet ve yük bir **renkleri** içeren özelleştirilmiş renkler paleti. (Varsayılan olarak, **renkleri** en son kullanılan palet Visual Studio'yu başlattığınızda otomatik olarak yüklenir.)

> [!TIP]
> Bu yana **görüntü** Düzenleyicisi olan varsayılan geri yüklemek için anlamına gelir **renkleri** paleti varsayılan kaydetmelisiniz **renkleri** palet gibi bir ad altında  *Standard.PAL* veya *default.pal* böylece bir kolayca varsayılan ayarları geri yükleyebilirsiniz.

Kullanma **palet renkleri Yükle** C++ projenizde kullanılacak özel renk paletlerini yüklemek için iletişim kutusu. Dahil edilen aşağıdaki özellikler şunlardır:

|Özellik|Açıklama|
|-----------------|-----------------|
|**İçine bak**|Bir dosya veya klasörü bulmak için istediğiniz konumu belirtir. Başka bir konum seçmek için oku seçin veya düzeyleri yukarı taşımak için araç çubuğundaki klasör simgesini seçin.|
|**Dosya adı**|Açmak istediğiniz dosyanın adını yazmanız için bir alan sağlar. Hızlıca önceden açmış olduğunuz dosyayı bulmak için varsa aşağı açılan listede, dosya adı seçin.<br/><br/>Bir dosya için arıyorsanız, joker karakter olarak yıldız işareti (*) kullanabilirsiniz. Örneğin, yazabilirsiniz \*.\* tüm dosyaların listesini görmek için. Ayrıca, örneğin, C:\My Documents\MyColorPalette.pal dosyasının tam yolunu yazın veya \\\NetworkServer\MyFolder\MyColorPalette.pal.|
|**Dosya türü**|Görüntülenecek dosya türlerini listeler. Palet (* .pal) renk paletlerini için varsayılan dosya türüdür.|

## <a name="how-to"></a>Nasıl Yapılır

### <a name="to-select-foreground-or-background-colors"></a>Ön plan veya arka plan renklerini seçin

Dışında **Silgi**, Araçlar **Resim Düzenleyicisi** araç çubuğu çizim sırasıyla sol veya sağ fare düğmesine bastığınızda geçerli ön plan veya arka plan rengi.

- Ön plan rengi, farenin sol düğmesiyle seçmek için istediğiniz rengi seçin **renkleri** palet.

- Arka plan rengi, farenin sağ düğmesiyle seçmek için istediğiniz rengi seçin **renkleri** palet.

### <a name="to-fill-a-bounded-area-of-an-image-with-a-color"></a>Görüntünün sınırlı bir alanını renkle doldurmak için

Resim Düzenleyicisi sağlar **dolgu** herhangi doldurma aracı geçerli çizim rengini veya arka plan rengi geçerli görüntü alanını alınmış.

> [!TIP]
> İmlecinizi bir araç çubuğu düğmenin üzerine geldiğinizde araç ipuçlarında görünür. Bu ipuçları her düğmesinin işlevini belirlemenize yardımcı olabilir.

### <a name="to-use-the-fill-tool"></a>Dolgu aracı kullanmak için

1. Üzerinde **Resim Düzenleyicisi** araç çubuğu (veya **görüntü** > **Araçları**) seçin **dolgu** aracı.

1. Gerekirse, renkler çizim seçin: İçinde [renkler paleti](../windows/colors-window-image-editor-for-icons.md), ön plan rengi seçmesini farenin sol düğmesine veya arka plan rengi seçmek için sağ fare düğmesini seçin.

1. Taşıma **dolgu** doldurmak istediğiniz alanı için aracı.

1. Sırasıyla ön plan rengini veya arka plan rengi ile doldurmak için sol veya sağ fare düğmesini seçin.

### <a name="to-pick-up-a-color-from-an-image-to-use-elsewhere"></a>Başka bir yerde kullanmak üzere görüntüden renk seçmek için

**Rengi seçin**, veya geçerli ön plan rengini veya arka plan rengi, sol veya sağ fare düğmesine basın olup olmadığına bağlı olarak, aracı-alma, renk görüntünün üzerinde herhangi bir renk yapar. İptal etmek için **rengi seçin** aracı, başka bir aracı seçin.

> [!TIP]
> İmlecinizi bir araç çubuğu düğmenin üzerine geldiğinizde araç ipuçlarında görünür. Bu ipuçları her düğmesinin işlevini belirlemenize yardımcı olabilir.

#### <a name="to-pick-up-a-color"></a>Renk seçmek için

1. Üzerinde **Resim Düzenleyicisi** araç çubuğu (veya **görüntü** menüsünde **Araçları** komutu) seçin **rengi seçin** aracı.

1. Görüntüyü almak istediğiniz rengi seçin.

   > [!NOTE]
   > Renk, seçin sonra **görüntü** Düzenleyicisi yeniden etkinleştirir en son kullanılan araç.

1. Ön plan rengini veya arka plan rengi sağ fare düğmesi için sol fare düğmesini kullanarak çizin.

### <a name="to-choose-the-background"></a>Arka plan seçme

Taşıdığınızda veya bir görüntüden bir seçimi Kopyala Geçerli arka plan rengiyle uyuşan pikselleri seçimdeki, varsayılan olarak, saydam olan ve hedef konum piksellerde gizlememeniz yok.

Donuk bir arka plan için saydam bir arka planından (varsayılan) geçin ve yeniden. Bir seçim aracını kullandığınızda **saydam arka plan** ve **donuk arka plan** seçenekleri görünür **seçeneği** seçicisinde **GörüntüDüzenleyicisi** (aşağıda görüldüğü gibi) araç çubuğu.

![Arka plan seçeneklerini &#45; opak ya da şeffaf](../windows/media/vcimageeditoropaqtranspback.gif "arka plan seçeneklerini &#45; opak ya da şeffaf")<br/>
**Saydam ve donuk seçenekleri** üzerinde **Resim Düzenleyicisi araç çubuğu**

#### <a name="to-switch-between-a-transparent-and-opaque-background"></a>Saydam ve donuk arka plan arasında geçiş yapmak için

İçinde **Resim Düzenleyicisi** araç, select **seçeneği** Seçici, uygun arka plan seçin:

- `Opaque Background (O)`: Mevcut görüntü seçimi tüm bölümleri tarafından engellenmesidir.

- `Transparent Background (T)`: Mevcut görüntü seçimin geçerli arka plan rengiyle uyuşan parçaları gösterilmektedir.

   \- veya -

Üzerinde **görüntü** menüsünü seçin veya temizleyin **çizmek opak**.

Bir seçim hangi parçalarının resminin saydam değiştirmek için etkin durumdayken arka plan rengini değiştirebilirsiniz.

### <a name="to-invert-the-colors-in-a-selection"></a>Seçimdeki renkleri ters çevirmek için

**Görüntü** Düzenleyicisi görüntü ters renklerle nasıl görüneceği söyleyebilirsiniz. böylece, seçili bir görüntünün parçası olarak renkleri ters çevir için kullanışlı bir yol sağlar.

Geçerli seçimdeki renkleri ters çevir şirket için **görüntü** menüsünde **renkleri**.

### <a name="to-customize-or-change-colors-on-the-colors-palette"></a>Renkler paleti renkleri değiştirmek veya özelleştirmek

1. Gelen **görüntü** menüsünde seçin **renkleri Ayarla**.

1. İçinde **özel renk seçici** iletişim kutusunda rengin RGB veya HSL değerleri ilgili metin kutularına yazarak tanımlayın veya bir renk seçin **gradyan renkli görüntüyü** kutusu.

1. Kaydırıcıyı hareket ettirerek parlaklık ayarlamak **parlaklık** çubuğu.

1. Birçok özel renkler Titrek. Düz renk Titremeli renk en yakın istiyorsanız çift **renk** kutusu.

   Titremeli renk istediğiniz daha sonra karar verirseniz, kaydırıcıyı taşıyın **parlaklık** çubuk veya işaretçileri taşıma **gradyan renkli görüntüyü** renk paleti öykünmesi yeniden yüklemeyi kutusu.

1. Seçin **Tamam** rengi ekleyin.

### <a name="to-save-a-custom-colors-palette"></a>Özel renkler paleti kaydetmek için

1. Gelen **görüntü** menüsünde seçin **Kaydet palet**.

1. Palet kaydetmek istediğiniz dizine gidin ve palet için bir ad yazın.

1. **Kaydet**’i seçin.

### <a name="to-load-a-custom-colors-palette"></a>Özel renkler paleti yüklemek için

1. Gelen **görüntü** menüsünde seçin **palet Yükle**.

1. İçinde **renk paletini yük** iletişim kutusunda doğru dizine gidin ve yüklemek istediğiniz paletini seçin. **Renk** paletleri .pal dosya uzantısıyla kaydedilir.

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Cihaz görüntülerinde saydam veya ters bölgeler oluşturma](../windows/creating-transparent-or-inverse-regions-in-device-images.md)<br/>
[Özel Renk Seçici iletişim kutusu](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)<br/>
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)<br/>
[Görüntü menüsü](../windows/image-menu-image-editor-for-icons.md)<br/>
