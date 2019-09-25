---
title: Simgeler (C++) Için görüntü Düzenleyicisi
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
ms.openlocfilehash: 0f8fe228b804538b6a0d0377f05d79c34e787587
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "69514224"
---
# <a name="image-editor-for-icons-c"></a>Simgeler (C++) Için görüntü Düzenleyicisi

**Çözüm Gezgini**' de bir görüntü dosyası (. ico,. bmp,. png gibi) seçtiğinizde, görüntü, kod **Düzenleyicisi**'nde kod dosyalarının açtığı şekilde **görüntü düzenleyicisinde** açılır. Bir **Görüntü Düzenleyicisi** sekmesi etkin olduğunda, görüntü oluşturma ve düzenleme için birçok araç içeren araç çubuklarını görürsünüz. Bit eşlemler, simgeler ve imleçlerle birlikte, resim **Düzenleyicisi** araç çubuğundaki **görüntü** menüsü ve araçlar 'daki komutları kullanarak GIF veya JPEG biçimindeki görüntüleri düzenleyebilirsiniz.

Grafik kaynakları, uygulamanız için tanımladığınız görüntülerdir. Şekilleri kullanarak serbest çizim veya çizim yapabilirsiniz. Bir görüntünün parçalarını düzenleyebilir, açabilir veya yeniden boyutlandırabilir veya bir görüntünün seçili bir bölümünden özel bir fırça oluşturabilir ve bu fırçayla çizim yapabilirsiniz. Görüntü özelliklerini tanımlayabilir, görüntüleri farklı biçimlerde kaydedebilir ve görüntüleri bir biçimden diğerine dönüştürebilirsiniz.

> [!NOTE]
> **Görüntü düzenleyicisini**kullanarak, 32 bitlik görüntüleri görüntüleyebilirsiniz, ancak düzenleyemezsiniz.

Yönetilen projelerde kaynak dosyalarıyla çalışmak için **resim düzenleyicisini** ve [ikili düzenleyiciyi](binary-editor.md) de kullanabilirsiniz. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri gömülü kaynakları düzenlemenizi desteklemez.

