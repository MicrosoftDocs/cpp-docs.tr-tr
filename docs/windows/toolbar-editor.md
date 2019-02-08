---
title: Araç çubuğu Düzenleyicisi (C++)
ms.date: 11/04/2016
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
ms.openlocfilehash: 61b4d3ba6fc70e78c6f794528822eb66fb94de7e
ms.sourcegitcommit: 5a7dbd640376e13379f5d5b2cf66c4842e5e737b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55905790"
---
# <a name="toolbar-editor-c"></a>Araç çubuğu Düzenleyicisi (C++)

**Araç** Düzenleyici, C++ araç çubuğu kaynakları oluşturmak ve bit eşlemleri araç çubuğu kaynakları Dönüştür olanak tanır. **Araç** Düzenleyicisi araç çubuğu ve tamamlanmış bir uygulamada nasıl atacağız yakın benzer düğmeleri göstermek için bir grafik görüntüsünü kullanır.

**Araç** Düzenleyicisi penceresi iki düğme resmini, Resim Düzenleyicisi penceresi ile aynı görünümlerini gösterir. Bölünmüş çubuk iki bölmeyi ayırır. Bölmelerin göreli boyutlarını değiştirmek için bölme çubuğunu yanlara doğru sürükleyebilirsiniz. Etkin bölmede bir seçim kenarlığı görüntülenir. İki görünüm görüntünün konu araç çubuğudur.

![Araç çubuğu Düzenleyicisi](../mfc/media/vctoolbareditor.gif "vcToolbarEditor") araç çubuğu Düzenleyicisi

**Araç** Düzenleyicisi benzer **görüntü** işlevleri düzenleyicisinde. Menü öğeleri, grafik araçları ve bit eşlem kılavuz penceresindekilerle aynıdır **görüntü** Düzenleyici. Bir menü komutu yoktur **görüntü** arasında geçiş yapmanıza izin vermek için menü **araç** Düzenleyicisi ve **görüntü** Düzenleyici. Kullanma hakkında daha fazla bilgi için **grafik** araç **renkleri** paleti veya **görüntü** menüsünde görmek [görüntü Düzenleyicisi](../windows/image-editor-for-icons.md).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

İle **araç** Düzenleyicisi, şunları yapabilirsiniz:

## <a name="create-new-toolbars"></a>Yeni araç çubukları oluşturma

1. İçinde **kaynak** görüntüleyebilir, .rc dosyasına sağ tıklayın ve ardından **kaynak Ekle** kısayol menüsünden. (Var olan bir araç çubuğu, bir .rc dosyasında varsa, sadece ne sağ tıklayarak **araç** klasörü ve select **araç çubuğu ekleme** kısayol menüsünden.)

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. İçinde **kaynak Ekle** iletişim kutusunda **araç** içinde **kaynak türü** listeleyin ve ardından **yeni**.

   Bir artı işareti (**+**) yanında görünen **araç** kaynak türü geldiğini araç şablonları kullanılabilir. Şablonlar listesinde genişletin, bir şablon seçin veya seçmek için artı işaretini seçin **yeni**.

## <a name="convert-bitmaps-to-toolbar-resources"></a>Bit eşlemleri araç çubuğu kaynakları Dönüştür

Bir bit eşlem dönüştürerek bir C++ projesinde yeni bir araç çubuğu oluşturabilirsiniz. Bit eşlem Grafik araç çubuğu düğmesi görüntülerde dönüştürür. Genellikle her düğme için bir görüntü ile birkaç düğme resimlerini üzerinde tek bir bit eşlem bit eşlem içerir. Varsayılan olarak 16 piksel genişliğinde ve resmin yüksekliğini görüntüleri herhangi bir boyutta olabilir. Düğme görüntüleri boyutunu belirtebilirsiniz **yeni araç çubuğu kaynağı** seçtiğinizde iletişim kutusu **araç çubuğu Düzenleyicisi** gelen **görüntü** Resim Düzenleyicisi sırada menüsünde.

**Yeni araç çubuğu kaynağı** iletişim kutusu, genişlik ve yükseklik bir C++ projesinde bir araç çubuğu kaynağı için eklediğiniz düğmelerinin belirtmenize olanak sağlar. Varsayılan değer 16 × 15 pikseldir.

Araç çubuğu oluşturmak için kullanılan bir bit eşlem 2048 maksimum genişliği sahiptir. Bunu yaparsanız **düğmesi genişliği** 512, yalnızca dört düğme olabilir. Genişliği için 513 ayarlarsanız, yalnızca üç düğme olabilir.

İletişim kutusunda, aşağıdaki özelliklere sahiptir:

|Özellik|Açıklama|
|---|---|
|**Düğme genişliği**|Araç çubuğu kaynak bit eşlem kaynağı dönüştürüyoruz araç çubuğu düğmeleri genişliğini girmek bir alan sağlar. Resimleri belirtilen yükseklik ve genişlik kırpılmış ve renkleri (16 renk) standart araç çubuğu renklerini kullanmak için ayarlanır.|
|**Düğme yüksekliği**|Araç çubuğu kaynak bit eşlem kaynağı dönüştürüyoruz araç çubuğu düğmeleri yüksekliği girmek bir alan sağlar. Resimleri belirtilen yükseklik ve genişlik kırpılmış ve renkleri (16 renk) standart araç çubuğu renklerini kullanmak için ayarlanır.|

