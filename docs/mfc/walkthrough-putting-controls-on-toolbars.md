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
ms.openlocfilehash: 258d8f10238db58be26743694943ae3bd6abc20e
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693581"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme
Bu konuda, bir Windows denetimine bir araç çubuğu içeren bir araç çubuğu düğmesi eklemeyi açıklar. MFC içinde araç çubuğu düğmesi olmalıdır bir [CMFCToolBarButton sınıfı](../mfc/reference/cmfctoolbarbutton-class.md)-türetilmiş sınıf, örneğin [CMFCToolBarComboBoxButton sınıfı](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [CMFCToolBarEditBoxButton sınıfı](../mfc/reference/cmfctoolbareditboxbutton-class.md), [CMFCDropDownToolbarButton sınıfı](../mfc/reference/cmfcdropdowntoolbarbutton-class.md), veya [CMFCToolBarMenuButton sınıfı](../mfc/reference/cmfctoolbarmenubutton-class.md).  
  
## <a name="adding-controls-to-toolbars"></a>Araç çubuklarına denetimler ekleme  
 Araç çubuğuna bir denetim eklemek için aşağıdaki adımları izleyin:  
  
1.  Üst araç çubuğunda kaynağında düğme için bir işlevsiz kaynak kimliği saklı tutarız. Visual Studio'da araç çubuğu Düzenleyicisi'ni kullanarak düğme oluşturma hakkında daha fazla bilgi için bkz. [araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md) konu.  
  
2.  Tüm bit eşlemler üst araç çubuğu düğmesi için araç çubuğu görüntüsü (düğmesinin simgesi) ayırın.  
  
3.  AFX_WM_RESETTOOLBAR iletiyi işleyen ileti işleyicisi, aşağıdakileri yapın:  
  
    1.  Düğme denetimini kullanarak oluşturmak bir `CMFCToolbarButton`-türetilmiş sınıf.  
  
    2.  İşlevsiz düğmesini kullanarak yeni denetim ile değiştirin. [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton). Yığında bir düğme nesnesi olduğundan oluşturabilirsiniz `ReplaceButton` düğmesi nesnesini kopyalar ve kopyayı korur.  
  
> [!NOTE]
>  Uygulamanızda Özelleştirme etkinleştirilirse, araç çubuğunu kullanarak sıfırlamanız gerekebilir **sıfırlama** düğmesini **araç çubukları** sekmesinde **Özelleştir** görmek için iletişim kutusu uygulamanızı yeniden derlemeden sonra denetiminde güncelleştirildi. Araç çubuğu durumu Windows kayıt defterinde kaydedilir ve kayıt defteri bilgilerini yüklenir ve sonra uygulanan `ReplaceButton` yöntemi, uygulama başlatma sırasında yürütülür.  
  
## <a name="toolbar-controls-and-customization"></a>Araç çubuğu denetimleri ve özelleştirme  
 **Komutları** sekmesinde **Özelleştir** iletişim kutusu uygulamada kullanılabilir komutların listesini içerir. Varsayılan olarak, **Özelleştir** iletişim kutusunda uygulama menüleri işler ve her bir kategorideki menü standart araç çubuğu düğmeleri listesini oluşturur. Araç çubuğu denetimleri sağlayan genişletilmiş işlevselliği korumak için standart araç çubuğu düğmesi içinde özel denetimi ile değiştirmelisiniz **Özelleştir** iletişim kutusu.  
  
 Özelleştirme etkinleştirdiğinizde, oluşturduğunuz **Özelleştir** özelleştirme işleyici iletişim kutusunda `OnViewCustomize` kullanarak [CMFCToolBarsCustomizeDialog sınıfı](../mfc/reference/cmfctoolbarscustomizedialog-class.md) sınıfı. Görüntü önce **Özelleştir** iletişim kutusunu çağırarak [CMFCToolBarsCustomizeDialog::Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create), çağrı [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) değiştirmek için Yeni denetimi ile standart düğmesi.  
  
## <a name="example-creating-a-find-combo-box"></a>Örnek: Bul birleşik giriş kutusu oluşturma  
 Bu bölüm nasıl oluşturulacağını açıklar bir **Bul** araç çubuğunda görünür ve son kullanılan arama dizelerini içeren birleşik giriş kutusu denetimi. Kullanıcı denetiminde bir dizeyi yazın ve ardından bir belge aramak için enter tuşuna basın veya ana kareye odağı dönmek için ESC tuşuna basın. Bu örnekte, belgeyi görüntülendiğini varsayılmaktadır. bir [CEditView sınıfı](../mfc/reference/ceditview-class.md)-görünüm türetilmiş.  
  
### <a name="creating-the-find-control"></a>Bul denetiminin oluşturma  
 İlk olarak, oluşturma `Find` birleşik giriş kutusu denetimi:  
  
1.  Düğme ve kendi komutları için uygulama kaynakları ekleyin:  
  
    1.  Uygulama kaynakları ile yeni bir düğme eklemek bir `ID_EDIT_FIND` uygulamanızdaki bir araç çubuğuna ve araç ile ilişkili herhangi bir bit eşlemler komut kimliği.  
  
    2.  Id_edıt_fınd komutu kimliği ile yeni bir menü öğesi oluşturma  
  
    3.  Yeni bir dize "için dize tablosu text\nFind bulma" ekleyin ve atayın bir `ID_EDIT_FIND_COMBO` komut kimliği. Bu kimliği komut kimliği kullanılacak `Find` birleşik giriş kutusu düğmesi.  
  
        > [!NOTE]
        >  Çünkü `ID_EDIT_FIND` tarafından işlenen standart bir komuttur `CEditView`, özel bir işleyici bu komut için uygulama gerekmez.  Ancak, yeni bir komut işleyici uygulamalıdır `ID_EDIT_FIND_COMBO`.  
  
2.  Yeni bir sınıf oluşturun `CFindComboBox`, türetilmiş [CComboBox sınıfı](../mfc/reference/ccombobox-class.md).  
  
3.  İçinde `CFindComboBox` sınıfı, geçersiz kılma `PreTranslateMessage` sanal yöntem. Bu yöntem işlemek birleşik giriş kutusu tanıyacak [WM_KEYDOWN](/windows/desktop/inputdev/wm-keydown) ileti. Kullanıcı escape tuşu değerse (`VK_ESCAPE`), odak noktası ana çerçeve penceresine geri dönün. Kullanıcı Enter tuşunu değerse (`VK_ENTER`), ana çerçeve penceresine içeren WM_COMMAND ileti gönderin `ID_EDIT_FIND_COMBO` komut kimliği.  
  
4.  Sınıfı için oluşturma **Bul** birleşik giriş kutusu düğmesi, türetilen [CMFCToolBarComboBoxButton sınıfı](../mfc/reference/cmfctoolbarcomboboxbutton-class.md). Bu örnekte, adlı `CFindComboButton`.  
  
5.  Oluşturucusuna `CMFCToolbarComboBoxButton` üç parametreleri alır: düğme, düğme görüntü dizini ve birleşik giriş kutusunun stili komut kimliği. Bu parametreleri aşağıdaki gibi ayarlayın:  
  
    1.  Geçirmek `ID_EDIT_FIND_COMBO` olarak komut kimliği.  
  
    2.  Kullanım [CCommandManager::GetCmdImage](reference/internal-classes.md) ile `ID_EDIT_FIND` resim dizinini elde edilir.  
  
    3.  Kullanılabilir birleşik giriş kutusu stilleri bir listesi için bkz. [birleşik giriş kutusu stilleri](../mfc/reference/styles-used-by-mfc.md#combo-box-styles).  
  
6.  İçinde `CFindComboButton` sınıfı, geçersiz kılma `CMFCToolbarComboBoxButton::CreateCombo` yöntemi. Burada oluşturmalısınız `CFindComboButton` nesne ve ona bir işaretçi döndürür.  
  
7.  Kullanım [ımplement_serıal](../mfc/reference/run-time-object-model-services.md#implement_serial) açılan düğmeye kalıcı hale getirmek için makro. Çalışma Alanı Yöneticisi'ni otomatik olarak yükler ve düğmenin durumu Windows kayıt defterine kaydeder.  
  
8.  Uygulama `ID_EDIT_FIND_COMBO` belge görünümünüzdeki işleyici. Kullanım [CMFCToolBar::GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons) ile `ID_EDIT_FIND_COMBO` tüm almak için **Bul** birleşik giriş kutusu düğmeleri. Özelleştirme nedeniyle çok sayıda kopya aynı komutu kimlikli bir düğmenin olabilir.  
  
9. Id_edıt_fınd ileti işleyicisi `OnFind`, kullanın [CMFCToolBar::IsLastCommandFromButton](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton) FIND komutu gönderildiği olup olmadığını belirlemek için **Bul** birleşik giriş kutusu düğmesi. Bu durumda, metni bulmak ve birleşik giriş kutusuna arama dizesini ekleyin.  
  
### <a name="adding-the-find-control-to-the-main-toolbar"></a>Ana araç çubuğuna bulma denetimi ekleme  
 Birleşik giriş kutusu düğmesi eklemek için bu adımları izleyin:  
  
1.  Uygulama `AFX_WM_RESETTOOLBAR` ileti işleyicisi `OnToolbarReset` ana çerçeve penceresinde.  
  
    > [!NOTE]
    >  Framework ana çerçeve penceresine araç çubuğu uygulaması başlatılırken başlatıldığında veya araç çubuğunu özelleştirme sırasında sıfırlandığında bu iletiyi gönderir. Her iki durumda da, standart araç çubuğu düğmesi ile özel değiştirmelisiniz **Bul** birleşik giriş kutusu düğmesi.  
  
2.  İçinde `AFX_WM_RESETTOOLBAR` işleyicisi, diğer bir deyişle araç Kimliğine inceleyin, *WPARAM* AFX_WM_RESETTOOLBAR ileti. Araç çubuğu kimliği içeren araç çubuğu eşitse, **Bul** birleşik giriş kutusu düğmesi, çağrı [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton) değiştirilecek **bulmak** düğmesine (diğer bir deyişle, Komut Kimliği düğmeyle `ID_EDIT_FIND)` ile bir `CFindComboButton` nesne.  
  
    > [!NOTE]
    >  Oluşturulabilir bir `CFindComboBox` çünkü yığında nesne `ReplaceButton` düğmesi nesnesini kopyalar ve kopyayı korur.  
  
### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>Bul denetiminin özelleştirme iletişim kutusuna ekleme  
 Özelleştirme işleyicisinde `OnViewCustomize`, çağrı [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) değiştirmek için **Bul** düğmesine (diğer bir deyişle, komut kimliği düğmeyle `ID_EDIT_FIND)` bir ile`CFindComboButton` nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../mfc/hierarchy-chart.md)   
 [Sınıfları](../mfc/reference/mfc-classes.md)   
 [CMFCToolBar sınıfı](../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton sınıfı](../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton sınıfı](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCToolBarsCustomizeDialog Sınıfı](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
