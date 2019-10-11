---
title: 'Nasıl yapılır: Bir simge veya başka görüntü oluşturma'
ms.date: 02/15/2019
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
ms.openlocfilehash: 2605644533d55527a07904ac89fa937db1b2eec5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513755"
---
# <a name="how-to-create-an-icon-or-other-image"></a>Nasıl yapılır: Bir simge veya başka görüntü oluşturma

Yeni bir görüntü, bit eşlem, simge, imleç veya araç çubuğu oluşturabilir ve sonra görünümünü özelleştirmek için **görüntü düzenleyicisini** kullanabilirsiniz. Ayrıca, bir [kaynak şablonundan](../windows/how-to-use-resource-templates.md)sonra desenli yeni bir bit eşlem de oluşturabilirsiniz.

## <a name="icons-and-cursors-image-resources-for-display-devices"></a>Simgeler ve Imleçler: Görüntü cihazları için görüntü kaynakları

Simgeler ve imleçler, farklı boyutlarda görüntü aygıtları için farklı boyutlarda ve renk şemalarında birden çok görüntü içerebilen grafik kaynaklarıdır. İmleç Ayrıca, Windows 'un konumunu izlemek için kullandığı konum üzerinde etkin bir nokta de vardır. Hem simgeler hem de imleçler, bit eşlemler ve diğer görüntüler gibi **Görüntü Düzenleyicisi**kullanılarak oluşturulur ve düzenlenir.

Yeni bir simge veya imleç oluşturduğunuzda, **Görüntü Düzenleyicisi** ilk olarak standart bir türün görüntüsünü oluşturur. Görüntü başlangıçta ekran (saydam) rengiyle doldurulur. Görüntü bir imlece ise, etkin nokta başlangıçta koordinatların `0,0`sol üst köşesinden belirlenir.

Varsayılan olarak, **Görüntü Düzenleyicisi** , aşağıdaki tabloda gösterilen cihazlar için ek görüntülerin oluşturulmasını destekler. **Özel görüntü** iletişim kutusuna genişlik, yükseklik ve renk sayısı parametrelerini yazarak diğer cihazlar için görüntü oluşturabilirsiniz.

|Renk|Genişlik (piksel)|Yükseklik (piksel)|
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

### <a name="create-a-device-image-icon-or-cursor"></a>Bir cihaz görüntüsü (simge veya imleç) oluşturma

Yeni bir simge veya imleç kaynağı oluşturduğunuzda, **Görüntü Düzenleyicisi** ilk olarak belirli bir stilde bir görüntü oluşturur (32 × 32, simgeler için 16 renk ve 32 × 32, Imleçler Için tek renkli). Daha sonra, farklı boyutlardaki ve stillerdeki görüntüleri ilk simgesine veya imlece ekleyebilir ve gerektiğinde farklı görüntü cihazlarına göre her ek görüntüyü düzenleyebilirsiniz. Ayrıca, var olan bir görüntü türünden veya bir grafik programında oluşturulan bir bit eşlemden kes ve yapıştır işlemi kullanarak bir görüntüyü düzenleyebilirsiniz.

[Görüntü düzenleyicisinde](../windows/image-editor-for-icons.md)simge veya imleç kaynağını açtığınızda, geçerli görüntü aygıtıyla en yakından eşleşen görüntü varsayılan olarak açılır.

