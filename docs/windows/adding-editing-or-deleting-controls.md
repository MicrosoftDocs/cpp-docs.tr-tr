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
- controls [C++], troubleshooting
- Dialog Editor [C++], troubleshooting
- dialog boxes [C++], troubleshooting
- InitCommonControls
- RichEdit 1.0 control
- rich edit controls [C++], RichEdit 1.0
ms.assetid: 73cef03f-5c8c-456a-87d1-1458dff185cf
ms.openlocfilehash: 648ac3329409ba221881f75eaa51e1779091b0f0
ms.sourcegitcommit: eb2b34a24e6edafb727e87b138499fa8945f981e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2019
ms.locfileid: "56264874"
---
# <a name="adding-editing-or-deleting-controls"></a>Denetimleri Ekleme, Düzenleme veya Silme

Kullanarak **iletişim** Düzenleyicisi, yeniden boyutlandırma ekleyebilir, düzenleme ve silme iletişim kutularındaki denetimler. Ayrıca kendi kimliği gibi bir denetimin özelliklerini düzenleyebilir ya da çalışma zamanında başlangıçta görünür olup.

**İletişim kutusu Düzenleyicisi** sekme görünür [araç penceresi](/visualstudio/ide/reference/toolbox) çalışırken **iletişim** Düzenleyici. Ayrıca özelleştirebilirsiniz **araç kutusu** penceresi daha kolay kullanım için. Daha fazla bilgi için [araç kutusunu kullanma](/visualstudio/ide/using-the-toolbox) ve [göster veya gizle Araç kutusu penceresini](showing-or-hiding-the-dialog-editor-toolbar.md).

Kısayol menüsünde kullanabileceğiniz **iletişim** Düzenleyicisi hızlı bir şekilde eklemek için kayıtlı bir iletişim kutusuna ActiveX denetimleri ve ActiveX denetimlerine ekleyebilirsiniz **araç kutusu** hızlı erişim için.

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

## <a name="known-issue"></a>Bilinen sorun

Bir iletişim kutusu için bir ortak denetimi veya zengin düzenleme denetimi ekledikten sonra iletişim kutusunu test ya da iletişim görünmez görünmez.

Sorunun bir örnek görmek için:

1. Bir Windows uygulaması (konsol uygulaması değil) oluşturmak için uygulama ayarları değiştirme bir Win32 projesi oluşturun.

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasına çift tıklayın.

1. İletişim seçeneği altında çift **hakkında** kutusu.

1. Ekleme bir **IP adresi denetimi** iletişim kutusu.

1. Kaydet ve **tümünü yeniden derle**.

1. Programı çalıştırın.

1. İletişim kutusunun üzerinde **yardımcı** menüsünde tıklatın **hakkında** komut; hiçbir iletişim kutusu görüntülenir.

Şu anda **iletişim** Düzenleyicisi değil otomatik olarak Ekle kod projenize aşağıdaki ortak denetimleri sürükleyip veya zengin düzenleme denetimleri üzerine bir iletişim kutusu. Ya da bu sorun ortaya çıktığında, Visual Studio bir hata veya uyarı sağlar. Sorunu gidermek için el ile denetim için kod ekleyin.

||||
|-|-|-|
|Kaydırıcı denetimi|Ağaç denetimi|Tarih Saat Seçici|
|Döndürme denetimi|Sekme denetimi|Aylık takvim|
|İlerleme denetimi|Animasyon denetimi|IP adresi denetimi|
|Kısayol tuşu|Zengin düzenleme denetimi|Genişletilmiş Birleşik giriş kutusu|
|Liste denetimi|Zengin düzenleme 2.0 denetimi|Özel Denetim|

İletişim kutusunda ortak denetimleri kullanmak için çağrı gerekir [InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex) veya `AFXInitCommonControls` iletişim kutusu oluşturmadan önce.

RichEdit denetimleri kullanmak için çağırmalıdır `LoadLibrary`. Daha fazla bilgi için [hakkında zengin düzenleme denetimleri](/windows/desktop/Controls/about-rich-edit-controls) Windows SDK ve [zengin düzenleme denetimine genel bakış](../mfc/overview-of-the-rich-edit-control.md).

> [!NOTE]
> MFC ile RichEdit denetimini kullanmak için öncelikle çağırmalısınız [Afxınitrichedit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) RichEdit 2.0 denetimi (RICHED20. yüklemek için DLL) veya çağrı [Afxınitrichedit](../mfc/reference/application-information-and-management.md#afxinitrichedit) eski RichEdit 1.0 denetimini (RICHED32. yüklemek için DLL).
>
> Geçerli kullanabilir [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) eski RichEdit 1.0 denetimi sınıfıyla ancak `CRichEditCtrl` yalnızca 2.0 RichEdit denetimini desteklemek için tasarlanmıştır. RichEdit 1.0 ve 2.0 RichEdit benzer olduğundan, çoğu yöntemleri çalışır. Ancak, bazı yöntemler yanlış çalışmasına veya hiç çalışmıyor 1.0 ve 2.0 denetimlerini arasında bazı farklar vardır unutmayın.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)<br/>
[İletişim Kutularındaki Denetimler](controls-in-dialog-boxes.md)<br/>
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