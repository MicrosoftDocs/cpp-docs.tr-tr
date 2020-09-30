---
title: 'Nasıl yapılır: düzen denetimleri (C++) | Microsoft Docs'
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
ms.openlocfilehash: ac21096f18b1331759f9bf7dfe613100298b7296
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509661"
---
# <a name="how-to-layout-controls-c"></a>Nasıl yapılır: düzen denetimleri (C++)

**Iletişim kutusu Düzenleyicisi** , denetimleri otomatik olarak hizalamakta ve boyutlandırmakta olan Düzen araçları sağlar. Çoğu görev için [Iletişim kutusu Düzenleyici araç çubuğunu](./dialog-editor.md)kullanabilirsiniz. Tüm **Iletişim kutusu düzenleyici** komutları **Biçim** menüsünde de bulunur ve çoğu [kısayol tuşlarına](./dialog-editor.md)sahiptir.

İletişim kutuları için birçok düzen komutu yalnızca birden fazla denetim seçildiğinde kullanılabilir. Tek bir denetim veya birden çok denetim seçebilirsiniz ve birden fazla denetim seçildiğinde, seçtiğiniz ilk, varsayılan olarak baskın denetim olur.

Geçerli denetimin konumu, yüksekliği ve genişliği durum çubuğunun sağ alt köşesinde görüntülenir. İletişim kutusunun tamamı seçildiğinde durum çubuğu, iletişim kutusunun bir bütün olarak konumunu ve yüksekliğini ve genişliğini görüntüler.

## <a name="arrange-controls"></a>Denetimleri Düzenleme

İletişim kutularındaki denetimleri, üç farklı durumdan birinde **iletişim kutusu Düzenleyicisi** ile düzenleyebilirsiniz:

- Kılavuzlar ve kenar boşlukları ile, varsayılan olarak ayarlanır.

- Üzerine düzen kılavuzu ile.

- Herhangi bir yaslama veya hizalama özelliği olmadan.

[Iletişim kutusu Düzenleyici araç çubuğu](./dialog-editor.md) , durumu denetleyen düğmeleri içerir.

- Durumu değiştirmek için, uygun simgeyi seçin veya menü **biçimlendirme**  >  **Kılavuzu ayarları**' na gidin.

**Kılavuz ayarları** iletişim kutusu aşağıdaki özelliklere sahiptir:

|Özellik|Açıklama|
|---|---|
|**Düzen kılavuzu**|Düzen kılavuzlarının ayarlarını görüntüler.|
|**Hiçbiri**|Düzen araçlarını gizler.|
|**Cetveller ve kılavuzlar**|Etkinleştirildiğinde, düzen araçlarına cetveller ekler ve kılavuzların cetvellere yerleştirilmesini sağlar. Varsayılan kılavuzlar kenar boşluklardır.|
|**Kılavuz**|Düzen kılavuzu oluşturur. Yeni denetimler otomatik olarak kılavuza hizalanır.|
|**Izgara aralığı**|İletişim kutusu birimlerindeki (DLUs) kılavuz aralıklarının ayarlarını görüntüler.|
|**Genişlik: DLUs**|DLUs 'teki Düzen kılavuzunun genişliğini ayarlar. Yatay bir DLU, iletişim kutusu yazı tipinin 4 ' ü bölü ortalama genişliğidir.|
|**Yükseklik: DLUs**|DLUs 'teki Düzen kılavuzunun yüksekliğini ayarlar. Dikey bir DLU, iletişim kutusu yazı tipinin 8 ' i bölü ortalama yüksekliğidir.|

### <a name="guides-and-margins"></a>Kılavuzlar ve kenar boşlukları

Denetimleri taşıyor, denetim ekleme veya geçerli düzeni yeniden düzenleme, kılavuzlar ve kenar boşlukları, denetimleri bir iletişim kutusu içinde doğru bir şekilde hizalamanıza yardımcı olabilir.

