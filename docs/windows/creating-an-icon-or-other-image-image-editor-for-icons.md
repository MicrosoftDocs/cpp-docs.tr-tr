---
title: Simge veya Başka Görüntü Oluşturma
ms.date: 11/04/2016
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
- vc.editors.newimagetype
- vc.editors.customimage
- vc.editors.opendeviceimage
- vc.editors.image.editing
- vc.editors.image.editing
helpviewer_keywords:
- bitmaps [C++]
- images [C++], creating
- resources [C++], creating images
- bitmaps [C++], creating
- graphics [C++], creating
- Image editor [C++], creating images
- cursors [C++], creating
- image resources [C++], display devices
- icons [C++], creating
- cursors [C++], types
- icons [C++]
- Image editor [C++], icons and cursors
- cursors [C++]
- display devices [C++], creating icons for
- cursors [C++], hot spots
- icons [C++], types
- icons [C++], creating
- display devices [C++], creating image
- images [C++], creating for display devices
- icons [C++], inserting
- New <Device> Image Type dialog box [C++]
- Custom Image dialog box [C++]
- Open <Device> Image dialog box [C++]
- New Device Image command
- display devices [C++], adding images
- cursors [C++], adding
- icons, adding
- display devices [C++], copying images
- cursors [C++], copying
- icons, copying
- cursors [C++], deleting
- display devices [C++], deleting device image
- icons, erasing
- icons, deleting
- cursors [C++], undoing changes
- icons, undoing changes
- cursors [C++], screen regions
- inverse colors [C++], device images
- transparent regions, device images
- transparency, device images
- Image editor [C++], device images
- inverse regions, device images
- cursors [C++], transparent regions
- screen colors
- regions, transparent
- icons [C++], transparent regions
- display devices [C++], transparent and screen regions
- transparent regions in devices
- regions, inverse
- colors [C++], Image editor
- device projects [C++], transparent images
- icons [C++], screen regions
- 256-color palette
- cursors [C++], color
- colors [C++], icons
- colors [C++], cursors
- icons, color
- colors [C++], icons and cursors
- color palettes, 256-color
- palettes, 256-color
- cursors [C++], hot spots
- hot spots
- .gif files [C++], saving bitmaps as
- jpg files [C++], saving bitmaps as
- jpeg files [C++], saving bitmaps as
- .jpg files [C++], saving bitmaps as
- Image editor [C++], converting image formats
- gif files [C++], saving bitmaps as
- bitmaps [C++], converting formats
- .jpeg files [C++], saving bitmaps as
- graphics [C++], converting formats
- images [C++], converting formats
- images [C++], stand-alone editing
- Image editor [C++], converting image formats
- graphics [C++], converting formats
- images [C++], converting formats
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
ms.openlocfilehash: 3ce4d10c9ab085973f1ab00dba205c22ff17f42f
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320737"
---
# <a name="creating-an-icon-or-other-image"></a>Simge veya Başka Görüntü Oluşturma

Yeni bir görüntü (bit eşlemi, simge, imleç veya araç) oluşturmak ve görünümünü özelleştirmek için görüntü Düzenleyicisi'ni kullanın. Desenli sonra yeni bir bit eşlem oluşturabilirsiniz bir [şablon](../windows/how-to-use-resource-templates.md).

## <a name="icons-and-cursors-image-resources-for-display-devices"></a>Simgeler ve İmleçler: Görüntüleme cihazları için görüntü kaynakları

Simgeler ve İmleçler, farklı boyutlarda birden fazla görüntüler içerir ve düzenleri görüntüleme cihazları farklı türleri için renk grafik kaynaklardır. Ayrıca, bir imleç "etkin nokta," Windows konumuna izlemek için kullandığı konumun sahiptir. Simgeler ve İmleçler hem oluşturulur ve düzenlenebilir **görüntü** Düzenleyicisi, bit eşlemler ve diğer görüntüler.

