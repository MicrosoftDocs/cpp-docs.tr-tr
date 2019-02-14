---
title: İletişim kutusu Düzenleyicisi (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.dialog
- vc.editors.dialog.F1
- vc.editors.dialog
helpviewer_keywords:
- resource editors [C++], Dialog editor
- editors, dialog boxes
- Dialog editor
- dialog boxes [C++], editing
- controls [C++], showing or hiding Dialog editor toolbar
- toolbars [C++], showing
- toolbars [C++], hiding
- Dialog Editor [C++], showing or hiding toolbar
- events [C++], viewing for controls
- Windows messages [C++], controls
- messages [C++], viewing for dialog boxes
- Dialog Editor [C++], accessing code
- code [C++], switching from Dialog Editor
- controls [C++], jumping to code
- Dialog Editor [C++], switching between controls and code
- Dialog Editor [C++], shortcut keys
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
ms.openlocfilehash: 827a7610aa919d5349313346ac0bfa80bd0647b0
ms.sourcegitcommit: eb2b34a24e6edafb727e87b138499fa8945f981e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2019
ms.locfileid: "56264900"
---
# <a name="dialog-editor-c"></a>İletişim kutusu Düzenleyicisi (C++)

**İletişim** Düzenleyicisi oluşturma veya düzenleme iletişim kutusu kaynakları sağlar. İletişim kutusu Düzenleyicisi iletişim kutusu .rc dosyasına çift tıklayarak açın **kaynak görünümü** penceresi (**görünümü** > **kaynak görünümü**). Unutmayın **kaynak görünümü** Express sürümlerinde kullanılamaz.

Yeni iletişim kutusu (veya iletişim kutusu şablonu) yapma, ilk adımlarından biri, denetimleri iletişim kutusuna eklemektir. İçinde **iletişim** Düzenleyicisi, belirli bir boyut, Şekil veya hizalama sığması için denetimleri düzenlemek ya da bunları yaklaşık iletişim kutusu içinde çalışacak şekilde taşıyabilirsiniz. Bir denetimi silmek kolaydır.

Onu tekrar kullanabilirsiniz, böylece şablon olarak bir iletişim kutusu depolayabilirsiniz. Ayrıca bir kolayca iletişim kutusu tasarlama ve onu uygulayan kod düzenleme arasında geçiş yapabilirsiniz.

İletişim kutusu düzenleyicisinde tek veya birden çok denetim özelliklerini düzenlemek mümkündür. Sekme sırasını değiştirebilirsiniz, diğer bir deyişle, hangi denetimlerin elde sırasını Odaklan ne zaman **sekmesini** tuşuna basıldığında veya klavyeyi kullanarak denetim seçmelerini sağlar bir erişim anahtarı (bir tuş bileşimi) tanımlayabilirsiniz. Önceden oluşturulmuş erişim anahtarları listesi için bkz. [iletişim kutusu Düzenleyicisi için hızlandırma tuşları](../windows/accelerator-keys-for-the-dialog-editor.md).

**İletişim** Düzenleyicisi de ActiveX denetimleri de dahil olmak üzere özel denetimler kullanmanızı sağlar. Ayrıca, düzenleyebileceğiniz bir [form görünümü](../mfc/reference/cformview-class.md), [kayıt görünümleri](../data/record-views-mfc-data-access.md), veya [iletişim kutusu çubukları](../mfc/dialog-bars.md).

Visual Studio 2015 ile başlayarak, iletişim kutusu Düzenleyicisi nasıl denetimleri taşımak kullanıcının bir iletişim kutusu boyutlandırdığında yeniden boyutlandırma belirtin ve dinamik düzenleri tanımlamak için kullanabilirsiniz. Daha fazla bilgi için [dinamik düzen](../mfc/dynamic-layout.md).

- [Yeni İletişim Kutusu Oluşturma](../windows/creating-a-new-dialog-box.md)

- [Çalışma zamanında kullanıcıların çıkamayacağı iletişim kutusu oluşturma](../windows/creating-a-dialog-box-that-users-cannot-exit.md)

- [İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)

- [İletişim Kutusu Denetimleri için Olay İşleyicileri Ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md)

- [İletişim Kutusunu Test Etme](../windows/testing-a-dialog-box.md)

- [İletişim Kutusu Düzenleyicisinde Sorun Giderme](../windows/troubleshooting-the-dialog-editor.md)

   > [!TIP]
   > Kullanırken **iletişim** düzenleyicisinde birçok örneği, sık kullanılan komutlar kısayol menüsünü görüntülemek için sağ fare düğmesine tıklayabilirsiniz.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="dialog-editor-toolbar"></a>İletişim kutusu Düzenleyicisi araç çubuğu

Açtığınızda **iletişim** Düzenleyicisi'nde bir C++ projesi **iletişim kutusu Düzenleyicisi** araç otomatik olarak çözümünüzü üst kısmında görünür.

|Simge|Açıklama|Simge|Açıklama|
|----------|-------------|----------|-------------|
|![Test iletişim kutusu düğmesini](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|Test iletişim kutusu|![Alanı arasında düğme](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|Arasında|
|![Hizalama sola düğmesi](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|Sola Hizala|![Alanı aşağı düğmesi](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|Aşağı|
|![Hizalama hakları düğmesi](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|Sağa Hizala|![Yapma aynı genişliği düğmesi](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|Aynı genişliğe Getir|
|![Hizalama kırpın düğmesi](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|Üste hizalama|![Yapma aynı yükseklikte düğmesi](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|Aynı yüksekliğe Getir|
|![Hizalama alta düğmesi](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|Alta Hizala|![Yapma aynı boyutu düğmesi](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|Aynı Boyuta Getir|
|![Dikey Orta düğmesi](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|Dikey|![İki durumlu kılavuz düğmesi](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|Kılavuzu Aç/Kapat|
|![Yatay Orta düğmesi](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|Yatay|![Geçiş kılavuzlarını düğmesi](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|Rehberi Aç/Kapat|

**İletişim kutusu Düzenleyicisi** araç çubuğu düğmeleri düzenleme iletişim kutusunda, örneğin boyutu ve hizalama denetim düzeni için içerir. **İletişim kutusu Düzenleyicisi** araç çubuğu düğmeleri üzerinde komutları karşılık **biçimi** menüsü.

Uygulamasındayken **iletişim** Düzenleyicisi görüntülenmesini geçiş yapabileceğiniz **iletişim kutusu Düzenleyicisi** kullanılabilir araç çubukları ve windows listesinden seçerek araç çubuğu.

- Göstermek veya iletişim kutusu Düzenleyicisi araç çubuğunda gizlemek için **görünümü** menüsünde **araç çubukları**, ardından **iletişim kutusu Düzenleyicisi** alt.

   > [!NOTE]
   > **İletişim kutusu Düzenleyicisi** bir iletişim kutusu kaynağı iletişim kutusu Düzenleyicisi'nde açtığınız zaman, araç varsayılan olarak görüntülenir; ancak, araç açıkça kapatırsanız, bir iletişim kutusu kaynağına sonraki açışınızda çağırma gerekecektir.

## <a name="switch-between-dialog-box-controls-and-code"></a>İletişim kutusu denetimleri ile kod arasında geçiş yapma

MFC uygulamalarında iletişim kutusu denetimleri üzerinde işleyici kodlarını atlayın veya hızlı bir şekilde saplama işleyici işlevleri oluşturmak için çift tıklayabilirsiniz.

Bir denetim seçili durumdayken tıklayın **ControlEvents'i** düğmesini veya **iletileri** düğmesine [Özellikler penceresi](/visualstudio/ide/reference/properties-window) Windows iletileri ve olayları tam listesini görüntülemek için Seçili öğe için kullanılabilir. Oluşturma veya düzenleme işleyici işlevleri listeden seçin.

- İletişim kutusu Düzenleyicisi'nden kodu atlamak için bir denetim, en son uygulanan ileti işleme işlevinin bildirimi atlamak için iletişim kutusuna çift tıklayın. (İletişim ATL tabanlı sınıflar için her zaman Oluşturucusu tanımına atlayın.)

- Bir denetimle bir denetim seçiliyken, olayları görüntülemeyi **ControlEvents'i** düğmesine [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

   > [!NOTE]
   > Seçme **ControlEvents'i** olduğunda düğme *iletişim kutusu* odak kullanıma sunan sonra olayları tek tek denetimler için Düzen genişletebilirsiniz iletişim kutusunda, tüm denetimleri listesi vardır.

   Tek bir denetim, iletişim kutusunda odağa sahip olduğunda, sağ tıklatın ve seçin **olay işleyici Ekle** kısayol menüsünden. Bu sınıfı işleyici ekleneceği belirtmenize olanak sağlar. Daha fazla bilgi için [olay işleyici ekleme](../ide/adding-an-event-handler-visual-cpp.md).

- Seçili, iletişim kutusu ile bir iletişim kutusu iletileri görüntülemeyi **iletileri** düğmesine [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

## <a name="accelerator-keys"></a>Hızlandırıcı Tuşları

Aşağıda varsayılan Hızlandırıcı tuşları iletişim kutusu Düzenleyicisi komutları için verilmiştir. Kısayol tuşlarını değiştirmek için seçin **seçenekleri** üzerinde **Araçları** menüsünde, ardından **klavye** altında **ortam** klasör. Daha fazla bilgi için [tanımlama ve özelleştirme klavye kısayolları](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).

> [!NOTE]
> İletişim kutuları, adları ve konumları gördüğünüz gibi menü komutlarının Seçenekleri Yardımı'nda, etkin ayarlarınıza ve sürüm bağlı olarak açıklanan nedir öğesinden farklı olabilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).

|Komut|anahtarları|Açıklama|
|-------------|----------|-----------------|
|Format.AlignBottoms|**CTRL** + **Shift** + **aşağı ok**|Baskın denetimi ile seçilen denetimleri alt kenarları hizalar.|
|Format.AlignCenters|**Shift** + **F9**|Baskın denetimi ile seçilen denetimlerin dikey merkezleri hizalar.|
|Format.AlignLefts|**CTRL** + **Shift** + **sol ok**|Sol kenarları Seçili denetimleri baskın denetimi ile hizalar.|
|Format.AlignMiddles|**F9**|Baskın denetimi ile seçilen denetimleri yatay merkezleri hizalar.|
|Format.AlignRights|**CTRL** + **Shift** + **sağ ok**|Baskın denetimi seçili denetimleriyle sağ kenarları hizalar.|
|Format.AlignTops|**CTRL** + **Shift** + **yukarı ok**|Üst kenarları Seçili denetimleri baskın denetimi ile hizalar.|
|Format.ButtonBottom|**CTRL** + **B**|Seçili düğmelerini iletişim kutusunun alt ortaya koyar.|
|Format.ButtonRight|**Ctrl** + **R**|Seçili düğmelerini iletişim kutusunun sağ üst köşedeki yerleştirir.|
|Format.CenterHorizontal|**CTRL** + **Shift** + **F9**|Denetimleri yatay olarak iletişim kutusu içinde ortalar.|
|Format.CenterVertical|**CTRL** + **F9**|Denetimler iletişim kutusu içinde dikey olarak ortalar.|
|Format.CheckMnemonics|**CTRL** + **M**|Anımsatıcıları benzersizliğini denetimleri|
|Format.SizeToContent|**Shift** + **F7**|Seçili denetim açıklamalı alt yazı metni uyacak şekilde yeniden boyutlandırır|
|Format.SpaceAcross|**Alt** + **sol ok**|Seçili denetimleri yatay olarak eşit boşluk|
|Format.SpaceDown|**Alt** + **aşağı ok**|Seçili denetimleri dikey olarak eşit boşluk|
|Format.TabOrder|**Ctrl** + **D**|İletişim kutusu içinde denetimlerin sırasını ayarlar|
|Format.TestDialog|**CTRL** + **T**|Görünümünü ve davranışını test etmek için iletişim kutusu çalıştırır|
|Format.ToggleGuides|**CTRL** + **G**|İletişim düzenlemek için hiçbir kılavuz, Kılavuzlar ve kılavuz arasında geçiş yapar|

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Nasıl yapılır: Kaynak Oluşturma](../windows/how-to-create-a-resource.md)<br/>
[Denetimler](../mfc/controls-mfc.md)<br/>
[Denetim Sınıfları](../mfc/control-classes.md)<br/>
[İletişim Kutusu Sınıfları](../mfc/dialog-box-classes.md)<br/>
[İletişim Kutusu Denetimleri ve Değişken Türleri](../ide/dialog-box-controls-and-variable-types.md)