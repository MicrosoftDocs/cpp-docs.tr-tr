---
title: Denetimlerin düzenlenmesi iletişim kutuları (C++) | Microsoft Docs
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.grouping
- vc.editors.dialog.combo
helpviewer_keywords:
- controls [C++], positioning
- dialog box controls [C++], placement
- Dialog Editor [C++], arranging controls
- Dialog Editor [C++], guides and margins
- guides, clearing
- guides
- dialog box controls [C++], placement
- controls [C++], guides and margins
- guides, creating
- guides, moving
- margins, moving
- DLUs (dialog units)
- controls [C++], aligning
- Dialog Editor [C++], snap to guides
- guides, tick mark interval
- dialog box controls [C++], placement
- guides, aligning controls
- dialog units (DLUs)
- snap to guides (Dialog editor)
- controls [C++], sizing
- tick mark interval in Dialog editor
- controls [C++], snap to guides/grid
- guides, disabling snapping
- controls [C++], snap to guides/grid
- controls [C++], layout grid
- snap to layout grid
- grids, turning on or off
- layout grid in Dialog Editor
- grids, changing size
- grid spacing
- guides, settings
- layout grid in Dialog Editor
- controls [C++], snap to guides/grid
- Guide Settings dialog box (Dialog editor)
- controls [C++], aligning
- controls [C++], positioning
- Space Evenly command
- dialog box controls [C++], placement
- Center in Dialog command
- Arrange Buttons command
- buttons, arranging push buttons in dialog boxes
- push buttons
- member variables, adding to radio button groups
- variables, dialog box control member variables
- dialog box controls [C++], grouping radio buttons
- grouping controls
- radio buttons [C++], grouping on dialog boxes
- controls [C++], tab order
- focus, tab order
- tab controls [C++], tab order
- Tabstop property for controls
- controls [C++], focus
- dialog box controls [C++], tab order
- Dialog Editor [C++], selecting controls
- dominant controls
- dialog box controls [C++], selecting in editor
- controls [C++], selecting
- size, controls
- controls [C++], dominant
- controls [C++], removing from groups
- Dialog Editor [C++], dominant control
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
- Make Same Size command
- combo boxes, sizing
- list controls [C++], scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars [C++], displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars [C++], width
ms.assetid: 832491cf-98af-42e5-a854-2cb135fd45c6
ms.openlocfilehash: 99667898428fe9532d59277bfedafd24927304dc
ms.sourcegitcommit: eb2b34a24e6edafb727e87b138499fa8945f981e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2019
ms.locfileid: "56264887"
---
# <a name="arrangement-of-controls-on-dialog-boxes-c"></a>Denetimlerin düzenlenmesi iletişim kutuları (C++)

**İletişim** Düzenleyicisi, hizalama ve denetimleri boyut otomatik düzeni araçlar sağlar. Çoğu görevler için kullanabileceğiniz [iletişim kutusu araç çubuğunu](../windows/showing-or-hiding-the-dialog-editor-toolbar.md). Tüm **iletişim kutusu Düzenleyicisi** araç çubuğu komutlarını kullanılabilir ayrıca **biçimi** menü ve çoğu [kısayol tuşları](../windows/accelerator-keys-for-the-dialog-editor.md).

İletişim kutuları için Düzen komutların çoğu yalnızca birden fazla denetim seçildiğinde kullanılabilir. Tek bir denetim veya birden çok denetim seçin ve birden fazla denetim seçildiğinde, seçtiğiniz birinci varsayılan olarak "baskın" denetimidir. Denetimleri ve baskın denetimi seçme hakkında daha fazla bilgi için bkz: [seçerek denetimleri](../windows/selecting-controls.md).

Konum, yükseklik ve genişlik geçerli denetimin durum çubuğunun sağ alt köşesinde görüntülenir. Tüm iletişim kutusu seçildiğinde durum çubuğunda bir bütün ve yüksekliğini ve genişliğini iletişim kutusunun konumunu görüntüler.

