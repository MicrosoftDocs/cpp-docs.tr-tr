---
title: İletişim Düzenleyicisi (C++)
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
ms.openlocfilehash: f1544d3a8e14f9373e21b77d888860d24ab1ed6a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370289"
---
# <a name="dialog-editor-c"></a>İletişim Düzenleyicisi (C++)

**İletişim** Düzenleyicisi, iletişim kutusu kaynakları oluşturmanıza veya bu kaynakları oluşturmanıza veya bu kaynakları oluşturmanıza olanak tanır.

- Düzenleyiciyi açmak için Kaynak **Görünümü** penceresindeki bir iletişim kutusunun .rc dosyasına çift tıklayın veya**Diğer Windows** > **Kaynak Görünümünü** **Görüntüle** > menüsüne gidin.

Yeni bir iletişim kutusu veya iletişim kutusu şablonu oluşturmanın ilk adımlarından biri denetimler eklemektir. **İletişim**Düzenleyicisi'nde, denetimleri belirli bir boyuta, şekle veya hizalamaya uyacak şekilde düzenleyebilir veya bunları iletişim kutusu içinde çalışacak şekilde hareket ettirebilirsiniz. Denetimi silmek de kolaydır.

Bir iletişim kutusunu şablon olarak depolayabilirsiniz, böylece yeniden kullanabilirsiniz. Ayrıca, iletişim kutusunu tasarlamak ve bunu uygulayan kodu düzenlemek arasında kolayca geçiş yapabilirsiniz.

İletişim Düzenleyicisi'nde tek veya birden çok denetimin özelliklerini de dilemek **mümkündür.** Sekme sırasını, diğer bir deyişle **Sekme** tuşuna basıldığında odak noktasını kontrol etme sırasını değiştirebilir veya kullanıcıların klavyeyi kullanarak denetim seçmesine olanak tanıyan bir erişim tuşu veya anahtar kombinasyonu tanımlayabilirsiniz.

**İletişim** Düzenleyicisi, ActiveX denetimleri de dahil olmak üzere özel denetimleri kullanmanıza da olanak tanır. Ayrıca form [görünümünü,](../mfc/reference/cformview-class.md)kayıtları [görünümlerini](../data/record-views-mfc-data-access.md)veya [iletişim çubuklarını](../mfc/dialog-bars.md)da edinebilirsiniz.