Yeni simgesi veya imleci, oluşturduğunuzda **görüntü** Düzenleyicisi ilk standart türünde bir görüntü oluşturur. Görüntü başlangıçta ekran (saydam) renkle doldurulur. Görüntünün bir imleç etkin nokta başlangıçta sol üst köşesinin (koordinatları 0,0) ise.

Varsayılan olarak, **görüntü** Düzenleyicisi aşağıdaki tabloda gösterilen cihazlar için ek görüntüleri oluşturulmasını destekler. Genişlik, yükseklik ve renk sayısı parametreleri içine yazarak diğer cihazları için görüntü oluşturabilirsiniz [özel görüntü iletişim kutusu](custom-image-dialog-box-image-editor-for-icons.md).

> [!NOTE]
> Kullanarak **Resim Düzenleyicisi**, 32 bitlik resimleri görüntüleyebilirsiniz, ancak onları düzenleyemezsiniz.

|Renk|Genişlik (piksel cinsinden)|Yükseklik (piksel cinsinden)|
|-----------|----------------------|-----------------------|
|Tek renkli|16|16|
|Tek renkli|32|32|
|Tek renkli|48|48|
|Tek renkli|64|64|
|Tek renkli|96|96|
|16|16|16|
|16|32|32|
|16|64|64|
|16|48|48|
|16|96|96|
|256|16|16|
|256|32|32|
|256|48|48|
|256|64|64|
|256|96|96|

### <a name="create-a-device-image-icon-or-cursor"></a>Cihaz görüntüsü (simgesi veya imleci) oluşturma

Yeni simgesi veya imleci kaynak oluşturduğunuzda **görüntü** Düzenleyicisi ilk oluşturur görüntü özel bir stili (32 x 32, 16 renk simgelerinin ve 32 x 32, tek renkli işaretçiler için). Ardından, ilk simgesi veya imleci için görüntüleri farklı boyut ve stil ekleyin ve ek her görüntü, farklı ekran cihazları için gerektiği gibi düzenleyin. Varolan bir görüntü türü veya bir grafik programında oluşturulan bir bit eşlem kesme ve yapıştırma işlemi kullanarak görüntü de düzenleyebilirsiniz.

Simgesi veya imleci kaynak açtığınızda [Resim Düzenleyicisi](../windows/image-editor-for-icons.md), görüntünün en yakın geçerli görüntü cihazı eşleşen varsayılan olarak açılır.

#### <a name="new-ltdevicegt-image-type-dialog-box"></a>Yeni &lt;cihaz&gt; görüntü türü iletişim kutusu

**Yeni &lt;cihaz&gt; görüntü türü** iletişim kutusu belirtilen bir türün yeni cihaz görüntüsü oluşturmanıza olanak sağlar. Açmak için **yeni \<cihaz > Görüntü** iletişim kutusunda **yeni görüntü tipi** üzerinde **görüntü** menüsü. Dahil edilen aşağıdaki özellikler **hedef görüntü tipi** ve **özel**.

##### <a name="target-image-type"></a>Hedef görüntü türü

Mevcut görüntü türlerini listeler. Açmak istediğiniz görüntü türünü seçin:

||||
|-|-|-|
|-16 16 x 16 renk|-48 x 48, 16 renk|-96 x 96 16 renk|
|-16 x 16, 256 renkleri|-48 x 48, 256 renkleri|-96 x 96, 256 renkleri|
|-16 x 16, tek renkli|-48 x 48, tek renkli|-96 x 96, tek renkli|
|-32 x 32 16 renk|-64, x 64 16 renk||
|-32 x 32, 256 renkleri|-64 x 64, 256 renkleri||
|-32 x 32, tek renkli|-64 x 64, tek renkli||

> [!NOTE]
> Bu listede herhangi bir mevcut görüntü görüntülenmez.

##### <a name="custom"></a>Özel

Açılır **özel görüntü** içinde oluşturabileceğiniz yeni bir görüntü özel boyutu ve renklerin sayısı ile iletişim kutusu.