## <a name="dialog-editor-states-guides-and-grids"></a>İletişim kutusu Düzenleyicisi durumları (Kılavuzlar ve Izgaralar)

Denetimler ile iletişim kutularında düzenleyebilirsiniz **iletişim** farklı üç durumdan birine düzenleyicisinde:

- Kılavuzlar ve kenar boşlukları (varsayılan ayar) ile

- İçeren düzen kılavuz

- Herhangi bir yaslama veya hizalama özellik

[İletişim kutusu araç çubuğunu](../windows/showing-or-hiding-the-dialog-editor-toolbar.md) durumunu denetle düğmeleri içerir. Durumu değiştirmek için ilgili simgeyi seçin. Durumları kullanarak da değiştirebilirsiniz **Kılavuz ayarları** komutunu **biçimi** menüsü.

**Kılavuz ayarları** iletişim kutusunda, aşağıdaki özelliklere sahiptir:

|Özellik|Açıklama|
|---|---|
|**Düzen kılavuzları**|Düzen kılavuzları ayarlarını görüntüler.|
|**Yok.**|Düzen Araçları gizler.|
|**Cetveller ve Kılavuzlar**|Etkin olduğunda, düzeni araçları Cetveller ekler; kılavuzları cetvellerin yerleştirilebilir. Varsayılan sürükleyerek taşınabilir kenar boşluklarını kılavuzlardır. Bir kılavuz yerleştirmek için cetvellerden seçin. "Denetimleri üzerinden veya bunların yanındaki taşındığında denetimleri Kılavuzlara Daya". Kendisine bağlı sonra denetimleri ile bir kılavuz da taşıyın. Her iki taraftaki bir kılavuz bir denetimin ekli olduğu ve bir kılavuz taşınır, denetimi yeniden boyutlandırır.|
|**Kılavuz**|Düzen kılavuzunu oluşturur. Yeni denetimler kılavuza otomatik olarak uyum sağlar.|
|**Kılavuz aralığı**|Kılavuz aralığı Ayarları iletişim kutusu birimleri (Dlu'lar) görüntüler.|
|**Genişlik: Dlu'lar**|Düzen kılavuzunu genişliğini Dlu'lar ayarlar. Yatay DLU dört tarafından ayrılmış iletişim kutusu yazı tipinin ortalama genişliğidir.|
|**Yükseklik: Dlu'lar**|Düzen kılavuzunu yüksekliğini Dlu'lar ayarlar. Dikey DLU sekiz tarafından ayrılmış iletişim kutusu yazı tipi ortalama yüksekliği olur.|

### <a name="create-and-set-guides-and-margins"></a>Kılavuzlar ve kenar boşlukları oluşturma ve

Denetimleri ekleme denetimleri, Taşımakta olduğunuz ya da geçerli düzenini yeniden düzenleme, kılavuzları yardımcı olabilecek bir iletişim kutusu içinde doğru bir şekilde denetimleri hizalayın. Kılavuzlar arasında Düzenleyicisi'ni ve karşılık gelen okları Cetveller üst ve sol tarafında görüntülenen iletişim kutusunda olarak mavi noktalı çizgilerin görünür **iletişim** Düzenleyici.

Bir iletişim kutusu oluşturduğunuzda, dört kenar boşlukları sağlanır. Kenar boşlukları, mavi noktalı çizgiler olarak görünen, değiştirilen kılavuzlardır.

|İşlem|Adımlar|
|----------------|----------------|
|Bir kılavuz oluşturmak için|Cetvel içinde bir kılavuz oluşturmak için bir kez seçin. (Tek bir tıklamayla oluşturur, yeni bir kılavuzu; başlatır çift **Kılavuz ayarları** içinde belirtebilirsiniz kılavuz Ayarları iletişim kutusu.)|
|Bir kılavuz ayarlamak için|İletişim kutusunda, Kılavuzu'nu tıklatın ve yeni bir konuma sürükleyin. (Ayrıca ilişkili Kılavuzu sürüklemek için cetvelin oka tıklayabilirsiniz.)<br/><br/>Kılavuzu koordinatlarını cetvel ve pencerenin altındaki durum çubuğunda görüntülenir. Tam Kılavuzu konumunu görüntülemek için cetvelin oka üzerine getirin.|
|Bir kılavuz silmek için|İletişim kutusunu kılavuzu sürükleyin.<br/><br/>\- veya -<br/><br/>Cetvelin karşılık gelen oku sürükleyin.|
|Kenar boşlukları taşımak için|Kenar boşluğu yeni konumuna sürükleyin.<br/><br/>Bir kenar boşluğu kaybolmasını sağlamak için kenar sıfır bir konuma taşıyın. Kenar boşluğu geri getirmek için işaretçiyi kenar ait sıfır konumuna getirin ve kenar boşluğu konumuna taşıyın.|

### <a name="align-controls-on-a-guide"></a>Kılavuzdaki denetimleri hizalama

Boyutlandırma denetimleri denetimleri taşınır ve daha önce Kılavuzu yaslanmış denetimler yoksa kılavuzları denetimlere Yasla Kılavuzlara Daya. Bir kılavuz taşındığında, kendisine tutturulduğunu denetimleri de taşıyın. Bir kılavuz taşındığında birden fazla Kılavuzu yaslanmış denetimleri yeniden boyutlandırılır.

Değer çizgilerinin kılavuzları ve denetimlerin aralığı belirlemek Cetveller içinde iletişim kutusu birimleri (Dlu'lar) tarafından tanımlanır. Bir DLU iletişim kutusu yazı tipi, normalde 8 noktası MS Shell Dlg boyutuna bağlıdır. Yatay DLU dört tarafından ayrılmış iletişim kutusu yazı tipinin ortalama genişliğidir. Dikey DLU sekiz tarafından ayrılmış yazı tipi ortalama yüksekliği olur.

Denetim grubunun kılavuzlarıyla boyutlandırmak için:

1. Denetimin (veya denetimleri) bir tarafı bir kılavuza yapışır.

1. Diğer tarafında denetimin (veya denetimleri) için bir kılavuz sürükleyin.

   Gerekirse birden çok denetimlerle her ikinci kılavuza uydurmayı boyutu.

1. Denetimin (veya denetimleri) boyutlandırmak için iki Kılavuzu taşıyın.

Değer çizgilerinin aralıklarına değiştirmek için:

1. Gelen **biçimi** menüsünde seçin **Kılavuz ayarları**.

1. İçinde **Kılavuz ayarları** iletişim kutusundaki **ızgara Aralama** alanında, yeni genişliği ve yüksekliği içinde Dlu'lar belirtin.

### <a name="disable-guides"></a>Kılavuzları devre dışı bırak

Özel anahtarları Yaslanma etkisini kılavuzları devre dışı bırakmak için fare ile birlikte kullanabilirsiniz. Kullanarak **Alt** anahtarı, seçilen Kılavuzu Yaslanma etkilerini devre dışı bırakır. Taşıma Kılavuzu ile **Shift** anahtar yaslanan denetimlerin kılavuzla taşınmasını engeller.

- Yaslanma etkisini kılavuzları devre dışı bırakmak için tutarken denetimi sürükleyin **Alt** anahtarı.

- Yaslanan denetimlerin taşımadan kılavuzları taşımak için tutarken kılavuzu sürükleyin **Shift** anahtarı.

- Gelen kılavuzları, açmak için **biçimi** menüsünde seçin **Kılavuz ayarları**. Ardından **Kılavuz ayarları** iletişim kutusunun **düzeni kılavuzları**seçin **hiçbiri**.

   > [!NOTE]
   > Ayrıca cetvel çubuğuna erişmek için çift **Kılavuz ayarları** iletişim kutusu.

> [!TIP]
> Kılavuzları için bir kısayol açıktır **biçimi** menüsünde **rehberi Aç/Kapat**.

### <a name="modify-the-layout-grid"></a>Düzen kılavuzunu değiştirme

Yerleştirme ya da iletişim kutusunda denetimleri düzenleme için daha kesin konumlandırma Düzen kılavuzunu kullanabilirsiniz. Kılavuz açıldığında, "için kılavuz noktalı satırlarını manyetik hale getirme gibi ek bileşen için" denetimleri görünür. Bu "kılavuz çizgilerinde" özelliğini açıp kapatmak ve Düzen kılavuz hücreleri boyutunu değiştirin.

Düzen kılavuzunu açıp kapatmak için:

1. Gelen **biçimi** menüsünde seçin **Kılavuz ayarları**.

1. İçinde **Kılavuz ayarları** iletişim kutusu, seçin veya temizleyin **kılavuz** düğmesi.

   Tek tek kılavuz yine de denetleyebilirsiniz **iletişim** Düzenleyici pencerelerini kullanarak **Kılavuzu Aç/Kapat** düğmesini [iletişim kutusu araç çubuğunu](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

Düzen kılavuzunu boyutunu değiştirmek için:

1. Gelen **biçimi** menüsünde seçin **Kılavuz ayarları**.

1. İçinde **Kılavuz ayarları** iletişim yükseklik ve genişlik kılavuzdaki hücreleri Dlu'lar içinde yazın. Minimum yükseklik veya genişlik 4 Dlu'lar ' dir.

## <a name="selecting-controls"></a>Denetimleri Seçme

Boyuta denetimleri seçin, hizalama, taşıyın, kopyalayın, veya silin ve ardından istediğiniz işlemi tamamlayın. Çoğu durumda, boyutu ve hizalama araçları kullanmak üzere birden fazla denetim seçmeniz gerekir [iletişim kutusu araç çubuğunu](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

Bir denetim seçili durumdayken, etrafında gölgeli bir kenarlık kesintisiz (etkin) sahip veya boş (etkin olmayan) "boyutlandırma tutamaçlarını" küçük kareler, zaman içinde seçim kenarlığı görüntülenir. Birden çok Denetim seçildiğinde, baskın denetimi düz boyutlandırma ve diğer seçilen tüm denetimleri boş boyutlandırma tutamaçlarını sahip olduğunuz.

Boyutlandırma ya da birden çok denetimi hizalama **iletişim** Düzenleyicisi kullanır "baskın denetimi" diğer denetimlerin nasıl boyutlandırılmış veya hizalı belirlemek için. Varsayılan olarak, baskın denetim seçili ilk bir denetimdir.

### <a name="to-select-multiple-controls"></a>Birden çok denetim seçin

1. İçinde [araç penceresi](/visualstudio/ide/reference/toolbox)seçin **işaretçi** aracı.

1. Seçiminizi yapmak için aşağıdaki adımlardan birini kullanın:

   - İletişim kutusunda istediğiniz denetimlerin çevresinde bir seçim kutusu çizmek için işaretçiyi sürükleyin. Fare düğmesini bıraktığınızda, tüm denetimleri iç ve seçim kutusu seçili kesişen.

   - Basılı **Shift** anahtar ve seçime dahil etmek istediğiniz denetimleri seçin.

   - Basılı **Ctrl** anahtar ve seçime dahil etmek istediğiniz denetimleri seçin.

### <a name="to-remove-a-control-from-a-group-of-selected-controls-or-to-add-a-control-to-a-group-of-selected-controls"></a>Bir denetim seçili denetimlerin bir gruptan kaldırmak için veya bir denetim seçili denetimlerin bir gruba eklemek için

Seçili denetimleri grubuyla basılı **Shift** anahtar ve mevcut seçime Ekle veya kaldırmak istediğiniz denetimi seçin.

   > [!NOTE]
   > Basılı **Ctrl** anahtarı ve bir seçim içindeki bir kontrolü seçme hale getirir, bu seçimdeki baskın denetim.

### <a name="to-specify-the-dominant-control"></a>Baskın denetimi belirtmek için

Basılı **Ctrl** boyutu ve diğer denetimlerin konumu etkilemek için kullanmak istediğiniz denetimi seçin ve anahtar *ilk*.

> [!NOTE]
> Bağımlı denetimlerin tutamaçları boş baskın denetimi boyutlandırma tutamaçlarını düz bağlıdır. Baskın denetimi tüm daha fazla yeniden boyutlandırma veya hizalama temel alır.

### <a name="to-change-the-dominant-control"></a>Baskın denetimi değiştirmek için

1. Şu anda seçili tüm denetimlerin dışındaki tıklayarak geçerli seçimi temizleyin.

1. Farklı bir denetim ilk seçerek önceki yordamı yineleyin.

## <a name="sizing-controls"></a>Boyutlandırma denetimleri

Bir denetimi yeniden boyutlandırmak için boyutlandırma tutamaçlarını kullanın. İşaretçi boyutlandırma tutamacı konumlandırıldığında Şekil Denetimi boyutlandırılabilir yönergeleri belirtmek için değiştirir. Etkin boyutlandırma tutamaçlarını düz; boyutlandırma tutamacı boş ise, bu eksen boyunca denetimi yeniden boyutlandırılamaz.

Denetim kılavuzları veya kenar boşlukları yaslama tarafından bir denetimin boyutunu değiştirebilirsiniz ya da taşıyarak bir denetim ve başka bir kılavuzu yaslanan.

### <a name="to-size-an-individual-control"></a>Tek bir denetim boyutu

1. Denetimi seçin.

1. Denetimin boyutunu değiştirmek için boyutlandırma tutamaçlarını sürükleyerek:

   - Boyutlandırma üstünde ve kenarlar, yatay veya dikey boyutunu değiştirin.

   - Boyutlandırma köşelere yatay ve dikey boyutunu değiştirin.

   > [!TIP]
   > Basılı tutarak bir kerede denetimi bir iletişim birim (DLU) boyutlandırabilirsiniz **Shift** anahtar ve kullanarak **sağ ok** ve **aşağı ok** anahtarları.

### <a name="to-automatically-size-a-control-to-fit-the-text-within-it"></a>Denetim içindeki metnin sığması için otomatik olarak boyutlandırmak için

Seçin **içerik boyutu** gelen **biçimi** menüsü veya denetime sağ tıklayın ve seçin **içerik boyutu** kısayol menüsünden.

### <a name="to-make-controls-the-same-width-height-or-size"></a>Aynı genişliğe, yüksekliğe veya boyuta denetimleri yapma

Baskın denetimi boyutuna göre Denetim grubunun yeniden boyutlandırabilirsiniz.

1. Yeniden boyutlandırmak istediğiniz denetimleri seçin.

   Bu serideki ilk Seçili denetim baskın bir denetimdir. Grup denetimleri son boyutu baskın denetimi boyutuna bağlıdır.

1. Gelen **biçimi** menüsünde, seçin **aynı boyutta yapın**, ardından **hem**, **yükseklik**, veya **genişliği**.

### <a name="to-set-the-size-of-the-combo-box-and-its-drop-down-list"></a>Boyutu birleşik giriş kutusu ve aşağı açılan listesinin ayarlamak için

İletişim kutusuna eklediğinizde bir birleşik giriş kutusu boyutlandırabilirsiniz. Aşağı açılan liste kutusunda boyutunu belirtebilirsiniz. Daha fazla bilgi için [değerleri birleşik giriş kutusu denetimi ekleme](../windows/adding-values-to-a-combo-box-control.md).

#### <a name="to-size-a-combo-box"></a>Boyutuna bir birleşik giriş kutusu

1. Birleşik giriş kutusu denetimi sizin iletişim kutunuzda seçin.

   Başlangıçta, yalnızca sağ ve sol boyutlandırma tutamaçlarını etkindir.

1. Birleşik giriş kutusunun genişliğini ayarlamak için boyutlandırma tutamaçlarını kullanın.

Ayrıca, birleşik giriş kutusunun yanıdaki açılan kısmı dikey boyutunu ayarlayabilirsiniz.

#### <a name="to-set-the-size-of-the-combo-box-drop-down-list"></a>Aşağı açılan liste kutusunda açılan boyutunu ayarlamak için

1. Birleşik giriş kutusunun sağındaki açılan ok düğmesini seçin.

   ![Bir MFC projesinde bir birleşik giriş kutusu oku](../mfc/media/vccomboboxarrow.gif "vcComboBoxArrow")

   Genişletilmiş açılır listede alanı ile birleşik giriş kutusunun boyutunu göstermek için Denetim değişikliklerin anahattı.

1. Alt boyutlandırma tutamacı açılır listede alanın başlangıç boyutunu değiştirmek için kullanın.

   ![Birleşik giriş&#45;kutusu boyutlandırma MFC projesinde](../mfc/media/vccomboboxsizing.gif "vcComboBoxSizing")

1. Birleşik giriş kutusundaki açılır listede bölümünü yeniden kapatmak için açılan oku seçin.

### <a name="to-set-the-width-of-a-horizontal-scroll-bar-and-make-it-appear"></a>Yatay kaydırma çubuğunun genişliğini ayarlama ve görünmesini sağlamak için

MFC sınıfları kullanarak iletişim kutusuna bir yatay kaydırma çubuğu içeren bir liste kutusu eklediğinizde, kaydırma çubuğu uygulamanızı otomatik olarak görünmez.

Çağırarak geniş öğesi için bir maksimum genişliğini ayarlamak [CListBox::SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) kodunuzda.

   Bu değer kümesi kaydırma çubuğu görünmez, hatta öğeleri liste kutusunda kutudan daha geniş olduğunda.

## <a name="group-radio-buttons-on-a-dialog-box"></a>Grup iletişim kutusundaki radyo düğmeleri

Radyo düğmeleri iletişim kutusuna eklediğinizde, bunları bir grup olarak ayarlayarak ele almanız bir **grubu** özelliğinde **özellikleri** gruptaki ilk düğmenin penceresi. Denetim Kimliği bu radyo düğmesi için daha sonra yer [üye değişkeni Ekleme Sihirbazı'nı](../ide/add-member-variable-wizard.md), radyo düğmesi grubunu için bir üye değişkeni ekleme etmenize imkan sağlar.

İletişim kutusundaki radyo düğmelerini birden fazla grup olabilir ve her grup, aşağıdaki yordamı kullanarak eklenmelidir.

### <a name="to-add-a-group-of-radio-buttons-to-a-dialog-box"></a>Bir iletişim kutusu için bir grup radyo düğmeleri eklemek için

1. Radyo düğmesi denetiminde seçme [araç penceresi](/visualstudio/ide/reference/toolbox) ve iletişim kutusunda, denetimi yerleştirmek istediğiniz konumu seçin.

1. 1. adım, ihtiyacınız kadar radyo düğmeleri eklemek için yineleyin. Radyo düğmesi grubunda sekme sırasının ardışık olduğundan emin olun.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window)ayarlayın **grubu** özelliği *ilk* radyo düğmesi için sekmesinde sırayla **True**.

   Değiştirme **grubu** özelliğini **True** WS_GROUP stili kaynak betiği iletişim nesnesinin düğmenin girişi ekler ve bir kullanıcı yalnızca bir radyo düğmesi birer birer düğmesinde seçebilirsiniz, sağlar Grup (kullanıcı bir radyo düğmesine tıkladığında, gruptaki diğer temizlenir).

   > [!NOTE]
   > Yalnızca ilk radyo düğmesi grubunda olmalıdır **grubu** özelliğini **True**. Düğmesi grubunun parçası olmayan ek denetimleri varsa Ayarla **grubu** ilk denetiminin özelliği *grubun dışına olan* için **True** de. İlk denetim grubu dışında tuşlarına basarak hızlıca tanımlayabilirsiniz **Ctrl**+**D** sekme sırasını görüntülemek için.

### <a name="to-add-a-member-variable-for-the-radio-button-group"></a>Radyo düğmesi grubunda için üye değişkeni eklemek için

1. Sekme sırasında ilk radyo düğmesi denetimini sağ tıklayın (baskın denetimi ve biriyle **grubu** özelliği True olarak ayarlayın).

1. Seçin **değişken Ekle** kısayol menüsünden.

1. İçinde [üye değişkeni Ekleme Sihirbazı'nı](../ide/add-member-variable-wizard.md)seçin **denetim değişkeni** onay kutusunu işaretleyin ve ardından **değer** radyo düğmesi.

1. İçinde **değişken adı** yeni bir üye değişkeni için bir ad yazın.

1. İçinde **değişken türü** liste kutusu, select **int** veya türü `int`.

1. Şimdi, kodunuzun hangi radyo düğmesini seçili görünmesi gerektiğini belirten değiştirebilirsiniz. Örneğin, `m_radioBox1 = 0;` gruptaki ilk radyo düğmesini seçer.

## <a name="to-align-groups-of-controls"></a>Denetim gruplarını hizalama

1. Denetimleri hizalama istediğiniz seçin. Baskın denetimi olmasını istediğiniz denetim seçtiğinizden emin olun veya hizalama yürütme ya da komut boyutlandırma önce baskın denetimi olacak şekilde ayarlayın.

   Denetim grubunun son konumunu baskın denetimi konumuna bağlıdır. Baskın denetimi seçme hakkında daha fazla bilgi için bkz. [baskın denetimi belirtme](../windows/specifying-the-dominant-control.md).

1. Gelen **biçimi** menüsünde seçin **Hizala**ve ardından aşağıdaki hizalamaları birini seçin:

   |Değer|Açıklama|
   |-----|-----------|
   |`Lefts`|Seçili denetimleri, sol kenarı boyunca hizalar.|
   |`Centers`|Seçili denetimleri yatay olarak kendi center noktalarını boyunca hizalar.|
   |`Rights`|Seçili denetimleri kendi sağ kenarı boyunca hizalar.|
   |`Tops`|Seçili denetimleri üst kenarları boyunca hizalar.|
   |`Middles`|Seçili denetimleri dikey olarak kendi orta noktaları boyunca hizalar.|
   |`Bottoms`|Seçili denetimleri alt kenarları boyunca hizalar.|

### <a name="to-even-the-spacing-between-controls"></a>Denetimler arasındaki aralığı bile için

**İletişim** Düzenleyicisi eşit olarak seçilen en dıştaki denetimler arasındaki boşluk denetimlere, sağlar.

1. Yeniden düzenlemek istediğiniz denetimleri seçin.

1. Gelen **biçimi** menüsünde seçin **eşit**ve ardından aşağıdaki aralığı hizalamaları birini seçin:

   - `Across`: alanı en soldaki ve sağdaki denetimi seçili arasında eşit olarak denetimleri.

   - `Down`: alanı üstteki ve alttaki denetimi seçili arasında eşit olarak denetimleri.

### <a name="to-center-controls-in-a-dialog-box"></a>İletişim kutusundaki denetimlere ortalamak için

1. Denetim veya yeniden düzenlemek istediğiniz denetimleri seçin.

1. Gelen **biçimi** menüsünde seçin **Merkezi iletişim**ve ardından aşağıdaki düzenlemeleri birini seçin:

   - `Vertical`: iletişim kutusu denetimleri dikey olarak ortalayın.

   - `Horizontal`: yatay olarak iletişim kutusunda denetimleri ortalama.

### <a name="to-arrange-push-buttons-along-the-right-or-bottom-of-a-dialog-box"></a>Basma düğmelerini iletişim kutusunun alt ve sağ düzenlemek için

1. Bir veya daha fazla basma düğmelerini seçin.

1. Gelen **biçimi** menüsünde seçin **Düzenle düğmeler**ve ardından aşağıdaki düzenlemeleri birini seçin:

   - `Right`: basma düğmelerini iletişim kutusunun sağ kenarı hizalar.

   - `Bottom`: basma düğmelerini iletişim kutusunun alt kenarı hizalar.

       Bir denetimin bir itme düğmesi dışında seçerseniz konumuna etkilenmez.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[Denetimler](../mfc/controls-mfc.md)