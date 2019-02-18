---
title: Erişimi denetlemek ve değerleri tanımlama
ms.date: 02/15/2019
f1_keywords:
- vc.editors.dialog.combo
helpviewer_keywords:
- access keys [C++], adding
- keyboard shortcuts [C++], controls
- dialog box controls [C++], mnemonics
- access keys [C++], checking
- mnemonics [C++], checking for duplicate
- mnemonics
- mnemonics [C++], dialog box controls
- keyboard shortcuts [C++], uniqueness checking
- Check Mnemonics command
- controls [C++], access keys
- access keys [C++]
- combo boxes [C++], Data property
- controls [C++], testing values in combo boxes
- combo boxes [C++], adding values
- combo boxes [C++], previewing values
- Data property
- combo boxes [C++], testing values
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
ms.openlocfilehash: 20319cd08d6d1e77faef1275e63bf3ffd354356b
ms.sourcegitcommit: 24592ba0a38c7c996ffd3d55fe1024231a59ccc2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/18/2019
ms.locfileid: "56336494"
---
# <a name="defining-control-access-and-values"></a>Erişimi denetlemek ve değerleri tanımlama

## <a name="change-the-tab-order-of-controls"></a>Denetimlerin sekme sırasını değiştirme

Sekme sırasını sırayı olan **sekmesini** anahtarı bir iletişim kutusu içindeki bir denetimden giriş odağını taşır. Genellikle sekme sırası, soldan sağa ve yukarıdan bir iletişim kutusunda devam eder. Her denetimin bir **sekme durağı** özelliği bir denetimin Girintiyi alıp almayacağını belirler.

### <a name="to-set-input-focus-for-a-control"></a>Bir denetim için giriş odağı ayarlamak için

İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window)seçin **True** veya **False** içinde **sekme durağı** özelliği.

Yoksa bile denetimleri **sekme durağı** özelliğini **True** sekme sırasını bir parçası olmanız gerekir. Sekme sırası önemlidir, örneğin, size [erişim tuşları (anımsatıcıları) tanımlamak](../windows/defining-mnemonics-access-keys.md) açıklamalı alt yazılar olmayan denetimler için. İlişkili bir denetim için bir erişim anahtarı içeren statik metin ilgili denetimin sekme sırasında hemen önce gelmelidir.

> [!NOTE]
> Sekme sırasını değiştirme, iletişim kutusu örtüşen denetimler içeriyorsa, denetimleri görüntülenme şeklini değiştirebilir. Daha sonra sekme sırasının gelen denetimler, her zaman sekme sırasının kendilerinden herhangi bir çakışan denetim üzerinde görüntülenir.

### <a name="to-view-the-current-tab-order-for-all-controls-in-a-dialog-box"></a>Geçerli sekme sırasını tüm denetimleri için iletişim kutusunda görüntülemek için

Git **biçimi** menü ve select **sekme sırasını**, veya basın **Ctrl** + **D**.

### <a name="to-change-the-tab-order-for-all-controls-in-a-dialog-box"></a>İletişim kutusundaki tüm denetimlerin sekme sırasını değiştirmek için

1. Üzerinde **biçimi** menüsünde **sekme sırasını**.

   Her denetimin sol üst köşedeki birkaç onun yerine geçerli sekme sırasının gösterir.

1. İstediğiniz sırayla her denetimi seçerek sekme sırasını ayarlama **sekmesini** izlemek için anahtar.

1. Tuşuna **Enter** çıkmak için **sekme sırasını** modu.

   > [!TIP]
   > Girdiğiniz sonra **sekme sırasını** modu basabilirsiniz **Esc** veya **Enter** sekme sırasını değiştirme özelliği devre dışı bırakmak için.

### <a name="to-change-the-tab-order-for-two-or-more-controls"></a>İki veya daha fazla denetim için sekmesinde sırasını değiştirmek için

1. Gelen **biçimi** menüsünde seçin **sekme sırasını**.

1. Sırayla değişikliğin nerede başlayacağını belirtin. İlk basılı **Ctrl** anahtar ve Denetim seçin ve ardından başlamak için değiştirilen sırasını istediğiniz yeri seçin.

   Örneğin, denetimlerin sırasını değiştirmek istiyorsanız `7` aracılığıyla `9`, basılı **Ctrl**, sonra kumanda `6` ilk.

   > [!NOTE]
   > Belirli bir denetim numarası için ayarlamak için `1` (ilk sekme sırasında), denetimi çift tıklatın.

