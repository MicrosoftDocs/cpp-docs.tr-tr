---
title: AFX iletileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- AFX messages [MFC]
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92f24c18de594cfe734b703ec13c3116b7b5d31b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391006"
---
# <a name="afx-messages"></a>AFX İletileri

Bu iletiler MFC'de kullanılır.

## <a name="messages"></a>İletiler

Aşağıdaki tabloda, MFC Kitaplığı'nda kullanılan mesajları listelenmektedir:

||||||
|-|-|-|-|-|
|İleti|Açıklama|[in] *wParam*|*lParam* (tüm parametreleri [in] aksi belirtilmedikçe bağlıdır.)|Dönüş Değeri|
|AFX_WM_ACCGETOBJECT|Kullanılmadı.|Kullanılmadı.|Yok.|Yok.|
|AFX_WM_ACCGETSTATE|Erişilebilirlik desteği için kullanılır. Bu ileti gönder `CMFCPopupMenu` veya `CMFCRibbonPanelMenu` geçerli öğe durumu alınamadı.|Menü düğmesine veya ayırıcı öğenin dizini.|Kullanılmadı.|Öğe durumu. Dizin geçersiz, -1 ise 0 menü düğmesine özel özniteliklere sahip değildir. Aksi takdirde aşağıdaki bayraklar birleşiminden oluşur:<br /><br /> TBBS_DISABLED — öğesi devre dışı bırakıldı<br /><br /> TBBS_CHECKED — öğesi denetlenir.<br /><br /> TBBS_BUTTON — standart bir basma düğmesi öğesidir<br /><br /> TBBS_PRESSED — düğmeye basıldığında<br /><br /> TBBS_INDETERMINATE — tanımlanmamış durumu<br /><br /> TBBS_SEPARATOR - yerine bir menü düğmesi bu öğenin forms diğer menü öğeleri arasında ayrım a|
|AFX_WM_CHANGE_ACTIVE_TAB|Framework yeniden boyutlandırılabilir denetim çubuğu denetimi için bu iletiyi gönderir. Bildirimleri almak için bu iletiyi işlemeli `CMFCTabCtrl` kullanıcı etkin bir sekme değiştirdiğinde nesneleri.|Sekme dizini.|Kullanılmadı.|Sıfır dışında.|
|AFX_WM_CHANGE_CURRENT_FOLDER|Framework üst öğesi için bu iletiyi gönderir `CMFCShellListCtrl` kullanıcı geçerli klasörde değiştirilmemiş olduğunda.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_CHANGEVISUALMANAGER|Kullanıcının geçerli Visual Yöneticisi değiştiğinde framework tüm çerçeve pencereleri için bu iletiyi gönderir. Yanıt olarak bu ileti, bir çerçeve penceresinin alt bölgeye yeniden hesaplar ve diğer parametrelerini gerektiği gibi ayarlar. Bu olay hakkında bildirim almak istiyorsanız, uygulamanızda AFX_WM_CHANGEVISUALMANAGER ileti işleyebilir. Temel sınıf işleyici çağırması gerekir (`OnChangeVisualManager`) framework iç emin olmak için bu olay işleme gerçekleşir.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_CHANGING_ACTIVE_TAB|Üst öğesi için gönderilen `CMFCTabCtrl` nesne.  Bildirimleri almak istemiyorsanız, bu iletiyi işlemeli `CMFCTabCtrl` nesneleri, bir kullanıcı bir sekmeye sıfırlar.|Etkinleştirilmekte olan sekme dizini.|Kullanılmadı.|Sıfır dışında.|
|AFX_WM_CHECKEMPTYMINIFRAME|Yalnızca iç kullanım içindir.|Yok.|Yok.|Yok.|
|AFX_WM_CREATETOOLBAR|Gönderilen `CMFCToolBarsListPropertyPage` ne zaman bir kullanıcının oluşturduğu yeni bir araç çubuğu özelleştirme işlemi sırasında. CMFCToolBar türetilen özel bir nesne örneği oluşturmak için bu ileti işleyebilir. Bu iletiyi işlemek ve kendi araç oluşturabilir, varsayılan işleyici çağrısı atlayın.|Kullanılmadı.|Araç adı içeren bir dize işaretçisi.|Yeni oluşturulan araç için bir işaretçi. Araç çubuğu oluşturma iptal edildi NULL gösterir.|
|AFX_WM_CUSTOMIZEHELP|Ana çerçeve penceresine özelleştirme özellik sayfasından gönderilen `CMFCToolbarCustomize Dialog` kullanıcının bastığında **yardımcı** düğme veya F1 tuşuna.|Etkin sayfa özelleştirme özellik sayfasının belirtir.|Bir işaretçi bir `CMFCToolbarCustomize Dialog` nesne.|Sıfır.|
|AFX_WM_CUSTOMIZETOOLBAR|`CMFCToolbarCustomize Dialog` Üst çerçevenin kullanıcı yeni bir araç çubuğu öğesini oluşturmakta olduğunu bildirmek için bu iletiyi gönderir.|Özelleştirme tamamlandığında özelleştirme, yanlış başlatıldığında TRUE.|Kullanılmadı.|Sıfır.|
|AFX_WM_DELETETOOLBAR|Kullanıcı bir araç çubuğu özelleştirme modunu silmek üzere olduğunda ana çerçeve penceresine Gönder.<br /><br /> Bir kullanıcı bir araç çubuğu özelleştirme modu sildiğinde ek işlemler gerçekleştirmeleri için bu iletiyi işler. Ayrıca, varsayılan işleyici çağırması gerekir (`OnToolbarDelete`), araç siler. Varsayılan işleyici araç çubuğunu silmek mümkün olup olmadığını belirten bir değer döndürür.|Kullanılmadı.|İşaretçi bir `CMFCToolBar` silinecek nesne.|Araç çubuğu silinemez olursa sıfır dışı; Aksi durumda 0.|
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton` Bu ileti, belge renkleri almak için ana çerçeve penceresine gönderir.|Kullanılmadı.|[out içinde] İşaretçi bir `CList<COLORREF, COLORREF>` nesne.|Sıfır.|
|AFX_WM_GETDRAGBOUNDS|Yalnızca iç kullanım içindir.|Yok.|Yok.|Yok.|
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|Ana çerçeve penceresine bir kullanıcı bir Şerit liste öğesi vurguladığında Gönder.|Vurgulanan öğe dizini|Bir işaretçi `CMFCBaseRibbonElement`|Kullanılmadı.|
|AFX_WM_ON_AFTER_SHELL_COMMAND|Üst öğesi için gönderilen `CMFCShellListCtrl` veya `CMFCShellTreeCtrl` Kabuk komutu yürütülürken bir kullanıcı tamamlandığında denetler.|Kullanıcı çalıştırılan komut kimliği|Kullanılmadı.|Uygulama bu iletiyi işleyen, sıfır döndürmelidir.|
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|Açılır menü görüntülemeden önce framework Şeridin üst öğeye bu iletiyi gönderir. Bu iletiyi işlemeli ve açılır menüler dilediğiniz zaman değiştirin.|Kullanılmadı.|Bir işaretçi `CMFCBaseRibbonElement`|Kullanılmadı.|
|AFX_WM_ON_CANCELTABMOVE|Yalnızca iç kullanım içindir.|Yok.|Yok.||
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|Kullanıcı etkin Şerit denetimi kategori değiştiğinde framework ana kareye bu iletiyi gönderir.|Kullanılmadı.|Bir işaretçi `CMFCRibbonBar` kategorisi değişti.|Kullanılmadı.|
|AFX_WM_ON_CLOSEPOPUPWINDOW|Framework sahibini bildirmek için bu iletiyi gönderir `CMFCDesktopAlertWnd` penceresi Kapatılmak üzere olduğunu.|Kullanılmadı.|Bir işaretçi `CMFCDesktopAlertWnd` nesne.|Kullanılmadı.|
|AFX_WM_ON_DRAGCOMPLETE|Yalnızca iç kullanım içindir.|Yok.|Yok.|Yok.|
|AFX_WM_ON_GET_TAB_TOOLTIP|Özel araç ipuçları etkinleştirilip etkinleştirilmediğini hakkında bir sekme için bir araç ipucu görüntülemek için sekmesinde pencere olduğunda ana çerçeve penceresine Gönder.|Kullanılmadı.|Bir işaretçi bir `CMFCTabToolTipInfo` yapısı.|Kullanılmadı.|
|AFX_WM_ON_HSCROLL|Yeniden boyutlandırılabilir denetim çubuğu denetimine gönderilir. Bildirimleri almak için bu iletiyi işlemeli `CMFCTabCtrl` sekmeli pencere öğesi yatay kaydırma çubuğunun kaydırma olay meydana geldiğinde nesneleri.|Düşük düzey word kullanıcı belirten bir kaydırma çubuğu değer isteği kaydırma belirtir.  Daha fazla bilgi için bu konunun ilerleyen bölümlerinde tabloya bakın.|Kullanılmadı.|Sıfır dışında.|
|AFX_WM_ON_MOVE_TAB|Bir kullanıcı yeni bir konuma bir sekme sürüklediğinde sekmeli pencere üstüne gönderilir.|Özgün konumuna sekmede sıfır tabanlı dizini.|[out] Yeni konumuna sekmede sıfır tabanlı dizini.|Sıfır.|
|AFX_WM_ON_MOVETABCOMPLETE|Yalnızca iç kullanım içindir.|Yok.|Yok.|Yok.|
|AFX_WM_ON_MOVETOTABGROUP|MDI alt penceresine bir kullanıcı bir sekmeli grubundan diğerine taşır ana çerçeve penceresine gönderilir.|Sekmeli pencere için bir tanıtıcı (`CMFCTabCtrl`) öğesinden MDI alt penceresi kaldırıldı.|[out] Sekmeli pencere için bir tanıtıcı (`CMFCTabCtrl`) için MDI alt penceresi eklenmiş.|Yoksayıldı.|
|AFX_WM_ON_PRESS_CLOSE_BUTTON|Üst öğesi için gönderilen `CDockablePane` kullanıcı tıkladığında **Kapat** denetim çubuğu başlığını düğmesi.|Kullanılmadı.|Bir işaretçi üzerinde kullanıcı tıkladı yerleştirilebilir bir bölmeye **Kapat** düğmesi.|Bir bölme kapattıysanız TRUE; Aksi durumda FALSE.|
|AFX_WM_ON_RENAME_TAB|Düzenlenebilir bir sekme kullanıcı olarak yeniden adlandırıldı sekmeli penceresinin üst Gönder.|Yeniden adlandırılan sekmeye sıfır tabanlı dizini.|[out] Yeni sekme adı içeren bir dize işaretçisi.|Uygulama bu iletiyi işleyen olursa sıfır dışı; Çerçeve çağrı bastırır `CMFCBaseTabCtrl::SetTabLabel`.  Sıfır, sonra döndürülürse `CMFCBaseTabCtrl::SetTabLabel` framework tarafından çağırılır.|
|AFX_WM_ON_RIBBON_CUSTOMIZE|Kullanıcı özelleştirme başlattığında ana kareye gönderilir. Kendi özelleştirme iletişim kutusunda görüntülemek istiyorsanız, bu iletiyi işlemeli.|Kullanılmadı.|Özelleştirilecek Şerit denetimi bir işaretçi.|Sıfır uygulama bu iletiyi işleyen ve kendi özelleştirme iletişim kutusunu görüntüler. Uygulama sıfır döndürürse, framework yerleşik özelleştirme iletişim kutusunu görüntüler.|
|AFX_WM_ON_TABGROUPMOUSEMOVE|Yalnızca iç kullanım içindir.|Yok.|Yok.|Yok.|
|AFX_WM_POSTSETPREVIEWFRAME|Ana çerçeve kullanıcı yazdırma Önizleme modundan değiştirdi bildirmek için gönderilen|TRUE, yazdırma Önizleme modundan ayarlandığını gösterir. FALSE, Baskı Önizleme modunu kapalı olduğunu gösterir.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_PROPERTY_CHANGED|Özellik Kılavuzu denetimini sahibine Gönder (`CMFCPropertyGridCtrl`) kullanıcı seçili özelliğinin değeri değiştiğinde.|Özellik listesi denetiminin kimliği.|Özellik için bir işaretçi (`CMFCPropertyGridProperty`) değiştirilmiş.|Kullanılmadı.|
|AFX_WM_RESETCONTEXTMENU|Kullanıcı bağlam menüsü özelleştirme sırasında sıfırlandıktan sonra ana çerçeve penceresine Gönder.|Bağlam menüsü kaynak kimliği.|Geçerli bağlam menüsüne bir işaretçi `CMFCPopupMenu`.|Kullanılmadı.|
|AFX_WM_RESETKEYBOARD|Kullanıcının tüm klavye Hızlandırıcılar özelleştirme sırasında sıfırlandıktan sonra framework ana çerçeve penceresine bu iletiyi gönderir.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_RESETMENU|Framework menü sahibine (bir çerçeve penceresi) bu iletiyi gönderir, kullanıcı sıfırlar bir uygulama çerçevesi menüsü özelleştirme sırasında|Menü kaynak kimliği|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_RESETPROMPT|Araç çubuğu araç çubuğundan bir kullanıcı sıfırlama Özelleştir iletişim kutusu, çerçeve bu iletiyi gönderir. Varsayılan işleyici kullanıcı araç çubuğunu sıfırlama isteyip istemediğini sorar bir ileti kutusu görüntüler.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_RESETTOOLBAR|A `CMFCToolBar` nesneyi bir araç çubuğunun özgün durumuna başka bir deyişle, kaynaklardan yüklenen geri yüklendiğinde bu iletiyi gönderir. Araç çubuğu düğmeleri sınıfından türetilen sınıflar, yeniden eklemek bu iletiyi işlemeli `CMFCToolbarButton`. Daha fazla bilgi için bkz. `CMFCToolbarComboBoxButton`.|Durumu geri yüklenen bir araç çubuğu kaynak kimliği.|Kullanılmadı.|Sıfır.|
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton` Kullanıcı bir normal menü düğmesine tıkladığında nesne için sahibi bu iletiyi gönderir. Kullandığınız her zaman bu iletiyi işlemeli `CMFCToolbarMenuButton` kullanıcı bir düğmeyi tıkladığında bir açılan menüyü görüntülemek için.|İleti gönderen bir düğme komut kimliği.|İmleç ekran koordinatları. Düşük düzey word x koordinatını belirtir. Dwpoint y koordinatını belirtir.|Kullanılmadı.|
|AFX_WM_TOOLBARMENU|Ana çerçeve penceresine fare işaretçisi bir istemci ya da istemci dışı alan bölmesinin üzerindeyken kullanıcı sağ fare düğmesini bıraktığında Gönder.|Kullanılmadı.|Fare işaretçisinin koordinatlarını ekran. Düşük düzey word x koordinatını belirtir. Dwpoint y koordinatını belirtir.|Uygulama bu iletiyi işleyen olursa sıfır; Aksi takdirde, sıfır dışında.|
|AFX_WM_UPDATETOOLTIPS|Kendi araç ipucu denetimlerinin oluşturulması belirtmek için tüm araç ipucu sahiplerine gönderilir.|Bu iletiyi işlemesi gerektiğini denetim türü. Olası değerler listesi için bu konunun ilerleyen bölümlerinde tabloya bakın.|Kullanılmadı.|Kullanılmadı.|
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog` kullanıcı tıkladığında bu iletiyi ana kareye **yardımcı** düğmesine veya tıklayarak Yardım moduna girer **yardımcı** başlık düğmesi veya F1 tuşuna.|Kullanılmadı.|Örneğine bir işaretçi `CMFCWindowsManagerDialog`.|Kullanılmadı.|

Alt sınırı için değerleri aşağıdaki tabloda gösterilmektedir *lParam* AFX_WM_HSCROLL yönteminin parametresi:

|||
|-|-|
|Değer|Açıklama|
|SB_ENDSCROLL|Kullanıcı kaydırma sona erer.|
|SB_LEFT|Kullanıcı için üst sol kaydırır.|
|SB_RIGHT|Bir kullanıcı alt sağa kaydırır.|
|SB_LINELEFT|Kullanıcı, tek bir birim olarak sol kaydırır.|
|SB_LINERIGHT|Kullanıcı, bir birim sağa kaydırır.|
|SB_PAGELEFT|Kullanıcı, pencerenin genişliğini olarak sol kaydırır.|
|SB_PAGERIGHT|Kullanıcı tarafından pencerenin genişliğini sağa kaydırır.|
|SB_THUMBPOSITION|Kullanıcı, kaydırma kutusunun (Flash) sürüklediğiniz ve fare düğmesi serbest. Dwpoint sürükleme işleminin sonunda kaydırma kutusunun konumu belirtir.|
|SB_THUMBTRACK|Kullanıcının kaydırma kutusunun sürüklemekte olduğunu. Kullanıcı fare düğmesini bırakmadan AFX_WM_ON_HSCROLL ileti sürekli olarak bu değeri ile gönderilir. Yüksek düzeyli sözcük kaydırma kutusunun sürüklenen konumu belirtir.|

> [!NOTE]
>  Yüksek düzeyli sözcüğün *lParam* parametresi, düşük düzey sözcük SB_THUMBPOSITION veya SB_THUMBTRACK ise kaydırma kutusunun geçerli konumu belirtir; Aksi takdirde, bu sözcüğü kullanılmaz.

Bayrak değerleri için aşağıdaki tabloda *lParam* AFX_WM_UPDATETOOLTIPS iletisinin parametresi:

|||
|-|-|
|Bayrağı|Değer|
|AFX_TOOLTIP_TYPE_DEFAULT|0x0001|
|AFX_TOOLTIP_TYPE_TOOLBAR|0x0002|
|AFX_TOOLTIP_TYPE_TAB|0x0004|
|AFX_TOOLTIP_TYPE_MINIFRAME|0x0008|
|AFX_TOOLTIP_TYPE_DOCKBAR|0x0010|
|AFX_TOOLTIP_TYPE_EDIT|0x0020|
|AFX_TOOLTIP_TYPE_BUTTON|0x0040|
|AFX_TOOLTIP_TYPE_TOOLBOX|0x0080|
|AFX_TOOLTIP_TYPE_ALL|0xFFFF|

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