Visual Studio 2015'ten başlayarak, kullanıcı bir iletişim kutusunu yeniden boyutlandırdığında denetimlerin nasıl hareket edip yeniden boyutlandırılabileceğini belirten dinamik düzenleri tanımlamak için İletişim Düzenleyicisi'ni kullanabilirsiniz. **Dialog Editor** Daha fazla bilgi için [Dinamik Düzen'e](../mfc/dynamic-layout.md)bakın.

Kaynaklar hakkında daha fazla bilgi için, İletişim Kutusu ve [İletişim Kutusu Denetimleri](../windows/controls-in-dialog-boxes.md) [Oluşturma'ya](../windows/creating-a-new-dialog-box.md) bakın.

> [!TIP]
> **İletişim**Düzenleyicisi'ni kullanırken, birçok durumda, sık kullanılan komutlardan oluşan bir kısayol menüsünü görüntülemek için sağ fare düğmesiyle seçim yapabilirsiniz.

## <a name="dialog-editor-toolbar"></a>İletişim Düzenleyiciaraç Çubuğu

**İletişim Düzenleyicisi** araç çubuğu, iletişim kutusundaki denetimlerin düzenini (örneğin boyut ve hizalama) düzenlemek için düğmeler içerir. **İletişim Düzenleyicisi** araç çubuğu düğmeleri **Biçim** menüsündeki komutlara karşılık gelir.

|Simge|Anlamı|Simge|Anlamı|
|----------|-------------|----------|-------------|
|![Test İletişim düğmesi](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditörTestDialog")|Test İletişimi|![Boşluk Tuşuna Basın](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|Karşısında|
|![Soldüğmeyi Hizala](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|Solları Hizala|![Aşağı Yaslayla](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|Aşağı|
|![Hakları Hizala düğmesi](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditörAlignRights")|Hakları Hizala|![Aynı Genişlik düğmesini yap](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditörSameWidth")|Aynı Genişlikte Yap|
|![Üstleri Hizala düğmesi](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|Üstleri Hizala|![Aynı Yükseklik düğmesini yap](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|Aynı Yükseklik olun|
|![Altları Hizala düğmesi](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|Altları Hizala|![Aynı Boyut düğmesini yap](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|Aynı Boyutta olun|
|![Dikey Düğmeyi Ortala](../mfc/media/vcdialogeditorvertical.png "vcDialogEditörDikey")|Dikey|![Grid düğmesini geçiş](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|Kılavuzu Aç/Kapat|
|![Yatay'ı Merkezle düğmesi](../mfc/media/vcdialogeditorhorizontal.png "vcDialogDüzenleyiciYatay")|Yatay|![Kılavuzları Geçiş düğmesi](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|Geçiş Kılavuzları|

- **İletişim Düzenleyicisi** araç çubuğunu göstermek veya gizlemek için,**Araç Çubuklarını** >  **Görüntüle** > **İletişim Düzenleyicisi**menüsüne gidin.

Bir C++ projesinde İletişim Düzenleyicisi'ni açtığınızda, **İletişim Düzenleyicisi** araç çubuğu otomatik olarak çözümünüzün üst kısmında görünür, ancak araç çubuğunu açıkça kapatırsanız, **İletişim Düzenleyicisi'ni**bir sonraki açtığınızda bu düzenlemeyi çağırmanız gerekir. **Dialog Editor** Kullanılabilir araç çubukları ve pencereler listesinden seçerek ekranını geçişyapabilirsiniz.

## <a name="switch-between-dialog-box-controls-and-code"></a>İletişim Kutusu Denetimleri ve Kod Arasında Geçiş Yap

MFC uygulamalarında, işleyici kodlarına atlamak veya hızlı bir şekilde saplama işleyiciişlevleri oluşturmak için iletişim kutusu denetimlerini çift tıklatabilirsiniz.

Bir denetim seçili olarak, seçili öğe için kullanılabilen Windows iletilerinin ve olayların tam listesini görüntülemek için [Özellikler penceresindeki](/visualstudio/ide/reference/properties-window) **Denetim Olayları** düğmesini veya **İletiler** düğmesini seçin. İşleyici işlevleri oluşturmak veya dağıtmak için listeden seçim yapın.

- **İletişim**Düzenleyicisi'nden koda atlamak için, en son uygulanan ileti işleme işlevi için bildirime atlamak için iletişim kutusu içindeki bir denetime çift tıklayın.

   ATL tabanlı iletişim sınıfları için her zaman oluşturucu tanımına atlarsınız.

- Denetim için olayları görüntülemek için, denetim seçili olarak, **Özellikler** penceresindeki **Denetim Olayları** düğmesini seçin.

   Tek bir denetim iletişim kutusunda odaklandığında, olay **işleyicisi ekle'yi**sağ tıklayıp seçebilirsiniz. Bu, işleyicinin eklendiği sınıfı belirtmenizi sağlar. Daha fazla bilgi için [bkz.](../ide/adding-an-event-handler-visual-cpp.md)

   > [!NOTE]
   > İletişim kutusu nda odak olduğunda **Denetim Olayları** düğmesini seçmek, iletişim kutusundaki tüm denetimlerin bir listesini ortaya çıkarır ve bu listeyi tek tek denetimlerin olaylarını yeniden düzenleyen lere genişletebilirsiniz.

- İletişim kutusu seçili bir iletişim kutusu için iletileri görüntülemek için **Özellikler** penceresindeki **İletiler** düğmesini seçin.

## <a name="accelerator-keys"></a>Hızlandırıcı Tuşları

Aşağıda, **İletişim Düzenleyicisi** komutları için varsayılan hızlandırıcı anahtarları verilmiştir.  

|Komut|Anahtarlar|Açıklama|
|-------------|----------|-----------------|
|Format.AlignBottoms|**Ctrl** + **Shift** + **Aşağı Ok**|Seçili denetimlerin alt kenarlarını baskın denetimle hizalar.|
|Format.AlignCenters|**Shift** + **F9**|Seçili denetimlerin dikey merkezlerini baskın kontrolle hizalar.|
|Format.AlignLefts|**Ctrl** + **Shift** + **Sol Ok**|Seçili denetimlerin sol kenarlarını baskın denetimle hizalar.|
|Format.AlignMiddles|**F9**|Seçili denetimlerin yatay merkezlerini baskın kontrolle hizalar.|
|Format.AlignRights|**Ctrl** + **Shift** + **Sağ Ok**|Seçili denetimlerin sağ kenarlarını baskın denetimle hizalar.|
|Format.AlignTops|**Ctrl** + **Yukarı** + **Ok**|Seçili denetimlerin üst kenarlarını baskın denetimle hizalar.|
|Format.ButtonBottom|**Ctrl** + **B**|Seçili düğmeleri iletişim kutusunun alt ortasına yerleştirir.|
|Format.ButtonRight|**Ctrl** + **R**|Seçili düğmeleri iletişim kutusunun sağ üst köşesine yerleştirir.|
|Format.CenterHorizontal|**Ctrl** + **Vites** + **F9**|Denetimleri iletişim kutusu içinde yatay olarak ortalar.|
|Format.CenterVertical|**Ctrl** + **F9**|Denetimleri iletişim kutusu içinde dikey olarak ortalar.|
|Format.CheckMnemonics|**Ctrl** + **M**|Mnemonics teklik kontrol eder.|
|Format.SizetoContent|**Vites** + **F7**|Alt yazı metnine uyacak şekilde seçili denetim(ler) yeniden boyutlandır.|
|Format.SpaceAcross|**Alt** + **Sol Ok**|Seçili denetimleri yatay olarak eşit olarak boşluklar.|
|Format.SpaceDown|**Alt** + **Aşağı Ok**|Seçili denetimleri dikey olarak eşit olarak yerle bir eder.|
|Format.TabOrder|**Ctrl** + **D**|İletişim kutusu içindeki denetimsırasını ayarlar.|
|Format.TestDialog|**Ctrl** + **T**|Görünüm ve davranışı sınamak için iletişim kutusunu çalıştırın.|
|Format.ToggleGuides|**Ctrl** + **G**|Kılavuz, yönergeler ve iletişim düzenleme için ızgara arasındaki döngüler.|

- Kısayol tuşlarını değiştirmek için **Araçlar** > **Seçenekleri**menüsüne gidin ve **Çevre** klasörünün altındaki **Klavye'yi** seçin.

   Daha fazla bilgi için bkz: [Klavye Kısayollarını Tanımlama ve Özelleştirme.](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)

- Ayarlarınızı değiştirmek için **Araçlar** > **İçe Ve Dışa Aktar Ayarları**menüsüne gidin.

   İletişim kutularında bulunan seçenekler ve gördüğünüz menü komutlarının adları ve konumları, etkin ayarlarınıza veya sürüme bağlı olarak **Yardım'da** açıklanandan farklı olabilir.  Daha fazla bilgi için [Visual Studio IDE'yi Kişiselleştir'e](/visualstudio/ide/personalizing-the-visual-studio-ide)bakın.

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
