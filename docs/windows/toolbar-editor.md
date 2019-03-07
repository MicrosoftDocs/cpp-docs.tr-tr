---
title: Araç çubuğu Düzenleyicisi (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.toolbar.F1
- vc.editors.toolbar
- vc.editors.newtoolbarresource
helpviewer_keywords:
- resource editors [C++], Toolbar editor
- editors, toolbars
- toolbars [C++], editing
- Toolbar editor
- toolbars [C++], creating
- Toolbar editor [C++], creating new toolbars
- Insert Resource
- bitmaps [C++], converting to toolbars
- Toolbar editor [C++], converting bitmaps
- toolbars [C++], converting bitmaps
- New Toolbar Resource dialog box [C++]
- buttons [C++], custom toolbars
- toolbar buttons [C++], editing
- buttons
- toolbar buttons [C++], creating
- Toolbar editor [C++], creating buttons
- toolbar buttons [C++], button image
- toolbar buttons [C++], creating
- toolbar buttons (in Toolbar editor)
- toolbar buttons [C++], moving
- Toolbar editor [C++], moving buttons
- Toolbar editor [C++], copying buttons
- toolbars [C++], copying buttons
- toolbar buttons [C++], copying
- toolbar buttons [C++], deleting
- Toolbar editor [C++], deleting buttons
- Toolbar editor [C++], spacing toolbar buttons
- toolbar buttons [C++], space between buttons
- toolbar controls [MFC], command ID
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- command IDs, toolbar buttons
- size, toolbar buttons
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- status bars [C++], active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
- tool tips [C++], adding to toolbar buttons
- "\n in tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor [C++], creating tool tips
ms.assetid: aa9f0adf-60f6-4f79-ab05-bc330f15ec43
ms.openlocfilehash: a138eb5aa40429696ca2efa4a67e1a1c5490f4fa
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57563257"
---
# <a name="toolbar-editor-c"></a>Araç çubuğu Düzenleyicisi (C++)

**Araç çubuğu Düzenleyicisi** araç çubuğu kaynakları oluşturmak ve bit eşlemleri araç çubuğu kaynakları dönüştürme sağlar. **Araç çubuğu Düzenleyicisi** bir araç ve tamamlanmış bir uygulamada nasıl atacağız yakın benzer düğmeleri göstermek için bir grafik görüntüsünü kullanır.

**Araç çubuğu Düzenleyicisi** düğmesi görüntünün, aynı iki Görünüm penceresi gösterir **Resim Düzenleyicisi** penceresi. Bölünmüş çubuk iki bölmeyi ayırır ve taraftan tarafı bölmelerin göreli boyutlarını değiştirmek için bölme çubuğunu sürükleyebilirsiniz. Etkin bölmede bir seçim kenarlığı görüntülenir ve görüntünün iki görünüm konu araç çubuğudur.

![Araç çubuğu Düzenleyicisi](../mfc/media/vctoolbareditor.gif "vcToolbarEditor")<br/>
**Araç Çubuğu Düzenleyicisi**

**Araç çubuğu Düzenleyicisi** benzer **Resim Düzenleyicisi** işlevselliği ve menü öğeleri, grafik araçları ve ikisi arasındaki bit eşlem kılavuz aynıdır. Bir menü komutu yoktur **görüntü** arasında geçiş yapmak için menü **araç çubuğu Düzenleyicisi** ve **Resim Düzenleyicisi**. Kullanma hakkında daha fazla bilgi için **grafik** araç **renkleri** paleti veya **görüntü** menüsünde görmek [görüntü Düzenleyicisi](../windows/image-editor-for-icons.md).

Bir bit eşlem dönüştürerek bir C++ projesinde yeni bir araç çubuğu oluşturabilirsiniz. Bit eşlem Grafik araç çubuğu düğmesi görüntülerde dönüştürür. Genellikle her düğme için bir görüntü ile birkaç düğme resimlerini üzerinde tek bir bit eşlem bit eşlem içerir. Varsayılan olarak 16 piksel genişliğinde ve resmin yüksekliğini görüntüleri herhangi bir boyutta olabilir. Düğme görüntüleri boyutunu belirtebilirsiniz **yeni araç çubuğu kaynağı** seçtiğinizde iletişim kutusu **araç çubuğu Düzenleyicisi** gelen **görüntü** çalışırken menüde  **Görüntü Düzenleyicisi**.

**Yeni araç çubuğu kaynağı** iletişim kutusu, genişlik ve yükseklik bir C++ projesinde bir araç çubuğu kaynağı için eklediğiniz düğmelerinin belirtmenize olanak sağlar. Varsayılan değer 16 × 15 pikseldir.

Araç çubuğu oluşturmak için kullanılan bir bit eşlem 2048, maksimum genişliği sahip bunu ayarlarsanız **düğmesi genişliği** için *512*, yalnızca dört düğme olabilir. Genişliğini ayarlamanız *513*, yalnızca üç düğme olabilir.

**Yeni araç çubuğu kaynağı** iletişim kutusunda, aşağıdaki özelliklere sahiptir:

|Özellik|Açıklama|
|---|---------------|
|**Düğme genişliği**|Araç çubuğu kaynak bit eşlem kaynağı dönüştürüyoruz araç çubuğu düğmeleri genişliğini girmek bir alan sağlar.|
|**Düğme yüksekliği**|Araç çubuğu kaynak bit eşlem kaynağı dönüştürüyoruz araç çubuğu düğmeleri yüksekliği girmek bir alan sağlar.|

> [!NOTE]
> Resimleri belirtilen yükseklik ve genişlik kırpılmış ve renkleri (16 renk) standart araç çubuğu renklerini kullanmak için ayarlanır.

Varsayılan olarak, araç çubuğunun sağ ucuna yeni ya da boş bir düğme görüntülenir. Bu düğme düzenlemeden önce taşıyabilirsiniz. Yeni bir düğme oluşturduğunuzda, başka bir boş düğme düzenlenen düğmesinin sağında görüntülenir. Araç çubuğu kaydettiğinizde, boş düğme kaydedilmez.

Araç çubuğu düğmesi, aşağıdaki özelliklere sahiptir:

|Özellik|Açıklama|
|--------------|-----------------|
|**ID**|Düğme için kimliği tanımlar. Açılır listede ortak sağlar **kimliği** adları.|
|**Genişlik**|Düğmesinin genişliğini belirler. 16 piksel önerilir.|
|**Yükseklik**|Düğmenin yüksekliğini belirler. Bir düğme yüksekliğini, araç çubuğundaki tüm düğmeler yüksekliğini değiştirir. 15 piksel önerilir.|
|**Sor**|Durum çubuğunda görüntülenen ileti tanımlar. Ekleme *\n* ve bir ad ekler bir **araç ipucu** bu araç çubuğu düğmesi için. Daha fazla bilgi için [bir araç ipucu oluşturmanın](../windows/creating-a-tool-tip-for-a-toolbar-button.md).|

**Genişlik** ve **yükseklik** tüm düğmeler için geçerlidir. Araç çubuğu oluşturmak için kullanılan bir bit eşlem 2048, maksimum genişliği sahip bu nedenle düğme genişliğini ayarlamak *512*, dört düğme dbmigrationsconfiguration ve genişliğini ayarlayın, *513*, yalnızca üç düğme olabilir.

## <a name="how-to"></a>Nasıl Yapılır

**Araç çubuğu Düzenleyicisi** sağlar:

### <a name="to-create-new-toolbars"></a>Yeni araç çubukları oluşturma

1. İçinde **kaynak görünümü**, sağ tıklayın, *.rc* seçin ve dosya **kaynak Ekle**. Var olan bir araç çubuğu varsa, *.rc* dosyası, sağ **araç** klasörü ve select **araç çubuğu ekleme**.

1. İçinde **kaynak Ekle** iletişim kutusunda **araç** içinde **kaynak türü** listeleyin ve ardından **yeni**.

   Bir artı işareti (**+**) yanında görünen **araç** kaynak türü geldiğini araç şablonları kullanılabilir. Şablonlar listesinde genişletin, bir şablon seçin veya seçmek için artı işaretini seçin **yeni**.

### <a name="to-convert-bitmaps-to-toolbar-resources"></a>Bit eşlemleri araç çubuğu kaynakları dönüştürmek için

1. Mevcut bir bit eşlem kaynağındaki açın [Resim Düzenleyicisi](../windows/image-editor-for-icons.md). Bit eşlem içinde değilse, *.rc* sağ tıklayın, dosya *.rc* seçin ve dosya **içeri aktarma**, eklemek istediğiniz bit eşlem penceresine gidin, *.rc*  seçin ve dosya **açık**.

1. Menü Git **görüntü** > **araç çubuğu Düzenleyicisi**.

   **Yeni araç çubuğu kaynağı** iletişim kutusu görüntülenir. Genişlik ve yükseklik simgesi görüntülerin bit eşlem eşleşecek şekilde değiştirebilirsiniz. Araç çubuğu görüntüsü ardından görüntülenen **araç çubuğu Düzenleyicisi**.

1. Dönüştürme işlemini tamamlamak için komutu değiştirmek **kimliği** düğmesini kullanarak [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Yeni tür *kimliği* veya bir **kimliği** aşağı açılan listeden.

   > [!TIP]
   > **Özellikleri** pencere bir başlık çubuğundaki Raptiye düğme içerir ve bu seçeneğin seçilmesi etkinleştirir veya devre dışı bırakır **Otomatik Gizle** penceresi. Tek tek özellik pencereleri yeniden açmak zorunda kalmadan tüm araç çubuğu düğmesi özellikleri arasında geçiş yapmak için kapatma **Otomatik Gizle** kapalı böylece **özellikleri** penceresi sabit kalır.

   Yeni araç çubuğundaki düğmeler komut kimlikleri kullanarak da değiştirebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

### <a name="to-manage-toolbar-buttons"></a>Araç çubuğu düğmeleri yönetmek için

#### <a name="to-create-a-new-toolbar-button"></a>Yeni araç çubuğu düğmesi oluşturma

1. İçinde [kaynak görünümü](../windows/resource-view-window.md) kaynak klasörünü genişletin (örneğin, *Project1.rc*).

1. Genişletin **araç** klasörü ve düzenlemek için bir araç çubuğunu seçin sonra yapın aşağıdakilerden biri:

   - Boş düğme araç çubuğunun sağ ucunda bir kimliği atayın. Düzenleyerek bunu yapabilirsiniz **kimliği** özelliğinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Örneğin, aynı menü seçeneği Kimliğine araç çubuğu düğmesi vermek isteyebilirsiniz. Bu durumda, seçmek için aşağı açılan liste kutusunu kullanın **kimliği** menü seçeneğinin.

   - Araç çubuğunda sağ ucunda boş düğmeyi seçin **araç çubuğu görünümü** bölmesi ve çizim başlayın. Varsayılan düğme komut kimliği atanır (ID_BUTTON\<n >).

#### <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>Görüntüyü bir araç çubuğuna bir düğme olarak eklemek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), araç çift tıklayarak açın.

1. Ardından, araç için eklemek istediğiniz görüntü açın.

   > [!NOTE]
   > Görüntüyü Visual Studio'da açın, içinde açılır **Resim Düzenleyicisi**. Diğer grafik programında görüntü de açabilirsiniz.

1. Menü Git **Düzenle** > **kopyalama**.

1. Kaynak pencerenin üst kısmındaki sekmesini seçerek, araç çubuğu'na geçin.

1. Menü Git **Düzenle** > **Yapıştır**.

   Görüntü, araç çubuğunda yeni bir düğme olarak görünür.

#### <a name="to-move-a-toolbar-button"></a>Araç çubuğu düğmesini taşıma

İçinde **araç çubuğu görünümü** bölmesinde, araç çubuğunda yeni konumuna taşımak istediğiniz düğme sürükleyin.

- Araç çubuğundan düğme kopyalama için basılı tutun **Ctrl** anahtarı ve **araç çubuğu görünümü** bölmesi, düğmeyi ya da yeni konumuna araç çubuğunda veya bir konuma başka bir araç sürükleyin.

- Araç çubuğu düğmesi silme için araç çubuğu düğmesini seçin ve araç çubuğundan sürükleyin.

- Ekleme veya araç çubuğundaki düğmeler arasındaki boşluğu kaldırma için ya da bunları UZAĞINIZDA veya başka bir doğrultusunda araç sürükleyin.

|Eylem|Adım|
|------|------|
|Ardından bir boşluk olmayan bir düğme öncesinde bir boşluk eklemek için|İleri düğmesine hakkında yarı yarıya çakışıyor kadar aşağı ya da sağ düğme sürükleyin.|
|Sondaki boşluğu bulundurmanız gereken ve ardından bir boşluk bir düğme önce boşluk Ekle|Düğmeyi kadar sağa sürükleyin veya alt kenarı yalnızca İleri düğmesine oncollisionstay veya yalnızca çakışıyor.|
|Ardından bir boşluk bir düğme önce bir boşluk ekleyin ve aşağıdaki söz konusu alanı kapatmak için|İleri düğmesine hakkında yarı yarıya çakışıyor kadar aşağı ya da sağ düğme sürükleyin.|
|Araç çubuğundaki düğmeler arasına boşluk kaldırmak için|Kadar olan sürenin yarısına ulaşıldığında hakkında İleri düğmesine çakışıyor düğmeyi bir düğmeyi diğer tarafta doğru alanı alanı tarafında sürükleyin.|

> [!NOTE]
> Liste kutusundan sürükleyerek düğmeyi kenarındaki boşluk varsa ve düğmeyi birden fazla bitişik düğmesi, son yarısı sürükleyin **araç çubuğu Düzenleyicisi** sürüklediğiniz düğmenin karşı tarafında boşluk ekler.

#### <a name="to-change-the-properties-of-a-toolbar-button"></a>Araç çubuğu düğmesi özelliklerini değiştirme

1. Bir C++ projesinde araç çubuğu düğmesini seçin.

1. İçinde yeni kimlik yazın **kimliği** özelliğinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), ya da yeni bir seçmek için açılan listeyi kullanın **kimliği**.

#### <a name="to-create-a-tool-tip-for-a-toolbar-button"></a>Araç çubuğu düğmesi için araç ipucu oluşturmak için

1. Araç çubuğu düğmesini seçin.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), **istemi** alan, düğmenin durum çubuğunu ve sonra yapılacak bir açıklama ekleyin, ekleme `\n` ve araç ipucu adı.

Örneğin, araç ipucu için görmek için **yazdırma** düğmesine **WordPad**:

1. Açık **WordPad**.

1. Fare işaretçinizi üzerine **yazdırma** araç çubuğu düğmesi ve bildirimi word `Print` fare işaretçinizi altında artık kayan noktalı.

1. Durum çubuğu altındaki bakın **WordPad** penceresi ve bunu şimdi metin gösterildiğine dikkat edin `Prints the active document`.

`Print` Araç İpucu adıdır ve `Prints the active document` durum çubuğu düğmesini açıklaması.

Efekt kullanarak bu istiyorsanız **araç çubuğu Düzenleyicisi**ayarlayın **istemi** özelliğini `Prints the active document\nPrint`.

## <a name="requirements"></a>Gereksinimler

MFC veya ATL

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)
<!--
[Menus and Other Resources](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)<br/>
[Toolbar Button Properties](../windows/toolbar-button-properties.md)<br/>-->