> [!NOTE]
> Projeniz zaten bir. rc dosyası içermiyorsa, bkz. [Yeni kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

**Yeni&lt;cihaz&gt; görüntü türü** iletişim kutusu, belirtilen türde yeni bir cihaz görüntüsü oluşturmanızı sağlar.  >   **Yeni\<cihaz > görüntüsü** iletişim kutusunu açmak için menü görüntüsü**yeni görüntü türü**' ne gidin. Dahil edilen aşağıdaki özellikler **hedef görüntü türü** ve **özel**' tir.

**Hedef görüntü türü** özelliği, açmak istediğiniz görüntü türünü seçtiğiniz kullanılabilir görüntü türlerini listeler:

||||
|-|-|-|
|-16 x 16, 16 renk|-48 x 48, 16 renk|-96 x 96, 16 renk|
|-16 x 16, 256 renk|-48 x 48, 256 renkleri|-96 x 96, 256 renkleri|
|-16 x 16, tek renkli|-48 x 48, tek renkli|-96 x 96, tek renkli|
|-32 x 32, 16 renk|-64 x 64, 16 renk||
|-32 x 32, 256 renkleri|-64 x 64, 256 renkleri||
|-32 x 32, tek renkli|-64 x 64, tek renkli||

> [!NOTE]
> Var olan tüm görüntüler bu listede gösterilmez.

Özel özellik, özel **görüntü** iletişim kutusunu açar, burada özel bir boyut ve renk sayısı ile yeni bir görüntü oluşturabilirsiniz.

**Özel görüntü** iletişim kutusu, özel boyut ve renk sayısıyla yeni bir görüntü oluşturmanıza olanak sağlar. Dahil edilen aşağıdaki özellikler şunlardır:

|Özellik|Açıklama|
|---|---|
|**Genişlik**|Özel görüntünün genişliğini piksel cinsinden (1-512, 2048 limiti) girebileceğiniz bir alan sağlar.|
|**Yükseklik**|Özel görüntünün yüksekliğini piksel (1-512, 2048 limiti) olarak girmeniz için bir alan sağlar.|
|**Renkler**|Özel görüntü için renk sayısını seçmeniz için bir alan sağlar: 2, 16 veya 256.|

Projelerdeki cihaz görüntülerini açmak için  **&lt;&gt; cihaz görüntüsünü aç** iletişim kutusunu kullanın. C++ Geçerli kaynakta mevcut cihaz görüntülerini (geçerli kaynağın parçası olan görüntüler) listeler. Aşağıdaki özellik eklenmiştir:

|Özellik|Açıklama|
|---|---|
|**Geçerli görüntüler**|Kaynağa dahil edilen görüntüleri listeler. Açmak istediğiniz görüntü türünü seçin.|

#### <a name="to-create-a-new-icon-or-cursor"></a>Yeni bir simge veya imleç oluşturmak için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), *. RC* dosyanıza sağ tıklayıp **Kaynak Ekle**' yi seçin. *. RC* dosyanızda bir imleç gibi var olan bir görüntü kaynağınız zaten varsa, **imleç** klasörüne sağ tıklayıp **imleç Ekle**' yi seçebilirsiniz.

1. [Kaynak Ekle iletişim kutusunda](../windows/add-resource-dialog-box.md) **simge** veya **Imleç** ' i seçin ve **Yeni**' yi seçin. Bu eylem, simgeler için 32 × 32, 16 renkli simgeyle bir simge kaynağı oluşturur. İmleçler için 32 × 32, tek renkli (2 renkli) görüntü oluşturulur.

   **Kaynak Ekle** iletişim kutusunda görüntü **+** kaynak türünün yanında bir artı işareti () görünürse, araç çubuğu şablonlarının kullanılabildiği anlamına gelir. Şablon listesini genişletmek için artı işaretini seçin, bir şablon seçin ve **Yeni**' yi seçin.

### <a name="to-add-an-image-for-a-different-display-device"></a>Farklı bir görüntü cihazının görüntüsünü eklemek için

1. Menü **görüntüsü** > **yeni cihaz görüntüsü**' ne gidin veya **Görüntü Düzenleyicisi** bölmesine sağ tıklayıp **yeni cihaz görüntüsü**' nü seçin.

1. Eklemek istediğiniz görüntü türünü seçin. Ayrıca, varsayılan listede boyutu kullanılamayan bir simge oluşturmak için **özel** ' i de seçebilirsiniz.

### <a name="to-copy-a-device-image"></a>Bir cihaz görüntüsünü kopyalamak için

1. Menü **resmi** > **Açık cihaz görüntüsü** ' ne gidin ve geçerli görüntüler listesinden bir görüntü seçin. Örneğin, bir simgenin 32 × 32, 16 renkli sürümünü seçin.

1. Görüntülenmekte olan simge görüntüsünü (**CTRL**+**C**) kopyalayın.

1. Başka bir **resim düzenleyici** penceresinde simgenin farklı bir görüntüsünü açın. Örneğin, simgenin 16 × 16, 16 renkli sürümünü açın.

1. Simge görüntüsünü (**CTRL**+**V**) bir **Görüntü Düzenleyicisi** penceresinden diğerine yapıştırın. Daha büyük bir boyutu daha küçük bir boyuta yapıştırıyorsanız, görüntüyü yeniden boyutlandırmak için simge tutamaçlarını kullanabilirsiniz.

### <a name="to-delete-a-device-image"></a>Bir cihaz görüntüsünü silmek için

Simge görüntüsü **görüntü düzenleyicisinde**görüntülenirken menü **görüntüsü** > **cihaz görüntüsünü Sil**' e gidin. Kaynaktaki son simge görüntüsünü sildiğinizde, kaynak de silinir.

> [!NOTE]
> **Del** tuşuna bastığınızda, bir simge üzerinde çizdiğiniz görüntüler ve renkler silinir, ancak simge kalır ve artık yeniden tasarlayabilirsiniz. Yanlışlıkla **del** tuşuna basarsanız, eylemi geri almak için **CTRL**+**Z** tuşuna basın.

### <a name="to-create-transparent-or-inverse-regions-in-device-images"></a>Cihaz görüntülerinde saydam veya ters bölgeler oluşturmak için

[Görüntü düzenleyicisinde](../windows/image-editor-for-icons.md), başlangıç simgesinin veya imleç resminin saydam bir özniteliği vardır. Simgenin ve imleç görüntülerinin dikdörtgen olmasına rağmen, görüntünün parçaları saydam olduğu ve ekrandaki alttaki görüntüde simge veya imleç üzerinden gösterdiği için pek çok görünmüyor. Bir simgeyi sürüklediğinizde, görüntünün bir kısmı ters bir renkte görünebilir. [Renkler penceresinde](../windows/colors-window-image-editor-for-icons.md)ekran rengini ve ters rengi ayarlayarak bu etkiyi oluşturursunuz.

Simgeler ve imleçler için uyguladığınız ekran ve ters renkler, türetilmiş görüntünün şeklini ve rengini ya da ters bölge atamasını sağlar. Renkler, bu özniteliklere sahip olan görüntünün parçalarını gösterir. Düzenlemede ekran rengi ve ters renk özniteliklerini temsil eden renkleri değiştirebilirsiniz. Bu değişiklikler uygulamanızdaki simgenin veya imlecin görünüşünü etkilemez.

> [!NOTE]
> İletişim kutuları ve menü komutları gördüğünüz içinde açıklanana göre farklılık **yardımcı** bağlı olarak, etkin ayarlarınıza ve sürüm. Ayarlarınızı değiştirmek için menü **araçları** > **içeri ve dışarı aktarma ayarları**' na gidin. Daha fazla bilgi için bkz. [Visual STUDIO IDE 'Yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).

