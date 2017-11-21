---
title: AFX iletileri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords: AFX messages [MFC]
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 217379d94ca4c44e04837a7f777fce9e0e42cba6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="afx-messages"></a>AFX İletileri
Bu iletiler MFC'de kullanılır.  
  
## <a name="messages"></a>İletiler  
 MFC Kitaplığı'nda kullanılan mesajları aşağıdaki tabloda listelenmektedir:  
  
||||||  
|-|-|-|-|-|  
|İleti|Açıklama|[in]`wParam`|`lParam`(Tüm [in] aksi belirtilmedikçe parametreleridir.)|Dönüş Değeri|  
|AFX_WM_ACCGETOBJECT|Kullanılmadı.|Kullanılmadı.|Yok.|Yok.|  
|AFX_WM_ACCGETSTATE|Erişilebilirlik desteği için kullanılır. Bu ileti gönder `CMFCPopupMenu` veya `CMFCRibbonPanelMenu` geçerli öğesinin durumunu almak için.|Menü düğmesi veya ayırıcı öğenin dizini.|Kullanılmadı.|Öğesi durumu. Dizin geçersiz ise -1. menü düğmesi özel özniteliklere sahipse 0. Aksi takdirde aşağıdaki bayraklar birleşiminden oluşur:<br /><br /> TBBS_DISABLED — öğesi devre dışı<br /><br /> TBBS_CHECKED — madde işaretli<br /><br /> TBBS_BUTTON — öğe standart basma düğmesi.<br /><br /> TBBS_PRESSED — düğmesine basıldığında<br /><br /> TBBS_INDETERMINATE — tanımsız durumu<br /><br /> TBBS_SEPARATOR - yerine bir menü düğmesi diğer menü öğeleri arasında ayrım bir bu öğesi formları|  
|AFX_WM_CHANGE_ACTIVE_TAB|Framework yeniden boyutlandırılabilir denetim çubuğu denetimi için bu iletiyi gönderir. Bildirimleri almak için bu iletiyi `CMFCTabCtrl` nesneleri bir kullanıcının etkin bir sekme değiştirdiğinde.|Sekme dizini.|Kullanılmadı.|Sıfır olmayan.|  
|AFX_WM_CHANGE_CURRENT_FOLDER|Framework üst öğesi için bu iletiyi gönderir `CMFCShellListCtrl` kullanıcı geçerli klasörde değiştirilmemiş olduğunda.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|  
|AFX_WM_CHANGEVISUALMANAGER|Kullanıcı geçerli Visual Yöneticisi değiştirdiğinde çerçevesi için tüm çerçeve pencereleri bu iletiyi gönderir. Bu iletisine yanıt olarak bir çerçeve penceresinde kendi bölge yeniden hesaplar ve diğer parametreleri gerektiği gibi ayarlar. Bu olay hakkında bildirim almak gerekiyorsa, uygulamanızda AFX_WM_CHANGEVISUALMANAGER ileti işleyebilir. Taban sınıfı işleyici çağırması gerekir (`OnChangeVisualManager`) framework iç emin olmak için bu olay işleme gerçekleşir.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|  
|AFX_WM_CHANGING_ACTIVE_TAB|Üst için gönderilen `CMFCTabCtrl` nesnesi.  ' Den bildirim almak istiyorsanız, bu iletiyi işleyen `CMFCTabCtrl` nesneleri bir kullanıcı bir sekme sıfırlandıktan sonra.|Etkinleştirilmekte olan sekme dizini.|Kullanılmadı.|Sıfır olmayan.|  
|AFX_WM_CHECKEMPTYMINIFRAME|Yalnızca dahili kullanım için.|Yok.|Yok.|Yok.|  
|AFX_WM_CREATETOOLBAR|Gönderilen `CMFCToolBarsListPropertyPage` kullanıcı özelleştirme işlemi sırasında yeni bir araç çubuğu oluşturduğunda. Özel bir CMFCToolBar türetilen nesne örneğini oluşturmak için bu iletiyi işleyebilir. Bu iletiyi işlemek ve kendi araç oluşturursanız, varsayılan işleyici çağrısı yok sayın.|Kullanılmadı.|Araç çubuğunun adını içeren bir dize için bir işaretçi.|Yeni oluşturulan araç için bir işaretçi. Araç çubuğu oluşturma işlemi iptal edildi NULL gösterir.|  
|AFX_WM_CUSTOMIZEHELP|Ana çerçeve penceresi özelleştirme özellik sayfasından gönderilen `CMFCToolbarCustomize Dialog` kullanıcı bastığında **yardımcı** düğmesini veya F1 tuşuna.|Etkin sayfa özelleştirme özellik sayfasının belirtir.|Bir işaretçi bir `CMFCToolbarCustomize Dialog` nesnesi.|Sıfır.|  
|AFX_WM_CUSTOMIZETOOLBAR|`CMFCToolbarCustomize Dialog` Kullanıcı yeni bir araç çubuğu oluşturuyor üst çerçeve bildirmek için bu iletiyi gönderir.|`TRUE`özelleştirme başlatıldığında, `FALSE` özelleştirme tamamlandığında.|Kullanılmadı.|Sıfır.|  
|AFX_WM_DELETETOOLBAR|Kullanıcı bir araç çubuğunu özelleştirme modunda silmek üzere olduğunda ana çerçeve penceresi gönderilir.<br /><br /> Bir kullanıcı bir araç çubuğunu özelleştirme modunda sildiğinde ek eylemleri uygulamak için bu iletiyi işleyin. Varsayılan işleyici çağırması gerekir (`OnToolbarDelete`), araç siler. Varsayılan işleyici araç silmek mümkün olup olmadığını belirten bir değer döndürür.|Kullanılmadı.|İşaretçi bir `CMFCToolBar` silinecek nesne.|Araç çubuğu sildiyseniz sıfır olmayan; Aksi takdirde 0.|  
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton`Bu iletiyi belge renkleri almak için ana çerçeve penceresi gönderir.|Kullanılmadı.|[içinde out] İşaretçi bir `CList<COLORREF, COLORREF>` nesnesi.|Sıfır.|  
|AFX_WM_GETDRAGBOUNDS|Yalnızca dahili kullanım için.|Yok.|Yok.|Yok.|  
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|Bir kullanıcı bir Şerit liste öğesi vurgular ana çerçeve penceresi gönderilir.|Vurgulanan öğeyi dizini|Bir işaretçi`CMFCBaseRibbonElement`|Kullanılmadı.|  
|AFX_WM_ON_AFTER_SHELL_COMMAND|Bir üst öğesi gönderilen `CMFCShellListCtrl` veya `CMFCShellTreeCtrl` bir kullanıcı bir kabuk komut yürütme tamamlandığında denetler.|Kullanıcı çalıştırılan komut kimliği|Kullanılmadı.|Uygulama bu iletiyi işliyorsa, sıfır döndürmelidir.|  
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|Açılır menü görüntülemeden önce framework Şeridin üst öğeye bu iletiyi gönderir. Bu iletiyi işlemek ve açılır menüler dilediğiniz zaman değiştirebilirsiniz.|Kullanılmadı.|Bir işaretçi`CMFCBaseRibbonElement`|Kullanılmadı.|  
|AFX_WM_ON_CANCELTABMOVE|Yalnızca dahili kullanım için.|Yok.|Yok.||  
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|Kullanıcı etkin Şerit denetimi kategori değiştirdiğinde framework ana çerçeve bu iletiyi gönderir.|Kullanılmadı.|Bir işaretçi `CMFCRibbonBar` kategorisi değişti.|Kullanılmadı.|  
|AFX_WM_ON_CLOSEPOPUPWINDOW|Framework sahibi bildirmek için bu iletiyi gönderir `CMFCDesktopAlertWnd` penceresi Kapatılmak üzere olduğunu.|Kullanılmadı.|Bir işaretçi `CMFCDesktopAlertWnd` nesnesi.|Kullanılmadı.|  
|AFX_WM_ON_DRAGCOMPLETE|Yalnızca dahili kullanım için.|Yok.|Yok.|Yok.|  
|AFX_WM_ON_GET_TAB_TOOLTIP|Özel araç ipuçları etkinleştirilirse hakkında bir sekme için bir araç ipucunu görüntüleyebilirsiniz sekmesi penceresi olduğunda ana çerçeve penceresi gönderilir.|Kullanılmadı.|Bir işaretçi bir `CMFCTabToolTipInfo` yapısı.|Kullanılmadı.|  
|AFX_WM_ON_HSCROLL|Yeniden boyutlandırılabilir denetim çubuğu denetimi için gönderilir. Bildirimleri almak için bu iletiyi `CMFCTabCtrl` nesneleri sekmeli pencere öğesi yatay kaydırma çubuğunun kaydırma olay ortaya çıktığında.|Düşük düzey word kullanıcı belirten bir kaydırma çubuğunun değer isteği kaydırma belirtir.  Daha fazla bilgi için bu konunun ilerleyen bölümlerinde tabloya bakın.|Kullanılmadı.|Sıfır olmayan.|  
|AFX_WM_ON_MOVE_TAB|Bir kullanıcı yeni bir konuma bir sekme sürüklendiğinde sekmeli penceresinin üst gönderdi.|Özgün konumuna sekmede sıfır tabanlı dizini.|[out] Yeni konumunu sekmede sıfır tabanlı dizini.|Sıfır.|  
|AFX_WM_ON_MOVETABCOMPLETE|Yalnızca dahili kullanım için.|Yok.|Yok.|Yok.|  
|AFX_WM_ON_MOVETOTABGROUP|Bir kullanıcı bir MDI alt pencere bir sekmeli grubundan diğerine taşındığında ana çerçeve penceresi gönderdi.|Sekmeli penceresi için bir tanıtıcı (`CMFCTabCtrl`) gelen MDI alt pencere kaldırılmıştır.|[out] Sekmeli penceresi için bir tanıtıcı (`CMFCTabCtrl`) MDI alt pencere eklenmiş için.|Yoksayıldı.|  
|AFX_WM_ON_PRESS_CLOSE_BUTTON|Bir üst öğesi gönderilen `CDockablePane` kullanıcı tıkladığında **Kapat** denetim çubuğu başlık çubuğunda.|Kullanılmadı.|Kullanıcı tıklattığınız dockable bölmesi için bir işaretçi **Kapat** düğmesi.|`TRUE`bir bölme kapatılamaz Aksi takdirde FALSE.|  
|AFX_WM_ON_RENAME_TAB|Kullanıcı bir düzenlenebilir sekme yeniden adlandırılmış sonra sekmeli penceresinin üst gönderdi.|Yeniden adlandırılmış sekmesini sıfır tabanlı dizini.|[out] Yeni sekme adı içeren bir dize için bir işaretçi.|Uygulama bu ileti işlediğinde sıfır olmayan; framework çağrısı bastırır `CMFCBaseTabCtrl::SetTabLabel`.  Sıfır, ardından döndürülürse `CMFCBaseTabCtrl::SetTabLabel` çerçevesi tarafından çağrılır.|  
|AFX_WM_ON_RIBBON_CUSTOMIZE|Kullanıcı özelleştirme başladığında üst çerçeve gönderdi. Kendi özelleştirme iletişim kutusunu görüntülemek istiyorsanız, bu iletiyi işleyin.|Kullanılmadı.|Özelleştirilmiş Şerit denetimi için bir işaretçi.|Sıfır olmayan bir değer uygulama bu iletiyi işler ve kendi özelleştirme iletişim kutusunu görüntüler. Uygulama sıfır döndürürse, framework yerleşik özelleştirme iletişim kutusu görüntüler.|  
|AFX_WM_ON_TABGROUPMOUSEMOVE|Yalnızca dahili kullanım için.|Yok.|Yok.|Yok.|  
|AFX_WM_POSTSETPREVIEWFRAME|Kullanıcı Baskı Önizleme modunu değiştirdi ana çerçeve bildirmek için gönderilen|`TRUE`Baskı Önizleme modunu ayarlandığını gösterir. `FALSE`Bu Baskı Önizleme modunu kapalı olduğunu gösterir.|Kullanılmadı.|Kullanılmadı.|  
|AFX_WM_PROPERTY_CHANGED|Özellik kılavuz denetimi sahibine gönderilen (`CMFCPropertyGridCtrl`) kullanıcının seçili özelliğinin değeri değiştiğinde.|Özellik listesi denetim kimliği.|Özelliği için bir işaretçi (`CMFCPropertyGridProperty`) değiştirilmiş.|Kullanılmadı.|  
|AFX_WM_RESETCONTEXTMENU|Kullanıcı bağlam menüsü özelleştirme sırasında sıfırlandıktan sonra ana çerçeve penceresi gönderdi.|Bağlam menüsü kaynak kimliği.|Geçerli bağlam menüsüne bir işaretçi `CMFCPopupMenu`.|Kullanılmadı.|  
|AFX_WM_RESETKEYBOARD|Kullanıcı tüm klavye Hızlandırıcıları özelleştirme sırasında sıfırlandıktan sonra framework ana çerçeve penceresi bu iletiyi gönderir.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|  
|AFX_WM_RESETMENU|Framework menü sahibine (bir çerçeve penceresinde) bu iletiyi gönderir zaman kullanıcı sıfırlar bir uygulama çerçevesi menüsü özelleştirme sırasında|Menü kaynak kimliği|Kullanılmadı.|Kullanılmadı.|  
|AFX_WM_RESETPROMPT|Araç çubuğu araç çubuğundan bir kullanıcı sıfırlama Özelleştir iletişim kutusu, çerçeve bu iletiyi gönderir. Varsayılan işleyici kullanıcı araç sıfırlamak istediğini soran bir ileti kutusu görüntüler.|Kullanılmadı.|Kullanılmadı.|Kullanılmadı.|  
|AFX_WM_RESETTOOLBAR|A `CMFCToolBar` nesne bir araç çubuğu özgün durumuna, diğer bir deyişle, kaynaklardan yüklenen geri yüklendiğinde bu iletiyi gönderir. Bu ileti, sınıfları türetilir araç çubuğu düğmeleri yeniden işleme `CMFCToolbarButton`. Daha fazla bilgi için bkz. `CMFCToolbarComboBoxButton`.|Durumu geri yüklenen bir araç çubuğu kaynak kimliği.|Kullanılmadı.|Sıfır.|  
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton`Kullanıcı bir normal menü düğmesini tıklattığında nesne sahibi bu iletiyi gönderir. Kullandığınız her zaman bu iletiyi işleyen `CMFCToolbarMenuButton` kullanıcı bir düğmesine tıkladığında açılır menü görüntülenecek.|İletinin gönderen bir düğme komut kimliği.|İmleç ekran koordinatları. Düşük düzey word x koordinatını belirtir. Yüksek düzey word y koordinatını belirtir.|Kullanılmadı.|  
|AFX_WM_TOOLBARMENU|Fare işaretçisini istemci veya istemci dışı alan bölmesinin durumdayken kullanıcı farenin sağ düğmesiyle bıraktığında ana çerçeve penceresi gönderdi.|Kullanılmadı.|Ekran koordinatları fare işaretçisi. Düşük düzey word x koordinatını belirtir. Yüksek düzey word y koordinatını belirtir.|Uygulama bu ileti işlediğinde sıfır; Aksi takdirde, sıfır olmayan bir değer.|  
|AFX_WM_UPDATETOOLTIPS|Kendi araç ipucu denetimlerinin yeniden oluşturulması belirtmek için tüm araç ipucu sahiplerine gönderilir.|Bu iletiyi işlemesi gerektiğini denetim türü. Olası değerler listesi için bu konunun ilerleyen bölümlerinde bkz.|Kullanılmadı.|Kullanılmadı.|  
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog`kullanıcı tıkladığında bu iletiyi üst çerçeve gönderir **yardımcı** düğmesini veya tıklayarak Yardım moduna girer **yardımcı** resim yazısı düğmesini veya F1 tuşuna.|Kullanılmadı.|Örneği için bir işaretçi `CMFCWindowsManagerDialog`.|Kullanılmadı.|  
  
 Düşük sözcüğün için değerleri aşağıdaki tabloda gösterilmektedir `lParam` AFX_WM_HSCROLL yönteminin parametresi:  
  
|||  
|-|-|  
|Değer|Açıklama|  
|SB_ENDSCROLL|Kullanıcı kaydırma sona erer.|  
|SB_LEFT|Kullanıcı için Üst Sola kaydırır.|  
|SB_RIGHT|Kullanıcı alt sağa kaydırır.|  
|SB_LINELEFT|Kullanıcı bir birim Sola kaydırır.|  
|SB_LINERIGHT|Kullanıcı bir birim sağa kaydırır.|  
|SB_PAGELEFT|Kullanıcı pencere genişliğine göre Sola kaydırır.|  
|SB_PAGERIGHT|Kullanıcı sağa penceresinin genişliğiyle kayar.|  
|SB_THUMBPOSITION|Kullanıcı, kaydırma kutusunun (Flash) sürüklenen ve fare düğmesini yayımladı. Yüksek düzey word sürükleme işleminin sonunda kaydırma kutusunun konumunu belirtir.|  
|SB_THUMBTRACK|Kullanıcı, kaydırma kutusunun sürükleyerek. Kullanıcının fare düğmesini serbest kadar AFX_WM_ON_HSCROLL ileti bu değerle sürekli olarak gönderilir. Yüksek düzey sözcük kaydırma kutusunun sürüklenen konumu belirtir.|  
  
> [!NOTE]
>  Yüksek düzey sözcüğün `lParam` parametresi, düşük düzey sözcük SB_THUMBPOSITION veya SB_THUMBTRACK ise kaydırma kutusunun geçerli konumu belirtir; Aksi takdirde, bu word kullanılmaz.  
  
 Bayrak değerleri aşağıdaki tabloda listelenmektedir `lParam` AFX_WM_UPDATETOOLTIPS iletisinin parametre:  
  
|||  
|-|-|  
|Bayrağı|Değer|  
|AFX_TOOLTIP_TYPE_DEFAULT|0X0001|  
|AFX_TOOLTIP_TYPE_TOOLBAR|0X0002|  
|AFX_TOOLTIP_TYPE_TAB|0X0004|  
|AFX_TOOLTIP_TYPE_MINIFRAME|0X0008|  
|AFX_TOOLTIP_TYPE_DOCKBAR|0x0010|  
|AFX_TOOLTIP_TYPE_EDIT|0x0020|  
|AFX_TOOLTIP_TYPE_BUTTON|0x0040|  
|AFX_TOOLTIP_TYPE_TOOLBOX|0x0080|  
|AFX_TOOLTIP_TYPE_ALL|0xFFFF|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
