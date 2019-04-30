---
title: İletişim kutusu Düzenleyicisi (C++)
ms.date: 02/15/2019
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
ms.openlocfilehash: dc5a823951e07af96efceec52d2aa23552c2d002
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414392"
---
# <a name="dialog-editor-c"></a>İletişim kutusu Düzenleyicisi (C++)

**İletişim kutusu Düzenleyicisi** oluşturma veya düzenleme iletişim kutusu kaynakları sağlar.

- Bir iletişim kutusu .rc dosyasında düzenleyicisini açmak için çift **kaynak görünümü** pencere veya menü Git **görünümü** > **kaynak görünümü**.

Yeni iletişim kutusu veya iletişim kutusu şablonu yapma, ilk adımlarından denetimleri eklemektir. İçinde **iletişim kutusu Düzenleyicisi**, belirli bir boyut, Şekil veya hizalama sığması için denetimleri düzenleyebilirsiniz veya bunları yaklaşık iletişim kutusu içinde çalışacak şekilde taşıyabilirsiniz. Bir denetimi silmek kolaydır.

Onu tekrar kullanabilirsiniz, böylece şablon olarak bir iletişim kutusu depolayabilirsiniz. Ayrıca bir kolayca iletişim kutusu tasarlama ve onu uygulayan kod düzenleme arasında geçiş yapabilirsiniz.

Tek özelliklerini düzenlemek mümkündür ya da birden çok denetimleri içinde **iletişim kutusu Düzenleyicisi**. Sekme sırasını değiştirebilirsiniz, diğer bir deyişle, hangi denetimlerin elde sırasını Odaklan ne zaman **sekmesini** tuşuna basıldığında veya bir erişim anahtarı veya klavyeyi kullanarak denetim seçmelerini sağlar tuş bileşimini tanımlayabilirsiniz.

**İletişim kutusu Düzenleyicisi** ayrıca ActiveX denetimleri de dahil olmak üzere özel denetimler kullanmanıza olanak tanır. Ayrıca düzenleyebileceğiniz bir [form görünümü](../mfc/reference/cformview-class.md), [kayıt görünümleri](../data/record-views-mfc-data-access.md), veya [iletişim kutusu çubukları](../mfc/dialog-bars.md).

Kullanabileceğiniz Visual Studio 2015 ile başlayarak, **iletişim kutusu Düzenleyicisi** bir iletişim kutusu kullanıcı yeniden boyutlandırdığında nasıl denetimleri taşımak belirtin dinamik düzenler ve yeniden boyutlandırma tanımlamak için. Daha fazla bilgi için [dinamik düzen](../mfc/dynamic-layout.md).

Kaynaklar hakkında daha fazla bilgi için bkz. nasıl [Oluştur iletişim kutusu](../windows/creating-a-new-dialog-box.md) ve [iletişim kutusu denetimleri](../windows/controls-in-dialog-boxes.md).

> [!TIP]
> Kullanırken **iletişim kutusu Düzenleyicisi**, çoğu durumda, sık kullanılan komutlar bir kısayol menüsünü görüntülemek için farenin sağ düğmesiyle seçebilirsiniz.

## <a name="dialog-editor-toolbar"></a>İletişim kutusu Düzenleyicisi araç çubuğu

**İletişim kutusu Düzenleyicisi** araç çubuğu düğmeleri düzenleme iletişim kutusunda, örneğin boyutu ve hizalama denetim düzeni için içerir. **İletişim kutusu Düzenleyicisi** araç çubuğu düğmeleri üzerinde komutları karşılık **biçimi** menüsü.

