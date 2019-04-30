---
title: 'Nasıl yapılır: Görüntü Düzenle'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.image.editing
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
ms.openlocfilehash: 849da0d14987a057d39d5f9531e97545b3d4b8cf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387956"
---
# <a name="how-to-edit-an-image"></a>Nasıl yapılır: Görüntü Düzenle

Seçim araçları, kesme, kopyalama, Temizle, yeniden boyutlandırma, Ters Çevir veya taşımak istediğiniz görüntüyü bir alanı tanımlamak için kullanabilirsiniz. İle **dikdörtgen seçim** aracı tanımlayabilir ve görüntünün dikdörtgen bir bölge seçin. İle **düzensiz seçim** aracı seçmek için kesme, kopyalama veya başka bir işlem için istediğiniz alanı serbest bir özetini çizebilir.

> [!NOTE]
> Bkz: **dikdörtgen seçim** ve **düzensiz seçim** araçları Resimli olarak [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md) veya herdüğmeileilişkiliaraçipuçlarınıgörüntüleyin**Resim Düzenleyicisi** araç çubuğu.

Özel fırça seçimden de oluşturabilirsiniz. Daha fazla bilgi için [özel Fırça oluşturma](../windows/creating-a-custom-brush-image-editor-for-icons.md).

## <a name="how-to"></a>Nasıl Yapılır

Görüntü düzenlemek için bkz. nasıl:

### <a name="to-select-an-image"></a>Bir görüntü seçin

1. Kullanım **Resim Düzenleyicisi** araç ya da menü **görüntü** > **Araçları** ve istediğiniz seçim aracını seçin.

1. Ekleme noktasını seçmek istediğiniz görüntü alan bir köşesine taşıyın. Ekleme noktasını resminin üstündeyken işaretçileri görünür.

1. Ekleme noktasını seçmek istediğiniz alanın zıt köşe için sürükleyin. Hangi piksel seçili bir dikdörtgen gösterilir. Dikdörtgen altında dahil olmak üzere bu dikdörtgenin içindeki tüm piksel seçime dahil edilir.

1. Fare düğmesini bırakın. Seçili alanı seçim kenarlığı barındırır.

#### <a name="to-select-an-entire-image"></a>Görüntünün tümünü seçmek için

Geçerli seçimi dışında görüntüsünü seçin. Seçim kenarlığı odak değiştikçe ve görüntünün tamamını yeniden kapsar.

### <a name="to-edit-parts-of-an-image"></a>Görüntünün parçalarını düzenleme

Standart düzenleme işlemleri gerçekleştirebileceğiniz — kesme, kopyalama, silme ve taşıma — üzerinde bir [seçimi](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md), görüntünün tamamını veya yalnızca bir kısmını seçim olup olmadığını. Çünkü **Resim Düzenleyicisi** kullanır **Windows Pano**, görüntülerin arasında aktarabilirsiniz **Resim Düzenleyicisi** ve diğer uygulamalar için Windows.

Ayrıca, görüntünün tamamını veya bir bölümünü içerip içermediğini seçimi yeniden boyutlandırabilirsiniz.

#### <a name="to-cut-the-current-selection-and-move-it-to-the-clipboard"></a>Geçerli seçimi kesip panoya Taşı

Menü Git **Düzenle** > **Kes**.

#### <a name="to-copy-the-selection"></a>Seçimi kopyalamak için

1. Seçim kenarlığı içinde veya herhangi bir işaretçiyi üzerinde boyutlandırma dışında tutun.

1. Basılı **Ctrl** anahtar seçimi yeni bir konuma sürükleyin. Özgün seçim alanı değiştirilmez.

1. Kendi geçerli konumunda görüntüye Seçimi kopyalamak için seçim imleci dışında'ı seçin.

#### <a name="to-paste-the-clipboard-contents-into-an-image"></a>Pano içeriğini bir görüntüye yapıştırmak için

1. Menü Git **Düzenle** > **Yapıştır**.

   Seçimi kenarlıkla Pano içeriğini bölmesinin sol üst köşesinde görünür.

1. Seçim kenarlığı içinde işaretçiyi ve görüntünün görüntü üzerinde istenen konuma sürükleyin.

1. Görüntünün yeni konumunda yer işareti için seçim kenarlığı dışında'ı seçin.

#### <a name="to-delete-the-current-selection-without-moving-it-to-the-clipboard"></a>Geçerli seçimi panoya taşımadan silmek için

Menü Git **Düzenle** > **Sil**.

   Özgün alan seçimin geçerli arka plan rengi ile doldurulur.

> [!NOTE]
> Erişebileceğiniz **Kes**, **kopyalama**, **Yapıştır**, ve **Sil** içinde sağ tıklanarak komutları **KaynakGörünümü** penceresi.

#### <a name="to-move-the-selection"></a>Seçimi taşımak için

1. Seçim kenarlığı içinde veya herhangi bir işaretçiyi üzerinde boyutlandırma dışında tutun.

1. Seçimi yeni konumuna sürükleyin.