**Özel görüntü** iletişim kutusu özel boyutu ve renk sayısını yeni bir görüntü oluşturmanıza olanak sağlar. Dahil edilen aşağıdaki özellikler şunlardır:

|Özellik|Açıklama|
|---|---|
|**Genişlik**|Özel görüntü genişliğini piksel cinsinden (1-512 sınırını 2048) girmeniz için bir alan sağlar.|
|**Yükseklik**|Özel görüntü (1-512 sınırını 2048) piksel cinsinden yüksekliği girmek bir alan sağlar.|
|**Renkler**|Özel görüntü için renk sayısını seçmenize olanak sağlar: 2, 16 veya 256.|

#### <a name="open-ltdevicegt-image-dialog-box"></a>Açık &lt;cihaz&gt; görüntü iletişim kutusu

Kullanım **açın &lt;cihaz&gt; görüntü** C++ projelerinde cihaz görüntüleri açmak için iletişim kutusu. Geçerli kaynak (geçerli kaynak bir parçası olan görüntüleri) var olan cihaz görüntülerinde listeler. Dahil edilen aşağıdaki özelliğidir:

|Özellik|Açıklama|
|---|---|
|**Mevcut görüntülerin**|Kaynakta bulunan görüntüleri listeler. Açmak istediğiniz görüntü türü seçin.|

#### <a name="to-create-a-new-icon-or-cursor"></a>Yeni simgesi veya imleci oluşturma

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasına sağ tıklayın ve ardından seçin **kaynak Ekle** kısayol menüsünden. (Bir imleç gibi bir .rc dosyasında var olan bir görüntü kaynağı zaten varsa sağ tıklayabilirsiniz **imleç** klasörü ve select **imleci yerleştirin** kısayol menüsünden.)

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, bkz. [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md)seçin **simgesi** veya **imleç** ve **yeni**. Simgeleri için bu eylem bir 32 x 32 ile 16-renk simgesi bir simge kaynağı oluşturur. İmleçler, bir 32 x 32, tek renkli (2-color) görüntü oluşturulur.

   Bir artı işareti (**+**) görüntü kaynak türünü yanında **kaynak Ekle** iletişim kutusu, geldiğini araç şablonları kullanılabilir. Şablonlar listesinde genişletin, bir şablon seçin veya seçmek için artı işaretini seçin **yeni**.

### <a name="add-an-image-for-a-different-display-device"></a>Farklı görüntüleme cihazı için görüntü ekleme

1. Üzerinde **görüntü** menüsünde **yeni cihaz görüntüsü** (veya sağ **Resim Düzenleyicisi** bölmesinde seçin **yeni cihaz görüntüsü** gelen kısayol menüsü).

1. Eklemek istediğiniz görüntü türünü seçin. Belirleyebilirsiniz **özel** boyutu varsayılan listesinde kullanılabilir olmayan bir simge oluşturmak için.

### <a name="copy-a-device-image"></a>Cihaz görüntüsü kopyalama

1. Üzerinde **görüntü** menüsünde **açık cihaz görüntüsü** ve geçerli görüntüleri listesinden görüntü seçin. Örneğin, 32 × 32 bir simge 16 renk sürümünü seçin.

1. Şu anda görüntülenen simge görüntüsü kopyalama (**Ctrl**+**C**).

1. Farklı bir simge görüntüsü başka bir programda açık **Resim Düzenleyicisi** penceresi. Örneğin, 16 x 16, simgenin 16 renk sürümü açın.

1. Simge görüntüsü yapıştırın (**Ctrl**+**V**) birinden **Resim Düzenleyicisi** diğer pencere. Daha büyük bir boyutu daha küçük bir boyuta yapıştırıyorsanız, görüntüyü yeniden boyutlandırmak için simge tutamaçlarını kullanabilirsiniz.

### <a name="delete-a-device-image"></a>Cihaz görüntüsünü silme