Bir iletişim kutusu oluşturduğunuzda, kenar boşlukları olarak adlandırılan dört değiştirme Kılavuzu sağlanır ve mavi noktalı çizgiler olarak görünür.

- Kenar boşluklarını taşımak için kenar boşluğunu yeni konuma sürükleyin.

- Kenar boşluğunu ortadan kaldıralmak için, kenar boşluğunu sıfır bir konuma taşıyın.

- Kenar boşluğunu geri getirmek için, işaretçiyi kenar boşluğunun sıfır konumunun üzerine getirin ve kenar boşluğunu konuma taşıyın.

Kılavuzlar, düzenleyicide görüntülenen iletişim kutusunda ve **iletişim kutusu düzenleyicisinin**sol tarafında ve sol tarafındaki cetvellerdeki ilgili oklarda mavi noktalı çizgiler olarak görünür. Denetimlerin boyutlandırma tutamaçları denetimler taşındığında kılavuzlara yaslanırlar ve daha önce kılavuza daha önce bir denetim yoksa kılavuzlar denetimlere yaslanırlar. Bir kılavuz taşındığında, bu denetime eklenen denetimler de taşınır. Kılavuzlardan biri taşındığında birden fazla kılavuza yapışmış denetimler yeniden boyutlandırılır.

- Cetvel içinde bir kılavuz oluşturmak için bir kılavuz oluşturmak üzere bir kez seçin ya da kılavuz ayarlarını belirtebileceğiniz **Kılavuz ayarları** iletişim kutusunu başlatmak için çift tıklayın.

- İletişim kutusunda bir kılavuz ayarlamak için Kılavuzu seçin ve yeni bir konuma sürükleyin ya da ilişkili Kılavuzu sürüklemek için cetveldeki oku seçin.

   Kılavuzun koordinatları pencerenin alt kısmındaki durum çubuğunda ve cetvelde görüntülenir ya da kılavuzun tam konumunu göstermek için işaretçiyi cetveldeki okun üzerine taşıyın.

- Bir Kılavuzu silmek için Kılavuzu iletişim kutusunun dışına sürükleyin veya ilgili oku cetvelin dışına sürükleyin.

Cetvellerdeki değer çizgileri, kılavuz ve denetimlerin boşluklarını belirler iletişim kutusu birimleri (DLUs) tarafından tanımlanır. Bir DLU, iletişim kutusu yazı tipinin boyutunu temel alır, normalde 8 noktalı MS kabuğu DLG. Yatay bir DLU, iletişim kutusu yazı tipinin dört bölü ortalama genişliğidir. Dikey bir DLU, yazı tipinin 8 ' den bölünen ortalama yüksekliğidir.

- Değer çizgilerinin aralıklarını değiştirmek için menü **Biçim**  >  **Kılavuzu ayarları**' na gidin ve **kılavuz aralığı** alanında DLUS ' de yeni bir genişlik ve yükseklik belirleyin.

### <a name="layout-grid"></a>Düzen kılavuzu

Bir iletişim kutusuna denetimleri yerleştirirken veya düzenleme yaparken, daha kesin konumlandırma için Düzen kılavuzunu kullanın. Izgara açık olduğunda, denetimler, manyetik hale getirilme gibi kılavuzun noktalı çizgilere yaslamayı sağlar.

- Düzen Kılavuzunu açmak veya kapatmak için menü **biçimlendirme**  >  **Kılavuzu ayarları** ' na gidin ve **kılavuz** düğmesini seçin veya temizleyin.

   Kılavuzu, [Iletişim kutusu Düzenleyicisi araç çubuğundaki](./dialog-editor.md) **kılavuzu aç** düğmesini kullanarak, tek bir **iletişim kutusu Düzenleyicisi** penceresinde yine de denetleyebilirsiniz.

