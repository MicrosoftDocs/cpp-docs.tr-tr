---
title: CBasePane sınıfı
ms.date: 11/06/2018
f1_keywords:
- CBasePane
- AFXBASEPANE/CBasePane
- AFXBASEPANE/CBasePane::AccNotifyObjectFocusEvent
- AFXBASEPANE/CBasePane::AddPane
- AFXBASEPANE/CBasePane::AdjustDockingLayout
- AFXBASEPANE/CBasePane::AdjustLayout
- AFXBASEPANE/CBasePane::CalcFixedLayout
- AFXBASEPANE/CBasePane::CanAcceptPane
- AFXBASEPANE/CBasePane::CanAutoHide
- AFXBASEPANE/CBasePane::CanBeAttached
- AFXBASEPANE/CBasePane::CanBeClosed
- AFXBASEPANE/CBasePane::CanBeDocked
- AFXBASEPANE/CBasePane::CanBeResized
- AFXBASEPANE/CBasePane::CanBeTabbedDocument
- AFXBASEPANE/CBasePane::CanFloat
- AFXBASEPANE/CBasePane::CanFocus
- AFXBASEPANE/CBasePane::CopyState
- AFXBASEPANE/CBasePane::CreateDefaultMiniframe
- AFXBASEPANE/CBasePane::CreateEx
- AFXBASEPANE/CBasePane::DockPane
- AFXBASEPANE/CBasePane::DockPaneUsingRTTI
- AFXBASEPANE/CBasePane::DockToFrameWindow
- AFXBASEPANE/CBasePane::DoesAllowDynInsertBefore
- AFXBASEPANE/CBasePane::EnableDocking
- AFXBASEPANE/CBasePane::EnableGripper
- AFXBASEPANE/CBasePane::FloatPane
- AFXBASEPANE/CBasePane::get_accHelpTopic
- AFXBASEPANE/CBasePane::get_accSelection
- AFXBASEPANE/CBasePane::GetCaptionHeight
- AFXBASEPANE/CBasePane::GetControlBarStyle
- AFXBASEPANE/CBasePane::GetCurrentAlignment
- AFXBASEPANE/CBasePane::GetDockingMode
- AFXBASEPANE/CBasePane::GetDockSiteFrameWnd
- AFXBASEPANE/CBasePane::GetEnabledAlignment
- AFXBASEPANE/CBasePane::GetMFCStyle
- AFXBASEPANE/CBasePane::GetPaneIcon
- AFXBASEPANE/CBasePane::GetPaneRow
- AFXBASEPANE/CBasePane::GetPaneStyle
- AFXBASEPANE/CBasePane::GetParentDockSite
- AFXBASEPANE/CBasePane::GetParentMiniFrame
- AFXBASEPANE/CBasePane::GetParentTabbedPane
- AFXBASEPANE/CBasePane::GetParentTabWnd
- AFXBASEPANE/CBasePane::GetRecentVisibleState
- AFXBASEPANE/CBasePane::HideInPrintPreviewMode
- AFXBASEPANE/CBasePane::InsertPane
- AFXBASEPANE/CBasePane::IsAccessibilityCompatible
- AFXBASEPANE/CBasePane::IsAutoHideMode
- AFXBASEPANE/CBasePane::IsDialogControl
- AFXBASEPANE/CBasePane::IsDocked
- AFXBASEPANE/CBasePane::IsFloating
- AFXBASEPANE/CBasePane::IsHorizontal
- AFXBASEPANE/CBasePane::IsInFloatingMultiPaneFrameWnd
- AFXBASEPANE/CBasePane::IsMDITabbed
- AFXBASEPANE/CBasePane::IsPaneVisible
- AFXBASEPANE/CBasePane::IsPointNearDockSite
- AFXBASEPANE/CBasePane::IsResizable
- AFXBASEPANE/CBasePane::IsRestoredFromRegistry
- AFXBASEPANE/CBasePane::IsTabbed
- AFXBASEPANE/CBasePane::IsVisible
- AFXBASEPANE/CBasePane::LoadState
- AFXBASEPANE/CBasePane::MoveWindow
- AFXBASEPANE/CBasePane::OnAfterChangeParent
- AFXBASEPANE/CBasePane::OnBeforeChangeParent
- AFXBASEPANE/CBasePane::OnDrawCaption
- AFXBASEPANE/CBasePane::OnMovePaneDivider
- AFXBASEPANE/CBasePane::OnPaneContextMenu
- AFXBASEPANE/CBasePane::OnRemoveFromMiniFrame
- AFXBASEPANE/CBasePane::OnSetAccData
- AFXBASEPANE/CBasePane::PaneFromPoint
- AFXBASEPANE/CBasePane::RecalcLayout
- AFXBASEPANE/CBasePane::RemovePaneFromDockManager
- AFXBASEPANE/CBasePane::SaveState
- AFXBASEPANE/CBasePane::SelectDefaultFont
- AFXBASEPANE/CBasePane::SetControlBarStyle
- AFXBASEPANE/CBasePane::SetDockingMode
- AFXBASEPANE/CBasePane::SetPaneAlignment
- AFXBASEPANE/CBasePane::SetPaneStyle
- AFXBASEPANE/CBasePane::SetWindowPos
- AFXBASEPANE/CBasePane::ShowPane
- AFXBASEPANE/CBasePane::StretchPane
- AFXBASEPANE/CBasePane::UndockPane
- AFXBASEPANE/CBasePane::DoPaint
helpviewer_keywords:
- CBasePane [MFC], AccNotifyObjectFocusEvent
- CBasePane [MFC], AddPane
- CBasePane [MFC], AdjustDockingLayout
- CBasePane [MFC], AdjustLayout
- CBasePane [MFC], CalcFixedLayout
- CBasePane [MFC], CanAcceptPane
- CBasePane [MFC], CanAutoHide
- CBasePane [MFC], CanBeAttached
- CBasePane [MFC], CanBeClosed
- CBasePane [MFC], CanBeDocked
- CBasePane [MFC], CanBeResized
- CBasePane [MFC], CanBeTabbedDocument
- CBasePane [MFC], CanFloat
- CBasePane [MFC], CanFocus
- CBasePane [MFC], CopyState
- CBasePane [MFC], CreateDefaultMiniframe
- CBasePane [MFC], CreateEx
- CBasePane [MFC], DockPane
- CBasePane [MFC], DockPaneUsingRTTI
- CBasePane [MFC], DockToFrameWindow
- CBasePane [MFC], DoesAllowDynInsertBefore
- CBasePane [MFC], EnableDocking
- CBasePane [MFC], EnableGripper
- CBasePane [MFC], FloatPane
- CBasePane [MFC], get_accHelpTopic
- CBasePane [MFC], get_accSelection
- CBasePane [MFC], GetCaptionHeight
- CBasePane [MFC], GetControlBarStyle
- CBasePane [MFC], GetCurrentAlignment
- CBasePane [MFC], GetDockingMode
- CBasePane [MFC], GetDockSiteFrameWnd
- CBasePane [MFC], GetEnabledAlignment
- CBasePane [MFC], GetMFCStyle
- CBasePane [MFC], GetPaneIcon
- CBasePane [MFC], GetPaneRow
- CBasePane [MFC], GetPaneStyle
- CBasePane [MFC], GetParentDockSite
- CBasePane [MFC], GetParentMiniFrame
- CBasePane [MFC], GetParentTabbedPane
- CBasePane [MFC], GetParentTabWnd
- CBasePane [MFC], GetRecentVisibleState
- CBasePane [MFC], HideInPrintPreviewMode
- CBasePane [MFC], InsertPane
- CBasePane [MFC], IsAccessibilityCompatible
- CBasePane [MFC], IsAutoHideMode
- CBasePane [MFC], IsDialogControl
- CBasePane [MFC], IsDocked
- CBasePane [MFC], IsFloating
- CBasePane [MFC], IsHorizontal
- CBasePane [MFC], IsInFloatingMultiPaneFrameWnd
- CBasePane [MFC], IsMDITabbed
- CBasePane [MFC], IsPaneVisible
- CBasePane [MFC], IsPointNearDockSite
- CBasePane [MFC], IsResizable
- CBasePane [MFC], IsRestoredFromRegistry
- CBasePane [MFC], IsTabbed
- CBasePane [MFC], IsVisible
- CBasePane [MFC], LoadState
- CBasePane [MFC], MoveWindow
- CBasePane [MFC], OnAfterChangeParent
- CBasePane [MFC], OnBeforeChangeParent
- CBasePane [MFC], OnDrawCaption
- CBasePane [MFC], OnMovePaneDivider
- CBasePane [MFC], OnPaneContextMenu
- CBasePane [MFC], OnRemoveFromMiniFrame
- CBasePane [MFC], OnSetAccData
- CBasePane [MFC], PaneFromPoint
- CBasePane [MFC], RecalcLayout
- CBasePane [MFC], RemovePaneFromDockManager
- CBasePane [MFC], SaveState
- CBasePane [MFC], SelectDefaultFont
- CBasePane [MFC], SetControlBarStyle
- CBasePane [MFC], SetDockingMode
- CBasePane [MFC], SetPaneAlignment
- CBasePane [MFC], SetPaneStyle
- CBasePane [MFC], SetWindowPos
- CBasePane [MFC], ShowPane
- CBasePane [MFC], StretchPane
- CBasePane [MFC], UndockPane
- CBasePane [MFC], DoPaint
ms.assetid: 8163dd51-d7c7-4def-9c74-61f8ecdfad82
ms.openlocfilehash: 59291516c14ea6ff8b1d2fe515d121dd6f910cba
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507466"
---
# <a name="cbasepane-class"></a>CBasePane sınıfı

