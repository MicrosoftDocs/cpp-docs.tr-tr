---
title: 'Nasıl yapılır: denetimleri ekleme, düzenleme veya silme (C++)'
ms.date: 02/15/2019
f1_keywords:
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
ms.openlocfilehash: ad14a0500336bc1ca61e00bcd6d9a6e1088afc81
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167530"
---
# <a name="how-to-add-edit-or-delete-controls-c"></a>Nasıl yapılır: denetimleri ekleme, düzenleme veya silme (C++)

Iletişim kutusu **düzenleyicisini**kullanarak, iletişim kutularında denetimleri ekleyebilir, yeniden boyutlandırabilir, düzenleyebilir ve silebilirsiniz. Ayrıca, bir denetimin özelliklerini (KIMLIĞI gibi) veya başlangıçta çalışma zamanında görünür olup olmadığını düzenleyebilirsiniz.

İletişim kutusu **düzenleyicisinde**çalışırken [araç kutusu penceresinde](/visualstudio/ide/reference/toolbox) **iletişim kutusu Düzenleyicisi** sekmesi görüntülenir. Ayrıca, **araç kutusu** penceresini daha kolay kullanılmak üzere özelleştirebilirsiniz. Daha fazla bilgi için bkz. [araç kutusunu kullanma](/visualstudio/ide/using-the-toolbox) ve [araç kutusu penceresini gösterme veya gizleme](showing-or-hiding-the-dialog-editor-toolbar.md).

> [!TIP]
> Birçok örnekte **Iletişim kutusu düzenleyicisini**kullanırken, sık kullanılan komutların kısayol menüsünü göstermek için sağ fare düğmesini seçebilirsiniz.

## <a name="add-controls"></a>Denetim Ekleme

### <a name="to-add-a-control"></a>Denetim eklemek için

1. İletişim kutusu sekmeli pencerenin düzenleyici çerçevesindeki geçerli belge olduğundan emin olun. Bir iletişim kutusu geçerli belge değilse **araç kutusunda** **Iletişim kutusu Düzenleyici sekmesini** görmezsiniz.

1. **Araç kutusu** penceresinin **iletişim kutusu düzenleyici** sekmesinde istediğiniz denetimi seçin, sonra aşağıdakilerden birini yapın:

   - Denetimi yerleştirmek istediğiniz konumdaki iletişim kutusunu seçin ve denetimin seçtiğiniz yerde görünmesini sağlayabilirsiniz.

   - **Araç** kutusu penceresinde denetimi sürükleyip iletişim kutusundaki konuma bırakın. Daha sonra denetimi taşıyabilir veya boyutunu ve şeklini değiştirebilirsiniz.

   - **Araç** kutusu penceresinde denetime çift tıklayın ve iletişim kutusunda görünür. Denetimi tercih ettiğiniz konuma göre yeniden konumlandırın.

### <a name="to-add-multiple-controls"></a>Birden çok denetim eklemek için

1. **CTRL** tuşunu basılı tutarken **araç kutusu** penceresinde bir denetim seçin.

1. **CTRL** tuşunu basılı bırakın ve belirli bir denetimi eklemek istediğiniz sayıda iletişim kutusunu seçin.

1. Denetimleri yerleştirmeyi durdurmak için **ESC** tuşuna basın.

### <a name="to-size-a-control-while-you-add-it"></a>Eklerken bir denetimi boyutlandırma

1. **Araç kutusu** penceresinde bir denetim seçin.

1. Yeni denetimin sağ üst köşesinin iletişim kutusunda olmasını istediğiniz imlecinizi, artı artı olarak görünen imlecinizi yerleştirin.

1. İletişim kutusunda denetiminizin sol üst köşesine bağlamak için fare düğmesini seçin ve basılı tutun. Ardından, denetim istediğiniz boyuta gelinceye kadar imleci sağa ve aşağı sürükleyin.

   > [!NOTE]
   > Çizim yaptığınız denetimin dört köşelerinden herhangi birini bağlayabilirsiniz. Bu yordam örnek olarak sol üst köşeyi kullandı.

1. Fare düğmesini bırakın. Denetim, belirttiğiniz boyuttaki iletişim kutusunun üzerine yükler.

