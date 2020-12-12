---
description: 'Daha fazla bilgi edinin: AFX Iletileri'
title: AFX İletileri
ms.date: 11/04/2016
f1_keywords:
- SB_LINELEFT
- SB_THUMBTRACK
- AFX_TOOLTIP_TYPE_EDIT
- AFX_WM_ON_HSCROLL
- SB_PAGERIGHT
- AFX_WM_RESETPROMPT
- AFX_WM_CHANGE_RIBBON_CATEGORY
- AFX_TOOLTIP_TYPE_MINIFRAME
- AFX_WM_CUSTOMIZETOOLBAR
- AFX_WM_CHANGE_ACTIVE_TAB
- AFX_WM_ACCGETOBJECT
- AFX_WM_TOOLBARMENU
- AFX_TOOLTIP_TYPE_DOCKBAR
- AFX_WM_CUSTOMIZEHELP
- AFX_WM_ON_GET_TAB_TOOLTIP
- AFX_WM_ON_RIBBON_CUSTOMIZE
- AFX_WM_ON_DRAGCOMPLETE
- AFX_WM_RESETTOOLBAR
- AFX_WM_ON_MOVETOTABGROUP
- AFX_WM_CHECKEMPTYMINIFRAME
- AFX_WM_GETDOCUMENTCOLORS
- SB_RIGHT
- AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU
- AFX_WM_ACCGETSTATE
- SB_PAGELEFT
- SB_ENDSCROLL
- AFX_WM_ON_CANCELTABMOVE
- AFX_TOOLTIP_TYPE_TAB
- AFX_WM_WINDOW_HELP
- AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM
- AFX_WM_SHOWREGULARMENU
- AFX_TOOLTIP_TYPE_TOOLBAR
- AFX_WM_CHANGE_CURRENT_FOLDER
- AFX_WM_UPDATETOOLTIPS
- AFX_WM_ON_MOVE_TAB
- AFX_WM_CHANGING_ACTIVE_TAB
- AFX_WM_RESETMENU
- AFX_WM_GETDRAGBOUNDS
- AFX_WM_RESETCONTEXTMENU
- AFX_TOOLTIP_TYPE_BUTTON
- AFX_WM_ON_CLOSEPOPUPWINDOW
- AFX_TOOLTIP_TYPE_TOOLBOX
- AFX_WM_CHANGEVISUALMANAGER
- SB_LINERIGHT
- AFX_WM_ON_RENAME_TAB
- AFX_TOOLTIP_TYPE_DEFAULT
- AFX_WM_ON_TABGROUPMOUSEMOVE
- SB_LEFT
- AFX_WM_DELETETOOLBAR
- AFX_WM_PROPERTY_CHANGED
- AFX_TOOLTIP_TYPE_ALL
- AFX_WM_ACCHITTEST
- AFX_WM_ON_AFTER_SHELL_COMMAND
- AFX_WM_ON_PRESS_CLOSE_BUTTON
- AFX_WM_RESETKEYBOARD
- AFX_WM_ON_MOVETABCOMPLETE
- AFX_WM_CREATETOOLBAR
- SB_THUMBPOSITION
- AFX_WM_POSTSETPREVIEWFRAME
helpviewer_keywords:
- AFX messages [MFC]
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
ms.openlocfilehash: edda0bffd7077a9898a83ff1a530145a008d2d94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322843"
---
# <a name="afx-messages"></a>AFX İletileri

Bu iletiler MFC 'de kullanılır.

## <a name="messages"></a>İletiler

Aşağıdaki tabloda, MFC kitaplığında kullanılan iletiler listelenmektedir:

