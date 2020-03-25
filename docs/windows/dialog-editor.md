---
title: İletişim kutusu DüzenleyicisiC++()
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
ms.openlocfilehash: 9d0f9993d81c499f67a08e5401c5e56dba7b281c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215260"
---
# <a name="dialog-editor-c"></a>İletişim kutusu DüzenleyicisiC++()

**İletişim kutusu Düzenleyicisi** , iletişim kutusu kaynakları oluşturmanıza veya düzenlemenize olanak tanır.

- Düzenleyiciyi açmak için **kaynak görünümü** penceresinde bir iletişim kutusunun. rc dosyasına çift tıklayın veya menü **görünümü** ' ne > **diğer Windows** > **kaynak görünümü**gidin.

Yeni bir iletişim kutusu veya iletişim kutusu şablonu oluşturmak için ilk adımlardan biri denetimleri ekliyor. Iletişim kutusu **düzenleyicisinde**, denetimleri belirli bir boyut, şekil veya hizalamayı sığacak şekilde düzenleyebilir veya iletişim kutusunda çalışmak için bu öğeleri etrafında taşıyabilirsiniz. Ayrıca, bir denetimi silmek de kolaydır.

Bir iletişim kutusunu yeniden kullanabilmeniz için şablon olarak saklayabilirsiniz. Ayrıca, iletişim kutusunu tasarlama ve bunu uygulayan kodu düzenlemeyle arasında kolayca geçiş yapabilirsiniz.

**Iletişim kutusu düzenleyicisinde**tek veya birden çok denetimin özelliklerini düzenlemek de mümkündür. Sekme sırasını, diğer bir deyişle **Tab** tuşuna basıldığında denetimlerin odaklandığı sırayı değiştirebilirsiniz veya kullanıcıların klavyeyi kullanarak denetim seçmesine izin veren bir erişim anahtarı ya da anahtar birleşimi tanımlayabilirsiniz.

**Iletişim kutusu Düzenleyicisi** , ActiveX denetimleri de dahil olmak üzere özel denetimler kullanmanıza da olanak tanır. [Form görünümünü](../mfc/reference/cformview-class.md), [kayıt görünümlerini](../data/record-views-mfc-data-access.md)veya [iletişim çubuklarını](../mfc/dialog-bars.md)da düzenleyebilirsiniz.

Visual Studio 2015 ' den başlayarak, Kullanıcı bir iletişim kutusu yeniden boyutlandırdığında denetimlerin nasıl hareket etdiğini belirten dinamik düzenleri tanımlamak için **Iletişim düzenleyicisini** kullanabilirsiniz. Daha fazla bilgi için bkz. [Dinamik düzen](../mfc/dynamic-layout.md).

Kaynaklar hakkında daha fazla bilgi için bkz. [Iletişim kutusu](../windows/creating-a-new-dialog-box.md) ve [Iletişim kutusu denetimleri](../windows/controls-in-dialog-boxes.md)oluşturma.

> [!TIP]
> Birçok örnekte **Iletişim kutusu düzenleyicisini**kullanırken, sık kullanılan komutların kısayol menüsünü göstermek için sağ fare düğmesi ile seçeneğini belirleyebilirsiniz.

## <a name="dialog-editor-toolbar"></a>İletişim kutusu Düzenleyici araç çubuğu

**İletişim kutusu düzenleyici** araç çubuğu, iletişim kutusundaki denetimlerin yerleşimini düzenlemek için düğmeler içerir, örneğin boyut ve hizalama. **Iletişim kutusu Düzenleyicisi** araç çubuğu düğmeleri **Biçim** menüsündeki komutlara karşılık gelir.