Yeni grafik kaynakları oluşturmaya ek olarak, [var olan görüntüleri](../windows/how-to-copy-resources.md#import-and-export-resources) düzenleyebilir ve ardından projenize ekleyebilirsiniz. Ayrıca, [tek başına görüntü düzenleme](../windows/editing-an-image-outside-of-a-project-image-editor-for-icons.md)için bir projenin parçası olmayan görüntüleri açabilir ve düzenleyebilirsiniz.

**Görüntü Düzenleyicisi**hakkında daha fazla bilgi için bkz. [bir simge veya başka görüntü oluşturma](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md), [görüntü düzenleme](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md), [Çizim Aracı kullanma](../windows/using-a-drawing-tool-image-editor-for-icons.md), [renk ile çalışma](../windows/working-with-color-image-editor-for-icons.md)ve [hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md).

> [!NOTE]
> Uygulamalarda kullanabileceğiniz birçok animasyon, bit eşlem ve simge içeren **Visual Studio Görüntü Kitaplığı** ' nı ücretsiz indirin. Kitaplığın nasıl indirileceği hakkında daha fazla bilgi için bkz. [Visual Studio resim kitaplığı](/visualstudio/designers/the-visual-studio-image-library).

## <a name="image-menu"></a>Görüntü Menüsü

Yalnızca **Görüntü Düzenleyicisi** etkinken görüntülenen **görüntü** menüsü, görüntüleri düzenleme, renk paletleri yönetme ve **Görüntü Düzenleyicisi** pencere seçeneklerini ayarlama komutlarına sahiptir. Ayrıca, simgeler ve imleçlerle çalışırken cihaz görüntülerini kullanmaya yönelik komutlar kullanılabilir.

|Komut|Açıklama|
|---|---|
|**Renkleri ters çevir**|Renklerinizi tersine çevirir.|
|**Yatay Çevir**|Görüntüyü veya seçimi yatay olarak çevirir.|
|**Dikey Çevir**|Görüntüyü veya seçimi dikey olarak çevirir.|
|**90 derece döndür**|Görüntüyü veya seçimi 90 derece döndürür.|
|**Renkler penceresini göster**|Görüntü için kullanılacak renkleri seçebileceğiniz **renkler** penceresini açar.|
|**Seçimi fırça olarak kullan**|Görüntünün bir kısmından özel bir fırça oluşturmanıza olanak sağlar.<br/><br/>Seçiminiz, seçimdeki renkleri görüntüde dağıtan özel bir fırça haline gelir. Seçimin kopyaları sürükleme yolu üzerinde bırakılır. Ne kadar yavaş sürüklediğiniz, daha fazla kopya yapılır.|
|**Seçimi Kopyala ve Seviyelendir**|Geçerli seçimin bir kopyasını oluşturur ve bu seçimi özetler.<br/><br/>Arka plan rengi geçerli seçimde yer alıyorsa, saydam seçiliyse, bu, dışarıda bırakılır.
|**Renkleri ayarla**|Resminizin sizin için kullandığınız renkleri özelleştirmenizi sağlayan **özel renk seçiciyi**açar.|
|**Palet Yükle**|Daha önce bir. pal dosyasına kaydedilen palet **renklerini yükleyebilirsiniz.**|
|**Paleti Kaydet**|Palet renklerini bir. pal dosyasına kaydeder.|
|**Donuk Çiz**|Seçildiğinde, geçerli seçimi donuk hale getirir.<br/><br/>Kaldırıldığında, geçerli seçimi saydam hale getirir.|
|**Araç Çubuğu Düzenleyicisi**|[Yeni araç çubuğu kaynağı iletişim kutusunu](../windows/new-toolbar-resource-dialog-box.md)açar.|
|**Kılavuz ayarları**|Görüntünüzün kılavuzlarını belirtebileceğiniz **Kılavuz ayarları** iletişim kutusunu açar.|
|**Yeni görüntü türü**|[ Yeni\<cihaz > görüntü türü iletişim kutusunu](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md)açar.<br/><br/>Tek bir simge kaynağı farklı boyutlarda birkaç görüntü içerebilir ve Windows, nasıl görüntüleneceklerinize bağlı olarak uygun simge boyutunu kullanabilir. Yeni bir cihaz türü simgenin boyutunu değiştirmez, bunun yerine simgenin içinde yeni bir görüntü oluşturur. Yalnızca simgeler ve imleçler için geçerlidir.|
|**Geçerli simge/Imleç resim türü**|Kullanılabilir ilk dokuz imleç veya simge görüntüsünü listeleyen bir alt menü açar. Alt menüdeki son komut, **daha fazla**, [Cihaz > görüntüsü aç \<iletişim kutusunu](../windows/open-device-image-dialog-box-image-editor-for-icons.md)açar.|
|**Görüntü türünü sil**|Seçili cihaz görüntüsünü siler.|
|**Araçlar**|**Görüntü Düzenleyicisi** araç çubuğundan kullanılabilen tüm araçları içeren bir alt menü başlatır.|

**Kılavuz ayarları** iletişim kutusu görüntünüzün kılavuz ayarlarını belirtmenize ve düzenlenmiş görüntü üzerinde kılavuz çizgileri görüntülemenize olanak sağlar. Satırlar görüntünün düzenlenmesinde faydalıdır, ancak görüntünün bir parçası olarak kaydedilmez.

|Özellik|Açıklama|
|---|---|
|**Piksel Kılavuzu**|İşaretlendiğinde, **görüntü düzenleyicisinde**her bir pikselin etrafında bir kılavuz görüntüler.<br/><br/>Kılavuz yalnızca 4 × ve daha yüksek çözünürlükte görünür.|
|**Kutucuk Kılavuzu**|Seçildiğinde, ızgara aralığı değerleriyle belirtilen **görüntü düzenleyicisinde**piksel blokları etrafında bir kılavuz görüntüler.|
|**Genişlik**|Her döşeme bloğunun genişliğini belirtir.<br/><br/>Bu özellik, düzenli aralıklarla düzenlenmiş birden çok görüntü içeren bit eşlemler çizerken yararlıdır.|
|**Yükseklik**|Her döşeme bloğunun yüksekliğini belirtir.<br/><br/>Bu özellik, düzenli aralıklarla düzenlenmiş birden çok görüntü içeren bit eşlemler çizerken yararlıdır.|

## <a name="toolbar"></a>Araç Çubuğu

**Resim Düzenleyicisi** araç çubuğu çizim, boyama, metin girme, silme ve görünümleri düzenleme araçlarını içerir. Ayrıca, her bir aracı kullanma seçeneklerini seçebileceğiniz bir seçenek seçici de içerir. Örneğin, çeşitli fırça genişlikleri, büyütme faktörleri ve çizgi stilleri arasından seçim yapabilirsiniz.

**Görüntü Düzenleyicisi** araç çubuğundaki tüm araçlar, menü **görüntüsü** > **araçlarından**de kullanılabilir. **Görüntü Düzenleyicisi** araç çubuğunu ve **seçenek** seçiciyi kullanmak için istediğiniz aracı veya seçeneği seçin.

![Görüntü Düzenleyicisi araç çubuğu](../mfc/media/vcimageeditortoolbar.gif "Vcımageeditortoolbar")<br/>
**Görüntü Düzenleyicisi** araç çubuğu

> [!TIP]
> İmleci bir araç çubuğu düğmesinin üzerine getirdiğinizde araç ipuçları görüntülenir. Bu ipuçları, her düğmenin işlevini belirlemenize yardımcı olabilir.

[Klavyede](../windows/accelerator-keys-image-editor-for-icons.md)birçok çizim aracı kullanılabilir olduğundan, bazen **resim Düzenleyicisi** araç çubuğunu gizlemek yararlı olur.

- **Görüntü Düzenleyicisi** araç çubuğunu görüntülemek veya gizlemek için menü **Görünüm** > **araç çubukları** ' na gidin ve **Görüntü Düzenleyicisi**' ni seçin.

> [!NOTE]
> Geçerli projeden veya çözümden bir görüntü dosyası **görüntü düzenleyicisinde**açık olmadığında, bu araç çubuğundan öğeler kullanılamaz görünür.

### <a name="option-selector"></a>Seçenek belirleyici

**Seçenek** seçiciyle bir çizginin genişliğini, fırça darbesini ve daha fazlasını belirtebilirsiniz. **Seçenek** seçici düğmesindeki simge, seçtiğiniz araca bağlı olarak değişir.

![Resim&#45;Düzenleyicisi araç çubuğunda şekil Seçicisi çizme](../mfc/media/vcimageeditortoolbaroptionselector.gif "Vcımageeditortoolbaroptionselector")<br/>
**Görüntü Düzenleyicisi** araç çubuğundaki **seçenek** seçici

### <a name="text-tool"></a>Metin aracı

Bir imlece, bit eşlem ya da simge kaynağına metin eklemek için **metin aracı** iletişim kutusunu kullanın.

Bu iletişim kutusuna erişmek için, **görüntü düzenleyicisini** açın ve menü **görüntüsü** > **araçları**' na gidin ve **metin aracı** komutunu seçin.

> [!TIP]
> Standart Windows komutlarının bir listesini içeren bir varsayılan kısayol menüsüne erişmek için **metin aracı** iletişim kutusuna sağ tıklayabilirsiniz.

İmleç yazı tipinin yazı tipini, stilini veya boyutunu değiştirmek için **metin aracı yazı tipi** iletişim kutusunu açın. Değişiklikler **metin** alanında görüntülenen metne uygulanır.

Bu iletişim kutusuna erişmek için **metin aracı** Iletişim kutusunda **yazı tipi** düğmesini seçin. Kullanılabilen özellikler şunlardır:

|Özellik|Açıklama|
|---|---|
|**Yazı tipi**|Kullanılabilir yazı tiplerini listeler.|
|**Yazı tipi stili**|Belirtilen yazı tipi için kullanılabilir stilleri listeler.|
|**Boyutla**|Belirtilen yazı tipi için kullanılabilir nokta boyutlarını listeler.|
|**Örnekli**|Metnin, belirtilen yazı tipi ayarlarıyla nasıl görüneceğini gösteren bir örnek gösterir.|
|**Komut Dosyası**|Belirtilen yazı tipi için kullanılabilir dil betiklerini listeler.<br/><br/>Farklı bir dil betiği seçtiğinizde, bu dilin karakter kümesi çok dilli belgeler oluşturmak için kullanılabilir hale gelir.|

#### <a name="to-change-the-font-of-text-on-an-image"></a>Görüntüdeki metnin yazı tipini değiştirmek için

Aşağıda, bir Windows uygulamasındaki simgeye metin ekleme ve metninizin yazı tipini değiştirme örnekleri verilmiştir.

1. C++ Windows Forms uygulaması oluşturun. Ayrıntılar için bkz [. nasıl yapılır: Windows Forms uygulamalar](/previous-versions/visualstudio/visual-studio-2008/s69bf10x(v%3dvs.90))oluşturun. Varsayılan olarak projenize bir *app. ico* dosyası eklenir.

1. **Çözüm Gezgini**' de *app. ico*dosyasına çift tıklayın. **Görüntü Düzenleyicisi** açılır.

1. Menü **görüntü** > **araçları** ' na gidin ve **metin aracı**' nı seçin.

1. **Metin aracı** iletişim kutusunda boş metin alanına yazın *C++* . Bu metin, **görüntü düzenleyicisinde** *app. ico* öğesinin sol üst köşesinde bulunan yeniden boyutlandırılabilir bir kutu içinde görüntülenir.

1. **Görüntü düzenleyicisinde**, metninizin okunabilirliğini geliştirmek için yeniden boyutlandırılabilir kutusunu *app. ico* ' ın ortasına sürükleyin.

1. **Metin aracı** Iletişim kutusunda **yazı tipi** düğmesini seçin.

1. **Metin araç yazı tipi** iletişim kutusunda:

   - **Yazı tipi** liste kutusunda listelenen kullanılabilir Fontlar listesinden **Times New Roman** ' u seçin.

   - **Yazı tipi stili** liste kutusunda listelenen kullanılabilir yazı tipi stilleri listesinden **kalın** ' ı seçin.

   - **Boyut** liste kutusunda listelenen kullanılabilir nokta boyutları listesinden **10** ' u seçin.

   - **Tamam**’ı seçin. **Metin aracı yazı tipi** iletişim kutusu kapanır ve yeni yazı tipi ayarları metninizi uygular.

1. **Metin aracı** Iletişim kutusunda **Kapat** ' ı seçin. Metninizin çevresindeki yeniden boyutlandırılabilir kutu, **görüntü düzenleyicisinden**kaybolacaktır.

Metin alanı, kaynağın bir parçası olarak görüntülenen metni görüntüler. Başlangıçta bu alan boştur.

> [!NOTE]
> **Saydam arka plan** ayarlandıysa, yalnızca metin görüntüye yerleştirilir. **Donuk arka plan** ayarlandıysa, arka plan rengiyle doldurulan bir sınırlayıcı dikdörtgen metnin arkasına yerleştirilir.

## <a name="window-panes"></a>Pencere Bölmeleri

**Resim Düzenleyicisi** penceresi, iki bölmeyi ayıran bölünmüş bir çubukla bir görüntünün iki görünümünü gösterir. Bölmelerin göreli boyutlarını değiştirmek için bölme çubuğunu yanlara doğru sürükleyebilirsiniz. Etkin bölmede bir seçim kenarlığı görüntülenir.

Bir görünüm gerçek boyutudur ve diğeri ise 6 ' nın varsayılan büyütme faktörüyle genişletilir. Bu iki bölmedeki görünümler otomatik olarak güncelleştirilir, bir bölmeden yaptığınız tüm değişiklikler hemen diğer bir bölmede gösterilir. İki bölme görüntünüzün büyütülmüş bir görünümünde çalışmanızı kolaylaştırır. Bu, tek tek pikselleri ayırabilmeniz ve aynı anda, görüntünün gerçek boyutlu görünümünde çalışmalarınızın etkisini gözlemleyebilirsiniz.

Sol bölmede, resminizin varsayılan 1:1 büyütme görünümünü görüntülemek için gereken kadar çok alan ( **görüntü** penceresinin yarısına kadar) kullanılır. Sağ bölmede, yakınlaştırılan varsayılan 6:1 büyütme resmi görüntülenir. Her bölmedeki büyütmeyi, **Görüntü Düzenleyicisi** araç çubuğundaki **büyütme** aracını veya hızlandırıcı tuşlarını kullanarak değiştirebilirsiniz.

**Görüntü Düzenleyicisi** penceresinin daha küçük bölmesini genişletebilirsiniz ve büyük bir görüntünün farklı bölgelerini göstermek için iki bölmeyi kullanabilirsiniz. Seçmek için bölmenin içini seçin.

İşaretçiyi bölme çubuğu üzerinde konumlandırarak bölme çubuğunu sağa veya sola taşıyarak, bölmelerin göreli boyutlarını değiştirebilirsiniz. Yalnızca bir bölme üzerinde çalışmak istiyorsanız bölünmüş çubuk her iki tarafa da herhangi bir şekilde hareket edebilir.

**Resim Düzenleyicisi** bölmesi 4 veya daha büyük bir faktörle genişletilirse, görüntüdeki tek pikselleri sınırlandıran bir piksel Kılavuzu görüntüleyebilirsiniz.

### <a name="to-change-the-magnification-factor"></a>Büyütme faktörünü değiştirmek için

Varsayılan olarak, **Görüntü Düzenleyicisi** gerçek boyutun sol bölmesindeki görünümü ve sağ bölmedeki gerçek boyutta olan görünümü görüntüler. Büyütme faktörü (çalışma alanının alt kısmındaki durum çubuğunda görülen), görüntünün gerçek boyutu ile görüntülenmiş boyut arasındaki orandır. Varsayılan faktör 6 ' dır ve Aralık 1 ile 10 arasındadır.

1. Büyütme faktörünü değiştirmek istediğiniz **Görüntü Düzenleyicisi** bölmesini seçin.

1. **Görüntü Düzenleyicisi** araç çubuğunda, **Büyüt** aracının sağındaki oku seçin ve alt menüden büyütme faktörünü seçin: **1x**, **2x**, **6x**veya **8X**.

   > [!NOTE]
   > **Büyütme aracında listelenenler** dışında bir büyütme faktörü seçmek için Hızlandırıcı tuşlarını kullanın.

### <a name="to-display-or-hide-the-pixel-grid"></a>Piksel kılavuzunu göstermek veya gizlemek için

4 veya daha büyük bir büyütme faktörü içeren tüm **görüntü düzenleyici** bölmeleri için görüntüdeki tek pikselleri sınırlandıran bir kılavuz görüntüleyebilirsiniz.

1. Menü **resmi** > **Kılavuz ayarları**' na gidin.

1. Kılavuzu göstermek için **piksel Kılavuzu** onay kutusunu seçin veya kılavuzu gizlemek için kutuyu temizleyin.

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Simgeler](/windows/win32/menurc/icons)