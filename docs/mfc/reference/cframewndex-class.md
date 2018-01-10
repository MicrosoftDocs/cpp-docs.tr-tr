---
title: "CFrameWndEx sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFrameWndEx
- AFXFRAMEWNDEX/CFrameWndEx
- AFXFRAMEWNDEX/CFrameWndEx::ActiveItemRecalcLayout
- AFXFRAMEWNDEX/CFrameWndEx::AddPane
- AFXFRAMEWNDEX/CFrameWndEx::AdjustDockingLayout
- AFXFRAMEWNDEX/CFrameWndEx::DelayUpdateFrameMenu
- AFXFRAMEWNDEX/CFrameWndEx::DockPane
- AFXFRAMEWNDEX/CFrameWndEx::DockPaneLeftOf
- AFXFRAMEWNDEX/CFrameWndEx::EnableAutoHidePanes
- AFXFRAMEWNDEX/CFrameWndEx::EnableDocking
- AFXFRAMEWNDEX/CFrameWndEx::EnableFullScreenMainMenu
- AFXFRAMEWNDEX/CFrameWndEx::EnableFullScreenMode
- AFXFRAMEWNDEX/CFrameWndEx::EnableLoadDockState
- AFXFRAMEWNDEX/CFrameWndEx::EnablePaneMenu
- AFXFRAMEWNDEX/CFrameWndEx::GetActivePopup
- AFXFRAMEWNDEX/CFrameWndEx::GetDefaultResId
- AFXFRAMEWNDEX/CFrameWndEx::GetDockingManager
- AFXFRAMEWNDEX/CFrameWndEx::GetMenuBar
- AFXFRAMEWNDEX/CFrameWndEx::GetPane
- AFXFRAMEWNDEX/CFrameWndEx::GetRibbonBar
- AFXFRAMEWNDEX/CFrameWndEx::GetTearOffBars
- AFXFRAMEWNDEX/CFrameWndEx::GetToolbarButtonToolTipText
- AFXFRAMEWNDEX/CFrameWndEx::InsertPane
- AFXFRAMEWNDEX/CFrameWndEx::IsFullScreen
- AFXFRAMEWNDEX/CFrameWndEx::IsMenuBarAvailable
- AFXFRAMEWNDEX/CFrameWndEx::IsPointNearDockSite
- AFXFRAMEWNDEX/CFrameWndEx::IsPrintPreview
- AFXFRAMEWNDEX/CFrameWndEx::LoadFrame
- AFXFRAMEWNDEX/CFrameWndEx::NegotiateBorderSpace
- AFXFRAMEWNDEX/CFrameWndEx::OnActivate
- AFXFRAMEWNDEX/CFrameWndEx::OnActivateApp
- AFXFRAMEWNDEX/CFrameWndEx::OnChangeVisualManager
- AFXFRAMEWNDEX/CFrameWndEx::OnClose
- AFXFRAMEWNDEX/CFrameWndEx::OnCloseDockingPane
- AFXFRAMEWNDEX/CFrameWndEx::OnCloseMiniFrame
- AFXFRAMEWNDEX/CFrameWndEx::OnClosePopupMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnCmdMsg
- AFXFRAMEWNDEX/CFrameWndEx::OnContextHelp
- AFXFRAMEWNDEX/CFrameWndEx::OnCreate
- AFXFRAMEWNDEX/CFrameWndEx::OnDestroy
- AFXFRAMEWNDEX/CFrameWndEx::OnDrawMenuImage
- AFXFRAMEWNDEX/CFrameWndEx::OnDrawMenuLogo
- AFXFRAMEWNDEX/CFrameWndEx::OnDWMCompositionChanged
- AFXFRAMEWNDEX/CFrameWndEx::OnExitSizeMove
- AFXFRAMEWNDEX/CFrameWndEx::OnGetMinMaxInfo
- AFXFRAMEWNDEX/CFrameWndEx::OnIdleUpdateCmdUI
- AFXFRAMEWNDEX/CFrameWndEx::OnLButtonDown
- AFXFRAMEWNDEX/CFrameWndEx::OnLButtonUp
- AFXFRAMEWNDEX/CFrameWndEx::OnMenuButtonToolHitTest
- AFXFRAMEWNDEX/CFrameWndEx::OnMenuChar
- AFXFRAMEWNDEX/CFrameWndEx::OnMouseMove
- AFXFRAMEWNDEX/CFrameWndEx::OnMoveMiniFrame
- AFXFRAMEWNDEX/CFrameWndEx::OnNcActivate
- AFXFRAMEWNDEX/CFrameWndEx::OnNcCalcSize
- AFXFRAMEWNDEX/CFrameWndEx::OnNcHitTest
- AFXFRAMEWNDEX/CFrameWndEx::OnNcMouseMove
- AFXFRAMEWNDEX/CFrameWndEx::OnNcPaint
- AFXFRAMEWNDEX/CFrameWndEx::OnPaneCheck
- AFXFRAMEWNDEX/CFrameWndEx::OnPostPreviewFrame
- AFXFRAMEWNDEX/CFrameWndEx::OnPowerBroadcast
- AFXFRAMEWNDEX/CFrameWndEx::OnSetMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnSetPreviewMode
- AFXFRAMEWNDEX/CFrameWndEx::OnSetText
- AFXFRAMEWNDEX/CFrameWndEx::OnShowCustomizePane
- AFXFRAMEWNDEX/CFrameWndEx::OnShowPanes
- AFXFRAMEWNDEX/CFrameWndEx::OnShowPopupMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnSize
- AFXFRAMEWNDEX/CFrameWndEx::OnSizing
- AFXFRAMEWNDEX/CFrameWndEx::OnSysColorChange
- AFXFRAMEWNDEX/CFrameWndEx::OnTearOffMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnToolbarContextMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnToolbarCreateNew
- AFXFRAMEWNDEX/CFrameWndEx::OnToolbarDelete
- AFXFRAMEWNDEX/CFrameWndEx::OnUpdateFrameMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnUpdateFrameTitle
- AFXFRAMEWNDEX/CFrameWndEx::OnUpdatePaneMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnWindowPosChanged
- AFXFRAMEWNDEX/CFrameWndEx::PaneFromPoint
- AFXFRAMEWNDEX/CFrameWndEx::PreTranslateMessage
- AFXFRAMEWNDEX/CFrameWndEx::RecalcLayout
- AFXFRAMEWNDEX/CFrameWndEx::RemovePaneFromDockManager
- AFXFRAMEWNDEX/CFrameWndEx::SetDockState
- AFXFRAMEWNDEX/CFrameWndEx::SetPrintPreviewFrame
- AFXFRAMEWNDEX/CFrameWndEx::SetupToolbarMenu
- AFXFRAMEWNDEX/CFrameWndEx::ShowFullScreen
- AFXFRAMEWNDEX/CFrameWndEx::ShowPane
- AFXFRAMEWNDEX/CFrameWndEx::UpdateCaption
- AFXFRAMEWNDEX/CFrameWndEx::WinHelp
dev_langs: C++
helpviewer_keywords:
- CFrameWndEx [MFC], ActiveItemRecalcLayout
- CFrameWndEx [MFC], AddPane
- CFrameWndEx [MFC], AdjustDockingLayout
- CFrameWndEx [MFC], DelayUpdateFrameMenu
- CFrameWndEx [MFC], DockPane
- CFrameWndEx [MFC], DockPaneLeftOf
- CFrameWndEx [MFC], EnableAutoHidePanes
- CFrameWndEx [MFC], EnableDocking
- CFrameWndEx [MFC], EnableFullScreenMainMenu
- CFrameWndEx [MFC], EnableFullScreenMode
- CFrameWndEx [MFC], EnableLoadDockState
- CFrameWndEx [MFC], EnablePaneMenu
- CFrameWndEx [MFC], GetActivePopup
- CFrameWndEx [MFC], GetDefaultResId
- CFrameWndEx [MFC], GetDockingManager
- CFrameWndEx [MFC], GetMenuBar
- CFrameWndEx [MFC], GetPane
- CFrameWndEx [MFC], GetRibbonBar
- CFrameWndEx [MFC], GetTearOffBars
- CFrameWndEx [MFC], GetToolbarButtonToolTipText
- CFrameWndEx [MFC], InsertPane
- CFrameWndEx [MFC], IsFullScreen
- CFrameWndEx [MFC], IsMenuBarAvailable
- CFrameWndEx [MFC], IsPointNearDockSite
- CFrameWndEx [MFC], IsPrintPreview
- CFrameWndEx [MFC], LoadFrame
- CFrameWndEx [MFC], NegotiateBorderSpace
- CFrameWndEx [MFC], OnActivate
- CFrameWndEx [MFC], OnActivateApp
- CFrameWndEx [MFC], OnChangeVisualManager
- CFrameWndEx [MFC], OnClose
- CFrameWndEx [MFC], OnCloseDockingPane
- CFrameWndEx [MFC], OnCloseMiniFrame
- CFrameWndEx [MFC], OnClosePopupMenu
- CFrameWndEx [MFC], OnCmdMsg
- CFrameWndEx [MFC], OnContextHelp
- CFrameWndEx [MFC], OnCreate
- CFrameWndEx [MFC], OnDestroy
- CFrameWndEx [MFC], OnDrawMenuImage
- CFrameWndEx [MFC], OnDrawMenuLogo
- CFrameWndEx [MFC], OnDWMCompositionChanged
- CFrameWndEx [MFC], OnExitSizeMove
- CFrameWndEx [MFC], OnGetMinMaxInfo
- CFrameWndEx [MFC], OnIdleUpdateCmdUI
- CFrameWndEx [MFC], OnLButtonDown
- CFrameWndEx [MFC], OnLButtonUp
- CFrameWndEx [MFC], OnMenuButtonToolHitTest
- CFrameWndEx [MFC], OnMenuChar
- CFrameWndEx [MFC], OnMouseMove
- CFrameWndEx [MFC], OnMoveMiniFrame
- CFrameWndEx [MFC], OnNcActivate
- CFrameWndEx [MFC], OnNcCalcSize
- CFrameWndEx [MFC], OnNcHitTest
- CFrameWndEx [MFC], OnNcMouseMove
- CFrameWndEx [MFC], OnNcPaint
- CFrameWndEx [MFC], OnPaneCheck
- CFrameWndEx [MFC], OnPostPreviewFrame
- CFrameWndEx [MFC], OnPowerBroadcast
- CFrameWndEx [MFC], OnSetMenu
- CFrameWndEx [MFC], OnSetPreviewMode
- CFrameWndEx [MFC], OnSetText
- CFrameWndEx [MFC], OnShowCustomizePane
- CFrameWndEx [MFC], OnShowPanes
- CFrameWndEx [MFC], OnShowPopupMenu
- CFrameWndEx [MFC], OnSize
- CFrameWndEx [MFC], OnSizing
- CFrameWndEx [MFC], OnSysColorChange
- CFrameWndEx [MFC], OnTearOffMenu
- CFrameWndEx [MFC], OnToolbarContextMenu
- CFrameWndEx [MFC], OnToolbarCreateNew
- CFrameWndEx [MFC], OnToolbarDelete
- CFrameWndEx [MFC], OnUpdateFrameMenu
- CFrameWndEx [MFC], OnUpdateFrameTitle
- CFrameWndEx [MFC], OnUpdatePaneMenu
- CFrameWndEx [MFC], OnWindowPosChanged
- CFrameWndEx [MFC], PaneFromPoint
- CFrameWndEx [MFC], PreTranslateMessage
- CFrameWndEx [MFC], RecalcLayout
- CFrameWndEx [MFC], RemovePaneFromDockManager
- CFrameWndEx [MFC], SetDockState
- CFrameWndEx [MFC], SetPrintPreviewFrame
- CFrameWndEx [MFC], SetupToolbarMenu
- CFrameWndEx [MFC], ShowFullScreen
- CFrameWndEx [MFC], ShowPane
- CFrameWndEx [MFC], UpdateCaption
- CFrameWndEx [MFC], WinHelp
ms.assetid: 5830aca8-4a21-4f31-91f1-dd5477ffcc8d
caps.latest.revision: "39"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b968985c598dafe2ed96295c7388d650dc18c636
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cframewndex-class"></a>CFrameWndEx sınıfı
Implements Windows işlevselliğini tek belge arabirimi (SDI) çakışan veya açılan pencere çerçeve penceresi ve pencere yönetmek için üyeleri sağlar. Bunu genişletir [CFrameWnd](../../mfc/reference/cframewnd-class.md) sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CFrameWndEx : public CFrameWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFrameWndEx::ActiveItemRecalcLayout](#activeitemrecalclayout)|OLE istemci öğesi ve çerçeve istemci alanını düzenini ayarlar.|  
|`CFrameWndEx::AddDockSite`|Bu yöntem kullanılmaz.|  
|[CFrameWndEx::AddPane](#addpane)|Denetim çubuğu yerleştirme Yöneticisi ile kaydeder.|  
|[CFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)|Çerçeve penceresi yerleştirilmiş tüm bölmeleri düzenini yeniden hesaplar.|  
|[CFrameWndEx::DelayUpdateFrameMenu](#delayupdateframemenu)|Çerçeve menüsü ayarlar ve komut işleme boştayken güncelleştirir.|  
|[CFrameWndEx::DockPane](#dockpane)|Belirtilen bölmesinde çerçeve penceresi docks.|  
|[CFrameWndEx::DockPaneLeftOf](#dockpaneleftof)|Başka bir bölme solundaki noktaları bir bölme.|  
|[CFrameWndEx::EnableAutoHidePanes](#enableautohidepanes)|Ana çerçeve penceresi belirtilen kenarlara yerleştirildiğinde bölmeleri için otomatik olarak Gizle modunu etkinleştirir.|  
|[CFrameWndEx::EnableDocking](#enabledocking)|Çerçeve penceresi ait bölmeleri yerleştirme sağlar.|  
|[CFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu)|Gösterir veya gizler ana menü tam ekran modunda.|  
|[CFrameWndEx::EnableFullScreenMode](#enablefullscreenmode)|Çerçeve penceresi için tam ekran modunu etkinleştirir.|  
|[CFrameWndEx::EnableLoadDockState](#enableloaddockstate)|Etkinleştirir veya takma durumunu yüklenmesini devre dışı bırakır.|  
|[CFrameWndEx::EnablePaneMenu](#enablepanemenu)|Etkinleştirir veya bölmesi menüsünde otomatik işlenmesini devre dışı bırakır.|  
|[CFrameWndEx::GetActivePopup](#getactivepopup)|Bir işaretçi şu anda görüntülenen açılır menüyü döndürür.|  
|[CFrameWndEx::GetDefaultResId](#getdefaultresid)|Çerçeve penceresi framework yüklendiğinde, belirttiğiniz kaynak kimliği döndürür.|  
|[CFrameWndEx::GetDockingManager](#getdockingmanager)|Alır [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) çerçeve penceresi için nesnesi.|  
|[CFrameWndEx::GetMenuBar](#getmenubar)|Çerçeve penceresi eklenen menü çubuğu nesnesi için bir işaretçi döndürür.|  
|[CFrameWndEx::GetPane](#getpane)|Belirtilen kimliğe sahip bölmesine bir işaretçi döndürür|  
|[CFrameWndEx::GetRibbonBar](#getribbonbar)|Çerçevesi için Şerit çubuğu denetimi alır.|  
|[CFrameWndEx::GetTearOffBars](#gettearoffbars)|Etiketleri durumda bölmesinde nesnelerin bir listesini döndürür.|  
|[CFrameWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|Araç çubuğu düğmesi için araç ipucu uygulama görüntüler çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::InsertPane](#insertpane)|Bir bölme takma Yöneticisi ile kaydeder.|  
|[CFrameWndEx::IsFullScreen](#isfullscreen)|Çerçeve penceresi tam ekran modunda olup olmadığını belirler.|  
|[CFrameWndEx::IsMenuBarAvailable](#ismenubaravailable)|Menü çubuğu nesnesine işaretçi geçerli olup olmadığını belirler.|  
|[CFrameWndEx::IsPointNearDockSite](#ispointneardocksite)|Noktası hizalama bölgede bulunup bulunmadığını gösterir.|  
|[CFrameWndEx::IsPrintPreview](#isprintpreview)|Çerçeve penceresi baskı önizleme modunda olup olmadığını gösterir.|  
|[CFrameWndEx::LoadFrame](#loadframe)|Bu yöntem, çerçeve penceresi oluşturmak ve kaynaklarını yüklemek için yapım sonra çağrılır.|  
|[CFrameWndEx::NegotiateBorderSpace](#negotiateborderspace)|Implements OLE istemci kenarlık anlaşması.|  
|[CFrameWndEx::OnActivate](#onactivate)|Kullanıcı girişi için veya çerçeve çıktığınızda geçildiğinde framework bu yöntemi çağırır.|  
|[CFrameWndEx::OnActivateApp](#onactivateapp)|Uygulama hem seçilen veya de seçili zaman çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnChangeVisualManager](#onchangevisualmanager)|Çerçeve değişiklik visual Yöneticisi değişiklik gerektirdiğinde çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnClose](#onclose)|Çerçeve çerçeve kapatmak için bu yöntemi çağırır.|  
|[CFrameWndEx::OnCloseDockingPane](#onclosedockingpane)|Kullanıcı tıklattığında çerçevesi tarafından çağrılır **Kapat** takma bölmesindeki düğmesi.|  
|[CFrameWndEx::OnCloseMiniFrame](#oncloseminiframe)|Kullanıcı tıklattığında çerçevesi tarafından çağrılır **Kapat** kayan mini çerçeve penceresi düğmesinde.|  
|[CFrameWndEx::OnClosePopupMenu](#onclosepopupmenu)|Etkin bir açılır menü WM_DESTROY ileti işlediğinde çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnCmdMsg](#oncmdmsg)|Komut iletileri gönderir.|  
|[CFrameWndEx::OnContextHelp](#oncontexthelp)|Çerçevesi tarafından çağrılır içeriği görüntülemek için Yardım ilgili.|  
|[CFrameWndEx::OnCreate](#oncreate)|Çerçeve oluşturulduktan sonra çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnDestroy](#ondestroy)|Çerçeve kaldırıldığı zaman çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnDrawMenuImage](#ondrawmenuimage)|Uygulama Menü öğesiyle ilişkilendirilmiş resim çizer çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|Çerçevesi tarafından çağrılır olduğunda bir `CMFCPopupMenu` nesne işlemleri bir [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) ileti.|  
|[CFrameWndEx::OnDWMCompositionChanged](#ondwmcompositionchanged)|Masaüstü Pencere Yöneticisi (DWM) birleşim etkin veya devre dışı olduğunda çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnExitSizeMove](#onexitsizemove)|Çerçeve taşıma veya yeniden boyutlandırma durduğunda çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnGetMinMaxInfo](#ongetminmaxinfo)|Çerçeve penceresi boyut sınırlarını ayarlamak için boyutlandırıldığında çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnIdleUpdateCmdUI](#onidleupdatecmdui)|Komut işleme boştayken çerçeve görüntü güncelleştirmek için çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnLButtonDown](#onlbuttondown)|Kullanıcı sol fare düğmesini bastığında framework bu yöntemi çağırır.|  
|[CFrameWndEx::OnLButtonUp](#onlbuttonup)|Kullanıcı sol fare düğmesini bıraktığında framework bu yöntemi çağırır.|  
|[CFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|Çerçevesi tarafından çağrılır olduğunda bir `CMFCToolBarButton` nesne işlemleri bir `WM_NCHITTEST` ileti.|  
|[CFrameWndEx::OnMenuChar](#onmenuchar)|Bir menüsü görüntülenir ve kullanıcı bir komuta karşılık gelmiyor bir tuşuna bastığında çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnMouseMove](#onmousemove)|Çerçeve işaretçisi hareket ettiğinde bu yöntemi çağırır.|  
|[CFrameWndEx::OnMoveMiniFrame](#onmoveminiframe)|Bir bölme penceresini taşındığında çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnNcActivate](#onncactivate)|Etkin durumda bir değişikliği göstermek için istemci dışı alan çerçevenin yeniden çizilmesi çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnNcCalcSize](#onnccalcsize)|Boyutunu ve konumunu istemci alanının hesaplanmalıdır çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnNcHitTest](#onnchittest)|İşaretçi geldiğinde veya fare düğmesini basılı veya serbest bırakıldığında çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnNcMouseMove](#onncmousemove)|İşaretçi bir istemci dışı alan geldiğinde çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnNcPaint](#onncpaint)|İstemci dışı alan yeniden boyandığında gerekir çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnPaneCheck](#onpanecheck)|Bir bölme görünürlüğünü denetlemek için çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnPostPreviewFrame](#onpostpreviewframe)|Baskı Önizleme modunu kullanıcı değiştiğinde çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnPowerBroadcast](#onpowerbroadcast)|Güç yönetimi olayı meydana geldiğinde çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnSetMenu](#onsetmenu)|Çerçeve Pencere menüsü değiştirmek için çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnSetPreviewMode](#onsetpreviewmode)|Çerçeve Baskı Önizleme modunu ayarlamak için çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnSetText](#onsettext)|Bir pencere metninin ayarlamak için çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnShowCustomizePane](#onshowcustomizepane)|Bir hızlı özelleştirdiğiniz zaman çerçevesi tarafından çağrılır bölmesinde etkindir.|  
|[CFrameWndEx::OnShowPanes](#onshowpanes)|Bölmeleri göstermek veya gizlemek için çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnShowPopupMenu](#onshowpopupmenu)|Açılır menü etkinleştirildiğinde çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnSize](#onsize)|Çerçeve çerçeve boyutu değiştikten sonra bu yöntemi çağırır.|  
|[CFrameWndEx::OnSizing](#onsizing)|Kullanıcı çerçeve yeniden boyutlandırır zaman çerçevesi bu yöntemi çağırır.|  
|[CFrameWndEx::OnSysColorChange](#onsyscolorchange)|Sistem renkleri değiştiğinde çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnTearOffMenu](#ontearoffmenu)|Etiketleri çubuğu sahip bir menü etkinleştirildiğinde çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnToolbarContextMenu](#ontoolbarcontextmenu)|Bir araç çubuğu bağlam menüsü oluşturmak için çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnToolbarCreateNew](#ontoolbarcreatenew)|Framework'te yeni bir araç çubuğu oluşturmak için bu yöntemi çağırır.|  
|[CFrameWndEx::OnToolbarDelete](#ontoolbardelete)|Araç çubuğu silindiğinde çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnUpdateFrameMenu](#onupdateframemenu)|Çerçeve menüsü Ayarla çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnUpdateFrameTitle](#onupdateframetitle)|Çerçeve çerçeve penceresinin başlık çubuğunu güncelleştirmek için bu yöntemi çağırır.|  
|[CFrameWndEx::OnUpdatePaneMenu](#onupdatepanemenu)|Bölmesi menüsünde güncelleştirmek için çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::OnWindowPosChanged](#onwindowposchanged)|Pencere yönetimi yöntemine yapılan bir çağrı nedeniyle çerçeve boyutu, konum veya z düzeni değiştiğinde çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::PaneFromPoint](#panefrompoint)|Belirtilen nokta içeren takma bölme döndürür.|  
|[CFrameWndEx::PreTranslateMessage](#pretranslatemessage)|Bunlar gönderilir önce belirli bir pencere iletileri işler.|  
|[CFrameWndEx::RecalcLayout](#recalclayout)|Dilimi ve onun alt öğe pencerelerini düzenini ayarlar.|  
|[CFrameWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|Bir bölme kaydını siler ve yerleştirme Yöneticisi'nde dahili listesinden kaldırır.|  
|[CFrameWndEx::SetDockState](#setdockstate)|Yerleştirme düzeni kayıt defterinde depolanan takma durumunu geri yükler.|  
|[CFrameWndEx::SetPrintPreviewFrame](#setprintpreviewframe)|Baskı Önizleme çerçeve penceresi ayarlar.|  
|[CFrameWndEx::SetupToolbarMenu](#setuptoolbarmenu)|Eklemeleri kullanıcı tanımlı komutları bir araç çubuğu menü içine.|  
|[CFrameWndEx::ShowFullScreen](#showfullscreen)|Ana çerçeve tam ekran ve normal modlar arasında geçiş yapar.|  
|[CFrameWndEx::ShowPane](#showpane)|Gösterir veya belirtilen bölmesini gizler.|  
|[CFrameWndEx::UpdateCaption](#updatecaption)|Pencere çerçevesi resim yazısı güncelleştirmek için çerçevesi tarafından çağrılır.|  
|[CFrameWndEx::WinHelp](#winhelp)|Ya da çağırır `WinHelp` uygulama veya bağlam ilgili Yardım.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir sınıftan gösterilmiştir `CFrameWndEx` sınıfı. Örnek alt yöntemi imzalar ve nasıl geçersiz kılınacağını gösterir `OnShowPopupMenu` yöntemi. Bu kod parçacığını parçası olan [Word paneli örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#3](../../mfc/reference/codesnippet/cpp/cframewndex-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad#4](../../mfc/reference/codesnippet/cpp/cframewndex-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CFrameWndEx](../../mfc/reference/cframewndex-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxframewndex.h  
  
##  <a name="activeitemrecalclayout"></a>CFrameWndEx::ActiveItemRecalcLayout  
 OLE istemci öğesi ve çerçeve istemci alanını düzenini ayarlar.  
  
```  
void ActiveItemRecalcLayout();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addpane"></a>CFrameWndEx::AddPane  
 Denetim çubuğu yerleştirme Yöneticisi ile kaydeder.  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pControlBar`  
 Kaydetmek için bir denetim çubuğu bölmesi.  
  
 [in]`bTail`  
 `TRUE`denetim çubuğu bölmesinde listesinin sonuna eklemek istiyorsanız; `FALSE` Aksi takdirde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`denetim çubuğu başarıyla kaydedilir; `FALSE` Aksi takdirde.  
  
##  <a name="adjustdockinglayout"></a>CFrameWndEx::AdjustDockingLayout  
 Çerçeve penceresi yerleştirilmiş tüm bölmeleri düzenini yeniden hesaplar.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `hdwp`  
 Birden çok windows konumlarını içeren bir yapı için bir tanıtıcı. biçimindeki telefon numarasıdır.  
  
### <a name="remarks"></a>Açıklamalar  
 Hdwp yapısı tarafından başlatılan [BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672) yöntemi.  
  
##  <a name="delayupdateframemenu"></a>CFrameWndEx::DelayUpdateFrameMenu  
 Çerçeve menüsü ayarlar ve komut işleme boştayken güncelleştirir.  
  
```  
virtual void DelayUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`hMenuAlt`  
 Bir alternatif menüsüne işleyin.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="dockpane"></a>CFrameWndEx::DockPane  
 Belirtilen bölmesinde çerçeve penceresi docks.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID=0,  
    LPCRECT lpRect=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 Denetim çubuğu yerleşik için bir işaretçi.  
  
 [in]`nDockBarID`  
 Çerçeve penceresi için sabitlemek için tarafında kimliği.  
  
 [in]`lpRect`  
 Pencerenin ekran konumunu ve boyutunu belirtir sabit bir Rect yapısı için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 `nDockBarID` Parametresi şu değerlerden biri olabilir:  
  
-   AFX_IDW_DOCKBAR_TOP  
  
-   AFX_IDW_DOCKBAR_BOTTOM  
  
-   AFX_IDW_DOCKBAR_LEFT  
  
-   AFX_IDW_DOCKBAR_RIGHT  
  
##  <a name="dockpaneleftof"></a>CFrameWndEx::DockPaneLeftOf  
 Belirtilen bölmesinde başka bir bölme soluna docks.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 Yerleşik için bölmesi nesnesi için bir işaretçi.  
  
 [in]`pLeftOf`  
 Biri tarafından belirtilen bölmesinde sabitlemek sol bölmesinde bir işaretçi `pBar`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`varsa `pBar` başarıyla yerleştirilir. `FALSE`Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem tarafından belirtilen araç alır `pBar` parametre ve araç sol tarafındaki belirtilen tarafından noktalarını `pLeftOf` parametresi.  
  
##  <a name="enableautohidepanes"></a>CFrameWndEx::EnableAutoHidePanes  
 Etkinleştirir otomatik modu bölmesi için belirtilen ana çerçeve penceresi tarafına yerleştirildiğinde gizle.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`dwDockStyle`  
 Bölmesinde sabitlemek ana çerçeve penceresine tarafında belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bir çubuk bölmesi tarafından belirtilen çerçeve penceresi dışarıdan yuvalanmış başarıyla `dwDockStyle`, `FALSE` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 `dwDockStyle`Aşağıdaki değerlerden biri olabilir:  
  
-   CBRS_ALIGN_TOP: bir çerçeve penceresinde istemci alanının üstüne yerleştirilmiş denetim çubuğu sağlar.  
  
-   CBRS_ALIGN_BOTTOM: bir çerçeve penceresinde istemci alanını altına yerleştirilmiş denetim çubuğu sağlar.  
  
-   CBRS_ALIGN_LEFT: istemci alanını bir çerçeve penceresinin sol tarafındaki için yerleşik denetim çubuğu sağlar.  
  
-   CBRS_ALIGN_RIGHT: istemci alanını bir çerçeve penceresinin sağ tarafındaki yerleşik denetim çubuğu sağlar.  
  
##  <a name="enabledocking"></a>CFrameWndEx::EnableDocking  
 Çerçeve pencere bölmeleri yerleştirme sağlar.  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`dwDockStyle`  
 Burada bölmesinde çubuğu noktalarını ana çerçeve penceresi tarafında belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bir çubuk bölmesi başarıyla yuvalanmış belirtilen tarafında. `FALSE`Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 `dwDockStyle` Parametresi şu değerlerden biri olabilir:  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="enablefullscreenmainmenu"></a>CFrameWndEx::EnableFullScreenMainMenu  
 Gösterir veya gizler ana menü tam ekran modunda.  
  
```  
void EnableFullScreenMainMenu(BOOL bEnableMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnableMenu`  
 `TRUE`tam ekran modunda ana menüye göstermek için `FALSE` Aksi takdirde.  
  
##  <a name="enablefullscreenmode"></a>CFrameWndEx::EnableFullScreenMode  
 Çerçeve penceresi için tam ekran modunu etkinleştirir.  
  
```  
void EnableFullScreenMode(UINT uiFullScreenCmd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiFullScreenCmd`  
 Sağlar ve tam ekran modu devre dışı bırakan bir komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Tam ekran modunda tüm yerleştirme denetim çubukları, araç çubukları ve menü gizlidir ve etkin görünüm tam ekran kaplayacak şekilde yeniden boyutlandırılır.  
  
 Tam ekran moduna etkinleştirdiğinizde, etkinleştirir veya devre dışı bırakır tam ekran moduna komut kimliği belirtmelisiniz. Çağırabilirsiniz `EnableFullScreenMode` ana çerçeve gelen `OnCreate` işlevi. Bir çerçeve penceresinde bir tam ekran moduna geçiş, framework kayan araç çubuğunu belirtilen komut kimliğe sahip bir düğmesi ile oluşturur.  
  
 Ana menü ekranda tutmak istiyorsanız, çağrı [CFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu).  
  
##  <a name="enableloaddockstate"></a>CFrameWndEx::EnableLoadDockState  
 Etkinleştirir veya takma durumunu yüklenmesini devre dışı bırakır.  
  
```  
void EnableLoadDockState(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
 `TRUE`Yuva durumu yüklenmesini etkinleştirmek için `FALSE` takma durumunu yüklenmesini devre dışı bırakmak için.  
  
##  <a name="enablepanemenu"></a>CFrameWndEx::EnablePaneMenu  
 Etkinleştirir veya bölmesi menüsünde otomatik işlenmesini devre dışı bırakır.  
  
```  
void EnablePaneMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeLabel,  
    UINT uiViewToolbarsMenuEntryID,  
    BOOL bContextMenuShowsToolbarsOnly=FALSE,  
    BOOL bViewMenuShowsToolbarsOnly=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
 `TRUE`açılır menüler çubuğu denetiminin otomatik işleme etkinleştirmek için; `FALSE` otomatik işleme açılır menüler çubuğu denetiminin devre dışı bırakmak için.  
  
 [in]`uiCustomizeCmd`  
 Komut Kimliği **Özelleştir** menü öğesi.  
  
 [in]`strCustomizeLabel`  
 Etiketi için görüntülenecek **Özelleştir** menü öğesi  
  
 [in]`uiViewToolbarsMenuEntryID`  
 Denetim çubuğu açılır menüyü açılır bir araç çubuğu menü öğesi kimliği.  
  
 [in]`bContextMenuShowsToolbarsOnly`  
 Varsa `TRUE`, bağlam menüsü çubuğu Denetim araç çubukları yalnızca listesini görüntüler. Varsa `FALSE`, menü araç çubukları ve yerleştirme çubukları listesini görüntüler.  
  
 [in]`bViewMenuShowsToolbarsOnly`  
 Varsa `TRUE`, denetim çubuğu menüsünde araç çubukları yalnızca listesini görüntüler. Varsa `FALSE`, menü araç çubukları ve yerleştirme çubukları listesini görüntüler.  
  
##  <a name="getactivepopup"></a>CFrameWndEx::GetActivePopup  
 Bir işaretçi şu anda görüntülenen açılır menüyü döndürür.  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda görüntülenen açılır menüde bir işaretçi; Aksi takdirde `NULL`.  
  
##  <a name="getdefaultresid"></a>CFrameWndEx::GetDefaultResId  
 Çerçeve penceresi framework yüklendiğinde, belirttiğiniz kaynak kimliği döndürür.  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı ne zaman framework çerçeve penceresi yüklenen belirtilen kaynak kimliği değeri. Çerçeve penceresi menü çubuğu yoksa sıfır.  
  
##  <a name="getdockingmanager"></a>CFrameWndEx::GetDockingManager  
 Alır [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) çerçeve penceresi için nesnesi.  
  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve penceresi oluşturduğu ve kullandığı bir [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) alt yerleştirme penceresi yönetmek için nesnesi.  
  
##  <a name="getmenubar"></a>CFrameWndEx::GetMenuBar  
 Çerçeve penceresi eklenen menü çubuğu nesnesi için bir işaretçi döndürür.  
  
```  
const CMFCMenuBar* GetMenuBar() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çerçeve penceresi eklenen menü çubuğu nesnesi için bir işaretçi.  
  
##  <a name="getpane"></a>CFrameWndEx::GetPane  
 Belirtilen kimliğe sahip bölmesine bir işaretçi döndürür  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nID`  
 Denetim kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen kimliğe sahip bölmesi için bir işaretçi `NULL`Bu tür bir bölmesinde varsa.  
  
##  <a name="getribbonbar"></a>CFrameWndEx::GetRibbonBar  
 Çerçevesi için Şerit çubuğu denetimi alır.  
  
```  
CMFCRibbonBar* GetRibbonBar();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi [CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md) çerçevesi için.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gettearoffbars"></a>CFrameWndEx::GetTearOffBars  
 Etiketleri durumda bölmesinde nesnelerin bir listesini döndürür.  
  
```  
const CObList& GetTearOffBars() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru `CObList` etiketleri durumda bölmesinde nesnelerine işaretçiler koleksiyonunu içeren nesne.  
  
##  <a name="gettoolbarbuttontooltiptext"></a>CFrameWndEx::GetToolbarButtonToolTipText  
 Araç çubuğu düğmesi için araç ipucu uygulama görüntüler çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton* pButton,  
    CString& strTTText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pButton`  
 Araç çubuğu düğmesi için bir işaretçi.  
  
 [in]`strTTText`  
 Düğme için görüntülenecek araç ipucu metni.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Araç İpucu gösterilmesi gerekiyorsa. `FALSE`Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem hiçbir şey yapmaz. Araç çubuğu düğmesi için araç ipucu görüntülemek istiyorsanız bu yöntemi geçersiz kılın.  
  
##  <a name="insertpane"></a>CFrameWndEx::InsertPane  
 Bölme denetim çubukları listesine ekler ve yerleştirme Yöneticisi ile kaydeder.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pControlBar`  
 Denetim çubuğu denetim çubukları listesine eklenir ve yerleştirme Yöneticisi ile kayıtlı olması için bir işaretçi.  
  
 `pTarget`  
 Denetim çubuğu öncesinde veya sonrasında bölmesi eklemek bir işaretçi.  
  
 `bAfter`  
 `TRUE`eklemek istiyorsanız `pControlBar` sonra `pTarget`, `FALSE` Aksi takdirde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`denetim çubuğu ise başarıyla eklendi ve kayıtlı `FALSE` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanarak her denetim çubuğu kaydolmalıdır [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) takma düzende katılmak için.  
  
##  <a name="isfullscreen"></a>CFrameWndEx::IsFullScreen  
 Çerçeve penceresi tam ekran modunda olup olmadığını belirler.  
  
```  
BOOL IsFullScreen() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`çerçeve penceresi tam ekran modunda değilse; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Tam ekran moduna çağırarak ayarlayabileceğiniz [CFrameWndEx::EnableFullScreenMode](#enablefullscreenmode) yöntemi.  
  
##  <a name="ismenubaravailable"></a>CFrameWndEx::IsMenuBarAvailable  
 Menü çubuğu nesnesine işaretçi geçerli olup olmadığını belirler.  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`çerçeve penceresi menü çubuğu varsa; Aksi takdirde `FALSE`.  
  
##  <a name="ispointneardocksite"></a>CFrameWndEx::IsPointNearDockSite  
 Noktası hizalama bölgede bulunup bulunmadığını belirler.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`point`  
 Noktasının konumu.  
  
 [out]`dwBarAlignment`  
 Burada noktası hizalanır. Olası değerler için açıklamalar bölümündeki tabloya bakın.  
  
 [out]`bOuterEdge`  
 `TRUE`Çerçeve kenarlığı yakın noktası bulunuyorsa; `FALSE` noktası istemci alanında bulunuyorsa.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`noktası hizalama bölgesinde bulunuyorsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin olası değerler aşağıdaki tabloda listelenmektedir `dwBarAlignment` parametresi.  
  
 `CBRS_ALIGN_TOP`  
 Üste hizalı.  
  
 `CBRS_ALIGN_RIGHT`  
 Sağa hizalı.  
  
 `CBRS_ALIGN_BOTTOM`  
 En Alta Hizala.  
  
 `CBRS_ALIGN_LEFT`  
 Sola hizalı.  
  
##  <a name="isprintpreview"></a>CFrameWndEx::IsPrintPreview  
 Çerçeve penceresi baskı önizleme modunda olup olmadığını belirler.  
  
```  
BOOL IsPrintPreview();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`çerçeve penceresi baskı önizleme modunda değilse; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="loadframe"></a>CFrameWndEx::LoadFrame  
 Bu yöntem, çerçeve penceresi oluşturmak ve kaynaklarını yüklemek için yapım sonra çağrılır.  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nIDResource`  
 Tüm çerçeve kaynakları yüklemek için kullanılan kaynak kimliği.  
  
 [in]`dwDefaultStyle`  
 Varsayılan çerçeve pencere stili.  
  
 [in]`pParentWnd`  
 Üst pencere çerçeve işaretçisi.  
  
 [in]`pContext`  
 İşaretçi bir [CCreateContext yapısı](../../mfc/reference/ccreatecontext-structure.md) çerçevesi tarafından uygulama oluşturma sırasında kullanılan sınıfı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="negotiateborderspace"></a>CFrameWndEx::NegotiateBorderSpace  
 Implements OLE istemci kenarlık anlaşması.  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nBorderCmd`  
 Kenarlık anlaşma komutu. Olası değerler için Açıklamalar bölümüne bakın.  
  
 [içinde out]`lpRectBorder`  
 Kenarlığın boyutları.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Düzen hesaplanmalıdır Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin olası değerler aşağıdaki tabloda listelenmektedir `nBorderCmd` parametresi.  
  
 `borderGet`  
 OLE istemci yer alır.  
  
 `borderRequest`  
 OLE istemci alanı isteyin.  
  
 `borderSet`  
 OLE istemci alanı ayarlayın.  
  
##  <a name="onactivate"></a>CFrameWndEx::OnActivate  
 Kullanıcı girişi için veya çerçeve çıktığınızda geçildiğinde framework bu yöntemi çağırır.  
  
```  
afx_msg void OnActivate(
    UINT nState,  
    CWnd* pWndOther,  
    BOOL bMinimized);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nState`  
 Çerçeve etkin veya devre dışı olup olmadığı. Olası değerler için açıklamalar bölümündeki tabloya bakın.  
  
 [in]`pWndOther`  
 Geçerli bir kullanıcı girişi geçiş başka bir pencere için işaretçi.  
  
 [in]`bMinimized`  
 Çerçeve simge durumuna küçültülmüş durumu. `TRUE`Çerçeve küçültülmüş; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin olası değerler aşağıdaki tabloda listelenmektedir `nState` parametresi.  
  
 `WA_ACTIVE`  
 Çerçeve fare dışında bir yöntem olarak seçilidir.  
  
 `WA_CLICKACTIVE`  
 Çerçeve bir fare tıklatma tarafından seçilir.  
  
 `WA_INACTIVE`  
 Çerçeve seçilmedi.  
  
##  <a name="onactivateapp"></a>CFrameWndEx::OnActivateApp  
 Uygulama hem seçilen veya de seçili zaman çerçevesi tarafından çağrılır.  
  
```  
afx_msg void OnActivateApp(
    BOOL bActive,  
    DWORD dwThreadID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bActive`  
 `TRUE`Uygulama seçtiyseniz; `FALSE` uygulama seçili değilse.  
  
 [in]`dwThreadID`  
 Bu parametre kullanılmaz.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onchangevisualmanager"></a>CFrameWndEx::OnChangeVisualManager  
 Çerçeve değişiklik visual Yöneticisi değişiklik gerektirdiğinde çerçevesi tarafından çağrılır.  
  
```  
afx_msg LRESULT OnChangeVisualManager(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`wParam`  
 Bu parametre kullanılmaz.  
  
 [in]`lParam`  
 Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 0 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onclose"></a>CFrameWndEx::OnClose  
 Çerçeve çerçeve kapatmak için bu yöntemi çağırır.  
  
```  
afx_msg void OnClose();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Baskı Önizleme modunda çerçeve baskı önizlemeyi kapatmak için Windows ileti gönderir; Aksi takdirde, çerçeve OLE istemci barındırıyorsa, istemci devre dışı bırakılır.  
  
##  <a name="onclosedockingpane"></a>CFrameWndEx::OnCloseDockingPane  
 Kullanıcı tıklattığında çerçevesi tarafından çağrılır **Kapat** takma bölmesindeki düğmesi.  
  
```  
virtual BOOL OnCloseDockingPane(CDockablePane* pPane);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yerleştirme çubuğu kapatılabilir durumunda. `FALSE`Aksi takdirde  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama hiçbir şey yapmaz. Yerleştirme çubuğu gizleme işlemek istiyorsanız bu yöntemi geçersiz kılın.  
  
##  <a name="oncloseminiframe"></a>CFrameWndEx::OnCloseMiniFrame  
 Kullanıcı tıklattığında çerçevesi tarafından çağrılır **Kapat** kayan mini çerçeve penceresi düğmesinde.  
  
```  
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bir kayan mini çerçeve penceresi kapatılabilir. `FALSE`Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama hiçbir şey yapmaz. Kayan mini çerçeve penceresi gizleme işlemek istiyorsanız bu yöntemi geçersiz kılın.  
  
##  <a name="onclosepopupmenu"></a>CFrameWndEx::OnClosePopupMenu  
 Etkin bir açılır menü WM_DESTROY ileti işlediğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>Parametreler  
 `pMenuPopup`  
 Açılır menü için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yaklaşık pencereyi kapatmak için olduğunda framework WM_DESTROY ileti gönderir. Bildirimler işlemek istiyorsanız bu yöntemi geçersiz kılın `CMFCPopupMenu` çerçeve penceresi ait nesneleri olduğunda bir `CMFCPopupMenu` nesnesini işleyen bir `WM_DESTROY` Pencere kapatıldığında çerçevesi tarafından gönderilen ileti.  
  
##  <a name="oncmdmsg"></a>CFrameWndEx::OnCmdMsg  
 Komut iletileri gönderir.  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nID`  
 Komut kimliği.  
  
 [in]`nCode`  
 Komut iletisi kategorisi.  
  
 [içinde out]`pExtra`  
 Komut nesnesi için işaretçi.  
  
 [içinde out]`pHandlerInfo`  
 Bir komut işleyici yapısına yönelik işaretçinin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`komut iletisi işlendi Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="oncontexthelp"></a>CFrameWndEx::OnContextHelp  
 Bağlamı ile ilgili Yardım görüntülemek üzere çerçevesi tarafından çağrılır.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="oncreate"></a>CFrameWndEx::OnCreate  
 Çerçeve oluşturulduktan sonra çerçevesi tarafından çağrılır.  
  
```  
afx_msg int OnCreate(LPCREATESTRUCT lpCreateStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpCreateStruct`  
 Bir işaretçi [CREATESTRUCT yapısı](../../mfc/reference/createstruct-structure.md) için yeni bir çerçeve.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çerçeve oluşturma işlemiyle devam etmek 0; çerçeve yok etmek için -1.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondestroy"></a>CFrameWndEx::OnDestroy  
 Çerçeve kaldırıldığı zaman çerçevesi tarafından çağrılır.  
  
```  
afx_msg void OnDestroy();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Hızlandırıcı tablosunu ve tüm pencereleri yok.  
  
##  <a name="ondrawmenuimage"></a>CFrameWndEx::OnDrawMenuImage  
 Uygulama Menü öğesiyle ilişkilendirilmiş resim çizer çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnDrawMenuImage(
    CDC* pDC,  
    const CMFCToolBarMenuButton* pMenuButton,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in]`pMenuButton`  
 Görüntü işlenen bir menü düğmesi için bir işaretçi.  
  
 [in]`rectImage`  
 Bir işaretçi bir `Rect` yapısı görüntünün boyutu ve ekran konumunu belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`framework başarıyla görüntü oluşturursa; `FALSE` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Görüntü işleme ait menü çubuğu ait menü öğeleri için özelleştirmek istiyorsanız bu yöntemi geçersiz kılın `CFrameWndEx` türetilmiş bir nesne içermelidir.  
  
##  <a name="ondrawmenulogo"></a>CFrameWndEx::OnDrawMenuLogo  
 Çerçevesi tarafından çağrılır olduğunda bir `CMFCPopupMenu` nesnesini WM_PAINT ileti işler.  
  
```  
virtual void OnDrawMenuLogo(
    CDC* pDC,  
    CMFCPopupMenu* pMenu,  
    const CRect& rectLogo);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in]`pMenu`  
 Menü öğesi için bir işaretçi.  
  
 [in]`rectLogo`  
 Bir sabit başvuru `CRect` yapısı menü logosu boyutunu ve ekran konumunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Sahibi menü çubuğu ait açılır menüsünde logosunu istiyorsanız, bu işlevi geçersiz kılma `CFrameWndEx` türetilmiş bir nesne içermelidir.  
  
##  <a name="ondwmcompositionchanged"></a>CFrameWndEx::OnDWMCompositionChanged  
 Masaüstü Pencere Yöneticisi (DWM) birleşim etkin veya devre dışı olduğunda çerçevesi tarafından çağrılır.  
  
```  
afx_msg LRESULT OnDWMCompositionChanged(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`wp`  
 Bu parametre kullanılmaz.  
  
 [in]`lp`  
 Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 0 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onexitsizemove"></a>CFrameWndEx::OnExitSizeMove  
 Çerçeve taşıma veya yeniden boyutlandırma durduğunda çerçevesi tarafından çağrılır.  
  
```  
LRESULT OnExitSizeMove(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`wp`  
 Bu parametre kullanılmaz.  
  
 [in]`lp`  
 Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 0 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ongetminmaxinfo"></a>CFrameWndEx::OnGetMinMaxInfo  
 Çerçeve penceresi boyut sınırlarını ayarlamak için boyutlandırıldığında çerçevesi tarafından çağrılır.  
  
```  
afx_msg void OnGetMinMaxInfo(MINMAXINFO FAR* lpMMI);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpMMI`  
 İşaretçi bir [MINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632605) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onidleupdatecmdui"></a>CFrameWndEx::OnIdleUpdateCmdUI  
 Komut işleme boştayken çerçeve görüntü güncelleştirmek için çerçevesi tarafından çağrılır.  
  
```  
afx_msg LRESULT OnIdleUpdateCmdUI(
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`wParam`  
 Bu parametre kullanılmaz.  
  
 [in]`lParam`  
 Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 0 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onlbuttondown"></a>CFrameWndEx::OnLButtonDown  
 Kullanıcı sol fare düğmesini bastığında framework bu yöntemi çağırır.  
  
```  
afx_msg void OnLButtonDown(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nFlags`  
 Kullanıcı değiştirici tuşları basılı olup olmadığını gösterir. Olası değerler için parametre bkz `wParam` içinde [WM_LBUTTONDOWN bildirim](http://msdn.microsoft.com/library/windows/desktop/ms645607).  
  
 [in]`point`  
 X ve y koordinatları işaretçinin, pencerenin sol üst köşesindeki göreli belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onlbuttonup"></a>CFrameWndEx::OnLButtonUp  
 Kullanıcı sol fare düğmesini bıraktığında framework bu yöntemi çağırır.  
  
```  
afx_msg void OnLButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nFlags`  
 Kullanıcı değiştirici tuşları basılı olup olmadığını gösterir. Olası değerler için parametre bkz `wParam` içinde [WM_LBUTTONUP bildirim](http://msdn.microsoft.com/library/windows/desktop/ms645608).  
  
 [in]`point`  
 X ve y koordinatları işaretçinin, pencerenin sol üst köşesindeki göreli belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onmenubuttontoolhittest"></a>CFrameWndEx::OnMenuButtonToolHitTest  
 Çerçevesi tarafından çağrılır olduğunda bir `CMFCToolBarButton` nesne işlemleri bir `WM_NCHITTEST` ileti.  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pButton`  
 Araç çubuğu düğmesi için bir işaretçi.  
  
 [out]`pTI`  
 Bir aracı bilgi yapısı için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`uygulama doldurur, `pTI` parametresi. `FALSE`Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli menü öğesi araç ipucu bilgilerini sağlamak istiyorsanız bu yöntemi geçersiz kılın.  
  
##  <a name="onmenuchar"></a>CFrameWndEx::OnMenuChar  
 Bir menüsü görüntülenir ve kullanıcı bir komuta karşılık gelmiyor bir tuşuna bastığında çerçevesi tarafından çağrılır.  
  
```  
afx_msg LRESULT OnMenuChar(
    UINT nChar,  
    UINT nFlags,  
    CMenu* pMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nChar`  
 Tuş karakter kodu.  
  
 [in]`nFlags`  
 İçeren `MF_POPUP` bayrağı görüntülenen menüsünün alt; ise içerir `MF_SYSMENU` görüntülenen menü Denetim menüsü ise bayrak.  
  
 [in]`pMenu`  
 Bir menüye işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yüksek düzey sözcük aşağıdaki değerlerden biri olmalıdır.  
  
 `0`  
 Framework tuş vuruşu yok saymanız gerekir.  
  
 `1`  
 Framework menü kapatmanız gerekir.  
  
 `2`  
 Framework menüsünde görüntülenen öğelerden birini seçmeniz gerekir. Düşük düzey word seçmek için komut Kimliğini içerir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onmousemove"></a>CFrameWndEx::OnMouseMove  
 Çerçeve işaretçisi hareket ettiğinde bu yöntemi çağırır.  
  
```  
afx_msg void OnMouseMove(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nFlags`  
 Bir kullanıcı değiştirici tuşları basılı olup olmadığını gösterir. Olası değerler için parametre bkz `wParam` içinde [WM_MOUSEMOVE bildirim](http://msdn.microsoft.com/library/windows/desktop/ms645616).  
  
 [in]`point`  
 X ve y belirtir işaretçiyi pencerenin sol üst köşesindeki göre koordinatları.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onmoveminiframe"></a>CFrameWndEx::OnMoveMiniFrame  
 Bir bölme penceresini taşındığında çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pFrame`  
 İşaretçi [CPaneFrameWnd sınıfı](../../mfc/reference/cpaneframewnd-class.md) Bölmesi penceresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bölme penceresini yerleştirilmemişse; `FALSE` bölme penceresini yerleşik durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onncactivate"></a>CFrameWndEx::OnNcActivate  
 Etkin durumda bir değişikliği göstermek için istemci dışı alan çerçevenin yeniden çizilmesi çerçevesi tarafından çağrılır.  
  
```  
afx_msg BOOL OnNcActivate(BOOL bActive);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bActive`  
 `TRUE`Etkin çerçeve çizmek için; `FALSE` etkin olmayan çerçeve çizmek için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan işleme devam etmek için sıfır olmayan; devre dışı bırakılan istemci dışı alan engellemek için 0'ı tıklatın.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onnccalcsize"></a>CFrameWndEx::OnNcCalcSize  
 Boyutunu ve konumunu istemci alanının hesaplanmalıdır çerçevesi tarafından çağrılır.  
  
```  
afx_msg void OnNcCalcSize(
    BOOL bCalcValidRects,  
    NCCALCSIZE_PARAMS FAR* lpncsp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bCalcValidRects`  
 `TRUE`olduğunda uygulamanın geçerli istemci alanını belirtmesi gerekir; Aksi takdirde `FALSE`.  
  
 [in]`lpncsp`  
 İşaretçi bir `NCCALCSIZE_PARAMS` çerçeve boyut değişiklikleri içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onnchittest"></a>CFrameWndEx::OnNcHitTest  
 İşaretçi geldiğinde veya fare düğmesini basılı veya serbest bırakıldığında çerçevesi tarafından çağrılır.  
  
```  
afx_msg LRESULT OnNcHitTest(CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`point`  
 Ekran koordinatları işaretçinin konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi Enum değeri ulaştı. Olası değerler listesi için bkz: [WM_NCHITTEST bildirim](http://msdn.microsoft.com/library/windows/desktop/ms645618).  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onncmousemove"></a>CFrameWndEx::OnNcMouseMove  
 İşaretçi bir istemci dışı alan geldiğinde çerçevesi tarafından çağrılır.  
  
```  
afx_msg void OnNcMouseMove(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nHitTest`  
 Bir işaretçi Enum değeri ulaştı. Olası değerler listesi için bkz: [WM_NCHITTEST bildirim](http://msdn.microsoft.com/library/windows/desktop/ms645618).  
  
 [in]`point`  
 Ekran koordinatları işaretçinin konumu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onncpaint"></a>CFrameWndEx::OnNcPaint  
 İstemci dışı alan yeniden boyandığında gerekir çerçevesi tarafından çağrılır.  
  
```  
afx_msg void OnNcPaint();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onpanecheck"></a>CFrameWndEx::OnPaneCheck  
 Bir bölme görünürlüğünü denetlemek için çerçevesi tarafından çağrılır.  
  
```  
afx_msg BOOL OnPaneCheck(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nID`  
 Bölme denetim kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`komutu işlendi `FALSE` komut işleme devam etmek için.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onpostpreviewframe"></a>CFrameWndEx::OnPostPreviewFrame  
 Kullanıcı Baskı Önizleme modunu değiştirdiğinde çerçevesi tarafından çağrılır.  
  
```  
afx_msg LRESULT OnPostPreviewFrame(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`wParam`  
 Bu parametre kullanılmaz.  
  
 [in]`lParam`  
 `TRUE`Çerçeve baskı önizleme modunda olduğunda; `FALSE` Baskı Önizleme modunu devre dışı olduğunda.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 0 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onpowerbroadcast"></a>CFrameWndEx::OnPowerBroadcast  
 Güç yönetimi olayı meydana geldiğinde çerçevesi tarafından çağrılır.  
  
```  
afx_msg LRESULT OnPowerBroadcast(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`wp`  
 Güç yönetimi olayı. Olası değerler listesi için bkz: [WM_POWERBROADCAST ileti](http://msdn.microsoft.com/library/windows/desktop/aa373247).  
  
 [in]`lp`  
 Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan pencere yordamı çağırma sonucu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsetmenu"></a>CFrameWndEx::OnSetMenu  
 Çerçeve Pencere menüsü değiştirmek için çerçevesi tarafından çağrılır.  
  
```  
afx_msg LRESULT OnSetMenu(
    WPARAM wp,  
    LPARAM lp);  
  
BOOL OnSetMenu(HMENU hmenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`wp`  
 Yeni çerçeve penceresi menüsüne işleyin.  
  
 [in]`lp`  
 Yeni Pencere menüsü işleyin.  
  
 [in]`hmenu`  
 Yeni çerçeve penceresi menüsüne işleyin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `LRESULT`Varsayılan pencere yordamı çağırma gelen sonucudur.  
  
 `BOOL`olan `TRUE` olayı, işlenmediyse, `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsetpreviewmode"></a>CFrameWndEx::OnSetPreviewMode  
 Çerçeve Baskı Önizleme modunu ayarlamak için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bPreview`  
 `TRUE`Baskı önizlemeyi etkinleştirmek için; `FALSE` Baskı Önizleme devre dışı bırakmak için.  
  
 [in]`pState`  
 İşaretçi bir `CPrintPreviewState` çerçeve durumu yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsettext"></a>CFrameWndEx::OnSetText  
 Bir pencere metninin ayarlamak için çerçevesi tarafından çağrılır.  
  
```  
afx_msg LRESULT OnSetText(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`wParam`  
 Bu parametre kullanılmaz.  
  
 [in]`lParam`  
 Pencere için metin işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çağrısından değer döndürmek [DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572).  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onshowcustomizepane"></a>CFrameWndEx::OnShowCustomizePane  
 Ne zaman çerçevesi tarafından çağrılır bir `QuickCustomizePane`.  
  
```  
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,  
    UINT uiToolbarID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pMenuPane`  
 Hızlı bir işaretçi bölmesinde özelleştirin.  
  
 [in]`uiToolbarID`  
 Denetim Kimliği özelleştirme araç.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem her zaman dönüş `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Hızlı özelleştirme menüsü tıkladığınızda görüntülenen araç çubuğunun özelleştirme düğmesini açılır menü olur  
  
##  <a name="onshowpanes"></a>CFrameWndEx::OnShowPanes  
 Bölmeleri göstermek veya gizlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bShow`  
 `TRUE`Uygulama bölmeleri gösterir `FALSE` Aksi takdirde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem her zaman dönüş `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama bölmeleri gösterir, `bShow` olan `TRUE` ve bölmeleri gizli veya ne zaman `bShow` olan `FALSE` bölmeleri görülebilir.  
  
 Varsayılan uygulama, bölmeleri gizler `bShow` olan `TRUE` bölmeleri görülebilir veya ne zaman `bShow` olan `FALSE` ve bölmeleri gizlenir.  
  
 Türetilen bir sınıfta framework gösterir veya gizler bölmeleri özel kod yürütmek için bu yöntemi geçersiz kılın.  
  
##  <a name="onshowpopupmenu"></a>CFrameWndEx::OnShowPopupMenu  
 Açılır menü görüntülediğinde çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu* pMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pMenu`  
 Açılır menü için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`açılır menü görünür durumdaysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta framework açılır menü görüntülediğinde özel kod yürütmek için bu yöntemi geçersiz kılın. Örneğin, bir açılır menü komutları arka plan rengini değiştirmek için bu yöntemi geçersiz kılın.  
  
##  <a name="onsize"></a>CFrameWndEx::OnSize  
 Çerçeve boyutu değiştikten sonra çerçevesi tarafından çağrılır.  
  
```  
afx_msg void OnSize(
    UINT nType,  
    int cx,  
    int cy);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nType`  
 Yeniden boyutlandırma türü. Olası değerler için parametre bkz `wParam` içinde [WM_SIZE bildirim](http://msdn.microsoft.com/library/windows/desktop/ms632646).  
  
 [in]`cx`  
 Yeni Çerçeve piksel cinsinden genişliği.  
  
 [in]`cy`  
 Yeni Çerçeve piksel cinsinden yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsizing"></a>CFrameWndEx::OnSizing  
 Kullanıcı çerçeve yeniden boyutlandırır çerçevesi tarafından çağrılır.  
  
```  
afx_msg void OnSizing(
    UINT fwSide,  
    LPRECT pRect);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`fwSide`  
 Kenarın çerçevenin taşınır. Bkz. parametre `wParam` içinde [WM_SIZING bildirim](http://msdn.microsoft.com/library/windows/desktop/ms632647).  
  
 [içinde out]`pRect`  
 İşaretçi bir [CRect](../../atl-mfc-shared/reference/crect-class.md) veya [RECT](../../mfc/reference/rect-structure1.md) çerçeve koordinatları içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsyscolorchange"></a>CFrameWndEx::OnSysColorChange  
 Sistem renkleri değiştiğinde çerçevesi tarafından çağrılır.  
  
```  
void OnSysColorChange();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ontearoffmenu"></a>CFrameWndEx::OnTearOffMenu  
 Uygulama bir etiketleri çubuğu sahip bir menü görüntülediğinde çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnTearOffMenu(
    CMFCPopupMenu* pMenuPopup,  
    CPane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pMenuPopup`  
 Açılır menü için bir işaretçi.  
  
 [in]`pBar`  
 Bir işaretçi etiketleri çubuğuna.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`etiketleri çubuğu açılır menü etkinleştirilirse; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim çubuğu framework görüntülediğinde, özel kod yürütmek için bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
 Varsayılan uygulama hiçbir şey yapmaz ve döndürür `TRUE`.  
  
##  <a name="ontoolbarcontextmenu"></a>CFrameWndEx::OnToolbarContextMenu  
 Araç çubuğu açılır menü oluşturmak için çerçevesi tarafından çağrılır.  
  
```  
afx_msg LRESULT OnToolbarContextMenu(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`wp`  
 Bu parametre kullanılmaz.  
  
 [in]`lp`  
 Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 1 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ontoolbarcreatenew"></a>CFrameWndEx::OnToolbarCreateNew  
 Framework'te yeni bir araç çubuğu oluşturmak için bu yöntemi çağırır.  
  
```  
afx_msg LRESULT OnToolbarCreateNew(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`wp`  
 Bu parametre kullanılmaz.  
  
 [in]`lp`  
 Araç çubuğunun başlık çubuğu için metin işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni araç çubuğu işaretçi; veya `NULL` bir araç çubuğu değil oluşturulduysa.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ontoolbardelete"></a>CFrameWndEx::OnToolbarDelete  
 Araç çubuğu silindiğinde çerçevesi tarafından çağrılır.  
  
```  
afx_msg LRESULT OnToolbarDelete(
    WPARAM, 
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]  
 Bu parametre kullanılmaz.  
  
 [in]`lp`  
 Araç çubuğu işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`araç çubuğu silindiyse; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onupdateframemenu"></a>CFrameWndEx::OnUpdateFrameMenu  
 Çerçeve menüsü Ayarla çerçevesi tarafından çağrılır.  
  
```  
virtual void OnUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`hMenuAlt`  
 Alternatif menüsüne işleyin.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onupdateframetitle"></a>CFrameWndEx::OnUpdateFrameTitle  
 Çerçeve çerçeve penceresinin başlık çubuğunu güncelleştirmek için bu yöntemi çağırır.  
  
```  
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bAddToTitle`  
 `TRUE`çerçeve penceresi başlık çubuğunda etkin belgeyi başlık eklemek için; Aksi takdirde`FALSE.`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onupdatepanemenu"></a>CFrameWndEx::OnUpdatePaneMenu  
 Bölmesi menüsünde güncelleştirmek için çerçevesi tarafından çağrılır.  
  
```  
afx_msg void OnUpdatePaneMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pCmdUI`  
 Bölmesinde kullanıcı arabirimi nesnesine işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onwindowposchanged"></a>CFrameWndEx::OnWindowPosChanged  
 Pencere yönetimi yöntemine yapılan bir çağrı nedeniyle çerçeve boyutu, konum veya z düzeni değiştiğinde çerçevesi tarafından çağrılır.  
  
```  
afx_msg void OnWindowPosChanged(WINDOWPOS FAR* lpwndpos);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpwndpos`  
 İşaretçi bir [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) yeni boyutunu ve konumunu içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="panefrompoint"></a>CFrameWndEx::PaneFromPoint  
 Her bölme için belirtilen noktasını arar.  
  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar,  
    CRuntimeClass* pRTCBarType) const;  
  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`point`  
 Ekran koordinatları kontrol noktasının.  
  
 [in]`nSensitivity`  
 Her denetim çubuğu sınırlayıcı dikdörtgenini noktası için arama yaparken bu miktarda genişletin.  
  
 [in]`bExactBar`  
 `TRUE`yoksaymak için `nSensitivity` parametresi; Aksi halde, `FALSE`.  
  
 [in]`pRTCBarType`  
 Aksi takdirde `NULL`, yalnızca belirtilen türe ait denetim çubukları yöntemi arar.  
  
 [out]`dwAlignment`  
 Başarılı olursa, bu parametre belirtilen noktasına en yakın olan denetim çubuğu tarafında yer alır. Aksi takdirde, bu parametre başlatılmadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi içeren denetim çubuğu `point`; `NULL` hiçbir denetim bulunursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, uygulamanız için tüm denetim çubukları arar bir `point`.  
  
 Kullanım `nSensitivity` arama alanı boyutunu artırabilirsiniz. Kullanım `pRTCBarType` yöntemi arar denetim çubukları türlerini kısıtlayacak şekilde.  
  
##  <a name="pretranslatemessage"></a>CFrameWndEx::PreTranslateMessage  
 Bunlar gönderilir önce belirli bir pencere iletileri işler.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pMsg`  
 Bir işaretçi bir [MSG](../../mfc/reference/msg-structure1.md) işlemek için ileti içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır dışı iletisi işlendi ve değil dağıtılması; 0 ileti işlenmediğini ve dağıtılması.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="recalclayout"></a>CFrameWndEx::RecalcLayout  
 Dilimi ve onun alt öğe pencerelerini düzenini ayarlar.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bNotify`  
 OLE istemci öğesi Düzen değiştirme hakkında bilgilendirmek belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, çerçeve penceresi boyutunu değiştiğinde veya denetim çubukları görüntülenir ya da gizli çağrılır.  
  
##  <a name="removepanefromdockmanager"></a>CFrameWndEx::RemovePaneFromDockManager  
 Bir bölme kaydını siler ve yerleştirme Yöneticisi'nden kaldırır.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pControlBar,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide,  
    CBasePane* pBarReplacement);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pControlBar`  
 Bir işaretçi kaldırmak için denetim çubuğu bölmesine.  
  
 [in]`bDestroy`  
 `TRUE`denetim çubuğu kaldırdıktan sonra yok etmek için; `FALSE` Aksi takdirde.  
  
 [in]`bAdjustLayout`  
 `TRUE`yerleştirme düzeni ayarlamak için; `FALSE` Aksi takdirde.  
  
 [in]`bAutoHide`  
 `TRUE`denetim çubuğu otomatik olarak gizle modundaysa; `FALSE` Aksi takdirde.  
  
 [in]`pBarReplacement`  
 Bir işaretçi bir bölmesine kaldırılan bölmesinde yerini alır.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim çubuğu çerçeve penceresi takma düzeninden kaldırmak için bu yöntemi kullanın.  
  
 [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) denetim çubukları yerleşimini işler. Kullanarak her denetim çubuğu yerleştirme yöneticisiyle kaydolmalıdır [CFrameWndEx::AddPane](#addpane) yöntemi veya [CFrameWndEx::InsertPane](#insertpane) yöntemi.  
  
##  <a name="setdockstate"></a>CFrameWndEx::SetDockState  
 Yerleştirme düzeni kayıt defterinde depolanan takma durumunu geri yükler.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Parametreler  
 `state`  
 Takma durumu. Bu parametre yoksayıldı.  
  
##  <a name="setprintpreviewframe"></a>CFrameWndEx::SetPrintPreviewFrame  
 Baskı Önizleme çerçeve penceresi ayarlar.  
  
```  
void SetPrintPreviewFrame(CFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWnd`  
 Baskı Önizleme çerçeve penceresi işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setuptoolbarmenu"></a>CFrameWndEx::SetupToolbarMenu  
 Eklemeleri kullanıcı tanımlı komutları bir araç çubuğu menü içine.  
  
```  
void SetupToolbarMenu(
    CMenu& menu,  
    const UINT uiViewUserToolbarCmdFirst,  
    const UINT uiViewUserToolbarCmdLast);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`menu`  
 A `CMenu` değiştirilecek nesne.  
  
 [in]`uiViewUserToolbarCmdFirst`  
 İlk kullanıcı tanımlı komutu.  
  
 [in]`uiViewUserToolbarCmdLast`  
 Son kullanıcı tarafından tanımlanan komutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework komutlarının kullanıcı tanımlı bir listede depolar. Kullanım `uiViewUserToolbarCmdFirst` ve `uiViewUserToolbarCmdList` komutları eklemek için dizinler belirtmek için.  
  
##  <a name="showfullscreen"></a>CFrameWndEx::ShowFullScreen  
 Ana çerçeve tam ekran modu ve normal modu arasında geçiş yapar.  
  
```  
void ShowFullScreen();
```  
  
##  <a name="showpane"></a>CFrameWndEx::ShowPane  
 Gösterir veya belirtilen bölmesini gizler.  
  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 Denetim çubuğu göstermek veya gizlemek için bir işaretçi.  
  
 [in]`bShow`  
 Varsa `TRUE`, uygulama denetim çubuğu gösterir. Aksi takdirde, uygulama denetim çubuğu gizler.  
  
 [in]`bDelay`  
 Varsa `TRUE`, yerleştirme düzenini ayarlama framework çağrıları kadar gecikme [CFrameWndEx::AdjustDockingLayout](#adjustdockinglayout). Aksi takdirde, yerleştirme düzeni hemen yeniden hesaplayın.  
  
 [in]`bActivate`  
 Varsa `TRUE`, denetim çubuğu etkin hale. Aksi durumda, etkin olmayan bir durumda denetim çubuğu gösteriliyor.  
  
##  <a name="updatecaption"></a>CFrameWndEx::UpdateCaption  
 Pencere çerçevesi resim yazısı güncelleştirmek için çerçevesi tarafından çağrılır.  
  
```  
void UpdateCaption();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="winhelp"></a>CFrameWndEx::WinHelp  
 WinHelp uygulaması veya bağlam çağırır ilgili Yardım.  
  
```  
virtual void WinHelp(
    DWORD dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwData`  
 Bağımlı veri `nCmd` parametresi. Olası değerler listesi için bkz: [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267).  
  
 `nCmd`  
 Help komutu. Olası değerler listesi için bkz: [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267).  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)