MFC 'deki tüm bölmeler için temel sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CBasePane : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CBasePane::CBasePane`|Varsayılan Oluşturucu.|
|`CBasePane::~CBasePane`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CBasePane::accHitTest`|Ekranın verilen bir noktada alt öğe veya alt nesne almak için Framework tarafından çağırılır. ( [CWnd:: accHitTest](../../mfc/reference/cwnd-class.md#acchittest)geçersiz kılar.)|
|`CBasePane::accLocation`|Belirtilen nesnenin geçerli ekran konumunu almak için Framework tarafından çağırılır. ( [CWnd:: accLocation](../../mfc/reference/cwnd-class.md#acclocation).)|
|[CBasePane:: AccNotifyObjectFocusEvent](#accnotifyobjectfocusevent)|`CBasePane`Bu yöntemi kullanmaz.|
|`CBasePane::accSelect`|Seçimi değiştirmek veya belirtilen nesnenin klavye odağını taşımak için Framework tarafından çağırılır. ( [CWnd:: accSelect](../../mfc/reference/cwnd-class.md#accselect).)|
|[CBasePane:: AddPane](#addpane)|Yerleştirme yöneticisine bir bölme ekler.|
|[CBasePane:: AdjustDockingLayout](#adjustdockinglayout)|Yerleştirme yerleşimini ayarlamak için yerleştirme Yöneticisi 'ne yapılan çağrıyı yeniden yönlendirir.|
|[CBasePane:: AdjustLayout](#adjustlayout)|Bölmenin iç yerleşimini ayarlaması gerektiğinde Framework tarafından çağırılır.|
|[CBasePane:: CalcFixedLayout](#calcfixedlayout)|Bir denetim çubuğunun yatay boyutunu hesaplar.|
|[CBasePane:: CanAcceptPane](#canacceptpane)|Başka bir bölmenin bölmesine yerleştirilip yerleştirilmeyeceğini belirler.|
|[CBasePane:: Canotomatik gizle](#canautohide)|Bölmenin otomatik gizleme modunu destekleyip desteklemediğini belirler.|
|[CBasePane:: Canbeekli](#canbeattached)|Bölmenin başka bir bölmeye sabitlenebilir olup olmayacağını belirler.|
|[CBasePane:: CanBeClosed](#canbeclosed)|Bölmenin kapatılıp kapatılamayacağını belirler.|
|[CBasePane:: Canbeyerleştirildi](#canbedocked)|Bölmenin başka bir bölmeye sabitlenebilir olup olmayacağını belirler.|
|[CBasePane:: Canbereslanmış](#canberesized)|Bölmenin yeniden boyutlandırılıp boyutlandırılmayacağını belirler.|
|[CBasePane:: CanBeTabbedDocument](#canbetabbeddocument)|Bölmenin bir MDI sekmeli belgesine dönüştürülüp dönüştürülmeyeceğini belirtir.|
|[CBasePane:: CanFloat](#canfloat)|Bölmenin kayıp kayamayacağını belirler.|
|[CBasePane:: CanFocus](#canfocus)|Bölmenin odak alıp alamayacağını belirtir.|
|[CBasePane:: CopyState](#copystate)|Verilen bölmenin durumunu kopyalar.|
|[CBasePane:: CreateDefaultMiniframe](#createdefaultminiframe)|Bölme taşınabilir ise, bir mini çerçeve penceresi oluşturur.|
|[CBasePane:: CreateEx](#createex)|Bölme denetimini oluşturur.|
|[CBasePane::D ockPane](#dockpane)|Bir bölmeyi başka bir bölmeye veya bir çerçeve penceresine göre oluşturma.|
|[CBasePane::D Ockbölmesi Usingrttı](#dockpaneusingrtti)|Çalışma zamanı tür bilgilerini kullanarak bölmeyi noktaları.|
|[CBasePane: ockToFrameWindow:D](#docktoframewindow)|Bir çerçeveye yerleştirilebilir bölmesi noktası oluşturma.|
|[CBasePane::D Oesallowdynınsertbefore](#doesallowdyninsertbefore)|Bu bölme ve üst çerçeve arasında dinamik olarak bir bölme eklenip eklenemeyeceğini belirler.|
|[CBasePane:: EnableDocking](#enabledocking)|Bölmeyi ana çerçeveye yerleştirmeyi sağlar.|
|[CBasePane:: Enablekavrayıcı](#enablegripper)|Kavrayıcıyı etkinleştirilir veya devre dışı bırakır. Kavrayıcı etkinleştirilmişse, Kullanıcı bölmeyi yeniden konumlandırmak için onu sürükleyebilirsiniz.|
|`CBasePane::FillWindowRect`|Dahili olarak kullanılır.|
|[CBasePane:: FloatPane](#floatpane)|Bölmeyi kayın.|
|`CBasePane::get_accChild`|Belirtilen alt için bir `IDispatch` arabirimin adresini almak üzere Framework tarafından çağırılır. ( [CWnd:: get_accChild](../../mfc/reference/cwnd-class.md#get_accchild).) öğesini geçersiz kılar|
|`CBasePane::get_accChildCount`|Bu nesneye ait alt öğelerin sayısını almak için Framework tarafından çağırılır. ( [CWnd:: get_accChildCount](../../mfc/reference/cwnd-class.md#get_accchildcount).) öğesini geçersiz kılar|
|`CBasePane::get_accDefaultAction`|Nesnenin varsayılan eylemini tanımlayan bir dize almak için Framework tarafından çağırılır. ( [CWnd:: get_accDefaultAction](../../mfc/reference/cwnd-class.md#get_accdefaultaction).) öğesini geçersiz kılar|
|`CBasePane::get_accDescription`|Belirtilen nesnenin görsel görünümünü açıklayan bir dize almak için Framework tarafından çağırılır. ( [CWnd:: get_accDescription](../../mfc/reference/cwnd-class.md#get_accdescription).) öğesini geçersiz kılar|
|`CBasePane::get_accFocus`|Klavye odağına sahip nesneyi almak için Framework tarafından çağırılır. ( [CWnd:: get_accFocus](../../mfc/reference/cwnd-class.md#get_accfocus).) öğesini geçersiz kılar|
|`CBasePane::get_accHelp`|Nesne için yardım özelliği dizesi almak için Framework tarafından çağırılır. ( [CWnd:: get_accHelp](../../mfc/reference/cwnd-class.md#get_acchelp).) öğesini geçersiz kılar|
|[CBasePane:: get_accHelpTopic](#get_acchelptopic)|Belirtilen nesneyle ilişkili WinHelp dosyasının tam yolunu ve bu dosyadaki ilgili konunun tanımlayıcısını almak için Framework tarafından çağırılır. ( [CWnd:: get_accHelpTopic](../../mfc/reference/cwnd-class.md#get_acchelptopic).) öğesini geçersiz kılar|
|`CBasePane::get_accKeyboardShortcut`|Nesne için belirtilen kısayol tuşunu almak için Framework tarafından çağırılır. ( [CWnd:: get_accKeyboardShortcut](../../mfc/reference/cwnd-class.md#get_acckeyboardshortcut).) öğesini geçersiz kılar|
|`CBasePane::get_accName`|Belirtilen nesnenin adını almak için Framework tarafından çağırılır. ( [CWnd:: get_accName](../../mfc/reference/cwnd-class.md#get_accname).) öğesini geçersiz kılar|
|`CBasePane::get_accParent`|Nesnenin üst öğesinin `IDispatch` arabirimini almak için Framework tarafından çağırılır. ( [CWnd:: get_accParent](../../mfc/reference/cwnd-class.md#get_accparent).) öğesini geçersiz kılar|
|`CBasePane::get_accRole`|Belirtilen nesnenin rolünü açıklayan bilgileri almak için Framework tarafından çağırılır. ( [CWnd:: get_accRole](../../mfc/reference/cwnd-class.md#get_accrole).) öğesini geçersiz kılar|
|[CBasePane:: get_accSelection](#get_accselection)|Bu nesnenin seçili alt öğelerini almak için Framework tarafından çağırılır. ( [CWnd:: get_accSelection](../../mfc/reference/cwnd-class.md#get_accselection).) öğesini geçersiz kılar|
|`CBasePane::get_accState`|Belirtilen nesnenin geçerli durumunu almak için Framework tarafından çağırılır. ( [CWnd:: get_accState](../../mfc/reference/cwnd-class.md#get_accstate).) öğesini geçersiz kılar|
|`CBasePane::get_accValue`|Belirtilen nesnenin değerini almak için Framework tarafından çağırılır. ( [CWnd:: get_accValue](../../mfc/reference/cwnd-class.md#get_accvalue).) öğesini geçersiz kılar|
|[CBasePane:: GetCaptionHeight](#getcaptionheight)|Başlık yüksekliğini döndürür.|
|[CBasePane:: GetControlBarStyle](#getcontrolbarstyle)|Denetim çubuğu stilini döndürür.|
|[CBasePane:: GetCurrentAlignment](#getcurrentalignment)|Geçerli bölme hizalamasını döndürür.|
|[CBasePane:: GetDockingMode](#getdockingmode)|Bölme için geçerli yerleştirme modunu döndürür.|
|[CBasePane:: GetDockSiteFrameWnd](#getdocksiteframewnd)|Bölmenin Dock sitesi olan pencereye bir işaretçi döndürür.|
|[CBasePane:: Getenabledhizalaması](#getenabledalignment)|Bölmeye uygulanan CBRS_ALIGN_ stillerini döndürür.|
|[CBasePane:: GetMFCStyle](#getmfcstyle)|MFC 'ye özgü bölme stillerini döndürür.|
|[CBasePane:: GetPaneIcon](#getpaneicon)|Bölme simgesine bir tanıtıcı döndürür.|
|`CBasePane::GetPaneRect`|Dahili olarak kullanılır.|
|[CBasePane:: GetPaneRow](#getpanerow)|Bölmenin yerleştirildiği [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)nesnesine bir işaretçi döndürür.|
|[CBasePane:: Getbölmesi stili](#getpanestyle)|Bölme stilini döndürür.|
|[CBasePane:: GetParentDockSite](#getparentdocksite)|Üst Dock sitesine bir işaretçi döndürür.|
|[CBasePane:: GetParentMiniFrame](#getparentminiframe)|Üst mini çerçeve penceresine bir işaretçi döndürür.|
|[CBasePane:: GetParentTabbedPane](#getparenttabbedpane)|Üst sekmeli bölmeye bir işaretçi döndürür.|
|[CBasePane:: GetParentTabWnd](#getparenttabwnd)|Bir sekme içinde olan üst pencereye bir işaretçi döndürür.|
|[CBasePane:: GetRecentVisibleState](#getrecentvisiblestate)|Bir bölme bir arşivden geri yüklendiğinde Framework bu yöntemi çağırır.|
|[CBasePane:: Hideınprintönizleme modu](#hideinprintpreviewmode)|Bölmenin baskı önizlemede gizlenip gizlenmeyeceğini belirtir.|
|[CBasePane:: InsertPane](#insertpane)|Belirtilen bölmeyi yerleştirme yöneticisiyle kaydeder.|
|[CBasePane:: IsAccessibilityCompatible](#isaccessibilitycompatible)|Bölmenin etkin erişilebilirliği destekleyip desteklemediğini belirtir.|
|[CBasePane:: ısoto Hidemode](#isautohidemode)|Bir bölmenin otomatik gizleme modunda olup olmadığını belirler.|
|[CBasePane:: ısdialogcontrol](#isdialogcontrol)|Bölmenin bir iletişim denetimi olup olmadığını belirtir.|
|[CBasePane:: ıyerleştirildi](#isdocked)|Bölmenin yerleştirilmiş olup olmadığını belirler.|
|[CBasePane:: ıskayan](#isfloating)|Bölmenin kayan olup olmadığını belirler.|
|[CBasePane:: ısyatay](#ishorizontal)|Bölmenin yatay olarak yerleştirilmiş olup olmadığını belirler.|
|[CBasePane:: ısinfloatingmultipane Framewnd](#isinfloatingmultipaneframewnd)|Bölmenin çok bölgeli bir çerçeve penceresinde olup olmadığını belirtir.|
|[CBasePane:: ısmdısekmeli](#ismditabbed)|Bölmenin bir MDI alt penceresine sekmeli belge olarak eklenip eklenmeyeceğini belirler.|
|[CBasePane:: IsPaneVisible](#ispanevisible)|Bölme için WS_VISIBLE bayrağının ayarlanmış olup olmadığını belirtir.|
|[CBasePane:: ıspointyaklaştığında Docksite](#ispointneardocksite)|Belirtilen noktanın Dock sitesine yakın olup olmadığını belirler.|
|[CBasePane:: ısyeniden boyutlandırılabilir](#isresizable)|Bölmenin yeniden boyutlandırılıp boyutlandırılmayacağını belirler.|
|[CBasePane:: ısrestoredfromregistry](#isrestoredfromregistry)|Bölmenin kayıt defterinden geri yüklenip yüklenmediğini belirler.|
|[CBasePane:: ıssekmeli](#istabbed)|Bölmenin sekmeli pencerenin Sekme denetimine eklenip eklenmeyeceğini belirler.|
|`CBasePane::IsTooltipTopmost`|Dahili olarak kullanılır.|
|[CBasePane:: IsVisible](#isvisible)|Bölmenin görünür olup olmadığını belirler.|
|[CBasePane:: LoadState](#loadstate)|Bölme durumunu kayıt defterinden yükler.|
|[CBasePane:: MoveWindow](#movewindow)|Bölmeyi gider.|
|[CBasePane:: OnAfterChangeParent](#onafterchangeparent)|Bölmenin üst öğesi değiştirildiğinde Framework tarafından çağırılır.|
|[CBasePane:: OnBeforeChangeParent](#onbeforechangeparent)|Bölme, ana penceresini değiştirmeden hemen önce çerçevesi tarafından çağırılır.|
|[CBasePane:: OnDrawCaption](#ondrawcaption)|Resim yazısı çizildiğinde çerçeve bu yöntemi çağırır.|
|[CBasePane:: OnMovePaneDivider](#onmovepanedivider)|Bu yöntem şu anda kullanılmıyor.|
|[CBasePane:: Onbölmesi ContextMenu](#onpanecontextmenu)|Bir bölme listesi olan bir menü oluşturduğunda Framework tarafından çağırılır.|
|[CBasePane:: OnRemoveFromMiniFrame](#onremovefromminiframe)|Bir bölme üst mini çerçeve penceresinden kaldırıldığında Framework tarafından çağırılır.|
|[CBasePane:: OnSetAccData](#onsetaccdata)|`CBasePane`Bu yöntemi kullanmaz.|
|`CBasePane::OnUpdateCmdUI`|Dahili olarak kullanılır.|
|[CBasePane::P aneFromPoint](#panefrompoint)|Verilen noktayı içeren bölmeyi döndürür.|
|`CBasePane::PreTranslateMessage`|[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine dağıtılmadan önce pencere iletilerini dönüştürmek için [CWinApp](../../mfc/reference/cwinapp-class.md) sınıfı tarafından kullanılır. ( [CWnd::P reTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)geçersiz kılar.)|
|[CBasePane:: RecalcLayout](#recalclayout)|`CBasePane`Bu yöntemi kullanmaz.|
|[CBasePane:: RemovePaneFromDockManager](#removepanefromdockmanager)|Bir bölmenin kaydını siler ve yerleştirme yöneticisindeki listeden kaldırır.|
|[CBasePane:: Savemlak](#savestate)|Bölmenin durumunu kayıt defterine kaydeder.|
|[CBasePane:: SelectDefaultFont](#selectdefaultfont)|Belirtilen cihaz bağlamı için varsayılan yazı tipini seçer.|
|`CBasePane::Serialize`|Bu nesneyi veya bir arşivden okur veya yazar. ( [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize)geçersiz kılar.)|
|[CBasePane:: SetControlBarStyle](#setcontrolbarstyle)|Denetim çubuğu stilini ayarlar.|
|[CBasePane:: SetDockingMode](#setdockingmode)|Bölme için yerleştirme modunu ayarlar.|
|`CBasePane::SetMDITabbed`|Dahili olarak kullanılır.|
|[CBasePane:: Setbölmesi hizalaması](#setpanealignment)|Bölmenin hizalamasını ayarlar.|
|`CBasePane::SetPaneRect`|Dahili olarak kullanılır.|
|[CBasePane:: Setbölmesi stili](#setpanestyle)|Bölmenin stilini ayarlar.|
|`CBasePane::SetRestoredFromRegistry`|Dahili olarak kullanılır.|
|[CBasePane:: SetWindowPos](#setwindowpos)|Bölmenin boyutunu, konumunu ve Z düzenini değiştirir.|
|[CBasePane:: ShowPane](#showpane)|Bölmeyi gösterir veya gizler.|
|[CBasePane:: ayarlayıcı bölmesi](#stretchpane)|Bir bölmeyi dikey veya yatay olarak uzatır.|
|[CBasePane:: UndockPane](#undockpane)|Bölmeyi yerleştirme sitesinden, varsayılan kaydırıcıdan veya şu anda yerleştirilmiş olan mini çerçeve penceresinden kaldırır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CBasePane::D oPaint](#dopaint)|Bölmenin arka planını doldurur.|

## <a name="remarks"></a>Açıklamalar

MFC 'de kullanılabilen genişletilmiş yerleştirme özelliklerini destekleyen bir bölme sınıfı oluşturmak isterseniz, `CBasePane` [CPane sınıfından](../../mfc/reference/cpane-class.md)veya sınıfından türetmeniz gerekir.

## <a name="customization-tips"></a>Özelleştirme Ipuçları

Aşağıdaki özelleştirme ipuçları, `CBasePane Class` ve bundan kalıtımla alan tüm sınıflar için de ilgilidir:

- Bir bölme oluşturduğunuzda, birkaç yeni stil uygulayabilirsiniz:

  - AFX_CBRS_FLOAT, bölmeyi yüzer hale getirir.

  - AFX_CBRS_AUTOHIDE otomatik gizleme moduna izin vermez.

  - AFX_CBRS_CLOSE, bölmenin kapatılmasını sağlar (gizli).

  Bunlar bit düzeyinde veya işlemle birleştirebileceğiniz bayraklardır.

`CBasePane`Bu bayrakları yansıtmak için aşağıdaki sanal Boole yöntemlerini uygular: [CBasePane:: CanBeClosed](#canbeclosed), [CBasePane:: canotomatik Gizle](#canautohide), [CBasePane:: CanFloat](#canfloat). Davranışlarını özelleştirmek için türetilmiş sınıflarda bunları geçersiz kılabilirsiniz.

- [CBasePane:: CanAcceptPane](#canacceptpane)öğesini geçersiz kılarak yerleştirme davranışını özelleştirebilirsiniz. Bölmenizi, başka bir bölmenin kendisine sabitlemesini engellemek için bu yöntemden FALSE döndürmenizi sağlar.

- Bir statik bölme oluşturmak isterseniz ve bundan önce başka bir bölmenin daha önce yer almasını önler (OutlookDemo örneğinde Outlook çubuğuna benzer), bunu kayan olmayan olarak oluşturun ve [CBasePane 'ı geçersiz kılın::D Oesallowdynınsertreturn](#doesallowdyninsertbefore) Yanlýþ. AFX_CBRS_FLOAT stili olmadan bölme oluşturulduysa varsayılan uygulama FALSE döndürür.

- Kimliği 1 ' den farklı olan tüm bölmeleri oluştur.

- Bölme görünürlüğünü öğrenmek için [CBasePane:: IsVisible](#isvisible)kullanın. Sekmeli ve otomatik gizleme modlarında görünürlük durumunu doğru şekilde işler.

- Kayan olmayan bir yeniden boyutlandırılabilir bölme oluşturmak istiyorsanız, AFX_CBRS_FLOAT stili olmadan oluşturun ve [CFrameWnd::D ockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar)' ı çağırın.

- Bir bölmeyi yerleştirme düzeninden dışlamak veya bir araç çubuğunu yerleştirme çubuğundan kaldırmak için, [CBasePane:: UndockPane](#undockpane)' ı çağırın. Bu yöntemi otomatik gizleme modundaki bölmeler veya sekmeli pencerelerin sekmelerinde bulunan bölmeler için çağırmayın.

- Otomatik gizleme modunda olan bir bölmeyi kaydırmak ya da çıkarmak istiyorsanız, [CBasePane:: FloatPane](#floatpane) veya [CBasePane:: UndockPane](#undockpane)' ı çağırmadan önce Ilk bağımsız değişken olarak [CDockablePane:: SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode) değerini çağırmanız gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CBasePane` sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir. Örnekte, `CFrameWndEx` sınıftan bir bölmenin nasıl alınacağını ve yerleştirme modunun, bölme hizalamasının ve bölme stilinin nasıl ayarlanacağı gösterilmektedir. Kod, [sözcük paneli](../../overview/visual-cpp-samples.md)örneğinden yapılır.

