---
title: 'Nasıl yapılır: renklerle çalışma'
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
ms.openlocfilehash: 3c9134fde9053f57f8848a37b1442728f6111c98
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502944"
---
# <a name="how-to-work-with-color"></a>Nasıl yapılır: renklerle çalışma

**Görüntü Düzenleyicisi** , renkleri özellikle işleyen ve özelleştiren birçok özellik içerir. Bir ön plan veya arka plan rengi ayarlayabilir, sınırlı alanları renklerle doldurabilir veya geçerli ön plan veya arka plan rengi olarak kullanılacak görüntüde bir renk seçebilirsiniz. [Görüntü Düzenleyicisi araç çubuğundaki](./image-editor-for-icons.md) araçları, renkler oluşturmak için **renkler** penceresindeki renkler paleti ile birlikte kullanabilirsiniz.

Tek renkli ve 16 renkli görüntülerin tüm renkleri **renkler** penceresindeki **renkler** paletinde gösterilir. 16 standart renklerle birlikte kendi özel renklerinizi de oluşturabilirsiniz. Paletteki renklerden herhangi birini değiştirmek görüntüdeki ilgili rengi hemen değiştirecek.

256 renkli simge ve imleç görüntüleriyle çalışırken, [Özellikler penceresi](/visualstudio/ide/reference/properties-window) **renkler** özelliği kullanılır. Daha fazla bilgi için bkz. [256 renkli bir simge veya Imleç oluşturma](./creating-an-icon-or-other-image-image-editor-for-icons.md).

True-Color görüntüleri de oluşturulabilir. Ancak, **renkler** penceresinin tam paletinde gerçek renk örnekleri görünmez; Bunlar yalnızca ön plan veya arka plan rengi gösterge alanında görünürler. **Özel renk seçici** iletişim kutusu kullanılarak gerçek renkler oluşturulur.

Özelleştirilmiş renk paletlerini diskte kaydedebilir ve gerektiğinde yeniden yükleyebilirsiniz. En son kullandığınız renk paleti kayıt defterine kaydedilir ve Visual Studio 'Yu bir sonraki başlatmanızda otomatik olarak yüklenir.

**Renkler** penceresinin iki bölümü vardır:

- Kullanabileceğiniz renkleri temsil eden renk örnekleri dizisi olan **renkler paleti**. Grafik araçlarını kullanırken ön plan ve arka plan renklerini seçmek için örnekleri seçebilirsiniz.

- Ekran ve ters renk için ön plan ve arka plan renklerini ve seçicileri gösteren **renk göstergesi**.

   ![Renkler penceresi](../windows/media/vccolorswindow.gif "vcColorsWindow")<br/>
   **Renkler** penceresi

> [!NOTE]
> **Ekran rengi** ve **ters renk** araçları yalnızca simgeler ve imleçler için kullanılabilir.

[Görüntü Düzenleyicisi araç çubuğu](./image-editor-for-icons.md)ile **renkler** penceresini kullanabilirsiniz.

- **Renkler** penceresini görüntülemek için, bir **Görüntü Düzenleyicisi** bölmesine sağ tıklayıp **renkleri göster penceresini**seçin ya da menü [görüntüsü](./image-editor-for-icons.md)  >  **renkler göster penceresini**seçin.

- **Renkler** penceresini gizlemek için pencereyi kaldırın (Bu eylem, kullanımda olmadığında pencerenin otomatik olarak gizlenmesi için) veya **Kapat** düğmesini seçmeyecektir.

**Renkler** paleti başlangıçta 16 standart renk görüntüler. Görüntülenmiş renkler ile kendi özel renklerinizi de oluşturabilirsiniz. Ardından özelleştirilmiş bir renk paletini kaydedebilir ve yükleyebilirsiniz.

**Özel Renk Seçicisi** iletişim kutusu, görüntünüz için kullandığınız renkleri aşağıdaki özelliklerle özelleştirmenize olanak tanır:

|Özellik|Açıklama|
|--------------------------|--------------------------|
|**Gradyan rengi görüntüleme**|Seçilen rengin değerlerini değiştirir.<br/><br/>Rengin parlaklığını veya RGB değerlerini değiştirmek için değiştirmek istediğiniz renge çapraz artı işareti kaydırarak kaydırıcıyı yukarı veya aşağı taşıyın.|
|**Parlaklık çubuğu**|**Degrade rengi görüntü** kutusunda seçtiğiniz rengin parlaklığını belirler.<br/><br/>Daha fazla parlaklık veya küçültme için çubuğa doğru beyaz oku seçin ve sürükleyin. **Renk** kutusu seçtiğiniz rengi ve belirlediğiniz renk parlaklığını etkiler.|
|**Color**|Tanımladığınız rengin tonunu (renk tekerleği değeri) listeler. Değerler 0 ile 240 arasında değişir; burada 0 kırmızı, 60 sarı, 120 yeşil, 180, 200 siyan ve 240 mavi.|
|**Renk**|Tanımladığınız rengin tonunu (renk tekerleği değeri) listeler. Değerler 0 ile 240 arasında değişir; burada 0 kırmızı, 60 sarı, 120 yeşil, 180, 200 siyan ve 240 mavi.|
|**Cts**|Tanımladığınız rengin doygunluk değerini belirtir. Doygunluk, belirtilen bir tondaki renk miktarıdır. Değerler 0 ile 240 arasındadır.|
|**Lum**|Tanımladığınız rengin parlaklığını (parlaklığını) listeler. Değerler 0 ile 240 arasındadır.|
|**Kırmızı**|Tanımladığınız rengin kırmızı değerini belirtir. Değerler 0 ile 255 arasındadır.|
|**Yeşil**|Tanımladığınız rengin yeşil değerini belirtir. Değerler 0 ile 255 arasındadır.|
|**Mavi**|Tanımladığınız rengin mavi değerini belirtir. Değerler 0 ile 255 arasındadır.|

