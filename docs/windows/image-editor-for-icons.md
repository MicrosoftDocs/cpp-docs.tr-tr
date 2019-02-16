---
title: Simgeler İçin Görüntü Düzenleyicisi
ms.date: 10/17/2018
f1_keywords:
- vc.editors.cursor.F1
- vc.editors.icon.F1
- vc.editors.cursor
- vc.editors.bitmap.F1
- vc.editors.bitmap
- vc.editors.dialog.GridSettings
- vc.editors.gridsettings
- vc.editors.bitmap
- vc.editors.icon
- vc.editors.texttool
- vc.editors.bitmap
- vc.editors.icon
helpviewer_keywords:
- editors, images
- resource editors [C++], graphics
- Image editor [C++]
- resource editors [C++], Image editor
- Image menu
- Grid Settings dialog box [C++]
- Graphics toolbar
- Image editor [C++], toolbar
- Image editor [C++], Option selector
- Properties window
- Option selector, Image editor
- toolbars [C++], showing
- toolbars [C++], hiding
- text, adding to an image
- Text Tool dialog box [C++]
- Text Tool Font dialog box [C++]
- fonts, changing on an image
- text, on images
- graphics editor [C++]
- Image editor [C++], panes
- Image editor [C++], magnification
- grids, pixel
- pixel grid, Image editor
- Image editor [C++], pixel grid
- Image editor [C++], grid settings
- grid settings, Image editor
ms.assetid: 586d2b8b-0348-4883-a85d-1ff0ddbf14dd
ms.openlocfilehash: 48b363b7b9021042fe6242be70c74f0daeade0c2
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320711"
---
# <a name="image-editor-for-icons"></a>Simgeler İçin Görüntü Düzenleyicisi

Bir görüntü dosyası (.ico, .bmp, .png) Çözüm Gezgini'nde tıkladığınızda, görüntü Kod Düzenleyicisi'nde kod dosyaları açmak aynı şekilde Resim Düzenleyicisi'nde açılır. Bir Resim Düzenleyicisi sekmesi etkin olduğunda, görüntü oluşturmaya ve düzenlemeye için birçok araç çubuklarıyla bakın. Bit eşlemler, simgeler ve imleçlerin yanı sıra komutlarını kullanarak GIF veya JPEG biçimindeki görüntüleri de düzenleyebilirsiniz **görüntü** menü ve araçları **Resim Düzenleyicisi** araç çubuğu.

Grafik kaynakları uygulamanız için tanımladığınız görüntüleridir. Freehand çizin veya şekilleri kullanarak çizin. Düzenleme, çevirme veya yeniden boyutlandırma için görüntünün parçalarını seçebilir veya seçili bir görüntü bölümünden özel bir fırça oluştur ve bu fırça ile çizin. Görüntü özelliklerini tanımlayın, görüntüleri farklı biçimlerde kaydetme ve görüntülerini bir biçimden diğerine dönüştürme.

Yeni grafik kaynakları oluşturmaya ek olarak, şunları yapabilirsiniz [var olan görüntülerden alma](../windows/how-to-import-and-export-resources.md) düzenleme ve projenize ekleyin. Ayrıca açabilir ve düzenlemek için bir projenin parçası olmayan görüntüleri [tek başına resim düzenleme](../windows/editing-an-image-outside-of-a-project-image-editor-for-icons.md).

> [!NOTE]
> Kullanarak **Resim Düzenleyicisi**, 32 bitlik resimleri görüntüleyebilirsiniz, ancak onları düzenleyemezsiniz.

Resim düzenleyicisi ile yapabilecekleriniz:

- [Renklerle çalışma](../windows/working-with-color-image-editor-for-icons.md)

- [Simgeler ve İmleçler ile çalışma: Görüntüleme cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)

- [Resim Düzenleyicisi komutları için kısayol tuşlarını kullanın](../windows/accelerator-keys-image-editor-for-icons.md)

**Resim Düzenleyicisi** görüntünün iki bölme çubukla bölme ile iki Görünüm penceresi gösterir. Bölmelerin göreli boyutlarını değiştirmek için bölme çubuğunu yanlara doğru sürükleyebilirsiniz. Etkin bölmede bir seçim kenarlığı görüntülenir.

**Resim Düzenleyicisi** penceresi, gereksinimlerinize ve tercihlerinize uyacak şekilde ayarlanabilir. Yapabilecekleriniz [büyütme katsayısını değiştirme](../windows/changing-the-magnification-factor-image-editor-for-icons.md) ve [görüntülemek veya piksel ızgarasını](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md).

