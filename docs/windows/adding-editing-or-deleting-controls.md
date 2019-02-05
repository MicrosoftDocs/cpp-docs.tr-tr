---
title: Denetimleri Ekleme, Düzenleme veya Silme
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.dialog
- vc.controls.activex
- vc.editors.dialog.insertActiveXControls
helpviewer_keywords:
- Dialog Editor [C++], creating controls
- dialog boxes [C++], adding controls to
- Toolbox [C++], Dialog Editor tab
- controls [C++], types
- syslink controls in dialog boxes
- custom controls [C++], dialog boxes
- controls [C++], standard
- Dialog Editor [C++], creating controls
- controls [C++], adding to dialog boxes
- controls [C++], adding multiple
- dialog box controls [C++], size
- controls [C++], sizing
- dialog boxes [C++], adding ActiveX controls
- ActiveX controls [C++], adding to dialog boxes
- Insert ActiveX Control dialog box [C++]
- controls [C++], editing properties
- ActiveX controls [C++], properties
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls [C++], editing properties
- dialog box controls [C++], deleting
- controls [C++], deleting
- Dialog Editor [C++], default control events
- controls [C++], default control events
- events [C++], controls
- dialog box controls [C++], events
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog Editor [C++], defining member variables for controls
ms.assetid: 73cef03f-5c8c-456a-87d1-1458dff185cf
ms.openlocfilehash: b4edb5b7a51e4f6d368759ebc2e05a1cc585f19a
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742758"
---
# <a name="adding-editing-or-deleting-controls"></a>Denetimleri Ekleme, Düzenleme veya Silme

Kullanarak **iletişim** Düzenleyicisi, yeniden boyutlandırma ekleyebilir, düzenleme ve silme iletişim kutularındaki denetimler. Ayrıca kendi kimliği gibi bir denetimin özelliklerini düzenleyebilir ya da çalışma zamanında başlangıçta görünür olup.

**İletişim kutusu Düzenleyicisi** sekme görünür [araç penceresi](/visualstudio/ide/reference/toolbox) çalışırken **iletişim** Düzenleyici. Ayrıca özelleştirebilirsiniz **araç kutusu** penceresi daha kolay kullanım için. Daha fazla bilgi için [araç kutusunu kullanma](/visualstudio/ide/using-the-toolbox) ve [göster veya gizle Araç kutusu penceresini](showing-or-hiding-the-dialog-editor-toolbar.md).

Kısayol menüsünde kullanabileceğiniz **iletişim** Düzenleyicisi hızlı bir şekilde eklemek için kayıtlı bir iletişim kutusuna ActiveX denetimleri ve ActiveX denetimlerine ekleyebilirsiniz **araç kutusu** hızlı erişim için.

Kullanılabilir standart denetimler **araç kutusu** varsayılan olaylar şunlardır:

