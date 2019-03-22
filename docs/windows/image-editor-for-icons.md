---
title: Simgeler (C++) için görüntü Düzenleyicisi
ms.date: 02/15/2019
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
ms.openlocfilehash: 22fe458a72d970bb09687a53232f94b171e14a45
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328434"
---
# <a name="image-editor-for-icons-c"></a>Simgeler (C++) için görüntü Düzenleyicisi

İçinde bir görüntü dosyası (.ico, .bmp, .png) seçtiğinizde **Çözüm Gezgini**, görüntünün açılır **Resim Düzenleyicisi** kod dosyaları açmak aynı şekilde **Kod Düzenleyicisi** . Olduğunda bir **Resim Düzenleyicisi** sekmesi etkin olduğu, görüntü oluşturmaya ve düzenlemeye için birçok araç çubuklarıyla göreceksiniz. Bit eşlemler, simgeler ve imleçlerin yanı sıra komutlarını kullanarak GIF veya JPEG biçimindeki görüntüleri de düzenleyebilirsiniz **görüntü** menü ve araçları **Resim Düzenleyicisi** araç çubuğu.

Grafik kaynakları uygulamanız için tanımladığınız görüntüleridir. Freehand çizin veya şekilleri kullanarak çizin. Düzenleme, çevirme veya yeniden boyutlandırma için görüntünün parçalarını seçebilir veya seçili bir görüntü bölümünden özel bir fırça oluştur ve bu fırça ile çizin. Görüntü özelliklerini tanımlayın, görüntüleri farklı biçimlerde kaydetme ve görüntülerini bir biçimden diğerine dönüştürme.

> [!NOTE]
> Kullanarak **Resim Düzenleyicisi**, 32 bitlik resimleri görüntüleyebilirsiniz, ancak onları düzenleyemezsiniz.