Özelleştirilmiş renkler içeren bir **renkler** paletini kaydedebilir ve yükleyebilirsiniz. Varsayılan olarak, en son kullanılan **renkler** paleti Visual Studio 'yu başlattığınızda otomatik olarak yüklenir.

> [!TIP]
> **Görüntü Düzenleyicisi** 'Nin varsayılan **renkler** paletini geri yükleme yolu olmadığından, varsayılan ayarları kolayca geri yükleyebilmeniz için *Standart. PAL* veya *default. PAL* gibi bir ad altında varsayılan **renkler** paletini kaydetmelisiniz.

C++ projenizde aşağıdaki özelliklerle kullanmak üzere özel renk paletleri yüklemek için **Palet renklerini yükle** iletişim kutusunu kullanın:

|Özellik|Açıklama|
|-----------------|-----------------|
|**Arama yeri**|Dosya veya klasörü bulmak istediğiniz konumu belirtir.<br/><br/>Başka bir konum seçmek için oku seçin veya araç çubuğundaki klasör simgesini seçerek düzeyleri taşıyın.|
|**Dosya adı**|Açmak istediğiniz dosyanın adını yazmanız için bir alan sağlar.<br/><br/>Daha önce açtığınız bir dosyayı hızlıca bulmak için, varsa açılan listede dosya adını seçin.<br/><br/>Bir dosya arıyorsanız, joker karakter olarak yıldız işareti (*) kullanabilirsiniz. Örneğin, \* \* tüm dosyaların listesini görmek için. yazabilirsiniz. Bir dosyanın tam yolunu da yazabilirsiniz, örneğin, *C:\belgelerim\mycolorpalette.exe* veya * \\ \Networkserver\myfolder\mycolorpalette.exe*.|
|**Dosya türü**|Görüntülenecek dosya türlerini listeler.<br/><br/>Palet (*. PAL), renk paletleri için varsayılan dosya türüdür.|

## <a name="how-to"></a>Nasıl yapılır

### <a name="to-select-foreground-or-background-colors"></a>Ön plan veya arka plan renklerini seçmek için

**Silgi**haricinde, **Görüntü Düzenleyicisi** araç çubuğundaki Araçlar, sırasıyla sol veya sağ fare düğmesine bastığınızda geçerli ön plan veya arka plan rengiyle çizilir.

- Bir ön plan rengi seçmek için, sol fare düğmesi ile **renkler** paletinde istediğiniz rengi seçin.

- Bir arka plan rengi seçmek için, sağ fare düğmesiyle, **renkler** paletinde istediğiniz rengi seçin.

### <a name="to-fill-a-bounded-area-of-an-image-with-a-color"></a>Görüntünün sınırlı bir alanını renkle dolduracak şekilde

**Görüntü Düzenleyicisi** , geçerli çizim rengine veya geçerli arka plan rengine sahip herhangi bir çevrelenmiş görüntü alanını doldurmak için **doldurma** aracı sağlar.

### <a name="to-use-the-fill-tool"></a>Fill aracını kullanmak için

1. **Görüntü Düzenleyicisi** araç çubuğunu kullanın veya menü **görüntüsü**  >  **araçları** ' na gidip **Fill** aracını seçin.

1. Gerekirse, çizim renkleri ' ni seçin. [Renkler paletinde](./image-editor-for-icons.md), arka plan rengi seçmek için bir ön plan rengi veya sağ fare düğmesini seçmek üzere sol fare düğmesini seçin.

1. **Fill** aracını, doldurmasını istediğiniz alana taşıyın.

1. Sırasıyla, ön plan rengiyle veya arka plan rengiyle doldurulacak olan sol veya sağ fare düğmesini seçin.

### <a name="to-pick-up-a-color-from-an-image-to-use-elsewhere"></a>Başka bir yerde kullanmak üzere görüntüden renk almak için

**Seçme rengi**veya renk toplama, araç, sol veya sağ fare düğmesine basmanıza bağlı olarak, görüntüde geçerli ön plan rengi veya arka plan rengi üzerinde herhangi bir renk sağlar. **Renk seç** aracını iptal etmek için başka bir araç seçin.

