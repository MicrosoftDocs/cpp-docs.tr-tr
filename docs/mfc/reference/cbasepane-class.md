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
ms.openlocfilehash: e0d6b844ba4a5c373dd69c0435bbb9972db3b49b
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58774483"
---
# <a name="cbasepane-class"></a>CBasePane sınıfı

MFC içinde tüm bölmeler için temel sınıf.

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
|`CBasePane::accHitTest`|Ekrandaki verilen noktanın alt nesne ya da çocuk öğesini almak için framework tarafından çağırılır. (Geçersiz kılmaları [CWnd::accHitTest](../../mfc/reference/cwnd-class.md#acchittest).)|
|`CBasePane::accLocation`|Belirtilen nesnenin şu anki ekran konumunu almak için framework tarafından çağırılır. (Geçersiz kılmaları [CWnd::accLocation](../../mfc/reference/cwnd-class.md#acclocation).)|
|[CBasePane::AccNotifyObjectFocusEvent](#accnotifyobjectfocusevent)|`CBasePane` Bu yöntem kullanmaz.|
|`CBasePane::accSelect`|Belirtilen nesnenin klavye girintisini taşımak ya da seçimi değiştirmek için framework tarafından çağırılır. (Geçersiz kılmaları [CWnd::accSelect](../../mfc/reference/cwnd-class.md#accselect).)|
|[CBasePane::AddPane](#addpane)|Bir bölme yerleştirme yöneticiye ekler.|
|[CBasePane::AdjustDockingLayout](#adjustdockinglayout)|Yerleştirme düzeni ayarlamak için bir çağrı yerleştirme Manager'a yönlendirir.|
|[CBasePane::AdjustLayout](#adjustlayout)|İç yerleşimi bölmesi ayarlamalıdır framework tarafından çağırılır.|
|[CBasePane::CalcFixedLayout](#calcfixedlayout)|Denetim çubuğu yatay boyutunu hesaplar.|
|[CBasePane::CanAcceptPane](#canacceptpane)|Başka bir bölme bölmesine yerleştirilmiş olup olmadığını belirler.|
|[CBasePane::CanAutoHide](#canautohide)|Bölmesinde otomatik gizleme modu destekleyip desteklemediğini belirler.|
|[CBasePane::CanBeAttached](#canbeattached)|Başka bir bölüme bölmesinde yerleştirilmiş olup olmadığını belirler.|
|[CBasePane::CanBeClosed](#canbeclosed)|Bölmesinde kapalı olup olmadığını belirler.|
|[CBasePane::CanBeDocked](#canbedocked)|Başka bir bölüme bölmesinde yerleştirilmiş olup olmadığını belirler.|
|[CBasePane::CanBeResized](#canberesized)|Bölmesinde boyutlandırılabilir olup olmadığını belirler.|
|[CBasePane::CanBeTabbedDocument](#canbetabbeddocument)|MDI sekmeli belgeye bölmesinde dönüştürülüp dönüştürülemeyeceğini belirler.|
|[CBasePane::CanFloat](#canfloat)|Bölmesinde kaydırabilirsiniz olup olmadığını belirler.|
|[CBasePane::CanFocus](#canfocus)|Bölmesinde odak alıp alamayacağını belirtir.|
|[CBasePane::CopyState](#copystate)|Belirli bir bölme durumu kopyalar.|
|[CBasePane::CreateDefaultMiniframe](#createdefaultminiframe)|Bölmesinde kaydırabilirsiniz bir mini çerçeve penceresi oluşturur.|
|[CBasePane::CreateEx](#createex)|Bölmesi denetimi oluşturur.|
|[CBasePane::DockPane](#dockpane)|Bir bölme, başka bir bölme ya da bir çerçeve penceresi docks.|
|[CBasePane::DockPaneUsingRTTI](#dockpaneusingrtti)|Çalışma zamanı tür bilgisini kullanarak bölmesinde docks.|
|[CBasePane::DockToFrameWindow](#docktoframewindow)|Yerleştirilebilir bir bölme için bir çerçeve docks.|
|[CBasePane::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Başka bir bölmesinde dinamik olarak bu bölme ve üst çerçevenin arasında eklenip eklenemeyeceğini belirler.|
|[CBasePane::EnableDocking](#enabledocking)|Etkinleştirir bölmesinde ana çerçevenin takma.|
|[CBasePane::EnableGripper](#enablegripper)|Etkinleştirir veya kavrayıcı devre dışı bırakır. Tutma etkinleştirmişse kullanıcının bölmesinde yeniden konumlandırmak için sürükleyebilirsiniz.|
|`CBasePane::FillWindowRect`|Dahili olarak kullanılır.|
|[CBasePane::FloatPane](#floatpane)|Bölmesinde kayar.|
|`CBasePane::get_accChild`|Adresini almak için framework tarafından çağırılır bir `IDispatch` belirtilen çocuk için arabirim. (Geçersiz kılmaları [CWnd::get_accChild](../../mfc/reference/cwnd-class.md#get_accchild).)|
|`CBasePane::get_accChildCount`|Bu nesneye ait çocukların sayısını almak için framework tarafından çağırılır. (Geçersiz kılmaları [CWnd::get_accChildCount](../../mfc/reference/cwnd-class.md#get_accchildcount).)|
|`CBasePane::get_accDefaultAction`|Nesnenin varsayılan eylemini tanımlayan dizeyi almak için framework tarafından çağırılır. (Geçersiz kılmaları [CWnd::get_accDefaultAction](../../mfc/reference/cwnd-class.md#get_accdefaultaction).)|
|`CBasePane::get_accDescription`|Belirtilen nesnenin görsel görünümünü tanımlayan dizeyi almak için framework tarafından çağırılır. (Geçersiz kılmaları [CWnd::get_accDescription](../../mfc/reference/cwnd-class.md#get_accdescription).)|
|`CBasePane::get_accFocus`|Klavye girintisine sahip nesneyi almak için framework tarafından çağırılır. (Geçersiz kılmaları [CWnd::get_accFocus](../../mfc/reference/cwnd-class.md#get_accfocus).)|
|`CBasePane::get_accHelp`|Bir nesnenin Yardım özellik dizesini almak için framework tarafından çağırılır. (Geçersiz kılmaları [CWnd::get_accHelp](../../mfc/reference/cwnd-class.md#get_acchelp).)|
|[CBasePane::get_accHelpTopic](#get_acchelptopic)|Belirtilen nesne ile ilişkili WinHelp dosyasının tam yolunu ve bu dosyayı ilgili konuya tanımlayıcısını almak için framework tarafından çağırılır. (Geçersiz kılmaları [CWnd::get_accHelpTopic](../../mfc/reference/cwnd-class.md#get_acchelptopic).)|
|`CBasePane::get_accKeyboardShortcut`|Nesnesinin Belirtilen kısayol tuşunu almak için framework tarafından çağırılır. (Geçersiz kılmaları [CWnd::get_accKeyboardShortcut](../../mfc/reference/cwnd-class.md#get_acckeyboardshortcut).)|
|`CBasePane::get_accName`|Belirtilen nesnenin adını almak için framework tarafından çağırılır. (Geçersiz kılmaları [CWnd::get_accName](../../mfc/reference/cwnd-class.md#get_accname).)|
|`CBasePane::get_accParent`|Almak için framework tarafından çağırılır `IDispatch` üst nesnenin arabirimi. (Geçersiz kılmaları [CWnd::get_accParent](../../mfc/reference/cwnd-class.md#get_accparent).)|
|`CBasePane::get_accRole`|Belirtilen nesnenin rolünü açıklayan bilgileri almak için framework tarafından çağırılır. (Geçersiz kılmaları [CWnd::get_accRole](../../mfc/reference/cwnd-class.md#get_accrole).)|
|[CBasePane::get_accSelection](#get_accselection)|Bu nesnenin seçili çocuğunu almak için framework tarafından çağırılır. (Geçersiz kılmaları [CWnd::get_accSelection](../../mfc/reference/cwnd-class.md#get_accselection).)|
|`CBasePane::get_accState`|Belirtilen nesnenin geçerli durumunu almak için framework tarafından çağırılır. (Geçersiz kılmaları [CWnd::get_accState](../../mfc/reference/cwnd-class.md#get_accstate).)|
|`CBasePane::get_accValue`|Belirtilen nesnenin değerini almak için framework tarafından çağırılır. (Geçersiz kılmaları [CWnd::get_accValue](../../mfc/reference/cwnd-class.md#get_accvalue).)|
|[CBasePane::GetCaptionHeight](#getcaptionheight)|Açıklamalı alt yazı yüksekliğini döndürür.|
|[CBasePane::GetControlBarStyle](#getcontrolbarstyle)|Denetim çubuğu stili döndürür.|
|[CBasePane::GetCurrentAlignment](#getcurrentalignment)|Geçerli bölmesinde hizalamasını döndürür.|
|[CBasePane::GetDockingMode](#getdockingmode)|Bölme için geçerli yerleştirme modunu döndürür.|
|[CBasePane::GetDockSiteFrameWnd](#getdocksiteframewnd)|Bölmesinin dock site penceresine bir işaretçi döndürür.|
|[CBasePane::GetEnabledAlignment](#getenabledalignment)|Bölmesine uygulanan CBRS_ALIGN_ stilleri döndürür.|
|[CBasePane::GetMFCStyle](#getmfcstyle)|MFC için belirli bölmesinde stilleri döndürür.|
|[CBasePane::GetPaneIcon](#getpaneicon)|Bölmesi simge için bir tanıtıcı döndürür.|
|`CBasePane::GetPaneRect`|Dahili olarak kullanılır.|
|[CBasePane::GetPaneRow](#getpanerow)|Bir işaretçi döndürür [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)nesne bölmesinde burada yerleştirilmiştir.|
|[CBasePane::GetPaneStyle](#getpanestyle)|Bölmesinde stili döndürür.|
|[CBasePane::GetParentDockSite](#getparentdocksite)|Üst dock sitesine bir işaretçi döndürür.|
|[CBasePane::GetParentMiniFrame](#getparentminiframe)|Üst Mini çerçeve penceresine bir işaretçi döndürür.|
|[CBasePane::GetParentTabbedPane](#getparenttabbedpane)|Üst sekmeli bölme için bir işaretçi döndürür.|
|[CBasePane::GetParentTabWnd](#getparenttabwnd)|İçinde bir sekmesinde olan üst penceresine bir işaretçi döndürür.|
|[CBasePane::GetRecentVisibleState](#getrecentvisiblestate)|Bir bölme arşivden geri yüklendiğinde framework bu yöntemi çağırır.|
|[CBasePane::HideInPrintPreviewMode](#hideinprintpreviewmode)|Baskı önizlemede bölmenin gizli olup olmadığını belirtir.|
|[CBasePane::InsertPane](#insertpane)|Belirtilen bölmenin yerleştirme Yöneticisi ile kaydeder.|
|[CBasePane::IsAccessibilityCompatible](#isaccessibilitycompatible)|Bölme etkin erişilebilirlik destekleyip desteklemediğini belirtir.|
|[CBasePane::IsAutoHideMode](#isautohidemode)|Bir bölme otomatik gizleme modunda olup olmadığını belirler.|
|[CBasePane::IsDialogControl](#isdialogcontrol)|Bölmesinde bir iletişim kutusu denetimi olup olmadığını belirtir.|
|[CBasePane::IsDocked](#isdocked)|Bölmenin yerleştirilmiş olup olmadığını belirler.|
|[CBasePane::IsFloating](#isfloating)|Bölmesinde kayan olup olmadığını belirler.|
|[CBasePane::IsHorizontal](#ishorizontal)|Bölmeyi yatay olarak yerleştirilmiş olup olmadığını belirler.|
|[CBasePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Bölmesinde bir çok bölmesinde çerçeve penceresinde olup olmadığını belirtir.|
|[CBasePane::IsMDITabbed](#ismditabbed)|Bir MDI alt penceresine bir sekmeli belge olarak bölmesine eklenip eklenmediğini belirler.|
|[CBasePane::IsPaneVisible](#ispanevisible)|Bölmesi ws_vısıble bayrağı ayarlanmış olup olmadığını belirtir.|
|[CBasePane::IsPointNearDockSite](#ispointneardocksite)|Belirli bir noktaya dock sitesine olup olmadığını belirler.|
|[CBasePane::IsResizable](#isresizable)|Bölmesinde boyutlandırılabilir olup olmadığını belirler.|
|[CBasePane::IsRestoredFromRegistry](#isrestoredfromregistry)|Kayıt defterinden bölmesinde geri yüklenip yüklenmeyeceğini belirler.|
|[CBasePane::IsTabbed](#istabbed)|Sekme denetimi sekmeli pencere bölmesi eklenen olup olmadığını belirler.|
|`CBasePane::IsTooltipTopmost`|Dahili olarak kullanılır.|
|[CBasePane::IsVisible](#isvisible)|Bölmesi görünür olup olmadığını belirler.|
|[CBasePane::LoadState](#loadstate)|Kayıt defterinden bölmesinde durumunu yükler.|
|[CBasePane::MoveWindow](#movewindow)|Bölme taşır.|
|[CBasePane::OnAfterChangeParent](#onafterchangeparent)|Bölmedeki üst değiştiğinde framework tarafından çağırılır.|
|[CBasePane::OnBeforeChangeParent](#onbeforechangeparent)|Yalnızca üst pencereye bölmesinde değiştirmeden önce framework tarafından çağırılır.|
|[CBasePane::OnDrawCaption](#ondrawcaption)|Açıklamalı alt yazı çizildiğinde framework bu yöntemi çağırır.|
|[CBasePane::OnMovePaneDivider](#onmovepanedivider)|Bu yöntem şu anda kullanılmıyor.|
|[CBasePane::OnPaneContextMenu](#onpanecontextmenu)|Bölmeleri listesini içeren bir menü oluşturduğunda framework tarafından çağırılır.|
|[CBasePane::OnRemoveFromMiniFrame](#onremovefromminiframe)|Bir bölme kendi üst mini çerçeve penceresinde kaldırıldığında framework tarafından çağırılır.|
|[CBasePane::OnSetAccData](#onsetaccdata)|`CBasePane` Bu yöntem kullanmaz.|
|`CBasePane::OnUpdateCmdUI`|Dahili olarak kullanılır.|
|[CBasePane::PaneFromPoint](#panefrompoint)|Belirtilen noktasını içeren bölme döndürür.|
|`CBasePane::PreTranslateMessage`|Sınıfı tarafından kullanılan [CWinApp](../../mfc/reference/cwinapp-class.md) için dağıtılmadan önce pencere iletilerini çevrilecek [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows işlevleri. (Geçersiz kılmaları [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CBasePane::RecalcLayout](#recalclayout)|`CBasePane` Bu yöntem kullanmaz.|
|[CBasePane::RemovePaneFromDockManager](#removepanefromdockmanager)|Bir bölme kaydını siler ve yerleştirme manager listesinden kaldırır.|
|[CBasePane::SaveState](#savestate)|Bölmedeki durumu kayıt defterine kaydeder.|
|[CBasePane::SelectDefaultFont](#selectdefaultfont)|Belirli bir cihaz bağlamı için varsayılan yazı tipi seçer.|
|`CBasePane::Serialize`|Okur veya ya da bir arşivden bu nesneyi yazar. (Geçersiz kılmaları [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[CBasePane::SetControlBarStyle](#setcontrolbarstyle)|Denetim çubuğu stilini ayarlar.|
|[CBasePane::SetDockingMode](#setdockingmode)|Bölmenin yerleştirme modunu ayarlar.|
|`CBasePane::SetMDITabbed`|Dahili olarak kullanılır.|
|[CBasePane::SetPaneAlignment](#setpanealignment)|Bölmenin hizalamasını ayarlar.|
|`CBasePane::SetPaneRect`|Dahili olarak kullanılır.|
|[CBasePane::SetPaneStyle](#setpanestyle)|Bölmesinin stilini ayarlar.|
|`CBasePane::SetRestoredFromRegistry`|Dahili olarak kullanılır.|
|[CBasePane::SetWindowPos](#setwindowpos)|Boyut, konum ve bir bölmenin Z düzenini değiştirir.|
|[CBasePane::ShowPane](#showpane)|Bölmesini gösterir veya gizler.|
|[CBasePane::StretchPane](#stretchpane)|Bir bölme, yatay veya dikey olarak genişletir.|
|[CBasePane::UndockPane](#undockpane)|Dock sitesiyle, varsayılan kaydırıcı veya mini çerçevenin şu anda dayandığı bölmesinde kaldırır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CBasePane::DoPaint](#dopaint)|Bölmenin arka doldurur.|

## <a name="remarks"></a>Açıklamalar

MFC'de kullanılabilen genişletilmiş yerleştirme özelliklerini destekleyen bir bölmesinde sınıfı oluşturmak istiyorsanız, buradan türetilmelidir `CBasePane` veya [CPane sınıfı](../../mfc/reference/cpane-class.md).

## <a name="customization-tips"></a>Özelleştirme ipuçları

Aşağıdaki özelleştirme ipuçları ilgilidir `CBasePane Class` ve ondan devralınan herhangi sınıflar:

- Bir bölme oluşturduğunuzda, birkaç yeni stil uygulayabilirsiniz:

  - AFX_CBRS_FLOAT bölmesinde float yapar.

  - AFX_CBRS_AUTOHIDE otomatik gizleme modunu etkinleştirir.

  - AFX_CBRS_CLOSE (gizli) kapatılması bölmesinde sağlar.

  Bu bir bit düzeyinde OR işlemle birleştirebilirsiniz bayraklar.

`CBasePane` Bu bayraklar yansıtacak şekilde aşağıdaki sanal Boole yöntemlerini uygular: [CBasePane::CanBeClosed](#canbeclosed), [CBasePane::CanAutoHide](#canautohide), [CBasePane::CanFloat](#canfloat). Bunları kendi davranışını özelleştirmek için türetilmiş sınıflarda geçersiz kılabilirsiniz.

- Yerleştirme davranışını geçersiz kılarak özelleştirebileceğiniz [CBasePane::CanAcceptPane](#canacceptpane). Başka bir bölme için yerleştirme önlemek için bu yöntemden false değerini döndürür, bölmenizde vardır.

- Olamaz, float ve engelleyen herhangi bir bölme önce yerleştirme statik bir bölme (OutlookDemo örnek Outlook çubuğuna benzer) oluşturmak, değişken olmayan olarak oluşturun ve geçersiz kılmak istiyorsanız [CBasePane::DoesAllowDynInsertBefore](#doesallowdyninsertbefore) FALSE döndürmek için. Varsayılan uygulama, bölmesinde AFX_CBRS_FLOAT stili oluşturulduysa false değerini döndürür.

- Tüm bölmeler -1 dışındaki kimlikleri ile oluşturun.

- Görünürlük bölmesi belirlemek için [CBasePane::IsVisible](#isvisible). Doğru görünürlük durumu işleme düz ve otomatik gizleme modları.

- Bir değişken olmayan yeniden boyutlandırılabilir bölmesi oluşturmak istiyorsanız, AFX_CBRS_FLOAT stil ve çağrı oluşturun [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).

- Bir bölme yerleştirme düzeninden hariç tutmak için ya da bir araç çubuğu yerleştirme çubuğunu kaldırmak için çağrı [CBasePane::UndockPane](#undockpane). Sekmeli pencerelerin sekmelerde bulunan bölmeleri veya otomatik gizleme modunda bölmeleri için bu yöntemi çağırmayın.

- Kayan nokta, veya otomatik gizleme modundayken bir bölme çıkarmak istiyorsanız çağırmalısınız [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode) çağırmadan önce ilk bağımsız değişken olarak FALSE ile [CBasePane::FloatPane](#floatpane) veya [ CBasePane::UndockPane](#undockpane).

## <a name="example"></a>Örnek

Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CBasePane` sınıfı. Örnek bir bölmesinden almak nasıl gösterir `CFrameWndEx` sınıfı ve yerleştirme modu, bölmesinde hizalama ve bölmesinde stilini ayarlama. Kod dandır [Word paneli örnek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#2](../../mfc/reference/codesnippet/cpp/cbasepane-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxbasepane.h

##  <a name="accnotifyobjectfocusevent"></a>  CBasePane::AccNotifyObjectFocusEvent

`CBasePane` Bu yöntem kullanmaz.

```
virtual void AccNotifyObjectFocusEvent(int);
```

### <a name="parameters"></a>Parametreler

*int*<br/>
[in] Kullanılmıyor.

##  <a name="addpane"></a>  CBasePane::AddPane

Bir bölme yerleştirme yöneticiye ekler.

```
void AddPane(CBasePane* pBar);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[in] Bir bölme eklemek için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu bölme bir yerleştirme Manager'a ekleyen bir kolaylık yöntemdir. Bu yöntemi kullanarak, üst çerçeve türünü çözümler kod yazma gerekmez.

Daha fazla bilgi için [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) ve [CMDIFrameWndEx::AddPane](../../mfc/reference/cmdiframewndex-class.md#addpane).

##  <a name="adjustdockinglayout"></a>  CBasePane::AdjustDockingLayout

Yerleştirme düzeni ayarlamak için bir çağrı yerleştirme Manager'a yönlendirir.

```
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```

### <a name="parameters"></a>Parametreler

*hdwp*<br/>
[out] Birden çok pencere konumlarını içeren bir yapıya tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu takma düzenini ayarlayan bir kullanışlı bir yöntemdir. Bu yöntemi kullanarak, üst çerçeve türünü çözümler kod yazma gerekmez.

Daha fazla bilgi için [CDockingManager::AdjustDockingLayout](../../mfc/reference/cdockingmanager-class.md#adjustdockinglayout)

##  <a name="adjustlayout"></a>  CBasePane::AdjustLayout

Bir bölme iç düzenini ayarlamak için framework tarafından çağırılır.

```
virtual void AdjustLayout();
```

### <a name="remarks"></a>Açıklamalar

İç düzenini ayarlamak bir bölme varsa framework bu yöntemi çağırır. Temel uygulama hiçbir şey yapmaz.

##  <a name="calcfixedlayout"></a>  CBasePane::CalcFixedLayout

Denetim çubuğu yatay boyutunu hesaplar.

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

*bStretch*<br/>
[in] Çubuk çerçevenin boyutuna esnetilmiş olup olmadığını gösterir. *BStretch* parametre olduğunda sıfır olmayan çubuğu (yerleştirme için kullanılamaz) bir takma çubuğu ve yerleşik veya kayan olduğunda 0 (yerleştirme için kullanılabilir).

*bHorz*<br/>
[in] Çubuk yatay veya dikey yönlendirilmiş olduğunu gösterir. *BHorz* parametresi ise sıfır olmayan çubuğu yönlendirilmiş yatay ve dikey yönlendirilmiş ise 0'dır.

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğu boyutu piksel cinsinden bir `CSize` nesne.

### <a name="remarks"></a>Açıklamalar

Açıklamalar kısmına bakın [CControlBar::CalcFixedLayout](../../mfc/reference/ccontrolbar-class.md#calcfixedlayout)

##  <a name="canacceptpane"></a>  CBasePane::CanAcceptPane

Başka bir bölme bölmesine yerleştirilmiş olup olmadığını belirler.

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[in] Yerleştirme bölmesine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başka bir bölme kabul edilebilir TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Tarafından belirtilen bölmesinde docks önce framework bu yöntemi çağırır *pBar* geçerli bölmesine.

Bu yöntemi kullanın ve [CBasePane::CanBeDocked](#canbedocked) nasıl bölmeleri, uygulamanızdaki diğer bölmeler için yerleştirme denetlemek için yöntemi.

Varsayılan uygulama false değerini döndürür.

##  <a name="canautohide"></a>  CBasePane::CanAutoHide

Bölmesinde otomatik gizleme modu destekleyip desteklemediğini belirler.

```
virtual BOOL CanAutoHide() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu bölme otomatik gizleme modunu destekliyorsa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Framework bölmesinde otomatik gizleme modu destekleyip desteklemediğini belirlemek için bu işlevi çağırır.

Oluşturma sırasında AFX_CBRS_AUTOHIDE bayrak geçirerek bu özelliği ayarlayabilirsiniz [CBasePane::CreateEx](#createex).

Varsayılan uygulama AFX_CBRS_AUTOHIDE bayrağı denetler. Türetilen bir sınıfta bu davranışını özelleştirmek için bu yöntemi yok sayın.

##  <a name="canbeattached"></a>  CBasePane::CanBeAttached

Başka bir bölüm ya da çerçeve penceresi bölmesi yerleştirilmiş olup olmadığını belirler.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başka bir bölüm ya da çerçeve penceresi bölmesi yuvalanabilir TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama false değerini döndürür. Etkinleştirme veya devre dışı arama olmadan yerleştirme olanağı türetilen bir sınıfta bu yöntemin üzerine yazması [CBasePane::EnableDocking](#enabledocking).

##  <a name="canbeclosed"></a>  CBasePane::CanBeClosed

Bölmesinde kapalı olup olmadığını belirler.

```
virtual BOOL CanBeClosed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme kapatılabilir TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Framework bölmesinde kapalı olup olmadığını belirlemek için bu yöntemi çağırır. Yöntem TRUE döndürürse bir **Kapat** düğmesi bölmedeki başlık çubuğuna eklenen veya bölmedeki Mini çerçeve gizlenmek başlık çubuğuna bölmesinde kayan olmadığını.

Oluşturma sırasında AFX_CBRS_CLOSE bayrak geçirerek bu özelliği ayarlayabilirsiniz [CBasePane::CreateEx](#createex).

Varsayılan uygulama AFX_CBRS_CLOSE bayrağı denetler.

##  <a name="canbedocked"></a>  CBasePane::CanBeDocked

Başka bir bölüme bölmesinde yerleştirilmiş olup olmadığını belirler.

```
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;
```

### <a name="parameters"></a>Parametreler

*pDockBar*<br/>
[in] Başka bir bölme için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bu bölme, başka bir bölüme yuvalanabilir TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Tarafından belirtilen bölmesinde docks önce framework bu yöntemi çağırır *pDockBar* geçerli bölmesine.

Bu yöntemi kullanın ve [CBasePane::CanAcceptPane](#canacceptpane) nasıl bölmeleri, uygulamanızdaki diğer bölmeler için yerleştirme denetlemek için yöntemi.

Varsayılan uygulama false değerini döndürür.

##  <a name="canberesized"></a>  CBasePane::CanBeResized

Bölmesinde boyutlandırılabilir olup olmadığını belirler.

```
virtual BOOL CanBeResized() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölmesinde yeniden boyutlandırılabilir TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem varsayılan olarak belirtilen AFX_CBRS_RESIZE bayrağı denetler `CBasePane::OnCreate`. Bu bayrak belirtilmezse, yerleştirme manager yerleştirme yerine dahili olarak immovable bölmesinde işaretler.

##  <a name="canbetabbeddocument"></a>  CBasePane::CanBeTabbedDocument

MDI sekmeli belgeye bölmesinde dönüştürülüp dönüştürülemeyeceğini belirler.

```
virtual BOOL CanBeTabbedDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekmeli belgeye bölmesinde dönüştürülebilir ise TRUE; Aksi takdirde FALSE. `CBasePane::CanBeTabbedDocument` Her zaman false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Yalnızca belirli nesnelerin `CBasePane`-gibi türetilmiş türleri, [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md), sekmeli belgelere dönüştürülebilir.

##  <a name="canfloat"></a>  CBasePane::CanFloat

Bölmesinde kaydırabilirsiniz olup olmadığını belirler.

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölmesinde kaydırabilirsiniz TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Framework bölmesinde kaydırabilirsiniz olup olmadığını belirlemek için bu yöntemi çağırır.

Oluşturma sırasında AFX_CBRS_FLOAT bayrak geçirerek bu özelliği ayarlayabilirsiniz [CBasePane::CreateEx](#createex).

> [!NOTE]
>  Framework kayan bölmeleri statik olduğunu ve bunların yerleştirme durumunu değiştiremezsiniz varsayar. Bu nedenle, çerçeve bölmeleri değişken olmayan yerleştirme durumunu kaydetmez.

Varsayılan uygulama AFX_CBRS_FLOAT stili denetler.

##  <a name="canfocus"></a>  CBasePane::CanFocus

Bölmesinde odak alıp alamayacağını belirtir.

```
virtual BOOL CanFocus() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölmesinde odak alıp TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Türetilen bir sınıfta odak denetlemek için bu yöntemi yok sayın. Örneğin, araç çubukları odak alınamıyor çünkü araç nesneler üzerinde çağrıldığında bu yöntem false değerini döndürür.

Bir bölme yerleştirilebilir ya da kaydırıldı giriş odağı ayarlamak framework çalışır.

##  <a name="copystate"></a>  CBasePane::CopyState

Belirli bir bölme durumu kopyalar.

```
virtual void CopyState(CBasePane* pOrgBar);
```

### <a name="parameters"></a>Parametreler

*pOrgBar*<br/>
[in] Başka bir bölme için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem durumundan kopyalar *pOrgBar* bu bölme için.

##  <a name="createdefaultminiframe"></a>  CBasePane::CreateDefaultMiniframe

Bölmesinde kaydırabilirsiniz ise bu yöntem için bir mini çerçeve penceresi oluşturur.

```
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```

### <a name="parameters"></a>Parametreler

*rectInitial*<br/>
[in] Mini çerçeve penceresi ilk koordinatlarını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir mini çerçeve penceresi ya da oluşturma başarısız olursa NULL bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir bölme bir kayan duruma geçtiğinde framework bu yöntemi çağırır. Yöntem bir mini çerçeve penceresi oluşturur ve bu pencereye bölmesine ekler.

Varsayılan uygulama, NULL döndürür.

##  <a name="createex"></a>  CBasePane::CreateEx

Bölmesi denetimi oluşturur.

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
[in] Genişletilmiş stiller (bkz [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) daha fazla bilgi için).

*lpszClassName*<br/>
[in] Pencere sınıfı adı.

*lpszWindowName*<br/>
[in] Pencere adı.

*dwStyle*<br/>
[in] Styl okna (bkz [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)).

*Rect*<br/>
[in] İlk dikdörtgen.

*pParentWnd*<br/>
[in] Üst penceresine bir işaretçi.

*nID*<br/>
[in] Bölmesinde kimliğini belirtir. Benzersiz olması gerekir.

*dwControlBarStyle*<br/>
[in] Stil bölmeleri için işaretler.

*pContext*<br/>
[in] Bir işaretçi `CcreateContext`

### <a name="return-value"></a>Dönüş Değeri

Bölmesinde başarıyla oluşturulursa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Sınıfın bir pencere oluşturur `lpszClassName`. Ws_captıon belirtirseniz, bu yöntem bit ws_captıon stili temizler ve ayarlar `CBasePane::m_bHasCaption` true olarak kitaplığı açıklamalı bölmeleri desteklemediği için.

Alt pencere stilleri ve MFC denetim çubuğu stilleri (CBRS_) herhangi bir birleşimini kullanabilirsiniz.

Kitaplık bölmeleri için birkaç yeni stiller ekler. Aşağıdaki tablo, yeni stilleri açıklar:

|Stil|Açıklama|
|-----------|-----------------|
|AFX_CBRS_FLOAT|Bölmesinde kaydırabilirsiniz.|
|AFX_CBRS_AUTOHIDE|Otomatik gizleme modu bölmesinde destekler|
|AFX_CBRS_RESIZE|Bölmesinde yeniden boyutlandırılabilir. **Önemli:**  Bu stil uygulanmadı.|
|AFX_CBRS_CLOSE|Bölme kapatılabilir.|
|AFX_CBRS_AUTO_ROLLUP|Bunu gezinen olduğunda bölmesinde sağlık dökümü.|
|AFX_CBRS_REGULAR_TABS|Bir bölme bu stil sahip başka bir bölme noktalarını, normal bir sekmeli pencere oluşturulur. (Daha fazla bilgi için [CTabbedPane sınıfı](../../mfc/reference/ctabbedpane-class.md).)|
|AFX_CBRS_OUTLOOK_TABS|Bir bölme bu stil sahip başka bir bölüme noktaları, bir Outlook stili sekmeli pencere oluşturulur. (Daha fazla bilgi için [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).)|

Yeni stilleri kullanmak için bunları belirtin *dwControlBarStyle*.

##  <a name="dockpane"></a>  CBasePane::DockPane

Bir bölme, başka bir bölme ya da bir çerçeve penceresi docks.

```
virtual BOOL DockPane(
    CBasePane* pDockBar,
    LPCRECT lpRect,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Parametreler

*pDockBar*<br/>
[in] Başka bir bölme için bir işaretçi.

*lpRect*<br/>
[in] Hedef dikdörtgenin belirtir.

*dockMethod*<br/>
[in] Yerleştirme yöntemini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğu başarıyla yerleştirilmiş TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bir bölme başka bir bölme ya da bir dock çubuğuna sabitlemek için bu işlevi çağırın ( [CDockSite sınıfı](../../mfc/reference/cdocksite-class.md)) tarafından belirtilen *pDockBar*, ya da bir ana çerçeve varsa *pDockBar* null.

*dockMethod* bölmesinde nasıl yerleştirildiğini belirler. Bkz: [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) olası değerler listesi.

##  <a name="dockpaneusingrtti"></a>  CBasePane::DockPaneUsingRTTI

Çalışma zamanı tür bilgisini kullanarak bölmesinde docks.

```
void DockPaneUsingRTTI(BOOL bUseDockSite);
```

### <a name="parameters"></a>Parametreler

*bUseDockSite*<br/>
[in] TRUE ise yerleştirme siteye yerleştir. FALSE ise, ana kareye yerleştir.

##  <a name="docktoframewindow"></a>  CBasePane::DockToFrameWindow

Yerleştirilebilir bir bölme için bir çerçeve docks.

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

*dwAlignment*<br/>
[in] Bölmesine sabitlemek istediğiniz üst çerçevenin yanında.

*lpRect*<br/>
[in] İstenen boyutu.

*dwDockFlags*<br/>
[in] Yoksayıldı.

*pRelativeBar*<br/>
[in] Yoksayıldı.

*nRelativeIndex*<br/>
[in] Yoksayıldı.

*bOuterEdge*<br/>
[in] Diğer yerleştirilebilir bölmeler tarafından belirtilen tarafında doğru ve var olup olmadığını *dwAlignment*, diğer bölmeler dışında bölmesinde yerleştirildiğini üst çerçevenin kenarına daha yakın. FALSE ise bölmesinde yakın istemci alanını merkezine yerleştirilir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bölmesinde ayırıcı, bu yöntem başarısız ( [CPaneDivider sınıfı](../../mfc/reference/cpanedivider-class.md)) oluşturulamıyor. Aksi takdirde, her zaman TRUE döndürür.

##  <a name="doesallowdyninsertbefore"></a>  CBasePane::DoesAllowDynInsertBefore

Başka bir bölmesinde dinamik olarak bu bölme ve üst çerçevenin arasında eklenip eklenemeyeceğini belirler.

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir kullanıcı başka bir bölme eklemek için TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Framework, bir kullanıcı, önce bu bölme bir bölmesinde dinamik olarak giremeyeceğinizi belirlemek için bu yöntemi çağırır.

Örneğin, uygulamanız (örneğin, Outlook Çubuğu) çerçevenin sol tarafında yerleştirilmiş bir bölme oluşturduğunu varsayalım. Kullanıcının ilk bölmesinin solunda başka bir bölme sabitlenmesini engellemek için bu yöntemi yok sayın ve false değerini döndürür.

Bu yöntemi yok sayın ve türetilen kayan bölmeleri için yanlış dönüş öneririz [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md).

Varsayılan uygulama, TRUE döndürür.

##  <a name="dopaint"></a>  CBasePane::DoPaint

Bölmenin arka doldurur.

```
virtual void DoPaint(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama arkaplanını doldurmak için geçerli görsel yöneticisini çağırır ( [CMFCVisualManager::OnFillBarBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfillbarbackground)).

##  <a name="enabledocking"></a>  CBasePane::EnableDocking

Etkinleştirir bölmesinde ana çerçevenin takma.

```
virtual void EnableDocking(DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

*dwAlignment*<br/>
[in] Etkinleştirmek için yerleştirme hizalamayı belirtir.

### <a name="remarks"></a>Açıklamalar

Ana çerçevenin takma hizalamayı etkinleştirmek için bu yöntemi çağırın. CBRS_ALIGN_ bayrakların birleşimi geçirebilirsiniz (daha fazla bilgi için [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)).

`EnableDocking` İç bayrağını ayarlar `CBasePane::m_dwEnabledAlignment` ve bölme yerleştirildiğinde framework bu bayrağı denetler.

Çağrı [CBasePane::GetEnabledAlignment](#getenabledalignment) bölmesi için yerleştirme hizalama belirlemek için.

##  <a name="enablegripper"></a>  CBasePane::EnableGripper

Etkinleştirir veya kavrayıcı devre dışı bırakır. Tutma etkinleştirmişse kullanıcının bölmesinde yeniden konumlandırmak için sürükleyebilirsiniz.

```
virtual void EnableGripper(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
[in] Kavrayıcının etkinleştirmek için TRUE; Devre dışı bırakmak için FALSE.

### <a name="remarks"></a>Açıklamalar

Çerçeve ws_captıon stili kullanmak yerine kavrayıcının etkinleştirmek için bu yöntemi kullanır.

##  <a name="floatpane"></a>  CBasePane::FloatPane

Bölmesinde kayar.

```
virtual BOOL FloatPane(
    CRect rectFloat,
    AFX_DOCK_METHOD dockMethod=DM_UNKNOWN,
    bool bShow=true);
```

### <a name="parameters"></a>Parametreler

*rectFloat*<br/>
[in] Kayan bölmesinde görüntülendiği ekran koordinatları belirtir.

*dockMethod*<br/>
[in] Bölmesinde kaydırmak için kullanılacak dock yöntemini belirtir.

*bBilgi Göster*<br/>
[in] Kayan bölme görünür (TRUE) olup olmadığını belirtir ya da gizli (FALSE).

### <a name="return-value"></a>Dönüş Değeri

Bölmesinde başarıyla kaydırıldı TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bir bölme tarafından belirtilen ekran konumunda kaydırmak için bu yöntemi çağıran *rectFloat*.

##  <a name="get_acchelptopic"></a>  CBasePane::get_accHelpTopic

Framework tam yolunu almak için bu yöntemi çağırır **WinHelp** belirtilen nesneyi ve bu dosyayı ilgili konuya tanıtıcısı ile ilişkili olan dosya.

```
virtual HRESULT get_accHelpTopic(
    BSTR* pszHelpFile,
    VARIANT varChild,
    long* pidTopic);
```

### <a name="parameters"></a>Parametreler

*pszHelpFile*<br/>
[in] Tam yolunu alır bir BSTR adresini **WinHelp** varsa belirtilen nesnesiyle ilişkilendirilen dosya.

*varChild*<br/>
[in] Yardım konusu, alınacak nesne veya bir nesnenin alt öğeleri olup olmadığını belirtir. Bu parametre, CHILDID_SELF (nesne için bir Yardım konusu almak için) veya bir alt öğe kimliği (Yardım konusunun bir alt nesne öğeleri elde edilir) olabilir.

*pidTopic*<br/>
[in] Tanımlar **yardımcı** belirtilen nesne ile ilişkili dosya konu.

### <a name="return-value"></a>Dönüş Değeri

`CBasePane` Bu yöntem uygulamıyor. Bu nedenle, `CBasePane::get_accHelpTopic` her zaman S_FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev MFC Active Accessibility desteğinin bir parçasıdır. Bu işlev, nesne hakkında Yardım bilgilerini sağlamak üzere türetilen bir sınıfta geçersiz kılar.

##  <a name="get_accselection"></a>  CBasePane::get_accSelection

Framework, bu nesnenin seçili çocuğunu almak için bu yöntemi çağırır.

```
virtual HRESULT get_accSelection(VARIANT* pvarChildren);
```

### <a name="parameters"></a>Parametreler

*pvarChildren*<br/>
[in] Seçilen alt öğeleri tanımlayan bilgileri alır.

### <a name="return-value"></a>Dönüş Değeri

`CBasePane` Bu yöntem uygulamıyor. Varsa *pvarChildren* NULL ise bu yöntem E_INVALIDARG döndürür. Aksi takdirde, bu yöntem DISP_E_MEMBERNOTFOUND döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev MFC Active Accessibility desteğinin bir parçasıdır. ActiveX denetimlerinin penceresiz dışında pencereli olmayan kullanıcı arabirimi öğeleri varsa, bu işlev türetilen bir sınıfta geçersiz kılar.

##  <a name="getcaptionheight"></a>  CBasePane::GetCaptionHeight

Açıklamalı alt yazı yüksekliğini döndürür.

```
virtual int GetCaptionHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açıklamalı alt yazı yüksekliği.

##  <a name="getcontrolbarstyle"></a>  CBasePane::GetControlBarStyle

Denetim çubuğu stili döndürür.

```
virtual DWORD GetControlBarStyle() const
```

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde OR AFX_CBRS_ bayrakların birleşimi.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri aşağıdaki değerlerden bir birleşimidir.

|Stil|Açıklama|
|-----------|-----------------|
|AFX_CBRS_FLOAT|Denetim çubuğu float yapar.|
|AFX_CBRS_AUTOHIDE|Etkinleştirir otomatik modu gizleme.|
|AFX_CBRS_RESIZE|Etkinleştirir, yeniden boyutlandırma denetim çubuğu. Bu bayrak ayarlandığında, denetim çubuğunun yerleştirilebilir bir bölmede yerleştirilebilir.|
|AFX_CBRS_CLOSE|Denetim çubuğu gizlenmesi etkinleştirir.|

##  <a name="getcurrentalignment"></a>  CBasePane::GetCurrentAlignment

Geçerli bölmesinde hizalamasını döndürür.

```
virtual DWORD GetCurrentAlignment() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğu hizalaması. Olası değerler aşağıdaki tabloda gösterilmektedir:

|Değer|Hizalama|
|-----------|---------------|
|CBRS_ALIGN_LEFT|Sola hizalama.|
|CBRS_ALIGN_RIGHT|Sağa hizalama.|
|CBRS_ALIGN_TOP|Üst hizalaması.|
|CBRS_ALIGN_BOTTOM|Alt hizalaması.|

##  <a name="getdockingmode"></a>  CBasePane::GetDockingMode

Bölme için geçerli yerleştirme modunu döndürür.

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölmesine sürükleyerek, DT_STANDARD ekranda bir sürükleme dikdörtgenini tarafından belirtilir. Bölmenin içeriği sürüklediyseniz DT_IMMEDIATE.

### <a name="remarks"></a>Açıklamalar

Framework geçerli yerleştirme modu bölmesinin belirlemek için bu yöntemi çağırır.

Varsa `CBasePane::m_dockMode` olan yerleştirme modu genel yerleştirme modundan alınır (DT_UNDEFINED) tanımlı değil (`AFX_GLOBAL_DATA::m_dockModeGlobal`).

Ayarlayarak *m_dockMode* veya geçersiz kılma `GetDockingMode` her bölme için yerleştirme modu denetleyebilirsiniz.

##  <a name="getdocksiteframewnd"></a>  CBasePane::GetDockSiteFrameWnd

Bir işaretçi döndürür [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)nesne bölmesinde burada yerleştirilmiştir.

```
virtual CWnd* GetDockSiteFrameWnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölmesinin dock sitesiyle bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir işaretçi bölmesinin dock sitesine almak için bu yöntemi çağırın. Dock sitesiyle bölmesinde kayan bölmesinde ana kareye yerleştirilmişse bir ana çerçeve penceresinin veya mini çerçevenin olabilir.

##  <a name="getenabledalignment"></a>  CBasePane::GetEnabledAlignment

Bölmesine uygulanan CBRS_ALIGN_ stilleri döndürür.

```
virtual DWORD GetEnabledAlignment() const;
```

### <a name="return-value"></a>Dönüş Değeri

CBRS_ALIGN_ stilleri birleşimi. Aşağıdaki tablo olası stilleri gösterir:

|Bayrağı|Etkin hizalama|
|----------|-----------------------|
|CBRS_ALIGN_LEFT|Sol.|
|CBRS_ALIGN_RIGHT|Sağ.|
|CBRS_ALIGN_TOP|Sayfanın Üstü.|
|CBRS_ALIGN_BOTTOM|Alt.|
|CBRS_ALIGN_ANY|Tüm bayrakların birleşimi.|

### <a name="remarks"></a>Açıklamalar

Bölme etkin hizalamasını belirlemek için bu yöntemi çağırın. Etkin hizalama için bölme yuvalanabilir ana çerçeve penceresinin tarafının anlamına gelir.

Kullanarak yerleştirme hizalamayı etkinleştirmek [CBasePane::EnableDocking](#enabledocking).

##  <a name="getmfcstyle"></a>  CBasePane::GetMFCStyle

MFC için belirli bölmesinde stilleri döndürür.

```
virtual DWORD GetMFCStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kitaplık özgü (AFX_CBRS_) bölmesinde stilleri birleşimi.

##  <a name="getpaneicon"></a>  CBasePane::GetPaneIcon

Bölmesi simge için bir tanıtıcı döndürür.

```
virtual HICON GetPaneIcon(BOOL bBigIcon);
```

### <a name="parameters"></a>Parametreler

*bBigIcon*<br/>
[in] TRUE ise 32 piksel simgesi ile 32 piksel belirtir. bir 16 piksel 16 piksel simgesi FALSE ise belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bölmesi simge tanıtıcı. İşlem başarısız olursa, NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan Uygulama çağrıları [CWnd::GetIcon](../../mfc/reference/cwnd-class.md#geticon).

##  <a name="getpanerow"></a>  CBasePane::GetPaneRow

Bir işaretçi döndürür [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)nesne bölmesinde burada yerleştirilmiştir.

```
CDockingPanesRow* GetPaneRow();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `CDockingPanesRow` bölmesinde yerleşik veya bu değişken, NULL ise.

### <a name="remarks"></a>Açıklamalar

Bir bölme nereye yerleştirildiğini satır erişmek için bu yöntemi çağırın. Örneğin, belirli bir satırda bölmeleri düzenlemek için çağrı `GetPaneRow` ve sonra çağrı [CDockingPanesRow::ArrangePanes](../../mfc/reference/cdockingpanesrow-class.md#arrangepanes).

##  <a name="getpanestyle"></a>  CBasePane::GetPaneStyle

Bölmesinde stili döndürür.

```
virtual DWORD GetPaneStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir birleşimi tarafından ayarlanan (CBRS_ stilleri dahil) denetim çubuğu stilleri [CBasePane::SetPaneStyle](#setpanestyle) olacak şekilde oluşturulma zamanında yöntemi.

##  <a name="getparentdocksite"></a>  CBasePane::GetParentDockSite

Üst dock sitesine bir işaretçi döndürür.

```
virtual CDockSite* GetParentDockSite() const;
```

### <a name="return-value"></a>Dönüş Değeri

Üst dock sitesiyle.

##  <a name="getparentminiframe"></a>  CBasePane::GetParentMiniFrame

Üst Mini çerçeve penceresine bir işaretçi döndürür.

```
virtual CPaneFrameWnd* GetParentMiniFrame(BOOL bNoAssert=FALSE) const;
```

### <a name="parameters"></a>Parametreler

*bNoAssert*<br/>
[in] TRUE ise bu yöntem için geçerli olmayan işaretçileri denetlemez. Bu yöntem çağırırsanız, uygulamanız çıkış yaptığında bu parametresi TRUE olarak ayarlayın.

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir işaretçi bölmesinde kayan, üst Mini çerçeve penceresi için; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Üst Mini çerçeve işaretçisi almak için bu işlevi çağırın. Bu yöntem tüm üst öğeler yinelenir ve bir nesne için denetimleri türetilen [CPaneFrameWnd sınıfı](../../mfc/reference/cpaneframewnd-class.md).

Kullanım `GetParentMiniFrame` bölmesinde kayan olup olmadığını belirlemek için.

##  <a name="getparenttabbedpane"></a>  CBasePane::GetParentTabbedPane

Üst sekmeli bölme için bir işaretçi döndürür.

```
CBaseTabbedPane* GetParentTabbedPane() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsa üst sekmeli bölme için bir işaretçi; bulunmazsa null değerini DÖNDÜRÜR.

##  <a name="getparenttabwnd"></a>  CBasePane::GetParentTabWnd

İçinde bir sekmesinde olan üst penceresine bir işaretçi döndürür.

```
CMFCBaseTabCtrl* GetParentTabWnd(HWND& hWndTab) const;
```

### <a name="parameters"></a>Parametreler

*hWndTab*<br/>
[out] Bu parametre, dönüş değeri NULL değilse üst sekmeli pencere tanıtıcıyı içerir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir işaretçi üst sekmeli pencere veya NULL.

### <a name="remarks"></a>Açıklamalar

Üst sekmeli penceresine bir işaretçi almak için bu işlevi kullanın. Bazen onu çağırmak yeterli değil `GetParent`, çünkü bir bölme içinde yerleştirme sarmalayıcı olabilir ( [CDockablePaneAdapter sınıfı](../../mfc/reference/cdockablepaneadapter-class.md)) veya bir bölmesinde bağdaştırıcısı içinde ( [CDockablePaneAdapter sınıfı](../../mfc/reference/cdockablepaneadapter-class.md)). Kullanarak `GetParentTabWnd` geçerli bir işaretçi (üst sekmeli pencere olduğunu varsayarak) Bu durumlarda almak mümkün olacaktır.

##  <a name="getrecentvisiblestate"></a>  CBasePane::GetRecentVisibleState

Bir bölme arşivden geri yüklendiğinde framework bu yöntemi çağırır.

```
virtual BOOL GetRecentVisibleState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Son görünürlük durumunu belirten bir Boole. TRUE ise bölmesinde serileştirilmiş ve geri olduğunda görünür olması görünür. FALSE ise bölmesinde serileştirilmiş ve geri olduğunda gizlenmelidir gizli.

##  <a name="hideinprintpreviewmode"></a>  CBasePane::HideInPrintPreviewMode

Baskı önizlemede bölmenin gizli olup olmadığını belirtir.

```
virtual BOOL HideInPrintPreviewMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Baskı Önizleme bölmesinde gösterilmez TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Temel bölme baskı önizlemede gösterilmez. Bu nedenle, bu yöntem, her zaman TRUE döndürür.

##  <a name="insertpane"></a>  CBasePane::InsertPane

Belirtilen bölmenin yerleştirme Yöneticisi ile kaydeder.

```
BOOL InsertPane(
    CBasePane* pControlBar,
    CBasePane* pTarget,
    BOOL bAfter = TRUE);
```

### <a name="parameters"></a>Parametreler

*pControlBar*<br/>
[in] Bölmesine eklemek için bir işaretçi.

*pTarget*<br/>
[in] Bitişik bölmesi için bir işaretçi.

*bBu*<br/>
[in] TRUE ise *pControlBar* eklenen *pTarget*. FALSE ise *pControlBar* önce eklenen *pTarget*.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE, FALSE Aksi takdirde.

##  <a name="isaccessibilitycompatible"></a>  CBasePane::IsAccessibilityCompatible

Bölme etkin erişilebilirlik destekleyip desteklemediğini belirtir.

```
virtual BOOL IsAccessibilityCompatible();
```

### <a name="return-value"></a>Dönüş Değeri

Bölme etkin erişilebilirlik destekliyorsa TRUE; Aksi takdirde FALSE.

##  <a name="isautohidemode"></a>  CBasePane::IsAutoHideMode

Bir bölme otomatik gizleme modunda olup olmadığını belirler.

```
virtual BOOL IsAutoHideMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik gizleme modundayken bölmesinde TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Temel bölme otomatik gizleme kullanılamaz. Bu yöntem, her zaman false değerini döndürür.

##  <a name="isdialogcontrol"></a>  CBasePane::IsDialogControl

Bölmesinde bir iletişim kutusu denetimi olup olmadığını belirtir.

```
BOOL IsDialogControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir iletişim kutusu denetimi bölmesi ise TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Framework, tüm bölmeler için Düzen tutarlılık sağlamak için bu yöntemi kullanır.

##  <a name="isdocked"></a>  CBasePane::IsDocked

Bölmenin yerleştirilmiş olup olmadığını belirler.

```
virtual BOOL IsDocked() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölmenin üst bir mini çerçeve değilse veya başka bir bölme Mini çerçeve içinde bölmesinde kayan TRUE; Aksi takdirde FALSE.

##  <a name="isfloating"></a>  CBasePane::IsFloating

Bölmesinde kayan olup olmadığını belirler.

```
virtual BOOL IsFloating() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölmesinde kayan TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem karşı değerini döndürür [CBasePane::IsDocked](#isdocked).

##  <a name="ishorizontal"></a>  CBasePane::IsHorizontal

Bölmeyi yatay olarak yerleştirilmiş olup olmadığını belirler.

```
virtual BOOL IsHorizontal() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölmeyi yatay olarak yerleştirildiğini TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama CBRS_ORIENT_HORZ geçerli yerleştirme hizalamasını denetler.

##  <a name="isinfloatingmultipaneframewnd"></a>  CBasePane::IsInFloatingMultiPaneFrameWnd

Bölmesinde bir çok bölmesinde çerçeve penceresinde olup olmadığını belirtir ( [CMultiPaneFrameWnd sınıfı](../../mfc/reference/cmultipaneframewnd-class.md)).

```
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir çok bölmesinde çerçeve penceresinde bölmesi ise TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Yalnızca yerleştirilebilir bölmeleri çok bölmesinde çerçeve penceresinde kaydırabilirsiniz. Bu nedenle, `CBasePane::IsInFloatingMultiPaneFrameWnd` her zaman false değerini döndürür.

##  <a name="ismditabbed"></a>  CBasePane::IsMDITabbed

Bir MDI alt penceresine bir sekmeli belge olarak bölmesine eklenip eklenmediğini belirler.

```
virtual BOOL IsMDITabbed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir MDI alt penceresine bir sekmeli belge olarak eklenen bölmesinde TRUE; Aksi takdirde FALSE.

##  <a name="ispanevisible"></a>  CBasePane::IsPaneVisible

Bölmesi ws_vısıble bayrağı ayarlanmış olup olmadığını belirtir.

```
BOOL IsPaneVisible() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ws_vısıble ayarlanmışsa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Kullanım [CBasePane::IsVisible](#isvisible) bölmesinde görünürlüğü belirlemek için.

##  <a name="ispointneardocksite"></a>  CBasePane::IsPointNearDockSite

Belirli bir noktaya dock sitesine olup olmadığını belirler.

```
BOOL IsPointNearDockSite(
    CPoint point,
    DWORD& dwBarAlignment,
    BOOL& bOuterEdge) const;
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
[in] Belirtilen nokta.

*dwBarAlignment*<br/>
[out] Hangi uç noktaya yaklaştı belirtir. CBRS_ALIGN_LEFT, CBRS_ALIGN_RIGHT CBRS_ALIGN_TOP ve CBRS_ALIGN_BOTTOM olası değerler şunlardır:

*bOuterEdge*<br/>
[out] Dock sitesiyle dış kenarlığı noktası ise TRUE; FALSE Aksi takdirde.

### <a name="return-value"></a>Dönüş Değeri

Dock sitesiyle noktası ise TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Yerleştirme Manager'da ayarladığınız duyarlılık içinde olduğunda dock sitesine noktasıdır. Varsayılan duyarlılık 15 pikseldir.

##  <a name="isresizable"></a>  CBasePane::IsResizable

Bölmesinde boyutlandırılabilir olup olmadığını belirler.

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tarafından yeniden boyutlandırılabilir bölmesinde TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bölmeleri [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md) yeniden boyutlandırılabilir.

Durum çubuğu ( [CMFCStatusBar sınıfı](../../mfc/reference/cmfcstatusbar-class.md)) ve dock çubuğu ( [CDockSite sınıfı](../../mfc/reference/cdocksite-class.md)) yeniden boyutlandırılamaz.

##  <a name="isrestoredfromregistry"></a>  CBasePane::IsRestoredFromRegistry

Kayıt defterinden bölmesinde geri yüklenip yüklenmeyeceğini belirler.

```
virtual BOOL IsRestoredFromRegistry() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt defterinden bölmesinde geri TRUE; Aksi takdirde FALSE.

##  <a name="istabbed"></a>  CBasePane::IsTabbed

Sekme denetimi sekmeli pencere bölmesi eklenen olup olmadığını belirler.

```
virtual BOOL IsTabbed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğunu sekmeli pencere bir sekmede eklenirse TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem ilk üst öğe için bir işaretçi alır ve ebeveynin çalışma zamanı sınıf olup olmadığını belirler [CMFCBaseTabCtrl sınıfı](../../mfc/reference/cmfcbasetabctrl-class.md).

##  <a name="isvisible"></a>  CBasePane::IsVisible

Bölmesi görünür olup olmadığını belirler.

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölmesi görünür durumda TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bir bölme görünürlüğünü belirlemek için bu yöntemi kullanın. Kullanmayın `::IsWindowVisible`.

Bölmesinde değil sekmeli (bkz [CBasePane::IsTabbed](#istabbed)), bu yöntem ws_vısıble stili denetler. Bu yöntem, bölmesinde sekmeli, üst sekmeli pencere görünürlüğünü denetler. Üst pencere görünür durumdaysa, işlev bölmesinde sekmesini kullanarak görünürlük denetimleri [CMFCBaseTabCtrl::IsTabVisible](../../mfc/reference/cmfcbasetabctrl-class.md#istabvisible).

##  <a name="loadstate"></a>  CBasePane::LoadState

Kayıt defterinden bölmedeki durumunu yükler.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName=NULL,
    int nIndex=-1,
    UINT uiID=(UINT)-1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[in] Profil adı.

*nIndex*<br/>
[in] Profili dizini.

*uiID*<br/>
[in] Bölmesinde kimliği.

### <a name="return-value"></a>Dönüş Değeri

Bölmesinde durumu başarıyla yüklendi TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Framework bölmesi durumu kayıt defterinden yüklenmesi için bu yöntemi çağırır. Türetilen bir sınıfta kaydeden ek bilgileri yüklemek için bir geçersiz kılma [CBasePane::SaveState](#savestate).

##  <a name="movewindow"></a>  CBasePane::MoveWindow

Bölme taşır.

```
virtual HDWP MoveWindow(
    CRect& rect,
    BOOL bRepaint = TRUE,
    HDWP hdwp = NULL);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
[in] Bir dikdörtgen bölmesinin boyutunu ve yeni konumunu belirtme.

*bRepaint*<br/>
[in] TRUE ise bölmesinde yeniden çizilmesini. FALSE ise bölmesinde yeniden çizilmesini değil.

*hdwp*<br/>
[in] Ertelenmiş pencere konumu yapısına işleyin.

### <a name="return-value"></a>Dönüş Değeri

Ertelenmiş pencere konumu yapısı ya da NULL işleyici.

### <a name="remarks"></a>Açıklamalar

NULL olarak geçirirseniz *hdwp* parametresi, bu yöntem penceresi normalde taşır. Bu yöntem, bir tanıtıcı geçirirseniz, ertelenmiş penceresi taşıma gerçekleştirir. Çağırarak bir tanıtıcı elde edebileceğiniz [BeginDeferWindowPos](/windows/desktop/api/winuser/nf-winuser-begindeferwindowpos) veya önceki bir çağrı bu yöntemin dönüş değerini depolayarak.

##  <a name="onafterchangeparent"></a>  CBasePane::OnAfterChangeParent

Bölmedeki üst değiştikten sonra framework tarafından çağırılır.

```
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```

### <a name="parameters"></a>Parametreler

*pWndOldParent*<br/>
[in] Önceki üst öğeye bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Ana bölmedeki, genellikle bir yerleştirme veya kayan işlemi nedeniyle değişiklikler yaptıktan sonra framework bu yöntemi çağırır.

Varsayılan uygulama, hiçbir şey yapmaz.

##  <a name="onbeforechangeparent"></a>  CBasePane::OnBeforeChangeParent

Yalnızca üst pencereye bölmesinde değiştirmeden önce framework tarafından çağırılır.

```
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,
    BOOL bDelay=FALSE);
```

### <a name="parameters"></a>Parametreler

*pWndNewParent*<br/>
[in] Yeni bir üst penceresine bir işaretçi.

*bDelay*<br/>
[in] Düzen ayarlamalar Gecikmeli olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Framework bölmedeki üst değişiklikleri hemen önce bu yöntem genellikle bir yerleştirme, kayan veya otomatik gizleme işlemi nedeniyle çağırır.

Varsayılan uygulama, hiçbir şey yapmaz.

##  <a name="ondrawcaption"></a>  CBasePane::OnDrawCaption

Açıklamalı alt yazı çizildiğinde framework bu yöntemi çağırır.

```
virtual void OnDrawCaption();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem için hiçbir işlevsellik sahip `CBasePane` sınıfı.

##  <a name="onmovepanedivider"></a>  CBasePane::OnMovePaneDivider

Bu yöntem şu anda kullanılmıyor.

```
virtual void OnMovePaneDivider(CPaneDivider* /* unused */);
```

### <a name="parameters"></a>Parametreler

*Kullanılmayan*<br/>
[in] Kullanılmıyor.

##  <a name="onpanecontextmenu"></a>  CBasePane::OnPaneContextMenu

Bölmeleri listesini içeren bir menü oluşturduğunda framework tarafından çağırılır.

```
virtual void OnPaneContextMenu(
    CWnd* pParentFrame,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pParentFrame*<br/>
[in] Ana çerçeve işaretçisi.

*Noktası*<br/>
[in] Kısayol menüsünü konumunu belirtir.

### <a name="remarks"></a>Açıklamalar

`OnPaneContextMenu` Geçerli çerçeve penceresine ait bölmeleri listesini tutar yerleştirme yöneticisini çağırır. Bu yöntem, bölmeleri adlarını bir kısayol menüsüne ekler ve görüntüler. Menü çubuğundaki komutları göster veya tek tek bölmeleri gizle.

Bu davranışını özelleştirmek için bu yöntemi yok sayın.

##  <a name="onremovefromminiframe"></a>  CBasePane::OnRemoveFromMiniFrame

Bir bölme kendi üst mini çerçeve penceresinde kaldırıldığında framework tarafından çağırılır.

```
virtual void OnRemoveFromMiniFrame(CPaneFrameWnd* pMiniFrame);
```

### <a name="parameters"></a>Parametreler

*pMiniFrame*<br/>
[in] İçinden bölmesinde kaldırılır bir mini çerçeve işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bir bölme (sonucunda, örneğin yerleştirme) kendi üst Mini çerçeve penceresi kaldırıldığında framework bu yöntemi çağırır.

Varsayılan uygulama, hiçbir şey yapmaz.

##  <a name="onsetaccdata"></a>  CBasePane::OnSetAccData

`CBasePane` Bu yöntem kullanmaz.

```
virtual BOOL OnSetAccData(long lVal);
```

### <a name="parameters"></a>Parametreler

*lVal*<br/>
[in] Kullanılmıyor.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem, her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="panefrompoint"></a>  CBasePane::PaneFromPoint

Belirtilen noktasını içeren bölme döndürür.

```
CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    bool bExactBar = false,
    CRuntimeClass* pRTCBarType = NULL) const;
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
[in] Noktasını denetlemek için ekran koordinatları olarak belirtir.

*nSensitivity*<br/>
[in] Bu tutara göre arama alanını artırın. Belirtilen noktasını artan alanında düşerse bir bölmesinde arama ölçütlerini eşleşecektir.

*bExactBar*<br/>
[in] Yok saymak için TRUE *nSensitivity* parametre; Aksi takdirde FALSE.

*pRTCBarType*<br/>
[in] BOŞ değilse, yalnızca belirtilen türün bölmeleri yöntemi arar.

### <a name="return-value"></a>Dönüş Değeri

`CBasePane`-Hiçbir bölmesinde bulunduysa belirtilen noktasını ya da NULL içeren türetilmiş nesne.

##  <a name="recalclayout"></a>  CBasePane::RecalcLayout

`CBasePane` Bu yöntem kullanmaz.

```
virtual void RecalcLayout();
```

##  <a name="removepanefromdockmanager"></a>  CBasePane::RemovePaneFromDockManager

Bir bölme kaydını siler ve yerleştirme manager listesinden kaldırır.

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
[in] Kaldırılacak bir bölme için bir işaretçi.

*bDestroy*<br/>
[in] TRUE ise, kaldırılan bölmesinde yok edilir.

*bAdjustLayout*<br/>
[in] TRUE ise yerleştirme düzeni hemen ayarlayın.

*bAutoHide*<br/>
[in] TRUE ise, yerleştirme düzeni autohide çubukları listesine ilişkilidir. FALSE ise, yerleştirme düzeni normal bölmeleri listesine ilişkilidir.

*pBarReplacement*<br/>
[in] Kaldırılan bölmesinde yerini alan bir bölme için bir işaretçi.

##  <a name="savestate"></a>  CBasePane::SaveState

Bölmedeki durumu kayıt defterine kaydeder.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName=NULL,
    int nIndex=-1,
    UINT uiID=(UINT)-1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[in] Profil adı.

*nIndex*<br/>
[in] Profili dizini.

*uiID*<br/>
[in] Bölmesinde kimliği.

### <a name="return-value"></a>Dönüş Değeri

Durumu başarılı bir şekilde kaydedilmiş ise TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Kayıt defterine bölmedeki durumu kaydettiğinde framework bu yöntemi çağırır. Geçersiz kılma `SaveState` ek bilgileri depolamak için türetilen bir sınıfta.

##  <a name="selectdefaultfont"></a>  CBasePane::SelectDefaultFont

Belirli bir cihaz bağlamı için varsayılan yazı tipi seçer.

```
CFont* SelectDefaultFont(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan bir işaretçiye [CFont sınıfı](../../mfc/reference/cfont-class.md) nesne.

##  <a name="setcontrolbarstyle"></a>  CBasePane::SetControlBarStyle

Denetim çubuğu stilini ayarlar.

```
virtual void SetControlBarStyle(DWORD dwNewStyle);
```

### <a name="parameters"></a>Parametreler

*dwNewStyle*<br/>
[in] Aşağıdaki değerlerden bit düzeyinde OR birleşimi.

|Stil|Açıklama|
|-----------|-----------------|
|AFX_CBRS_FLOAT|Denetim çubuğu float yapar.|
|AFX_CBRS_AUTOHIDE|Etkinleştirir otomatik modu gizleme.|
|AFX_CBRS_RESIZE|Etkinleştirir, yeniden boyutlandırma denetim çubuğu. Bu bayrak ayarlandığında, denetim çubuğunun yerleştirilebilir bir bölmede yerleştirilebilir.|
|AFX_CBRS_CLOSE|Denetim çubuğu gizlenmesi etkinleştirir.|

##  <a name="setdockingmode"></a>  CBasePane::SetDockingMode

Bölmenin yerleştirme modunu ayarlar.

```
void SetDockingMode(AFX_DOCK_TYPE dockModeNew);
```

### <a name="parameters"></a>Parametreler

*dockModeNew*<br/>
[in] Yeni takma bölmesi modunu belirtir.

### <a name="remarks"></a>Açıklamalar

Framework iki yerleştirme modunu destekler: standart ve hemen.

Standart yerleştirme modda, bölme ve Mini çerçeve pencereleri sürükleme dikdörtgenini kullanarak geçici olarak taşınır. Hemen yerleştirme modunda, Denetim çubuklarını ve Mini çerçeve pencereleri hemen, bağlamları ile birlikte taşınır.

Başlangıçta, yerleştirme modu genel olarak tanımlanan [CDockingManager::m_dockModeGlobal](../../mfc/reference/cdockingmanager-class.md#m_dockmodeglobal). Yerleştirme modu kullanarak tek tek her bölme için ayarlayabileceğiniz `SetDockingMode` yöntemi.

##  <a name="setpanealignment"></a>  CBasePane::SetPaneAlignment

Bölmenin hizalamasını ayarlar.

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

*dwAlignment*<br/>
[in] Yeni hizalamayı belirtir.

### <a name="remarks"></a>Açıklamalar

Genellikle, bir bölme başka bir ana çerçeve taraftan yerleştirildiğinde framework bu yöntemi çağırır.

İçin olası değerler aşağıdaki tabloda gösterilmektedir *dwAlignment*:

|Değer|Hizalama|
|-----------|---------------|
|CBRS_ALIGN_LEFT|Sola hizalama.|
|CBRS_ALIGN_RIGHT|Sağa hizalama.|
|CBRS_ALIGN_TOP|Üst hizalaması.|
|CBRS_ALIGN_BOTTOM|Alt hizalaması.|

##  <a name="setpanestyle"></a>  CBasePane::SetPaneStyle

Bölmesinin stilini ayarlar.

```
virtual void SetPaneStyle(DWORD dwNewStyle);
```

### <a name="parameters"></a>Parametreler

*dwNewStyle*<br/>
[in] Ayarlanacak yeni stilini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, afxres.h içinde tanımlanan CBRS_ stilleri birini ayarlamak için kullanılabilir. Bölmesinde stil ve bölmesinde hizalama birlikte depolandığından, yeni stil ile geçerli hizalaması gibi birleştirerek için bunu ayarlayın.

`pPane->SetPaneStyle (pPane->GetCurrentAlignment() | CBRS_TOOLTIPS);`

##  <a name="setwindowpos"></a>  CBasePane::SetWindowPos

Boyut, konum ve bir bölmenin Z düzenini değiştirir.

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
[in] Tanımlar `CWnd` önce gelen nesne `CWnd` Z düzenini nesnesi. Daha fazla bilgi için [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos).

*x*<br/>
[in] Pencerenin sol tarafındaki konumunu belirtir.

*Y*<br/>
[in] Pencerenin konumunu belirtir.

*cx*<br/>
[in] Pencerenin genişliğini belirtir.

*CY*<br/>
[in] Pencerenin yüksekliğini belirtir.

*nFlags*<br/>
[in] Boyut ve konum seçeneklerini belirtir. Daha fazla bilgi için [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos).

*hdwp*<br/>
[in] Bir veya daha fazla windows boyut ve konum bilgilerini içeren bir yapıya işleyin.

### <a name="return-value"></a>Dönüş Değeri

Tanıtıcı bir güncelleştirilmiş ertelenmiş pencere konumu yapısı veya NULL.

### <a name="remarks"></a>Açıklamalar

Varsa *pWndInsertAfter* NULL ise bu yöntemi çağırır [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos). Varsa *pWndInsertAfter* olduğu NULL olmayan, bu yöntemin çağırdığı `DeferWindowPos`.

##  <a name="showpane"></a>  CBasePane::ShowPane

Bölmesini gösterir veya gizler.

```
virtual void ShowPane(
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>Parametreler

*bBilgi Göster*<br/>
[in] Bir bölme belirtir (TRUE) gösterme veya gizleme (FALSE).

*bDelay*<br/>
[in] TRUE ise, yerleştirme düzeni yeniden hesaplama gecikir.

*bActivate*<br/>
[in] TRUE ise bölmesinde gösterilen etkin değil.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bölmesini gösterir veya bir gizler. Bu yöntemi yerine kullanın `ShowWindow` çünkü bu yöntem ilgili yerleştirme yöneticileri bölmedeki görünürlük değişiklikler hakkında bilgilendirir.

Kullanım [CBasePane::IsVisible](#isvisible) bölmesinin geçerli görünürlüğü belirlemek için.

##  <a name="stretchpane"></a>  CBasePane::StretchPane

Bir bölme, yatay veya dikey olarak genişletir.

```
virtual CSize StretchPane(
    int nLength,
    BOOL bVert);
```

### <a name="parameters"></a>Parametreler

*nLength*<br/>
[in] Uzunluğu, bölmesinde esnetme.

*bVert*<br/>
[in] TRUE ise bölmeyi dikey olarak esnetin. FALSE ise bölmeyi yatay olarak esnetin.

### <a name="return-value"></a>Dönüş Değeri

Esnetilmiş bölmesi boyutu.

##  <a name="undockpane"></a>  CBasePane::UndockPane

Dock sitesiyle, varsayılan kaydırıcı veya mini çerçevenin şu anda dayandığı bölmesinde kaldırır.

```
virtual void UndockPane(BOOL bDelay=FALSE);
```

### <a name="parameters"></a>Parametreler

*bDelay*<br/>
TRUE ise yerleştirme düzeni hemen hesaplanır değil.

### <a name="remarks"></a>Açıklamalar

Bölmesinde durumu işlemek veya bölmenin yerleştirme düzenden hariç tutmak için bu yöntemi çağırın.

Bu bölme kullanmaya devam etmek istiyorsanız, çağırın ya da [CBasePane::DockPane](#dockpane) veya [CBasePane::FloatPane](#floatpane) bu yöntemi çağırmadan önce.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CPane](../../mfc/reference/cbasepane-class.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)
