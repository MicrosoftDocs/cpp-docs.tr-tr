---
title: 'İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme'
ms.date: 04/25/2019
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
ms.openlocfilehash: 2a801e61c49301d9b8780bbf7eb77025990337ad
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360264"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme

Bu makalede, araç çubuğuna Windows denetimi içeren bir araç çubuğu düğmesi nasıl ekleyeceğiniz açıklanmaktadır. MFC'de, bir araç çubuğu düğmesi [CMFCToolBarButton Sınıfı](../mfc/reference/cmfctoolbarbutton-class.md)türemiş sınıf olmalıdır, örneğin [CMFCToolBarComboBoxButton Class](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [CMFCToolBarEditBoxButton Class](../mfc/reference/cmfctoolbareditboxbutton-class.md), [CMFCDropDropToolbarButton Class](../mfc/reference/cmfcdropdowntoolbarbutton-class.md), veya [CMFCToolBarMenuButton Class](../mfc/reference/cmfctoolbarmenubutton-class.md).

## <a name="adding-controls-to-toolbars"></a>Araç Çubuklarına Denetim Ekleme

Araç çubuğuna denetim eklemek için aşağıdaki adımları izleyin:

1. Ana araç çubuğu kaynağındaki düğme için sahte bir kaynak kimliği ayırın. Visual Studio'daki Araç Çubuğu Düzenleyicisi'ni kullanarak düğme oluşturma hakkında daha fazla bilgi için [Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md) makalesine bakın. **Toolbar Editor**

1. Üst araç çubuğunun tüm bit eşlemlerinde düğme için bir araç çubuğu görüntüsü (düğme simgesi) ayırın.

1. İletiyi işleyen ileti işleyicisinde `AFX_WM_RESETTOOLBAR` aşağıdaki adımları yapın:

   1. Türetilmiş bir `CMFCToolbarButton`sınıf kullanarak düğme denetimini oluştur.

   1. CMFCToolBar kullanarak yeni denetim ile kukla düğmesini [değiştirin::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton). Düğme nesnesini `ReplaceButton` kopyaladığı ve kopyayı koruduğu için düğme nesnesini yığında oluşturabilirsiniz.

> [!NOTE]
> Uygulamanızda özelleştirmeyi etkinleştirdiyseniz, yeniden derledikten sonra uygulamanızdaki güncelleştirilmiş denetimi görmek için **Özelleştir** iletişim kutusunun Araç Çubukları sekmesindeki Araç **Çubuklarını** **Sıfırla** düğmesini kullanarak araç çubuğunu sıfırlamanız gerekebilir. Araç çubuğu durumu Windows kayıt defterine kaydedilir ve uygulama başlatma sırasında `ReplaceButton` yöntem yürütüldükten sonra kayıt defteri bilgileri yüklenir ve uygulanır.

## <a name="toolbar-controls-and-customization"></a>Araç Çubuğu Denetimleri ve Özelleştirme

**Özelleştir** iletişim kutusunun **Komutlar** sekmesi, uygulamada kullanılabilen komutların listesini içerir. Varsayılan olarak, **Özelleştir** iletişim kutusu uygulama menülerini işler ve her menü kategorisinde standart araç çubuğu düğmelerinin bir listesini oluşturur. Araç çubuğu denetimleri tarafından genişletilmiş işlevselliği korumak için, standart araç çubuğu düğmesini **Özelleştir** iletişim kutusundaki özel denetimle değiştirmeniz gerekir.

Özelleştirmeyi etkinleştirdiğinizde, [CMFCToolBarsCustomizeDialog Class](../mfc/reference/cmfctoolbarscustomizedialog-class.md) sınıfını `OnViewCustomize` kullanarak özelleştirme işleyicisi içinde **özelleştir** iletişim kutusunu oluşturursunuz. [CMFCToolBarsCustomizeDialog'u](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create)arayarak **özelleştir** iletişim kutusunu görüntülemeden önce:Oluştur, [CMFCToolBarsCustomizeDialog'u arayın::Standart](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) düğmeyi yeni denetimle değiştirmek için Düğmeyi Değiştir.

## <a name="example-creating-a-find-combo-box"></a>Örnek: Combo Kutusu Bul Oluşturma

Bu bölümde, araç çubuğunda görünen ve en son kullanılan arama dizeleri içeren **bir** bul açılan kutusu denetimi nasıl oluşturulacak açıklanmaktadır. Kullanıcı denetime bir dize yazabilir ve belgeyi aramak için enter tuşuna basabilir veya odağı ana çerçeveye döndürmek için kaçış tuşuna basabilir. Bu örnek, belgenin [CEditView Sınıfı](../mfc/reference/ceditview-class.md)türetilmiş bir görünümde görüntülendiğini varsayar.

### <a name="creating-the-find-control"></a>Bul Denetimini Oluşturma

İlk olarak, açılan kutu denetimini **bul** denetimini oluşturun:

1. Düğmeyi ve komutlarını uygulama kaynaklarına ekleyin:

   1. Uygulama kaynaklarında, uygulamanızdaki araç `ID_EDIT_FIND` çubuğuna ve araç çubuğuyla ilişkili bit eşlemlere komut kimliği içeren yeni bir düğme ekleyin.

   1. `ID_EDIT_FIND` Komut kimliği yle birlikte yeni bir menü öğesi oluşturun.

   1. Dize tablosuna yeni bir dize "Metin bul\nBul" `ID_EDIT_FIND_COMBO` ekleyin ve bir komut kimliği atayın. Bu **kimlik,** bulbo kutusu düğmesinin komut kimliği olarak kullanılacaktır.

        > [!NOTE]
        > Tarafından `ID_EDIT_FIND` işlenen standart bir komut `CEditView`olduğundan, bu komut için özel bir işleyici uygulamanız gerekmez.  Ancak, yeni komut `ID_EDIT_FIND_COMBO`için bir işleyici uygulamanız gerekir.