Simge görüntüsü görüntülenirken **görüntü** Düzenleyicisi'ni seçin **cihaz görüntüsünü silme** gelen **görüntü** menüsü. Kaynak son simge görüntüsü sildiğinizde, kaynak da silinir.

   > [!NOTE]
   > Bastığınızda **Del** anahtar, bir simge çizilmiş renkleri ve görüntüleri silinir ancak simge kalır; artık bunu tasarlayabilirsiniz. Basarsanız **Del** yanlışlıkla basabilirsiniz **Ctrl**+**Z** eylemi geri alamazsınız.

### <a name="create-transparent-or-inverse-regions-in-device-images"></a>Cihaz görüntülerinde saydam veya ters bölgeler oluşturma

İçinde [Resim Düzenleyicisi](../windows/image-editor-for-icons.md), ilk simgesi veya imleci görüntünün saydam bir öznitelik vardır. Simge ve imleç görüntü dikdörtgen olsa da, görüntünün bölümlerini şeffaf olduğundan çok bunu görünmez; temel alınan görüntünün ekranında simgesi veya imleci gösterilir. Simge sürüklediğinizde, bir ters renkte bölümleri görünebilir. Ekran rengi ve ters renk ayarlayarak bu etkiyi oluşturmak [renkler penceresini](../windows/colors-window-image-editor-for-icons.md).

Ekran ve ters renk uyguladığınız için simgeler ve İmleçler şekil ve türetilmiş görüntü renk veya ters bölgeler atamak. Renkleri, bu özniteliklere sahip görüntünün parçalarını gösterir. Düzenleme ekranı rengi ve ters renk özniteliklerini temsil eden renklerini değiştirebilirsiniz. Bu değişiklikler simgesi veya imleci uygulamanızın görünümünü etkilemez.

> [!NOTE]
> İletişim kutuları ve menü komutları gördüğünüz içinde açıklanana göre farklılık **yardımcı** bağlı olarak, etkin ayarlarınıza ve sürüm. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).

#### <a name="to-create-transparent-or-inverse-regions"></a>Saydam veya ters bölgeler oluşturma

1. İçinde **renkleri** penceresinde **ekran rengi** Seçici veya **ters renk** Seçici.

1. Ekran veya ters renk, resim çizim aracı kullanma uygulayın. Çizim Araçları ile ilgili daha fazla bilgi için bkz: [çizim aracı kullanma](using-a-drawing-tool-image-editor-for-icons.md).

#### <a name="to-change-the-screen-or-inverse-color"></a>Ekran veya ters rengini değiştirmek için

1. Şunlardan birini seçin **ekran rengi** Seçici veya **ters renk** Seçici.

1. Bir renk seçin **renkleri** palette **renkleri** penceresi.

   Tamamlayıcı renk diğer Seçicisi otomatik olarak atanır.

   > [!TIP]
   > Çift tıkladığınızda, **ekran rengi** veya **ters renk** Seçici, [Özel Renk Seçici iletişim kutusu](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md) görünür.

### <a name="use-the-256-color-palette"></a>256-renk paletini kullanma

Kullanarak **görüntü** Düzenleyicisi, simgeler ve İmleçler boyutlu büyük (64 × 64) aralarından seçim yapabileceğiniz bir 256-renk paletini sahip olabilir. Kaynak oluşturduktan sonra bir cihaz görüntü stili seçilir.

#### <a name="to-create-a-256-color-icon-or-cursor"></a>256-renk simgesi veya imleci oluşturma

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasına sağ tıklayın ve ardından seçin **kaynak Ekle** kısayol menüsünden. (Bir imleç gibi bir .rc dosyasında var olan bir görüntü kaynağı zaten varsa sağ tıklayabilirsiniz **imleç** klasörü ve select **imleci yerleştirin** kısayol menüsünden.)

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md)seçin **simgesi** veya **imleç** ve **yeni**.

1. Üzerinde **görüntü** menüsünde **yeni cihaz görüntüsü**.

1. 256-renk görüntü stili seçin.