#### <a name="to-create-transparent-or-inverse-regions"></a>Saydam veya ters bölgeler oluşturmak için

1. **Renkler** penceresinde, seçici **ekran rengi** veya **ters renk**' i seçin.

1. Bir çizim aracı kullanarak ekran veya ters rengi yansımanıza uygulayın. Çizim araçları hakkında daha fazla bilgi için bkz. [bir çizim aracı kullanma](using-a-drawing-tool-image-editor-for-icons.md).

#### <a name="to-change-the-screen-or-inverse-color"></a>Ekranı veya ters rengi değiştirmek için

1. **Ekran rengi** seçicisini ya da **ters renk** seçiciyi seçin.

1. **Renkler** penceresindeki **renkler** paletinden bir renk seçin.

   Tamamlayıcı renk, diğer seçici için otomatik olarak atanır.

   > [!TIP]
   > **Ekran rengi** veya **ters renk** seçiciyi çift tıklarsanız, [Özel Renk Seçicisi iletişim kutusu](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md) görüntülenir.

### <a name="use-the-256-color-palette"></a>256 renkli paleti kullanma

**Görüntü düzenleyicisini**kullanarak, simgeler ve imleçler, aralarından seçim yapabileceğiniz bir 256-Color paleti ile büyük (64 × 64) boyutunda boyutlandırılabilir. Kaynağı oluşturduktan sonra bir cihaz görüntüsü stili seçilidir.

