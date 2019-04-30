---
title: 'Nasıl yapılır: Düzen denetimleri (C++) | Microsoft Docs'
ms.date: 02/15/2019
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
ms.openlocfilehash: 878b7371dfa77880d68f1001444ed44b84d7240c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391081"
---
# <a name="how-to-layout-controls-c"></a>Nasıl yapılır: Düzen denetimleri (C++)

**İletişim kutusu Düzenleyicisi** hizalama ve denetimleri boyut otomatik düzeni araçlar sağlar. Çoğu görevler için kullanabileceğiniz [iletişim kutusu araç çubuğunu](../windows/showing-or-hiding-the-dialog-editor-toolbar.md). Tüm **iletişim kutusu Düzenleyicisi** araç çubuğu komutlarını kullanılabilir ayrıca **biçimi** menü ve çoğu [kısayol tuşları](../windows/accelerator-keys-for-the-dialog-editor.md).

İletişim kutuları için Düzen komutların çoğu yalnızca birden fazla denetim seçildiğinde kullanılabilir. Tek bir denetim veya birden çok denetim seçin ve birden fazla denetim seçildiğinde, seçtiğiniz birinci varsayılan olarak baskın denetimidir.

Konum, yükseklik ve genişlik geçerli denetimin durum çubuğunun sağ alt köşesinde görüntülenir. Tüm iletişim kutusu seçildiğinde durum çubuğunda bir bütün ve yüksekliğini ve genişliğini iletişim kutusunun konumunu görüntüler.

## <a name="arrange-controls"></a>Denetimleri düzenleme

Denetimler ile iletişim kutularında düzenleyebilirsiniz **iletişim kutusu Düzenleyicisi** üç farklı durumu:

- Kılavuzlar ve kenar, varsayılan olarak ayarlayın.

- Düzen Kılavuzu'nun ile.

- Tüm ek veya hizalama özellikleri olmadan.

[İletişim kutusu araç çubuğunu](../windows/showing-or-hiding-the-dialog-editor-toolbar.md) durumunu denetle düğmeleri içerir.

- Durumu değiştirmek için uygun simgeyi seçin veya menüsüne gidin **biçimi** > **Kılavuz ayarları**.

**Kılavuz ayarları** iletişim kutusunda, aşağıdaki özelliklere sahiptir:

|Özellik|Açıklama|
|---|---|
|**Düzen kılavuzları**|Düzen kılavuzları ayarlarını görüntüler.|
|**Yok.**|Düzen Araçları gizler.|
|**Cetveller ve Kılavuzlar**|Etkin olduğunda, düzeni araçları Cetveller ekler ve kılavuzları cetvellerin yerleştirilmesini sağlar. Varsayılan, kenar boşlukları kılavuzlardır.|
|**Kılavuz**|Düzen kılavuzunu oluşturur. Yeni denetimler kılavuza otomatik olarak uyum sağlar.|
|**Kılavuz aralığı**|Kılavuz aralığı Ayarları iletişim kutusu birimleri (Dlu'lar) görüntüler.|
|**Genişlik: Dlu'lar**|Düzen kılavuzunu genişliğini Dlu'lar ayarlar. Yatay DLU bölü 4 iletişim kutusu yazı tipinin ortalama genişliğidir.|
|**Yükseklik: Dlu'lar**|Düzen kılavuzunu yüksekliğini Dlu'lar ayarlar. Dikey DLU 8 tarafından ayrılmış iletişim kutusu yazı tipi ortalama yüksekliği olur.|

### <a name="guides-and-margins"></a>Kılavuzlar ve kenar boşlukları

Denetimleri ekleme denetimleri, Taşımakta olduğunuz ya da geçerli düzenini yeniden düzenleme, Kılavuzlar ve kenar boşlukları yardımcı olabilecek denetimleri bir iletişim kutusu içinde doğru bir şekilde hizalayın.

Bir iletişim kutusu oluşturduğunuzda, kenar boşlukları adlı dört değiştirilmiş kılavuzları sağlanır ve mavi noktalı çizgilerin görünür.

- Kenar boşlukları taşımak için kenar yeni konumuna sürükleyin.

- Bir kenar boşluğu kaybolmasını sağlamak için kenar sıfır bir konuma taşıyın.

- Kenar boşluğu geri getirmek için işaretçiyi kenar ait sıfır konumuna getirin ve kenar boşluğu konumuna taşıyın.

Kılavuzlar arasında Düzenleyicisi'ni ve karşılık gelen okları Cetveller üst ve sol tarafında görüntülenen iletişim kutusunda olarak mavi noktalı çizgilerin görünür **iletişim kutusu Düzenleyicisi**. Boyutlandırma denetimleri denetimleri taşınır ve daha önce Kılavuzu yaslanmış denetimler yoksa kılavuzları denetimlere Yasla Kılavuzlara Daya. Bir kılavuz taşındığında, kendisine tutturulduğunu denetimleri de taşıyın. Bir kılavuz taşındığında birden fazla Kılavuzu yaslanmış denetimleri yeniden boyutlandırılır.

- Cetvel içinde bir kılavuz oluşturmak için bir kılavuz oluşturmak için bir kez seçtiğinizde veya başlatmak için çift **Kılavuz ayarları** Kılavuz ayarları belirtebileceğiniz iletişim kutusu.

- İletişim kutusunda bir kılavuz ayarlamak için kılavuz'u seçin ve yeni bir konuma sürükleyin veya cetvelin ilişkili Kılavuzu sürüklemek için oku seçin.

   Kılavuzu koordinatlarını cetvel ve pencerenin altındaki durum çubuğunda görüntülenen veya işaretçiyi cetvel tam Kılavuzu konumunu görüntülemek için oka üzerine.

- Bir kılavuz silmek için cetvelin karşılık gelen oku sürükleyin veya iletişim kutusunu kılavuzu sürükleyin.

Değer çizgilerinin kılavuzları ve denetimlerin aralığı belirlemek Cetveller içinde iletişim kutusu birimleri (Dlu'lar) tarafından tanımlanır. Bir DLU iletişim kutusu yazı tipi, normalde 8 noktası MS Shell Dlg boyutuna bağlıdır. Yatay DLU dört tarafından ayrılmış iletişim kutusu yazı tipinin ortalama genişliğidir. Dikey DLU 8 tarafından ayrılmış yazı tipi ortalama yüksekliği olur.

- Değer çizgilerinin aralıklarına değiştirmek için menüsüne gidin **biçimi** > **Kılavuz ayarları**, ardından **ızgara Aralama** alanında, yeni genişliği ve yüksekliği içinde Dlu'lar belirtin.

### <a name="layout-grid"></a>Düzen kılavuzu

Ne zaman yerleştirme ya da iletişim kutusunda denetimleri düzenleme, daha kesin konumlandırma Düzen kılavuzunu kullanın. Kılavuz açıldığında, denetimleri manyetik hale getirme gibi kılavuz noktalı satırlarını yaslanacak.

- Düzen kılavuzunu açıp kapatmak için menüsüne gidin **biçimi** > **Kılavuz ayarları** ve seçin veya temizleyin **kılavuz** düğmesi.

   Tek tek kılavuz yine de denetleyebilirsiniz **iletişim kutusu Düzenleyicisi** kullanarak windows **Kılavuzu Aç/Kapat** düğmesini [iletişim kutusu araç çubuğunu](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

- Düzen kılavuzunu boyutunu değiştirmek için menüsüne gidin **biçimi** > **Kılavuz ayarları** ve yüksekliğini ve genişliğini kılavuzdaki hücreleri Dlu'lar içinde yazın. Minimum yükseklik veya genişlik 4 ' dir.

### <a name="disable-guides"></a>Kılavuzları devre dışı bırak

Özel anahtarları Yaslanma etkisini kılavuzları devre dışı bırakmak için fare ile birlikte kullanabilirsiniz. Kullanarak **Alt** anahtarı, seçilen Kılavuzu Yaslanma etkilerini devre dışı bırakır. Taşıma Kılavuzu ile **Shift** anahtar yaslanan denetimlerin kılavuzla taşınmasını engeller.

- Yaslanma etkisini kılavuzları devre dışı bırakmak için tutarken denetimi sürükleyin **Alt** anahtarı.

- Yaslanan denetimlerin taşımadan kılavuzları taşımak için tutarken kılavuzu sürükleyin **Shift** anahtarı.

- Kılavuzları devre dışı bırakmak için menüsüne gidin **biçimi** > **Kılavuz ayarları**. Ardından, altında **düzeni kılavuzları**seçin **hiçbiri**.

   > [!TIP]
   > Kısayol menüsünde kullanabilirsiniz **biçimi** > **rehberi Aç/Kapat**.

## <a name="select-controls"></a>Denetimleri seçin

Boyuta denetimleri seçin, hizalama, taşıyın, kopyalayın, veya silin ve ardından istediğiniz işlemi tamamlayın. Çoğu durumda, boyutu ve hizalama araçları kullanmak üzere birden fazla denetim seçmeniz gerekir [iletişim kutusu araç çubuğunu](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

Bir Denetim seçildiğinde, düz (etkin) ile veya boş (etkin olmayan), seçim kenarlığı içinde görünen küçük kareler boyutlandırma etrafında gölgeli bir kenarlık vardır. Birden çok Denetim seçildiğinde, baskın denetimi düz boyutlandırma ve diğer seçilen tüm denetimleri boş boyutlandırma tutamaçlarını sahip olduğunuz.

- Denetimler, seçmek için [araç penceresi](/visualstudio/ide/reference/toolbox)seçin **işaretçi** aracı ve seçiminizi yapın için aşağıdaki adımlardan birini kullanın:

  - İletişim kutusunda istediğiniz denetimlerin çevresinde bir seçim kutusu çizmek için işaretçiyi sürükleyin. Fare düğmesini bıraktığınızda, tüm denetimleri iç ve seçim kutusu seçili kesişen.

  - Basılı **Shift** anahtar ve seçime dahil etmek istediğiniz denetimleri seçin.

  - Basılı **Ctrl** anahtar ve seçime dahil etmek istediğiniz denetimleri seçin.

- Ekleme veya bir denetim Seçili denetimleri grubundan kaldırmak için basılı **Shift** anahtar ve eklemek veya kaldırmak istediğiniz denetimi seçin.

### <a name="dominant-controls"></a>Baskın denetimler

Boyutlandırma ya da birden çok denetimi hizalama **iletişim kutusu Düzenleyicisi** baskın denetimi diğer denetimlerin nasıl boyutlandırılmış veya hizalı belirlemek için kullanır. Varsayılan olarak, baskın denetim seçili ilk bir denetimdir.

- Baskın denetimi belirtmek için basılı **Ctrl** boyutu ve diğer denetimlerin konumu etkilemek için kullanmak istediğiniz denetimi seçin ve anahtar *ilk*. Basılı **Ctrl** anahtarı ve bir seçim içindeki bir kontrolü seçme ayrıca hale getirir, bu seçimdeki baskın denetim.

- Baskın denetimi değiştirmek için şu anda seçili tüm denetimlerin dışındaki seçerek geçerli seçimi temizleyin ve farklı bir denetimi seçip yukarıdaki yordamı yineleyin *ilk*.

> [!NOTE]
> Bağımlı denetimlerin tutamaçları boş baskın denetimi boyutlandırma tutamaçlarını düz bağlıdır. Baskın denetimi tüm daha fazla yeniden boyutlandırma veya hizalama temel alır.

## <a name="size-controls"></a>Boyut denetimleri

Bir denetimi yeniden boyutlandırmak için boyutlandırma tutamaçlarını kullanın. İşaretçi boyutlandırma tutamacı konumlandırıldığında Şekil Denetimi boyutlandırılabilir yönergeleri belirtmek için değiştirir. Etkin boyutlandırma tutamaçlarını düz ve boyutlandırma tutamacı boş ise, bu eksen boyunca denetimi yeniden boyutlandırılamıyor.

- Bir denetimi boyutlandırmak için denetimi seçin ve boyutunu değiştirmek için boyutlandırma sürükleyin.

  - Boyutu tanıtıcıları üstünde ve kenarlar, yatay veya dikey boyutunu değiştirin.

  - Boyutu tanıtıcıları köşelere yatay ve dikey boyutunu değiştirin.

   > [!TIP]
   > Basılı tutarak bir kerede denetimi bir iletişim birim (DLU) boyutlandırabilirsiniz **Shift** anahtar ve kullanarak **sağ** ve **aşağı** ok tuşları.

- Denetim içindeki metnin sığması için otomatik boyut için menüsüne gidin **biçimi** veya denetime sağ tıklayın ve seçin **içerik boyutu**.

- Denetimleri aynı boyuta getirmek için menüsüne gidin ve yeniden boyutlandırmak istediğiniz denetimleri seçin **biçimi** > **aynı boyutta yapın**, ya da seçin **hem**, **Yükseklik**, veya **genişliği**.

   Denetim dizideki ilk Seçili denetim baskın denetimi boyutuna göre grubunun yeniden boyutlandırma. Grup denetimleri son boyutu baskın denetimi boyutuna bağlıdır.

- Denetim grubunun kılavuzlarıyla boyutlandırmak için denetimin (veya denetimleri) bir yan bir kılavuza yaslama ve diğer tarafında denetimin (veya denetimleri) için bir kılavuz sürükleyin. Şimdi, denetimin (veya denetimleri) boyutlandırmak için iki Kılavuzu taşıyabilirsiniz.

   Gerekirse birden çok denetimlerle her ikinci kılavuza uydurmayı boyutu.

### <a name="other-controls"></a>Diğer denetimleri

İletişim kutusuna eklediğinizde bir birleşik giriş kutusu boyutlandırabilirsiniz. Aşağı açılan liste kutusunda boyutunu belirtebilirsiniz. Daha fazla bilgi için [değerleri birleşik giriş kutusu denetimi ekleme](../windows/adding-values-to-a-combo-box-control.md).

1. Birleşik giriş kutusunun sağındaki açılan ok düğmesini seçin.

   ![Bir MFC projesinde bir birleşik giriş kutusu oku](../mfc/media/vccomboboxarrow.gif "vcComboBoxArrow")

   Genişletilmiş açılır listede alanı ile birleşik giriş kutusunun boyutunu göstermek için Denetim değişikliklerin anahattı.

1. Alt boyutlandırma tutamacı açılır listede alanın başlangıç boyutunu değiştirmek için kullanın.

   ![Birleşik giriş&#45;kutusu boyutlandırma MFC projesinde](../mfc/media/vccomboboxsizing.gif "vcComboBoxSizing")

1. Birleşik giriş kutusundaki açılır listede bölümünü yeniden kapatmak için açılan oku seçin.

> [!NOTE]
> MFC kullanarak iletişim kutusuna bir yatay kaydırma çubuğu içeren bir liste kutusu eklediğinizde, kaydırma çubuğu uygulamanızı otomatik olarak görünmez.
>
> Çağırarak geniş öğesi için bir maksimum genişliğini ayarlamak [CListBox::SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) kodunuzda. Bu değer kümesi kaydırma çubuğu görünmez, hatta öğeleri liste kutusunda kutudan daha geniş olduğunda.

## <a name="align-controls"></a>Denetimleri hizalama

- Denetimleri hizalama için hizalamak için istediğiniz denetimleri seçin. Menü Git **biçimi** > **Hizala** ve aşağıdaki hizalamaları birini seçin:

   |Hizalama|Açıklama|
   |-----|-----------|
   |**Hizala**|Seçili denetimleri, sol kenarı boyunca hizalar.|
   |**Merkezleri**|Seçili denetimleri yatay olarak kendi center noktalarını boyunca hizalar.|
   |**Hakları**|Seçili denetimleri kendi sağ kenarı boyunca hizalar.|
   |**Kırpın**|Seçili denetimleri üst kenarları boyunca hizalar.|
   |**Ortaları**|Seçili denetimleri dikey olarak kendi orta noktaları boyunca hizalar.|
   |**Alta**|Seçili denetimleri alt kenarları boyunca hizalar.|

   İlk baskın olmasını istediğiniz denetim seçtiğinizden emin olun veya hizalama yürütme ya da komut son denetim grubunun konumunu baskın denetimi konumuna olarak boyutlandırma önce baskın denetimi olacak şekilde ayarlayın.

- Eşit alanı denetimleri yeniden düzenlemek istediğiniz denetimleri seçin. Menü Git **biçimi** > **eşit** ve aşağıdaki aralığı hizalamaları birini seçin:

   |Aralığı|Açıklama|
   |---|---|
   |**Arasında**|En soldaki ve sağdaki denetimi seçili arasında eşit alanı denetler.|
   |**Aşağı**|Üstteki ve alttaki denetimi seçili arasında eşit alanı denetler.|

- Denetim merkezi için denetimi veya denetimleri yeniden düzenlemek istediğiniz'ı seçin. Menü Git **biçimi** > **Merkezi iletişim** ve aşağıdaki düzenlemeleri birini seçin:

   |Düzenleme|Açıklama|
   |---|---|
   |**Dikey**|İletişim kutusu denetimleri dikey olarak ortalayın.|
   |**Yatay**|Denetimleri yatay olarak iletişim kutusunda ortalayın.|

- Basma düğmelerini hizalamak için bir veya daha fazla basma düğmelerini seçin. Menü Git **biçimi** > **Düzenle düğmeler**, aşağıdaki düzenlemeleri birini seçin:

   |Düzenleme|Açıklama|
   |---|---|
   |**sağ**|Basma düğmelerini iletişim kutusunun sağ kenarı hizalar.|
   |**alt**|Basma düğmelerini iletişim kutusunun alt kenarı hizalar.|

   Bir denetimin bir itme düğmesi dışında seçerseniz konumuna etkilenmez.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutusu denetimleri yönetme](controls-in-dialog-boxes.md)<br/>
[Nasıl yapılır: Denetimleri Ekleme, Düzenleme veya Silme](adding-editing-or-deleting-controls.md)<br/>
[Nasıl yapılır: Denetim Erişimini ve Değerlerini Tanımlama](defining-mnemonics-access-keys.md)<br/>