#### <a name="to-choose-a-color-from-the-256-color-palette-for-large-icons"></a>Büyük simgeler için 256-renk paletinden bir renk seçmek için

256-renk paletinden bir seçimle çizmek için renk seçmeniz gerekir **renkleri** palette [renkler penceresini](../windows/colors-window-image-editor-for-icons.md).

1. Büyük simgesi veya imleci seçin veya yeni büyük simgesi veya imleci oluşturma.

1. Görüntülenen 256 renkten bir renk seçin **renkleri** palette **renkleri** penceresi.

   Seçili renk geçerli rengi olur **renkleri** palette **renkleri** penceresi.

   > [!NOTE]
   > 256-renk görüntüler için kullanılan ilk paleti tarafından döndürülen palet eşleşen `CreateHalftonePalette` Windows API. Windows Kabuğu için hedeflenen tüm simgeleri palet gerçekleştirme sırasında titreşimini önlemek için bu paletin kullanmanız gerekir.

### <a name="set-a-cursor39s-hot-spot"></a>Bir imleç ayarlamak&#39;s etkin nokta

Bir imlecin etkin noktasını noktasıdır imlecinizin konumunu izlemek için Windows başvurduğu için. Varsayılan olarak etkin nokta imleci (koordinatları 0,0) sol üst köşesinde ayarlanır. **Etkin nokta** özelliğinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window) etkin nokta koordinatları gösterir.

#### <a name="to-set-a-cursors-hot-spot"></a>İmlecin etkin noktasını ayarlama

1. Üzerinde [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md), seçin **etkin nokta Ayarla** aracı.

1. İmlecin etkin noktasını atamak istediğiniz piksel seçin.

   **Etkin nokta** özelliğinde **özellikleri** penceresi yeni koordinatları görüntüler.

   > [!TIP]
   > İmlecinizi bir araç çubuğu düğmenin üzerine geldiğinizde araç ipuçlarında görünür. Bu ipuçları her düğmesinin işlevini belirlemenize yardımcı olabilir.

## <a name="saving-bitmaps-as-gifs-or-jpegs"></a>Bit Eşlemleri GIF veya JPEG Olarak Kaydetme

Bir bit eşlem oluşturduğunuzda, görüntü bit eşlem (.bmp) biçiminde oluşturulur. Ancak, görüntünün bir GIF veya JPEG olarak veya diğer grafik biçimlerde tasarruf edebilirsiniz.

> [!NOTE]
> Bu işlem, simgeler ve İmleçler için geçerli değildir.

### <a name="to-create-and-save-a-bitmap-as-a-gif-or-jpeg"></a>Oluşturmak ve bir bit eşlem .gif veya .jpeg olarak kaydetmek için

1. Gelen **dosya** menüsünde seçin **açık**, ardından **dosya**.

1. İçinde **yeni dosya iletişim kutusu**, seçin **Visual C++** klasörünü seçip **bit eşlem dosyası (.bmp)** içinde **şablonları** kutusunda ve seçin **Açık**.

   Bit eşlem açılır **görüntü** Düzenleyici.

1. Yeni, bit eşlem için gerekli değişiklikleri yapın.

1. Bit eşlem içinde açık olan **görüntü** Düzenleyicisi'ni seçin **Kaydet *filename*.bmp olarak** üzerinde **dosya** menüsü.