|Simge|Anlamı|Simge|Anlamı|
|----------|-------------|----------|-------------|
|![Test Iletişim düğmesi](../mfc/media/vcdialogeditortestdialog.png "Vcdialogedıtortestdialog")|Test Iletişim kutusu|![Çapraz boşluk düğmesi](../mfc/media/vcdialogeditoracross.png "Vcdialogedıtorat")|Yönlendirilmesine|
|![Sola Hizala düğmesi](../mfc/media/vcdialogeditoralignlefts.png "Vcdialogeditorhizalaması solları")|Solları Hizala|![Boşluk aşağı düğmesi](../mfc/media/vcdialogeditordown.png "Vcdialogedıtori")|Aşağı|
|![Sağa Hizala düğmesi](../mfc/media/vcdialogeditoralignrights.png "Vcdialogeditorhizalaması hakları")|Hakları Hizala|![Aynı genişliğe getir düğmesi](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|Aynı genişliğe getir|
|![Üste Hizala düğmesi](../mfc/media/vcdialogeditoraligntops.png "Vcdialogeditorhizalaması")|Üste Hizala|![Aynı yüksekliğe getir düğmesi](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|Aynı yüksekliğe getir|
|![Botlar düğmesini Hizala](../mfc/media/vcdialogeditoralignbottoms.png "Vcdialogeditorhizalaması botları")|Botları Hizala|![Aynı boyuta getir düğmesi](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|Aynı boyuta getir|
|![Dikey Ortala düğmesi](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|Matema|![Kılavuza geç düğmesi](../mfc/media/vcdialogeditortogglegrid.png "Vcdialogedıtortogglegrid")|Kılavuzu Aç/Kapat|
|![Yatay Ortala düğmesi](../mfc/media/vcdialogeditorhorizontal.png "Vcdialogeditoryatay")|Yatay|![Kılavuzlara geçiş düğmesi](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|Geçiş kılavuzlarını|

- **Iletişim kutusu Düzenleyicisi** araç çubuğunu göstermek veya gizlemek Için menü **görünümü** > **araç çubukları** > **iletişim kutusu Düzenleyicisi**' ne gidin.

**İletişim kutusu düzenleyicisini** C++ bir projede açtığınızda, iletişim kutusu **Düzenleyici** araç çubuğu çözümünüzün en üstünde otomatik olarak görünür, ancak araç çubuğunu açıkça kapatırsanız, **iletişim kutusu düzenleyicisini**bir sonraki açışınızda çağırmanız gerekir. Kullanılabilir araç çubukları ve pencereler listesinden seçerek görüntülenmesini sağlayabilirsiniz.

## <a name="switch-between-dialog-box-controls-and-code"></a>Iletişim kutusu denetimleri ile kod arasında geçiş yapma

MFC uygulamalarında, iletişim kutusu denetimlerine çift tıklayarak kendi işleyici koduna atlayabilir veya saplama işleyici işlevlerini hızlıca oluşturabilirsiniz.

Seçilen bir denetim seçiliyken seçili öğe için mevcut olan Windows iletilerinin ve olaylarının tüm listesini görüntülemek için [Özellikler penceresi](/visualstudio/ide/reference/properties-window) **controtavents** düğmesini veya **iletiler** düğmesini seçin. İşleyici işlevleri oluşturmak veya düzenlemek için listeden seçin.

- **İletişim kutusu düzenleyicisinden**koda geçmek için, en son uygulanan ileti işleme işlevine yönelik bildirime gitmek için iletişim kutusundaki bir denetime çift tıklayın.

   ATL tabanlı iletişim sınıfları için, her zaman Oluşturucu tanımına atlayın.

- Bir denetimin olaylarını görüntülemek için, bir denetim seçiliyken, **Özellikler** penceresinde **controtavents** düğmesini seçin.

   İletişim kutusunda tek bir denetim odağa sahip olduğunda, sağ tıklayıp **olay Işleyicisi Ekle**' yi seçebilirsiniz. Bu, işleyicinin eklendiği Sınıfı belirtmenize olanak sağlar. Daha fazla bilgi için bkz. [olay Işleyicisi ekleme](../ide/adding-an-event-handler-visual-cpp.md).

   > [!NOTE]
   > İletişim kutusu odağa sahip olduğunda **Controtavents** düğmesini seçmek, iletişim kutusundaki tüm denetimlerin bir listesini kullanıma sunar. Bu, daha sonra her bir denetimin olaylarını düzenlemek için genişletebilirsiniz.

- İletişim kutusu seçili iletişim kutusunda iletileri görüntülemek için, **Özellikler** penceresinde **iletiler** düğmesini seçin.

## <a name="accelerator-keys"></a>Hızlandırıcı Tuşları

**Iletişim kutusu Düzenleyicisi** komutları için varsayılan hızlandırıcı tuşları aşağıda verilmiştir.  

|Komut|Anahtarlar|Açıklama|
|-------------|----------|-----------------|
|Format.AlignBottoms|**Ctrl** + **SHIFT** + **aşağı ok**|Baskın denetim ile seçili denetimlerin alt kenarlarını hizalar.|
|Format.AlignCenters|**Shıft** + **F9**|Seçilen denetimlerin dikey merkezlerini baskın denetimle hizalar.|
|Format.AlignLefts|**Ctrl** + **SHIFT** + **sol ok**|Seçilen denetimlerin sol kenarlarını baskın denetim ile hizalar.|
|Format.AlignMiddles|**F9'a**|Seçilen denetimlerin yatay merkezlerini baskın denetimle hizalar.|
|Format.AlignRights|**Ctrl** + **SHIFT** + **sağ ok**|Seçilen denetimlerin sağ kenarlarını baskın denetim ile hizalar.|
|Format.AlignTops|**Ctrl** + **SHIFT** + **yukarı ok**|Baskın denetim ile seçili denetimlerin üst kenarlarını hizalar.|
|Format.ButtonBottom|**Ctrl** + **B**|Seçili düğmeleri iletişim kutusunun alt ortasına koyar.|
|Format.ButtonRight|**Ctrl** + **R**|Seçili düğmeleri iletişim kutusunun sağ üst köşesine koyar.|
|Format.CenterHorizontal|**Ctrl** + **SHIFT** + **F9**|Denetimleri iletişim kutusu içinde yatay olarak ortalar.|
|Format.CenterVertical|**Ctrl** + **F9**|Denetimleri iletişim kutusu içinde dikey olarak ortalar.|
|Format.CheckMnemonics|**Ctrl** + **a**|Anımsatıcıları benzersiz denetler.|
|Format. SizeToContent|**Shıft** + **F7**|Seçili denetimleri, açıklamalı alt yazı metnine sığacak şekilde yeniden boyutlandırır.|
|Format.SpaceAcross|**Alt** + **sol ok**|Seçili denetimleri yatay olarak eşit boşluklar.|
|Format.SpaceDown|**Alt** + **aşağı ok**|Seçili denetimleri dikey olarak eşit boşluklar.|
|Format.TabOrder|**Ctrl** + **D**|İletişim kutusu içindeki denetimlerin sırasını ayarlar.|
|Format.TestDialog|**Ctrl** + **t**|Görünümü ve davranışı test etmek için iletişim kutusunu çalıştırır.|
|Format.ToggleGuides|**Ctrl** + **G**|İletişim kutusu düzenlemesi için kılavuz, yönergeler ve kılavuz yok.|

- Kısayol tuşlarını değiştirmek için menü **araçları** > **Seçenekler**' e gidin ve **ortam** klasörünün altında **klavye** ' yi seçin.

   Daha fazla bilgi için bkz. [klavye kısayollarını tanımlama ve özelleştirme](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).

- Ayarlarınızı değiştirmek için, **Ayarları içeri ve dışarı aktarma** > menü **araçları** ' na gidin.

   İletişim kutularında kullanılabilen seçenekler ve gördüğünüz menü komutlarının adları ve konumları, etkin ayarlarınıza veya sürümüne bağlı olarak **Yardım** altında açıklananlar arasından farklılık gösterebilir.  Daha fazla bilgi için bkz. [Visual STUDIO IDE 'Yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Nasıl yapılır: Iletişim kutusu oluşturma](../windows/creating-a-new-dialog-box.md)<br/>
[İletişim Kutusu Denetimleri](../windows/controls-in-dialog-boxes.md)<br/>
<!--
[Controls](../mfc/controls-mfc.md)<br/>
[Control Classes](../mfc/control-classes.md)<br/>
[Dialog Box Classes](../mfc/dialog-box-classes.md)<br/>
[Dialog Box Controls and Variable Types](../ide/dialog-box-controls-and-variable-types.md)-->