Ayrıca **Resim Düzenleyicisi** ve [ikili düzenleyici](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

Yeni grafik kaynakları oluşturmaya ek olarak, şunları yapabilirsiniz [var olan görüntülerden alma](../windows/how-to-copy-resources.md#import-and-export-resources) düzenleme ve projenize ekleyin. Ayrıca açabilir ve düzenlemek için bir projenin parçası olmayan görüntüleri [tek başına resim düzenleme](../windows/editing-an-image-outside-of-a-project-image-editor-for-icons.md).

Hakkında bilgi için **görüntü Düzenleyicisi**, bkz. nasıl [bir simge veya diğer görüntü oluşturma](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md), [görüntü Düzenle](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md), [çizim aracı kullanma](../windows/using-a-drawing-tool-image-editor-for-icons.md), [Renklerle çalışma](../windows/working-with-color-image-editor-for-icons.md), ve [kısayol tuşları](../windows/accelerator-keys-image-editor-for-icons.md).

> [!NOTE]
> Ücretsiz olarak indirin **Visual Studio görüntü kitaplığı** birçok animasyon, bit eşlemler ve uygulamalarınızda kullanabileceğiniz simgeler içeriyor. Kitaplığı indirme hakkında daha fazla bilgi için bkz. [Visual Studio görüntü kitaplığı](/visualstudio/designers/the-visual-studio-image-library).

## <a name="image-menu"></a>Görüntü Menüsü

**Görüntü** yalnızca görüntülenen menü **görüntü Düzenleyicisi** etkin, görüntüleri düzenleme, renk paletlerini yönetmek ve ayarlamak için komutlarını **Resim Düzenleyicisi** penceresi Seçenekler. Ayrıca, simgeler ve İmleçler ile çalışırken komutları kullanarak cihaz görüntüleri için kullanılabilir.

|Komut|Açıklama|
|---|---|
|**Renkleri ters çevir**|Renkleri tersine çevirir.|
|**Yatay Çevir**|Görüntüyü ya da seçimi yatay çevirir.|
|**Dikey Çevir**|Görüntüyü ya da seçimi dikey çevirir.|
|**90 derece döndür**|Görüntüyü ya da seçimi 90 derece çevirir.|
|**Renkler penceresini göster**|Açılır **renkleri** görüntünüzü kullanmak için renkleri, seçebileceğiniz penceresinde.|
|**Seçimi fırça olarak kullanma**|Özel fırça görüntü bölümünden oluşturmanızı sağlar.<br/><br/>Seçimdeki renkleri arasında görüntüyü dağıtır özel bir fırça seçiminizi olur. Seçimin bir kopyasını sürükleyerek yol boyunca bırakılır. Daha yavaş sürükleyin, kopya yapılmaz.|
|**Kopyalama ve ana hat seçimi**|Geçerli seçimin bir kopyasını oluşturur ve bunu açıklar.<br/><br/>Arka plan rengi geçerli seçimse, içeriyorsa, saydam varsa hariç tutulacaktır seçili.
|**Renkleri Ayarla**|Açılır **özel renk seçici**, görüntünüzü kullanmak renkleri özelleştirme sağlar.|
|**Palet yükle**|Açılır **renk paletini yük** .pal dosyaya daha önce kaydettiğiniz palet renkleri yükle olanak tanıyan iletişim kutusu.|
|**Palet Kaydet**|Palet renkleri .pal dosyaya kaydeder.|
|**Donuk Çiz**|Bu onay kutusu seçildiğinde, geçerli seçimi opak yapar.<br/><br/>Bu onay kutusu temizlenirse, geçerli seçimi saydam hale getirir.|
|**Araç Çubuğu Düzenleyicisi**|Açılır [yeni araç çubuğu kaynağı iletişim kutusu](../windows/new-toolbar-resource-dialog-box.md).|
|**Kılavuz ayarları**|Açılır **Kılavuz ayarları** içinde belirtebilirsiniz Kılavuzlar görüntünüzü iletişim kutusu.|
|**Yeni görüntü tipi**|Açılır [yeni \<cihaz > görüntü türü iletişim kutusu](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md).<br/><br/>Tek bir simge kaynak birkaç görüntüyü farklı boyutlardaki içerebilir ve windows görüntülenecek nasıl kolaylaştıracağını bağlı olarak uygun bir simge boyutu kullanabilirsiniz. Yeni bir cihaz türü simge boyutunu değiştirmez, ancak bunun yerine simgesi içinde yeni bir görüntü oluşturur. Yalnızca, simgeler ve İmleçler için geçerlidir.|
|**Geçerli simge/imleç görüntü tipi**|İlk dokuz kullanılabilir işaretçi veya simge görüntülerini listeleyen bir alt menü açılır. Son komut, alt **daha fazla**, açılır [açık \<cihaz > Görüntü iletişim kutusu](../windows/open-device-image-dialog-box-image-editor-for-icons.md).|
|**Görüntü türünü Sil**|Seçili cihaz görüntüsünü siler.|
|**Araçlar**|Kullanılabilir olan tüm araçları içeren bir alt başlatır **Resim Düzenleyicisi** araç çubuğu.|

**Kılavuz ayarları** iletişim kutusunda, görüntünüzü için kılavuz ayarları belirtmenize olanak tanır ve düzenlenen görüntüsünden kılavuz çizgilerini görüntüler. Satırları düzenleme görüntüsü için yararlıdır, ancak görüntünün kendisi bir parçası olarak kaydedilmez.

|Özellik|Açıklama|
|---|---|
|**Piksel Kılavuzu**|Bu onay kutusu işaretlendiğinde, her pikselin etrafında bir kılavuz görüntüler **Resim Düzenleyicisi**.<br/><br/>Kılavuz, yalnızca 4 × ve daha yüksek çözünürlüklerde görünür.|
|**Döşeme**|Bu onay kutusu seçildiğinde, piksel cinsinden bloklarını etrafında bir kılavuz görüntüler **Resim Düzenleyicisi**, kılavuz aralık değerleri tarafından belirtilen.|
|**Genişlik**|Her kutucuk bloğunun genişliğini belirtir.<br/><br/>Bu özellik, düzenli aralıklarla düzenlenmiş birden fazla görüntü içeren bir bit eşlem yeniden çizilirken yararlıdır.|
|**Yükseklik**|Her kutucuk blok yüksekliğini belirtir.<br/><br/>Bu özellik, düzenli aralıklarla düzenlenmiş birden fazla görüntü içeren bir bit eşlem yeniden çizilirken yararlıdır.|

## <a name="toolbar"></a>Araç Çubuğu

**Resim Düzenleyicisi** araç çubuğu çizim, boyama, metin girme, silme ve görünüm işlemek için araçları içerir. Ayrıca, her aracını kullanma seçenekleri seçebilirsiniz bir seçenek belirleyici içerir. Örneğin, çeşitli fırça genişlikleri, büyütme faktörleri ve satır stilleri seçebilirsiniz.

Tüm araçlar kullanılabilir **Resim Düzenleyicisi** araç çubuğu menüsü'nden kullanılabilir ayrıca **görüntü** > **Araçları**. Kullanılacak **Resim Düzenleyicisi** araç ve **seçeneği** Seçici, Aracı'nı seçin veya istediğiniz seçeneği.

![Resim Düzenleyicisi araç çubuğu](../mfc/media/vcimageeditortoolbar.gif "vcImageEditorToolbar")<br/>
**Görüntü Düzenleyicisi** araç çubuğu

> [!TIP]
> İmlecinizi bir araç çubuğu düğmenin üzerine geldiğinizde araç ipuçlarında görünür. Bu ipuçları her düğmesinin işlevini belirlemenize yardımcı olabilir.

Çizim araçlarından birçoğunu kullanılabilir olduğundan [klavye](../windows/accelerator-keys-image-editor-for-icons.md), gizlemek bazen kullanışlıdır **Resim Düzenleyicisi** araç çubuğu.

- Göstermek veya gizlemek için **Resim Düzenleyicisi** araç menüsüne gidin **görünümü** > **araç çubukları** ve **Resim Düzenleyicisi**.

> [!NOTE]
> Bu araç çubuğu öğeleri görünür bir resim dosyası olduğunda kullanılamaz geçerli projeden veya çözüm değil Aç **Resim Düzenleyicisi**.

### <a name="option-selector"></a>Seçenek belirleyici

İle **seçeneği** Seçici genişliğini bir satır, bir fırça vuruşu ve daha fazlasını belirtebilirsiniz. Simgeye **seçeneği** seçtiğiniz bağlı olarak hangi aracın Seçici değişir.

![Çizim&#45;şekli Seçici görüntü düzenleyici araç çubuğunda](../mfc/media/vcimageeditortoolbaroptionselector.gif "vcImageEditorToolbarOptionSelector")<br/>
**Seçenek** seçicisinde **Resim Düzenleyicisi** araç çubuğu

### <a name="text-tool"></a>Metin aracı

Kullanım **metin aracı** imleç, bit eşlem ve simge kaynak metin eklemek için iletişim kutusu.

Bu iletişim kutusuna erişmek için açık **Resim Düzenleyicisi** ve menüsüne gidin **görüntü** > **Araçları**, ardından **metin aracı** komutu.

> [!TIP]
> Sağ tıklayabilirsiniz **metin aracı** standart Windows komutların bir listesini içeren bir varsayılan kısayol menüsüne erişmek için iletişim kutusu.

Açık **metin aracı yazı tipi** iletişim kutusu, yazı tipi, stil veya imleç yazı tipi boyutunu değiştirmek için. Değişiklikleri görüntülenen metni uygulanır **metin** alan.

Bu iletişim kutusuna erişmek için seçin **yazı tipi** düğmesine **metin aracı** iletişim kutusu. Kullanılabilir özellikler şunlardır:

|Özellik|Açıklama|
|---|---|
|**Yazı tipi**|Yazı tiplerini listeler.|
|**Yazı tipi stili**|Belirtilen yazı tipi için kullanılabilir stilleri listeler.|
|**Boyutu**|Belirtilen yazı tipi noktası kullanılabilir boyutları listeler.|
|**Örnek**|Metnin belirtilen yazı tipi ayarlarını ile nasıl görüneceğini gösterir.|
|**Komut Dosyası**|Belirtilen yazı tipi kullanılabilir dil kodları listeler.<br/><br/>Farklı dil komut dosyasını seçin, karakter için dil, çok dilli belgeleri oluşturmak için kullanılabilir duruma ayarlanır.|

#### <a name="to-change-the-font-of-text-on-an-image"></a>Görüntüdeki metnin yazı tipini değiştirmek için

Bir Windows uygulamasındaki bir simge metin ekleyin ve yazı tipi, metin işlemek nasıl bir örnek aşağıda verilmiştir.

1. Bir C++ Windows Forms uygulaması oluşturun. Ayrıntılar için bkz [nasıl yapılır: Windows Forms uygulamaları oluşturma](/previous-versions/visualstudio/visual-studio-2008/s69bf10x(v%3dvs.90)). Bir *n app.ico* dosya varsayılan olarak projenize eklenir.

1. İçinde **Çözüm Gezgini**, dosyayı çift *n app.ico*. **Resim Düzenleyicisi** açılır.

1. Menü Git **görüntü** > **Araçları** seçip **metin aracı**.

1. İçinde **metin aracı** iletişim kutusuna *C++* boş metin alanında. Bu metin kutusunda sol üst köşedeki bir yeniden boyutlandırılabilir görünür *n app.ico* içinde **Resim Düzenleyicisi**.

1. İçinde **Resim Düzenleyicisi**, yeniden boyutlandırılabilir kutusu ortasına sürükleyin *n app.ico* metnin okunabilirliğini geliştirmek için.

1. İçinde **metin aracı** iletişim kutusunda **yazı tipi** düğmesi.

1. İçinde **metin aracı yazı tipi** iletişim kutusunda:

   - Seçin **Times yeni Roman** listelenen tiplerinin listesinden **yazı tipi** liste kutusu.

   - Seçin **kalın** listelenen kullanılabilir yazı tipi stillerini listesinden **yazı tipi stili** liste kutusu.

   - Seçin **10** listesinden kullanılabilir boyutları listelenen noktası **boyutu** liste kutusu.

   - **Tamam**’ı seçin. **Metin aracı yazı tipi** iletişim kutusunu kapatmak ve yeni yazı tipi ayarlarını metninize uygulanır.

1. Seçin **Kapat** üzerinde **metin aracı** iletişim kutusu. Yeniden boyutlandırılabilir kutu çevresinde, metin alanından kaybolur **Resim Düzenleyicisi**.

Metin alanı kaynağının bir parçası olarak görünen metni görüntüler. Başlangıçta bu alan boştur.

> [!NOTE]
> Varsa **saydam arka plan** , yalnızca metin görüntüsüne yerleştirilir ayarlanmış. Varsa **donuk arka plan** , arka plan rengi ile doldurulmuş sınırlayıcı bir dikdörtgen metnin arkasına yerleştirilecek ayarlanmış.

## <a name="window-panes"></a>Pencere Bölmeleri

**Resim Düzenleyicisi** görüntünün iki bölme çubukla bölme ile iki Görünüm penceresi gösterir. Bölmelerin göreli boyutlarını değiştirmek için bölme çubuğunu yanlara doğru sürükleyebilirsiniz. Etkin bölmede bir seçim kenarlığı görüntülenir.

Gerçek boyut bir görünümüdür ve diğer 6 varsayılan büyütme faktörüyle genişletilir. Bu iki bölme görünümlerde otomatik olarak güncelleştirilir, bir bölmesinde yaptığınız tüm değişiklikler hemen diğer gösterilir. İki bölme içinde tek tek her piksel ayırmak ve kullanabilirsiniz, aynı zamanda, görüntünün boyutu gerçek görünümünü iş etkisi gözlemleyin görüntünüzü genişletilmiş bir görünüm üzerinde çalışmayı kolaylaştırır.

Sol bölmede gerektiği kadar bu alanı kullanır (en fazla yarısını **görüntü** pencere) görüntünüzün varsayılan 1:1 büyütme görüntülemek için. Sağ bölmede, varsayılan 6:1 büyütme yakınlaştırılmış görüntüsünü görüntüler. Her bölmesini kullanarak büyütme değiştirebilirsiniz **Magnıfy** aracındaki **Resim Düzenleyicisi** araç veya kısayol tuşları kullanarak.

Daha küçük bölmesinde genişletebilirsiniz **Resim Düzenleyicisi** penceresi ve büyük bir görüntü, farklı bölgelerde göstermek için iki bölme kullanın. Seçmek için içinde Bölmesi'ni seçin.

İşaretçinin bölünmüş çubuğunda konumlandırma ve bölme çubuğunu sağa veya sola taşıyarak bölmelerin göreli boyutlarını değiştirebilirsiniz. Yalnızca bir bölmesinde çalışmak istiyorsanız bölme çubuğunu taraflardan tüm taşıyabilirsiniz.

Varsa **Resim Düzenleyicisi** bölmesi faktörü olarak 4 ile genişletilmiş veya daha büyük, tek tek her piksel görüntüde sınırlandıran bir piksel kılavuzunu görüntüleyebilir.

### <a name="to-change-the-magnification-factor"></a>Büyütme katsayısını değiştirmek için

Varsayılan olarak, **Resim Düzenleyicisi** gerçek boyut ve sağ taraftaki bölmede 6 kez gerçek boyutta görünümü sol bölmesinde görünümünü görüntüler. Büyütme katsayısını (çalışma alanı altındaki durum çubuğunda görülen) resmi gerçek boyutuna ve görüntülenen boyut arasındaki oran ' dir. Varsayılan faktörü 6 ve aralık 1 ile 10.

1. Seçin **Resim Düzenleyicisi** Büyütme katsayısı değiştirmek istediğiniz bölmesi.

1. Üzerinde **görüntü Düzenleyicisi** araç sağındaki oku seçerek **Magnıfy** katsayısını menüden seçin ve aracı: **1 X**, **2 X**, **6 X**, veya **8 X**.

   > [!NOTE]
   > Katsayısını listelenenler dışında seçilecek **Magnıfy** aracı, kısayol tuşlarını kullanın.

### <a name="to-display-or-hide-the-pixel-grid"></a>Görüntülenecek veya piksel kılavuzunu Gizle

Tüm **Resim Düzenleyicisi** bölmeleri katsayısını 4 veya daha büyük ile tek tek her piksel görüntüde sınırlandıran bir kılavuz görüntüleyebilirsiniz.

1. Menü Git **görüntü** > **Kılavuz ayarları**.

1. Seçin **piksel kılavuzunu** onay kutusunu kılavuz görüntülemek veya ızgarasını için onay kutusunu temizleyin.

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>

<!--[Icons](https://msdn.microsoft.com/library/windows/desktop/ms646973.aspx)-->