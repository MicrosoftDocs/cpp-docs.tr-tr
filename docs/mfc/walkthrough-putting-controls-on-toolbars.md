---
title: 'İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme'
ms.date: 09/20/2018
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
ms.openlocfilehash: 3e0cc066e39cc71833e2061a1964619d04a80be3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580303"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme

Bu makalede, bir Windows denetimine bir araç çubuğu içeren bir araç çubuğu düğmesi eklemeyi açıklar. MFC içinde araç çubuğu düğmesi olmalıdır bir [CMFCToolBarButton sınıfı](../mfc/reference/cmfctoolbarbutton-class.md)-türetilmiş sınıf, örneğin [CMFCToolBarComboBoxButton sınıfı](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [CMFCToolBarEditBoxButton sınıfı](../mfc/reference/cmfctoolbareditboxbutton-class.md), [CMFCDropDownToolbarButton sınıfı](../mfc/reference/cmfcdropdowntoolbarbutton-class.md), veya [CMFCToolBarMenuButton sınıfı](../mfc/reference/cmfctoolbarmenubutton-class.md).

## <a name="adding-controls-to-toolbars"></a>Araç çubuklarına denetimler ekleme

Araç çubuğuna bir denetim eklemek için aşağıdaki adımları izleyin:

1. Üst araç çubuğunda kaynağında düğme için bir işlevsiz kaynak kimliği saklı tutarız. Düğmeleri kullanarak oluşturma hakkında daha fazla bilgi için **araç çubuğu Düzenleyicisi** Visual Studio'da görmek [araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md) makalesi.

1. Tüm bit eşlemler üst araç çubuğu düğmesi için araç çubuğu görüntüsü (düğmesinin simgesi) ayırın.

1. İşler ileti işleyicisi `AFX_WM_RESETTOOLBAR` iletisi, aşağıdaki adımları uygulayın:

   1. Düğme denetimini kullanarak oluşturmak bir `CMFCToolbarButton`-türetilmiş sınıf.

   1. İşlevsiz düğmesini kullanarak yeni denetim ile değiştirin. [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton). Yığında bir düğme nesnesi olduğundan oluşturabilirsiniz `ReplaceButton` düğmesi nesnesini kopyalar ve kopyayı korur.

> [!NOTE]
>  Uygulamanızda Özelleştirme etkinleştirilirse, araç çubuğunu kullanarak sıfırlamanız gerekebilir **sıfırlama** düğmesini **araç çubukları** sekmesinde **Özelleştir** görmek için iletişim kutusu uygulamanızı yeniden derlemeden sonra denetiminde güncelleştirildi. Araç çubuğu durumu Windows kayıt defterinde kaydedilir ve kayıt defteri bilgilerini yüklenir ve sonra uygulanan `ReplaceButton` yöntemi, uygulama başlatma sırasında yürütülür.

## <a name="toolbar-controls-and-customization"></a>Araç çubuğu denetimleri ve özelleştirme

**Komutları** sekmesinde **Özelleştir** iletişim kutusu uygulamada kullanılabilir komutların listesini içerir. Varsayılan olarak, **Özelleştir** iletişim kutusunda uygulama menüleri işler ve her bir kategorideki menü standart araç çubuğu düğmeleri listesini oluşturur. Araç çubuğu denetimleri sağlayan genişletilmiş işlevselliği tutmak için standart araç çubuğu düğmesi içinde özel denetimi ile değiştirmelisiniz **Özelleştir** iletişim kutusu.

Özelleştirme etkinleştirdiğinizde, oluşturduğunuz **Özelleştir** özelleştirme işleyici iletişim kutusunda `OnViewCustomize` kullanarak [CMFCToolBarsCustomizeDialog sınıfı](../mfc/reference/cmfctoolbarscustomizedialog-class.md) sınıfı. Görüntü önce **Özelleştir** iletişim kutusunu çağırarak [CMFCToolBarsCustomizeDialog::Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create), çağrı [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) değiştirmek için Yeni denetimi ile standart düğmesi.

## <a name="example-creating-a-find-combo-box"></a>Örnek: Bul birleşik giriş kutusu oluşturma

Bu bölüm nasıl oluşturulacağını açıklar bir **Bul** araç çubuğunda görünür ve son kullanılan arama dizelerini içeren birleşik giriş kutusu denetimi. Kullanıcı denetiminde bir dizeyi yazın ve ardından bir belge aramak için enter tuşuna basın veya ana kareye odağı dönmek için ESC tuşuna basın. Bu örnekte, belgeyi görüntülendiğini varsayılmaktadır. bir [CEditView sınıfı](../mfc/reference/ceditview-class.md)-görünüm türetilmiş.

### <a name="creating-the-find-control"></a>Bul denetiminin oluşturma

İlk olarak, oluşturma **Bul** birleşik giriş kutusu denetimi:

1. Düğme ve kendi komutları için uygulama kaynakları ekleyin:

   1. Uygulama kaynakları ile yeni bir düğme eklemek bir `ID_EDIT_FIND` uygulamanızdaki bir araç çubuğuna ve araç ile ilişkili herhangi bir bit eşlemler komut kimliği.

   1. Yeni Menü öğesiyle oluşturma `ID_EDIT_FIND` komut kimliği.

   1. Yeni bir dize "için dize tablosu text\nFind bulma" ekleyin ve atayın bir `ID_EDIT_FIND_COMBO` komut kimliği. Bu kimliği komut kimliği kullanılacak **Bul** birleşik giriş kutusu düğmesi.

        > [!NOTE]
        > Çünkü `ID_EDIT_FIND` tarafından işlenen standart bir komuttur `CEditView`, özel bir işleyici bu komut için uygulama gerekmez.  Ancak, yeni bir komut işleyici uygulamalıdır `ID_EDIT_FIND_COMBO`.

1. Yeni bir sınıf oluşturun `CFindComboBox`, türetilmiş [CComboBox sınıfı](../mfc/reference/ccombobox-class.md).

1. İçinde `CFindComboBox` sınıfı, geçersiz kılma `PreTranslateMessage` sanal yöntem. Bu yöntem işlemek birleşik giriş kutusu tanıyacak [WM_KEYDOWN](/windows/desktop/inputdev/wm-keydown) ileti. Kullanıcı escape tuşu değerse (`VK_ESCAPE`), odak noktası ana çerçeve penceresine geri dönün. Kullanıcı Enter tuşunu değerse (`VK_ENTER`), sonrası ana çerçeve penceresine bir `WM_COMMAND` içeren ileti `ID_EDIT_FIND_COMBO` komut kimliği.

1. Sınıfı için oluşturma **Bul** birleşik giriş kutusu düğmesi, türetilen [CMFCToolBarComboBoxButton sınıfı](../mfc/reference/cmfctoolbarcomboboxbutton-class.md). Bu örnekte, adlı `CFindComboButton`.

1. Oluşturucusuna `CMFCToolbarComboBoxButton` üç parametreleri alır: düğme, düğme görüntü dizini ve birleşik giriş kutusunun stili komut kimliği. Bu parametreleri aşağıdaki gibi ayarlayın:

   1. Geçirmek `ID_EDIT_FIND_COMBO` olarak komut kimliği.

   1. Kullanım [CCommandManager::GetCmdImage](reference/internal-classes.md) ile `ID_EDIT_FIND` resim dizinini alınamıyor.

   1. Kullanılabilir birleşik giriş kutusu stilleri bir listesi için bkz. [birleşik giriş kutusu stilleri](../mfc/reference/styles-used-by-mfc.md#combo-box-styles).

1. İçinde `CFindComboButton` sınıfı, geçersiz kılma `CMFCToolbarComboBoxButton::CreateCombo` yöntemi. Burada oluşturmalısınız `CFindComboButton` nesne ve ona bir işaretçi döndürür.

1. Kullanım [ımplement_serıal](../mfc/reference/run-time-object-model-services.md#implement_serial) açılan düğmeye kalıcı hale getirmek için makro. Çalışma Alanı Yöneticisi'ni otomatik olarak yükler ve düğmenin durumu Windows kayıt defterine kaydeder.

1. Uygulama `ID_EDIT_FIND_COMBO` belge görünümünüzdeki işleyici. Kullanım [CMFCToolBar::GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons) ile `ID_EDIT_FIND_COMBO` tüm almak için **Bul** birleşik giriş kutusu düğmeleri. Özelleştirme nedeniyle çok sayıda kopya aynı komutu kimlikli bir düğmenin olabilir.

1. İçinde `ID_EDIT_FIND` ileti işleyicisi `OnFind`, kullanın [CMFCToolBar::IsLastCommandFromButton](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton) FIND komutu gönderildiği olup olmadığını belirlemek için **Bul** birleşik giriş kutusu düğmesi. Bu durumda, metni bulmak ve birleşik giriş kutusuna arama dizesini ekleyin.

### <a name="adding-the-find-control-to-the-main-toolbar"></a>Ana araç çubuğuna bulma denetimi ekleme

Birleşik giriş kutusu düğmesi eklemek için bu adımları izleyin:

1. Uygulama `AFX_WM_RESETTOOLBAR` ileti işleyicisi `OnToolbarReset` ana çerçeve penceresinde.

    > [!NOTE]
    > Framework ana çerçeve penceresine araç çubuğu uygulaması başlatılırken başlatıldığında veya araç çubuğunu özelleştirme sırasında sıfırlandığında bu iletiyi gönderir. Her iki durumda da, standart araç çubuğu düğmesi ile özel değiştirmelisiniz **Bul** birleşik giriş kutusu düğmesi.

1. İçinde `AFX_WM_RESETTOOLBAR` işleyicisi, diğer bir deyişle araç Kimliğine inceleyin, *WPARAM* AFX_WM_RESETTOOLBAR ileti. Araç çubuğu kimliği içeren araç çubuğu eşitse, **Bul** birleşik giriş kutusu düğmesi, çağrı [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton) değiştirilecek **bulmak** düğmesine (diğer bir deyişle, Komut Kimliği düğmeyle `ID_EDIT_FIND)` ile bir `CFindComboButton` nesne.

    > [!NOTE]
    > Oluşturulabilir bir `CFindComboBox` çünkü yığında nesne `ReplaceButton` düğmesi nesnesini kopyalar ve kopyayı korur.

### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>Bul denetiminin özelleştirme iletişim kutusuna ekleme

Özelleştirme işleyicisinde `OnViewCustomize`, çağrı [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) değiştirmek için **Bul** düğmesine (diğer bir deyişle, komut kimliği düğmeyle `ID_EDIT_FIND`) bir ile`CFindComboButton` nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton Sınıfı](../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton Sınıfı](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCToolBarsCustomizeDialog Sınıfı](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