- Düzen kılavuzunun boyutunu değiştirmek için menü **Biçim**  >  **Kılavuzu ayarları** ' na gidin ve kılavuzdaki hücreler için DLUS yükseklik ve genişlik değerlerini yazın. En küçük yükseklik veya Genişlik 4 ' ün altında.

### <a name="disable-guides"></a>Kılavuzu devre dışı bırak

Kılavuzların yapışma efektini devre dışı bırakmak için fare ile birlikte özel anahtarlar kullanabilirsiniz. **Alt** tuşu kullanmak, kılavuzun yapışma etkilerinin seçili olduğunu devre dışı bırakır. Bir kılavuzun **SHIFT** tuşuyla taşınması, denetimsiz denetimlerin kılavuz ile taşınmasını önler.

- Kılavuzların yapışma efektini devre dışı bırakmak için, **alt** tuşunu basılı tutarken denetimi sürükleyin.

- Denetimleri, denetimsiz denetimleri taşımadan taşımak için **SHIFT** tuşunu basılı tutarken kılavuzu sürükleyin.

- Kılavuzlarını kapatmak için menü **biçimlendirme**  >  **Kılavuzu ayarları**' na gidin. Ardından, **Düzen kılavuzlarındaki** **hiçbiri**' ni seçin.

   > [!TIP]
   > Kısayol tuşlarını menü **biçimi**  >  **geçiş kılavuzlarındaki**de kullanabilirsiniz.

## <a name="select-controls"></a>Denetimleri Seç

Bunları boyutuna getirmek, hizalamak, taşımak, kopyalamak veya silmek için denetimler ' i seçin ve ardından istediğiniz işlemi doldurun. Çoğu durumda, [Iletişim kutusu Düzenleyici araç çubuğunda](./dialog-editor.md)boyutlandırma ve hizalama araçlarını kullanmak için birden fazla denetim seçmeniz gerekir.

Bir denetim seçildiğinde, düz (etkin) veya boş (etkin) boyutlandırma tutamaçları (seçim kenarlığında görünen küçük kareler) etrafında gölgeli bir kenarlığı vardır. Birden çok denetim seçildiğinde, baskın denetimin katı boyutlandırma tutamaçları ve tüm seçili denetimlerin boş boyutlandırma tutamaçları vardır.

- Denetimleri seçmek için [araç kutusu penceresinde](/visualstudio/ide/reference/toolbox) **işaretçi** aracını seçin ve seçiminizi yapmak için aşağıdaki adımlardan birini kullanın:

  - İletişim kutusunda seçmek istediğiniz denetimlerin çevresinde bir seçim kutusu çizmek için işaretçiyi sürükleyin. Fare düğmesini serbest bırakırsanız, seçim kutusu içindeki ve kesişmekte olan tüm denetimler seçilidir.

  - **SHIFT** tuşunu basılı tutarak seçime dahil etmek istediğiniz denetimleri seçin.

  - **CTRL** tuşunu basılı tutarak seçime dahil etmek istediğiniz denetimleri seçin.

- Seçili denetimler grubundan bir denetim eklemek veya kaldırmak için, **SHIFT** tuşunu basılı tutun ve eklemek veya kaldırmak istediğiniz denetimi seçin.

### <a name="dominant-controls"></a>Baskın denetimler

Birden çok denetimi boyutlandırdığınızda veya hizaladığınızda, **Iletişim kutusu Düzenleyicisi** diğer denetimlerin nasıl boyutlandırıldığını veya hizalandığını anlamak için baskın denetimi kullanır. Varsayılan olarak, baskın denetim, seçilen ilk denetimdir.

- Baskın denetimi belirtmek için **CTRL** tuşunu basılı tutun ve *önce*diğer denetimlerin boyutunu veya konumunu etkilemek için kullanmak istediğiniz denetimi seçin. **CTRL** tuşunu basılı tutarak ve seçim içinde bir denetim seçtiğinizde, bu denetimin bu seçimde de baskın denetim olması gerekir.

