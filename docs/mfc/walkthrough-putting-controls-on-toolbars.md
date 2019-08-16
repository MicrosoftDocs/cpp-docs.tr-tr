---
title: 'İzlenecek yol: Araç çubuklarına denetimleri yerleştirme'
ms.date: 04/25/2019
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
ms.openlocfilehash: 0c62a8b484cb666427f873244221afec5d4719da
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510731"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>İzlenecek yol: Araç çubuklarına denetimleri yerleştirme

Bu makalede bir araç çubuğuna Windows denetimi içeren bir araç çubuğu düğmesinin nasıl ekleneceği açıklanır. MFC 'de bir araç çubuğu düğmesi [CMFCToolBarButton sınıfında](../mfc/reference/cmfctoolbarbutton-class.md)türetilmiş bir sınıf olmalıdır, örneğin [CMFCToolBarComboBoxButton sınıfı](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [CMFCToolBarEditBoxButton sınıfı](../mfc/reference/cmfctoolbareditboxbutton-class.md), [CMFCDropDownToolbarButton sınıfı](../mfc/reference/cmfcdropdowntoolbarbutton-class.md)veya [ Cmfctoolbarmenubtan sınıfı](../mfc/reference/cmfctoolbarmenubutton-class.md).

## <a name="adding-controls-to-toolbars"></a>Araç çubuklarına denetim ekleme

Bir araç çubuğuna denetim eklemek için aşağıdaki adımları izleyin:

1. Ana araç çubuğu kaynağında düğme için bir kukla kaynak KIMLIĞI ayırın. Visual Studio 'da **araç çubuğu düzenleyicisini** kullanarak düğme oluşturma hakkında daha fazla bilgi Için [Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md) makalesine bakın.

1. Ana araç çubuğunun tüm bit eşlemleriyle ilgili düğme için bir araç çubuğu görüntüsünü (düğme simgesi) ayırın.

1. `AFX_WM_RESETTOOLBAR` İletiyi işleyen ileti işleyicisinde, aşağıdaki adımları uygulayın:

   1. Türetilmiş bir `CMFCToolbarButton`sınıf kullanarak düğme denetimini oluşturun.

   1. İşlevsiz düğmesini [CMFCToolBar:: ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton)kullanarak yeni denetim ile değiştirin. Düğme nesnesini `ReplaceButton` kopyalar ve kopyayı koruduğundan, düğme nesnesini yığında oluşturabilirsiniz.

> [!NOTE]
>  Uygulamanızda özelleştirmeyi etkinleştirdiyseniz, yeniden derlemeden sonra uygulamanızdaki güncelleştirilmiş denetimi görmek için **Özelleştir** Iletişim kutusunun **araç çubukları** sekmesindeki **Sıfırla** düğmesini kullanarak araç çubuğunu sıfırlamanız gerekebilir. Araç çubuğu durumu Windows kayıt defterine kaydedilir ve kayıt defteri bilgileri, uygulama başlatılırken `ReplaceButton` Yöntem yürütüldükten sonra yüklenir ve uygulanır.

## <a name="toolbar-controls-and-customization"></a>Araç çubuğu denetimleri ve özelleştirmesi

**Özelleştir** Iletişim kutusunun **Komutlar** sekmesi, uygulamada kullanılabilen komutların bir listesini içerir. Varsayılan olarak, **Özelleştir** iletişim kutusu uygulama menülerini işler ve her bir menü kategorisinde Standart araç çubuğu düğmelerinin bir listesini oluşturur. Araç çubuğu denetimlerinin sağladığı Genişletilmiş işlevselliği korumak için, Standart araç çubuğu düğmesini **Özelleştir** iletişim kutusundaki özel denetimle değiştirmelisiniz.

Özelleştirmeyi etkinleştirdiğinizde, [CMFCToolBarsCustomizeDialog Class](../mfc/reference/cmfctoolbarscustomizedialog-class.md) sınıfını kullanarak özelleştirme işleyicisinde `OnViewCustomize` özelleştirme iletişim kutusunu oluşturursunuz. [CMFCToolBarsCustomizeDialog:: Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create)öğesini çağırarak **Özelleştir** iletişim kutusunu görüntülemeden önce, standart düğmeyi yeni denetimle değiştirmek Için [CMFCToolBarsCustomizeDialog:: ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) öğesini çağırın.

## <a name="example-creating-a-find-combo-box"></a>Örnek: Find açılan kutusu oluşturma

Bu bölümde, bir araç çubuğunda görüntülenen ve en son kullanılan arama dizelerini içeren bir arama açılan kutusu denetiminin nasıl oluşturulacağı açıklanmaktadır. Kullanıcı denetimde bir dize yazabilir ve sonra bir belge aramak için ENTER tuşuna basabilir ya da odağı ana çerçeveye döndürmek için çıkış tuşuna basabilir. Bu örnek, belgenin bir [CEditView sınıfı](../mfc/reference/ceditview-class.md)türetilmiş görünümünde görüntülendiğini varsayar.

### <a name="creating-the-find-control"></a>Bul denetimi oluşturma

İlk olarak, **bulma** açılan kutusu denetimini oluşturun:

1. Uygulama kaynaklarına düğme ve komutlarını ekleyin:

   1. Uygulama kaynaklarında, uygulamanızdaki bir araç çubuğuna ve araç çubuğuyla ilişkili `ID_EDIT_FIND` tüm bit eşlemlere komut kimliğiyle yeni bir düğme ekleyin.

   1. `ID_EDIT_FIND` Komut kimliğiyle yeni bir menü öğesi oluşturun.

   1. Dize tablosuna "Text\nFind bul" dizesini ekleyin ve bir `ID_EDIT_FIND_COMBO` komut kimliği atayın. Bu KIMLIK, açılan kutu **bul** DÜĞMESININ komut kimliği olarak kullanılacaktır.

        > [!NOTE]
        > `ID_EDIT_FIND` Tarafından`CEditView`işlenen standart bir komut olduğundan, bu komut için özel bir işleyici uygulamanız gerekmez.  Ancak, yeni komut `ID_EDIT_FIND_COMBO`için bir işleyici uygulamanız gerekir.