> [!NOTE]
> Kullanarak **Resim Düzenleyicisi**, 32 bitlik resimleri görüntüleyebilirsiniz, ancak onları düzenleyemezsiniz.

## <a name="image-menu"></a>Görüntü Menüsü

**Görüntü** yalnızca görüntülenen menü **görüntü** Düzenleyici etkin, görüntüleri düzenleme, renk paletlerini yönetmek ve ayarlamak için komutlarını **Resim Düzenleyicisi** penceresi Seçenekler. Ayrıca, simgeler ve İmleçler ile çalışırken komutları kullanarak cihaz görüntüleri için kullanılabilir.

|Komut|Açıklama|
|---|---|
|**Renkleri ters çevir**|Renkleri tersine çevirir. Daha fazla bilgi için [seçimdeki renkleri ters çevirme](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md).|
|**Yatay Çevir**|Görüntüyü ya da seçimi yatay çevirir. Daha fazla bilgi için [görüntüyü çevirme](../windows/flipping-an-image-image-editor-for-icons.md).|
|**Dikey Çevir**|Görüntüyü ya da seçimi dikey çevirir. Daha fazla bilgi için [görüntüyü çevirme](../windows/flipping-an-image-image-editor-for-icons.md).|
|**90 derece döndür**|Görüntüyü ya da seçimi 90 derece çevirir. Daha fazla bilgi için [görüntüyü çevirme](../windows/flipping-an-image-image-editor-for-icons.md).|
|**Renkler penceresini göster**|Açılır [renkler penceresini](../windows/colors-window-image-editor-for-icons.md), içinde görüntünüzü kullanmak için renkleri seçebilirsiniz. Daha fazla bilgi için [renklerle çalışma](../windows/working-with-color-image-editor-for-icons.md).|
|**Seçimi fırça olarak kullanma**|Özel fırça görüntü bölümünden oluşturmanızı sağlar. Seçimdeki renkleri arasında görüntüyü dağıtır özel bir fırça seçiminizi olur. Seçimin bir kopyasını sürükleyerek yol boyunca bırakılır. Daha yavaş sürükleyin, kopya yapılmaz. Daha fazla bilgi için [özel Fırça oluşturma](../windows/creating-a-custom-brush-image-editor-for-icons.md).|
|**Kopyalama ve ana hat seçimi**|Geçerli seçimin bir kopyasını oluşturur ve bunu açıklar. Arka plan rengi geçerli seçimse, içeriyorsa, belirttiyseniz hariç tutulacaktır [saydam](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) seçili.
|**Renkleri Ayarla**|Açılır [özel renk seçici](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md), görüntünüzü kullanmak renkleri özelleştirme sağlar. Daha fazla bilgi için [özelleştirme veya değiştirme renklerini](../windows/customizing-or-changing-colors-image-editor-for-icons.md).|
|**Palet yükle**|Açılır [renk paletini Yükle iletişim kutusu](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md), daha önce .pal dosyasına kaydedildi palet renkleri yükle sağlar.|
|**Palet Kaydet**|Palet renkleri .pal dosyaya kaydeder.|
|**Donuk Çiz**|Bu onay kutusu seçildiğinde, geçerli seçimi opak yapar. Bu onay kutusu temizlenirse, geçerli seçimi saydam hale getirir. Daha fazla bilgi için [opak ya da saydam arka plan seçme](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).|
|**Araç Çubuğu Düzenleyicisi**|Açılır [yeni araç çubuğu kaynağı iletişim kutusu](../windows/new-toolbar-resource-dialog-box.md).|
|**Kılavuz ayarları**|Açılır **Kılavuz ayarları** içinde belirtebilirsiniz Kılavuzlar görüntünüzü iletişim kutusu.|
|**Yeni görüntü tipi**|Açılır [yeni \<cihaz > görüntü türü iletişim kutusu](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md). Tek bir simge kaynak birkaç görüntüyü farklı boyutlardaki içerebilir ve windows görüntülenecek nasıl kolaylaştıracağını bağlı olarak uygun bir simge boyutu kullanabilirsiniz. Yeni bir cihaz türü simge boyutunu değiştirmez, ancak bunun yerine simgesi içinde yeni bir görüntü oluşturur. Yalnızca, simgeler ve İmleçler için geçerlidir.|
|**Geçerli simge/imleç görüntü tipi**|İlk kullanılabilir işaretçi veya simge görüntüleri (ilk dokuz) listeleyen bir alt menü açılır. Son komut, alt **daha...** , açılır [açık \<cihaz > Görüntü iletişim kutusu](../windows/open-device-image-dialog-box-image-editor-for-icons.md).|
|**Görüntü türünü Sil**|Seçili cihaz görüntüsünü siler.|
|**Araçlar**|Kullanılabilir olan tüm araçları içeren bir alt başlatır [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md).|