- Baskın denetimi değiştirmek için, seçili olan tüm denetimlerin dışında seçim yaparak geçerli seçimi temizleyin ve *önce*farklı bir denetim seçerek yukarıdaki yordamı tekrarlayın.

> [!NOTE]
> Baskın denetimin boyutlandırma tutamaçları, alt denetimlerin tutamaçları boş olduğu sürece Solid ' dir. Daha fazla yeniden boyutlandırma veya hizalama, baskın denetimi temel alır.

## <a name="size-controls"></a>Boyut denetimleri

Bir denetimi yeniden boyutlandırmak için boyutlandırma tutamaçlarını kullanın. İşaretçi bir boyutlandırma tutamacı üzerine konumlandırıldığında, denetimin yeniden boyutlandırılabileceği yönergeleri belirtmek için şekli değiştirir. Etkin boyutlandırma tutamaçları Solid ve boyutlandırma tutamacı boş ise, denetim bu eksen üzerinde yeniden boyutlandırılamaz.

- Bir denetimi boyutlandırmak için denetimi seçin ve boyutlandırma tutamaçlarını sürükleyerek boyutu değiştirin.

  - Üstteki ve kenarlarda bulunan boyut tutamaçları, yatay veya dikey boyutunu değiştirir.

  - Köşelerde bulunan boyut tutamaçları hem yatay hem de dikey boyutunu değiştirir.

   > [!TIP]
   > **Shift** tuşunu basılı tutarak ve **sağ** ve **aşağı** ok tuşlarını kullanarak bir iletişim kutusu birimini (dlu) tek seferde yeniden boyutlandırabilirsiniz.

- Bir denetimin içindeki metne sığması için otomatik olarak boyutunu belirlemek için, menü **biçimi** ' ne gidin veya denetime sağ tıklayın ve **içeriğe göre boyutlandır**' ı seçin.

- Denetimleri aynı boyutta yapmak için, yeniden boyutlandırmak istediğiniz denetimleri seçin ve menü **biçimi**  >  **aynı boyuta getir**' e gidip **her ikisi**, **Yükseklik**veya **Genişlik**' i seçin.

   Bir denetim grubunu, serinin ilk bölümünde seçilen denetim olan baskın denetimin boyutuna göre yeniden boyutlandırır. Gruptaki denetimlerin son boyutu, baskın denetimin boyutuna bağlıdır.

- Bir denetim grubunu kılavuzlarla boyutlandırma, denetimin bir tarafını (veya denetimleri) bir kılavuza Yaslama, ardından bir Kılavuzu denetimin diğer tarafına sürükleyin (veya denetimleri). Artık, denetimin (veya denetimlerin) boyutunu göstermek için iki kılavuzu da taşıyabilirsiniz.

   Birden çok denetim ile gerekirse, ikinci kılavuza yasla her biri için boyut.

### <a name="other-controls"></a>Diğer denetimler

İletişim kutusuna eklediğinizde bir açılan kutunun boyutunu değiştirebilirsiniz. Açılır liste kutusunun boyutunu da belirtebilirsiniz. Daha fazla bilgi için bkz. [Birleşik giriş kutusu denetimine değer ekleme](./defining-mnemonics-access-keys.md).

1. Birleşik giriş kutusunun sağ tarafındaki aşağı açılan ok düğmesini seçin.

   ![MFC projesindeki Birleşik giriş kutusunda bulunan ok](../mfc/media/vccomboboxarrow.gif "Vccomboboxok")

   Denetimin ana hattı, açılan liste alanı genişletilmiş olan Birleşik giriş kutusunun boyutunu gösterecek şekilde değişir.