> [!TIP]
> Denetimin kenarlığının boyutlandırma tutamaçlarını taşıyarak iletişim kutusuna bırakarak denetimi yeniden boyutlandırabilirsiniz. Daha fazla bilgi için bkz. [tek denetimleri boyutlandırma](../windows/sizing-individual-controls.md).

### <a name="to-add-a-custom-control"></a>Özel bir denetim eklemek için

İletişim kutusuna özel denetimler ekleyebilirsiniz. **Araç kutusu** ' nda **özel denetim** simgesini seçin ve iletişim kutusuna sürükleyin. `Syslink` bir denetim eklemek için özel bir denetim ekleyin ve sonra denetimin **Class** özelliğini `Syslink`olarak değiştirin. Bu eylem, özelliklerin yenilenmesine ve `Syslink` denetim özelliklerini görüntülemesine neden olur. MFC sarmalayıcı sınıfı hakkında daha fazla bilgi için bkz. [CLinkCtrl](../mfc/reference/clinkctrl-class.md).

## <a name="edit-controls"></a>Denetimleri Düzenle

### <a name="to-edit-the-properties-of-a-control-or-controls"></a>Bir denetimin veya denetimlerin özelliklerini düzenlemek için

1. İletişim kutusunda, değiştirmek istediğiniz denetimi seçin.

   > [!NOTE]
   > Birden çok denetim seçerseniz, yalnızca seçili denetimlerde ortak olan özellikler düzenlenebilir.

1. [Özellikler penceresi](/visualstudio/ide/reference/properties-window), denetiminizin özelliklerini değiştirin.

   > [!NOTE]
   > Bir düğme, radyo düğmesi veya onay kutusu denetiminin **bit eşlem** özelliğini **true**değerine eşitse, denetiminiz için BS_BITMAP stil uygulanır. Daha fazla bilgi için bkz. [düğme stilleri](../mfc/reference/styles-used-by-mfc.md#button-styles). Bir bitmapi bir denetimle ilişkilendirme örneği için bkz. [CButton:: SetBit eşlem](../mfc/reference/cbutton-class.md#setbitmap). **Iletişim kutusu Düzenleyicinizde**, bit eşlemler denetiminiz üzerinde görünmez.

### <a name="to-undo-changes-to-the-properties-of-a-control"></a>Bir denetimin özelliklerinde yapılan değişiklikleri geri almak için

1. Denetimin **Iletişim kutusu düzenleyicisine**odaklanıp bulunmadığından emin olun.

1. Menü **düzenle** > **geri al**'a gidin. Odak denetimde yoksa, **geri al** komutu kullanılamaz olur.

### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>Bir (düğme dışı) iletişim kutusu denetimi için bir üye değişkeni tanımlamak için

> [!NOTE]
> Bu işlem yalnızca bir MFC projesi içindeki iletişim kutusu denetimleri için geçerlidir. ATL projeleri **Yeni Windows iletileri ve olay işleyicileri** iletişim kutusunu kullanmalıdır. Daha fazla bilgi için bkz. [Kullanıcı arabirimi nesneleriyle Ilişkili Ileti türleri](../mfc/reference/message-types-associated-with-user-interface-objects.md), [ileti Işleyicisini düzenlemeyle](../mfc/reference/editing-a-message-handler.md)ve [yansıtılan bir ileti için ileti işleyicisi tanımlama](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md).

1. [Iletişim kutusu düzenleyicisinde](../windows/dialog-editor.md)bir denetim seçin.

1. **CTRL** tuşuna basıldığında iletişim kutusu denetimine çift tıklayın.

   [Üye değişkeni Ekleme Sihirbazı](../ide/add-member-variable-wizard.md) görünür.

1. **Üye değişkeni ekleme** sihirbazına ilgili bilgileri yazın. Daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi](../mfc/dialog-data-exchange.md).

1. **Iletişim kutusu düzenleyicisine**dönmek için **Tamam ' ı** seçin.

> [!TIP]
> Herhangi bir iletişim kutusu denetiminden mevcut işleyicisine geçmek için denetime çift tıklayın.

