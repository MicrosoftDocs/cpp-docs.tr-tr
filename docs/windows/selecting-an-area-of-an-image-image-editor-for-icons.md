---
title: 'Nasıl yapılır: görüntü düzenleme'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.image.editing
helpviewer_keywords:
- Image editor [C++], image selection
- Image editor [C++], selecting images
- images [C++], selecting
- cursors [C++], selecting areas of
- Image editor [C++], editing images
- Clipboard [C++], pasting
- images [C++], editing
- images [C++], deleting selected parts
- images [C++], copying selected parts
- images [C++], moving selected parts
- images [C++], dragging and replicating selected parts
- images [C++], pasting into
- graphics [C++], editing
- Image editor [C++], flipping and rotating images
- images [C++], flipping
- images [C++], rotating
- Image editor [C++], resizing images
- graphics [C++], resizing
- images [C++], resizing
- resizing images
- size [C++], images
- images [C++], cropping
- images [C++], extending
- Image editor [C++], cropping or extending images
- Image editor [C++], shrinking and stretching images
- images [C++], stretching
- images [C++], shrinking
- bitmaps [C++], shrinking
- bitmaps [C++], stretching
- Image editor [C++], editing images
- images [C++], editing
- images [C++], properties
- Image editor [C++], Properties window
- Properties window, image editor
ms.assetid: 8b6ce4ad-eba1-4ece-86ba-cea92c3edff2
ms.openlocfilehash: 9324e3dc5c6691a7b50f137da1fad446b416e968
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167855"
---
# <a name="how-to-edit-an-image"></a>Nasıl yapılır: görüntü düzenleme

Bir görüntünün kesmek, kopyalamak, temizlemek, yeniden boyutlandırmak, ters çevirmek veya taşımak istediğiniz bir alanını tanımlamak için seçim araçlarını kullanabilirsiniz. **Dikdörtgen seçim** aracı ile görüntünün dikdörtgen bir bölgesini tanımlayabilir ve seçebilirsiniz. **Düzensiz seçim** aracı ile kesme, kopyalama veya başka işlemler için seçmek istediğiniz alanın serbest bir anahattını çizebilirsiniz.

> [!NOTE]
> [Resim Düzenleyicisi araç çubuğunda](../windows/toolbar-image-editor-for-icons.md) **dikdörtgen seçimi** ve **düzensiz seçim** Araçları ' na bakın veya **Görüntü Düzenleyicisi** araç çubuğundaki her bir düğmeyle ilişkili araç ipuçlarını görüntüleyin.

Ayrıca, bir seçimden özel bir fırça da oluşturabilirsiniz. Daha fazla bilgi için bkz. [özel fırça oluşturma](../windows/creating-a-custom-brush-image-editor-for-icons.md).

## <a name="how-to"></a>Nasıl yapılır

Bir görüntüyü düzenlemek için bkz. nasıl yapılır:

### <a name="to-select-an-image"></a>Bir görüntü seçmek için

1. **Görüntü Düzenleyicisi** araç çubuğunu kullanın veya menü **görüntüsü** > **Araçlar** ' a gidin ve istediğiniz seçim aracını seçin.

1. Ekleme noktasını, seçmek istediğiniz görüntü alanının bir köşesine taşıyın. Ekleme noktası görüntünün üzerindeyken çapraz artı işareti görüntülenir.

1. Ekleme noktasını, seçmek istediğiniz alanın zıt köşesine sürükleyin. Bir dikdörtgen hangi piksellerin seçili olacağını gösterir. Dikdörtgenin içindeki tüm pikseller seçime dahil edilir.

1. Fare düğmesini bırakın. Seçim kenarlığı seçili alanı barındırır.

#### <a name="to-select-an-entire-image"></a>Görüntünün tamamını seçmek için

Geçerli seçimin dışında bir görüntü seçin. Seçim kenarlığı odağı değiştirir ve görüntünün tamamını bir kez daha kapsar.

### <a name="to-edit-parts-of-an-image"></a>Bir görüntünün parçalarını düzenlemek için

Seçimin tamamı görüntünün tamamının mı yoksa yalnızca bir parçası mi olduğunu seçerek, bir [seçimde](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)standart Düzenle işlemleri yapabilirsiniz — kesme, kopyalama, temizleme ve taşıma —. **Resim Düzenleyicisi** **Windows panosunu**kullandığından, **Görüntü Düzenleyicisi** ve Windows için diğer uygulamalar arasında görüntü aktarabilirsiniz.

