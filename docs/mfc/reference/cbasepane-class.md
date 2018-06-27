---
title: CBasePane sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74e8909a86a9382121dc2dc3375d12ed828c8c88
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957474"
---
# <a name="cbasepane-class"></a>CBasePane sınıfı
MFC içinde tüm bölmeleri için temel sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CBasePane : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CBasePane::CBasePane`|Varsayılan Oluşturucu.|  
|`CBasePane::~CBasePane`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CBasePane::accHitTest`|Alt öğesi veya alt nesne ekranında belirli bir noktada almak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CWnd::accHitTest](../../mfc/reference/cwnd-class.md#acchittest).)|  
|`CBasePane::accLocation`|Belirtilen nesne geçerli ekran konumunu almak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CWnd::accLocation](../../mfc/reference/cwnd-class.md#acclocation).)|  
|[CBasePane::AccNotifyObjectFocusEvent](#accnotifyobjectfocusevent)|`CBasePane` Bu yöntem kullanmaz.|  
|`CBasePane::accSelect`|Seçimi değiştirmek veya belirtilen nesnenin klavye odağı taşımak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CWnd::accSelect](../../mfc/reference/cwnd-class.md#accselect).)|  
|[CBasePane::AddPane](#addpane)|Bir bölme takma Yöneticisi'ni ekler.|  
|[CBasePane::AdjustDockingLayout](#adjustdockinglayout)|Yerleştirme düzeni ayarlamak için bir çağrı takma Manager'a yönlendirir.|  
|[CBasePane::AdjustLayout](#adjustlayout)|Bölmesinde iç düzenini ayarlamalıdır çerçevesi tarafından çağrılır.|  
|[CBasePane::CalcFixedLayout](#calcfixedlayout)|Denetim çubuğu yatay boyutunu hesaplar.|  
|[CBasePane::CanAcceptPane](#canacceptpane)|Başka bir bölme bölmesine yerleştirilmiş olup olmadığını belirler.|  
|[CBasePane::CanAutoHide](#canautohide)|Bölmesinde otomatik olarak Gizle modunu destekleyip desteklemediğini belirler.|  
|[CBasePane::CanBeAttached](#canbeattached)|Başka bir bölüme bölmenin yerleştirilmiş olup olmadığını belirler.|  
|[CBasePane::CanBeClosed](#canbeclosed)|Bölmesinde kapalı olup olmadığını belirler.|  
|[CBasePane::CanBeDocked](#canbedocked)|Başka bir bölüme bölmenin yerleştirilmiş olup olmadığını belirler.|  
|[CBasePane::CanBeResized](#canberesized)|Bölmesinde boyutlandırılabilir olup olmadığını belirler.|  
|[CBasePane::CanBeTabbedDocument](#canbetabbeddocument)|Bölmesinde bir MDI sekmeli belge dönüştürülebilir olup olmadığını belirtir.|  
|[CBasePane::CanFloat](#canfloat)|Bölmesinde kaydırabilirsiniz olup olmadığını belirler.|  
|[CBasePane::CanFocus](#canfocus)|Bölmesinde odak alıp alamayacağını belirtir.|  
|[CBasePane::CopyState](#copystate)|Belirli bir bölme durumunu kopyalar.|  
|[CBasePane::CreateDefaultMiniframe](#createdefaultminiframe)|Bölmesinde float, bir kısa çerçeve penceresi oluşturur.|  
|[CBasePane::CreateEx](#createex)|Bölmesi denetimi oluşturur.|  
|[CBasePane::DockPane](#dockpane)|Bir bölme başka bir bölme ya da bir çerçeve penceresinde docks.|  
|[CBasePane::DockPaneUsingRTTI](#dockpaneusingrtti)|Çalışma zamanı türü bilgileri kullanarak bölmesinde docks.|  
|[CBasePane::DockToFrameWindow](#docktoframewindow)|Dockable bölmesinde çerçeveye docks.|  
|[CBasePane::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Başka bir bölme dinamik olarak bu bölme ve üst çerçeve arasında eklenebilir olup olmadığını belirler.|  
|[CBasePane::EnableDocking](#enabledocking)|Etkinleştirir bölmesinde ana çerçeve yerleştirme.|  
|[CBasePane::EnableGripper](#enablegripper)|Etkinleştirir veya kavrayıcının devre dışı bırakır. Kavrayıcının etkinleştirilirse, kullanıcının bölmesini yeniden konumlandırmak için sürükleyebilirsiniz.|  
|`CBasePane::FillWindowRect`|Dahili olarak kullanılır.|  
|[CBasePane::FloatPane](#floatpane)|Bölmesinde kayar.|  
|`CBasePane::get_accChild`|Adresini almak için çerçevesi tarafından çağrılır bir `IDispatch` belirtilen alt arabirimi. (Geçersiz kılmaları [CWnd::get_accChild](../../mfc/reference/cwnd-class.md#get_accchild).)|  
|`CBasePane::get_accChildCount`|Bu nesneye ait alt sayısını almak üzere çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CWnd::get_accChildCount](../../mfc/reference/cwnd-class.md#get_accchildcount).)|  
|`CBasePane::get_accDefaultAction`|Nesne için varsayılan eylem tanımlayan bir dize almak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CWnd::get_accDefaultAction](../../mfc/reference/cwnd-class.md#get_accdefaultaction).)|  
|`CBasePane::get_accDescription`|Belirtilen nesneyi görsel görünümünü tanımlayan bir dize almak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CWnd::get_accDescription](../../mfc/reference/cwnd-class.md#get_accdescription).)|  
|`CBasePane::get_accFocus`|Klavye odağı olan nesnesini almak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CWnd::get_accFocus](../../mfc/reference/cwnd-class.md#get_accfocus).)|  
|`CBasePane::get_accHelp`|Nesne için Yardım özelliği dizesini almak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CWnd::get_accHelp](../../mfc/reference/cwnd-class.md#get_acchelp).)|  
|[CBasePane::get_accHelpTopic](#get_acchelptopic)|Belirtilen nesne ile ilişkili olan WinHelp dosyanın tam yolunu ve bu dosyayı uygun konusunda tanıtıcısı almak üzere çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CWnd::get_accHelpTopic](../../mfc/reference/cwnd-class.md#get_acchelptopic).)|  
|`CBasePane::get_accKeyboardShortcut`|Nesne için belirtilen kısayol tuşu almak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CWnd::get_accKeyboardShortcut](../../mfc/reference/cwnd-class.md#get_acckeyboardshortcut).)|  
|`CBasePane::get_accName`|Belirtilen nesnenin adını almak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CWnd::get_accName](../../mfc/reference/cwnd-class.md#get_accname).)|  
|`CBasePane::get_accParent`|Alınacak çerçevesi tarafından çağrılır `IDispatch` nesnenin üst arabirimi. (Geçersiz kılmaları [CWnd::get_accParent](../../mfc/reference/cwnd-class.md#get_accparent).)|  
|`CBasePane::get_accRole`|Belirtilen nesnenin rol açıklayan bilgileri almak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CWnd::get_accRole](../../mfc/reference/cwnd-class.md#get_accrole).)|  
|[CBasePane::get_accSelection](#get_accselection)|Seçili alt öğe bu nesnenin almak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CWnd::get_accSelection](../../mfc/reference/cwnd-class.md#get_accselection).)|  
|`CBasePane::get_accState`|Belirtilen nesne geçerli durumunu almak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CWnd::get_accState](../../mfc/reference/cwnd-class.md#get_accstate).)|  
|`CBasePane::get_accValue`|Belirtilen nesne değerini almak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CWnd::get_accValue](../../mfc/reference/cwnd-class.md#get_accvalue).)|  
|[CBasePane::GetCaptionHeight](#getcaptionheight)|Resim yazısı yükseklik döndürür.|  
|[CBasePane::GetControlBarStyle](#getcontrolbarstyle)|Denetim çubuğu stilini döndürür.|  
|[CBasePane::GetCurrentAlignment](#getcurrentalignment)|Geçerli bölmesinde hizalama döndürür.|  
|[CBasePane::GetDockingMode](#getdockingmode)|Bölmesinde geçerli takma modunun döndürür.|  
|[CBasePane::GetDockSiteFrameWnd](#getdocksiteframewnd)|Bölmenin yerleştirme sitesidir penceresine bir işaretçi döndürür.|  
|[CBasePane::GetEnabledAlignment](#getenabledalignment)|Bölmesine uygulanan CBRS_ALIGN_ stiller döndürür.|  
|[CBasePane::GetMFCStyle](#getmfcstyle)|MFC için belirli bölmesinde stilleri döndürür.|  
|[CBasePane::GetPaneIcon](#getpaneicon)|Bir tanıtıcı bölmesinde simgesini döndürür.|  
|`CBasePane::GetPaneRect`|Dahili olarak kullanılır.|  
|[CBasePane::GetPaneRow](#getpanerow)|Bir işaretçi döndürür [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)bölmesinde burada yerleştirilmiştir nesnesi.|  
|[CBasePane::GetPaneStyle](#getpanestyle)|Bölmesinde stili döndürür.|  
|[CBasePane::GetParentDockSite](#getparentdocksite)|Bir işaretçi üst yerleştirme siteye döndürür.|  
|[CBasePane::GetParentMiniFrame](#getparentminiframe)|Bir işaretçi üst kısa çerçeve pencere döndürür.|  
|[CBasePane::GetParentTabbedPane](#getparenttabbedpane)|Bir işaretçi üst sekmeli bölmesine döndürür.|  
|[CBasePane::GetParentTabWnd](#getparenttabwnd)|İçinde bir sekme üst penceresine bir işaretçi döndürür.|  
|[CBasePane::GetRecentVisibleState](#getrecentvisiblestate)|Bir bölme arşivden geri yüklendiğinde framework bu yöntemi çağırır.|  
|[CBasePane::HideInPrintPreviewMode](#hideinprintpreviewmode)|Baskı önizlemede bölmenin gizli olup olmadığını belirtir.|  
|[CBasePane::InsertPane](#insertpane)|Belirtilen bölmesinde takma Yöneticisi ile kaydeder.|  
|[CBasePane::IsAccessibilityCompatible](#isaccessibilitycompatible)|Bölmesinde Active Accessibility destekleyip desteklemediğini belirtir.|  
|[CBasePane::IsAutoHideMode](#isautohidemode)|Bir bölme otomatik gizleme modunda olup olmadığını belirler.|  
|[CBasePane::IsDialogControl](#isdialogcontrol)|Bölmesinde iletişim denetimi olup olmadığını belirtir.|  
|[CBasePane::IsDocked](#isdocked)|Bölmenin yerleştirilmiş olup olmadığını belirler.|  
|[CBasePane::IsFloating](#isfloating)|Bölmesinde kayan olup olmadığını belirler.|  
|[CBasePane::IsHorizontal](#ishorizontal)|Bölmesinin yatay olarak yerleştirilmiş olup olmadığını belirler.|  
|[CBasePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Bölmesinde çok bölmesi çerçeve penceresinde olup olmadığını belirtir.|  
|[CBasePane::IsMDITabbed](#ismditabbed)|MDI alt penceresine sekmeli belge olarak bölmesinde eklenmiş olup olmadığını belirler.|  
|[CBasePane::IsPaneVisible](#ispanevisible)|Belirtir olup olmadığını `WS_VISIBLE` bayrağı bölmesi ayarlanır.|  
|[CBasePane::IsPointNearDockSite](#ispointneardocksite)|Belirli bir noktaya yerleştirme site olup olmadığını belirler.|  
|[CBasePane::IsResizable](#isresizable)|Bölmesinde boyutlandırılabilir olup olmadığını belirler.|  
|[CBasePane::IsRestoredFromRegistry](#isrestoredfromregistry)|Bölmesinde kayıt defterinden geri yüklenip yüklenmeyeceğini belirler.|  
|[CBasePane::IsTabbed](#istabbed)|Sekmeli penceresinin sekme denetimi bölmesinde eklenmiş olup olmadığını belirler.|  
|`CBasePane::IsTooltipTopmost`|Dahili olarak kullanılır.|  
|[CBasePane::IsVisible](#isvisible)|Bölmesinde görünür olup olmadığını belirler.|  
|[CBasePane::LoadState](#loadstate)|Bölmesinde durum kayıt defterinden yükler.|  
|[CBasePane::MoveWindow](#movewindow)|Bölme taşır.|  
|[CBasePane::OnAfterChangeParent](#onafterchangeparent)|Bölmesi'nin üst değiştiğinde çerçevesi tarafından çağrılır.|  
|[CBasePane::OnBeforeChangeParent](#onbeforechangeparent)|Yalnızca kendi üst penceresi bölmesinde değiştirmeden önce çerçevesi tarafından çağrılır.|  
|[CBasePane::OnDrawCaption](#ondrawcaption)|Resim yazısını çizildiğinde framework bu yöntemi çağırır.|  
|[CBasePane::OnMovePaneDivider](#onmovepanedivider)|Bu yöntem şu anda kullanılmaz.|  
|[CBasePane::OnPaneContextMenu](#onpanecontextmenu)|Bölmeleri listesini içeren bir menü oluşturduğunda çerçevesi tarafından çağrılır.|  
|[CBasePane::OnRemoveFromMiniFrame](#onremovefromminiframe)|Bir bölme kendi üst mini çerçeve penceresinden kaldırıldığında çerçevesi tarafından çağrılır.|  
|[CBasePane::OnSetAccData](#onsetaccdata)|`CBasePane` Bu yöntem kullanmaz.|  
|`CBasePane::OnUpdateCmdUI`|Dahili olarak kullanılır.|  
|[CBasePane::PaneFromPoint](#panefrompoint)|Belirtilen noktasını içeren bölme döndürür.|  
|`CBasePane::PreTranslateMessage`|Sınıfı tarafından kullanılan [CWinApp](../../mfc/reference/cwinapp-class.md) için gönderilen önce pencere iletileri çevirmek için [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows çalışır. (Geçersiz kılmaları [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CBasePane::RecalcLayout](#recalclayout)|`CBasePane` Bu yöntem kullanmaz.|  
|[CBasePane::RemovePaneFromDockManager](#removepanefromdockmanager)|Bir bölme kaydını siler ve yerleştirme Yöneticisi listesinden kaldırır.|  
|[CBasePane::SaveState](#savestate)|Kayıt defterine Bölmesi'nin durumunu kaydeder.|  
|[CBasePane::SelectDefaultFont](#selectdefaultfont)|Verilen cihaz bağlamı için varsayılan yazıtipi seçer.|  
|`CBasePane::Serialize`|Okur veya bir arşiv değiştirilmesine veya bu nesneyi yazar. (Geçersiz kılmaları [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CBasePane::SetControlBarStyle](#setcontrolbarstyle)|Denetim çubuğu stilini ayarlar.|  
|[CBasePane::SetDockingMode](#setdockingmode)|Bölmenin yerleştirme modunu ayarlar.|  
|`CBasePane::SetMDITabbed`|Dahili olarak kullanılır.|  
|[CBasePane::SetPaneAlignment](#setpanealignment)|Bölmenin hizalamasını belirler.|  
|`CBasePane::SetPaneRect`|Dahili olarak kullanılır.|  
|[CBasePane::SetPaneStyle](#setpanestyle)|Bölmesinin stilini ayarlar.|  
|`CBasePane::SetRestoredFromRegistry`|Dahili olarak kullanılır.|  
|[CBasePane::SetWindowPos](#setwindowpos)|Boyut, konum ve bir bölmenin Z düzenini değiştirir.|  
|[CBasePane::ShowPane](#showpane)|Bölmesini gösterir veya gizler.|  
|[CBasePane::StretchPane](#stretchpane)|Dikey veya yatay bölme uzatır.|  
|[CBasePane::UndockPane](#undockpane)|Bölmenin yerleştirme site, varsayılan kaydırıcı veya şu anda dayandığı kısa çerçeve penceresi kaldırır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBasePane::DoPaint](#dopaint)|Bölmenin arka plan doldurur.|  
  
## <a name="remarks"></a>Açıklamalar  
 MFC'de kullanılabilen genişletilmiş yerleştirme özellikleri destekleyen bir bölmesinde sınıfı oluşturmak istiyorsanız, ondan türetilmelidir `CBasePane` veya [CPane sınıfı](../../mfc/reference/cpane-class.md).  
  
## <a name="customization-tips"></a>Özelleştirme ipuçları  
 Aşağıdaki özelleştirme ipuçları ilgilidir `CBasePane Class` ve ondan devralan tüm sınıflar:  
  
-   Bir bölme oluşturduğunuzda, birkaç yeni stiller uygulayabilirsiniz:  
  
    - `AFX_CBRS_FLOAT` bölmesinde float yapar.  
  
    - `AFX_CBRS_AUTOHIDE` etkinleştirir otomatik modu gizle.  
  
    - `AFX_CBRS_CLOSE` (gizli) kapatılması için bölmesinde sağlar.  
  
     Bit düzeyinde OR işlemi ile birleştirebilirsiniz bayrakları bunlar.  
  
 `CBasePane` Bu bayrakların yansıtacak şekilde aşağıdaki sanal Boolean yöntemlerini uygular: [CBasePane::CanBeClosed](#canbeclosed), [CBasePane::CanAutoHide](#canautohide), [CBasePane::CanFloat](#canfloat). Bunları kendi davranışını özelleştirmek için türetilmiş sınıflarda geçersiz kılabilirsiniz.  
  
-   Geçersiz kılarak yerleştirme davranışını özelleştirebilirsiniz [CBasePane::CanAcceptPane](#canacceptpane). Dönüş, bölmeniz `FALSE` başka bir bölme kendisine sabitlenmesini engellemek için bu yönteminden.  
  
-   Olamaz float ve engelleyen herhangi bir bölme önce yerleştirme statik bir bölmesi (OutlookDemo örnek Outlook çubuğunda benzer) oluşturmak, değişken olmayan olarak oluşturun ve geçersiz kılmak istiyorsanız, [CBasePane::DoesAllowDynInsertBefore](#doesallowdyninsertbefore) döndürülecek `FALSE`. Varsayılan uygulama döndürür `FALSE` bölmesi olmadan oluşturulursa `AFX_CBRS_FLOAT` stili.  
  
-   Tüm bölmeleri kimliklerle -1 dışındaki oluşturun.  
  
-   Bölmesinde görünürlük belirlemek için [CBasePane::IsVisible](#isvisible). Doğru görünürlük durumu işler içinde sekmeli ve modları otomatik olarak gizle.  
  
-   Kayan yeniden boyutlandırılabilir bölmesi oluşturmak istiyorsanız, bu olmadan oluşturmak `AFX_CBRS_FLOAT` stili ve çağrı [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).  
  
-   Bir bölme takma düzeninden hariç ya da bir araç çubuğu yerleştirme çubuğunu kaldırmak için [CBasePane::UndockPane](#undockpane). Sekmeli windows sekmelerde bulunan bölmeleri veya otomatik olarak gizle modunda bölmeleri için bu yöntemi çağırmanız gerekmez.  
  
-   Kayana istediğiniz ya da otomatik olarak gizle modunda bir bölme yuvadan varsa çağırmalıdır [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode) ile `FALSE` çağırmadan önce ilk bağımsız değişken olarak [CBasePane::FloatPane](#floatpane) veya [ CBasePane::UndockPane](#undockpane).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CBasePane` sınıfı. Örnek bir bölmesinden almayı gösterir `CFrameWndEx` sınıfı ve yerleştirme modu, bölmesinde hizalama ve bölmesinde stili nasıl ayarlanacağı. Kod arasındadır [Word paneli örnek](../../visual-cpp-samples.md).  
  
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
 [in] *int*  
 Kullanılmadı.  
  
##  <a name="addpane"></a>  CBasePane::AddPane  
 Bir bölme takma Yöneticisi'ni ekler.  
  
```  
void AddPane(CBasePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
 Bir işaretçi bir bölmesine eklemek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bir bölme bir takma Yöneticisi ekleyen bir kolaylık yöntemidir. Bu yöntemi kullanarak, üst çerçeve türünü çözümler kod yazmanız gerekmez.  
  
 Daha fazla bilgi için bkz: [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) ve [CMDIFrameWndEx::AddPane](../../mfc/reference/cmdiframewndex-class.md#addpane).  
  
##  <a name="adjustdockinglayout"></a>  CBasePane::AdjustDockingLayout  
 Yerleştirme düzeni ayarlamak için bir çağrı takma Manager'a yönlendirir.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *hdwp*  
 Birden çok pencereyi konumlarını içeren bir yapı için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yerleşik düzeni ayarlayan bir kolaylık yöntemidir. Bu yöntemi kullanarak, üst çerçeve türünü çözümler kod yazmanız gerekmez.  
  
 Daha fazla bilgi için bkz: [CDockingManager::AdjustDockingLayout](../../mfc/reference/cdockingmanager-class.md#adjustdockinglayout)  
  
##  <a name="adjustlayout"></a>  CBasePane::AdjustLayout  
 Bir bölme iç düzenini ayarlamak için çerçevesi tarafından çağrılır.  
  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İç düzenini ayarlamak bir bölme sahip olduğunda framework bu yöntemi çağırır. Temel uygulama hiçbir şey yapmaz.  
  
##  <a name="calcfixedlayout"></a>  CBasePane::CalcFixedLayout  
 Denetim çubuğu yatay boyutunu hesaplar.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bStretch*  
 Çubuğu çerçevesinin boyutunu uzatılmış olup olmadığını gösterir. *BStretch* parametresi olduğunda sıfır olmayan çubuğu bir takma çubuğu (yerleştirme için kullanılamaz) değil ve yerleşik veya kayan olduğunda 0 (yerleştirme için kullanılabilir).  
  
 [in] *bHorz*  
 Çubuk yatay veya dikey olarak yönlendirilmiş olduğunu gösterir. *BHorz* çubuğu yatay olarak yönlendirilmiş ve dikey olarak yönlendirilmiş ise 0 ise parametresi sıfırdan farklı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim çubuğu boyutu piksel cinsinden bir `CSize` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Açıklamalar bölümüne bakın [CControlBar::CalcFixedLayout](../../mfc/reference/ccontrolbar-class.md#calcfixedlayout)  
  
##  <a name="canacceptpane"></a>  CBasePane::CanAcceptPane  
 Başka bir bölme bölmesine yerleştirilmiş olup olmadığını belirler.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
 Yerleştirme için bölmesinde bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` başka bir bölme kabul Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework tarafından belirtilen bölmesinde docks önce bu yöntemi çağırır *pBar* geçerli bölmesine.  
  
 Bu yöntemi kullanın ve [CBasePane::CanBeDocked](#canbedocked) nasıl uygulamanızdaki diğer bölmeleri için bölmeleri yerleştirme denetlemek için yöntem.  
  
 Varsayılan uygulama döndürür `FALSE`.  
  
##  <a name="canautohide"></a>  CBasePane::CanAutoHide  
 Bölmesinde otomatik olarak Gizle modunu destekleyip desteklemediğini belirler.  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Bu bölme otomatik olarak Gizle modunu destekliyorsa, Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework bölmesinde otomatik olarak gizle modu destekleyip desteklemediğini belirlemek için bu işlevi çağırır.  
  
 Oluşturma sırasında geçirerek özelliği ayarlayabilir `AFX_CBRS_AUTOHIDE` bayrağını [CBasePane::CreateEx](#createex).  
  
 Varsayılan uygulama denetler `AFX_CBRS_AUTOHIDE` bayrağı. Bu davranış özelleştirmek için bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="canbeattached"></a>  CBasePane::CanBeAttached  
 Başka bir bölme veya çerçeveye penceresine bölmesinde yerleştirilmiş olup olmadığını belirler.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde başka bir bölme veya çerçeveye penceresine; yerleşik, Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama döndürür `FALSE`. Etkinleştirmek veya arama olmadan yerleştirme becerisini devre dışı bırakmak için bir türetilmiş sınıfta bu yöntemin üzerine [CBasePane::EnableDocking](#enabledocking).  
  
##  <a name="canbeclosed"></a>  CBasePane::CanBeClosed  
 Bölmesinde kapalı olup olmadığını belirler.  
  
```  
virtual BOOL CanBeClosed() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölme kapatılabilir Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework Bölmesi Kapalı olup olmadığını belirlemek için bu yöntemi çağırır. Yöntem döndürüyorsa `TRUE`, **Kapat** düğmesi Bölmesi'nin başlık çubuğuna eklenen ya da Bölmesi'nin miniframe penceresinin başlık çubuğunu bölmesinde kayan durumlarda.  
  
 Oluşturma sırasında geçirerek özelliği ayarlayabilir `AFX_CBRS_CLOSE` bayrağını [CBasePane::CreateEx](#createex).  
  
 Varsayılan uygulama denetler `AFX_CBRS_CLOSE` bayrağı.  
  
##  <a name="canbedocked"></a>  CBasePane::CanBeDocked  
 Başka bir bölüme bölmenin yerleştirilmiş olup olmadığını belirler.  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDockBar*  
 Başka bir bölme için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Bu bölme başka bir bölüme; yerleşik, Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework tarafından belirtilen bölmesinde docks önce bu yöntemi çağırır *pDockBar* geçerli bölmesine.  
  
 Bu yöntemi kullanın ve [CBasePane::CanAcceptPane](#canacceptpane) nasıl uygulamanızdaki diğer bölmeleri için bölmeleri yerleştirme denetlemek için yöntem.  
  
 Varsayılan uygulama döndürür `FALSE`.  
  
##  <a name="canberesized"></a>  CBasePane::CanBeResized  
 Bölmesinde boyutlandırılabilir olup olmadığını belirler.  
  
```  
virtual BOOL CanBeResized() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde yeniden boyutlandırılabilir Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem denetler `AFX_CBRS_RESIZE` varsayılan olarak belirtilen bayrağı `CBasePane::OnCreate`. Bu bayrak belirtilmezse, yerleşik yönetici yerleştirme yerine dahili olarak immovable bölmesinde işaretler.  
  
##  <a name="canbetabbeddocument"></a>  CBasePane::CanBeTabbedDocument  
 Bölmesinde bir MDI sekmeli belge dönüştürülebilir olup olmadığını belirtir.  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` sekmeli belge bölmesinde dönüştürülebilir ise; Aksi takdirde `FALSE`. `CBasePane::CanBeTabbedDocument` her zaman döndürür `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli nesneler yalnızca `CBasePane`-türleri gibi türetilen [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md), sekmeli belgeler dönüştürülebilir.  
  
##  <a name="canfloat"></a>  CBasePane::CanFloat  
 Bölmesinde kaydırabilirsiniz olup olmadığını belirler.  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde kaydırabilirsiniz; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework bölmesinde kaydırabilirsiniz olup olmadığını belirlemek için bu yöntemi çağırır.  
  
 Oluşturma sırasında geçirerek özelliği ayarlayabilir `AFX_CBRS_FLOAT` bayrağını [CBasePane::CreateEx](#createex).  
  
> [!NOTE]
>  Framework değişken olmayan bölmeleri statik ve yerleştirme durumlarına değiştiremezsiniz varsayar. Bu nedenle, framework değişken olmayan bölmeleri takma durumunu kaydetmez.  
  
 Varsayılan uygulama denetler `AFX_CBRS_FLOAT` stili.  
  
##  <a name="canfocus"></a>  CBasePane::CanFocus  
 Bölmesinde odak alıp alamayacağını belirtir.  
  
```  
virtual BOOL CanFocus() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde odak alamıyorsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Odağı denetlemek için bir türetilmiş sınıfta bu yöntemi geçersiz kılın. Örneğin, araç çubukları odak alamaz olduğundan, bu yöntem `FALSE` zaman çağırıldığında araç nesneler üzerinde.  
  
 Bir bölme yerleşik ya da kaydırılmış giriş odağını ayarlamak framework çalışır.  
  
##  <a name="copystate"></a>  CBasePane::CopyState  
 Belirli bir bölme durumunu kopyalar.  
  
```  
virtual void CopyState(CBasePane* pOrgBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pOrgBar*  
 Başka bir bölme için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem durumundan kopyalar *pOrgBar* bu bölmesine.  
  
##  <a name="createdefaultminiframe"></a>  CBasePane::CreateDefaultMiniframe  
 Bölmesinde float varsa, bu yöntem için bir kısa çerçeve penceresi oluşturur.  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rectInitial*  
 Kısa çerçeve penceresi ilk koordinatlarını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni bir kısa çerçeve penceresi için bir işaretçi veya `NULL` oluşturma başarısız olursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme bir kayan durumuna geçtiğinde framework bu yöntemi çağırır. Yöntemi, bir kısa çerçeve penceresi oluşturur ve bu penceresine bölmesinde iliştirir.  
  
 Varsayılan uygulama döndürür `NULL`.  
  
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
 [in] *dwStyleEx*  
 Genişletilmiş stilleri (bkz [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) daha fazla bilgi için).  
  
 [in] *lpszClassName*  
 Pencere sınıfı adı.  
  
 [in] *lpszWindowName*  
 Pencere adı.  
  
 [in] *dwStyle*  
 Pencere stili (bkz [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)).  
  
 [in] *rect*  
 İlk dikdörtgen.  
  
 [in] *pParentWnd*  
 Üst pencere için bir işaretçi.  
  
 [in] *nID*  
 Bölmesinde kimliğini belirtir. Benzersiz olmalıdır.  
  
 [in] *dwControlBarStyle*  
 Stil bölmeleri için işaretler.  
  
 [in] *pContext*  
 Bir işaretçi `CcreateContext`  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde başarıyla oluşturulduysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınıfının bir pencere oluşturur `lpszClassName`. Belirtirseniz `WS_CAPTION`, bu yöntem temizler `WS_CAPTION` stili bit ve kümelerini `CBasePane::m_bHasCaption` için `TRUE`, kitaplık açıklamalı alt bölmeleri desteklemediğinden.  
  
 Alt pencere stilleri ve MFC denetimi (CBRS_) stilleri çubuğu herhangi bir bileşimini kullanabilirsiniz.  
  
 Kitaplık bölmeleri için birkaç yeni stiller ekler. Aşağıdaki tabloda yeni stiller açıklanmaktadır:  
  
|Stil|Açıklama|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|Bölmesinde float.|  
|`AFX_CBRS_AUTOHIDE`|Bölmesinde otomatik olarak Gizle modunu destekler|  
|`AFX_CBRS_RESIZE`|Bölmesinde yeniden boyutlandırılabilir. **Önemli:** bu stili uygulanmadı.|  
|`AFX_CBRS_CLOSE`|Bölme kapatılabilir.|  
|`AFX_CBRS_AUTO_ROLLUP`|Bunu gezinen zaman bölmesinde dökümüne.|  
|`AFX_CBRS_REGULAR_TABS`|Bir bölme bu stili sahip başka bir bölüme noktalarını sekmeli normal bir pencere oluşturulur. (Daha fazla bilgi için bkz: [CTabbedPane sınıfı](../../mfc/reference/ctabbedpane-class.md).)|  
|`AFX_CBRS_OUTLOOK_TABS`|Bir bölme bu stili sahip başka bir bölüme noktaları bir Outlook stili sekmeli penceresi oluşturulur. (Daha fazla bilgi için bkz: [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).)|  
  
 Yeni stiller kullanmak için bunları belirtin *dwControlBarStyle*.  
  
##  <a name="dockpane"></a>  CBasePane::DockPane  
 Bir bölme başka bir bölme ya da bir çerçeve penceresinde docks.  
  
```  
virtual BOOL DockPane(
    CBasePane* pDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDockBar*  
 Başka bir bölme için bir işaretçi.  
  
 [in] *lpRect*  
 Hedef dikdörtgen belirtir.  
  
 [in] *dockMethod*  
 Takma yöntemini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` denetim çubuğu başarıyla; yerleşik varsa Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme başka bir bölme veya bir yerleştirme çubuğuna sabitlemek için bu işlevi çağırmak ( [CDockSite sınıfı](../../mfc/reference/cdocksite-class.md)) tarafından belirtilen *pDockBar*, veya bir ana çerçeve varsa *pDockBar* olan `NULL`.  
  
 *dockMethod* bölmesinde nasıl yerleştirildiğini belirler. Bkz: [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) olası değerler listesi.  
  
##  <a name="dockpaneusingrtti"></a>  CBasePane::DockPaneUsingRTTI  
 Çalışma zamanı türü bilgileri kullanarak bölmesinde docks.  
  
```  
void DockPaneUsingRTTI(BOOL bUseDockSite);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bUseDockSite*  
 Varsa `TRUE`, yerleştirme siteye sabitleyin. Varsa `FALSE`, üst çerçeve sabitleyin.  
  
##  <a name="docktoframewindow"></a>  CBasePane::DockToFrameWindow  
 Dockable bölmesinde çerçeveye docks.  
  
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
 [in] *dwAlignment*  
 Bölmesine sabitlemek istediğiniz üst çerçeve tarafında.  
  
 [in] *lpRect*  
 İstenen boyutu.  
  
 [in] *dwDockFlags*  
 Yoksayıldı.  
  
 [in] *pRelativeBar*  
 Yoksayıldı.  
  
 [in] *nRelativeIndex*  
 Yoksayıldı.  
  
 [in] *bOuterEdge*  
 Varsa `TRUE` ve diğer dockable bölmeler tarafından belirtilen tarafında *dwAlignment*, diğer bölmeleri dışında bölmesi yuvalanmış üst çerçeve köşesine yakın. Varsa `FALSE`, bölmesinde yakın istemci alanını merkezine yerleştirilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bölmesinde ayırıcı başarısız olur ( [CPaneDivider sınıfı](../../mfc/reference/cpanedivider-class.md)) oluşturulamıyor. Aksi takdirde, her zaman döndürür `TRUE`.  
  
##  <a name="doesallowdyninsertbefore"></a>  CBasePane::DoesAllowDynInsertBefore  
 Başka bir bölme dinamik olarak bu bölme ve üst çerçeve arasında eklenebilir olup olmadığını belirler.  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bir kullanıcı başka bir bölme ekleyebilirsiniz Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve bir kullanıcı bu bölme önce bölmesini dinamik olarak eklemek için olup olmadığını belirlemek için bu yöntemi çağırır.  
  
 Örneğin, uygulamanızın çerçeve (örneğin, Outlook Çubuğu) sol tarafındaki yerleşik bölmesinde oluşturduğu varsayalım. Kullanıcının ilk bölmesi sol için başka bir bölüme yerleştirme engellemek için bu yöntemi geçersiz kılın ve dönmek `FALSE`.  
  
 Bu yöntemi geçersiz kılın ve dönüş öneririz `FALSE` değişken olmayan bölmeleri türetildiği için [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md).  
  
 Varsayılan uygulama döndürür `TRUE`.  
  
##  <a name="dopaint"></a>  CBasePane::DoPaint  
 Bölmenin arka plan doldurur.  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama arka doldurmak için geçerli visual yöneticisini çağırır ( [CMFCVisualManager::OnFillBarBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfillbarbackground)).  
  
##  <a name="enabledocking"></a>  CBasePane::EnableDocking  
 Etkinleştirir bölmesinde ana çerçeve yerleştirme.  
  
```  
virtual void EnableDocking(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwAlignment*  
 Etkinleştirmek için takma hizalamasını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Ana çerçeveye takma hizalama etkinleştirmek için bu yöntemi çağırın. Bir birleşimini geçirebilirsiniz `CBRS_ALIGN_` bayrakları (daha fazla bilgi için bkz: [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)).  
  
 `EnableDocking` İç bayrağını ayarlar `CBasePane::m_dwEnabledAlignment` ve bölme yerleştirildiğinde framework bu bayrağı denetler.  
  
 Çağrı [CBasePane::GetEnabledAlignment](#getenabledalignment) bölmesi için takma hizalama belirlemek için.  
  
##  <a name="enablegripper"></a>  CBasePane::EnableGripper  
 Etkinleştirir veya kavrayıcının devre dışı bırakır. Kavrayıcının etkinleştirilirse, kullanıcının bölmesini yeniden konumlandırmak için sürükleyebilirsiniz.  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSistemlerde*  
 `TRUE` kavrayıcının etkinleştirmek için; `FALSE` devre dışı bırakmak için.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve kullanmak yerine kavrayıcının etkinleştirmek için bu yöntemi kullanır `WS_CAPTION` stili.  
  
##  <a name="floatpane"></a>  CBasePane::FloatPane  
 Bölmesinde kayar.  
  
```  
virtual BOOL FloatPane(
    CRect rectFloat,  
    AFX_DOCK_METHOD dockMethod=DM_UNKNOWN,  
    bool bShow=true);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rectFloat*  
 Kayan bölmesinde görüntülendiği ekran koordinatları belirtir.  
  
 [in] *dockMethod*  
 Bölmesinde float için kullanılacak yerleştirme yöntemini belirtir.  
  
 [in] *bBilgi Göster*  
 Kayan bölmesinde görünür olup olmadığını belirtir ( `TRUE`) veya gizli ( `FALSE`).  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde başarıyla kaydırılmış Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme tarafından belirtilen ekran konumunda float için bu yöntemi çağırın *rectFloat*.  
  
##  <a name="get_acchelptopic"></a>  CBasePane::get_accHelpTopic  
 Framework tam yolunu almak için bu yöntemi çağırır `WinHelp` belirtilen nesnenin ve bu dosyayı uygun konusunda tanıtıcısı ile ilişkili dosya.  
  
```  
virtual HRESULT get_accHelpTopic(
    BSTR* pszHelpFile,  
    VARIANT varChild,  
    long* pidTopic);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pszHelpFile*  
 Adres bir `BSTR` tam yolunu alır `WinHelp` varsa belirtilen nesne ile ilişkili dosya.  
  
 [in] *varChild*  
 Alınacak Yardım konusunu nesnesi veya bir nesne alt öğelerinin olup olmadığını belirtir. Bu parametre ya da olabilir `CHILDID_SELF` (nesne için Yardım konusunun elde etmek için) veya bir alt kimliği (Yardım konusunun bir alt nesne öğelerini almak için).  
  
 [in] *pidTopic*  
 Tanımlayan `Help` belirtilen nesne ile ilişkili dosya konu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `CBasePane` Bu yöntem uygulamıyor. Bu nedenle, `CBasePane::get_accHelpTopic` her zaman döndürür `S_FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev MFC'de Active Accessibility desteği bir parçasıdır. Bu işlev nesnenizin ilgili Yardım bilgileri sağlamak için bir türetilmiş sınıfta geçersiz kılar.  
  
##  <a name="get_accselection"></a>  CBasePane::get_accSelection  
 Çerçeve, bu nesnenin seçilen alt almak için bu yöntemi çağırır.  
  
```  
virtual HRESULT get_accSelection(VARIANT* pvarChildren);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pvarChildren*  
 Seçili alt tanımlayan bilgileri alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `CBasePane` Bu yöntem uygulamıyor. Varsa *pvarChildren* olan `NULL`, bu yöntem `E_INVALIDARG`. Aksi takdirde, bu yöntemi döndürür `DISP_E_MEMBERNOTFOUND`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev MFC'de Active Accessibility desteği bir parçasıdır. Penceresiz ActiveX denetimlerini dışında pencereli dışı kullanıcı arabirimi öğeleri varsa, bu işlev bir türetilmiş sınıfta geçersiz kılar.  
  
##  <a name="getcaptionheight"></a>  CBasePane::GetCaptionHeight  
 Resim yazısı yükseklik döndürür.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Resim yazısı yüksekliği.  
  
##  <a name="getcontrolbarstyle"></a>  CBasePane::GetControlBarStyle  
 Denetim çubuğu stilini döndürür.  
  
```  
virtual DWORD GetControlBarStyle() const 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 AFX_CBRS_ bayrakları Bitsel veya birleşimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri, aşağıdaki olası değerler birleşimidir.  
  
|Stil|Açıklama|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|Denetim çubuğu float yapar.|  
|`AFX_CBRS_AUTOHIDE`|etkinleştirir otomatik modu gizle.|  
|`AFX_CBRS_RESIZE`|Etkinleştirir denetim çubuğu yeniden boyutlandırma. Bu bayrak ayarlandığında, denetim çubuğu dockable bölmesinde yerleştirilebilir.|  
|`AFX_CBRS_CLOSE`|Denetim çubuğu gizlenmesi etkinleştirir.|  
  
##  <a name="getcurrentalignment"></a>  CBasePane::GetCurrentAlignment  
 Geçerli bölmesinde hizalama döndürür.  
  
```  
virtual DWORD GetCurrentAlignment() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim çubuğu geçerli hizalaması. Olası değerler aşağıdaki tabloda gösterilmektedir:  
  
|Değer|Hizalama|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|Sol hizalaması.|  
|`CBRS_ALIGN_RIGHT`|Sağa hizalama.|  
|`CBRS_ALIGN_TOP`|Üst hizalama.|  
|`CBRS_ALIGN_BOTTOM`|Alt hizalaması.|  
  
##  <a name="getdockingmode"></a>  CBasePane::GetDockingMode  
 Bölmesinde geçerli takma modunun döndürür.  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde sürükleyerek, DT_STANDARD ekranda sürükleyin dikdörtgeni tarafından belirtilir. Bölmenin içeriği sürüklediyseniz DT_IMMEDIATE.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework bölmesinin geçerli yerleştirme modu belirlemek için bu yöntemi çağırır.  
  
 Varsa `CBasePane::m_dockMode` olan yerleştirme modu genel takma modundan alınır (DT_UNDEFINED) undefined ( `AFX_GLOBAL_DATA::m_dockModeGlobal`).  
  
 Ayarlayarak *m_dockMode* veya geçersiz kılma `GetDockingMode` her bölme için takma modu kontrol edebilirsiniz.  
  
##  <a name="getdocksiteframewnd"></a>  CBasePane::GetDockSiteFrameWnd  
 Bir işaretçi döndürür [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)bölmesinde burada yerleştirilmiştir nesnesi.  
  
```  
virtual CWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmenin yerleştirme site için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmenin yerleştirme site için bir işaretçi almak için bu yöntemi çağırın. Yerleştirme site bölmesinde kayan bölmesi ana çerçeve yerleştirilmişse ana çerçeve penceresi ya da bir kısa çerçeve penceresi olabilir.  
  
##  <a name="getenabledalignment"></a>  CBasePane::GetEnabledAlignment  
 Bölmesine uygulanan CBRS_ALIGN_ stiller döndürür.  
  
```  
virtual DWORD GetEnabledAlignment() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 CBRS_ALIGN_ stilleri birleşimi. Aşağıdaki tabloda olası stilleri gösterir:  
  
|Bayrağı|Etkin hizalama|  
|----------|-----------------------|  
|`CBRS_ALIGN_LEFT`|Sol.|  
|`CBRS_ALIGN_RIGHT`|Sağa.|  
|`CBRS_ALIGN_TOP`|Sayfanın Üstü.|  
|`CBRS_ALIGN_BOTTOM`|Alt.|  
|`CBRS_ALIGN_ANY`|Tüm bayraklar birleşimi.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmesinde etkin hizalamasını belirlemek için bu yöntemi çağırın. Etkin hizalama bölme yerleştirilmiş ana çerçeve penceresi yanlarından anlamına gelir.  
  
 Kullanarak yerleştirme hizalama etkinleştirmek [CBasePane::EnableDocking](#enabledocking).  
  
##  <a name="getmfcstyle"></a>  CBasePane::GetMFCStyle  
 MFC için belirli bölmesinde stilleri döndürür.  
  
```  
virtual DWORD GetMFCStyle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kitaplık özgü (AFX_CBRS_) bölmesinde stilleri birleşimi.  
  
##  <a name="getpaneicon"></a>  CBasePane::GetPaneIcon  
 Bir tanıtıcı bölmesinde simgesini döndürür.  
  
```  
virtual HICON GetPaneIcon(BOOL bBigIcon);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bBigIcon*  
 Bir 32 piksel 32 piksel simgesiyle belirtir `TRUE`; 16 piksel 16 piksel simgesiyle belirtir `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde simgesi için bir tanıtıcı. İşlem başarısız olursa, döndürür `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan Uygulama çağrıları [CWnd::GetIcon](../../mfc/reference/cwnd-class.md#geticon).  
  
##  <a name="getpanerow"></a>  CBasePane::GetPaneRow  
 Bir işaretçi döndürür [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)bölmesinde burada yerleştirilmiştir nesnesi.  
  
```  
CDockingPanesRow* GetPaneRow();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `CDockingPanesRow` bölmenin yerleştirilmiş olup olmadığını veya `NULL` , kayan durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 Burada bir bölmesi yuvalanmış satır erişmek için bu yöntemi çağırın. Örneğin, belirli bir satır bölmelerinde düzenlemek için arama `GetPaneRow` ve ardından arama [CDockingPanesRow::ArrangePanes](../../mfc/reference/cdockingpanesrow-class.md#arrangepanes).  
  
##  <a name="getpanestyle"></a>  CBasePane::GetPaneStyle  
 Bölmesinde stili döndürür.  
  
```  
virtual DWORD GetPaneStyle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayarlanan tarafından (CBRS_ stilleri dahil) denetim çubuğu stilleri bileşimini [CBasePane::SetPaneStyle](#setpanestyle) oluşturma zamanında yöntemi.  
  
##  <a name="getparentdocksite"></a>  CBasePane::GetParentDockSite  
 Bir işaretçi üst yerleştirme siteye döndürür.  
  
```  
virtual CDockSite* GetParentDockSite() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üst yerleştirme sitesi.  
  
##  <a name="getparentminiframe"></a>  CBasePane::GetParentMiniFrame  
 Bir işaretçi üst kısa çerçeve pencere döndürür.  
  
```  
virtual CPaneFrameWnd* GetParentMiniFrame(BOOL bNoAssert=FALSE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bNoAssert*  
 Varsa `TRUE`, bu yöntem için geçerli olmayan işaretçileri denetlemez. Uygulamanızı çıktığında bu yöntemini çağırırsanız, bu parametre kümesine `TRUE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde kayan varsa üst kısa çerçeve penceresi için geçerli bir işaretçi; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Üst kısa çerçeve penceresi için bir işaretçi almak için bu işlevini çağırın. Bu yöntem tüm üst ilerler ve bir nesne için denetimleri türetilen [CPaneFrameWnd sınıfı](../../mfc/reference/cpaneframewnd-class.md).  
  
 Kullanım `GetParentMiniFrame` bölmesinde kayan olup olmadığını belirlemek için.  
  
##  <a name="getparenttabbedpane"></a>  CBasePane::GetParentTabbedPane  
 Bir işaretçi üst sekmeli bölmesine döndürür.  
  
```  
CBaseTabbedPane* GetParentTabbedPane() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi varsa üst sekmeli bölmesine; Aksi takdirde `NULL`.  
  
##  <a name="getparenttabwnd"></a>  CBasePane::GetParentTabWnd  
 İçinde bir sekme üst penceresine bir işaretçi döndürür.  
  
```  
CMFCBaseTabCtrl* GetParentTabWnd(HWND& hWndTab) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *hWndTab*  
 Dönüş değeri değilse `NULL`, bu parametre üst sekmeli pencere tanıtıcıyı içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üst için geçerli bir işaretçi sekmeli penceresi veya `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Üst sekmeli pencere bir işaretçi almak için bu işlevi kullanın. Bazen çağırmak yeterli değildir `GetParent`, çünkü bir bölme içinde yerleşik bir sarmalayıcı olabilir ( [CDockablePaneAdapter sınıfı](../../mfc/reference/cdockablepaneadapter-class.md)) veya bir bölmesinde bağdaştırıcısı içinde ( [CDockablePaneAdapter sınıfı](../../mfc/reference/cdockablepaneadapter-class.md)). Kullanarak `GetParentTabWnd` (üst sekmeli bir pencere olduğunu varsayarak) Bu durumlarda geçerli bir işaretçi almak mümkün olacaktır.  
  
##  <a name="getrecentvisiblestate"></a>  CBasePane::GetRecentVisibleState  
 Bir bölme arşivden geri yüklendiğinde framework bu yöntemi çağırır.  
  
```  
virtual BOOL GetRecentVisibleState() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `BOOL` son görünürlük durumunu belirtir. Varsa `TRUE`, bölmesinde görünür serileştirilmiş ve geri görünürken olmalıdır oluştu. Varsa `FALSE`, bölmesinde serileştirilmiş ve geri zaman gizleneceğini gizli.  
  
##  <a name="hideinprintpreviewmode"></a>  CBasePane::HideInPrintPreviewMode  
 Baskı önizlemede bölmenin gizli olup olmadığını belirtir.  
  
```  
virtual BOOL HideInPrintPreviewMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Baskı önizlemede bölmesinde gösterilmez Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel bölmeleri baskı önizlemede gösterilmez. Bu nedenle, bu yöntem her zaman döndürür `TRUE`.  
  
##  <a name="insertpane"></a>  CBasePane::InsertPane  
 Belirtilen bölmesinde takma Yöneticisi ile kaydeder.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pControlBar*  
 Bir işaretçi bölmesine eklemek için.  
  
 [in] *pTarget*  
 Bitişik bölmesi için bir işaretçi.  
  
 [in] *bBu*  
 Varsa `TRUE`, *pControlBar* sonra eklenen *pTarget*. Varsa `FALSE`, *pControlBar* önce eklenen *pTarget*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yöntem başarılı olursa, `FALSE` Aksi takdirde.  
  
##  <a name="isaccessibilitycompatible"></a>  CBasePane::IsAccessibilityCompatible  
 Bölmesinde Active Accessibility destekleyip desteklemediğini belirtir.  
  
```  
virtual BOOL IsAccessibilityCompatible();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Etkin Erişilebilirlik bölmesinde destekliyorsa, Aksi takdirde `FALSE`.  
  
##  <a name="isautohidemode"></a>  CBasePane::IsAutoHideMode  
 Bir bölme otomatik gizleme modunda olup olmadığını belirler.  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde otomatik olarak gizle modundaysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel bölmeleri otomatik gizleme olamaz. Bu yöntem her zaman `FALSE`.  
  
##  <a name="isdialogcontrol"></a>  CBasePane::IsDialogControl  
 Bölmesinde bir iletişim kutusu denetimi olup olmadığını belirtir.  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bir iletişim kutusu denetimi bölmesidir Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçevesi için tüm bölmeleri düzeni tutarlılığını sağlamak için bu yöntemi kullanır.  
  
##  <a name="isdocked"></a>  CBasePane::IsDocked  
 Bölmenin yerleştirilmiş olup olmadığını belirler.  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinin üst bir kısa çerçeve değilse veya başka bir bölmesiyle; kısa bir çerçevede bölmesinde kayan Aksi takdirde `FALSE`.  
  
##  <a name="isfloating"></a>  CBasePane::IsFloating  
 Bölmesinde kayan olup olmadığını belirler.  
  
```  
virtual BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde kayan; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ters değerini döndürür [CBasePane::IsDocked](#isdocked).  
  
##  <a name="ishorizontal"></a>  CBasePane::IsHorizontal  
 Bölmesinin yatay olarak yerleştirilmiş olup olmadığını belirler.  
  
```  
virtual BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde yatay; yerleştirilmişse Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama için geçerli takma hizalama denetler `CBRS_ORIENT_HORZ`.  
  
##  <a name="isinfloatingmultipaneframewnd"></a>  CBasePane::IsInFloatingMultiPaneFrameWnd  
 Bölmesinde çok bölmesi çerçeve penceresinde olup olmadığını belirtir ( [CMultiPaneFrameWnd sınıfı](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bir çok bölmesi çerçeve penceresinde bölmesidir Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca dockable bölmeleri çok bölmesi çerçeve penceresinde float. Bu nedenle, `CBasePane::IsInFloatingMultiPaneFrameWnd` her zaman döndürür `FALSE`.  
  
##  <a name="ismditabbed"></a>  CBasePane::IsMDITabbed  
 MDI alt penceresine sekmeli belge olarak bölmesinde eklenmiş olup olmadığını belirler.  
  
```  
virtual BOOL IsMDITabbed() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde MDI alt penceresine sekmeli belge olarak eklendiyse; Aksi takdirde `FALSE`.  
  
##  <a name="ispanevisible"></a>  CBasePane::IsPaneVisible  
 Belirtir olup olmadığını `WS_VISIBLE` bayrağı bölmesi ayarlanır.  
  
```  
BOOL IsPaneVisible() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` varsa `WS_VISIBLE` ayarlayın; Aksi takdirde, `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CBasePane::IsVisible](#isvisible) bölmesinde görünürlük belirlemek için.  
  
##  <a name="ispointneardocksite"></a>  CBasePane::IsPointNearDockSite  
 Belirli bir noktaya yerleştirme site olup olmadığını belirler.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *noktası*  
 Belirtilen nokta.  
  
 [out] *dwBarAlignment*  
 Hangi uç noktasıdır yakın belirtir. Olası değerler şunlardır: `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP`, ve `CBRS_ALIGN_BOTTOM`  
  
 [out] *bOuterEdge*  
 `TRUE` yerleştirme site dış kenarlık noktasıdır `FALSE` Aksi takdirde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` noktası yerleştirme sitesiyse; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerleştirme Manager'da ayarladığınız duyarlılık içinde olduğunda yerleştirme site noktasıdır. Varsayılan duyarlılık 15 pikseldir.  
  
##  <a name="isresizable"></a>  CBasePane::IsResizable  
 Bölmesinde boyutlandırılabilir olup olmadığını belirler.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde kullanıcı tarafından yeniden boyutlandırılabilir Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmeleri [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md) yeniden boyutlandırılabilir.  
  
 Durum çubuğu ( [CMFCStatusBar sınıfı](../../mfc/reference/cmfcstatusbar-class.md)) ve yerleştirme çubuğu ( [CDockSite sınıfı](../../mfc/reference/cdocksite-class.md)) yeniden boyutlandırılamaz.  
  
##  <a name="isrestoredfromregistry"></a>  CBasePane::IsRestoredFromRegistry  
 Bölmesinde kayıt defterinden geri yüklenip yüklenmeyeceğini belirler.  
  
```  
virtual BOOL IsRestoredFromRegistry() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` kayıt defterinden bölmesinde geri yüklenirse; Aksi takdirde `FALSE`.  
  
##  <a name="istabbed"></a>  CBasePane::IsTabbed  
 Sekmeli penceresinin sekme denetimi bölmesinde eklenmiş olup olmadığını belirler.  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` denetim çubuğu sekmeli bir pencere sekmede eklediyseniz; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, en yakın üst için bir işaretçi alır ve üst öğenin çalışma zamanı sınıf olup olmadığını belirler [CMFCBaseTabCtrl sınıfı](../../mfc/reference/cmfcbasetabctrl-class.md).  
  
##  <a name="isvisible"></a>  CBasePane::IsVisible  
 Bölmesinde görünür olup olmadığını belirler.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde görünür durumdaysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme görünürlüğünü belirlemek için bu yöntemi kullanın. Kullanmayın `::IsWindowVisible`.  
  
 Bölmesinde değil sekmeli (bkz [CBasePane::IsTabbed](#istabbed)), bu yöntem denetler `WS_VISIBLE` stili. Bölmesinde sekmeli bu yöntem üst sekmeli pencere görünürlüğünü denetler. Üst pencere görünür durumdaysa işlevi bölmesinde sekmesini kullanarak görünürlüğü denetler [CMFCBaseTabCtrl::IsTabVisible](../../mfc/reference/cmfcbasetabctrl-class.md#istabvisible).  
  
##  <a name="loadstate"></a>  CBasePane::LoadState  
 Kayıt defterinden Bölmesi'nin durumu yükler.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName=NULL,  
    int nIndex=-1,  
    UINT uiID=(UINT)-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszProfileName*  
 Profil adı.  
  
 [in] *nIndex*  
 Profil dizini.  
  
 [in] *uiID*  
 Bölmesinde kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde durumu başarıyla yüklendiyse; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework kayıt defterinden bölmesinde durumu yüklemek için bu yöntemi çağırır. Tarafından kaydedilen ek bilgileri yüklemek için bir türetilmiş sınıfta geçersiz [CBasePane::SaveState](#savestate).  
  
##  <a name="movewindow"></a>  CBasePane::MoveWindow  
 Bölme taşır.  
  
```  
virtual HDWP MoveWindow(
    CRect& rect,  
    BOOL bRepaint = TRUE,  
    HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rect*  
 Yeni bir konuma ve bölmesinin boyutunu belirleyen bir dikdörtgen.  
  
 [in] *bRepaint*  
 Varsa `TRUE`, bölmesi yeniden çizilmiş. Varsa `FALSE`, bölmesi yeniden çizilmiş değil.  
  
 [in] *hdwp*  
 Ertelenmiş penceresi konumu yapısına işleyin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ertelenmiş penceresi konumu yapısı için bir tanıtıcı veya `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçirirseniz `NULL` olarak *hdwp* parametresi, bu yöntem Pencereyi normal olarak taşır. Bir tanıtıcı geçirirseniz, bu yöntem ertelenmiş penceresi taşıma gerçekleştirir. Çağırarak bir tanıtıcı elde edebileceğiniz [BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672) veya önceki bir çağrı bu yöntemin dönüş değerini depolayarak.  
  
##  <a name="onafterchangeparent"></a>  CBasePane::OnAfterChangeParent  
 Bölmesi'nin üst değiştikten sonra çerçevesi tarafından çağrılır.  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWndOldParent*  
 Önceki üst için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmesi'nin üst, genellikle bir takma veya kayan işlemi nedeniyle değişiklikler sonra framework bu yöntemi çağırır.  
  
 Varsayılan uygulama hiçbir şey yapmaz.  
  
##  <a name="onbeforechangeparent"></a>  CBasePane::OnBeforeChangeParent  
 Yalnızca kendi üst penceresi bölmesinde değiştirmeden önce çerçevesi tarafından çağrılır.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWndNewParent*  
 Yeni bir üst penceresi için bir işaretçi.  
  
 [in] *bDelay*  
 Düzen ayarlamalar Gecikmeli olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework Bölmesi'nin üst değişiklikleri hemen önce bu yöntem genellikle bir yerleştirme, kayan veya otomatik olarak gizle işlemi nedeniyle çağırır.  
  
 Varsayılan uygulama hiçbir şey yapmaz.  
  
##  <a name="ondrawcaption"></a>  CBasePane::OnDrawCaption  
 Resim yazısını çizildiğinde framework bu yöntemi çağırır.  
  
```  
virtual void OnDrawCaption();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem için hiçbir işlevsellik sahip `CBasePane` sınıfı.  
  
##  <a name="onmovepanedivider"></a>  CBasePane::OnMovePaneDivider  
 Bu yöntem şu anda kullanılmaz.  
  
```  
virtual void OnMovePaneDivider(CPaneDivider*);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *CPaneDivider\**  
 Kullanılmadı.  
  
##  <a name="onpanecontextmenu"></a>  CBasePane::OnPaneContextMenu  
 Bölmeleri listesini içeren bir menü oluşturduğunda çerçevesi tarafından çağrılır.  
  
```  
virtual void OnPaneContextMenu(
    CWnd* pParentFrame,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pParentFrame*  
 Üst çerçeve işaretçisi.  
  
 [in] *noktası*  
 Kısayol menüsünün konumunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 `OnPaneContextMenu` Geçerli çerçeve penceresi ait bölmeleri listesini tutar takma yöneticisini çağırır. Bu yöntem bir kısayol menüsü bölmeleri adlarını ekler ve görüntüler. Menü komutlarını göstermek veya tek tek bölmelerini gizleme.  
  
 Bu davranış özelleştirmek için bu yöntemi geçersiz kılın.  
  
##  <a name="onremovefromminiframe"></a>  CBasePane::OnRemoveFromMiniFrame  
 Bir bölme kendi üst mini çerçeve penceresinden kaldırıldığında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnRemoveFromMiniFrame(CPaneFrameWnd* pMiniFrame);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pMiniFrame*  
 Bölmesinde kaldırılmış bir kısa çerçeve penceresi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme (sonucu olarak, örneğin yerleştirme) kendi üst kısa çerçeve penceresi kaldırıldığında framework bu yöntemi çağırır.  
  
 Varsayılan uygulama hiçbir şey yapmaz.  
  
##  <a name="onsetaccdata"></a>  CBasePane::OnSetAccData  
 `CBasePane` Bu yöntem kullanmaz.  
  
```  
virtual BOOL OnSetAccData(long lVal);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lVal*  
 Kullanılmadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem her zaman `TRUE`.  
  
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
 [in] *noktası*  
 Noktası denetlemek için ekran koordinatları olarak belirtir.  
  
 [in] *nSensitivity*  
 Arama alanı bu tarafından artırın. Belirtilen noktasını artan alanında düşerse bir bölmesinde arama ölçütlerini karşılayan.  
  
 [in] *bExactBar*  
 `TRUE` yoksaymak için *nSensitivity* parametresi; Aksi halde, `FALSE`.  
  
 [in] *pRTCBarType*  
 Aksi takdirde `NULL`, yalnızca belirtilen türde bölmeleri yöntemi arar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `CBasePane`-Belirtilen noktasını içeren nesne türetilmiş veya `NULL` hiçbir bölmesinde bulunduysa.  
  
##  <a name="recalclayout"></a>  CBasePane::RecalcLayout  
 `CBasePane` Bu yöntem kullanmaz.  
  
```  
virtual void RecalcLayout();
```  
  
##  <a name="removepanefromdockmanager"></a>  CBasePane::RemovePaneFromDockManager  
 Bir bölme kaydını siler ve yerleştirme Yöneticisi listesinden kaldırır.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pBar,  
    BOOL bDestroy = TRUE,  
    BOOL bAdjustLayout = FALSE,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
 Bir işaretçi bir bölmesine kaldırılacak.  
  
 [in] *bDestroy*  
 Varsa `TRUE`, kaldırılan bölmesinde yok.  
  
 [in] *bAdjustLayout*  
 Varsa `TRUE`, yerleştirme düzenini hemen ayarlayın.  
  
 [in] *bAutoHide*  
 Varsa `TRUE`, yerleştirme düzeni autohide çubukları listesine ilişkilidir. Varsa `FALSE`, yerleştirme düzeni normal bölmeleri listesine ilişkilidir.  
  
 [in] *pBarReplacement*  
 Bir işaretçi bir bölmesine kaldırılan bölmesinde yerini alır.  
  
##  <a name="savestate"></a>  CBasePane::SaveState  
 Kayıt defterine Bölmesi'nin durumunu kaydeder.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName=NULL,  
    int nIndex=-1,  
    UINT uiID=(UINT)-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszProfileName*  
 Profil adı.  
  
 [in] *nIndex*  
 Profil dizini.  
  
 [in] *uiID*  
 Bölmesinde kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` durumu başarıyla kaydedildi Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt defterine Bölmesi'nin durumu kaydettiğinde framework bu yöntemi çağırır. Geçersiz kılma `SaveState` ek bilgileri depolamak için bir türetilmiş sınıfta.  
  
##  <a name="selectdefaultfont"></a>  CBasePane::SelectDefaultFont  
 Verilen cihaz bağlamı için varsayılan yazıtipi seçer.  
  
```  
CFont* SelectDefaultFont(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bir cihaz bağlamı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan bir işaretçi [CFont sınıfı](../../mfc/reference/cfont-class.md) nesnesi.  
  
##  <a name="setcontrolbarstyle"></a>  CBasePane::SetControlBarStyle  
 Denetim çubuğu stilini ayarlar.  
  
```  
virtual void SetControlBarStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwNewStyle*  
 Aşağıdaki olası değerlerin Bitsel veya birleşimi.  
  
|Stil|Açıklama|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|Denetim çubuğu float yapar.|  
|`AFX_CBRS_AUTOHIDE`|etkinleştirir otomatik modu gizle.|  
|`AFX_CBRS_RESIZE`|Etkinleştirir denetim çubuğu yeniden boyutlandırma. Bu bayrak ayarlandığında, denetim çubuğu dockable bölmesinde yerleştirilebilir.|  
|`AFX_CBRS_CLOSE`|Denetim çubuğu gizlenmesi etkinleştirir.|  
  
##  <a name="setdockingmode"></a>  CBasePane::SetDockingMode  
 Bölmenin yerleştirme modunu ayarlar.  
  
```  
void SetDockingMode(AFX_DOCK_TYPE dockModeNew);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dockModeNew*  
 Bölmesinde yeni takma modunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework iki takma modlarını destekler: standard ve hemen.  
  
 Standart takma modda bölmeleri ve kısa çerçeve pencereleri sürükleme dikdörtgen kullanarak geçici taşınır. Hemen yerleştirme modunda, Denetim çubuklarını ve kısa çerçeve pencereleri hemen kendi bağlamla taşınır.  
  
 Başlangıçta, yerleştirme modu genel olarak tanımlanan [CDockingManager::m_dockModeGlobal](../../mfc/reference/cdockingmanager-class.md#m_dockmodeglobal). Yerleştirme modunu kullanarak tek tek her bölme için ayarlayabilirsiniz `SetDockingMode` yöntemi.  
  
##  <a name="setpanealignment"></a>  CBasePane::SetPaneAlignment  
 Bölmenin hizalamasını belirler.  
  
```  
virtual void SetPaneAlignment(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwAlignment*  
 Yeni hizalamasını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, bir bölme başka bir ana çerçeve taraftan yerleştirildiğinde framework bu yöntemi çağırır.  
  
 İçin olası değerler aşağıdaki tabloda gösterilmektedir *dwAlignment*:  
  
|Değer|Hizalama|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|Sol hizalaması.|  
|`CBRS_ALIGN_RIGHT`|Sağa hizalama.|  
|`CBRS_ALIGN_TOP`|Üst hizalama.|  
|`CBRS_ALIGN_BOTTOM`|Alt hizalaması.|  
  
##  <a name="setpanestyle"></a>  CBasePane::SetPaneStyle  
 Bölmesinin stilini ayarlar.  
  
```  
virtual void SetPaneStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwNewStyle*  
 Ayarlanacak yeni stilini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, herhangi bir afxres.h içinde tanımlanan CBRS_ stilleri ayarlamak için kullanılabilir. Bölmesinde stili ve bölmesinde hizalama birlikte depolandığından, geçerli hizalama ile şu şekilde bir araya getirerek yeni stil ayarlayın.  
  
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
 [in] *pWndInsertAfter*  
 Tanımlayan `CWnd` bu önce gelir nesne `CWnd` Z düzenini nesne. Daha fazla bilgi için bkz: [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos).  
  
 [in] *x*  
 Pencerenin sol tarafında konumunu belirtir.  
  
 [in] *y*  
 Pencerenin üstündeki konumunu belirtir.  
  
 [in] *cx*  
 Pencerenin genişliğini belirtir.  
  
 [in] *cy*  
 Pencerenin yüksekliğini belirtir.  
  
 [in] *nFlags*  
 Boyut ve konum seçeneklerini belirtir. Daha fazla bilgi için bkz: [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos).  
  
 [in] *hdwp*  
 Bir veya daha fazla windows boyut ve konum bilgilerini içeren bir yapı için işleyin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir güncelleştirilmiş ertelenmiş penceresi konumu yapısı için bir tanıtıcı veya `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *pWndInsertAfter* olan `NULL`, bu yöntemi çağırır [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos). Varsa *pWndInsertAfter* olan olmayan `NULL`, bu yöntemi çağırır `DeferWindowPos`.  
  
##  <a name="showpane"></a>  CBasePane::ShowPane  
 Bölmesini gösterir veya gizler.  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bBilgi Göster*  
 Gösterilip gösterilmeyeceğini belirler ( `TRUE`) veya gizleme ( `FALSE`) bir bölme.  
  
 [in] *bDelay*  
 Varsa `TRUE`, yerleştirme düzenini yeniden hesaplanması gecikir.  
  
 [in] *bActivate*  
 Varsa `TRUE`, bölmesinde gösterilen etkindir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gösterir veya bir bölmesini gizler. Yerine bu yöntemi kullanmak `ShowWindow` çünkü bu yöntem ilgili takma yöneticileri Bölmesi'nin görünürlük değişiklikleri hakkında bilgilendirir.  
  
 Kullanım [CBasePane::IsVisible](#isvisible) bir bölme geçerli görünürlüğünü belirlemek için.  
  
##  <a name="stretchpane"></a>  CBasePane::StretchPane  
 Dikey veya yatay bölme uzatır.  
  
```  
virtual CSize StretchPane(
    int nLength,  
    BOOL bVert);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nLength*  
 Bölmesinde uzatmak uzunluğu.  
  
 [in] *bVert*  
 Varsa `TRUE`, Bölmesi Dikey olarak esnetin. Varsa `FALSE`, bölmesinin yatay olarak esnetin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Esnetilen bölmesinin boyutunu.  
  
##  <a name="undockpane"></a>  CBasePane::UndockPane  
 Bölmenin yerleştirme site, varsayılan kaydırıcı veya şu anda dayandığı kısa çerçeve penceresi kaldırır.  
  
```  
virtual void UndockPane(BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bDelay*  
 TRUE ise, yerleştirme düzeni hemen hesaplanır değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmesinde durumu işlemek veya takma düzeninden bölmesinde hariç tutmak için bu yöntemi çağırın.  
  
 Bu bölme kullanmaya devam etmek istiyorsanız, ya da çağrısı [CBasePane::DockPane](#dockpane) veya [CBasePane::FloatPane](#floatpane) bu yöntemi çağırmadan önce.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CPane](../../mfc/reference/cbasepane-class.md)   
 [CWnd Sınıfı](../../mfc/reference/cwnd-class.md)