Ayrıca, belirtilen bir sınıf için yeni üye değişkenleri eklemek ve önceden tanımlı üye değişkenlerini görüntülemek için [MFC sınıf Sihirbazı](../mfc/reference/mfc-class-wizard.md) 'Ndaki **üye değişkenleri** sekmesini de kullanabilirsiniz.

## <a name="delete-controls"></a>Denetimleri Sil

İletişim kutusunda, denetimi seçin, ardından **Delete** tuşuna basın veya menü **Düzenle** > **Sil**' e gidin.

## <a name="other-issues"></a>Diğer Sorunlar

### <a name="troubleshooting"></a>Sorun giderme

İletişim kutusuna ortak denetim veya zengin düzenleme denetimi ekledikten sonra, iletişim kutusunu test ettiğinizde görünmez. Ya da iletişim kutusu görünmez. Örneğin:

1. Bir Windows uygulaması (konsol uygulaması değil) oluşturmak için uygulama ayarlarını değiştirerek bir Win32 projesi oluşturun.

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), *. RC* dosyasına çift tıklayın.

1. İletişim kutusu seçeneğinde **hakkında** kutusuna çift tıklayın.

1. İletişim kutusuna bir **IP adresi denetimi** ekleyin.

1. Tümünü kaydedin ve **yeniden derleyin**.

1. Programı yürütün.

1. İletişim kutusunun **Yardım** menüsünde, **hakkında** komutunu seçin ve Hayır iletişim kutusu görüntülenir.

Şu anda, iletişim kutusunda aşağıdaki ortak denetimleri veya zengin düzenleme denetimlerini sürükleyip bıraktığınızda, **iletişim kutusu Düzenleyicisi** projenize otomatik olarak kod eklemez. Visual Studio, bu sorun oluştuğunda bir hata veya uyarı sağlar. Onarmak için, denetimin kodunu el ile ekleyin.

||||
|-|-|-|
|Kaydırıcı denetimi|Ağaç denetimi|Tarih saat seçici|
|Döndürme denetimi|Sekme denetimi|Aylık takvim|
|İlerleme denetimi|Animasyon denetimi|IP adresi denetimi|
|Kısayol tuşu|Zengin düzenleme denetimi|Genişletilmiş Birleşik giriş kutusu|
|Liste denetimi|Zengin düzenleme 2,0 denetimi|Özel denetim|

İletişim kutusu üzerinde ortak denetimleri kullanmak için, iletişim kutusunu oluşturmadan önce [InitCommonControlsEx](/windows/win32/api/commctrl/nf-commctrl-initcommoncontrolsex) veya `AFXInitCommonControls` çağrısı yapmanız gerekir.

RichEdit denetimlerini kullanmak için `LoadLibrary`çağırmanız gerekir. Daha fazla bilgi için bkz. Windows SDK [zengin düzenleme denetimleri](/windows/win32/Controls/about-rich-edit-controls) ve [zengin düzenleme denetimine genel bakış](../mfc/overview-of-the-rich-edit-control.md).

> [!NOTE]
> Bir RichEdit denetimini MFC ile birlikte kullanmak için, öncelikle [AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) öğesini çağırıp RichEdit 2,0 DENETIMINI (RICHED20) yüklemeniz gerekir. DLL) veya eski RichEdit 1,0 denetimini (RICHED32) yüklemek için [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) 'i çağırın. DLL).
>
> Geçerli [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) sınıfını eski RichEdit 1,0 denetimiyle kullanabilirsiniz, ancak `CRichEditCtrl` yalnızca RichEdit 2,0 denetimini destekleyecek şekilde tasarlanmıştır. RichEdit 1,0 ve RichEdit 2,0 benzer olduğundan çoğu Yöntem çalışacaktır. Ancak, 1,0 ve 2,0 denetimleri arasında bazı farklılıklar vardır. bu nedenle bazı yöntemler yanlış çalışabilir veya hiç çalışmayabilir.

### <a name="activex-controls"></a>ActiveX Denetimleri

Visual Studio, iletişim kutusuna ActiveX denetimleri eklemenize olanak sağlar. Daha fazla bilgi için bkz. [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md) ve [ActiveX denetim kapsayıcıları](../mfc/activex-control-containers.md).