Ayrıca, resmin tamamını veya yalnızca bir kısmını içerip içermediğini seçerek seçimi yeniden boyutlandırabilirsiniz.

#### <a name="to-cut-the-current-selection-and-move-it-to-the-clipboard"></a>Geçerli seçimi kesmek ve panoya taşımak için

Menü **düzenle** > **Kes**' e gidin.

#### <a name="to-copy-the-selection"></a>Seçimi kopyalamak için

1. İşaretçiyi seçim kenarlığının içine veya boyutlandırma tutamaçları dışında herhangi bir yere konumlandırın.

1. Seçimi yeni bir konuma sürüklerken **CTRL** tuşunu basılı tutun. Özgün seçimin alanı değiştirilmez.

1. Seçimi görüntüye geçerli konumunda kopyalamak için seçim imleci dışında ' yi seçin.

#### <a name="to-paste-the-clipboard-contents-into-an-image"></a>Pano içeriğini bir görüntüye yapıştırmak için

1. Menü **düzenle** > **Yapıştır**'a gidin.

   Seçim kenarlığı ile çevrelenen Pano içeriği bölmenin sol üst köşesinde görüntülenir.

1. İşaretçiyi seçim kenarlığı içinde konumlandırın ve görüntüyü görüntüde istenen konuma sürükleyin.

1. Görüntüyü yeni konumuna bağlamak için seçim kenarlığının dışını seçin.

#### <a name="to-delete-the-current-selection-without-moving-it-to-the-clipboard"></a>Geçerli seçimi panoya taşımadan silmek için

Menü **düzenle** > **Sil**' e gidin.

   Seçimin özgün alanı geçerli arka plan rengiyle doldurulmuştur.

> [!NOTE]
> **Kesme**, **kopyalama**, **Yapıştırma**ve **silme** komutlarına **kaynak görünümü** penceresine sağ tıklayarak erişebilirsiniz.

#### <a name="to-move-the-selection"></a>Seçimi taşımak için

1. İşaretçiyi seçim kenarlığının içine veya boyutlandırma tutamaçları dışında herhangi bir yere konumlandırın.

1. Seçimi yeni konumuna sürükleyin.

1. Görüntüde seçimi yeni konumunda bağlamak için seçim kenarlığının dışında ' yı seçin.

Seçim ile çizim hakkında daha fazla bilgi için bkz. [özel fırça oluşturma](../windows/creating-a-custom-brush-image-editor-for-icons.md).

### <a name="to-flip-an-image"></a>Bir görüntüyü çevirmek için

Özgün görüntünün ayna görüntüsünü oluşturmak için bir görüntüyü çevirebilir veya döndürebilirsiniz, görüntüyü ters döndürerek veya görüntüyü bir seferde doğru 90 derece döndürebilir.

- Görüntüyü yatayda (ayna görüntüsünü) çevirmek için menü **görüntüsü** > **Yatay Çevir**' e gidin.