### <a name="to-convert-bitmaps-to-a-toolbar"></a>Bit eşlemleri araç çubuğuna dönüştürmek için

1. Mevcut bir bit eşlem kaynağındaki açın [Resim Düzenleyicisi](../windows/image-editor-for-icons.md). (Bit eşlem .rc dosyanızda değilse .rc dosyasına sağ tıklayın, seçin **alma** kısayol menüsünden, .rc dosyasına eklemek istediğiniz bit eşlem gidin ve ardından **açık**.)

1. Gelen **görüntü** menüsünde seçin **araç çubuğu Düzenleyicisi**.

   **Yeni araç çubuğu kaynağı** iletişim kutusu görüntülenir. Genişlik ve yükseklik simgesi görüntülerin bit eşlem eşleşecek şekilde değiştirebilirsiniz. Araç çubuğu görüntüsü, ardından araç çubuğu Düzenleyicisi'nde görüntülenir.

1. Dönüştürme işlemini tamamlamak için komutu değiştirmek **kimliği** düğmesini kullanarak [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Yeni tür **kimliği** veya bir **kimliği** aşağı açılan listeden.

   > [!TIP]
   > **Özellikleri** pencere bir başlık çubuğundaki Raptiye düğme içerir. Bu düğmeyi seçerek etkinleştirir veya devre dışı bırakır **Otomatik Gizle** penceresi. Tek tek özellik windows yeniden gerek kalmadan hızla tüm araç çubuğu düğmesi özellikleri geçiş yapmak için kapatma **Otomatik Gizle** kapalı böylece **özellikleri** penceresi sabit kalır.

Yeni araç çubuğundaki düğmeler komut kimlikleri kullanarak da değiştirebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

## <a name="create-move-and-edit-toolbar-buttons"></a>Oluşturma, taşıma ve düzenleme araç çubuğu düğmeleri

Kolayca oluşturun, taşıma kopyalayın ve araç çubuğu düğmeleri Düzenle.

Varsayılan olarak, araç çubuğunun sağ ucuna yeni ya da boş bir düğme görüntülenir. Bu düğme düzenlemeden önce taşıyabilirsiniz. Yeni bir düğme oluşturduğunuzda, başka bir boş düğme düzenlenen düğmesinin sağında görüntülenir. Araç çubuğu kaydettiğinizde, boş düğme kaydedilmez.

Araç çubuğu düğmesi özellikleri şunlardır:

|Özellik|Açıklama|
|--------------|-----------------|
|**ID**|Düğme için kimliği tanımlar. Açılır listede ortak sağlar **kimliği** adları.|
|**Genişlik**|Düğmesinin genişliğini belirler. 16 piksel önerilir.|
|**Yükseklik**|Düğmenin yüksekliğini belirler. Bir düğme yüksekliğini, araç çubuğundaki tüm düğmeler yüksekliğini değiştirir. 15 piksel önerilir.|
|**Sor**|Durum çubuğunda görüntülenen ileti tanımlar. Bir araç ipucu \n ve bir ad eklemek için bu araç çubuğu düğmesini ekler. Daha fazla bilgi için [bir araç ipucu oluşturmanın](../windows/creating-a-tool-tip-for-a-toolbar-button.md).|

**Genişlik** ve **yükseklik** tüm düğmeler için geçerlidir. Araç çubuğu oluşturmak için kullanılan bir bit eşlem 2048 maksimum genişliği sahiptir. Bu nedenle düğme genişliği 512 ayarlarsanız, yalnızca dört düğme olabilir ve genişliği için 513 ayarlarsanız, yalnızca üç düğme olabilir.

Aşağıdaki eylemleri bakın:

### <a name="to-create-a-new-toolbar-button"></a>Yeni araç çubuğu düğmesi oluşturma

1. İçinde [kaynak görünümü](../windows/resource-view-window.md) kaynak klasörünü genişletin (örneğin, *Project1.rc*).

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. Genişletin **araç** klasörü ve düzenlemek için bir araç çubuğunu seçin.

1. Boş düğme araç çubuğunun sağ ucunda bir kimliği atayın. Düzenleyerek bunu yapabilirsiniz **kimliği** özelliğinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Örneğin, aynı menü seçeneği Kimliğine araç çubuğu düğmesi vermek isteyebilirsiniz. Bu durumda, seçmek için aşağı açılan liste kutusunu kullanın **kimliği** menü seçeneğinin.

   -veya-

   Araç çubuğunun sağ ucunda boş düğmeyi seçin (içinde **araç çubuğu görünümü** bölmesinde) ve çizim başlayın. Varsayılan düğme komut kimliği atanır (ID_BUTTON\<n >).

Ayrıca, kopyalayın ve bir görüntüyü yeni bir düğme olarak bir araç çubuğu üzerine yapıştırın.

### <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>Görüntüyü bir araç çubuğuna bir düğme olarak eklemek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), araç çift tıklayarak açın.

1. Ardından, araç için eklemek istediğiniz görüntü açın.

   > [!NOTE]
   > Görüntüyü Visual Studio'da açın, içinde açılır **görüntü** Düzenleyici. Diğer grafik programında görüntü de açabilirsiniz.

1. Gelen **Düzenle** menüsünde seçin **kopyalama**.

1. Kaynak pencerenin üst kısmındaki sekmesini seçerek, araç çubuğu'na geçin.

1. Gelen **Düzenle** menüsünde seçin **Yapıştır**.

   Görüntü, araç çubuğunda yeni bir düğme olarak görünür.

### <a name="to-move-a-toolbar-button"></a>Araç çubuğu düğmesini taşıma

İçinde **araç çubuğu görünümü** bölmesinde, araç çubuğunda yeni konumuna taşımak istediğiniz düğme sürükleyin.

### <a name="to-copy-buttons-from-a-toolbar"></a>Araç çubuğundan düğme kopyalama

1. Basılı **Ctrl** anahtarı.

1. İçinde **araç çubuğu görünümü** bölmesi, düğmeyi ya da yeni konumuna araç çubuğunda veya bir konuma başka bir araç sürükleyin.

### <a name="to-delete-a-toolbar-button"></a>Araç çubuğu düğmesi silme

Araç çubuğu düğmesini seçin ve araç çubuğundan sürükleyin.

### <a name="to-insert-or-remove-space-between-buttons-on-a-toolbar"></a>Ekleme veya araç çubuğundaki düğmeler arasındaki boşluğu kaldırma

Genel olarak, düğmeler arasına boşluk eklemek için bunları başka uzağa araç sürükleyin. Alanı kaldırmak için bunları birbirine doğru sürükleyin.

|Eylem|Adım|
|------|------|
|Ardından bir boşluk olmayan bir düğme öncesinde bir boşluk eklemek için|İleri düğmesine hakkında yarı yarıya çakışıyor kadar aşağı ya da sağ düğme sürükleyin.|
|Sondaki boşluğu bulundurmanız gereken ve ardından bir boşluk bir düğme önce boşluk Ekle|Düğmeyi kadar sağa sürükleyin veya alt kenarı yalnızca İleri düğmesine oncollisionstay veya yalnızca çakışıyor.|
|Ardından bir boşluk bir düğme önce bir boşluk ekleyin ve aşağıdaki söz konusu alanı kapatmak için|İleri düğmesine hakkında yarı yarıya çakışıyor kadar aşağı ya da sağ düğme sürükleyin.|
|Araç çubuğundaki düğmeler arasına boşluk kaldırmak için|Kadar olan sürenin yarısına ulaşıldığında hakkında İleri düğmesine çakışıyor düğmeyi bir düğmeyi diğer tarafta doğru alanı alanı tarafında sürükleyin.|

> [!NOTE]
> Liste kutusundan sürükleyerek düğmeyi kenarındaki boşluk olmaması ve düğmeyi birden fazla bitişik düğmesi, son yarısı sürükleyin **araç** Düzenleyicisi de ters tarafında boşluk çeken düğmenin ekler sürükleme.

### <a name="to-change-the-properties-of-a-toolbar-button"></a>Araç çubuğu düğmesi özelliklerini değiştirme

1. Bir C++ projesinde araç çubuğu düğmesini seçin.

1. İçinde yeni kimlik yazın **kimliği** özelliğinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), ya da yeni bir seçmek için açılan listeyi kullanın **kimliği**.