#### <a name="to-create-a-256-color-icon-or-cursor"></a>256 renkli bir simge veya imleç oluşturmak için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), *. RC* dosyanıza sağ tıklayıp **Kaynak Ekle**' yi seçin. *. RC* dosyanızda bir imleç gibi var olan bir görüntü kaynağınız zaten varsa, **imleç** klasörüne sağ tıklayıp **imleç Ekle**' yi seçebilirsiniz.

1. [Kaynak Ekle iletişim kutusunda](../windows/add-resource-dialog-box.md) **simge** veya **Imleç** ' i seçin ve **Yeni**' yi seçin.

1. Menü **görüntüsü** > **yeni cihaz görüntüsü** ' ne gidin ve istediğiniz 256 renkli görüntü stilini seçin.

#### <a name="to-choose-a-color-from-the-256-color-palette-for-large-icons"></a>Büyük simgeler için 256 renkli paletten bir renk seçmek için

256 renkli paletten seçim ile çizim yapmak için renkler [penceresindeki](../windows/colors-window-image-editor-for-icons.md)renkler paletinden renkler ' i seçmeniz gerekir.

1. Büyük simge veya imleci seçin ya da yeni bir büyük simge veya imleç oluşturun.

1. **Renkler** penceresindeki **renkler** paletinde bulunan 256 renkten bir renk seçin.

   Seçilen renk **renkler** penceresindeki **renkler** paletindeki geçerli renge dönüşecek.

   > [!NOTE]
   > 256 renkli görüntüler için kullanılan ilk palet, `CreateHalftonePalette` Windows API tarafından döndürülen paletle eşleşir. Windows kabuğu için tasarlanan tüm simgeler, palet gerçekleştirme sırasında titreşimi engellemek için bu paleti kullanmalıdır.

### <a name="to-set-a-cursors-hot-spot"></a>İmlecin Etkin noktasını ayarlamak için

İmlecin etkin noktası, Windows 'un imlecin konumunu izlemede başvurduğu noktasıdır. Varsayılan olarak, etkin nokta, imlecin koordinatlarıyla `0,0`sol üst köşesine ayarlanır. Özellikler penceresi **Hotspot** özelliği, etkin [](/visualstudio/ide/reference/properties-window) nokta koordinatlarını gösterir.

1. [Görüntü Düzenleyicisi araç çubuğunda](../windows/toolbar-image-editor-for-icons.md), **etkin nokta ayarla** aracını seçin.

1. İmlecin etkin noktası olarak atamak istediğiniz pikseli seçin.

   **Özellikler** penceresindeki **etkin nokta** özelliği yeni koordinatları görüntüler.

### <a name="to-create-and-save-a-bitmap-as-a-gif-or-jpeg"></a>Bir bit eşlemi bir. gif veya. JPEG olarak oluşturmak ve kaydetmek için

Bir bit eşlem oluşturduğunuzda, görüntü bit eşlem biçiminde (. bmp) oluşturulur. Ancak, görüntüyü bir GIF veya JPEG ya da başka bir grafik biçiminde kaydedebilirsiniz.

> [!NOTE]
> Bu işlem simgeler ve imleçler için geçerlidir.

1. Menü **dosyası** > **Aç**' a gidin ve ardından **Dosya**' yı seçin.

1. **Yeni dosya iletişim kutusunda**  **C++ görsel** klasörünü seçin, ardından **Şablonlar** kutusunda **bit eşlem dosyası (. bmp)** öğesini seçin ve **Aç**' ı seçin.

   Bit eşlem **görüntü düzenleyicisinde**açılır.

1. Gerektiğinde yeni bit eşleminiz üzerinde değişiklik yapın.

1. Bit eşlem hala **görüntü düzenleyicisinde**açıkken, menü **dosyası** > **e gidin. *dosya adı*. bmp dosyasını olarak kaydet**'