- Görüntüyü dikey olarak çevirmek için (ters çevir ' i açın) menü **görüntüsü** ' ne gidin > **Dikey çevirin**.

- Görüntüyü 90 derece döndürmek için menü **görüntüsü** ' ne gidin > **90 derece döndürün**.

   > [!NOTE]
   > Bu komutlar için [Hızlandırıcı (kısayol) tuşlarını](../windows/accelerator-keys-image-editor-for-icons.md) da kullanabilir veya kısayol menüsünden komutlara erişebilirsiniz ( **görüntü Düzenleyicinizde**görüntü dışında seçim yapabilirsiniz).

### <a name="to-resize-an-image"></a>Bir görüntüyü yeniden boyutlandırmak için

Görüntüyü yeniden boyutlandırırken görüntü **düzenleyicisinin** davranışı görüntünün tamamını veya yalnızca bir kısmını [seçmiş](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) olmanıza bağlıdır.

Seçim yalnızca görüntünün bir kısmını içerdiğinde **Görüntü Düzenleyicisi** , satırları veya piksel sütunlarını silerek ve geçerli arka plan rengiyle aşağı alanları doldurarak seçimi küçültür. Ayrıca, satırları veya piksel sütunlarını çoğaltarak seçimi genişletebilirsiniz.

Seçim tüm görüntüyü içerdiğinde, görüntü **Düzenleyicisi** görüntüyü daraltır ve uzatır ya da kırpar ve genişletir.

Bir görüntüyü yeniden boyutlandırmak için iki mekanizma vardır: boyutlandırma tutamaçları ve [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Bir görüntünün tümünün veya bir kısmının boyutunu değiştirmek için boyutlandırma tutamaçlarını sürükleyin. Sürükleyebileceğiniz boyutlandırma tutamaçları Solid. Boş olan tutamaçları sürükleyemezsiniz. Seçilen bir parçayı değil, yalnızca görüntünün tamamını yeniden boyutlandırmak için **Özellikler** penceresini kullanın.

![Bit eşlemdeki boyutlandırma tutamaçları](../mfc/media/vcimageeditorsizinghandles.gif "Vcımageeditorsizinghandles")<br/>
Boyutlandırma tutamaçları

> [!NOTE]
> [Kılavuz ayarları iletişim kutusunda](../windows/grid-settings-dialog-box-image-editor-for-icons.md) **kutucuk Kılavuzu** seçeneğini belirlediyseniz yeniden boyutlandırma sonraki döşeme kılavuz çizgisi ile yaslanır. Yalnızca **piksel kılavuz** seçeneği işaretliyse (varsayılan ayar) yeniden boyutlandırma, bir sonraki kullanılabilir piksele yapışır.

#### <a name="to-resize-an-entire-image-using-the-properties-window"></a>Özellikler penceresini kullanarak görüntünün tamamını yeniden boyutlandırmak için

1. Özelliklerini değiştirmek istediğiniz görüntüyü açın.

1. [Özellikler penceresi](/visualstudio/ide/reference/properties-window) **Genişlik** ve **Yükseklik** kutularına istediğiniz boyutları yazın.

   Görüntünün boyutunu artırdıysanız, **Görüntü Düzenleyicisi** görüntüyü sağa, aşağı veya her ikisine genişletir ve yeni bölgeyi geçerli arka plan rengiyle doldurur. Görüntü uzatılmamıştır.

   Görüntünün boyutunu kısaltıp, görüntü **Düzenleyicisi** görüntüyü sağ veya alt kenarda veya her ikisinde de kırpar.

   > [!NOTE]
   > Kısmi bir seçimi yeniden boyutlandırmak için değil, yalnızca görüntünün tamamını yeniden boyutlandırmak için **Genişlik** ve **Yükseklik** özelliklerini kullanabilirsiniz.

#### <a name="to-crop-or-extend-an-entire-image"></a>Görüntünün tamamını kırpmak veya genişletmek için

1. Tüm görüntüyü seçin.

   Görüntünün bir kısmı seçili ise ve görüntünün tamamını seçmek istiyorsanız geçerli seçim kenarlığının dışında görüntüde herhangi bir yeri seçin.

1. Resim doğru boyuta gelinceye kadar bir boyutlandırma tutamacı sürükleyin.

Normal olarak, **Görüntü Düzenleyicisi** bir boyutlandırma tutamacını taşıyarak yeniden boyutlandırdığınızda bir görüntüyü kırpar veya büyütür. Boyutlandırma tutamacını taşırken **SHIFT** tuşunu basılı tutarsanız, **Görüntü Düzenleyicisi** görüntüyü küçültür veya uzatır.

#### <a name="to-shrink-or-stretch-an-entire-image"></a>Görüntünün tamamını küçültmek veya uzatmak için

1. Tüm görüntüyü seçin.

   Görüntünün bir kısmı seçili ise ve görüntünün tamamını seçmek istiyorsanız, geçerli seçim kenarlığının dışında görüntüde herhangi bir yeri seçin.

1. **Shift** tuşunu basılı tutarak görüntü doğru boyuta gelene kadar bir boyutlandırma tutamacı sürükleyin.

#### <a name="to-shrink-or-stretch-part-of-an-image"></a>Bir görüntünün bir bölümünü küçültmek veya uzatmak için

1. Görüntünün yeniden boyutlandırmak istediğiniz bölümünü seçin. Daha fazla bilgi için bkz. [görüntünün bir alanını seçme](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md).

1. Seçim doğru boyuta gelinceye kadar boyutlandırma tutamaçlarından birini sürükleyin.

### <a name="to-edit-an-image-outside-of-a-project"></a>Projenin dışında bir görüntüyü düzenlemek için

Geliştirme ortamındaki görüntüleri, tıpkı herhangi bir grafik uygulamasında yaptığınız gibi açabilir ve düzenleyebilirsiniz; Örneğin, tek başına düzenleme için bir bit eşlem açma. Birlikte çalıştığınız görüntülerin bir Visual Studio projesinin parçası olması gerekmez.

1. Menü **dosyası** > **Aç**' a gidin.

1. **Dosya türü** kutusunda, **tüm dosyalar**' ı seçin.

1. Düzenlemek istediğiniz görüntüyü bulun ve açın.

### <a name="to-change-image-properties"></a>Görüntü özelliklerini değiştirmek için

[Özellikler penceresi](/visualstudio/ide/reference/properties-window)kullanarak bir görüntünün özelliklerini ayarlayabilir veya değiştirebilirsiniz.

1. Görüntüyü **görüntü düzenleyicisinde**açın.

1. **Özellikler** penceresinde, resminizin tüm özelliklerini veya tüm özelliklerini değiştirin.

   |Özellik|Açıklama|
   |--------------|-----------------|
   |**Renkler**|Görüntünün renk düzenini belirtir. **Tek renkli**, **16**veya **256**veya **gerçek renk**' i seçin.<br/><br/>Görüntüyü 16 renkli bir paletle zaten çizdiyseniz, **tek renkli** seçildiğinde görüntüdeki renkler için siyah ve beyaz değişimler de vardır. Karşıtlık her zaman korunmaz: Örneğin, kırmızı ve yeşil bitişik alanların her ikisi de siyaha dönüştürülür.|
   |**Kısaltın**|Görüntü dosyasının adını belirtir.<br/><br/>Varsayılan olarak, Visual Studio varsayılan kaynak tanımlayıcısından (IDB_BITMAP1) ilk dört karakteri ("IDB_") kaldırarak ve uygun uzantıyı ekleyerek oluşturulan bir temel dosya adı atar. Bu örnekteki görüntünün dosya adı *BITMAP1. bmp*olacaktır. *MYBITMAP1. bmp*olarak yeniden adlandırabilirsiniz.|
   |**Yükseklik**|Resmin yüksekliğini (piksel cinsinden) ayarlar. Varsayılan değer 48 ' dir.<br/><br/>Görüntü kırpılmış veya var olan görüntünün altına boş bir boşluk eklenir.|
   |**ID**|Kaynağın tanımlayıcısını ayarlar.<br/><br/>Bir görüntü için, varsayılan olarak Microsoft Visual Studio bir serideki bir sonraki kullanılabilir tanımlayıcıyı atar: IDB_BITMAP1, IDB_BITMAP2, vb. Simgeler ve imleçler için benzer adlar kullanılır.|
   |**İnizdeki**|Renk özelliklerini değiştirir.<br/><br/>Bir renk seçmek ve [Özel Renk Seçici iletişim kutusunu](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)göstermek için çift tıklayın. Uygun metin kutularına RGB veya HSL değerlerini yazarak rengi tanımlayın.|
   |**SaveCompressed**|Resmin sıkıştırılmış bir biçimde olup olmadığını gösterir. Bu özellik salt okunur durumdadır.<br/><br/>Visual Studio, resimleri sıkıştırılmış bir biçimde kaydetmenize izin vermez. bu nedenle, Visual Studio 'da oluşturulan tüm görüntüler için bu özellik **false**olur. Visual Studio 'da sıkıştırılmış bir görüntü açarsanız (başka bir programda oluşturulan), bu özellik **true**olur. Visual Studio 'Yu kullanarak sıkıştırılmış bir görüntü kaydederseniz, sıkıştırması kaldırılır ve bu özellik **false**değerine geri döndürülür.|
   |**Genişlik**|Resmin genişliğini (piksel cinsinden) ayarlar. Bit eşlemler için varsayılan değer 48 ' dir.<br/><br/>Görüntü kırpılmış veya mevcut görüntünün sağına boş bir boşluk eklenir.|

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca bkz.

[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)<br/>
[Nasıl yapılır: simge veya başka görüntü oluşturma](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[Nasıl yapılır: çizim aracını kullanma](../windows/using-a-drawing-tool-image-editor-for-icons.md)<br/>
[Nasıl yapılır: renklerle çalışma](../windows/working-with-color-image-editor-for-icons.md)<br/>
[Hızlandırıcı Tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