1. [CComboBox](../mfc/reference/ccombobox-class.md) `CFindComboBox`Class'tan türetilen yeni bir sınıf oluşturun.

1. `CFindComboBox` Sınıfta, `PreTranslateMessage` sanal yöntemi geçersiz kılın. Bu yöntem, açılan kutunun [WM_KEYDOWN](/windows/win32/inputdev/wm-keydown) iletiyi işlemesini sağlar. Kullanıcı kaçış tuşuna vurursa (`VK_ESCAPE`), odağı ana çerçeve penceresine döndürün. Kullanıcı Enter tuşuna (`VK_ENTER`), ana çerçeve penceresine `WM_COMMAND` `ID_EDIT_FIND_COMBO` komut kimliğini içeren bir ileti gönderin.

1. [CMFCToolBarComboBoxButton Class'tan](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)türetilen açılan kutuyu **bul** düğmesi için bir sınıf oluşturun. Bu örnekte, adı `CFindComboButton`.

1. Oluşturucu üç `CMFCToolbarComboBoxButton` parametre alır: düğmenin komut kimliği, düğme görüntü dizini ve açılan kutunun stili. Bu parametreleri aşağıdaki gibi ayarlayın:

   1. Komut `ID_EDIT_FIND_COMBO` kimliğini geçirin.

   1. Görüntü dizini almak için [CCommandManager kullanın::GetCmdImage](reference/internal-classes.md) ile. `ID_EDIT_FIND`

   1. Kullanılabilir açılan kutu stillerinin listesi için [Bkz. Combo-Box Stilleri.](../mfc/reference/styles-used-by-mfc.md#combo-box-styles)

1. `CFindComboButton` Sınıfta, `CMFCToolbarComboBoxButton::CreateCombo` yöntemi geçersiz kılın. Burada nesneyi `CFindComboButton` oluşturmalı ve bir işaretçi döndürmeniz gerekir.

1. Açılan düğmeyi kalıcı hale getirmek için [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) makroyu kullanın. Çalışma alanı yöneticisi otomatik olarak yükler ve düğmenin durumunu Windows kayıt defterine kaydeder.

1. Belge `ID_EDIT_FIND_COMBO` görünümünde işleyiciyi uygulayın. [CMFCToolBar kullanın::GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons) ile `ID_EDIT_FIND_COMBO` tüm combo kutu düğmeleri **bul.** Özelleştirme nedeniyle aynı komut kimliğine sahip bir düğmenin birkaç kopyası olabilir.

1. İleti `ID_EDIT_FIND` `OnFind`işleyicisinde, **bul** komutu combo kutusu düğmesinden gönderilip gönderilmediğini belirlemek için [CMFCToolBar::IsLastCommandFromButton'ı](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton) kullanın. Bu ysa, metni bulun ve arama dizesini açılan kutuya ekleyin.

### <a name="adding-the-find-control-to-the-main-toolbar"></a>Ana Araç Çubuğuna Bul Denetimi Ekleme

Araç çubuğuna açılan kutu düğmesini eklemek için aşağıdaki adımları izleyin:

1. İleti `AFX_WM_RESETTOOLBAR` işleyicisini `OnToolbarReset` ana çerçeve penceresinde uygulayın.

    > [!NOTE]
    > Çerçeve, uygulama başlatma sırasında bir araç çubuğu başolarak başlattığında veya özelleştirme sırasında bir araç çubuğu sıfırlandığında bu iletiyi ana çerçeve penceresine gönderir. Her iki durumda da, standart araç çubuğu düğmesini **özel** bul kutu düğmesiyle değiştirmeniz gerekir.

1. Işleyicide, `AFX_WM_RESETTOOLBAR` araç çubuğu kimliğini, yani AFX_WM_RESETTOOLBAR iletisinin *WPARAM'ını* inceleyin. Araç çubuğu **kimliği,** bul combo kutusu düğmesini içeren araç çubuğununkimliğine eşitse, BUL düğmesini değiştirmek için [CMFCToolBar'ı arayın:Değiştir Düğmesi'ni](../mfc/reference/cmfctoolbar-class.md#replacebutton) **bul** düğmesini (diğer bir cisimle `ID_EDIT_FIND)` `CFindComboButton` komut kimliğine sahip düğme).

    > [!NOTE]
    > Düğme nesnesini `CFindComboBox` `ReplaceButton` kopyaladığı ve kopyayı koruduğu için yığında bir nesne oluşturabilirsiniz.

### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>Özelleştir İletişim Kutusuna Denetim Bul ekleme

Özelleştirme `OnViewCustomize`işleyicisinde [CMFCToolBarsCustomizeDialog'u arayın::Değiştir Düğmesi](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) ile **Bul** düğmesini (diğer bir `ID_EDIT_FIND`deyişle `CFindComboButton` komut kimliğiyle düğme) bir nesneyle değiştirin.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton Sınıfı](../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton Sınıfı](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCToolBarsCustomizeDialog Sınıfı](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