1. Aşağı doğru boyutlandırma tutamacını kullanarak aşağı açılan liste alanının başlangıç boyutunu değiştirin.

   ![Bir MFC projesinde Birleşik giriş&#45;kutusu boyutlandırma](../mfc/media/vccomboboxsizing.gif "vccomboboxs")

1. Açılan kutunun aşağı açılan liste bölümünü kapatmak için açılır oku yeniden seçin.

> [!NOTE]
> MFC kullanarak bir iletişim kutusuna yatay kaydırma çubuğu içeren bir liste kutusu eklediğinizde, kaydırma çubuğu uygulamanızda otomatik olarak görünmez.
>
> Kodunuzda [Clienstbox:: SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) çağırarak en geniş öğe için bir maksimum genişlik ayarlayın. Bu değer kümesi olmadan, liste kutusundaki öğeler kutudan daha geniş olduğunda bile kaydırma çubuğu görünmez.

## <a name="align-controls"></a>Denetimleri hizalama

- Denetimleri hizalamak için, hizalamak istediğiniz denetimleri seçin. Menü **Biçimlendir**  >  **hizalı** öğesine gidin ve aşağıdaki hizalamalara birini seçin:

   |Hizalama|Açıklama|
   |-----|-----------|
   |**Hizala**|Seçili denetimleri sol taraflarıyla hizalar.|
   |**Merkeziyle**|Seçili denetimleri orta noktaları üzerinde yatay olarak hizalar.|
   |**Haklar**|Seçili denetimleri sağ taraflarıyla hizalar.|
   |**Arşivlerinizin başından**|Seçili denetimleri üst kenarları üzerinde hizalar.|
   |**Ortaları**|Seçili denetimleri orta noktaları üzerinde dikey olarak hizalar.|
   |**Alt kenarlar**|Seçili denetimleri alt kenarları üzerinde hizalar.|

   Önce baskın olmasını istediğiniz denetimi seçtiğinizden emin olun veya denetim grubunun son konumu baskın denetimin konumuna bağlı olarak hizalama veya boyutlandırma komutunu yürütmeden önce baskın denetim olarak ayarlayın.

- Denetimleri eşit aralıklı olarak belirlemek için yeniden düzenlemek istediğiniz denetimleri seçin. Menü **Biçimlendir**  >  **boşluk** ' a gidin ve aşağıdaki Aralık hizalamalarının birini seçin:

   |Aralık|Açıklama|
   |---|---|
   |**Yönlendirilmesine**|Sol ve en sağdaki denetimin seçildiği boşluk denetimleri.|
   |**Aşağı**|Boşluk denetimleri, en üstteki ve en altta bulunan denetim arasında eşit olarak seçilir.|

- Denetimleri ortalamak için, yeniden düzenlemek istediğiniz denetimi veya denetimleri seçin. İletişim kutusunda menü **Biçim**  >  **Merkezi** ' ne gidin ve aşağıdaki düzenlemeden birini seçin:

   |Sidir|Açıklama|
   |---|---|
   |**Dikey**|İletişim kutusunda denetimleri dikey olarak ortalayın.|
   |**Yatay**|İletişim kutusunda denetimleri yatay olarak ortalayın.|

- Basma düğmelerini hizalamak için bir veya daha fazla gönderme düğmesi seçin. Menü **biçimlendirme**  >  **Düzenle düğmelerine**gidin ve aşağıdaki düzenlemelerin birini seçin:

   |Sidir|Açıklama|
   |---|---|
   |**Right**|İletişim kutusunun sağ kenarında basma düğmelerini hizalar.|
   |**Aşağıya**|İletişim kutusunun alt kenarı üzerinde basma düğmelerini hizalar.|

   Bir Gönder düğmesi dışında bir denetim seçerseniz, konumu etkilenmez.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Iletişim kutusu denetimlerini Yönet](controls-in-dialog-boxes.md)<br/>
[Nasıl yapılır: denetimleri ekleme, düzenleme veya silme](adding-editing-or-deleting-controls.md)<br/>
[Nasıl yapılır: denetim erişimini ve değerlerini tanımlama](defining-mnemonics-access-keys.md)<br/>