### <a name="to-create-a-tool-tip-for-a-toolbar-button"></a>Araç çubuğu düğmesi için araç ipucu oluşturmak için

1. Araç çubuğu düğmesini seçin.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), **istemi** özellik alanı, ileti sonra; durum çubuğunu düğmenin bir açıklama ekleyin, ekleme `\n` ve araç ipucu adı.

Ortak bir araç ipucu örneğidir **yazdırma** düğmesine **WordPad**:

1. Açık **WordPad**.

1. Fare işaretçinizi üzerine **yazdırma** araç çubuğu düğmesi.

1. Dikkat word `Print` fare işaretçinizi altında artık kayan noktalı.

1. Durum çubuğu bakın (sayfanın alt kısmında **WordPad** penceresi)-bunu şimdi metin gösterdiğine dikkat edin `Prints the active document`.

`Print` İçinde **3. adım** "araç ipucu" adıdır ve `Prints the active document` gelen **4. adım** "açıklama için durum çubuğu düğmesinin."

Efekt kullanarak bu istiyorsanız **araç** Düzenleyicisi, ayarladığınız **istemi** özelliğini `Prints the active document\nPrint`.

> [!NOTE]
> İstem metnini kullanarak düzenleyebileceğiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

## <a name="requirements"></a>Gereksinimler

MFC veya ATL

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Menüler ve diğer kaynaklar](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)<br/>
[Araç Çubuğu Düğmesi Özellikleri](../windows/toolbar-button-properties.md)<br/>