|İleti|Açıklama|'ndaki *wParam*|*lParam* (tüm parametreler, aksi belirtilmediği takdirde [in].)|Dönüş Değeri|
|-|-|-|-|-|
|AFX_WM_ACCGETOBJECT|Kullanılmadı.|Kullanılmadı.|Geçerli değildir.|Geçerli değildir.|
|AFX_WM_ACCGETSTATE|Erişilebilirlik desteği için kullanılır. `CMFCPopupMenu` `CMFCRibbonPanelMenu` Geçerli öğenin durumunu almak için bu iletiyi veya öğesine gönderin.|Bir menü düğmesi veya ayırıcı olabilecek öğenin dizini.|Kullanılmadı.|Öğe durumu. Dizin geçersizse-1, menü düğmesinin özel öznitelikleri yoksa 0 olur. Aksi takdirde, aşağıdaki bayrakların bir birleşimidir:<br /><br /> TBBS_DISABLED — öğe devre dışı<br /><br /> TBBS_CHECKED — öğe işaretlendi<br /><br /> TBBS_BUTTON — öğe standart bir basma düğmesi<br /><br /> TBBS_PRESSED — düğme basıldı<br /><br /> TBBS_INDETERMINATE — tanımsız durum<br /><br /> TBBS_SEPARATOR, bu öğe, bir menü düğmesi yerine, diğer menü öğeleri arasında bir ayrım oluşturur|
|AFX_WM_CHANGE_ACTIVE_TAB|Çerçeve bu iletiyi yeniden boyutlandırılabilir denetim çubuğu denetimine gönderir. Kullanıcı etkin bir sekmeyi değiştirdiğinde, nesnelerden bildirim almak için bu iletiyi işleyin `CMFCTabCtrl` .|Bir sekmenin dizini.|Kullanılmadı.|Sıfır olmayan.|
|AFX_WM_CHANGE_CURRENT_FOLDER|Çerçeve bu iletiyi `CMFCShellListCtrl` Kullanıcı geçerli klasörü değiştirdiği zaman üst öğesine gönderir.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_CHANGEVISUALMANAGER|Bu ileti, Kullanıcı geçerli Visual Manager 'ı değiştirdiğinde bu iletiyi tüm çerçeve pencereleri olarak gönderir. Bu iletiye yanıt olarak bir çerçeve penceresi, bölgesini yeniden hesaplar ve gerektiğinde diğer parametreleri ayarlar. Bu olay hakkında bildirim almanız gerekiyorsa uygulamanızdaki AFX_WM_CHANGEVISUALMANAGER iletisini işleyebilirsiniz. `OnChangeVisualManager`Framework 'ün bu olayın iç işlemenin gerçekleşmesini sağlamak için temel sınıf işleyicisini () çağırmanız gerekir.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_CHANGING_ACTIVE_TAB|Nesnenin üst öğesine gönderilir `CMFCTabCtrl` .  `CMFCTabCtrl`Bir Kullanıcı bir sekmeyi sıfırladığında nesnelerden bildirim almak istiyorsanız bu iletiyi işleyin.|Etkinleştirilmekte olan sekmenin dizini.|Kullanılmadı.|Sıfır olmayan.|
|AFX_WM_CHECKEMPTYMINIFRAME|Yalnızca dahili kullanım içindir.|Geçerli değildir.|Geçerli değildir.|Geçerli değildir.|
|AFX_WM_CREATETOOLBAR|`CMFCToolBarsListPropertyPage`Bir kullanıcı özelleştirme işlemi sırasında yeni bir araç çubuğu oluşturduğunda gönderilir. Bu iletiyi, özel bir CMFCToolBar-türetilmiş nesnesinin örneğini oluşturmak için işleyebilirsiniz. Bu iletiyi işler ve kendi araç çubuğu oluşturursanız, varsayılan işleyicinin çağrısını atlayın.|Kullanılmadı.|Araç çubuğunun adını içeren bir dize işaretçisi.|Yeni oluşturulan araç çubuğuna bir işaretçi. NULL, araç çubuğu oluşturma 'nın iptal edildiğini gösterir.|
|AFX_WM_CUSTOMIZEHELP|`CMFCToolbarCustomize Dialog`Kullanıcı **Yardım** düğmesine veya F1 tuşuna bastığında özelleştirme özellik sayfasından ana çerçeve penceresine gönderilir.|Özelleştirme özellik sayfasının etkin sayfasını belirtir.|Bir `CMFCToolbarCustomize Dialog` nesne işaretçisi.|Sıfır.|
|AFX_WM_CUSTOMIZETOOLBAR|`CMFCToolbarCustomize Dialog`Bu iletiyi, kullanıcının yeni bir araç çubuğu oluşturanı ana çerçeveye bildirmek üzere gönderir.|Özelleştirme başlatıldığında TRUE, özelleştirme bittiğinde FALSE.|Kullanılmadı.|Sıfır.|
|AFX_WM_DELETETOOLBAR|Kullanıcı özelleştirme modundaki bir araç çubuğunu silmek üzere olduğunda ana çerçeve penceresine gönderilir.<br /><br /> Bir kullanıcı özelleştirme modundaki bir araç çubuğunu sildiğinde ek eylemler gerçekleştirmek için bu iletiyi işleyin. Ayrıca, araç çubuğunu silen varsayılan işleyiciyi ( `OnToolbarDelete` ) çağırmanız gerekir. Varsayılan işleyici, araç çubuğunu silmenin mümkün olup olmadığını gösteren bir değer döndürür.|Kullanılmadı.|`CMFCToolBar`Silinecek nesnenin işaretçisi.|Bir araç çubuğu silinemediği takdirde sıfır dışı; Aksi takdirde 0.|
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton` belge renklerini almak için bu iletiyi ana çerçeve penceresine gönderir.|Kullanılmadı.|[in, out] Bir nesne işaretçisi `CList<COLORREF, COLORREF>` .|Sıfır.|
|AFX_WM_GETDRAGBOUNDS|Yalnızca dahili kullanım içindir.|Geçerli değildir.|Geçerli değildir.|Geçerli değildir.|
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|Kullanıcı bir şerit listesi öğesi vurgulamaları durumunda ana çerçeve penceresine gönderilir.|Vurgulanan öğenin dizini|Bir işaretçisi `CMFCBaseRibbonElement`|Kullanılmadı.|
|AFX_WM_ON_AFTER_SHELL_COMMAND|`CMFCShellListCtrl` `CMFCShellTreeCtrl` Bir Kullanıcı bir kabuk komutunu yürütmeyi bitirdiğinde bir üst öğeye veya denetimlerine gönderilir.|Kullanıcının yürüttüğü komutun KIMLIĞI|Kullanılmadı.|Uygulama bu iletiyi işliyorsa, sıfır döndürmelidir.|
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|Çerçeve, açılan menüyü görüntülemeden önce bu iletiyi şeridin üst öğesine gönderir. Bu iletiyi işleyebilir ve açılır menüleri dilediğiniz zaman değiştirebilirsiniz.|Kullanılmadı.|Bir işaretçisi `CMFCBaseRibbonElement`|Kullanılmadı.|
|AFX_WM_ON_CANCELTABMOVE|Yalnızca dahili kullanım içindir.|Geçerli değildir.|Geçerli değildir.||
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|Çerçeve, Kullanıcı etkin şerit denetim kategorisini değiştirdiğinde bu iletiyi ana çerçeveye gönderir.|Kullanılmadı.|Kendi kategorisine yönelik bir işaretçi `CMFCRibbonBar` değişti.|Kullanılmadı.|
|AFX_WM_ON_CLOSEPOPUPWINDOW|Framework, `CMFCDesktopAlertWnd` pencerenin kapatılmak üzere olduğunu kullanıcıya bildirmek için bu iletiyi gönderir.|Kullanılmadı.|`CMFCDesktopAlertWnd`Nesne işaretçisi.|Kullanılmadı.|
|AFX_WM_ON_DRAGCOMPLETE|Yalnızca dahili kullanım içindir.|Geçerli değildir.|Geçerli değildir.|Geçerli değildir.|
|AFX_WM_ON_GET_TAB_TOOLTIP|Bir sekme penceresi bir sekme için araç ipucunu göstermek üzere olduğunda, özel araç ipuçları etkinse ana çerçeve penceresine gönderilir.|Kullanılmadı.|Bir yapıya yönelik işaretçi `CMFCTabToolTipInfo` .|Kullanılmadı.|
|AFX_WM_ON_HSCROLL|Yeniden boyutlandırılabilir denetim çubuğu denetimine gönderilir. `CMFCTabCtrl`Sekmeli pencere öğesi yatay kaydırma çubuğunda bir kaydırma olayı oluştuğunda nesnelerden bildirim almak için bu iletiyi işleyin.|Düşük sıralı sözcük, kullanıcının kaydırma isteğini gösteren bir kaydırma çubuğu değeri belirtir.  Daha fazla bilgi için bu konunun ilerleyen kısımlarında bulunan tabloya bakın.|Kullanılmadı.|Sıfır olmayan.|
|AFX_WM_ON_MOVE_TAB|Kullanıcı yeni bir konuma sekme sürüklediğinde sekmeli pencerenin üst öğesine gönderilir.|Sekmenin özgün konumundaki sıfır tabanlı dizini.|dışı Sekmenin yeni konumundaki sıfır tabanlı dizini.|Sıfır.|
|AFX_WM_ON_MOVETABCOMPLETE|Yalnızca dahili kullanım içindir.|Geçerli değildir.|Geçerli değildir.|Geçerli değildir.|
|AFX_WM_ON_MOVETOTABGROUP|Bir kullanıcı MDI alt penceresini bir sekmeli gruptan diğerine taşırken ana çerçeve penceresine gönderilir.|MDI alt penceresinin kaldırıldığı sekmeli pencere () için bir işleyici `CMFCTabCtrl` .|dışı MDI alt penceresinin eklendiği sekmeli pencereye () yönelik bir işleyici `CMFCTabCtrl` .|LIP.|
|AFX_WM_ON_PRESS_CLOSE_BUTTON|`CDockablePane`Kullanıcı denetim çubuğunun açıklamalı alt yazısının **Kapat** düğmesine tıkladığında bir üst öğesine gönderilir.|Kullanılmadı.|Kullanıcının **Kapat** düğmesine tıkladığını bir yerleştirilebilir bölmesi işaretçisi.|Bölme kapatılmadığı takdirde TRUE; Aksi halde yanlış.|
|AFX_WM_ON_RENAME_TAB|Kullanıcı düzenlenebilir bir sekmeyi yeniden adlandırdıktan sonra sekmeli pencerenin üst öğesine gönderilir.|Yeniden adlandırılan sekmenin sıfır tabanlı dizini.|dışı Yeni sekme adını içeren bir dize işaretçisi.|Uygulama bu iletiyi işliyorsa sıfır dışı; çerçeve, çağrısını bastırır `CMFCBaseTabCtrl::SetTabLabel` .  Sıfır döndürülürse, `CMFCBaseTabCtrl::SetTabLabel` Framework tarafından çağırılır.|
|AFX_WM_ON_RIBBON_CUSTOMIZE|Kullanıcı özelleştirmeye başladığında üst çerçeveye gönderilir. Kendi özelleştirme iletişim kutusunu göstermek istiyorsanız bu iletiyi işleyin.|Kullanılmadı.|Özelleştirilecek şerit denetimine yönelik bir işaretçi.|Uygulama bu iletiyi işliyorsa ve kendi özelleştirme iletişim kutusunu görüntülediğinde sıfır dışında. Uygulama sıfır döndürürse, çerçeve yerleşik özelleştirme iletişim kutusunu görüntüler.|
|AFX_WM_ON_TABGROUPMOUSEMOVE|Yalnızca dahili kullanım içindir.|Geçerli değildir.|Geçerli değildir.|Geçerli değildir.|
|AFX_WM_POSTSETPREVIEWFRAME|Kullanıcının Baskı Önizleme modunu değiştirdiği ana çerçeveye bildirim göndermek için gönderilir|DOĞRU, Baskı Önizleme modunun ayarlandığını gösterir. YANLıŞ, Baskı Önizleme modunun kapalı olduğunu gösterir.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_PROPERTY_CHANGED|Kullanıcı Seçili özelliğin değerini değiştirdiğinde Özellik Kılavuzu denetiminin sahibine ( `CMFCPropertyGridCtrl` ) gönderilir.|Özellik listesinin denetim KIMLIĞI.|Değiştirilen () özelliğine yönelik bir işaretçi `CMFCPropertyGridProperty` .|Kullanılmadı.|
|AFX_WM_RESETCONTEXTMENU|Özelleştirme sırasında Kullanıcı bağlam menüsünü sıfırladığında ana çerçeve penceresine gönderilir.|Bağlam menüsünün kaynak KIMLIĞI.|Geçerli bağlam menüsüne yönelik bir işaretçi `CMFCPopupMenu` .|Kullanılmadı.|
|AFX_WM_RESETKEYBOARD|Kullanıcı özelleştirme sırasında tüm klavye hızlandırıcılarını sıfırladığında çerçeve bu iletiyi ana çerçeve penceresine gönderir.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_RESETMENU|Çerçeve, özelleştirme sırasında Kullanıcı bir uygulama çerçevesi menüsünü sıfırladığında bu iletiyi menü sahibine (bir çerçeve penceresi) gönderir|Menü kaynak KIMLIĞI.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_RESETPROMPT|Kullanıcı araç çubuğu Özelleştir iletişim kutusundan bir araç çubuğunu sıfırladığında Framework bu iletiyi gönderir. Varsayılan işleyici, kullanıcının araç çubuğunu sıfırlamak isteyip istemediğini soran bir ileti kutusu görüntüler.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_RESETTOOLBAR|Bir `CMFCToolBar` nesne, bir araç çubuğu özgün durumuna geri yüklendiğinde, diğer bir deyişle, kaynaklardan yüklendiğinde bu iletiyi gönderir. Sınıfları türetilmiş olan araç çubuğu düğmelerini yeniden eklemek için bu iletiyi işleyin `CMFCToolbarButton` . Daha fazla bilgi için bkz. `CMFCToolbarComboBoxButton`.|Durumu geri yüklenmiş olan bir araç çubuğunun kaynak KIMLIĞI.|Kullanılmadı.|Sıfır.|
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton` Kullanıcı bir normal menü düğmesine tıkladığında nesne bu iletiyi sahibine gönderir. `CMFCToolbarMenuButton`Kullanıcı bir düğmeye tıkladığında bir açılan menüyü göstermek için her seferinde bu iletiyi işleyin.|İletiyi gönderen bir düğmenin komut KIMLIĞI.|İmlecin ekran koordinatları. Düşük sıralı kelime x koordinatını belirtir. Yüksek sıralı sözcük y koordinatını belirtir.|Kullanılmadı.|
|AFX_WM_TOOLBARMENU|Fare işaretçisi bir bölmenin istemci veya istemci dışı alanındayken Kullanıcı farenin sağ düğmesini bıraktığında ana çerçeve penceresine gönderilir.|Kullanılmadı.|Fare işaretçisinin ekran koordinatları. Düşük sıralı kelime x koordinatını belirtir. Yüksek sıralı sözcük y koordinatını belirtir.|Uygulama bu iletiyi işliyorsa sıfır; Aksi takdirde, sıfır dışında.|
|AFX_WM_UPDATETOOLTIPS|Araç ipucu denetimlerinin yeniden oluşturulması gerektiğini belirtmek için tüm araç ipucu sahiplerine gönderilir.|Bu iletiyi işlemesi gereken denetim türü. Olası değerlerin listesi için bu konunun ilerleyen kısımlarında bulunan tabloya bakın.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog` Kullanıcı **Yardım** düğmesine tıkladığında bu iletiyi üst çerçeveye gönderir veya yardım yazısı düğmesine veya F1 tuşuna **tıklayarak yardım moduna** girer.|Kullanılmadı.|Örneğine yönelik bir işaretçi `CMFCWindowsManagerDialog` .|Kullanılmadı.|

Aşağıdaki tabloda AFX_WM_HSCROLL yönteminin *lParam* parametresinin alt kelimesinin değerleri gösterilmektedir:

|Değer|Anlamı|
|-|-|
|SB_ENDSCROLL|Kullanıcı, kaydırmayı sonlandırır.|
|SB_LEFT|Kullanıcı sol üst sola kayar.|
|SB_RIGHT|Kullanıcı sağ alt düzeye kayar.|
|SB_LINELEFT|Kullanıcı sola bir birim kaydırır.|
|SB_LINERIGHT|Kullanıcı bir birimi sağa kaydırır.|
|SB_PAGELEFT|Kullanıcı sola, pencerenin genişliğine göre kayar.|
|SB_PAGERIGHT|Kullanıcı, sağa pencere genişliğine göre kayar.|
|SB_THUMBPOSITION|Kullanıcı kaydırma kutusunu (Thumb) sürüklemiş ve fare düğmesini yayımlamıştır. Yüksek sıralı sözcük, sürükleme işleminin sonundaki kaydırma kutusunun konumunu gösterir.|
|SB_THUMBTRACK|Kullanıcı kaydırma kutusunu sürüklemektir. AFX_WM_ON_HSCROLL ileti, Kullanıcı fare düğmesini bıraktığında bu değerle tekrar tekrar gönderilir. Yüksek sıralı sözcük, kaydırma kutusunun sürüklenen konumunu gösterir.|

> [!NOTE]
> *LParam* parametresinin yüksek sıralı sözcüğü, düşük sıralı kelime SB_THUMBPOSITION veya SB_THUMBTRACK, kaydırma kutusunun geçerli konumunu belirtir; Aksi takdirde, bu sözcük kullanılmaz.

Aşağıdaki tablo AFX_WM_UPDATETOOLTIPS iletisinin *lParam* parametresi için bayrak değerlerini listeler:

|Bayrak|Değer|
|-|-|
|AFX_TOOLTIP_TYPE_DEFAULT|0x0001|
|AFX_TOOLTIP_TYPE_TOOLBAR|0x0002|
|AFX_TOOLTIP_TYPE_TAB|0x0004|
|AFX_TOOLTIP_TYPE_MINIFRAME|0x0008|
|AFX_TOOLTIP_TYPE_DOCKBAR|0x0010|
|AFX_TOOLTIP_TYPE_EDIT|0x0020|
|AFX_TOOLTIP_TYPE_BUTTON|0x0040|
|AFX_TOOLTIP_TYPE_TOOLBOX|0x0080|
|AFX_TOOLTIP_TYPE_ALL|0xFFFF|

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