1. Görüntüdeki yeni konumunda seçimi bağlantı için seçim kenarlığı dışında'ı seçin.

Çizim ile bir seçim hakkında daha fazla bilgi için bkz. [özel Fırça oluşturma](../windows/creating-a-custom-brush-image-editor-for-icons.md).

### <a name="to-flip-an-image"></a>Bir resmi döndürmek için

Özgün bir Ayna görüntüsünü oluşturun, görüntüyü baş aşağı döndürmek veya resmi sağa aynı anda 90 derece döndür görüntü döndürme ya da ters çevir.

- Görüntüyü yatay olarak çevrilip çevrilmediği (Ayna görüntüsünü) menüsüne gidin **görüntü** > **Yatay Çevir**.

- Görüntüyü dikey olarak çevrilip çevrilmediği (ters bırakma) menüsüne gidin **görüntü** > **Dikey Çevir**.

- Görüntü 90 derece döndürme için menüsüne gidin **görüntü** > **90 derece döndür**.

   > [!NOTE]
   > Ayrıca [(kısayol) Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md) bu komutların veya kısayol menüsünden komutlara erişmek (dışında görüntüyü seçin **görüntü Düzenleyicisi**).

### <a name="to-resize-an-image"></a>Bir görüntüyü yeniden boyutlandırmak için

Davranışını **Resim Düzenleyicisi** olup seçtiğiniz bağlıdır görüntüyü yeniden boyutlandırma sırasında [seçili](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) görüntünün tamamını veya yalnızca bir bölümü.

Seçimi görüntüsü yalnızca bir bölümünü içerdiğinde **Resim Düzenleyicisi** satırları veya sütunları piksel silme ve arka plan rengiyle boşaltılmış bölgeleri girerek seçim küçültür. Seçimi satır veya sütun piksel çoğaltarak ayrıca uzatabilirsiniz.

Seçimi görüntünün tamamını içerdiği durumlarda **Resim Düzenleyicisi** ya da daraltır ve resmi uzatır veya kırpar ve genişletir.