**ActiveX denetimi Ekle** iletişim kutusu, Iletişim kutusu [düzenleyicisini](../windows/dialog-editor.md)kullanırken iletişim kutusuna ActiveX denetimleri eklemenize olanak sağlar. Bu iletişim kutusu aşağıdaki özellikleri içerir:

|Özellik|Açıklama|
|---|---|
|**ActiveX denetimi**|ActiveX denetimlerinin bir listesini görüntüler.<br/><br/>Bu iletişim kutusundan bir denetim eklemek sarmalayıcı sınıfı oluşturmaz. Sarmalayıcı sınıfa ihtiyacınız varsa, oluşturmak için [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code) kullanın, bkz. [sınıf ekleme](../ide/adding-a-class-visual-cpp.md).<br/><br/>ActiveX denetimi bu iletişim kutusunda görünmezse, denetimi satıcının yönergelerine göre yüklemeyi deneyin.|
|**Path**|ActiveX denetiminin bulunduğu dosyayı görüntüler.|

> [!CAUTION]
> Sisteminizdeki tüm ActiveX denetimlerini dağıtmak yasal olmayabilir. Denetimleri yükleyen yazılım için lisans sözleşmesine başvurun veya yazılım şirketiyle iletişim kurun.

#### <a name="to-add-an-activex-control"></a>ActiveX denetimi eklemek için

1. **İletişim kutusu düzenleyicisinde**bir iletişim kutusu açın.

1. İletişim kutusunun gövdesinde herhangi bir yere sağ tıklayın ve **ActiveX denetimi Ekle**' yi seçin.

   Sisteminizdeki tüm ActiveX denetimlerini gösteren **ActiveX denetimi Ekle** iletişim kutusu görünür. İletişim kutusunun en altında, ActiveX Denetim dosyasının yolu görüntülenir.

1. İletişim kutusuna eklemek istediğiniz denetimi seçin ve **Tamam**' ı seçin.

   Denetim, iletişim kutusunda görünür, burada, diğer denetimleri yaptığınız gibi onu düzenleyebilir veya işleyicileri oluşturabilirsiniz.

> [!TIP]
> İletişim kutusuna kayıtlı ActiveX denetimlerini hızlıca eklemek veya kolay erişim için **araç kutusu** penceresine ActiveX denetimleri eklemeyi denemek için **iletişim kutusu düzenleyicisindeki** kısayol menüsünü kullanabilirsiniz.

#### <a name="to-edit-properties-for-an-activex-control"></a>ActiveX denetiminin özelliklerini düzenlemek için

Bağımsız satıcılar tarafından sağlanan ActiveX denetimleri kendi özellikleri ve özellikleriyle donatılmış olabilir. Bu özellikler **Özellikler** penceresinde görüntülenir. ActiveX denetiminin yazarları tarafından oluşturulan tüm özellik sayfaları, **Özellikler sayfaları** iletişim kutusunda görüntülenir. (Belirli bir ActiveX denetiminin **özellik sayfasını** görüntülemek için [Özellikler penceresi](/visualstudio/ide/reference/properties-window)) **özellik sayfası** düğmesini seçin.

- Özellikleri görüntülemek için **ActiveX** denetimini seçin ve menü **görünümü** > **özellik sayfasına** gidin. Özellik sayfasında gerektiğinde değişiklik yapın.

   ActiveX denetiminin bir parçası olarak gelen özellik sayfalarına bağlı olarak, ActiveX denetiminin özellik sayfasında çeşitli sekmeler görüntülenir.

> [!NOTE]
> Bu yordam, ActiveX denetimlerini düzenlemek için özellik sayfasını kullanma için geçerlidir. Ayrıca, yeni **Özellikler** penceresinde ActiveX özelliklerine gözatabilir ve bunları düzenleyebilirsiniz.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Iletişim kutusu denetimlerini Yönet](controls-in-dialog-boxes.md)<br/>
[Nasıl yapılır: düzen denetimleri](arrangement-of-controls-on-dialog-boxes.md)<br/>
[Nasıl yapılır: denetim erişimini ve değerlerini tanımlama](defining-mnemonics-access-keys.md)

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