|Simge|Açıklama|Simge|Açıklama|
|----------|-------------|----------|-------------|
|![Test iletişim kutusu düğmesini](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|Test iletişim kutusu|![Alanı arasında düğme](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|Arasında|
|![Hizalama sola düğmesi](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|Sola Hizala|![Alanı aşağı düğmesi](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|Aşağı|
|![Hizalama hakları düğmesi](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|Sağa Hizala|![Yapma aynı genişliği düğmesi](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|Aynı genişliğe Getir|
|![Hizalama kırpın düğmesi](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|Üste hizalama|![Yapma aynı yükseklikte düğmesi](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|Aynı yüksekliğe Getir|
|![Hizalama alta düğmesi](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|Alta Hizala|![Yapma aynı boyutu düğmesi](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|Aynı Boyuta Getir|
|![Dikey Orta düğmesi](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|Dikey|![İki durumlu kılavuz düğmesi](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|Kılavuzu Aç/Kapat|
|![Yatay Orta düğmesi](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|Yatay|![Geçiş kılavuzlarını düğmesi](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|Rehberi Aç/Kapat|

- Göstermek veya gizlemek için **iletişim kutusu Düzenleyicisi** araç menüsüne gidin **görünümü** > **araç çubukları** > **iletişim kutusu Düzenleyicisi**.

Açtığınızda **iletişim kutusu Düzenleyicisi** bir C++ projesinde **iletişim kutusu Düzenleyicisi** araç otomatik olarak çözümünüzü üst kısmında görüntülenir, ancak açıkça araç kapatırsanız, onu çağırmak gerekecektir bir sonraki açışınızda **iletişim kutusu Düzenleyicisi**. Mevcut araç çubukları ve windows listesinden seçerek görünümünü geçiş yapabilirsiniz.

## <a name="switch-between-dialog-box-controls-and-code"></a>İletişim kutusu denetimleri ile kod arasında geçiş yapma

MFC uygulamalarında iletişim kutusu denetimleri üzerinde işleyici kodlarını atlayın veya hızlı bir şekilde saplama işleyici işlevleri oluşturmak için çift tıklayabilirsiniz.

Bir denetim seçili durumdayken seçin **ControlEvents'i** düğmesini veya **iletileri** düğmesine [Özellikler penceresi](/visualstudio/ide/reference/properties-window) Windows iletileri ve olayları tam listesini görüntülemek için Seçili öğe için kullanılabilir. Oluşturma veya düzenleme işleyici işlevleri listeden seçin.

- Koddan atlamak için **iletişim kutusu Düzenleyicisi**, Denetim, en son uygulanan ileti işleme işlevinin bildirimi atlamak için iletişim kutusuna çift tıklayın.

   ATL tabanlı iletişim sınıfları için her zaman Oluşturucusu tanımına atlayın.

- Bir denetimle bir denetim seçiliyken, olayları görüntülemeyi **ControlEvents'i** düğmesine **özellikleri** penceresi.

   Tek bir denetim, iletişim kutusunda odağa sahip olduğunda, sağ seçin tıklayıp **olay işleyici Ekle**. Bu sınıfı işleyici ekleneceği belirtmenize olanak sağlar. Daha fazla bilgi için [olay işleyici ekleme](../ide/adding-an-event-handler-visual-cpp.md).

   > [!NOTE]
   > Seçme **ControlEvents'i** iletişim kutusu odağa sahip olduğunda düğme sonra olayları tek tek denetimler için Düzen genişletebilirsiniz iletişim kutusunda, tüm denetimlerin listesini gösterir.

- Seçili, iletişim kutusu ile bir iletişim kutusu iletileri görüntülemeyi **iletileri** düğmesine **özellikleri** penceresi.

## <a name="accelerator-keys"></a>Hızlandırıcı Tuşları

Varsayılan Hızlandırıcı tuşları aşağıda verilmiştir **iletişim kutusu Düzenleyicisi** komutları.  

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
|Format.CenterHorizontal|**CTRL** + **Shift** + **F9**|Denetimler iletişim kutusu içinde yatay olarak merkezlendirir.|
|Format.CenterVertical|**CTRL** + **F9**|Denetimler iletişim kutusu içinde dikey olarak ortalar.|
|Format.CheckMnemonics|**CTRL** + **M**|Anımsatıcıları benzersizliğini denetler.|
|Format.SizeToContent|**Shift** + **F7**|Seçili denetim açıklamalı alt yazı metni uyacak şekilde yeniden boyutlandırır.|
|Format.SpaceAcross|**Alt** + **sol ok**|Eşit olarak seçili denetimleri yatay boşluk.|
|Format.SpaceDown|**Alt** + **aşağı ok**|Seçili denetimleri eşit dikey boşluk.|
|Format.TabOrder|**Ctrl** + **D**|İletişim kutusu içinde denetimlerin sırasını ayarlar.|
|Format.TestDialog|**CTRL** + **T**|Görünümünü ve davranışını test etmek için iletişim kutusu çalıştırır.|
|Format.ToggleGuides|**CTRL** + **G**|İletişim düzenlemek için döngüleri arasında hiçbir kılavuz, Kılavuzlar ve kılavuz.|

- Kısayol tuşlarını değiştirmek için menüsüne gidin **Araçları** > **seçenekleri**ve **klavye** altında **ortam** klasör.

   Daha fazla bilgi için [tanımlama ve özelleştirme klavye kısayolları](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).

- Ayarlarınızı değiştirmek için menüsüne gidin **Araçları** > **içeri ve dışarı aktarma ayarları**.

   Açıklanan nedir gelen iletişim kutuları, adları ve konumları gördüğünüz gibi menü komutlarının seçenekleri değişebilir **yardımcı** bağlı olarak, etkin ayarlarınıza ve sürüm.  Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Nasıl yapılır: İletişim Kutusu Oluşturma](../windows/creating-a-new-dialog-box.md)<br/>
[İletişim Kutusu Denetimleri](../windows/controls-in-dialog-boxes.md)<br/>
<!--
[Controls](../mfc/controls-mfc.md)<br/>
[Control Classes](../mfc/control-classes.md)<br/>
[Dialog Box Classes](../mfc/dialog-box-classes.md)<br/>
[Dialog Box Controls and Variable Types](../ide/dialog-box-controls-and-variable-types.md)-->