1. Yayın **Ctrl** anahtar ve ardından istediğiniz sırayla denetimleri seçin **sekmesini** o noktadan itibaren izlemek için anahtar.

1. Tuşuna **Enter** çıkmak için **sekme sırasını** modu.

## <a name="define-mnemonics-access-keys"></a>Anımsatıcıları (erişim tuşları) tanımlayın

Normalde, klavye kullanıcıları içeren bir iletişim kutusu alanındaki başka bir denetimden giriş odağı Taşı **sekmesini** ve **ok** anahtarları. Ancak, tek bir tuşa basarak bir denetim seçmelerini sağlar bir erişim anahtarı (bir anımsatıcı ya da unutmayacağınızdan kolay ad) tanımlayabilirsiniz.

### <a name="to-define-an-access-key-for-a-control-with-a-visible-caption-push-buttons-check-boxes-and-radio-buttons"></a>Bir denetimin görünür başlığı (düğmeler, onay kutularını ve radyo düğmeleri) olan bir erişim tuşunu tanımlamak için

1. İletişim kutusunda bir denetimi seçin.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), **açıklamalı alt yazı** özelliği, ve işareti yazarak denetim için yeni bir ad yazın (`&`) Bu denetim için erişim anahtarı olarak istediğiniz harfi önünde. Örneğin: `&Radio1`

1. Tuşuna **girin**.

   Örneğin, erişim anahtarı belirtmek için görüntülenen resim bir çizgi görünür **R**adio1.

### <a name="to-define-an-access-key-for-a-control-without-a-visible-caption"></a>Resim yazısı görünür olmayan bir denetim için bir erişim tuşunu tanımlamak için

1. Denetim için bir başlık kullanarak yapmak bir **statik metin** denetim [araç kutusu](/visualstudio/ide/reference/toolbox).

1. Statik metin başlığı ve işareti yazın (`&`) erişim anahtarı olarak istediğiniz harfi önünde.

1. Statik metin denetimi sekme sırasının etiket denetimi karaktere emin olun.

> [!NOTE]
> Bir iletişim kutusu içindeki tüm erişim anahtarları benzersiz olmalıdır. Yinelenen erişim tuşları denetlemek için Git **biçimi** menü ve select **anımsatıcıları kontrol**.

## <a name="combo-box-values"></a>Birleşik giriş kutusu değerleri

Sahip olduğunuz sürece bir birleşik giriş kutusu denetimine değer ekleyebilirsiniz **iletişim** Düzenleyicisi'ni açın.

> [!TIP]
> Açılan kutu tüm değerler eklemek için iyi bir fikirdir *önce* kutuya boyut **iletişim** Düzenleyicisi veya birleşik giriş denetiminde görüntülenecek metin kesin.

### <a name="to-enter-values-into-a-combo-box-control"></a>Bir birleşik giriş kutusu denetimine değer girmek için

1. Birleşik giriş kutusu denetimi seçerek seçin.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), ekranı aşağı kaydırarak **veri** özelliği.

   > [!NOTE]
   > Türüne göre gruplandırılmış bir özellikler görüntülüyorsanız **veri** görünür **çeşitli** özellikleri.

1. Değer alanı için seçin **veri** özelliği ve türü, veri değerleri noktalı virgülle ayrılmış.

   > [!NOTE]
   > Aşağı açılan listesinde alfabetik hale getirme ile alanları müdahale çünkü değerleri arasında boşluk yerleştirmeyin.

1. Tuşuna **Enter** değerleri eklemeyi tamamladığınızda.

Bir açılan kutunun açılır bölümünü genişleterek hakkında daha fazla bilgi için bkz: [birleşik giriş kutusu ve kendi aşağı açılan listesinin boyutunu ayarlama](setting-the-size-of-the-combo-box-and-its-drop-down-list.md).

> [!NOTE]
> Bu yordamı kullanarak Win32 projeleri için değerleri eklenemiyor ( **veri** özelliği gri Win32 projeleri için). Win32 projeleri bu özelliği eklemek kitaplıkları olmadığı için değerleri bir Win32 projesi içeren bir birleşik giriş kutusu için programlı olarak eklemeniz gerekir.