[!code-cpp[NVC_MFC_WordPad#2](../../mfc/reference/codesnippet/cpp/cbasepane-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxbasepane. h

##  <a name="accnotifyobjectfocusevent"></a>CBasePane:: AccNotifyObjectFocusEvent

`CBasePane`Bu yöntemi kullanmaz.

```
virtual void AccNotifyObjectFocusEvent(int);
```

### <a name="parameters"></a>Parametreler

*int*<br/>
'ndaki Kullanılmıyor.

##  <a name="addpane"></a>CBasePane:: AddPane

Yerleştirme yöneticisine bir bölme ekler.

```
void AddPane(CBasePane* pBar);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
'ndaki Eklenecek bölmeye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu, bir yerleştirme yöneticisine bölme ekleyen kullanışlı bir yöntemdir. Bu yöntemi kullanarak, üst çerçevenin türünü analiz eden bir kod yazmanız gerekmez.

Daha fazla bilgi için bkz. [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) ve [CMDIFrameWndEx:: AddPane](../../mfc/reference/cmdiframewndex-class.md#addpane).

##  <a name="adjustdockinglayout"></a>CBasePane:: AdjustDockingLayout

Yerleştirme yerleşimini ayarlamak için yerleştirme Yöneticisi 'ne yapılan çağrıyı yeniden yönlendirir.

```
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```

### <a name="parameters"></a>Parametreler

*hdwp*<br/>
dışı Birden çok pencere konumu içeren bir yapıya yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu, yerleştirme düzeninin ayarlayan kullanışlı bir yöntemdir. Bu yöntemi kullanarak, üst çerçevenin türünü analiz eden bir kod yazmanız gerekmez.

Daha fazla bilgi için bkz [. CDockingManager:: AdjustDockingLayout](../../mfc/reference/cdockingmanager-class.md#adjustdockinglayout)

##  <a name="adjustlayout"></a>CBasePane:: AdjustLayout

Bir bölmenin iç yerleşimini ayarlamak için Framework tarafından çağırılır.

```
virtual void AdjustLayout();
```

### <a name="remarks"></a>Açıklamalar

Bir bölmenin iç yerleşimini ayarlaması gerektiğinde, çerçeve bu yöntemi çağırır. Temel uygulama hiçbir şey yapmaz.

##  <a name="calcfixedlayout"></a>CBasePane:: CalcFixedLayout

Bir denetim çubuğunun yatay boyutunu hesaplar.

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

*Besnetme*<br/>
'ndaki Çubuğun çerçevenin boyutuna esnetilip uzatılmayacağını gösterir. Çubuk bir yerleştirme çubuğu olmadığında (yerleştirme için kullanılamaz) ve yerleştirildiğinde veya kayan olduğunda (yerleştirme için kullanılabilir) 0 olduğunda *Besnetme* parametresi sıfır dışı olur.

*bHorz*<br/>
'ndaki Çubuğun yatay veya dikey olarak yönlendirildiğini gösterir. Çubuk yatay olarak yönlendirilse *bHorz* parametresi sıfır değildir ve dikey olarak yönlendirilse 0 ' dır.

### <a name="return-value"></a>Dönüş Değeri

Bir `CSize` nesnenin piksel cinsinden denetim çubuğu boyutu.

### <a name="remarks"></a>Açıklamalar

[CControlBar:: CalcFixedLayout](../../mfc/reference/ccontrolbar-class.md#calcfixedlayout) içindeki açıklamalar bölümüne bakın

##  <a name="canacceptpane"></a>CBasePane:: CanAcceptPane

Başka bir bölmenin bölmesine yerleştirilip yerleştirilmeyeceğini belirler.

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
'ndaki Dock bölmesine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başka bir bölme kabul edilebilmesi için doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Framework, *pBar* tarafından belirtilen bölmeyi geçerli bölmeye göre ayarlamadan önce bu yöntemi çağırır.

Bölmelerin uygulamanızdaki diğer bölmelere nasıl yerleştirildiğini denetlemek için bu yöntemi ve [CBasePane:: Canbesabitlenmiş](#canbedocked) yöntemini kullanın.

Varsayılan uygulama yanlış döndürür.

##  <a name="canautohide"></a>CBasePane:: Canotomatik gizle

Bölmenin otomatik gizleme modunu destekleyip desteklemediğini belirler.

```
virtual BOOL CanAutoHide() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu bölme otomatik gizleme modunu destekliyorsa, doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Framework, bölmenin otomatik gizleme modunu destekleyip desteklemediğini öğrenmek için bu işlevi çağırır.

Oluşturma sırasında, AFX_CBRS_AUTOHIDE bayrağını [CBasePane:: CreateEx](#createex)öğesine geçirerek bu özelliği ayarlayabilirsiniz.

Varsayılan uygulama AFX_CBRS_AUTOHIDE bayrağını denetler. Bu davranışı özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

##  <a name="canbeattached"></a>CBasePane:: Canbeekli

Bölmenin başka bir bölmeye veya çerçeve penceresine sabitlenebilir olup olmayacağını belirler.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme başka bir bölmeye veya çerçeve penceresine sabitlenebilir ise doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama yanlış döndürür. [CBasePane:: enabledock](#enabledocking)çağrılmadan yerleştirme yeteneğini etkinleştirmek veya devre dışı bırakmak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

##  <a name="canbeclosed"></a>CBasePane:: CanBeClosed

Bölmenin kapatılıp kapatılamayacağını belirler.

```
virtual BOOL CanBeClosed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme kapatılabiliyorsa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Framework, bölmenin kapatılıp kapatılamayacağını anlamak için bu yöntemi çağırır. Yöntem TRUE değerini döndürürse, bölmenin başlık çubuğuna bir **kapatma** düğmesi eklenir ya da bölme ise bölmenin miniframe penceresinin başlık çubuğuna eklenir.

Oluşturma sırasında, AFX_CBRS_CLOSE bayrağını [CBasePane:: CreateEx](#createex)öğesine geçirerek bu özelliği ayarlayabilirsiniz.

Varsayılan uygulama AFX_CBRS_CLOSE bayrağını denetler.

##  <a name="canbedocked"></a>CBasePane:: Canbeyerleştirildi

Bölmenin başka bir bölmeye sabitlenebilir olup olmayacağını belirler.

```
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;
```

### <a name="parameters"></a>Parametreler

*pDockBar*<br/>
'ndaki Başka bir bölmeye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bu bölme başka bir bölmeye sabitlenebilir ise doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Framework, *pDockBar* tarafından belirtilen bölmeyi geçerli bölmeye almadan önce bu yöntemi çağırır.

Bölmelerin uygulamanızdaki diğer bölmelere nasıl ekleneceğini denetlemek için bu yöntemi ve [CBasePane:: CanAcceptPane](#canacceptpane) yöntemini kullanın.

Varsayılan uygulama yanlış döndürür.

##  <a name="canberesized"></a>CBasePane:: Canbereslanmış

Bölmenin yeniden boyutlandırılıp boyutlandırılmayacağını belirler.

```
virtual BOOL CanBeResized() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme yeniden boyutlandırılabiliyorsa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, içinde `CBasePane::OnCreate`varsayılan olarak belirtilen AFX_CBRS_RESIZE bayrağını denetler. Bu bayrak belirtilmemişse, yerleştirme Yöneticisi bölmeyi sabitleme yerine, dahili olarak bir taşınabilir olarak işaretler.

##  <a name="canbetabbeddocument"></a>CBasePane:: CanBeTabbedDocument

Bölmenin bir MDI sekmeli belgesine dönüştürülüp dönüştürülmeyeceğini belirtir.

```
virtual BOOL CanBeTabbedDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme sekmeli belgeye dönüştürülebiliyorsa TRUE; Aksi takdirde, FALSE. `CBasePane::CanBeTabbedDocument`her zaman FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Yalnızca, `CBasePane` [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md)gibi belirli türetilmiş türlerin nesneleri sekmeli belgelere dönüştürülebilir.

##  <a name="canfloat"></a>CBasePane:: CanFloat

Bölmenin kayıp kayamayacağını belirler.

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme kaybiliyorsa, doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Framework, bölmenin kayıp kayamayacağını öğrenmek için bu yöntemi çağırır.

Oluşturma sırasında, AFX_CBRS_FLOAT bayrağını [CBasePane:: CreateEx](#createex)öğesine geçirerek bu özelliği ayarlayabilirsiniz.

> [!NOTE]
>  Çerçeve, kayan olmayan bölmelerin statik olduğunu ve yerleştirme durumunun değiştiredüğünü varsayar. Bu nedenle, çerçeve, kayan olmayan bölmelerin yerleştirme durumunu kaydetmez.

Varsayılan uygulama AFX_CBRS_FLOAT stilini denetler.

##  <a name="canfocus"></a>CBasePane:: CanFocus

Bölmenin odak alıp alamayacağını belirtir.

```
virtual BOOL CanFocus() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme odak alabiliyorsa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Odağı denetlemek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın. Örneğin, araç çubukları odağı alamadığı için, bu yöntem araç çubuğu nesnelerinde çağrıldığında FALSE döndürür.

Çerçeve, bir bölme yerleştirildiğinde veya katdığında giriş odağını ayarlamaya çalışır.

##  <a name="copystate"></a>CBasePane:: CopyState

Verilen bölmenin durumunu kopyalar.

```
virtual void CopyState(CBasePane* pOrgBar);
```

### <a name="parameters"></a>Parametreler

*pOrgBar*<br/>
'ndaki Başka bir bölmeye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, durumu *pOrgBar* 'tan bu bölmeye kopyalar.

##  <a name="createdefaultminiframe"></a>CBasePane:: CreateDefaultMiniframe

Bölme kaydırma yapabilir, bu yöntem için bir mini çerçeve penceresi oluşturur.

```
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```

### <a name="parameters"></a>Parametreler

*Rectınitial*<br/>
'ndaki Mini çerçeve penceresinin ilk koordinatlarını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yeni mini çerçeve penceresine yönelik bir işaretçi veya oluşturma başarısız olduysa NULL.

### <a name="remarks"></a>Açıklamalar

Bir bölme bir kayan duruma geçtiğinde Framework bu yöntemi çağırır. Yöntemi bir mini çerçeve penceresi oluşturur ve bölmeyi bu pencereye ekler.

Varsayılan uygulama NULL değerini döndürür.

##  <a name="createex"></a>CBasePane:: CreateEx

Bölme denetimini oluşturur.

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    DWORD dwControlBarStyle=0,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>Parametreler

*dwStyleEx*<br/>
'ndaki Genişletilmiş stiller (daha fazla bilgi için bkz. [CWnd:: CreateEx](../../mfc/reference/cwnd-class.md#createex) ).

*lpszClassName*<br/>
'ndaki Pencere sınıfı adı.

*lpszWindowName*<br/>
'ndaki Pencere adı.

*dwStyle*<br/>
'ndaki Pencere stili (bkz. [CWnd:: CreateEx](../../mfc/reference/cwnd-class.md#createex)).

*Rect*<br/>
'ndaki İlk dikdörtgen.

*pParentWnd*<br/>
'ndaki Ana pencereye yönelik bir işaretçi.

*NID*<br/>
'ndaki Bölme KIMLIĞINI belirtir. Benzersiz olmalıdır.

*dwControlBarStyle*<br/>
'ndaki Panolar için stil bayrakları.

*pContext*<br/>
'ndaki Bir işaretçisi`CcreateContext`

### <a name="return-value"></a>Dönüş Değeri

Bölme başarıyla oluşturulursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Sınıfının `lpszClassName`bir penceresini oluşturur. WS_CAPTION belirtirseniz, bu yöntem WS_CAPTION stil bitini temizler ve kitaplık, açıklamalı alt `CBasePane::m_bHasCaption` yazıların bulunduğu bölmeleri desteklemediğinden true olarak ayarlanır.

Alt pencere stillerinin ve MFC denetim çubuğu (CBRS_) stillerinin herhangi bir birleşimini kullanabilirsiniz.

Kitaplık, bölmeler için birkaç yeni stil ekler. Aşağıdaki tabloda yeni stiller açıklanmaktadır:

|Stil|Açıklama|
|-----------|-----------------|
|AFX_CBRS_FLOAT|Bölme de taşınabilir.|
|AFX_CBRS_AUTOHIDE|Bölmesi otomatik gizleme modunu destekler|
|AFX_CBRS_RESIZE|Bölme yeniden boyutlandırılabilir. **Önemli:**  Bu stil uygulanmadı.|
|AFX_CBRS_CLOSE|Bölmesi kapatılabilir.|
|AFX_CBRS_AUTO_ROLLUP|Bölmesi, kayan olduğunda yukarı alınabilir.|
|AFX_CBRS_REGULAR_TABS|Bir bölme Bu stile sahip başka bir bölmeye ayarlandığında, normal sekmeli pencere oluşturulur. (Daha fazla bilgi için bkz. [CTabbedPane sınıfı](../../mfc/reference/ctabbedpane-class.md).)|
|AFX_CBRS_OUTLOOK_TABS|Bir bölme Bu stile sahip başka bir bölmeye ayarlandığında, bir Outlook stili sekmeli pencere oluşturulur. (Daha fazla bilgi için bkz. [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).)|

Yeni stilleri kullanmak için, bunları *dwControlBarStyle*içinde belirtin.

##  <a name="dockpane"></a>CBasePane::D ockPane

Bir bölmeyi başka bir bölmeye veya bir çerçeve penceresine göre oluşturma.

```
virtual BOOL DockPane(
    CBasePane* pDockBar,
    LPCRECT lpRect,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Parametreler

*pDockBar*<br/>
'ndaki Başka bir bölmeye yönelik bir işaretçi.

*lpRect*<br/>
'ndaki Hedef dikdörtgeni belirtir.

*Dockyöntemi*<br/>
'ndaki Yerleştirme yöntemini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğu başarıyla yerleştirilmişse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bir bölmeyi, *pDockBar*tarafından belirtilen başka bir bölmeye veya takma çubuğuna ( [CDockSite sınıfı](../../mfc/reference/cdocksite-class.md)) veya *pDockBar* null ise ana çerçeveye yerleştirmek için bu işlevi çağırın.

*dockMethod* , bölmenin nasıl yerleştirildiğini belirtir. Olası değerler listesi için bkz. [CPane::D ockPane](../../mfc/reference/cpane-class.md#dockpane) .

##  <a name="dockpaneusingrtti"></a>CBasePane::D Ockbölmesi Usingrttı

Çalışma zamanı tür bilgilerini kullanarak bölmeyi noktaları.

```
void DockPaneUsingRTTI(BOOL bUseDockSite);
```

### <a name="parameters"></a>Parametreler

*bUseDockSite*<br/>
'ndaki DOĞRU ise, yerleştirme sitesine yerleştir. YANLıŞSA, üst çerçeveye yerleştir.

##  <a name="docktoframewindow"></a>CBasePane: ockToFrameWindow:D

Bir çerçeveye yerleştirilebilir bölmesi noktası oluşturma.

```
virtual BOOL DockToFrameWindow(
    DWORD dwAlignment,
    LPCRECT lpRect = NULL,
    DWORD dwDockFlags = DT_DOCK_LAST,
    CBasePane* pRelativeBar = NULL,
    int nRelativeIndex = -1,
    BOOL bOuterEdge = FALSE);
```

### <a name="parameters"></a>Parametreler

*Dwhizalaması*<br/>
'ndaki Bölmeyi yerleştirmek istediğiniz üst çerçevenin tarafı.

*lpRect*<br/>
'ndaki İstenen boyut.

*dwDockFlags*<br/>
'ndaki LIP.

*pRelativeBar*<br/>
'ndaki LIP.

*Nrelativeındex*<br/>
'ndaki LIP.

*Bukenar*<br/>
'ndaki Doğru ise ve *dwhizalaması*tarafından belirtilen tarafta diğer yerleştirilebilir bölmeler varsa, bölmesi diğer bölmelerin dışına yerleştirilir ve üst çerçevenin kenarına yaklaştırır. YANLıŞSA, bölmesi istemci alanının merkezine daha yakın bir şekilde yerleştirilir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir bölme bölücü ( [CPaneDivider sınıfı](../../mfc/reference/cpanedivider-class.md)) oluşturulamazsa başarısız olur. Aksi halde, her zaman TRUE değerini döndürür.

##  <a name="doesallowdyninsertbefore"></a>CBasePane::D Oesallowdynınsertbefore

Bu bölme ve üst çerçeve arasında dinamik olarak bir bölme eklenip eklenemeyeceğini belirler.

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir Kullanıcı başka bir bölme ekleyebiliyorsa, doğru. Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Framework, bir kullanıcının bu bölmeden önce dinamik olarak bir bölme ekleyip ekleyemeyeceğini belirlemede bu yöntemi çağırır.

Örneğin, uygulamanızın çerçevenin sol tarafında (Outlook çubuğu gibi) yerleştirilmiş bir bölme oluşturduğunu varsayalım. Kullanıcının ilk bölmenin soluna bir başka bölme takmasını engellemek için bu yöntemi geçersiz kılın ve FALSE döndürün.

[CDockablePane sınıfından](../../mfc/reference/cdockablepane-class.md)türetilmiş kayan olmayan bölmeler için bu yöntemi geçersiz kılmanızı ve false döndürmenizi öneririz.

Varsayılan uygulama TRUE değerini döndürür.

##  <a name="dopaint"></a>CBasePane::D oPaint

Bölmenin arka planını doldurur.

```
virtual void DoPaint(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama arka planı ( [CMFCVisualManager:: OnFillBarBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfillbarbackground)) dolduracak şekilde geçerli Visual Manager 'ı çağırır.

##  <a name="enabledocking"></a>CBasePane:: EnableDocking

Bölmeyi ana çerçeveye yerleştirmeyi sağlar.

```
virtual void EnableDocking(DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

*Dwhizalaması*<br/>
'ndaki Etkinleştirilecek yerleştirme hizalamasını belirtir.

### <a name="remarks"></a>Açıklamalar

Ana çerçeveye yerleştirme hizalamasını etkinleştirmek için bu yöntemi çağırın. CBRS_ALIGN_ bayraklarının bir birleşimini geçirebilirsiniz (daha fazla bilgi için bkz. [CControlBar:: EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)).

`EnableDocking`iç bayrağı `CBasePane::m_dwEnabledAlignment` ayarlar ve bir bölme yerleştirildiğinde Framework bu bayrağı denetler.

Bir bölmenin yerleştirme hizalamasını öğrenmek için [CBasePane:: Getenabledhizalaması](#getenabledalignment) çağırın.

##  <a name="enablegripper"></a>CBasePane:: Enablekavrayıcı

Kavrayıcıyı etkinleştirilir veya devre dışı bırakır. Kavrayıcı etkinleştirilmişse, Kullanıcı bölmeyi yeniden konumlandırmak için onu sürükleyebilirsiniz.

```
virtual void EnableGripper(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Kavrayıcıyı etkinleştirmek için TRUE; Devre dışı bırakmak için FALSE.

### <a name="remarks"></a>Açıklamalar

Framework, WS_CAPTION stilini kullanmak yerine bir kavrayıcıyı etkinleştirmek için bu yöntemi kullanır.

##  <a name="floatpane"></a>CBasePane:: FloatPane

Bölmeyi kayın.

```
virtual BOOL FloatPane(
    CRect rectFloat,
    AFX_DOCK_METHOD dockMethod=DM_UNKNOWN,
    bool bShow=true);
```

### <a name="parameters"></a>Parametreler

*rectFloat*<br/>
'ndaki Kayan bölmenin göründüğü ekran koordinatlarını belirtir.

*Dockyöntemi*<br/>
'ndaki Bölmeyi kaydırmak için kullanılacak yuva yöntemini belirtir.

*bShow*<br/>
'ndaki Kayan bölmenin görünür (TRUE) veya gizli (yanlış) olduğunu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bölme başarıyla kaydırılır, doğru, Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

*RectFloat*tarafından belirtilen ekran konumundaki bir bölmeyi kaydırmak için bu yöntemi çağırın.

##  <a name="get_acchelptopic"></a>CBasePane:: get_accHelpTopic

Framework, belirtilen nesneyle ilişkili **WinHelp** dosyasının tam yolunu ve bu dosyadaki ilgili konunun tanımlayıcısını almak için bu yöntemi çağırır.

```
virtual HRESULT get_accHelpTopic(
    BSTR* pszHelpFile,
    VARIANT varChild,
    long* pidTopic);
```

### <a name="parameters"></a>Parametreler

*pszHelpFile*<br/>
'ndaki Varsa, belirtilen nesneyle ilişkili **WinHelp** dosyasının tam yolunu alan bir BSTR 'nin adresi.

*varChild*<br/>
'ndaki Alınacak Yardım konusunun nesnenin veya nesne alt öğelerinden birinin olup olmadığını belirtir. Bu parametre, CHILDID_SELF (nesne için yardım konusu almak için) veya bir alt KIMLIK (nesnenin alt öğelerinden biri için yardım konusu almak amacıyla) olabilir.

*pidTopic*<br/>
'ndaki Belirtilen nesneyle ilişkili **Yardım** dosyası konusunu tanımlar.

### <a name="return-value"></a>Dönüş Değeri

`CBasePane`Bu yöntemi uygulamaz. Bu nedenle `CBasePane::get_accHelpTopic` , her zaman S_FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, MFC 'de Etkin Erişilebilirlik desteğinin bir parçasıdır. Nesneniz hakkında yardım bilgileri sağlamak için türetilmiş bir sınıftaki bu işlevi geçersiz kılın.

##  <a name="get_accselection"></a>CBasePane:: get_accSelection

Framework, bu nesnenin seçili alt öğelerini almak için bu yöntemi çağırır.

```
virtual HRESULT get_accSelection(VARIANT* pvarChildren);
```

### <a name="parameters"></a>Parametreler

*pvarChildren*<br/>
'ndaki Seçili alt öğeleri tanımlayan bilgileri alır.

### <a name="return-value"></a>Dönüş Değeri

`CBasePane`Bu yöntemi uygulamaz. *Pvarchildren* null ise, bu yöntem E_INVALIDARG döndürür. Aksi takdirde, bu yöntem DISP_E_MEMBERNOTFOUND döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, MFC 'de Etkin Erişilebilirlik desteğinin bir parçasıdır. Penceresiz ActiveX denetimleri dışında pencereli olmayan kullanıcı arabirimi öğeleriniz varsa, bu işlevi türetilmiş bir sınıfta geçersiz kılın.

##  <a name="getcaptionheight"></a>CBasePane:: GetCaptionHeight

Başlık yüksekliğini döndürür.

```
virtual int GetCaptionHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başlık yüksekliği.

##  <a name="getcontrolbarstyle"></a>CBasePane:: GetControlBarStyle

Denetim çubuğu stilini döndürür.

```
virtual DWORD GetControlBarStyle() const
```

### <a name="return-value"></a>Dönüş Değeri

AFX_CBRS_ bayraklarının bit düzeyinde veya birleşimi.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri, aşağıdaki olası değerlerin bir birleşimidir.

|Stil|Açıklama|
|-----------|-----------------|
|AFX_CBRS_FLOAT|Denetim çubuğunu yüzer hale getirir.|
|AFX_CBRS_AUTOHIDE|Otomatik gizleme modunu izin vermez.|
|AFX_CBRS_RESIZE|Denetim çubuğunun yeniden boyutlandırılmasına izin vermez. Bu bayrak ayarlandığında, denetim çubuğu bir yerleştirilebilir bölmesine yerleştirilebilir.|
|AFX_CBRS_CLOSE|Denetim çubuğunun gizlenmesine izin vermez.|

##  <a name="getcurrentalignment"></a>CBasePane:: GetCurrentAlignment

Geçerli bölme hizalamasını döndürür.

```
virtual DWORD GetCurrentAlignment() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğunun geçerli hizalaması. Aşağıdaki tabloda olası değerler gösterilmektedir:

|Değer|Hizalama|
|-----------|---------------|
|CBRS_ALIGN_LEFT|Sola hizalama.|
|CBRS_ALIGN_RIGHT|Sağa hizalama.|
|CBRS_ALIGN_TOP|Üst hizalama.|
|CBRS_ALIGN_BOTTOM|Alt hizalama.|

##  <a name="getdockingmode"></a>CBasePane:: GetDockingMode

Bölme için geçerli yerleştirme modunu döndürür.

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

DT_STANDARD bölmesi sürüklenirken, bir sürükleme dikdörtgeni tarafından ekranda gösterilir. Bölmenin içeriği sürüklenirse DT_IMMEDIATE.

### <a name="remarks"></a>Açıklamalar

Framework, bölmenin geçerli yerleştirme modunu belirlemede bu yöntemi çağırır.

Tanımsız (DT_UNDEFINED) ise, yerleştirme modu genel yerleştirme modundan (`AFX_GLOBAL_DATA::m_dockModeGlobal`) alınır. `CBasePane::m_dockMode`

*M_dockMode* veya geçersiz kılmayı `GetDockingMode` ayarlayarak, her bölme için yerleştirme modunu kontrol edebilirsiniz.

##  <a name="getdocksiteframewnd"></a>CBasePane:: GetDockSiteFrameWnd

Bölmenin yerleştirildiği [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)nesnesine bir işaretçi döndürür.

```
virtual CWnd* GetDockSiteFrameWnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölmenin Dock sitesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bölmenin Dock sitesine bir işaretçi almak için bu yöntemi çağırın. Dock sitesi, bölme ana çerçeveye yerleştirilmişse bir ana çerçeve penceresi ya da bölme yüzer ise bir mini çerçeve penceresi olabilir.

##  <a name="getenabledalignment"></a>CBasePane:: Getenabledhizalaması

Bölmeye uygulanan CBRS_ALIGN_ stillerini döndürür.

```
virtual DWORD GetEnabledAlignment() const;
```

### <a name="return-value"></a>Dönüş Değeri

CBRS_ALIGN_ stillerinin birleşimi. Aşağıdaki tabloda olası stiller gösterilmektedir:

|Bayrağı|Etkin hizalama|
|----------|-----------------------|
|CBRS_ALIGN_LEFT|Tarafta.|
|CBRS_ALIGN_RIGHT|Right.|
|CBRS_ALIGN_TOP|Sayfanın Üstü.|
|CBRS_ALIGN_BOTTOM|Aşağıya.|
|CBRS_ALIGN_ANY|Tüm bayrakların birleşimi.|

### <a name="remarks"></a>Açıklamalar

Bölmenin etkin hizalamasını öğrenmek için bu yöntemi çağırın. Etkin hizalama, bir bölmenin sabitlenebilir olduğu ana çerçeve penceresinin tarafları anlamına gelir.

[CBasePane:: Enabletakmayı](#enabledocking)kullanarak yerleştirme hizalamasını etkinleştirin.

##  <a name="getmfcstyle"></a>CBasePane:: GetMFCStyle

MFC 'ye özgü bölme stillerini döndürür.

```
virtual DWORD GetMFCStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kitaplığa özel (AFX_CBRS_) bölmesi stillerinin birleşimi.

##  <a name="getpaneicon"></a>CBasePane:: GetPaneIcon

Bölme simgesine bir tanıtıcı döndürür.

```
virtual HICON GetPaneIcon(BOOL bBigIcon);
```

### <a name="parameters"></a>Parametreler

*Barıgigıcon*<br/>
'ndaki TRUE ise 32 piksel simgesiyle 32 piksel olduğunu belirtir; YANLıŞSA 16 piksellik 16 piksellik simgeyi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bölme simgesine yönelik bir tanıtıcı. Başarısız olursa, NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama [CWnd:: GetIcon](../../mfc/reference/cwnd-class.md#geticon)öğesini çağırır.

##  <a name="getpanerow"></a>CBasePane:: GetPaneRow

Bölmenin yerleştirildiği [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)nesnesine bir işaretçi döndürür.

```
CDockingPanesRow* GetPaneRow();
```

### <a name="return-value"></a>Dönüş Değeri

Bölmenin yerleştirilmiş olması `CDockingPanesRow` veya yüzer olması halinde null olması için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir bölmenin yerleştirildiği satıra erişmek için bu yöntemi çağırın. Örneğin, belirli bir satırdaki bölmeleri düzenlemek için, `GetPaneRow` [CDockingPanesRow:: arrangebölmelerini](../../mfc/reference/cdockingpanesrow-class.md#arrangepanes)çağırın ve çağırın.

##  <a name="getpanestyle"></a>CBasePane:: Getbölmesi stili

Bölme stilini döndürür.

```
virtual DWORD GetPaneStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Oluşturma sırasında [CBasePane:: Setpane stil](#setpanestyle) yöntemi tarafından ayarlanan denetim çubuğu STILLERININ (cbrs_ stilleri dahil) birleşimi.

##  <a name="getparentdocksite"></a>CBasePane:: GetParentDockSite

Üst Dock sitesine bir işaretçi döndürür.

```
virtual CDockSite* GetParentDockSite() const;
```

### <a name="return-value"></a>Dönüş Değeri

Üst yerleştirme sitesi.

##  <a name="getparentminiframe"></a>CBasePane:: GetParentMiniFrame

Üst mini çerçeve penceresine bir işaretçi döndürür.

```
virtual CPaneFrameWnd* GetParentMiniFrame(BOOL bNoAssert=FALSE) const;
```

### <a name="parameters"></a>Parametreler

*Bnoonaylama*<br/>
'ndaki TRUE ise, bu yöntem geçerli olmayan işaretçileri denetlemez. Uygulamanız çıktığında bu yöntemi çağırırsanız, bu parametreyi TRUE olarak ayarlayın.

### <a name="return-value"></a>Dönüş Değeri

Bölme yüzer ise üst mini çerçeve penceresine geçerli bir işaretçi; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Üst mini çerçeve penceresine bir işaretçi almak için bu işlevi çağırın. Bu yöntem, [Cpgframewnd sınıfından](../../mfc/reference/cpaneframewnd-class.md)türetilmiş bir nesne için tüm üst öğeleri ve denetimleri yineler.

Bölmenin `GetParentMiniFrame` kayan olup olmadığını anlamak için kullanın.

##  <a name="getparenttabbedpane"></a>CBasePane:: GetParentTabbedPane

Üst sekmeli bölmeye bir işaretçi döndürür.

```
CBaseTabbedPane* GetParentTabbedPane() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsa üst sekmeli bölmeye yönelik bir işaretçi; Aksi takdirde NULL.

##  <a name="getparenttabwnd"></a>CBasePane:: GetParentTabWnd

Bir sekme içinde olan üst pencereye bir işaretçi döndürür.

```
CMFCBaseTabCtrl* GetParentTabWnd(HWND& hWndTab) const;
```

### <a name="parameters"></a>Parametreler

*hWndTab*<br/>
dışı Dönüş değeri NULL değilse, bu parametre üst sekmeli pencerenin tanıtıcısını içerir.

### <a name="return-value"></a>Dönüş Değeri

Üst sekmeli pencere veya NULL için geçerli bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üst sekmeli pencereye bir işaretçi almak için bu işlevi kullanın. Bazı durumlarda, bir bölme bir yerleştirme `GetParent`Sarmalayıcısı ( [CDockablePaneAdapter sınıfı](../../mfc/reference/cdockablepaneadapter-class.md)) içinde veya bir bölme bağdaştırıcısı ( [CDockablePaneAdapter sınıfı](../../mfc/reference/cdockablepaneadapter-class.md)) içinde olabileceği için çağrı yapmak yeterli değildir. Bunu kullanarak `GetParentTabWnd` , bu durumlarda geçerli bir işaretçi elde edebilirsiniz (üst öğenin sekmeli pencere olduğu varsayılırsa).

##  <a name="getrecentvisiblestate"></a>CBasePane:: GetRecentVisibleState

Bir bölme bir arşivden geri yüklendiğinde Framework bu yöntemi çağırır.

```
virtual BOOL GetRecentVisibleState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Son görünen durumu belirten bir BOOL. TRUE ise bölme serileştirildiğinde görünür ve geri yüklendiğinde görünür olması gerekir. FALSE ise bölme serileştirildiğinde gizlidir ve geri yüklendiğinde gizli olması gerekir.

##  <a name="hideinprintpreviewmode"></a>CBasePane:: Hideınprintönizleme modu

Bölmenin baskı önizlemede gizlenip gizlenmeyeceğini belirtir.

```
virtual BOOL HideInPrintPreviewMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme baskı önizlemede gösterilmiyorsa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Temel bölmeler baskı önizlemede gösterilmez. Bu nedenle, bu yöntem her zaman TRUE değerini döndürür.

##  <a name="insertpane"></a>CBasePane:: InsertPane

Belirtilen bölmeyi yerleştirme yöneticisiyle kaydeder.

```
BOOL InsertPane(
    CBasePane* pControlBar,
    CBasePane* pTarget,
    BOOL bAfter = TRUE);
```

### <a name="parameters"></a>Parametreler

*pControlBar*<br/>
'ndaki Eklenecek bölmeye yönelik bir işaretçi.

*pTarget*<br/>
'ndaki Bitişik bölmeye yönelik bir işaretçi.

*bAfter*<br/>
'ndaki TRUE ise *pControlBar* , *pTarget*öğesinden sonra eklenir. FALSE ise *pControlBar* , *pTarget*öğesinden önce eklenir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE, aksi takdirde FALSE.

##  <a name="isaccessibilitycompatible"></a>CBasePane:: IsAccessibilityCompatible

Bölmenin etkin erişilebilirliği destekleyip desteklemediğini belirtir.

```
virtual BOOL IsAccessibilityCompatible();
```

### <a name="return-value"></a>Dönüş Değeri

Bölme etkin erişilebilirliği destekliyorsa doğru; Aksi takdirde, FALSE.

##  <a name="isautohidemode"></a>CBasePane:: ısoto Hidemode

Bir bölmenin otomatik gizleme modunda olup olmadığını belirler.

```
virtual BOOL IsAutoHideMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme otomatik gizleme modundaysa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Temel bölmeler otomatik olarak gizlenemez. Bu yöntem her zaman FALSE döndürür.

##  <a name="isdialogcontrol"></a>CBasePane:: ısdialogcontrol

Bölmenin bir iletişim kutusu denetimi olup olmadığını belirtir.

```
BOOL IsDialogControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme bir iletişim kutusu denetimi ise doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Framework, tüm bölmelerde düzen tutarlılığı sağlamak için bu yöntemi kullanır.

##  <a name="isdocked"></a>CBasePane:: ıyerleştirildi

Bölmenin yerleştirilmiş olup olmadığını belirler.

```
virtual BOOL IsDocked() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölmenin üst öğesi bir mini çerçeve değilse veya bölme başka bir bölme ile bir mini çerçevede yüzer ise TRUE. Aksi takdirde, FALSE.

##  <a name="isfloating"></a>CBasePane:: ıskayan

Bölmenin kayan olup olmadığını belirler.

```
virtual BOOL IsFloating() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme yüzer ise doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CBasePane:: ısıse](#isdocked)değerinin karşıt değerini döndürür.

##  <a name="ishorizontal"></a>CBasePane:: ısyatay

Bölmenin yatay olarak yerleştirilmiş olup olmadığını belirler.

```
virtual BOOL IsHorizontal() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme yatay olarak yuvalanmışsa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, CBRS_ORIENT_HORZ için geçerli yerleştirme hizalamasını denetler.

##  <a name="isinfloatingmultipaneframewnd"></a>CBasePane:: ısinfloatingmultipane Framewnd

Bölmenin çok bölgeli bir çerçeve penceresinde ( [Cmultipane Framewnd sınıfı](../../mfc/reference/cmultipaneframewnd-class.md)) olup olmadığını belirtir.

```
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme çok bölgeli bir çerçeve penceresinde ise doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Yalnızca yerleştirilebilir bölmeler, çok bölgeli bir çerçeve penceresinde taşınabilir. Bu nedenle `CBasePane::IsInFloatingMultiPaneFrameWnd` , her zaman false döndürür.

##  <a name="ismditabbed"></a>CBasePane:: ısmdısekmeli

Bölmenin bir MDI alt penceresine sekmeli belge olarak eklenip eklenmeyeceğini belirler.

```
virtual BOOL IsMDITabbed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme bir MDI alt penceresine sekmeli belge olarak eklendiyse TRUE; Aksi takdirde, FALSE.

##  <a name="ispanevisible"></a>CBasePane:: IsPaneVisible

Bölme için WS_VISIBLE bayrağının ayarlanmış olup olmadığını belirtir.

```
BOOL IsPaneVisible() const;
```

### <a name="return-value"></a>Dönüş Değeri

WS_VISIBLE ayarlandıysa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bölüm görünürlüğünü tespit etmek için [CBasePane:: IsVisible](#isvisible) kullanın.

##  <a name="ispointneardocksite"></a>CBasePane:: ıspointyaklaştığında Docksite

Belirtilen noktanın Dock sitesine yakın olup olmadığını belirler.

```
BOOL IsPointNearDockSite(
    CPoint point,
    DWORD& dwBarAlignment,
    BOOL& bOuterEdge) const;
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
'ndaki Belirtilen nokta.

*Dwbarhizalaması*<br/>
dışı Noktanın yakınında olduğunu belirtir. Olası değerler şunlardır CBRS_ALIGN_LEFT, CBRS_ALIGN_RIGHT, CBRS_ALIGN_TOP ve CBRS_ALIGN_BOTTOM

*Bukenar*<br/>
dışı Nokta, dock sitesinin dış kenarlığına yaklaşmışsa TRUE; Aksi takdirde FALSE.

### <a name="return-value"></a>Dönüş Değeri

Nokta dock sitesinin yakınında ise doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Nokta, yerleştirme yöneticisinde ayarlanan duyarlılık dahilinde olduğunda yerleştirme sitesinin yakınında olur. Varsayılan duyarlılık 15 pikseldir.

##  <a name="isresizable"></a>CBasePane:: ısyeniden boyutlandırılabilir

Bölmenin yeniden boyutlandırılıp boyutlandırılmayacağını belirler.

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme Kullanıcı tarafından yeniden boyutlandırılabiliyorsa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

[CDockablePane sınıfının](../../mfc/reference/cdockablepane-class.md) bölmeleri yeniden boyutlandırılabilir.

Durum çubuğu ( [CMFCStatusBar sınıfı](../../mfc/reference/cmfcstatusbar-class.md)) ve yerleştirme çubuğu ( [CDockSite sınıfı](../../mfc/reference/cdocksite-class.md)) yeniden boyutlandırılamaz.

##  <a name="isrestoredfromregistry"></a>CBasePane:: ısrestoredfromregistry

Bölmenin kayıt defterinden geri yüklenip yüklenmediğini belirler.

```
virtual BOOL IsRestoredFromRegistry() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme kayıt defterinden geri yüklenirse doğru. Aksi takdirde, FALSE.

##  <a name="istabbed"></a>CBasePane:: ıssekmeli

Bölmenin sekmeli pencerenin Sekme denetimine eklenip eklenmeyeceğini belirler.

```
virtual BOOL IsTabbed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğu sekmeli pencerenin bir sekmesine eklenirse TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, hemen üst öğeye bir işaretçi alır ve üst öğenin çalışma zamanı sınıfının [CMFCBaseTabCtrl sınıfı](../../mfc/reference/cmfcbasetabctrl-class.md)olup olmadığını belirler.

##  <a name="isvisible"></a>CBasePane:: IsVisible

Bölmenin görünür olup olmadığını belirler.

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme görünür durumdaysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bir bölmenin görünürlüğünü öğrenmek için bu yöntemi kullanın. Kullanmayın `::IsWindowVisible`.

Bölme sekmeli değilse (bkz. [CBasePane:: ıssekmeli](#istabbed)), bu yöntem WS_VISIBLE stilini denetler. Bölmesi sekmeli ise, bu yöntem üst sekmeli pencerenin görünürlüğünü denetler. Üst pencere görünür durumdaysa, işlev [CMFCBaseTabCtrl:: IsTabVisible](../../mfc/reference/cmfcbasetabctrl-class.md#istabvisible)kullanarak bölme sekmesinin görünürlüğünü denetler.

##  <a name="loadstate"></a>CBasePane:: LoadState

Bölmenin durumunu kayıt defterinden yükler.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName=NULL,
    int nIndex=-1,
    UINT uiID=(UINT)-1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
'ndaki Profil adı.

*nDizin*<br/>
'ndaki Profil dizini.

*Uııd*<br/>
'ndaki Bölme KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Bölme durumu başarıyla yüklenmişse, doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Framework, kayıt defterinden bölme durumunu yüklemek için bu yöntemi çağırır. [CBasePane:: savtiği](#savestate)tarafından kaydedilen ek bilgileri yüklemek için türetilmiş bir sınıfta bunu geçersiz kılın.

##  <a name="movewindow"></a>CBasePane:: MoveWindow

Bölmeyi gider.

```
virtual HDWP MoveWindow(
    CRect& rect,
    BOOL bRepaint = TRUE,
    HDWP hdwp = NULL);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
'ndaki Bölmenin yeni konumunu ve boyutunu belirten bir dikdörtgen.

*bYeniden çizmeyi*<br/>
'ndaki TRUE ise bölme yeniden boyanır. YANLıŞSA, bölme yeniden boyanmaz.

*hdwp*<br/>
'ndaki Ertelenmiş pencere konumu yapısına yönelik tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Ertelenmiş pencere konumu yapısına yönelik bir tanıtıcı veya NULL.

### <a name="remarks"></a>Açıklamalar

NULL değerini *hdwp* parametresi olarak geçirirseniz, bu yöntem pencereyi normal şekilde taşır. Bir tanıtıcı geçirirseniz, bu yöntem ertelenmiş bir pencere taşır. [BeginDeferWindowPos](/windows/win32/api/winuser/nf-winuser-begindeferwindowpos) ' i çağırarak veya önceki çağrının dönüş değerini bu yönteme depolayarak bir tanıtıcı elde edebilirsiniz.

##  <a name="onafterchangeparent"></a>CBasePane:: OnAfterChangeParent

Bölmenin üst değişikliklerinden sonra Framework tarafından çağırılır.

```
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```

### <a name="parameters"></a>Parametreler

*pWndOldParent*<br/>
'ndaki Önceki üst öğeye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Çerçeve, genellikle bir takma veya kayan işlem nedeniyle bölmenin üst değişikliklerinden sonra bu yöntemi çağırır.

Varsayılan uygulama hiçbir şey yapmaz.

##  <a name="onbeforechangeparent"></a>CBasePane:: OnBeforeChangeParent

Bölme, ana penceresini değiştirmeden hemen önce çerçevesi tarafından çağırılır.

```
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,
    BOOL bDelay=FALSE);
```

### <a name="parameters"></a>Parametreler

*pWndNewParent*<br/>
'ndaki Yeni bir üst pencerenin işaretçisi.

*bDelay*<br/>
'ndaki Düzen ayarlamaları Gecikmeli olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Çerçeve, genellikle bir yerleştirme, kayan veya otomatik gizleme işlemi nedeniyle bölmenin üst değişikliklerinden hemen önce bu yöntemi çağırır.

Varsayılan uygulama hiçbir şey yapmaz.

##  <a name="ondrawcaption"></a>CBasePane:: OnDrawCaption

Resim yazısı çizildiğinde çerçeve bu yöntemi çağırır.

```
virtual void OnDrawCaption();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntemin `CBasePane` sınıf için bir işlevi yoktur.

##  <a name="onmovepanedivider"></a>CBasePane:: OnMovePaneDivider

Bu yöntem şu anda kullanılmıyor.

```
virtual void OnMovePaneDivider(CPaneDivider* /* unused */);
```

### <a name="parameters"></a>Parametreler

*kullanılmayan*<br/>
'ndaki Kullanılmıyor.

##  <a name="onpanecontextmenu"></a>CBasePane:: Onbölmesi ContextMenu

Bir bölme listesi olan bir menü oluşturduğunda Framework tarafından çağırılır.

```
virtual void OnPaneContextMenu(
    CWnd* pParentFrame,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pParentFrame*<br/>
'ndaki Üst çerçeveye yönelik bir işaretçi.

*seçeneğinin*<br/>
'ndaki Kısayol menüsünün konumunu belirtir.

### <a name="remarks"></a>Açıklamalar

`OnPaneContextMenu`geçerli çerçeve penceresine ait bölmeler listesini tutan yerleştirme yöneticisini çağırır. Bu yöntem, bölmelerin adlarını bir kısayol menüsüne ekler ve görüntüler. Menüdeki komutlar tek tek bölmeleri gösterir veya gizler.

Bu davranışı özelleştirmek için bu yöntemi geçersiz kılın.

##  <a name="onremovefromminiframe"></a>CBasePane:: OnRemoveFromMiniFrame

Bir bölme üst mini çerçeve penceresinden kaldırıldığında Framework tarafından çağırılır.

```
virtual void OnRemoveFromMiniFrame(CPaneFrameWnd* pMiniFrame);
```

### <a name="parameters"></a>Parametreler

*pMiniFrame*<br/>
'ndaki Bölmenin kaldırıldığı mini çerçeve penceresine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir bölme üst mini çerçeve penceresinden kaldırıldığında (örneğin, yerleştirme sonucu olarak) bu yöntemi çağırır.

Varsayılan uygulama hiçbir şey yapmaz.

##  <a name="onsetaccdata"></a>CBasePane:: OnSetAccData

`CBasePane`Bu yöntemi kullanmaz.

```
virtual BOOL OnSetAccData(long lVal);
```

### <a name="parameters"></a>Parametreler

*lVal*<br/>
'ndaki Kullanılmıyor.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="panefrompoint"></a>CBasePane::P aneFromPoint

Verilen noktayı içeren bölmeyi döndürür.

```
CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    bool bExactBar = false,
    CRuntimeClass* pRTCBarType = NULL) const;
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
'ndaki Denetlenecek işaretçiyi ekran koordinatları olarak belirtir.

*Duyarlılık*<br/>
'ndaki Arama alanını bu miktara göre artırın. Verilen nokta artan alana denk geliyorsa, bir bölme arama ölçütlerini karşılar.

*bExactBar*<br/>
'ndaki *Nduyarlılık* parametresini YOKSAYMAK için true; Aksi takdirde, FALSE.

*pRTCBarType*<br/>
'ndaki NULL değilse, yöntem yalnızca belirtilen türdeki bölmeleri arar.

### <a name="return-value"></a>Dönüş Değeri

`CBasePane`Belirtilen noktayı içeren türetilmiş nesne veya hiçbir bölme bulunmazsa null.

##  <a name="recalclayout"></a>CBasePane:: RecalcLayout

`CBasePane`Bu yöntemi kullanmaz.

```
virtual void RecalcLayout();
```

##  <a name="removepanefromdockmanager"></a>CBasePane:: RemovePaneFromDockManager

Bir bölmenin kaydını siler ve yerleştirme yöneticisindeki listeden kaldırır.

```
void RemovePaneFromDockManager(
    CBasePane* pBar,
    BOOL bDestroy = TRUE,
    BOOL bAdjustLayout = FALSE,
    BOOL bAutoHide = FALSE,
    CBasePane* pBarReplacement = NULL);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
'ndaki Kaldırılacak bölmeye yönelik bir işaretçi.

*bDestroy*<br/>
'ndaki TRUE ise kaldırılan bölme yok edilir.

*Roztlayout*<br/>
'ndaki DOĞRU ise, yerleştirme yerleşimini hemen ayarlayın.

*bAutoHide*<br/>
'ndaki DOĞRU ise, yerleştirme düzeni otomatik gizleme çubuklarının listesiyle ilgilidir. FALSE ise, yerleştirme düzeni normal bölmeler listesiyle ilgilidir.

*Pbardeğiştirme*<br/>
'ndaki Kaldırılan bölmenin yerini alan bölme işaretçisi.

##  <a name="savestate"></a>CBasePane:: Savemlak

Bölmenin durumunu kayıt defterine kaydeder.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName=NULL,
    int nIndex=-1,
    UINT uiID=(UINT)-1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
'ndaki Profil adı.

*nDizin*<br/>
'ndaki Profil dizini.

*Uııd*<br/>
'ndaki Bölme KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Durum başarıyla kaydedilmişse doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Framework, bölmenin durumunu kayıt defterine kaydettiğinde bu yöntemi çağırır. Ek `SaveState` bilgileri depolamak için türetilmiş bir sınıfta geçersiz kılın.

##  <a name="selectdefaultfont"></a>CBasePane:: SelectDefaultFont

Belirtilen cihaz bağlamı için varsayılan yazı tipini seçer.

```
CFont* SelectDefaultFont(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Bir cihaz bağlamı.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan [CFont sınıfı](../../mfc/reference/cfont-class.md) nesnesine yönelik bir işaretçi.

##  <a name="setcontrolbarstyle"></a>CBasePane:: SetControlBarStyle

Denetim çubuğu stilini ayarlar.

```
virtual void SetControlBarStyle(DWORD dwNewStyle);
```

### <a name="parameters"></a>Parametreler

*dwNewStyle*<br/>
'ndaki Aşağıdaki olası değerlerin bit düzeyinde veya birleşimi.

|Stil|Açıklama|
|-----------|-----------------|
|AFX_CBRS_FLOAT|Denetim çubuğunu yüzer hale getirir.|
|AFX_CBRS_AUTOHIDE|Otomatik gizleme modunu izin vermez.|
|AFX_CBRS_RESIZE|Denetim çubuğunun yeniden boyutlandırılmasına izin vermez. Bu bayrak ayarlandığında, denetim çubuğu bir yerleştirilebilir bölmesine yerleştirilebilir.|
|AFX_CBRS_CLOSE|Denetim çubuğunun gizlenmesine izin vermez.|

##  <a name="setdockingmode"></a>CBasePane:: SetDockingMode

Bölme için yerleştirme modunu ayarlar.

```
void SetDockingMode(AFX_DOCK_TYPE dockModeNew);
```

### <a name="parameters"></a>Parametreler

*dockModeNew*<br/>
'ndaki Bölme için yeni yerleştirme modunu belirtir.

### <a name="remarks"></a>Açıklamalar

Framework iki yerleştirme modunu destekler: Standart ve anında.

Standart yerleştirme modunda bölmeler ve mini çerçeve pencereleri, bir sürükleme dikdörtgeni kullanılarak taşınır. Anında yerleştirme modunda, denetim çubukları ve mini çerçeve pencereleri bağlamlarıyla hemen taşınır.

İlk olarak, yerleştirme modu [CDockingManager:: m_dockModeGlobal](../../mfc/reference/cdockingmanager-class.md#m_dockmodeglobal)tarafından genel olarak tanımlanmıştır. `SetDockingMode` Yöntemini kullanarak her bölme için yerleştirme modunu ayrı ayrı ayarlayabilirsiniz.

##  <a name="setpanealignment"></a>CBasePane:: Setbölmesi hizalaması

Bölmenin hizalamasını ayarlar.

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

*Dwhizalaması*<br/>
'ndaki Yeni hizalamayı belirtir.

### <a name="remarks"></a>Açıklamalar

Genellikle, bir bölme ana çerçevenin bir tarafından diğerine yerleştirildiğinde, çerçeve bu yöntemi çağırır.

Aşağıdaki tabloda *Dwhizalaması*için olası değerler gösterilmektedir:

|Değer|Hizalama|
|-----------|---------------|
|CBRS_ALIGN_LEFT|Sola hizalama.|
|CBRS_ALIGN_RIGHT|Sağa hizalama.|
|CBRS_ALIGN_TOP|Üst hizalama.|
|CBRS_ALIGN_BOTTOM|Alt hizalama.|

##  <a name="setpanestyle"></a>CBasePane:: Setbölmesi stili

Bölmenin stilini ayarlar.

```
virtual void SetPaneStyle(DWORD dwNewStyle);
```

### <a name="parameters"></a>Parametreler

*dwNewStyle*<br/>
'ndaki Ayarlanacak yeni stili belirtir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, afxres. h içinde tanımlanan CBRS_ stillerinden herhangi birini ayarlamak için kullanılabilir. Bölme stili ve bölme hizalaması birlikte depolandığından, yeni stili geçerli hizalamayla birleştirerek aşağıdaki gibi ayarlayın.

`pPane->SetPaneStyle (pPane->GetCurrentAlignment() | CBRS_TOOLTIPS);`

##  <a name="setwindowpos"></a>CBasePane:: SetWindowPos

Bölmenin boyutunu, konumunu ve Z düzenini değiştirir.

```
virtual HDWP SetWindowPos(
    const CWnd* pWndInsertAfter,
    int x,
    int y,
    int cx,
    int cy,
    UINT nFlags,
    HDWP hdwp = NULL);
```

### <a name="parameters"></a>Parametreler

*pWndInsertAfter*<br/>
'ndaki Z düzeninde bu `CWnd` nesneden önce gelen nesneyitanımlar.`CWnd` Daha fazla bilgi için bkz. [CWnd:: SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos).

*x*<br/>
'ndaki Pencerenin sol tarafının konumunu belirtir.

*Iz*<br/>
'ndaki Pencerenin üst öğesinin konumunu belirtir.

*yazmaç*<br/>
'ndaki Pencerenin genişliğini belirtir.

*lı*<br/>
'ndaki Pencerenin yüksekliğini belirtir.

*nFlags*<br/>
'ndaki Boyut ve konum seçeneklerini belirtir. Daha fazla bilgi için bkz. [CWnd:: SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos).

*hdwp*<br/>
'ndaki Bir veya daha fazla pencere için boyut ve konum bilgilerini içeren bir yapıya işleyin.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş ertelenmiş pencere konumu yapısına yönelik bir tanıtıcı veya NULL.

### <a name="remarks"></a>Açıklamalar

*PWndInsertAfter* null ise, bu yöntem [CWnd:: SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)öğesini çağırır. *PWndInsertAfter* null değilse, bu yöntem çağrılır `DeferWindowPos`.

##  <a name="showpane"></a>CBasePane:: ShowPane

Bölmeyi gösterir veya gizler.

```
virtual void ShowPane(
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>Parametreler

*bShow*<br/>
'ndaki Bir bölmenin gösterilip gösterilmeyeceğini (TRUE) veya gizleneceğini (FALSE) belirtir.

*bDelay*<br/>
'ndaki DOĞRU ise, yerleştirme düzeninin yeniden hesaplanması gecikilir.

*Bacetkinleştir*<br/>
'ndaki TRUE ise, bölmesi gösterildiğinde etkin olur.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir bölmeyi gösterir veya gizler. Bu yöntem bunun yerine bu `ShowWindow` yöntemi kullanın çünkü bu yöntem ilgili yerleşik yöneticilere, bölmedeki görünürlükdeki değişikliklerle ilgili bildirimde bulunur.

Bir bölmenin geçerli görünürlüğünü öğrenmek için [CBasePane:: IsVisible](#isvisible) kullanın.

##  <a name="stretchpane"></a>CBasePane:: ayarlayıcı bölmesi

Bir bölmeyi dikey veya yatay olarak uzatır.

```
virtual CSize StretchPane(
    int nLength,
    BOOL bVert);
```

### <a name="parameters"></a>Parametreler

*nLength*<br/>
'ndaki Bölmenin uzatılabileceği uzunluk.

*bVert*<br/>
'ndaki DOĞRU ise, bölmeyi dikey olarak uzatın. YANLıŞSA, bölmeyi yatay olarak uzatın.

### <a name="return-value"></a>Dönüş Değeri

Uzatılmış bölmenin boyutu.

##  <a name="undockpane"></a>CBasePane:: UndockPane

Bölmeyi yerleştirme sitesinden, varsayılan kaydırıcıdan veya şu anda yerleştirilmiş olan mini çerçeve penceresinden kaldırır.

```
virtual void UndockPane(BOOL bDelay=FALSE);
```

### <a name="parameters"></a>Parametreler

*bDelay*<br/>
DOĞRU ise, yerleştirme düzeni hemen yeniden hesaplanmaz.

### <a name="remarks"></a>Açıklamalar

Bölme durumunu değiştirmek veya bölmeyi yerleştirme düzeninden dışlamak için bu yöntemi çağırın.

Bu bölmeyi kullanmaya devam etmek istiyorsanız, bu yöntemi çağırmadan önce [CBasePane::D ockPane](#dockpane) veya [CBasePane:: FloatPane](#floatpane) ' ı çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CPane](../../mfc/reference/cbasepane-class.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)