1. **Dosyayı farklı kaydet** iletişim kutusunda, dosyaya vermek istediğiniz adı ve dosya **adı** kutusunda istediğiniz dosya biçimini belirten uzantıyı yazın. Örneğin, *Dosyam. gif*.

   > [!NOTE]
   > Başka bir dosya biçimi olarak kaydetmek için projenizin dışında bit eşlem oluşturmanız veya açmanız gerekir. Projeyi içinde oluşturur veya açarsanız, **farklı kaydet** komutu kullanılamaz olur. Daha fazla bilgi için bkz. bir [proje dışındaki kaynak betik dosyasındaki kaynakları görüntüleme (tek başına)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

1. **Kaydet**’i seçin.

### <a name="to-convert-an-image-from-one-format-to-another"></a>Bir görüntüyü bir biçimden diğerine dönüştürmek için

GIF veya JPEG görüntülerini **görüntü düzenleyicisinde** açabilir ve bunları bit eşlemler olarak kaydedebilirsiniz. Ayrıca, bir bit eşlem dosyası açıp GIF veya JPEG olarak kaydedebilirsiniz. İle çalıştığınız görüntülerin geliştirme ortamında düzenlenmek üzere bir projenin parçası olması gerekmez (bkz. [tek başına görüntü düzenlemesi](../windows/editing-an-image-outside-of-a-project-image-editor-for-icons.md)).

1. Görüntüyü **görüntü düzenleyicisinde**açın.

1. Menü **dosyası** > **dosya *adını* farklı kaydet**' e gidin.

1. **Dosyayı farklı kaydet** iletişim kutusunda, **dosya adı** kutusuna istediğiniz biçimi gösteren dosya adını ve uzantıyı yazın.

1. **Kaydet**’i seçin.

### <a name="to-add-a-new-image-resource-to-an-unmanaged-c-project"></a>Yönetilmeyen C++ bir projeye yeni bir görüntü kaynağı eklemek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), *. RC* dosyanıza sağ tıklayıp **Kaynak Ekle**' yi seçin. *. RC* dosyanızda imleç gibi bir görüntü kaynağınız zaten varsa, **imleç** klasörüne sağ tıklayıp **imleç Ekle**' yi seçmeniz yeterlidir.

1. [Kaynak Ekle iletişim kutusunda](../windows/add-resource-dialog-box.md), oluşturmak istediğiniz görüntü kaynağı türünü seçin (örneğin,**bit eşlem**) ve ardından **Yeni**' yi seçin.

   **Kaynak Ekle** iletişim kutusunda görüntü **+** kaynak türünün yanında bir artı işareti () görünürse, araç çubuğu şablonlarının kullanılabildiği anlamına gelir. Şablon listesini genişletmek için artı işaretini seçin, bir şablon seçin ve **Yeni**' yi seçin.

### <a name="to-add-a-new-image-resource-to-a-project-in-a-net-programming-language"></a>.NET programlama dilinde bir projeye yeni bir görüntü kaynağı eklemek için

1. **Çözüm Gezgini**, proje klasörüne sağ tıklayın (örneğin, *WindowsApplication1*).

1. Kısayol menüsünde **Ekle**' yi ve ardından **Yeni öğe Ekle**' yi seçin.

1. **Kategoriler** bölmesinde, **Yerel proje öğeleri** klasörünü genişletin ve **kaynaklar**' ı seçin.

1. **Şablonlar** bölmesinde, projenize eklemek istediğiniz kaynak türünü seçin.

   Kaynak, **Çözüm Gezgini** projenize eklenir ve kaynak [görüntü düzenleyicisinde](../windows/image-editor-for-icons.md)açılır. Artık görüntünüzü değiştirmek için **görüntü düzenleyicisinde** bulunan tüm araçları kullanabilirsiniz. Yönetilen bir projeye görüntü ekleme hakkında daha fazla bilgi için bkz. [tasarım zamanında resim yükleme](/dotnet/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca bkz.

[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)<br/>
[Nasıl yapılır: Görüntü Kopyalama](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[Nasıl yapılır: Çizim Aracı Kullanma](../windows/using-a-drawing-tool-image-editor-for-icons.md)<br/>
[Nasıl yapılır: Renklerle Çalışma](../windows/working-with-color-image-editor-for-icons.md)<br/>
[Hızlandırıcı Tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
<!--
[Converting Bitmaps to Toolbars](../windows/converting-bitmaps-to-toolbars.md)<br/>
[Creating New Toolbars](../windows/creating-new-toolbars.md)<br/>
[Icons](/windows/win32/menurc/icons)<br/>
[Cursors](/windows/win32/menurc/cursors)<br/>-->