Görüntüyü yeniden boyutlandırma için iki mekanizma vardır: boyutlandırma ve [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Görüntünün bir parçasını ve tüm boyutunu değiştirmek için boyutlandırma sürükleyin. Sürükleyebilirsiniz boyutlandırma tutamaçlarını dolu. Boş tanıtıcıları sürükleyemezsiniz. Kullanım **özellikleri** tamamını yeniden boyutlandırmak için pencere görüntü yalnızca seçili bir parçası değil.

![Boyutlandırma tutamaçları üzerinde bir bit eşlem](../mfc/media/vcimageeditorsizinghandles.gif "vcImageEditorSizingHandles")<br/>
Boyutlandırma

> [!NOTE]
> Varsa **döşeme Kılavuzu** seçeneğe [kılavuz Ayarları iletişim kutusu](../windows/grid-settings-dialog-box-image-editor-for-icons.md), ardından sonraki kutucuğu kılavuz çizgisi yapışır yeniden boyutlandırma. Yalnızca **piksel kılavuzunu** seçeneği (varsayılan ayar) seçili, sonraki kullanılabilir piksel yapışır yeniden boyutlandırma.

#### <a name="to-resize-an-entire-image-using-the-properties-window"></a>Özellikler penceresini kullanarak görüntünün tümünü yeniden boyutlandırma

1. Özelliklerini değiştirmek istediğiniz görüntüyü açın.

1. İçinde **genişliği** ve **yükseklik** kutularındaki [Özellikler penceresi](/visualstudio/ide/reference/properties-window), istediğiniz boyutları yazın.

   Resmin boyutu genişletirseniz **Resim Düzenleyicisi** resmi sağa, aşağı, veya her ikisi de genişletir ve yeni bölge geçerli arka plan rengi ile doldurur. Görüntü uzatılabilir değil.

   Resmin boyutu kısaltırsanız **Resim Düzenleyicisi** sağ veya alt kenarı veya her ikisi de resmi kırpar.

   > [!NOTE]
   > Kullanabileceğiniz **genişliği** ve **yükseklik** kısmi bir seçim değil yeniden boyutlandırmak için tüm görüntü yalnızca yeniden boyutlandırmak için özellikleri.

#### <a name="to-crop-or-extend-an-entire-image"></a>Görüntünün tümünü kırpma veya

1. Görüntünün tamamını seçin.

   Görüntünün seçili ve görüntünün tamamını seçmek istediğiniz herhangi bir geçerli seçim kenarlığı dış görüntü seçin.

1. Resim doğru boyutta olana kadar boyutlandırma tutamacı sürükleyin.

Normalde, **Resim Düzenleyicisi** kırpar veya yeniden boyutlandırma tutamacı hareket ettirerek boyutlandırma sırasında bir görüntü büyütür. Basılı tutun, **Shift** anahtar bir boyutlandırma tutamacı hareket ettikçe **Resim Düzenleyicisi** daraltır ya da resmi uzatır.

#### <a name="to-shrink-or-stretch-an-entire-image"></a>Görüntünün Tümünü Genişlet veya Daralt

1. Görüntünün tamamını seçin.

   Görüntünün bir parçasını seçili ve görüntünün tamamını seçmek istediğiniz herhangi bir geçerli seçim kenarlığı dışındaki görüntüyü seçin.

1. Basılı **Shift** anahtar ve resim doğru boyutta olana kadar boyutlandırma tutamacı sürükleyin.

#### <a name="to-shrink-or-stretch-part-of-an-image"></a>Küçültme veya uzatma bir görüntünün parçası

1. Görüntüyü yeniden boyutlandırmak istediğiniz bölümü seçin. Daha fazla bilgi için [görüntü alanını seçme](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md).

1. Boyutlandırma tutamaçlarından birinin doğru boyut seçimi olana kadar sürükleyin.

### <a name="to-edit-an-image-outside-of-a-project"></a>Proje dışındaki görüntüyü düzenleme

Açın ve örneğin bir bit eşlem bağımsız düzenleme için açma herhangi bir grafik uygulamada olduğu gibi geliştirme ortamında görüntülerini düzenleyin. Birlikte çalıştığınız görüntüleri, Visual Studio projesinin bir parçası olması gerekmez.

1. Menü Git **dosya** > **açık**.

1. İçinde **dosya türü** kutusunda **tüm dosyaları**.

1. Bulun ve düzenlemek istediğiniz görüntüyü açın.

### <a name="to-change-image-properties"></a>Görüntü özelliklerini değiştirmek için

Ayarlayabilir veya kullanmanın bir görüntü özelliklerini değiştirme [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

1. Görüntüde açın **Resim Düzenleyicisi**.

1. İçinde **özellikleri** penceresinde görüntünüzü tüm özelliklerini değiştirin.

   |Özellik|Açıklama|
   |--------------|-----------------|
   |**Renkler**|Görüntü için renk düzenini belirtir. Seçin **tek renkli**, **16**, veya **256**, veya **gerçek renk**.<br/><br/>Zaten bir 16-renk paletini görüntüsüyle kazandık, seçerek **tek renkli** değişimler siyah beyaz renkler için görüntüyü neden olur. Karşıtlık her zaman tutulmaz: Örneğin, kırmızı ve yeşil bitişik alanlarının her ikisini de siyah olarak dönüştürülür.|
   |**Dosya adı**|Görüntü dosyasının adını belirtir.<br/><br/>Varsayılan olarak, Visual Studio varsayılan kaynak tanımlayıcısı (IDB_BITMAP1) ve uygun uzantısı ekleme ("IDB_") ilk dört karakterleri kaldırarak oluşturulan temel bir dosya adı atar. Bu örnekte bir görüntü için dosya adı *BITMAP1.bmp*. Bunu adlandırabilirsiniz *MYBITMAP1.bmp*.|
   |**Yükseklik**|Resmin yüksekliğini (piksel cinsinden) ayarlar. Varsayılan değer 48'dir.<br/><br/>Resim kırpılmış veya mevcut görüntü altında boş bir boşluk eklenir.|
   |**ID**|Kaynağın tanımlayıcısını ayarlar.<br/><br/>Bir görüntü için Microsoft Visual Studio, varsayılan olarak, serideki sonraki kullanılabilir tanımlayıcı atar: IDB_BITMAP1 IDB_BITMAP2 ve benzeri. Benzer adlar, simgeler ve İmleçler için kullanılır.|
   |**Palet**|Özellikleri rengi değiştirir.<br/><br/>Bir renk seçin ve görüntülemek için çift [Özel Renk Seçici iletişim kutusu](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md). Renk RGB veya HSL değerleri ilgili metin kutularına yazarak tanımlayın.|
   |**SaveCompressed**|Görüntü sıkıştırılmış bir biçimde olup olmadığını belirtir. Bu özellik salt okunurdur.<br/><br/>Visual Studio, görüntüleri sıkıştırılmış bir biçimde kaydetmek izin vermez böylece Visual Studio'da oluşturulan herhangi bir görüntü için bu özellik **False**. (Başka bir programda oluşturan) bir sıkıştırılmış görüntüyü Visual Studio'da açarsanız, bu özellik olacak **True**. Visual Studio kullanarak bir sıkıştırılmış görüntüyü kaydederseniz, sıkıştırılmamış ve bu özellik, geri dönecek **False**.|
   |**Genişlik**|Resmin genişliğini (piksel cinsinden) ayarlar. 48 bit eşlemler için varsayılan değerdir.<br/><br/>Resim kırpılmış veya boş alan var olan görüntünün sağına eklenir.|

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca bkz.

[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)<br/>
[Nasıl yapılır: Simge veya Başka Görüntü Oluşturma](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[Nasıl yapılır: Çizim Aracı Kullanma](../windows/using-a-drawing-tool-image-editor-for-icons.md)<br/>
[Nasıl yapılır: Renklerle Çalışma](../windows/working-with-color-image-editor-for-icons.md)<br/>
[Hızlandırıcı Tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>