1. **Görüntü Düzenleyicisi** araç çubuğunu kullanın veya menü **görüntüsü**  >  **araçları** ' na gidin ve **renk seç** aracını seçin.

1. Görüntüden almak istediğiniz rengi seçin.

   > [!NOTE]
   > Bir renk seçtikten sonra, **Görüntü Düzenleyicisi** en son kullanılan aracı yeniden etkinleştirir.

1. Ön plan rengi için sol fare düğmesini veya arka plan rengi için sağ fare düğmesini kullanarak çizin.

### <a name="to-choose-the-background"></a>Arka planı seçmek için

Bir görüntüden seçim yaptığınızda veya bir seçimi kopyaladığınızda, seçimdeki geçerli arka plan rengiyle eşleşen tüm pikseller varsayılan olarak saydamdır ve hedef konumda renkleri gizlemiyor.

Saydam bir arka planda (varsayılan) donuk bir arka plana geçiş yapabilir ve yeniden geri dönebilirsiniz. Seçim aracı kullandığınızda, **saydam arka plan** ve **donuk arka plan** seçenekleri **Görüntü Düzenleyicisi** araç çubuğundaki **seçenek** seçicisinde görüntülenir.

![Arka plan seçenekleri donuk veya saydam &#45;](../windows/media/vcimageeditoropaqtranspback.gif "Arka plan seçenekleri donuk veya saydam &#45;")<br/>
**Görüntü Düzenleyicisi araç çubuğundaki** **saydam ve donuk seçenekler**

#### <a name="to-switch-between-a-transparent-and-opaque-background"></a>Saydam ve donuk arka plan arasında geçiş yapmak için

**Görüntü Düzenleyicisi** araç çubuğunda, **seçenek** seçicisini seçin ve ardından uygun arka planı seçin:

- **Donuk arka plan (O)**: varolan görüntü, seçimin tüm bölümleri tarafından görünmez.

- **Saydam arka plan (T)**: mevcut görüntü, seçimin geçerli arka plan rengiyle eşleşen parçalarını gösterir.

> [!TIP]
> Bir kısayol için **görüntü** menüsünde **Donuk Çiz**' i seçin veya temizleyin.

Görüntünün hangi bölümlerinin saydam olduğunu değiştirmek için seçim zaten etkin durumdayken arka plan rengini değiştirebilirsiniz.

### <a name="to-invert-the-colors-in-a-selection"></a>Seçimdeki renkleri ters çevirmek için

Görüntü **Düzenleyicisi** görüntünün seçili bölümündeki renkleri ters çevirmek için kullanışlı bir yol sağlar, böylece bir görüntünün ters renklerle nasıl görüneceğini söyleyebilirsiniz.

Geçerli seçimdeki renkleri ters çevirmek için menü **görüntüsü**  >  **renkleri ters çevir**' e gidin.

### <a name="to-customize-or-change-colors-on-the-colors-palette"></a>Renkler paletindeki renkleri özelleştirmek veya değiştirmek için

1. Menü **görüntüsü**  >  **renkleri ayarla**' ya gidin.

1. **Özel Renk Seçicisi** iletişim kutusunda, uygun metın kutularına RGB veya HSL değerlerini yazarak rengi tanımlayın veya **degrade rengi görüntü** kutusunda bir renk seçin.

1. Kaydırıcıyı **parlaklık** çubuğuna taşıyarak parlaklığı ayarlayın.

1. Birçok özel renk titremeli ' dir. Düz rengin titremeli rengine en yakın olmasını istiyorsanız **renk** kutusuna çift tıklayın.

   Daha sonra titremeli rengini istediğinize karar verirseniz, renk parlaklığını geri yüklemek için kaydırıcıyı **parlaklık** çubuğunun üzerine taşıyın veya **gradyan renk görüntüleme** kutusundaki ince artı işareti kaydırın.

1. Yeni rengi eklemek için **Tamam ' ı** seçin.

### <a name="to-save-a-custom-colors-palette"></a>Özel renk paleti kaydetmek için

1. Menü **resmi**  >  **kaydetme paleti**' ne gidin.

1. Paleti kaydetmek istediğiniz dizine gidin ve palet için bir ad yazın.

1. **Kaydet**'i seçin.

### <a name="to-load-a-custom-colors-palette"></a>Özel renk paleti yüklemek için

1. Menü **resmi**  >  **Yükleme paleti**' ne gidin.

1. **Renk paleti Yükle** iletişim kutusunda doğru dizine gidin ve yüklemek istediğiniz paleti seçin. **Renk** paletleri. pal dosya uzantısıyla kaydedilir.

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca bkz.

[Simgeler için görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)<br/>
[Nasıl yapılır: simge veya başka görüntü oluşturma](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[Nasıl yapılır: görüntü düzenleme](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[Nasıl yapılır: çizim aracını kullanma](../windows/using-a-drawing-tool-image-editor-for-icons.md)<br/>
[Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
