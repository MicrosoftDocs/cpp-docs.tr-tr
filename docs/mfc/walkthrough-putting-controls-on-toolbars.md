---
description: 'Daha fazla bilgi edinin: Izlenecek yol: denetimleri araç çubuklarına yerleştirme'
title: 'İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme'
ms.date: 04/25/2019
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
ms.openlocfilehash: eafb1afa2ffffeaaabfc6b463e2951d8d532db58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143058"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme

Bu makalede bir araç çubuğuna Windows denetimi içeren bir araç çubuğu düğmesinin nasıl ekleneceği açıklanır. MFC 'de bir araç çubuğu düğmesi [CMFCToolBarButton sınıfında](../mfc/reference/cmfctoolbarbutton-class.md)türetilmiş bir sınıf olmalıdır, örneğin [CMFCToolBarComboBoxButton Class](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [CMFCToolBarEditBoxButton Class](../mfc/reference/cmfctoolbareditboxbutton-class.md), [CMFCDropDownToolbarButton Class](../mfc/reference/cmfcdropdowntoolbarbutton-class.md)veya [cmfctoolbarmenubtan Class](../mfc/reference/cmfctoolbarmenubutton-class.md).

## <a name="adding-controls-to-toolbars"></a>Araç çubuklarına denetim ekleme

Bir araç çubuğuna denetim eklemek için aşağıdaki adımları izleyin:

1. Ana araç çubuğu kaynağında düğme için bir kukla kaynak KIMLIĞI ayırın. Visual Studio 'da **araç çubuğu düzenleyicisini** kullanarak düğme oluşturma hakkında daha fazla bilgi Için [Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md) makalesine bakın.

1. Ana araç çubuğunun tüm bit eşlemleriyle ilgili düğme için bir araç çubuğu görüntüsünü (düğme simgesi) ayırın.

1. İletiyi işleyen ileti işleyicisinde `AFX_WM_RESETTOOLBAR` , aşağıdaki adımları uygulayın:

   1. Türetilmiş bir sınıf kullanarak düğme denetimini oluşturun `CMFCToolbarButton` .

   1. İşlevsiz düğmesini [CMFCToolBar:: ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton)kullanarak yeni denetim ile değiştirin. Düğme nesnesini `ReplaceButton` kopyalar ve kopyayı koruduğundan, düğme nesnesini yığında oluşturabilirsiniz.

> [!NOTE]
> Uygulamanızda özelleştirmeyi etkinleştirdiyseniz, yeniden derlemeden sonra uygulamanızdaki güncelleştirilmiş denetimi görmek için **Özelleştir** Iletişim kutusunun **araç çubukları** sekmesindeki **Sıfırla** düğmesini kullanarak araç çubuğunu sıfırlamanız gerekebilir. Araç çubuğu durumu Windows kayıt defterine kaydedilir ve kayıt defteri bilgileri, `ReplaceButton` uygulama başlatılırken Yöntem yürütüldükten sonra yüklenir ve uygulanır.

## <a name="toolbar-controls-and-customization"></a>Araç çubuğu denetimleri ve özelleştirmesi

**Özelleştir** Iletişim kutusunun **Komutlar** sekmesi, uygulamada kullanılabilen komutların bir listesini içerir. Varsayılan olarak, **Özelleştir** iletişim kutusu uygulama menülerini işler ve her bir menü kategorisinde Standart araç çubuğu düğmelerinin bir listesini oluşturur. Araç çubuğu denetimlerinin sağladığı Genişletilmiş işlevselliği korumak için, Standart araç çubuğu düğmesini **Özelleştir** iletişim kutusundaki özel denetimle değiştirmelisiniz.

Özelleştirmeyi etkinleştirdiğinizde, CMFCToolBarsCustomizeDialog Class sınıfını kullanarak özelleştirme **işleyicisinde özelleştirme iletişim kutusunu** oluşturursunuz `OnViewCustomize` . [](../mfc/reference/cmfctoolbarscustomizedialog-class.md) [CMFCToolBarsCustomizeDialog:: Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create)öğesini çağırarak **Özelleştir** iletişim kutusunu görüntülemeden önce, standart düğmeyi yeni denetimle değiştirmek Için [CMFCToolBarsCustomizeDialog:: ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) öğesini çağırın.

## <a name="example-creating-a-find-combo-box"></a>Örnek: Find açılan kutusu oluşturma

Bu bölümde, bir araç çubuğunda görüntülenen ve en son kullanılan arama dizelerini içeren bir **arama açılan kutusu** denetiminin nasıl oluşturulacağı açıklanmaktadır. Kullanıcı denetimde bir dize yazabilir ve sonra bir belge aramak için ENTER tuşuna basabilir ya da odağı ana çerçeveye döndürmek için çıkış tuşuna basabilir. Bu örnek, belgenin bir [CEditView sınıfı](../mfc/reference/ceditview-class.md)türetilmiş görünümünde görüntülendiğini varsayar.

### <a name="creating-the-find-control"></a>Bul denetimi oluşturma

İlk olarak, **bulma** açılan kutusu denetimini oluşturun:

1. Uygulama kaynaklarına düğme ve komutlarını ekleyin:

   1. Uygulama kaynaklarında, `ID_EDIT_FIND` uygulamanızdaki bir araç çubuğuna ve araç çubuğuyla ilişkili tüm bit eşlemlere komut kimliğiyle yeni bir düğme ekleyin.

   1. Komut KIMLIĞIYLE yeni bir menü öğesi oluşturun `ID_EDIT_FIND` .

   1. Dize tablosuna "text\nFind bul" dizesini ekleyin ve bir `ID_EDIT_FIND_COMBO` komut kimliği atayın. Bu KIMLIK, açılan kutu **bul** DÜĞMESININ komut kimliği olarak kullanılacaktır.

        > [!NOTE]
        > `ID_EDIT_FIND`Tarafından işlenen standart bir komut olduğundan `CEditView` , bu komut için özel bir işleyici uygulamanız gerekmez.  Ancak, yeni komut için bir işleyici uygulamanız gerekir `ID_EDIT_FIND_COMBO` .