1. [CComboBox sınıfından](../mfc/reference/ccombobox-class.md)türetilmiş yeni `CFindComboBox`bir sınıf oluşturun.

1. Sınıfında, `PreTranslateMessage` sanal yöntemi geçersiz kılın. `CFindComboBox` Bu yöntem, [WM_KEYDOWN](/windows/win32/inputdev/wm-keydown) iletisini işlemek için Birleşik giriş kutusunun etkinleştirecektir. Kullanıcı çıkış anahtarını (`VK_ESCAPE`) ziyaret ederseniz, odağı ana çerçeve penceresine döndürün. Kullanıcı ENTER tuşuna (`VK_ENTER`) rastluyorsa, ana çerçeve penceresine `ID_EDIT_FIND_COMBO` komut kimliğini içeren bir `WM_COMMAND` ileti gönderin.

1. [CMFCToolBarComboBoxButton sınıfından](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)türetilen Birleşik giriş kutusu **bul** düğmesi için bir sınıf oluşturun. Bu örnekte, olarak adlandırılmıştır `CFindComboButton`.

1. Öğesinin `CMFCToolbarComboBoxButton` Oluşturucusu üç parametre alır: düğmenin komut kimliği, düğme görüntüsü dizini ve Birleşik giriş kutusunun stili. Bu parametreleri aşağıdaki şekilde ayarlayın:

   1. Komutunu komut kimliği olarak geçirin. `ID_EDIT_FIND_COMBO`

   1. Görüntü dizinini almak `ID_EDIT_FIND` için [CCommandManager:: GetCmdImage](reference/internal-classes.md) komutunu kullanın.

   1. Kullanılabilir Birleşik giriş kutusu stillerinin listesi için bkz. [Birleşik giriş kutusu stilleri](../mfc/reference/styles-used-by-mfc.md#combo-box-styles).

1. Sınıfında, `CMFCToolbarComboBoxButton::CreateCombo` yöntemini geçersiz kılın. `CFindComboButton` Burada `CFindComboButton` nesneyi oluşturmanız ve ona bir işaretçi döndürmelisiniz.

1. Birleşik düğme ' i kalıcı hale getirmek için [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) makrosunu kullanın. Çalışma alanı yöneticisi, Windows kayıt defteri 'nde düğmenin durumunu otomatik olarak yükler ve kaydeder.

1. `ID_EDIT_FIND_COMBO` İşleyiciyi belge görünüminizde uygulayın. Tüm **arama** açılan kutusu düğmelerini almak `ID_EDIT_FIND_COMBO` için [CMFCToolBar:: GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons) komutunu kullanın. Özelleştirme nedeniyle aynı komut KIMLIĞINE sahip bir düğmenin birkaç kopyası olabilir.

1. İleti işleyicisinde `OnFind`, Find komutunun açılan kutuyu bul düğmesinden gönderilip gönderilmediğini öğrenmek için [CMFCToolBar:: IsLastCommandFromButton](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton) komutunu kullanın. `ID_EDIT_FIND` Bu durumda, metni bulun ve arama dizesini Birleşik giriş kutusuna ekleyin.

### <a name="adding-the-find-control-to-the-main-toolbar"></a>Ana araç çubuğuna bulma denetimini ekleme

Araç çubuğuna Birleşik giriş kutusu düğmesini eklemek için aşağıdaki adımları izleyin:

1. Ana çerçeve penceresinde `OnToolbarReset`iletiişleyicisiniuygulayın `AFX_WM_RESETTOOLBAR` .

    > [!NOTE]
    > Çerçeve, uygulama başlangıcında bir araç çubuğu başlatıldığında veya özelleştirme sırasında bir araç çubuğu sıfırlandığında, bu iletiyi ana çerçeve penceresine gönderir. Her iki durumda da, Standart araç çubuğu düğmesini özel **bul** açılan kutusu düğmesi ile değiştirmelisiniz.

1. İşleyicisinde, araç çubuğu kimliğini, diğer bir deyişle, AFX_WM_RESETTOOLBAR iletisinin wParam ' ı inceleyin. `AFX_WM_RESETTOOLBAR` Araç çubuğu kimliği, açılan kutuyu **bul** düğmesini içeren araç çubuğundan eşitse, **bul** düğmesini (diğer bir deyişle, bir `ID_EDIT_FIND)` `CFindComboButton` nesnesiyle komut kimliği olan düğme) değiştirmek için [CMFCToolBar:: ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton) öğesini çağırın.

    > [!NOTE]
    > Düğme nesnesini `ReplaceButton` kopyalayan ve `CFindComboBox` kopyayı koruduğu için yığında bir nesne oluşturabilirsiniz.

### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>Özelleştirme Iletişim kutusuna bulma denetimini ekleme

Özelleştirme işleyicisinde `OnViewCustomize`, **bul** düğmesini (diğer bir deyişle, komut kimliği `ID_EDIT_FIND`olan düğme) bir `CFindComboButton` nesneyle değiştirmek için [CMFCToolBarsCustomizeDialog:: ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) öğesini çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton Sınıfı](../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton Sınıfı](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCToolBarsCustomizeDialog Sınıfı](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