1. İçinde **dosyayı farklı Kaydet** iletişim kutusuna, dosya ve istediğiniz dosya biçimini gösterir uzantısı vermek istediğiniz adı yazın **dosya adı** kutusu. Örneğin, *myfile.gif*.

   > [!NOTE]
   > Oluşturma veya başka bir dosya biçiminde kaydetmek için projenizin dışında bit eşlem açmak gerekir. Oluşturur veya kendi projesi içinde açın **Kaydet** komutu kullanılamaz. Daha fazla bilgi için [kaynaklar içinde bir kaynak betik dosyası dışında sonuna bir proje (tek başına) görüntüleme](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

1. **Kaydet**’i seçin.

## <a name="converting-an-image-from-one-format-to-another"></a>Görüntüyü Bir Biçimden Diğerine Dönüştürme

GIF veya JPEG resimleri açabileceğiniz **görüntü** Düzenleyicisi ve bit eşlemler kaydedebilirsiniz. Ayrıca, bir bit eşlem dosyası açın ve bir GIF veya JPEG olarak kaydetme. İş görüntüleri olması gerekmez geliştirme ortamında düzenlemek için bir projenin parçası (bkz [tek başına resim düzenleme](../windows/editing-an-image-outside-of-a-project-image-editor-for-icons.md)).

### <a name="to-convert-an-image-from-one-format-to-another"></a>Görüntüyü bir biçimden diğerine dönüştürmek için

1. Görüntüde açın **görüntü** Düzenleyici.

1. Gelen **dosya** menüsünde seçin **Kaydet *filename* olarak**.

1. İçinde **dosyayı farklı Kaydet** iletişim kutusundaki **dosya adı** dosya adı ve biçimini gösteren uzantısını yazın.

1. **Kaydet**’i seçin.

## <a name="to-add-a-new-image-resource-to-an-unmanaged-c-project"></a>Yönetilmeyen C++ projesinde yeni bir görüntü kaynağı eklemek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasına sağ tıklayın ve ardından seçin **kaynak Ekle** kısayol menüsünden. (Bir imleç gibi bir .rc dosyasında var olan bir görüntü kaynağı zaten varsa, yalnızca sağ tıklayabilirsiniz **imleç** klasörü ve select **imleci yerleştirin** kısayol menüsünden.)

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md), oluşturmak istediğiniz görüntü kaynak türünü seçin (**bit eşlem**, örneğin) ardından **yeni**.

   Bir artı işareti (**+**) görüntü kaynak türünü yanında **kaynak Ekle** iletişim kutusu, geldiğini araç şablonları kullanılabilir. Şablonlar listesinde genişletin, bir şablon seçin veya seçmek için artı işaretini seçin **yeni**.

## <a name="to-add-a-new-image-resource-to-a-project-in-a-net-programming-language"></a>Yeni bir görüntü kaynağı bir programlama dilinde bir .NET projesine eklemek için

1. İçinde **Çözüm Gezgini**, proje klasörüne sağ tıklayın (örneğin, `WindowsApplication1`).

1. Kısayol menüsünden seçin **Ekle**, ardından **Yeni Öğe Ekle**.

1. İçinde **kategorileri** bölmesini genişletin **yerel proje öğeleri** klasörü seçin **kaynakları**.

1. İçinde **şablonları** bölmesinde, projenize eklemek istediğiniz kaynak türünü seçin.

   Projenizde kaynağa eklenir **Çözüm Gezgini** ve kaynak açılır [Resim Düzenleyicisi](../windows/image-editor-for-icons.md). Artık, görüntünüzü değiştirmek için görüntü Düzenleyicisi'nde kullanılabilir olan tüm araçları da kullanabilirsiniz. Görüntüleri yönetilen bir projeye ekleme ile ilgili daha fazla bilgi için bkz: [tasarım zamanında bir resim yükleme](/dotnet/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms).

   > [!NOTE]
   > Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez. Daha fazla bilgi için [Creating Resource Files](/dotnet/framework/resources/creating-resource-files-for-desktop-apps) içinde *.NET Framework Geliştirici Kılavuzu*.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca bkz.

[Bit Eşlemleri Araç Çubuklarına Dönüştürme](../windows/converting-bitmaps-to-toolbars.md)<br/>
[Yeni Araç Çubukları Oluşturma](../windows/creating-new-toolbars.md)<br/>
[Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)<br/>
[Görüntü menüsü](../windows/image-menu-image-editor-for-icons.md)<br/>
[Simgeler](/windows/desktop/menurc/icons)<br/>
[İmleçler](/windows/desktop/menurc/cursors)<br/>
[Hızlandırıcı Tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>