### <a name="to-test-the-appearance-of-values-in-a-combo-box"></a>Açılan kutuda değerleri görünümünü test etmek için

Değerleri girdikten sonra **veri** özelliği, select **Test** düğmesini [iletişim kutusu araç çubuğunu](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

   Tüm değer listede aşağı kaydırma deneyin. Değerlerin göründüğü içinde tam olarak yazdığınız şekilde **veri** özelliğinde **özellikleri** penceresi. Yazım denetimi veya büyük/küçük harf denetimi yoktur.

   Tuşuna **Esc** dönmek için **iletişim kutusu** Düzenleyici.

   Şimdi, kodunuzun hangi radyo düğmesini seçili görünmesi gerektiğini belirten değiştirebilirsiniz. Örneğin, `m_radioBox1 = 0;` gruptaki ilk radyo düğmesini seçer.
Şimdi, kodunuzun hangi radyo düğmesini seçili görünmesi gerektiğini belirten değiştirebilirsiniz. Örneğin, `m_radioBox1 = 0;` gruptaki ilk radyo düğmesini seçer.

## <a name="radio-button-values"></a>Radyo düğmesi değerleri

Radyo düğmeleri iletişim kutusuna eklediğinizde, bunları bir grup olarak ayarlayarak ele almanız bir **grubu** özelliğinde **özellikleri** gruptaki ilk düğmenin penceresi. Denetim Kimliği bu radyo düğmesi için daha sonra yer [üye değişkeni Ekleme Sihirbazı'nı](../ide/add-member-variable-wizard.md), radyo düğmesi grubunu için bir üye değişkeni ekleme etmenize imkan sağlar.

İletişim kutusundaki radyo düğmelerini birden fazla grup olabilir. Aşağıdaki yordamı kullanarak her bir grup ekleyin.

### <a name="to-add-a-group-of-radio-buttons-to-a-dialog-box"></a>Bir iletişim kutusu için bir grup radyo düğmeleri eklemek için

1. Radyo düğmesi denetiminde seçme [araç penceresi](/visualstudio/ide/reference/toolbox) ve konumu iletişim kutusuna denetim yerleştirileceği yeri seçin.

1. Gereksinim duyduğunuz kadar çok radyo düğmeleri eklemek için yukarıdaki adımı yineleyin. Radyo düğmesi grubunda sekme sırasının ardışık olduğundan emin olun.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window)ayarlayın **grubu** özelliği *ilk* radyo düğmesi için sekmesinde sırayla **True**.

   Değiştirme **grubu** özelliğini **True** WS_GROUP stili kaynak betiği iletişim nesnesinin düğmenin girişi ekler ve birden fazla radyo düğmesini seçerek bir zamanında kullanıcı engeller (kullanıcı seçer bir radyo düğmesi grubundaki diğer temizlendiğinde) düğmesi grubunda.

   > [!NOTE]
   > Yalnızca ilk radyo düğmesi grubunda olmalıdır **grubu** özelliğini **True**. Düğmesi grubunun parçası olmayan ek denetimleri varsa Ayarla **grubu** ilk denetiminin özelliği *grubun dışına olan* için **True** de. İlk denetim grubu dışında kullanarak hızlıca tanımlayabilirsiniz **Ctrl**+**D** sekme sırasını görüntülemek için.

### <a name="to-add-a-member-variable-for-the-radio-button-group"></a>Radyo düğmesi grubunda için üye değişkeni eklemek için

1. Sekme sırasında ilk radyo düğmesi denetimini sağ tıklayın (baskın denetimi ve bir **grubu** özelliğini **True**) seçip **değişken Ekle** gelen kısayol menüsü.

1. İçinde [üye değişkeni Ekleme Sihirbazı'nı](../ide/add-member-variable-wizard.md)seçin **denetim değişkeni** onay kutusunu işaretleyin ve ardından **değer** radyo düğmesi.

1. İçinde **değişken adı** yeni bir üye değişkeni için bir ad yazın.

1. İçinde **değişken türü** liste kutusu, select **int** veya türü *int*.

   Şimdi, kodunuzun hangi radyo düğmesini seçili görünmesi gerektiğini belirten değiştirebilirsiniz. Örneğin, `m_radioBox1 = 0;` gruptaki ilk radyo düğmesini seçer.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[Denetimler](../mfc/controls-mfc.md)