**Kılavuz ayarları** iletişim kutusunda, görüntünüzü için kılavuz ayarları belirtmenize olanak tanır ve düzenlenen görüntüsünden kılavuz çizgilerini görüntüler. Satırları düzenleme görüntüsü için yararlıdır, ancak görüntünün kendisi bir parçası olarak kaydedilmez.

|Özellik|Açıklama|
|---|---|
|**Piksel Kılavuzu**|Bu onay kutusu işaretlendiğinde, her pikselin çevresindeki bir kılavuz Resim Düzenleyicisi'nde görüntüler. Kılavuz, yalnızca 4 × ve daha yüksek çözünürlüklerde görünür.|
|**Döşeme**|Seçili olduğunda, görüntü düzenleyicisinde kılavuz aralık değerleri tarafından belirtilen blokları piksel etrafında bir kılavuz görüntüler.|
|**Genişlik**|Her kutucuk bloğunun genişliğini belirtir. Bu özellik, düzenli aralıklarla düzenlenmiş birden fazla görüntü içeren bir bit eşlem yeniden çizilirken yararlıdır.|
|**Yükseklik**|Her kutucuk blok yüksekliğini belirtir. Bu özellik, düzenli aralıklarla düzenlenmiş birden fazla görüntü içeren bir bit eşlem yeniden çizilirken yararlıdır.|

## <a name="toolbar"></a>Araç Çubuğu

**Resim Düzenleyicisi** araç çubuğu çizim, boyama, metin girme, silme ve görünüm işlemek için araçları içerir. Ayrıca, her aracını kullanma seçenekleri seçebilirsiniz bir seçenek belirleyici içerir. Örneğin, çeşitli fırça genişlikleri, büyütme faktörleri ve satır stilleri seçebilirsiniz.

> [!NOTE]
> Kullanılabilir olan tüm araçları **Resim Düzenleyicisi** araç web'da ayrıca **görüntü** menü (altında **Araçları** komutu).

![Resim Düzenleyicisi araç çubuğu](../mfc/media/vcimageeditortoolbar.gif "vcImageEditorToolbar") Resim Düzenleyicisi araç çubuğu

Kullanılacak **Resim Düzenleyicisi** araç ve **seçeneği** Seçici, Aracı'nı seçin veya istediğiniz seçeneği.

> [!TIP]
> İmlecinizi bir araç çubuğu düğmenin üzerine geldiğinizde araç ipuçlarında görünür. Bu ipuçları her düğmesinin işlevini belirlemenize yardımcı olabilir.

İle **seçeneği** Seçici genişliğini bir satır, bir fırça vuruşu ve daha fazlasını belirtebilirsiniz. Simgeye **seçeneği** seçtiğiniz bağlı olarak hangi aracın Seçici değişir.

