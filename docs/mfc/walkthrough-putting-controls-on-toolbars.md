---
title: 'İzlenecek yol: Araç çubuklarına denetimler yerleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c134431500ed3e7b2b2229ea5b4b3da7cac6fa48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385089"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme
Bu konuda, bir araç için bir Windows denetimini içeren bir araç çubuğu düğmesi eklemeyi açıklar. MFC içinde bir araç çubuğu düğmesi olmalıdır bir [CMFCToolBarButton sınıfı](../mfc/reference/cmfctoolbarbutton-class.md)-türetilmiş sınıf, örneğin [CMFCToolBarComboBoxButton sınıfı](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [CMFCToolBarEditBoxButton sınıfı](../mfc/reference/cmfctoolbareditboxbutton-class.md), [CMFCDropDownToolbarButton sınıfı](../mfc/reference/cmfcdropdowntoolbarbutton-class.md), veya [CMFCToolBarMenuButton sınıfı](../mfc/reference/cmfctoolbarmenubutton-class.md).  
  
## <a name="adding-controls-to-toolbars"></a>Araç çubuklarına denetimler ekleme  
 Bir araç için bir denetim eklemek için aşağıdaki adımları izleyin:  
  
1.  Bir kukla kaynağı kimliği üst araç çubuğu kaynak düğmesi için ayrılmış. Visual Studio'da araç çubuğu Düzenleyicisi'ni kullanarak düğmeler oluşturma hakkında daha fazla bilgi için bkz: [araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md) konu.  
  
2.  Tüm bit eşlemler üst araç çubuğu düğmesi için araç çubuğu görüntüsünü (düğme simgesi) ayırın.  
  
3.  İşler ileti işleyicisi'ndeki `AFX_WM_RESETTOOLBAR` iletisi, aşağıdakileri yapın:  
  
    1.  Düğme denetimi kullanarak oluşturmak bir `CMFCToolbarButton`-türetilmiş sınıf.  
  
    2.  Sahte düğmesini kullanarak yeni denetimiyle değiştirin [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton). Olduğundan yığınındaki düğme nesnesi oluşturabileceğiniz `ReplaceButton` düğmesi nesnesini kopyalar ve kopyasını tutar.  
  
> [!NOTE]
>  Uygulamanızda Özelleştirme etkinleştirilirse, araç çubuğunu kullanarak sıfırlamanız gerekebilir **sıfırlama** düğmesini **araç çubukları** sekmesinde **Özelleştir** görmek için iletişim kutusu Denetim yeniden derlenmesi sonra uygulamanızdaki güncelleştirildi. Araç çubuğu durumu Windows Kayıt Defteri'nde kaydedilir ve kayıt defteri bilgilerini yüklenen ve sonra uygulanan `ReplaceButton` yöntemi uygulama başlangıcında gerçekleştirilir.  
  
## <a name="toolbar-controls-and-customization"></a>Araç çubuğu denetimleri ve özelleştirme  
 **Komutları** sekmesinde **Özelleştir** iletişim kutusu uygulamada kullanılabilir komutların listesini içerir. Varsayılan olarak, **Özelleştir** iletişim kutusu uygulama menüleri işler ve her menü kategorisi standart araç çubuğu düğmeleri listesini oluşturur. Araç çubuğu denetimleri sağlayan genişletilmiş işlevselliği korumak için standart araç çubuğu düğmesi içinde özel denetimi ile değiştirmelisiniz **Özelleştir** iletişim kutusu.  
  
 Özelleştirme etkinleştirdiğinizde, oluşturduğunuz **Özelleştir** özelleştirme işleyici iletişim kutusunda `OnViewCustomize` kullanarak [CMFCToolBarsCustomizeDialog sınıfı](../mfc/reference/cmfctoolbarscustomizedialog-class.md) sınıfı. Görüntü önce **Özelleştir** çağırarak iletişim kutusu [CMFCToolBarsCustomizeDialog::Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create), çağrı [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) değiştirmek için Yeni Denetim ile standart düğme.  
  
## <a name="example-creating-a-find-combo-box"></a>Örnek: Bul birleşik giriş kutusu oluşturma  
 Bu bölümde nasıl oluşturulacağını açıklar bir `Find` araç çubuğunda görünür ve kısa süre önce kullanılan arama dizelerini içeren birleşik giriş kutusu denetimi. Kullanıcı denetiminde bir dizeyi yazın ve ardından bir belge aramak için enter tuşuna basın veya ana çerçeve odağı dönmek için ESC tuşuna basın. Bu örnek, belge görüntülenir varsayar. bir [CEditView sınıfı](../mfc/reference/ceditview-class.md)-görünüm türetilmiş.  
  
### <a name="creating-the-find-control"></a>Bul denetimi oluşturma  
 İlk olarak, oluşturma `Find` birleşik giriş kutusu denetimi:  
  
1.  Düğme ve kendi komutları için uygulama kaynaklarını ekleyin:  
  
    1.  Uygulama kaynakları ile yeni bir düğme ekleme bir `ID_EDIT_FIND` , uygulamanızdaki bir araç ve araç ile ilişkili tüm bit eşlemler komut kimliği.  
  
    2.  Id_edıt_fınd komutu kimliğiyle yeni menü öğesi oluşturma  
  
    3.  Yeni bir dize "dizesi tabloya text\nFind Bul" ekleyin ve atayın bir `ID_EDIT_FIND_COMBO` komut kimliği. Komut kimliği kullanılan bu kimliği `Find` birleşik giriş kutusu düğmesi.  
  
        > [!NOTE]
        >  Çünkü `ID_EDIT_FIND` tarafından işlenen standart bir komuttur `CEditView`, bu komut için özel bir işleyici uygulamak gerekmez.  Ancak, yeni bir komut işleyici uygulamalıdır `ID_EDIT_FIND_COMBO`.  
  
2.  Yeni bir sınıf oluşturun `CFindComboBox`, türetilmiş [CComboBox sınıfı](../mfc/reference/ccombobox-class.md).  
  
3.  İçinde `CFindComboBox` sınıfı, geçersiz kılma `PreTranslateMessage` sanal yöntemi. Birleşik giriş kutusu işlemek bu yöntemi etkinleştirecek [WM_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280) ileti. Kullanıcı kaçış anahtar değerse (`VK_ESCAPE`), odağı ana çerçeve penceresine geri dönün. Kullanıcı Enter tuşuna değerse (`VK_ENTER`), post için ana çerçeve penceresi bir `WM_COMMAND` içeren ileti `ID_EDIT_FIND_COMBO` komut kimliği.  
  
4.  Sınıfı için oluşturma `Find` türetilmiş birleşik giriş kutusu düğmesi [CMFCToolBarComboBoxButton sınıfı](../mfc/reference/cmfctoolbarcomboboxbutton-class.md). Bu örnekte adlı `CFindComboButton`.  
  
5.  Oluşturucusunun `CMFCToolbarComboBoxButton` üç parametre alır: düğme, düğme görüntü dizini ve birleşik giriş kutusu stilini komut kimliği. Bu parametreleri aşağıdaki gibi ayarlayın:  
  
    1.  Geçirmek `ID_EDIT_FIND_COMBO` olarak komut kimliği.  
  
    2.  Kullanım [CCommandManager::GetCmdImage](http://msdn.microsoft.com/en-us/4094d08e-de74-4398-a483-76d27a742dca) ile `ID_EDIT_FIND` resim dizinini elde edilir.  
  
    3.  Kullanılabilir birleşik giriş kutusu stilleri listesi için bkz: [birleşik giriş kutusu stilleri](../mfc/reference/styles-used-by-mfc.md#combo-box-styles).  
  
6.  İçinde `CFindComboButton` sınıfı, geçersiz kılma `CMFCToolbarComboBoxButton::CreateCombo` yöntemi. Burada oluşturmalısınız `CFindComboButton` nesne ve bir işaretçi döndürün.  
  
7.  Kullanım [ımplement_serıal](../mfc/reference/run-time-object-model-services.md#implement_serial) makrosu açılan düğmesini kalıcı hale getirmek için. Çalışma Alanı Yöneticisi'ni otomatik olarak yükler ve Windows Kayıt Defteri'nde düğmenin durumunu kaydeder.  
  
8.  Uygulama `ID_EDIT_FIND_COMBO` belge görünümünüzde işleyici. Kullanım [CMFCToolBar::GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons) ile `ID_EDIT_FIND_COMBO` tüm almak için `Find` birleşik giriş kutusu düğmeler. Özelleştirme nedeniyle düğmesi aynı komut kimliği ile birçok kopyası olabilir.  
  
9. Id_edıt_fınd ileti işleyicisi'ndeki `OnFind`, kullanın [CMFCToolBar::IsLastCommandFromButton](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton) Bul komutu gönderildiği olup olmadığını belirlemek için `Find` birleşik giriş kutusu düğmesi. Bu durumda, metin bulma ve açılan kutu arama dizesi ekleyin.  
  
### <a name="adding-the-find-control-to-the-main-toolbar"></a>Bulma Denetimi ana araç çubuğuna ekleme  
 Birleşik giriş kutusu düğmesi için araç eklemek için aşağıdaki adımları izleyin:  
  
1.  Uygulama `AFX_WM_RESETTOOLBAR` ileti işleyicisi `OnToolbarReset` ana çerçeve penceresinde.  
  
    > [!NOTE]
    >  Uygulama başlatma sırasında bir araç çubuğu başlatıldığında veya bir araç çubuğunu özelleştirme sırasında sıfırladığınızda framework ana çerçeve penceresi bu iletiyi gönderir. Her iki durumda da, standart araç çubuğu düğmesi ile özel değiştirmelisiniz `Find` birleşik giriş kutusu düğmesi.  
  
2.  İçinde `AFX_WM_RESETTOOLBAR` işleyici, araç kimliği, yani inceleyin, `WPARAM` , `AFX_WM_RESETTOOLBAR` ileti. Araç çubuğu kimliği içeren araç çubuğu eşitse, `Find` birleşik giriş kutusu düğmesi, çağrı [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton) değiştirmek için `Find` düğmesini (diğer bir deyişle, komut kimliği düğmesiyle `ID_EDIT_FIND)` ile bir `CFindComboButton` nesnesi.  
  
    > [!NOTE]
    >  Oluşturabileceğiniz bir `CFindComboBox` olduğundan yığınındaki nesne `ReplaceButton` düğmesi nesnesini kopyalar ve kopyasını tutar.  
  
### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>Özelleştir iletişim kutusu bulma denetim ekleme  
 Özelleştirme işleyicisinde `OnViewCustomize`, çağrı [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) değiştirmek için `Find` düğmesini (diğer bir deyişle, komut kimliği düğmesiyle `ID_EDIT_FIND)` ile bir `CFindComboButton` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../mfc/hierarchy-chart.md)   
 [Sınıfları](../mfc/reference/mfc-classes.md)   
 [CMFCToolBar sınıfı](../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton sınıfı](../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton sınıfı](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCToolBarsCustomizeDialog Sınıfı](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