1. `CFindComboBox` [CComboBox sınıfından](../mfc/reference/ccombobox-class.md)türetilmiş yeni bir sınıf oluşturun.

1. `CFindComboBox`Sınıfında, sanal yöntemi geçersiz kılın `PreTranslateMessage` . Bu yöntem, [WM_KEYDOWN](/windows/win32/inputdev/wm-keydown) iletisini işlemek için Birleşik giriş kutusunun etkinleştirecektir. Kullanıcı çıkış anahtarını () ziyaret ederseniz `VK_ESCAPE` , odağı ana çerçeve penceresine döndürün. Kullanıcı ENTER tuşuna () rastluyorsa `VK_ENTER` , ana çerçeve penceresine `WM_COMMAND` komut kimliğini içeren bir ileti gönderin `ID_EDIT_FIND_COMBO` .

1. [CMFCToolBarComboBoxButton sınıfından](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)türetilen Birleşik giriş kutusu **bul** düğmesi için bir sınıf oluşturun. Bu örnekte, olarak adlandırılmıştır `CFindComboButton` .

1. Öğesinin Oluşturucusu `CMFCToolbarComboBoxButton` üç parametre alır: düğmenin komut kimliği, düğme görüntüsü dizini ve Birleşik giriş kutusunun stili. Bu parametreleri aşağıdaki şekilde ayarlayın:

   1. `ID_EDIT_FIND_COMBO`Komutunu komut kimliği olarak geçirin.

   1. Görüntü dizinini almak için [CCommandManager:: GetCmdImage](reference/internal-classes.md) komutunu kullanın `ID_EDIT_FIND` .

   1. Kullanılabilir Birleşik giriş kutusu stillerinin listesi için bkz. [Birleşik giriş kutusu stilleri](../mfc/reference/styles-used-by-mfc.md#combo-box-styles).

1. Sınıfında, `CFindComboButton` yöntemini geçersiz kılın `CMFCToolbarComboBoxButton::CreateCombo` . Burada `CFindComboButton` nesneyi oluşturmanız ve ona bir işaretçi döndürmelisiniz.

1. Birleşik düğme kalıcı hale getirmek için [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) makrosunu kullanın. Çalışma alanı yöneticisi, Windows kayıt defteri 'nde düğmenin durumunu otomatik olarak yükler ve kaydeder.

1. `ID_EDIT_FIND_COMBO`İşleyiciyi belge görünüminizde uygulayın. Tüm arama açılan kutusu düğmelerini almak için [CMFCToolBar:: GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons) komutunu kullanın `ID_EDIT_FIND_COMBO` .  Özelleştirme nedeniyle aynı komut KIMLIĞINE sahip bir düğmenin birkaç kopyası olabilir.

1. `ID_EDIT_FIND`İleti işleyicisinde `OnFind` , Find komutunun açılan kutuyu **bul** düğmesinden gönderilip gönderilmediğini öğrenmek için [CMFCToolBar:: IsLastCommandFromButton](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton) komutunu kullanın. Bu durumda, metni bulun ve arama dizesini Birleşik giriş kutusuna ekleyin.

### <a name="adding-the-find-control-to-the-main-toolbar"></a>Ana araç çubuğuna bulma denetimini ekleme

Araç çubuğuna Birleşik giriş kutusu düğmesini eklemek için aşağıdaki adımları izleyin:

1. `AFX_WM_RESETTOOLBAR` `OnToolbarReset` Ana çerçeve penceresinde ileti işleyicisini uygulayın.

    > [!NOTE]
    > Çerçeve, uygulama başlangıcında bir araç çubuğu başlatıldığında veya özelleştirme sırasında bir araç çubuğu sıfırlandığında, bu iletiyi ana çerçeve penceresine gönderir. Her iki durumda da, Standart araç çubuğu düğmesini özel **bul** açılan kutusu düğmesi ile değiştirmelisiniz.

1. İşleyicisinde, `AFX_WM_RESETTOOLBAR` araç çubuğu kimliğini, diğer bir deyişle AFX_WM_RESETTOOLBAR Iletisinin *wParam* ' ı inceleyin. Araç çubuğu KIMLIĞI, açılan kutuyu **bul** düğmesini içeren araç çubuğundan eşitse, **bul** düğmesini (diğer bir deyişle, bir nesnesiyle komut kimliği olan düğme) değiştirmek için [CMFCToolBar:: ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton) öğesini çağırın `ID_EDIT_FIND)` `CFindComboButton` .

    > [!NOTE]
    > `CFindComboBox` `ReplaceButton` Düğme nesnesini kopyalayan ve kopyayı koruduğu için yığında bir nesne oluşturabilirsiniz.

### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>Özelleştirme Iletişim kutusuna bulma denetimini ekleme

Özelleştirme işleyicisinde `OnViewCustomize` , **bul** düğmesini (diğer bir DEYIŞLE, komut kimliği olan düğme) bir nesneyle değiştirmek için [CMFCToolBarsCustomizeDialog:: ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) öğesini çağırın `ID_EDIT_FIND` `CFindComboButton` .

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar sınıfı](../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton sınıfı](../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton sınıfı](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCToolBarsCustomizeDialog sınıfı](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