![Çizim&#45;şekli Seçici görüntü düzenleyici araç çubuğunda](../mfc/media/vcimageeditortoolbaroptionselector.gif "vcImageEditorToolbarOptionSelector") görüntü düzenleyici araç çubuğunda seçenek belirleyici

### <a name="use-the-text-tool-dialog-box"></a>Metin aracı iletişim kutusunu kullanın

Kullanım **metin aracı** imleç, bit eşlem ve simge kaynak metin eklemek için iletişim kutusu.

Bu iletişim kutusuna erişmek için açık [Resim Düzenleyicisi](../windows/window-panes-image-editor-for-icons.md). Seçin **Araçları** gelen **görüntü** menüsüne ve ardından **metin aracı** komutu.

#### <a name="font-button"></a>Yazı tipi düğmesi

Açılır **metin aracı yazı tipi** iletişim kutusu, hangi değiştirebilirsiniz yazı tipini, stili veya imleç yazı tipi boyutu. Değişiklikleri görüntülenen metni uygulanır **metin** alan.

Bu iletişim kutusuna erişmek için seçin **yazı tipi** düğmesine **metin aracı** iletişim kutusu. Kullanılabilir özellikler şunlardır:

|Özellik|Açıklama|
|---|---|
|**Yazı tipi**|Yazı tiplerini listeler.|
|**Yazı tipi stili**|Belirtilen yazı tipi için kullanılabilir stilleri listeler.|
|**Boyutu**|Belirtilen yazı tipi noktası kullanılabilir boyutları listeler.|
|**Örnek**|Metnin belirtilen yazı tipi ayarlarını ile nasıl görüneceğini gösterir.|
|**Komut Dosyası**|Belirtilen yazı tipi kullanılabilir dil kodları listeler. Farklı dil komut dosyasını seçin, karakter için dil, çok dilli belgeleri oluşturmak için kullanılabilir duruma ayarlanır.|

Görüntüdeki metnin yazı tipini değiştirmek için:

Aşağıdaki yordamda, bir Windows uygulamasındaki bir simge metin ekleyin ve yazı tipi, metin işlemek nasıl örneğidir.

1. Bir C++ Windows Forms uygulaması oluşturun. Ayrıntılar için bkz [bir Windows uygulaması projesi oluşturma](/previous-versions/visualstudio/visual-studio-2010/42wc9kk5). Bir *n app.ico* dosya varsayılan olarak projenize eklenir.

1. İçinde **Çözüm Gezgini**, dosyayı çift *n app.ico*. [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) açılır.

1. Gelen **görüntü** menüsünde **Araçları** seçip **metin aracı**. **Metin aracı** iletişim kutusu görüntülenir.

1. İçinde **metin aracı** iletişim kutusuna *C++* boş metin alanında. Bu metin kutusunda sol üst köşedeki bir yeniden boyutlandırılabilir görünür *n app.ico*, **Resim Düzenleyicisi**.

1. İçinde **Resim Düzenleyicisi**, yeniden boyutlandırılabilir kutusunda metnin okunabilirliğini geliştirmek için n app.ico ortasına sürükleyin.

1. İçinde **metin aracı** iletişim kutusunda **yazı tipi** düğmesi. **Metin aracı yazı tipi** iletişim kutusu görüntülenir.

1. İçinde **metin aracı yazı tipi** iletişim kutusunda **Times yeni Roman** listelenen tiplerinin listesinden **yazı tipi** liste kutusu.

1. Seçin **kalın** listelenen kullanılabilir yazı tipi stillerini listesinden **yazı tipi stili** liste kutusu.

1. Seçin **10** listesinden kullanılabilir boyutları listelenen noktası **boyutu** liste kutusu.

1. **Tamam** düğmesini seçin. **Metin aracı yazı tipi** iletişim kutusunu kapatmak ve yeni yazı tipi ayarlarını metninize uygulanır.

1. Seçin **Kapat** düğmesini **metin aracı** iletişim kutusu. Yeniden boyutlandırılabilir kutu çevresinde, metin alanından kaybolur **Resim Düzenleyicisi**.

#### <a name="text-area"></a>Metin alanı

Kaynak bir parçası olarak görünen metni görüntüler. Başlangıçta bu alan boştur.

> [!NOTE]
> Varsa **saydam arka plan** , yalnızca metin görüntüsüne yerleştirilir ayarlanmış. Varsa **donuk arka plan** ayarlandığında, sınırlayıcı bir dikdörtgen ile doldurulan [arka plan rengi](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md), metnin arkasında yer alır. Daha fazla bilgi için [seçme opak ve saydam arka planlar](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

Sağ tıklayabilirsiniz **metin aracı** standart Windows komutların bir listesini içeren bir varsayılan kısayol menüsüne erişmek için iletişim kutusu.

### <a name="to-display-or-hide-the-image-editor-toolbar"></a>Görüntülenecek veya Resim Düzenleyicisi araç çubuğunu gizle

Çizim araçlarından birçoğunu kullanılabilir olduğundan [klavye](../windows/accelerator-keys-image-editor-for-icons.md), gizlemek bazen kullanışlıdır **Resim Düzenleyicisi** araç çubuğu.

Üzerinde **görünümü** menüsünde **araç çubukları** ardından **Resim Düzenleyicisi**.

   > [!NOTE]
   > Bu araç çubuğu öğeleri görünür bir resim dosyası olduğunda kullanılamaz geçerli projeden veya çözüm açık değil **Resim Düzenleyicisi**. Bkz: [bir simge veya diğer görüntü oluşturma](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md), projelerinize görüntü dosyaları ekleme hakkında bilgi için.

## <a name="window-panes"></a>Pencere Bölmeleri

**Resim Düzenleyicisi** penceresi genellikle görüntüler görüntüyü bir ayırıcı çubukla ayırarak iki bölme. Bir görünümdür gerçek boyut ve diğer genişletilir (varsayılan büyütme faktörü 6'dır). Bu iki bölme görünümlerde otomatik olarak güncelleştirilir: bir bölmesinde yaptığınız değişiklikler hemen gösterilen diğer. İki bölme içinde tek tek her piksel ayırmak ve kullanabilirsiniz, aynı zamanda, görüntünün boyutu gerçek görünümünü iş etkisi gözlemleyin görüntünüzü genişletilmiş bir görünüm üzerinde çalışmayı kolaylaştırır.

Sol bölmede gerektiği kadar bu alanı kullanır (en fazla yarısını **görüntü** pencere) görüntünüzü 1:1 büyütme görünümünü (varsayılan) görüntülemek için. Sağ bölmede, yakınlaştırılmış görüntü (varsayılan olarak 6:1 büyütme) görüntüler. Her bölmesini kullanarak büyütme değiştirebilirsiniz **Magnıfy** aracındaki [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md) veya kısayol tuşları kullanarak.

Daha küçük bölmesinde genişletebilirsiniz **Resim Düzenleyicisi** penceresi ve büyük bir görüntü, farklı bölgelerde göstermek için iki bölme kullanın. Seçmek için içinde Bölmesi'ni seçin.

İşaretçinin bölünmüş çubuğunda konumlandırma ve bölme çubuğunu sağa veya sola taşıyarak bölmelerin göreli boyutlarını değiştirebilirsiniz. Yalnızca bir bölmesinde çalışmak istiyorsanız bölme çubuğunu taraflardan tüm taşıyabilirsiniz.

Varsa **Resim Düzenleyicisi** bölmesi faktörü olarak 4 ile genişletilmiş veya daha büyük, tek tek her piksel görüntüde sınırlandıran bir piksel kılavuzunu görüntüleyebilir.

### <a name="to-change-the-magnification-factor"></a>Büyütme katsayısını değiştirmek için

Varsayılan olarak, **görüntü** Düzenleyicisi gerçek boyutta sol bölmede görünümü gösterilir ve görünüm 6 sağ bölmesinde zaman gerçek boyut. Büyütme katsayısını (çalışma alanı altındaki durum çubuğunda görülen) resmi gerçek boyutuna ve görüntülenen boyut arasındaki oran ' dir. Varsayılan faktörü 6 ve aralık 1 ile 10.

1. Seçin **Resim Düzenleyicisi** Büyütme katsayısı değiştirmek istediğiniz bölmesi.

1. Üzerinde [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md), sağındaki oku seçerek [Büyüteç aracına](../windows/toolbar-image-editor-for-icons.md) katsayısını menüden seçin: **1 X**, **2 X**, **6 X**, veya **8 X**.

   > [!NOTE]
   > Katsayısını listelenenler dışında seçilecek **Magnıfy** aracı, kısayol tuşlarını kullanın.

### <a name="to-display-or-hide-the-pixel-grid"></a>Görüntülenecek veya piksel kılavuzunu Gizle

Tüm **Resim Düzenleyicisi** bölmeleri katsayısını 4 veya daha büyük ile tek tek her piksel görüntüde sınırlandıran bir kılavuz görüntüleyebilirsiniz.

1. Üzerinde **görüntü** menüsünde **Kılavuz ayarları**.

1. Seçin **piksel kılavuzunu** onay kutusunu kılavuz görüntülemek veya ızgarasını için onay kutusunu temizleyin.

> [!TIP]
> İmlecinizi bir araç çubuğu düğmenin üzerine geldiğinizde araç ipuçlarında görünür. Bu ipuçları her düğmesinin işlevini belirlemenize yardımcı olabilir.

## <a name="visual-studio-image-library"></a>Visual Studio Görüntü Kitaplığı

Ücretsiz olarak indirebilirsiniz **Visual Studio görüntü kitaplığı** birçok animasyon, bit eşlemler ve uygulamalarınızda kullanabileceğiniz simgeler içeriyor. Kitaplığı indirme hakkında daha fazla bilgi için bkz. [Visual Studio Resim Kitaplığı](/visualstudio/designers/the-visual-studio-image-library).

## <a name="managed-resources"></a>Yönetilen Kaynaklar

Kullanabileceğiniz **görüntü** Düzenleyicisi ve [ikili düzenleyiciyi](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Simgeler](https://msdn.microsoft.com/library/windows/desktop/ms646973.aspx)