|Denetim adı|Varsayılan olay|
|---|---|
|[Düğme denetimi](../mfc/reference/cbutton-class.md)|BN_CLICKED|
|[Onay kutusu denetimi](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[Birleşik giriş kutusu denetimi](../mfc/reference/ccombobox-class.md)|CBN_SELCHANGE|
|[Düzenleme denetimi](../mfc/reference/cedit-class.md)|EN_CHANGE|
|Grup kutusu|(Uygulanamaz)|
|[Liste kutusu denetimi](../mfc/reference/clistbox-class.md)|LBN_SELCHANGE|
|[Radyo düğmesi denetimini](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[Statik metin denetimi](../mfc/reference/cstatic-class.md)|(Uygulanamaz)|
|[Resim denetimi](../mfc/reference/cpictureholder-class.md)|(Uygulanamaz)|
|[Zengin düzenleme 2.0 denetimi](../mfc/using-cricheditctrl.md)|EN_CHANGE|
|[Kaydırma çubuğu denetimi](../mfc/reference/cscrollbar-class.md)|NM_THEMECHANGED|

Kullanma hakkında daha fazla bilgi için **RichEdit 1.0** MFC ile denetlemek için bkz: [MFC ile RichEdit 1.0 denetimini kullanma](../windows/using-the-richedit-1-0-control-with-mfc.md) ve [zengin düzenleme denetimine örnekler](../mfc/rich-edit-control-examples.md).

[Windows ortak denetimleri](../mfc/controls-mfc.md) bulunan **araç kutusu** uygulamanızdaki işlevsellik sağlar. Bunlara aşağıdakiler dahildir:

|Denetim adı|Varsayılan olay|
|---|---|
|[Kaydırıcı denetimi](../mfc/slider-control-styles.md)|NM_CUSTOMDRAW|
|[Döndürme denetimi](../mfc/using-cspinbuttonctrl.md)|UDN_DELTAPOS|
|[İlerleme denetimi](../mfc/styles-for-the-progress-control.md)|NM_CUSTOMDRAW|
|[Sık kullanılan anahtarı denetimi](../mfc/using-a-hot-key-control.md)|NM_OUTOFMEMORY|
|[Liste denetimi](../mfc/list-control-and-list-view.md)|LVN_ITEMCHANGE|
|[Ağaç denetimi](../mfc/tree-control-styles.md)|TVN_SELCHANGE|
|[Sekme denetimi](../mfc/tab-controls-and-property-sheets.md)|TCN_SELCHANGE|
|[Animasyon denetimi](../mfc/using-an-animation-control.md)|ACN_START|
|[Tarih Saat Seçici denetimi](../mfc/creating-the-date-and-time-picker-control.md)|DTN_DATETIMECHANGE|
|[Ay takvim denetimi](../mfc/month-calendar-control-examples.md)|MCN_SELCHANGE|
|[IP adresi denetimi](../mfc/reference/cipaddressctrl-class.md)|IPN_FIELDCHANGED|
|[Genişletilmiş Birleşik giriş kutusu denetimi](../mfc/creating-an-extended-combo-box-control.md)||
|[Özel Denetim](custom-controls-in-the-dialog-editor.md)|TTN_GETDISPINFO|

Daha fazla bilgi için [denetim sınıfları](../mfc/control-classes.md), [iletişim kutusu sınıfları](../mfc/dialog-box-classes.md), ve [kaydırma çubuğu stilleri](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="to-add-a-control"></a>Bir denetim eklemek için

Yeni, iletişim kutusuna denetimler ekleme, denetimleri sürükleyin **araç kutusu** oluşturduğunuz iletişim kutusu. Ardından, denetimleri yerleri veya kendi boyutu ve şekli değiştirin.

Seçerek iletişim kutusuna özel denetimleri ekleyebilirsiniz **özel denetim** simgesini **araç kutusu** ve, iletişim kutusuna sürükleyerek. Eklemek için bir **Syslink** denetimi, bir özel denetim eklemek ve ardından denetimin değiştirme **sınıfı** özelliğini **Syslink**. Bu eylem yenileyin ve göstermek için özellikleri neden olacak **Syslink** denetim özellikleri. MFC sarmalayıcı sınıfı hakkında daha fazla bilgi için bkz. [CLinkCtrl](../mfc/reference/clinkctrl-class.md).

### <a name="to-add-a-control-to-a-dialog-box"></a>İletişim kutusuna denetim ekleme

1. Sekmeli pencere iletişim kutusu Düzenleyicisi çerçeveyi geçerli belgede olduğundan emin olun. Bir iletişim kutusu geçerli belge değilse göremezsiniz **iletişim kutusu Düzenleyicisi sekmesi** içinde **araç kutusu**.

1. Üzerinde **iletişim kutusu Düzenleyicisi** sekmesinde **araç kutusu** penceresi, ardından istediğiniz denetimi seçin:

   İletişim kutusunu denetimi yerleştirmek istediğiniz yeri seçin. Burada seçtiğiniz denetimi görünür.

   \- veya -

   Sürükle ve bırak denetiminden **araç kutusu** pencere, iletişim kutusu konumuna.

   \- veya -

   Denetimde çift **araç kutusu** penceresi (iletişim kutusunda görünür) sonra denetim tercih ettiğiniz bir konuma yeniden konumlandırma.

### <a name="to-add-multiple-controls"></a>Birden çok denetim eklemek için

1. Tutarken **Ctrl** anahtar, bir denetimi seçin **araç kutusu** penceresi.

1. Yayın **Ctrl** anahtar ve birçok kez olarak özel denetim eklemek istediğiniz gibi iletişim kutusunu seçin.

1. Tuşuna **Esc** denetimleri yerleştirme durdurmak için.

### <a name="to-size-a-control-while-you-add-it"></a>Eklerken denetimi bir boyutu

1. Bir denetimi seçin **araç kutusu** penceresi.

1. (Bu çizgileri gibi çapraz görünür) imlecinizi yeni denetim, iletişim kutusunda sol üst köşesindeki istediğiniz konuma yerleştirin.

1. Seçin ve iletişim kutusunda, denetimin sol üst köşesinin bağlantı için fare düğmesini basılı tutun ve imleci denetimin istediğiniz boyuta kadar sağa ve aşağı sürükleyin.

   > [!NOTE]
   > Aslında, çizim denetimi dört köşelerini hiçbirini kenarına bağlanabilir. Bu yordam üst sol löşede örnek olarak kullanılır.

1. Fare düğmesini bırakın. İletişim kutusunda, belirtilen boyut üzerine denetimini kapatır.

   > [!TIP]
   > İletişim kutusuna boyutlandırma kenarlığı denetimin taşıyarak bırakmadan sonra denetimi yeniden boyutlandırabilirsiniz. Daha fazla bilgi için [tek denetimleri boyutlandırma](../windows/sizing-individual-controls.md).

### <a name="to-add-an-activex-control"></a>ActiveX denetimi eklemek için

Visual Studio, iletişim kutusuna ActiveX denetimleri eklemenize olanak tanır. Daha fazla bilgi için [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md) ve [ActiveX denetim kapsayıcıları](../mfc/activex-control-containers.md).

**ActiveX denetimi Ekle** iletişim kutusu kullanırken, iletişim kutusuna ActiveX denetimleri eklemenize olanak sağlayan [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md). Bu iletişim kutusunda, aşağıdaki özellikleri içerir:

|Özellik|Açıklama|
|---|---|
|**ActiveX denetimi**|ActiveX denetimleri listesini görüntüler. Bu iletişim kutusundan bir denetim ekleme, bir sarmalayıcı sınıfı oluşturmaz. Sarmalayıcı sınıf ihtiyacınız varsa, [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code) oluşturmak için (daha fazla bilgi için [sınıf ekleme](../ide/adding-a-class-visual-cpp.md)). Bu iletişim kutusunda bir ActiveX denetimi görünmüyorsa, satıcının yönergelerine göre denetim yükleme deneyin.|
|**Yolu**|ActiveX denetimi içinde bulunan dosyayı görüntüler.|

#### <a name="to-see-the-activex-controls-available"></a>ActiveX denetimlerini görmek için

1. Bir iletişim kutusu, iletişim kutusu Düzenleyicisi'nde açın.

1. Herhangi bir iletişim kutusunun gövdesinde sağ tıklayın.

1. Kısayol menüsünde **ActiveX denetimi Ekle**.

   **ActiveX denetimi Ekle** iletişim kutusu görüntülenirse, sisteminizdeki tüm ActiveX denetimlerini gösterme. ActiveX denetimi dosyasının yolu iletişim kutusunun en altında görünür.

#### <a name="to-add-an-activex-control-to-a-dialog-box"></a>İletişim kutusuna ActiveX denetimi eklemek için

1. İçinde **ActiveX denetimi Ekle** iletişim kutusunda, istediğiniz, iletişim kutusuna ekleyin ve denetimi seçin **Tamam**.

   Denetim, düzenlemek veya başka bir denetimde olduğu gibi işleyicileri için oluşturma iletişim kutusunda görüntülenir.

   > [!NOTE]
   > ActiveX denetimlerine ekleyebilirsiniz **araç kutusu** penceresi kolay erişim için.

   > [!CAUTION]
   > ActiveX denetimleri, sisteminizdeki tüm dağıtmak için geçerli olmayabilir. Lütfen denetimleri yüklü yazılımlar için lisans sözleşmesi bakın veya yazılım şirketine başvurun.

## <a name="to-edit-a-control"></a>Bir denetim düzenlemek için

### <a name="to-edit-the-properties-of-a-control-or-controls"></a>Bir denetim veya denetimlerin özelliklerini düzenlemek için

1. İletişim kutusunda, değiştirmek istediğiniz denetimi seçin.

   > [!NOTE]
   > Birden çok denetim seçerseniz yalnızca seçili denetimleri ortak özelliklerini düzenleyebilirsiniz.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), denetim özelliklerini değiştirin.

   > [!NOTE]
   > Ayarladığınızda **bit eşlem** özelliği için bir düğme, radyo düğmesinin veya onay kutusu denetimi eşit **True**, bs_bıtmap denetim için uygulanan stili. Daha fazla bilgi için [düğme stilleri](../mfc/reference/styles-used-by-mfc.md#button-styles). Bir bit eşlem bir denetimle ilişkilendirme ilişkin bir örnek için bkz [CButton::SetBitmap](../mfc/reference/cbutton-class.md#setbitmap). Bit eşlemler içerikteyken denetiminizi görünmez **iletişim** Kaynak Düzenleyicisi.

### <a name="to-undo-changes-to-the-properties-of-a-control"></a>Bir denetimin özelliklerini değişiklikleri geri almak için

1. Denetim odağa sahip olduğundan emin olun **iletişim** Düzenleyici.

1. Seçin **geri** gelen **Düzenle** menü (odak denetimde değilse **geri** komutu kullanılamaz).

### <a name="to-edit-properties-for-an-activex-control"></a>ActiveX denetimi özelliklerini düzenlemek için

ActiveX denetimleri bağımsız satıcıları tarafından sağlanan kendi özellikleri ve özellikleri ile donatıldı gelebilir. ActiveX denetimleri için özellikleri görüntülenir **özellikleri** penceresi. ActiveX denetiminin yazarlar tarafından oluşturulan tüm özellik sayfaları da görüntülenir **özellikler sayfaları** iletişim kutusu (görüntülemek için **özellik sayfası** belirlibirActiveXdenetiminetıklayın**Özellik sayfası** düğmesine [Özellikler penceresi](/visualstudio/ide/reference/properties-window)).

Çeşitli sekmelere ActiveX denetiminin bir parçası olarak gelen özellik sayfalarını bağlı olarak bir ActiveX denetimi için özellik sayfası görüntülenir.

> [!NOTE]
> Aşağıdaki yordam, özellik sayfasını kullanarak ActiveX denetimlerini düzenlemek için geçerlidir. Ayrıca göz atabilir ve ActiveX özellikleri yeni Düzenle **özellikleri** penceresi.

1. Seçin **ActiveX** denetimi.

1. Üzerinde **görünümü** menüsünde **özellik sayfası** ve özelliklerini görüntüleyin.

1. Özellik sayfasında gerekli değişiklikleri yapın.

### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>(Düğme olmayan) iletişim kutusu denetimi için bir üye değişkeni tanımlamak için

Düğmeleri dışında herhangi bir iletişim kutusu denetimi için bir üye değişkeni tanımlamak için aşağıdaki yöntemi kullanabilirsiniz.

> [!NOTE]
> Bu işlem yalnızca bir MFC projesi içinde iletişim kutusu denetimleri için geçerlidir. ATL projeleri kullanması gereken **yeni Windows iletileri ve olay işleyicileri** iletişim kutusu. Daha fazla bilgi için [ileti türlerini kullanıcı arabirimi nesneleri ile ilişkili](../mfc/reference/message-types-associated-with-user-interface-objects.md), [ileti işleyicisini düzenleme](../mfc/reference/editing-a-message-handler.md), ve [için yansıtılan iletiiletiişleyicisitanımlama](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md).

1. İçinde [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md), bir denetim seçin.

1. Tuşlarına basarak çalışırken **Ctrl** anahtar, iletişim kutusu denetimini çift tıklayın.

   [Üye değişkeni Ekleme Sihirbazı'nı](../ide/add-member-variable-wizard.md) görünür.

1. İlgili bilgileri yazın **üye değişkeni ekleme** Sihirbazı. Daha fazla bilgi için [iletişim kutusu veri değişimi](../mfc/dialog-data-exchange.md).

1. Seçin **Tamam** dönmek için **iletişim** Düzenleyici.

   > [!TIP]
   > Herhangi bir iletişim kutusu denetiminden mevcut işleyicisine atlamak için denetimi çift tıklatın.

Ayrıca **üye değişkenleri** sekmesinde [MFC Sınıf Sihirbazı](../mfc/reference/mfc-class-wizard.md) belirli bir sınıf için yeni üye değişkenlerini ekleyin ve önceden tanımlanmış üye değişkenlerine görüntüleyin.

## <a name="to-delete-a-control"></a>Bir denetim silinemedi

İletişim kutusunda, Denetim ve ENTER tuşuna seçin **Sil** anahtarı.

   \- veya -

Üzerinde **Düzenle** menüsünde **Sil**.

   > [!TIP]
   > Kullanırken **iletişim** düzenleyicisinde birçok örneği, sık kullanılan komutlar kısayol menüsünü görüntülemek için sağ fare düğmesine tıklayabilirsiniz.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutularındaki Denetimler](controls-in-dialog-boxes.md)<br/>
[İletişim Kutusu Denetimleri ve Değişken Türleri](../ide/dialog-box-controls-and-variable-types.md)<br/>
[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>

<!-- excluded links
[Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md)<br/>
[Adding Functionality with Code Wizards](../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Adding a Class](../ide/adding-a-class-visual-cpp.md)<br/>
[Adding a Member Function](../ide/adding-a-member-function-visual-cpp.md)<br/>
[Adding a Member Variable](../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Overriding a Virtual Function](../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Message Handler](../mfc/reference/adding-an-mfc-message-handler.md)
[Declaring a Variable Based on Your New Control Class](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)<br/>
-->
