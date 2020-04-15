---
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
ms.openlocfilehash: b4ed86c11d3c5b5f1ce38e3146533109f3a6b00d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363593"
---
# <a name="afx-messages"></a>AFX İletileri

Bu iletiler MFC'de kullanılır.

## <a name="messages"></a>İletiler

Aşağıdaki tablo, MFC kitaplığında kullanılan iletileri listeler:

||||||
|-|-|-|-|-|
|İleti|Açıklama|[içinde] *wParam*|*lParam* (Aksi belirtilmedikçe tüm parametreler [in] vardır.)|Dönüş Değeri|
|AFX_WM_ACCGETOBJECT|Kullanılmadı.|Kullanılmadı.|Geçerli değildir.|Geçerli değildir.|
|AFX_WM_ACCGETSTATE|Erişilebilirlik desteği için kullanılır. Bu iletiyi `CMFCRibbonPanelMenu` geçerli öğenin durumuna veya almak için `CMFCPopupMenu` gönderin.|Bir menü düğmesi veya ayırıcı olabilir öğe nin dizin.|Kullanılmadı.|Öğe durumu. Dizin geçersizse -1, menü düğmesinin özel öznitelikleri yoksa 0'dır. Aksi takdirde aşağıdaki bayrakların bir kombinasyonudur:<br /><br /> TBBS_DISABLED — öğe devre dışı<br /><br /> TBBS_CHECKED — öğe işaretli<br /><br /> TBBS_BUTTON — öğe standart bir düğmedir<br /><br /> TBBS_PRESSED — düğmesine basıldığında<br /><br /> TBBS_INDETERMINATE — tanımsız durum<br /><br /> TBBS_SEPARATOR - menü düğmesi yerine, bu öğe diğer menü öğeleri arasında bir ayrım oluşturur|
|AFX_WM_CHANGE_ACTIVE_TAB|Çerçeve bu iletiyi yeniden boyutlandırılabilir denetim çubuğu denetimine gönderir. Kullanıcı etkin bir sekmeyi `CMFCTabCtrl` değiştirdiğinde nesnelerden bildirim almak için bu iletiyi işle.|Sekme dizini.|Kullanılmadı.|Sıfır.|
|AFX_WM_CHANGE_CURRENT_FOLDER|Çerçeve, bu iletiyi `CMFCShellListCtrl` kullanıcı geçerli klasörü değiştirdiğinde üst öğeye gönderir.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_CHANGEVISUALMANAGER|Kullanıcı geçerli Visual Manager'ı değiştirdiğinde çerçeve bu iletiyi tüm çerçeve pencerelerine gönderir. Bu iletiye yanıt olarak, bir çerçeve penceresi bölgesini yeniden hesaplar ve gerektiğinde diğer parametreleri ayarlar. Bu olayhakkında bilgilendirilmeniz gerekiyorsa, uygulamanızdaki AFX_WM_CHANGEVISUALMANAGER iletiyi işleyebilirsiniz. Bu olayın çerçevesinin dahili`OnChangeVisualManager`işleme sinin gerçekleştiğinden emin olmak için temel sınıf işleyicisini ( ) aramanız gerekir.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_CHANGING_ACTIVE_TAB|Nesnenin üst `CMFCTabCtrl` öğesine gönderilir.  Kullanıcı bir sekmeyi sıfırladığında nesnelerden `CMFCTabCtrl` bildirim almak istiyorsanız bu iletiyi işleme.|Etkinleştirilmekte olan sekme dizini.|Kullanılmadı.|Sıfır.|
|AFX_WM_CHECKEMPTYMINIFRAME|Yalnızca dahili kullanım içindir.|Geçerli değildir.|Geçerli değildir.|Geçerli değildir.|
|AFX_WM_CREATETOOLBAR|Özelleştirme `CMFCToolBarsListPropertyPage` işlemi sırasında kullanıcı yeni bir araç çubuğu oluşturduğunda gönderilir. Özel cmfctoolbar türetilmiş nesne anlık olarak bu iletiyi işleyebilirsiniz. Bu iletiyi işler ve kendi araç çubuğunuzu oluşturursanız, aramayı varsayılan işleyiciye atla.|Kullanılmadı.|Araç çubuğunun adını içeren bir dize için işaretçi.|Yeni oluşturulan araç çubuğuiçin bir işaretçi. NULL, araç çubuğu oluşturmanın iptal edildiğini gösterir.|
|AFX_WM_CUSTOMIZEHELP|Kullanıcı **Yardım düğmesine** veya F1 `CMFCToolbarCustomize Dialog` tuşuna bastığında özelleştirme özelliği sayfasından ana çerçeve penceresine gönderilir.|Özelleştirme özelliği sayfasının etkin sayfasını belirtir.|Bir `CMFCToolbarCustomize Dialog` nesneye işaretçi.|Sıfır.|
|AFX_WM_CUSTOMIZETOOLBAR|Üst `CMFCToolbarCustomize Dialog` çerçeveye kullanıcının yeni bir araç çubuğu oluşturduğunu bildirmek için bu iletiyi gönderir.|Özelleştirme başlatıldığında DOĞRU, özelleştirme tamamlandığında FALSE.|Kullanılmadı.|Sıfır.|
|AFX_WM_DELETETOOLBAR|Kullanıcı özelleştirme modunda bir araç çubuğunu silmek üzereyken ana çerçeve penceresine gönderilir.<br /><br /> Kullanıcı özelleştirme modunda bir araç çubuğunu sildiğinde ek işlemler yapmak için bu iletiyi işleme yapın. Araç çubuğunu silen`OnToolbarDelete`varsayılan işleyiciyi (), de aramalısınız. Varsayılan işleyici, araç çubuğunu silmenin mümkün olup olmadığını gösteren bir değer döndürür.|Kullanılmadı.|Silinecek `CMFCToolBar` bir nesneye işaretçi.|Araç çubuğu silinemiyorsa sıfıra inmez; aksi takdirde 0.|
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton`belge renklerini almak için bu iletiyi ana çerçeve penceresine gönderir.|Kullanılmadı.|[içinde, dışarı] Bir `CList<COLORREF, COLORREF>` nesneye işaretçi.|Sıfır.|
|AFX_WM_GETDRAGBOUNDS|Yalnızca dahili kullanım içindir.|Geçerli değildir.|Geçerli değildir.|Geçerli değildir.|
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|Bir kullanıcı bir şerit listesi öğesini vurguladığında ana çerçeve penceresine gönderilir.|Vurgulanan öğenin dizini|Bir işaretçi`CMFCBaseRibbonElement`|Kullanılmadı.|
|AFX_WM_ON_AFTER_SHELL_COMMAND|Bir kullanıcı kabuk `CMFCShellListCtrl` `CMFCShellTreeCtrl` komutunu yürütmeyi bitirdiğinde bir üst öğeye veya denetimlere gönderilir.|Kullanıcının yürüttüğü komutun kimliği|Kullanılmadı.|Uygulama bu iletiyi işlerse, sıfır döndürmelidir.|
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|Çerçeve, açılır menüyü görüntülemeden önce bu iletiyi şeridin üst öğesine gönderir. Bu iletiyi işleyebilir ve istediğiniz zaman açılır menüleri değiştirebilirsiniz.|Kullanılmadı.|Bir işaretçi`CMFCBaseRibbonElement`|Kullanılmadı.|
|AFX_WM_ON_CANCELTABMOVE|Yalnızca dahili kullanım içindir.|Geçerli değildir.|Geçerli değildir.||
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|Kullanıcı etkin Şerit Denetimi kategorisini değiştirdiğinde çerçeve bu iletiyi ana çerçeveye gönderir.|Kullanılmadı.|`CMFCRibbonBar` Kimin kategorisi değişti için bir işaretçi.|Kullanılmadı.|
|AFX_WM_ON_CLOSEPOPUPWINDOW|Çerçeve, pencerenin `CMFCDesktopAlertWnd` kapatılmak üzere olduğunu sahibine bildirmek için bu iletiyi gönderir.|Kullanılmadı.|İtiraz için `CMFCDesktopAlertWnd` bir işaretçi.|Kullanılmadı.|
|AFX_WM_ON_DRAGCOMPLETE|Yalnızca dahili kullanım içindir.|Geçerli değildir.|Geçerli değildir.|Geçerli değildir.|
|AFX_WM_ON_GET_TAB_TOOLTIP|Özel araç uçları etkinse, sekme için araç ipucu nu görüntülemek üzereyken ana çerçeve penceresine gönderilir.|Kullanılmadı.|Bir yapıiçin `CMFCTabToolTipInfo` bir işaretçi.|Kullanılmadı.|
|AFX_WM_ON_HSCROLL|Yeniden boyutlandırılabilir kontrol çubuğu kontrolüne gönderildi. Sekmeli widget yatay `CMFCTabCtrl` kaydırma çubuğunda bir kaydırma olayı oluştuğunda nesnelerden bildirim almak için bu iletiyi işle.|Düşük sıralı sözcük, kullanıcının kaydırma isteğini gösteren bir kaydırma çubuğu değeri belirtir.  Daha fazla bilgi için, bu konunun ilerleyen saatlerinde tabloya bakın.|Kullanılmadı.|Sıfır.|
|AFX_WM_ON_MOVE_TAB|Kullanıcı sekmeyi yeni bir konuma sürüklediğinde sekmeli pencerenin üst bölümüne gönderilir.|Sekmenin özgün konumundaki sıfır tabanlı dizini.|[çıkış] Sekmenin yeni konumundaki sıfır tabanlı dizini.|Sıfır.|
|AFX_WM_ON_MOVETABCOMPLETE|Yalnızca dahili kullanım içindir.|Geçerli değildir.|Geçerli değildir.|Geçerli değildir.|
|AFX_WM_ON_MOVETOTABGROUP|Bir kullanıcı bir MDI alt penceresini sekmeli bir gruptan diğerine taşırken ana çerçeve penceresine gönderilir.|MDI alt penceresinin`CMFCTabCtrl`kaldırıldığı sekmeli pencere ( ) için bir tutamaç.|[çıkış] MDI alt penceresinin`CMFCTabCtrl`eklendiği sekmeli pencere ( ) için bir tutamaç.|Göz ardı.|
|AFX_WM_ON_PRESS_CLOSE_BUTTON|Kullanıcı denetim çubuğunun `CDockablePane` alt yazısındaki **Kapat** düğmesini tıklattığında bir ebeveyne gönderilir.|Kullanılmadı.|Kullanıcının **Kapat** düğmesini tıklatdığı takılabilir bölmeye işaretçi.|Bir bölme kapatılamazsa DOĞRU; aksi takdirde YANLIŞ.|
|AFX_WM_ON_RENAME_TAB|Kullanıcı değiştirilebilir bir sekmeyi yeniden adlandırdıktan sonra sekmeli pencerenin üst bölümüne gönderilir.|Yeniden adlandırılmış sekmenin sıfır tabanlı dizini.|[çıkış] Yeni sekme adını içeren bir dize için işaretçi.|Uygulama bu iletiyi işlerse sıfırsız; çerçeve için çağrı bastırmak `CMFCBaseTabCtrl::SetTabLabel`olacaktır.  Sıfır döndürülürse, çerçeve tarafından `CMFCBaseTabCtrl::SetTabLabel` çağrılır.|
|AFX_WM_ON_RIBBON_CUSTOMIZE|Kullanıcı özelleştirmeye başladığında ana çerçeveye gönderilir. Kendi özelleştirme iletişim kutunuzu görüntülemek istiyorsanız bu iletiyi işleme.|Kullanılmadı.|Özelleştirilecek şerit denetimiiçin bir işaretçi.|Uygulama bu iletiyi işler ve kendi özelleştirme iletişim kutusunu görüntülerse sıfıra aykırıdır. Uygulama sıfır döndürürse, çerçeve yerleşik özelleştirme iletişim kutusunu görüntüler.|
|AFX_WM_ON_TABGROUPMOUSEMOVE|Yalnızca dahili kullanım içindir.|Geçerli değildir.|Geçerli değildir.|Geçerli değildir.|
|AFX_WM_POSTSETPREVIEWFRAME|Kullanıcının yazdırma önizleme modunu değiştirdiğini ana çerçeveye bildirmek için gönderildi|TRUE, yazdırma önizleme modunun ayarlı olduğunu gösterir. FALSE, yazdırma önizleme modunun kapalı olduğunu gösterir.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_PROPERTY_CHANGED|Kullanıcı seçili özelliğin değerini`CMFCPropertyGridCtrl`değiştirdiğinde özellik ızgara denetiminin sahibine gönderilir.|Özellik listesinin denetim kimliği.|`CMFCPropertyGridProperty`() değiştirilen özellik için bir işaretçi.|Kullanılmadı.|
|AFX_WM_RESETCONTEXTMENU|Kullanıcı özelleştirme sırasında bağlam menüsünü sıfırladığında ana çerçeve penceresine gönderilir.|Bağlam menüsünün kaynak kimliği.|Geçerli bağlam menüsüne işaretçi, `CMFCPopupMenu`.|Kullanılmadı.|
|AFX_WM_RESETKEYBOARD|Kullanıcı özelleştirme sırasında tüm klavye hızlandırıcılarını sıfırladığında çerçeve bu iletiyi ana çerçeve penceresine gönderir.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_RESETMENU|Kullanıcı özelleştirme sırasında bir uygulama çerçevesi menüsünü sıfırladığında çerçeve bu iletiyi menü sahibine (çerçeve penceresi) gönderir|Menü kaynak kimliği.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_RESETPROMPT|Kullanıcı araç çubuğundan bir araç çubuğunu sıfırladığında çerçeve bu iletiyi gönderir. Varsayılan işleyici, kullanıcının araç çubuğunu sıfırlamak isteyip istemediğini soran bir ileti kutusu görüntüler.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_RESETTOOLBAR|Bir `CMFCToolBar` araç çubuğu özgün durumuna geri yüklendiğinde, yani kaynaklardan yüklendiğinde, nesne bu iletiyi gönderir. Sınıfları türetilen araç çubuğu düğmelerini yeniden eklemek `CMFCToolbarButton`için bu iletiyi işleme Daha fazla bilgi için bkz. `CMFCToolbarComboBoxButton`.|Durumu geri yüklenen bir araç çubuğunun kaynak kimliği.|Kullanılmadı.|Sıfır.|
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton`kullanıcı normal bir menü düğmesini tıklattığında nesne bu iletiyi sahibine gönderir. Kullanıcı bir düğmeyi tıklattığında açılır menüyü görüntülemek için her kullandığınızda `CMFCToolbarMenuButton` bu iletiyi işleyin.|İletiyi gönderen bir düğmenin komut kimliği.|İmlecin ekran koordinatları. Düşük sıralı sözcük x-koordinatını belirtir. Yüksek sıralı sözcük y-koordinatını belirtir.|Kullanılmadı.|
|AFX_WM_TOOLBARMENU|Fare işaretçisi bir bölmenin istemci veya istemci olmayan alanındayken, kullanıcı farenin sağ düğmesini serbest bıraktıklarında ana çerçeve penceresine gönderilir.|Kullanılmadı.|Fare işaretçisinin ekran koordinatları. Düşük sıralı sözcük x-koordinatını belirtir. Yüksek sıralı sözcük y-koordinatını belirtir.|Uygulama bu iletiyi işlerse sıfır; aksi takdirde, sıfır değil.|
|AFX_WM_UPDATETOOLTIPS|Araç ipucu denetimlerinin yeniden oluşturulması gerektiğini belirtmek için tüm araç ucu sahiplerine gönderilir.|Bu iletiyi işlemesi gereken denetim türü. Olası değerlerin listesi için bu konunun ardından tabloya bakın.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog`kullanıcı **Yardım düğmesini** tıklattığında bu iletiyi ana çerçeveye gönderir veya **Yardım** altyazı düğmesini veya F1 tuşunu tıklatarak yardım moduna girer.|Kullanılmadı.|Örneğinbir işaretçi `CMFCWindowsManagerDialog`.|Kullanılmadı.|

Aşağıdaki tablo, AFX_WM_HSCROLL yönteminin *lParam* parametresinin düşük sözcüğünün değerlerini gösterir:

|||
|-|-|
|Değer|Anlamı|
|SB_ENDSCROLL|Kullanıcı kaydırmayı sona erdiriyor.|
|SB_LEFT|Kullanıcı sol üstlere kaydırılır.|
|SB_RIGHT|Kullanıcı sağ alta kaydırılır.|
|SB_LINELEFT|Kullanıcı bir birim tarafından sola kaydırılır.|
|SB_LINERIGHT|Kullanıcı bir birim tarafından sağa kaydırılır.|
|SB_PAGELEFT|Kullanıcı pencerenin genişliğinden sola kaydırır.|
|SB_PAGERIGHT|Kullanıcı pencerenin genişliğine doğru kaydırılır.|
|SB_THUMBPOSITION|Kullanıcı kaydırma kutusunu (başparmak) sürükledi ve fare düğmesini yayımladı. Yüksek sıralı sözcük, sürükleme işleminin sonundakaydırma kutusunun konumunu gösterir.|
|SB_THUMBTRACK|Kullanıcı kaydırma kutusunu sürüklüyor. Kullanıcı fare düğmesini serbest bırakana kadar AFX_WM_ON_HSCROLL iletisi bu değerle tekrar tekrar gönderilir. Yüksek sıralı sözcük, kaydırma kutusunun sürüklendiği konumu gösterir.|

> [!NOTE]
> *lParam* parametresinin yüksek sıralı sözcüğü, düşük sıralı sözcük SB_THUMBPOSITION veya SB_THUMBTRACK ise kaydırma kutusunun geçerli konumunu belirtir; aksi takdirde, bu sözcük kullanılmaz.

Aşağıdaki tabloda AFX_WM_UPDATETOOLTIPS iletisinin *lParam* parametresi için bayrak değerleri listelenir:

|||
|-|-|
|Bayrak|Değer|
|AFX_TOOLTIP_TYPE_DEFAULT|0x0001|
|AFX_TOOLTIP_TYPE_TOOLBAR|0x0002|
|AFX_TOOLTIP_TYPE_TAB|0x0004|
|AFX_TOOLTIP_TYPE_MINIFRAME|0x0008|
|AFX_TOOLTIP_TYPE_DOCKBAR|0x0010|
|AFX_TOOLTIP_TYPE_EDIT|0x0020|
|AFX_TOOLTIP_TYPE_BUTTON|0x0040|
|AFX_TOOLTIP_TYPE_TOOLBOX|0x0080|
|AFX_TOOLTIP_TYPE_ALL|0xffff|

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
