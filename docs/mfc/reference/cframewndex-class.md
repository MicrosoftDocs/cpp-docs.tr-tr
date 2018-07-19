---
title: CFrameWndEx sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97548fca6b47e8d765eb7744a86ab0d4cfa27b17
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337495"
---
# <a name="cframewndex-class"></a>CFrameWndEx sınıfı
Implements işlevselliğinin bir Windows tek Belgeli Arabirim (SDI) çakışan veya açılır çerçeve penceresinde ve pencereyi yönetmek için üyeleri sağlar. Bunu genişleten [CFrameWnd](../../mfc/reference/cframewnd-class.md) sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CFrameWndEx : public CFrameWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFrameWndEx::ActiveItemRecalcLayout](#activeitemrecalclayout)|Bir OLE istemci öğesi ve çerçevenin istemci alanını düzenini ayarlar.|  
|`CFrameWndEx::AddDockSite`|Bu yöntem kullanılmaz.|  
|[CFrameWndEx::AddPane](#addpane)|Denetim çubuğu yerleştirme Yöneticisi ile kaydeder.|  
|[CFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)|Çerçeve penceresi için yerleşik tüm bölmeleri düzenini yeniden hesaplar.|  
|[CFrameWndEx::DelayUpdateFrameMenu](#delayupdateframemenu)|Çerçeve menüsü ayarlar ve komut işleme boşta olduğunda güncelleştirir.|  
|[CFrameWndEx::DockPane](#dockpane)|Çerçeve penceresi için belirtilen bölmesinde docks.|  
|[CFrameWndEx::DockPaneLeftOf](#dockpaneleftof)|Başka bir bölmenin sol noktaları bir bölme.|  
|[CFrameWndEx::EnableAutoHidePanes](#enableautohidepanes)|Ana çerçeve penceresinin belirtilen kenarlara yerleştirildiğinde bölmeleri otomatik gizleme modunu etkinleştirir.|  
|[CFrameWndEx::EnableDocking](#enabledocking)|Çerçeve penceresi için ait bölmeleri yerleştirme sağlar.|  
|[CFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu)|Tam ekran moduna ana menüde gizler veya gösterir.|  
|[CFrameWndEx::EnableFullScreenMode](#enablefullscreenmode)|Çerçeve penceresi için tam ekran modunu etkinleştirir.|  
|[CFrameWndEx::EnableLoadDockState](#enableloaddockstate)|Etkinleştirir veya takma durumunu yüklenmesini devre dışı bırakır.|  
|[CFrameWndEx::EnablePaneMenu](#enablepanemenu)|Etkinleştirir veya bölmesi menüsünde otomatik işlenmesi devre dışı bırakır.|  
|[CFrameWndEx::GetActivePopup](#getactivepopup)|Şu anda görüntülenen açılır menüsüne bir işaretçi döndürür.|  
|[CFrameWndEx::GetDefaultResId](#getdefaultresid)|Çerçeve çerçeve penceresi yüklendiğinde, belirttiğiniz kaynak Kimliğini döndürür.|  
|[CFrameWndEx::GetDockingManager](#getdockingmanager)|Alır [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) çerçeve penceresi için nesne.|  
|[CFrameWndEx::GetMenuBar](#getmenubar)|Çerçeve penceresi için bağlı menü çubuğu nesneye bir işaretçi döndürür.|  
|[CFrameWndEx::GetPane](#getpane)|Belirtilen kimliğe sahip bölmesine bir işaretçi döndürür|  
|[CFrameWndEx::GetRibbonBar](#getribbonbar)|Çerçeve için Şerit çubuğu denetimi alır.|  
|[CFrameWndEx::GetTearOffBars](#gettearoffbars)|Bir etiket kapalı durumda olan bölmesinde nesnelerin bir listesini döndürür.|  
|[CFrameWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|Uygulama araç çubuğu düğmesi için araç ipucu görüntülendiğinde framework tarafından çağırılır.|  
|[CFrameWndEx::InsertPane](#insertpane)|Bir bölme yerleştirme Yöneticisi ile kaydeder.|  
|[CFrameWndEx::IsFullScreen](#isfullscreen)|Çerçeve penceresi tam ekran modunda olup olmadığını belirler.|  
|[CFrameWndEx::IsMenuBarAvailable](#ismenubaravailable)|Menü çubuğu nesne işaretçisi geçerli olup olmadığını belirler.|  
|[CFrameWndEx::IsPointNearDockSite](#ispointneardocksite)|Noktası bir hizalama alanında bulunup bulunmadığını gösterir.|  
|[CFrameWndEx::IsPrintPreview](#isprintpreview)|Çerçeve penceresi yazdırma önizleme modunda olup olmadığını belirtir.|  
|[CFrameWndEx::LoadFrame](#loadframe)|Bu yöntem çerçevesi penceresi oluştur ve kaynaklarıyla yüklemek için yapı sonra çağrılır.|  
|[CFrameWndEx::NegotiateBorderSpace](#negotiateborderspace)|OLE istemci border anlaşması uygular.|  
|[CFrameWndEx::OnActivate](#onactivate)|Kullanıcı girişi için veya çerçevenin uzağa geçildiğinde framework bu yöntemi çağırır.|  
|[CFrameWndEx::OnActivateApp](#onactivateapp)|Uygulama hem seçilen veya de seçili framework tarafından çağırılır.|  
|[CFrameWndEx::OnChangeVisualManager](#onchangevisualmanager)|Çerçevenin bir değişiklik görsel yöneticiyi değişiklik gerektirdiğinde framework tarafından çağırılır.|  
|[CFrameWndEx::OnClose](#onclose)|Framework çerçeveyi kapatmak için bu yöntemi çağırır.|  
|[CFrameWndEx::OnCloseDockingPane](#onclosedockingpane)|Kullanıcı tıkladığında framework tarafından çağırılır **Kapat** bir yerleştirme bölmesi düğmesi.|  
|[CFrameWndEx::OnCloseMiniFrame](#oncloseminiframe)|Kullanıcı tıkladığında framework tarafından çağırılır **Kapat** düğmesine bir kayan mini çerçeve penceresi.|  
|[CFrameWndEx::OnClosePopupMenu](#onclosepopupmenu)|Etkin bir açılan menü WM_DESTROY iletiyi işleyen framework tarafından çağırılır.|  
|[CFrameWndEx::OnCmdMsg](#oncmdmsg)|İleti gönderileri komutu.|  
|[CFrameWndEx::OnContextHelp](#oncontexthelp)|Framework tarafından çağırılır içeriği görüntülemek için Yardım ilgili.|  
|[CFrameWndEx::OnCreate](#oncreate)|Çerçeve oluşturulduktan sonra framework tarafından çağırılır.|  
|[CFrameWndEx::OnDestroy](#ondestroy)|Çerçeve kaldırıldığında framework tarafından çağırılır.|  
|[CFrameWndEx::OnDrawMenuImage](#ondrawmenuimage)|Uygulama Menü öğesiyle ilişkili görüntü çizdiğinde framework tarafından çağırılır.|  
|[CFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|Framework tarafından çağırılır, bir `CMFCPopupMenu` nesne işlemleri bir [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) ileti.|  
|[CFrameWndEx::OnDWMCompositionChanged](#ondwmcompositionchanged)|Masaüstü Pencere Yöneticisi'ni (DWM) kompozisyonu etkin veya devre dışı olduğunda framework tarafından çağırılır.|  
|[CFrameWndEx::OnExitSizeMove](#onexitsizemove)|Çerçeve taşıma veya yeniden boyutlandırma durduğunda framework tarafından çağırılır.|  
|[CFrameWndEx::OnGetMinMaxInfo](#ongetminmaxinfo)|Çerçeve penceresi boyut sınırlarını ayarlamak için yeniden boyutlandırıldığında framework tarafından çağırılır.|  
|[CFrameWndEx::OnIdleUpdateCmdUI](#onidleupdatecmdui)|Çerçeve görüntü komutu işleme boşta olduğunda güncelleştirmek için framework tarafından çağırılır.|  
|[CFrameWndEx::OnLButtonDown](#onlbuttondown)|Kullanıcının sol fare düğmesine bastığında framework bu yöntemi çağırır.|  
|[CFrameWndEx::OnLButtonUp](#onlbuttonup)|Kullanıcının sol fare düğmesini bıraktığında framework bu yöntemi çağırır.|  
|[CFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|Framework tarafından çağırılır, bir `CMFCToolBarButton` bir wm_nchıttest mesajı nesnesini işler.|  
|[CFrameWndEx::OnMenuChar](#onmenuchar)|Bir menü görüntülenir ve kullanıcı bir komuta karşılık gelmeyen anahtar framework tarafından çağırılır.|  
|[CFrameWndEx::OnMouseMove](#onmousemove)|İşaretçiyi hareket ettirdiğinde framework bu yöntemi çağırır.|  
|[CFrameWndEx::OnMoveMiniFrame](#onmoveminiframe)|Bölme penceresi hareket ettiğinde framework tarafından çağırılır.|  
|[CFrameWndEx::OnNcActivate](#onncactivate)|Çerçevenin istemci olmayan alanın etkin durumundaki bir değişikliği göstermek için çizilmesini framework tarafından çağırılır.|  
|[CFrameWndEx::OnNcCalcSize](#onnccalcsize)|Boyutunu ve konumunu istemci alanının hesaplanmalıdır framework tarafından çağırılır.|  
|[CFrameWndEx::OnNcHitTest](#onnchittest)|İşaretçiyi hareket ettirdiğinde veya bir fare düğmesine basıldığında veya serbest framework tarafından çağırılır.|  
|[CFrameWndEx::OnNcMouseMove](#onncmousemove)|Bir istemci olmayan alanda işaretçiyi hareket ettirdiğinde framework tarafından çağırılır.|  
|[CFrameWndEx::OnNcPaint](#onncpaint)|İstemci olmayan alanın boyanan framework tarafından çağırılır.|  
|[CFrameWndEx::OnPaneCheck](#onpanecheck)|Bir bölme görünürlüğünü denetleme için framework tarafından çağırılır.|  
|[CFrameWndEx::OnPostPreviewFrame](#onpostpreviewframe)|Kullanıcı yazdırma Önizleme modundan değiştiğinde framework tarafından çağırılır.|  
|[CFrameWndEx::OnPowerBroadcast](#onpowerbroadcast)|Bir güç yönetimi olayının meydana geldiğinde framework tarafından çağırılır.|  
|[CFrameWndEx::OnSetMenu](#onsetmenu)|Çerçeve Pencere menüsü değiştirmek için framework tarafından çağırılır.|  
|[CFrameWndEx::OnSetPreviewMode](#onsetpreviewmode)|Çerçeve Baskı Önizleme modunu ayarlamak için framework tarafından çağırılır.|  
|[CFrameWndEx::OnSetText](#onsettext)|Pencere metnini ayarlamak için framework tarafından çağırılır.|  
|[CFrameWndEx::OnShowCustomizePane](#onshowcustomizepane)|Hızlı özelleştirdiğinizde framework tarafından çağırılır bölmesinde etkinleştirilir.|  
|[CFrameWndEx::OnShowPanes](#onshowpanes)|Bölmeleri göstermek veya gizlemek için framework tarafından çağırılır.|  
|[CFrameWndEx::OnShowPopupMenu](#onshowpopupmenu)|Açılır menü etkinleştirildiğinde framework tarafından çağırılır.|  
|[CFrameWndEx::OnSize](#onsize)|Çerçeve çerçeve boyutu değiştikten sonra bu yöntemi çağırır.|  
|[CFrameWndEx::OnSizing](#onsizing)|Çerçeve kullanıcı yeniden boyutlandırdığında framework bu yöntemi çağırır.|  
|[CFrameWndEx::OnSysColorChange](#onsyscolorchange)|Sistem renkleri değiştiğinde framework tarafından çağırılır.|  
|[CFrameWndEx::OnTearOffMenu](#ontearoffmenu)|Bölünmüş çubuk içeren menü etkinleştirildiğinde framework tarafından çağırılır.|  
|[CFrameWndEx::OnToolbarContextMenu](#ontoolbarcontextmenu)|Araç çubuğu bağlam menüsü oluşturmak için framework tarafından çağırılır.|  
|[CFrameWndEx::OnToolbarCreateNew](#ontoolbarcreatenew)|Framework, yeni bir araç çubuğu oluşturmak için bu yöntemi çağırır.|  
|[CFrameWndEx::OnToolbarDelete](#ontoolbardelete)|Araç çubuğu silindiğinde framework tarafından çağırılır.|  
|[CFrameWndEx::OnUpdateFrameMenu](#onupdateframemenu)|Çerçevenin menüsünü ayarlamak için framework tarafından çağırılır.|  
|[CFrameWndEx::OnUpdateFrameTitle](#onupdateframetitle)|Çerçeve çerçeve penceresinin başlık çubuğunu güncellemek için bu yöntemi çağırır.|  
|[CFrameWndEx::OnUpdatePaneMenu](#onupdatepanemenu)|Bölme menüsü güncelleştirmek için framework tarafından çağırılır.|  
|[CFrameWndEx::OnWindowPosChanged](#onwindowposchanged)|Pencere Yönetimi yönteme bir çağrı nedeniyle çerçeve boyutu, konumu ve z düzenini değiştiğinde framework tarafından çağırılır.|  
|[CFrameWndEx::PaneFromPoint](#panefrompoint)|Belirtilen nokta içeren bir yerleştirme bölmesi döndürür.|  
|[CFrameWndEx::PreTranslateMessage](#pretranslatemessage)|Belirli bir pencere iletilerini dağıtılmadan önceden işler.|  
|[CFrameWndEx::RecalcLayout](#recalclayout)|Çerçeve ve onun alt pencereleri düzenini ayarlar.|  
|[CFrameWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|Bir bölme kaydını siler ve yerleştirme manager iç listesinden kaldırır.|  
|[CFrameWndEx::SetDockState](#setdockstate)|Yerleştirme düzeni, kayıt defterinde depolanan yerleştirme durumuna geri yükler.|  
|[CFrameWndEx::SetPrintPreviewFrame](#setprintpreviewframe)|Baskı Önizleme çerçeve penceresinin ayarlar.|  
|[CFrameWndEx::SetupToolbarMenu](#setuptoolbarmenu)|Ekler araç çubuğu menüsü içine komutları kullanıcı tanımlı.|  
|[CFrameWndEx::ShowFullScreen](#showfullscreen)|Ana çerçeve tam ekran ile normal modlar arasında geçiş yapar.|  
|[CFrameWndEx::ShowPane](#showpane)|Belirtilen bölmesini gizler veya gösterir.|  
|[CFrameWndEx::UpdateCaption](#updatecaption)|Pencere çerçevesi başlığı güncelleştirmek için framework tarafından çağırılır.|  
|[CFrameWndEx::WinHelp](#winhelp)|Ya da çağırır `WinHelp` uygulama veya bağlam ilgili Yardım.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir sınıftan gösterilmektedir `CFrameWndEx` sınıfı. Örnek yöntem imzaları alt ve nasıl geçersiz kılınacağını gösterir `OnShowPopupMenu` yöntemi. Bu kod parçacığı parçasıdır [Word paneli örnek](../../visual-cpp-samples.md).  
  
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
  
##  <a name="activeitemrecalclayout"></a>  CFrameWndEx::ActiveItemRecalcLayout  
 Bir OLE istemci öğesi ve çerçevenin istemci alanını düzenini ayarlar.  
  
```  
void ActiveItemRecalcLayout();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addpane"></a>  CFrameWndEx::AddPane  
 Denetim çubuğu yerleştirme Yöneticisi ile kaydeder.  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pControlBar*  
 Kaydetmek için bir denetim çubuğu bölmesi.  
  
 [in] *bTail*  
 Denetim çubuğu bölmesini listenin sonuna eklemek istiyorsanız TRUE; FALSE Aksi takdirde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim çubuğu başarıyla kaydedildi TRUE; FALSE Aksi takdirde.  
  
##  <a name="adjustdockinglayout"></a>  CFrameWndEx::AdjustDockingLayout  
 Çerçeve penceresi için yerleşik tüm bölmeleri düzenini yeniden hesaplar.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *hdwp*  
 Birden çok windows konumlarını içeren bir yapıya tanıtıcı. biçimindeki telefon numarasıdır.  
  
### <a name="remarks"></a>Açıklamalar  
 Hdwp yapısı tarafından başlatılan [BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672) yöntemi.  
  
##  <a name="delayupdateframemenu"></a>  CFrameWndEx::DelayUpdateFrameMenu  
 Çerçeve menüsü ayarlar ve komut işleme boşta olduğunda güncelleştirir.  
  
```  
virtual void DelayUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *hMenuAlt*  
 Alternatif bir menüye işleyin.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="dockpane"></a>  CFrameWndEx::DockPane  
 Çerçeve penceresi için belirtilen bölmesinde docks.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID=0,  
    LPCRECT lpRect=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
 Yerleştirilemediğinde denetim çubuğu için bir işaretçi.  
  
 [in] *nDockBarID*  
 Çerçeve penceresi için sabitlemek için tarafında kimliği.  
  
 [in] *lpRect*  
 Pencerenin ekran konumunu ve boyutunu belirten sabit bir Rect yapısı işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 *NDockBarID* parametre aşağıdaki değerlerden biri olabilir:  
  
-   AFX_IDW_DOCKBAR_TOP  
  
-   AFX_IDW_DOCKBAR_BOTTOM  
  
-   AFX_IDW_DOCKBAR_LEFT  
  
-   AFX_IDW_DOCKBAR_RIGHT  
  
##  <a name="dockpaneleftof"></a>  CFrameWndEx::DockPaneLeftOf  
 Başka bir bölmesinin solunda belirtilen bölmesinde docks.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
 Yerleştirilemediğinde bölmesinde nesnesine bir işaretçi.  
  
 [in] *pLeftOf*  
 Bir işaretçi tarafından belirtilen bölmesinde sabitlemek istediğiniz solundaki bölmesine *pBar*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE ise *pBar* başarıyla yerleştirilir. FALSE Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem tarafından belirtilen araç alır *pBar* parametresi ve bu araç sol tarafında belirtilen noktaları *pLeftOf* parametresi.  
  
##  <a name="enableautohidepanes"></a>  CFrameWndEx::EnableAutoHidePanes  
 Etkinleştirir otomatik modu bölmesi için ana çerçeve penceresinin belirtilen tarafına yerleştirildiğinde gizleme.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwDockStyle*  
 Bölmesinde sabitlemek ana çerçeve penceresine tarafını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir çubuk TRUE bölmesi tarafından belirtilen çerçeve penceresi tarafına yuvalanmış başarıyla *dwDockStyle*false Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 *dwDockStyle* aşağıdaki değerlerden biri olabilir:  
  
-   CBRS_ALIGN_TOP: bir çerçeve penceresinin istemci alanına üstüne yerleştirilemediğinde denetim çubuğu sağlar.  
  
-   CBRS_ALIGN_BOTTOM: bir çerçeve penceresinin istemci alanına altına yerleştirilemediğinde denetim çubuğu sağlar.  
  
-   CBRS_ALIGN_LEFT: bir çerçeve penceresinin istemci alanına sol tarafına sabitlenebilir denetim çubuğu sağlar.  
  
-   CBRS_ALIGN_RIGHT: bir çerçeve penceresinin istemci alanına sağ tarafına sabitlenebilir denetim çubuğu sağlar.  
  
##  <a name="enabledocking"></a>  CFrameWndEx::EnableDocking  
 Çerçeve pencere bölmelerinde yerleştirme sağlar.  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwDockStyle*  
 Ana çerçeve penceresinin nerede bölmesinde çubuk noktaları yan belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir çubuk TRUE bölmesi başarıyla yuvalanmış belirtilen yanında. FALSE Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 *DwDockStyle* parametre aşağıdaki değerlerden biri olabilir:  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="enablefullscreenmainmenu"></a>  CFrameWndEx::EnableFullScreenMainMenu  
 Tam ekran moduna ana menüde gizler veya gösterir.  
  
```  
void EnableFullScreenMainMenu(BOOL bEnableMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bEnableMenu*  
 Show tam bir ana menüde true modu, yanlış Aksi halde ekran.  
  
##  <a name="enablefullscreenmode"></a>  CFrameWndEx::EnableFullScreenMode  
 Çerçeve penceresi için tam ekran modunu etkinleştirir.  
  
```  
void EnableFullScreenMode(UINT uiFullScreenCmd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiFullScreenCmd*  
 Sağlar ve tam ekran modu devre dışı bırakan bir komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Tam ekran modunda, tüm yerleştirme denetim çubukları, araç çubuklarını ve menü gizlidir ve etkin görünüm tam ekranı kaplayacak şekilde yeniden boyutlandırılır.  
  
 Tam ekran modunda etkinleştirdiğinizde, tam ekran modu devre dışı bırakır veya komut kimliği belirtmelisiniz. Çağırabilirsiniz `EnableFullScreenMode` ana çerçeve gelen `OnCreate` işlevi. Bir çerçeve penceresinde bir tam ekran moduna geçiş, framework dolaştırılabilir araç kutusu ile belirtilen komut kimliğe sahip bir düğme oluşturur.  
  
 Ana menü ekranda tutmak istiyorsanız, çağrı [CFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu).  
  
##  <a name="enableloaddockstate"></a>  CFrameWndEx::EnableLoadDockState  
 Etkinleştirir veya takma durumunu yüklenmesini devre dışı bırakır.  
  
```  
void EnableLoadDockState(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSistemlerde*  
 Yerleştirme durumu yüklenmesini devre dışı bırakmak için FALSE yerleştirme durumu yüklenmesini etkinleştirmek için TRUE.  
  
##  <a name="enablepanemenu"></a>  CFrameWndEx::EnablePaneMenu  
 Etkinleştirir veya bölmesi menüsünde otomatik işlenmesi devre dışı bırakır.  
  
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
 [in] *bSistemlerde*  
 Açılır menü çubuğu denetiminin otomatik işlemesini etkinleştirmek için TRUE; Açılır menü çubuğu denetiminin otomatik işlemeyi devre dışı bırakmak için FALSE.  
  
 [in] *uiCustomizeCmd*  
 Komut Kimliği **Özelleştir** menü öğesi.  
  
 [in] *strCustomizeLabel*  
 Etiketi için görüntülenecek **Özelleştir** menü öğesi  
  
 [in] *uiViewToolbarsMenuEntryID*  
 Açılır menüyü açılır denetim çubuğunda bir araç çubuğu menü öğesi kimliği.  
  
 [in] *bContextMenuShowsToolbarsOnly*  
 TRUE ise denetim çubuğu bağlam menüsü araç çubukları sadece listesini görüntüler. FALSE ise menüsü araç çubukları ve yerleştirme çubukları listesini görüntüler.  
  
 [in] *bViewMenuShowsToolbarsOnly*  
 TRUE ise denetim çubuğu menüsü araç çubukları sadece listesini görüntüler. FALSE ise menüsü araç çubukları ve yerleştirme çubukları listesini görüntüler.  
  
##  <a name="getactivepopup"></a>  CFrameWndEx::GetActivePopup  
 Şu anda görüntülenen açılır menüsüne bir işaretçi döndürür.  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda görüntülenen açılır menüde bir işaretçi; bulunmazsa null değerini DÖNDÜRÜR.  
  
##  <a name="getdefaultresid"></a>  CFrameWndEx::GetDefaultResId  
 Çerçeve çerçeve penceresi yüklendiğinde, belirttiğiniz kaynak Kimliğini döndürür.  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı ne zaman çerçeve penceresi framework yüklü belirtilen kaynak kimliği değeri. Çerçeve penceresinin menü çubuğunu yoksa sıfır.  
  
##  <a name="getdockingmanager"></a>  CFrameWndEx::GetDockingManager  
 Alır [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) çerçeve penceresi için nesne.  
  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve penceresi oluşturur ve bir [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) alt pencere yerleştirme yönetmek için nesne.  
  
##  <a name="getmenubar"></a>  CFrameWndEx::GetMenuBar  
 Çerçeve penceresi için bağlı menü çubuğu nesneye bir işaretçi döndürür.  
  
```  
const CMFCMenuBar* GetMenuBar() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çerçeve penceresi için bağlı menü çubuğu nesnesine bir işaretçi.  
  
##  <a name="getpane"></a>  CFrameWndEx::GetPane  
 Belirtilen kimliğe sahip bölmesine bir işaretçi döndürür  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nID*  
 Denetim kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen kimliğe sahip bölmesine bir işaretçi Böyle bir bölmesinde yoksa NULL.  
  
##  <a name="getribbonbar"></a>  CFrameWndEx::GetRibbonBar  
 Çerçeve için Şerit çubuğu denetimi alır.  
  
```  
CMFCRibbonBar* GetRibbonBar();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi [CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md) çerçevesi için.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gettearoffbars"></a>  CFrameWndEx::GetTearOffBars  
 Bir etiket kapalı durumda olan bölmesinde nesnelerin bir listesini döndürür.  
  
```  
const CObList& GetTearOffBars() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru `CObList` etkinleştiriliyorken durumda olan bölmesinde nesnelerine işaretçiler koleksiyonunu içeren nesne.  
  
##  <a name="gettoolbarbuttontooltiptext"></a>  CFrameWndEx::GetToolbarButtonToolTipText  
 Uygulama araç çubuğu düğmesi için araç ipucu görüntülendiğinde framework tarafından çağırılır.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton* pButton,  
    CString& strTTText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pButton*  
 Araç çubuğu düğmesi için bir işaretçi.  
  
 [in] *strTTText*  
 Düğme için görüntülenecek araç ipucu metni.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Araç İpucu görüntüleniyorsa TRUE. FALSE Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntemi hiçbir şey yapmaz. Araç çubuğu düğmesi için araç ipucunu görüntülemek istiyorsanız bu yöntemi yok sayın.  
  
##  <a name="insertpane"></a>  CFrameWndEx::InsertPane  
 Bölme denetim çubukları listesine ekler ve yerleştirme Yöneticisi ile kaydeder.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *pControlBar*  
 Denetim çubuğu denetim listesine eklenecek bir işaretçiye çubukları ve yerleştirme Manager'a kayıtlı.  
  
 *pTarget*  
 Denetim çubuğu önce veya sonra bölmesinde eklenecek bir işaretçi.  
  
 *bBu*  
 Eklemek istiyorsanız TRUE *pControlBar* sonra *pTarget*yanlış, aksi takdirde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim çubuğu başarıyla eklenen ve kayıtlı, yanlış Aksi durumda, TRUE.  
  
### <a name="remarks"></a>Açıklamalar  
 Her denetim çubuğu kullanarak kaydetmelisiniz [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) yerleştirme düzende katılmak için.  
  
##  <a name="isfullscreen"></a>  CFrameWndEx::IsFullScreen  
 Çerçeve penceresi tam ekran modunda olup olmadığını belirler.  
  
```  
BOOL IsFullScreen() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çerçeve penceresi tam ekran modunda ise TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırarak tam ekran modunu ayarlayabilirsiniz [CFrameWndEx::EnableFullScreenMode](#enablefullscreenmode) yöntemi.  
  
##  <a name="ismenubaravailable"></a>  CFrameWndEx::IsMenuBarAvailable  
 Menü çubuğu nesne işaretçisi geçerli olup olmadığını belirler.  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çerçeve penceresinin menü çubuğunu varsa TRUE; Aksi durumda FALSE.  
  
##  <a name="ispointneardocksite"></a>  CFrameWndEx::IsPointNearDockSite  
 Noktası bir hizalama alanında bulunup bulunmadığını belirler.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *noktası*  
 Noktası konumu.  
  
 [out] *dwBarAlignment*  
 Burada noktası hizalanır. Olası değerler için Açıklamalar bölümü içindeki tabloya bakın.  
  
 [out] *bOuterEdge*  
 Çerçeve kenarlığı yakın noktası bulunuyorsa TRUE; Noktası bir istemci alanında bulunuyorsa FALSE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Noktası bir hizalama bölgede yer alıyorsa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin olası değerler aşağıdaki tabloda *dwBarAlignment* parametresi.  
  
 CBRS_ALIGN_TOP  
 Dosyanın en üstüne hizalanmış.  
  
 CBRS_ALIGN_RIGHT  
 Sağa hizalanır.  
  
 CBRS_ALIGN_BOTTOM  
 En Alta Hizala.  
  
 CBRS_ALIGN_LEFT  
 Sola hizalanır.  
  
##  <a name="isprintpreview"></a>  CFrameWndEx::IsPrintPreview  
 Çerçeve penceresi yazdırma önizleme modunda olup olmadığını belirler.  
  
```  
BOOL IsPrintPreview();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çerçeve penceresi yazdırma önizleme modunda ise TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="loadframe"></a>  CFrameWndEx::LoadFrame  
 Bu yöntem çerçevesi penceresi oluştur ve kaynaklarıyla yüklemek için yapı sonra çağrılır.  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIDResource*  
 Tüm çerçeve kaynakları yüklemek için kullanılan kaynak kimliği.  
  
 [in] *dwDefaultStyle*  
 Varsayılan çerçeve pencere stili.  
  
 [in] *pParentWnd*  
 Çerçevenin üst pencere işaretçisi.  
  
 [in] *pContext*  
 İşaretçi bir [CCreateContext yapısı](../../mfc/reference/ccreatecontext-structure.md) framework tarafından uygulama oluşturma sırasında kullanılan sınıf.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olduysa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="negotiateborderspace"></a>  CFrameWndEx::NegotiateBorderSpace  
 OLE istemci border anlaşması uygular.  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nBorderCmd*  
 Kenarlık anlaşma komutu. Olası değerler için Açıklamalar bölümüne bakın.  
  
 [out içinde] *lpRectBorder*  
 Boyutları kenarlığın kalınlığı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düzen hesaplanmalıdır TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin olası değerler aşağıdaki tabloda *nBorderCmd* parametresi.  
  
 *borderGet*  
 OLE istemci yer alın.  
  
 *borderRequest*  
 OLE istemci alanı istek.  
  
 *borderSet*  
 OLE istemci alanı ayarlayın.  
  
##  <a name="onactivate"></a>  CFrameWndEx::OnActivate  
 Kullanıcı girişi için veya çerçevenin uzağa geçildiğinde framework bu yöntemi çağırır.  
  
```  
afx_msg void OnActivate(
    UINT nState,  
    CWnd* pWndOther,  
    BOOL bMinimized);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nDurum*  
 Çerçeve etkin veya devre dışı olup olmadığı. Olası değerler için Açıklamalar bölümü içindeki tabloya bakın.  
  
 [in] *pWndOther*  
 Kullanıcı girişi geçerli bir değiştirme başka bir pencere işaretçisi.  
  
 [in] *bMinimized*  
 Çerçevenin simge durumuna küçültülmüş durumda. Çerçeve simge durumuna küçültülmüş olan TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin olası değerler aşağıdaki tabloda *nDurum* parametresi.  
  
 WA_ACTIVE  
 Çerçevenin bir fare tıklaması dışında bir yöntem tarafından seçilir.  
  
 WA_CLICKACTIVE  
 Çerçeve tarafından bir fare tıklaması seçilir.  
  
 WA_INACTIVE  
 Çerçeve seçilmedi.  
  
##  <a name="onactivateapp"></a>  CFrameWndEx::OnActivateApp  
 Uygulama hem seçilen veya de seçili framework tarafından çağırılır.  
  
```  
afx_msg void OnActivateApp(
    BOOL bActive,  
    DWORD dwThreadID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bActive*  
 Uygulama seçiliyse TRUE; Uygulama seçili değilse FALSE.  
  
 [in] *dwThreadID*  
 Bu parametre kullanılmaz.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onchangevisualmanager"></a>  CFrameWndEx::OnChangeVisualManager  
 Çerçevenin bir değişiklik görsel yöneticiyi değişiklik gerektirdiğinde framework tarafından çağırılır.  
  
```  
afx_msg LRESULT OnChangeVisualManager(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *wParam*  
 Bu parametre kullanılmaz.  
  
 [in] *lParam*  
 Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 0 değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onclose"></a>  CFrameWndEx::OnClose  
 Framework çerçeveyi kapatmak için bu yöntemi çağırır.  
  
```  
afx_msg void OnClose();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Baskı Önizleme modunda çerçeve baskı önizlemeyi kapatmak için Windows iletisi gönderir; Aksi takdirde çerçeveyi bir OLE istemci barındırıyorsa, istemci devre dışı bırakılır.  
  
##  <a name="onclosedockingpane"></a>  CFrameWndEx::OnCloseDockingPane  
 Kullanıcı tıkladığında framework tarafından çağırılır **Kapat** bir yerleştirme bölmesi düğmesi.  
  
```  
virtual BOOL OnCloseDockingPane(CDockablePane* pPane);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Takma çubuğu kapatılabilir TRUE. FALSE Aksi takdirde  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama, hiçbir şey yapmaz. Takma çubuğu gizleme işlemek istiyorsanız bu yöntemi yok sayın.  
  
##  <a name="oncloseminiframe"></a>  CFrameWndEx::OnCloseMiniFrame  
 Kullanıcı tıkladığında framework tarafından çağırılır **Kapat** düğmesine bir kayan mini çerçeve penceresi.  
  
```  
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kayan mini çerçeve pencere kapatılabilir, TRUE. FALSE Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama, hiçbir şey yapmaz. Bir kayan mini çerçeve penceresinin gizleme işlemek istiyorsanız bu yöntemi yok sayın.  
  
##  <a name="onclosepopupmenu"></a>  CFrameWndEx::OnClosePopupMenu  
 Etkin bir açılan menü WM_DESTROY iletiyi işleyen framework tarafından çağırılır.  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>Parametreler  
 *pMenuPopup*  
 Açılır menü için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Pencere kapanmak üzere olduğunda framework WM_DESTROY ileti gönderir. Bildirimler işlemek istiyorsanız bu yöntemi yok sayın `CMFCPopupMenu` çerçeve penceresine ait nesneleri, bir `CMFCPopupMenu` nesne penceresi kapatıldığında framework tarafından gönderilen WM_DESTROY mesaj işleniyor.  
  
##  <a name="oncmdmsg"></a>  CFrameWndEx::OnCmdMsg  
 İleti gönderileri komutu.  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nID*  
 Komut kimliği.  
  
 [in] *nCode*  
 İleti kategorisi komutu.  
  
 [out içinde] *pExtra*  
 Komut nesnesi için işaretçi.  
  
 [out içinde] *pHandlerInfo*  
 Bir komut işleyici yapıya yönelik işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Komut iletisini işleniyorsa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="oncontexthelp"></a>  CFrameWndEx::OnContextHelp  
 Bağlam ile ilgili yardımı görüntülemek için framework tarafından çağırılır.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="oncreate"></a>  CFrameWndEx::OnCreate  
 Çerçeve oluşturulduktan sonra framework tarafından çağırılır.  
  
```  
afx_msg int OnCreate(LPCREATESTRUCT lpCreateStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpCreateStruct*  
 Bir işaretçi [CREATESTRUCT yapısı](../../mfc/reference/createstruct-structure.md) için yeni bir çerçeve.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çerçeve oluşturma işlemine devam etmek için 0; çerçeve yok etmek için -1.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondestroy"></a>  CFrameWndEx::OnDestroy  
 Çerçeve kaldırıldığında framework tarafından çağırılır.  
  
```  
afx_msg void OnDestroy();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Hızlandırıcı tablosunu ve tüm windows yok edilir.  
  
##  <a name="ondrawmenuimage"></a>  CFrameWndEx::OnDrawMenuImage  
 Uygulama Menü öğesiyle ilişkili görüntü çizdiğinde framework tarafından çağırılır.  
  
```  
virtual BOOL OnDrawMenuImage(
    CDC* pDC,  
    const CMFCToolBarMenuButton* pMenuButton,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] *pMenuButton*  
 Bir menü düğmesi, görüntü işlenen bir işaretçi.  
  
 [in] *rectImage*  
 Bir işaretçi bir `Rect` yapısı görüntünün boyutu ve ekran konumunu belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Framework görüntüsünü başarıyla işler TRUE; FALSE Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Görüntü işleme ait tarafından sahip olunan menü çubuğuna menü öğeleri için özelleştirmek istiyorsanız bu yöntemi yok sayın `CFrameWndEx` türetilmiş bir nesneye.  
  
##  <a name="ondrawmenulogo"></a>  CFrameWndEx::OnDrawMenuLogo  
 Framework tarafından çağırılır, bir `CMFCPopupMenu` nesnesini WM_PAINT iletisini işler.  
  
```  
virtual void OnDrawMenuLogo(
    CDC* pDC,  
    CMFCPopupMenu* pMenu,  
    const CRect& rectLogo);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] *pMenu*  
 Menü öğesi için bir işaretçi.  
  
 [in] *rectLogo*  
 Bir sabit bir başvuru `CRect` menü logosu boyutunu ve ekran konumunu belirten yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev tarafından sahip olunan menü çubuğuna ait açılan menüden bir logo görüntülemek istiyorsanız geçersiz kılma `CFrameWndEx` türetilmiş bir nesneye.  
  
##  <a name="ondwmcompositionchanged"></a>  CFrameWndEx::OnDWMCompositionChanged  
 Masaüstü Pencere Yöneticisi'ni (DWM) kompozisyonu etkin veya devre dışı olduğunda framework tarafından çağırılır.  
  
```  
afx_msg LRESULT OnDWMCompositionChanged(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *wp*  
 Bu parametre kullanılmaz.  
  
 [in] *lp*  
 Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 0 değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onexitsizemove"></a>  CFrameWndEx::OnExitSizeMove  
 Çerçeve taşıma veya yeniden boyutlandırma durduğunda framework tarafından çağırılır.  
  
```  
LRESULT OnExitSizeMove(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *wp*  
 Bu parametre kullanılmaz.  
  
 [in] *lp*  
 Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 0 değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ongetminmaxinfo"></a>  CFrameWndEx::OnGetMinMaxInfo  
 Çerçeve penceresi boyut sınırlarını ayarlamak için yeniden boyutlandırıldığında framework tarafından çağırılır.  
  
```  
afx_msg void OnGetMinMaxInfo(MINMAXINFO FAR* lpMMI);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpMMI*  
 İşaretçi bir [MINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632605) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onidleupdatecmdui"></a>  CFrameWndEx::OnIdleUpdateCmdUI  
 Çerçeve görüntü komutu işleme boşta olduğunda güncelleştirmek için framework tarafından çağırılır.  
  
```  
afx_msg LRESULT OnIdleUpdateCmdUI(
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *wParam*  
 Bu parametre kullanılmaz.  
  
 [in] *lParam*  
 Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 0 değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onlbuttondown"></a>  CFrameWndEx::OnLButtonDown  
 Kullanıcının sol fare düğmesine bastığında framework bu yöntemi çağırır.  
  
```  
afx_msg void OnLButtonDown(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nFlags*  
 Kullanıcı değiştirici tuşları basılı olup olmadığını gösterir. Olası değerler için parametre bkz *wParam* içinde [WM_LBUTTONDOWN bildirim](http://msdn.microsoft.com/library/windows/desktop/ms645607).  
  
 [in] *noktası*  
 X ve y koordinatları işaretçinin, pencerenin sol üst köşesindeki göreli belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onlbuttonup"></a>  CFrameWndEx::OnLButtonUp  
 Kullanıcının sol fare düğmesini bıraktığında framework bu yöntemi çağırır.  
  
```  
afx_msg void OnLButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nFlags*  
 Kullanıcı değiştirici tuşları basılı olup olmadığını gösterir. Olası değerler için parametre bkz *wParam* içinde [WM_LBUTTONUP bildirim](http://msdn.microsoft.com/library/windows/desktop/ms645608).  
  
 [in] *noktası*  
 X ve y koordinatları işaretçinin, pencerenin sol üst köşesindeki göreli belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onmenubuttontoolhittest"></a>  CFrameWndEx::OnMenuButtonToolHitTest  
 Framework tarafından çağırılır, bir `CMFCToolBarButton` bir wm_nchıttest mesajı nesnesini işler.  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pButton*  
 Araç çubuğu düğmesi için bir işaretçi.  
  
 [out] *PTI*  
 Bir aracı bilgi yapısı işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygulama doldurur, doğru *PTI* parametresi. FALSE Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli bir menü öğesi hakkında bir araç ipucu bilgisini sağlamak istiyorsanız bu yöntemi yok sayın.  
  
##  <a name="onmenuchar"></a>  CFrameWndEx::OnMenuChar  
 Bir menü görüntülenir ve kullanıcı bir komuta karşılık gelmeyen anahtar framework tarafından çağırılır.  
  
```  
afx_msg LRESULT OnMenuChar(
    UINT nChar,  
    UINT nFlags,  
    CMenu* pMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nChar*  
 Basılan tuşa karakter kodu.  
  
 [in] *nFlags*  
 Bir alt menüsünü ise MF_POPUP bayrağı içerir. görüntülenen menüyü Denetim menüsü ise MF_SYSMENU bayrağı içeriyor.  
  
 [in] *pMenu*  
 Bir menü işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dwpoint aşağıdaki değerlerden biri olmalıdır.  
  
 `0`  
 Framework tuş vuruşu yok saymanız gerekir.  
  
 `1`  
 Çerçevenin menüsünü kapatmalısınız.  
  
 `2`  
 Framework menüde görüntülenen öğelerden birini seçmeniz gerekir. Düşük düzey word seçmek için komutu Kimliğini içerir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onmousemove"></a>  CFrameWndEx::OnMouseMove  
 İşaretçiyi hareket ettirdiğinde framework bu yöntemi çağırır.  
  
```  
afx_msg void OnMouseMove(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nFlags*  
 Bir kullanıcı değiştirici tuşları basılı olup olmadığını gösterir. Olası değerler için parametre bkz *wParam* içinde [WM_MOUSEMOVE bildirim](http://msdn.microsoft.com/library/windows/desktop/ms645616).  
  
 [in] *noktası*  
 X ve y belirtir işaretçinin penceresinin sol üst köşesindeki göreli koordinatları.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onmoveminiframe"></a>  CFrameWndEx::OnMoveMiniFrame  
 Bölme penceresi hareket ettiğinde framework tarafından çağırılır.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pFrame*  
 İşaretçi [CPaneFrameWnd sınıfı](../../mfc/reference/cpaneframewnd-class.md) bölme penceresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölme penceresi yuvaya TRUE; Bölme penceresi sabitlenmiş FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onncactivate"></a>  CFrameWndEx::OnNcActivate  
 Çerçevenin istemci olmayan alanın etkin durumundaki bir değişikliği göstermek için çizilmesini framework tarafından çağırılır.  
  
```  
afx_msg BOOL OnNcActivate(BOOL bActive);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bActive*  
 Çizim etkin çerçeve için true; Etkin olmayan çerçeve çizmek için FALSE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan işleme devam etmek için sıfır olmayan; İstemci olmayan alanın devre dışı bırakılan önlemek için 0'ı tıklatın.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onnccalcsize"></a>  CFrameWndEx::OnNcCalcSize  
 Boyutunu ve konumunu istemci alanının hesaplanmalıdır framework tarafından çağırılır.  
  
```  
afx_msg void OnNcCalcSize(
    BOOL bCalcValidRects,  
    NCCALCSIZE_PARAMS FAR* lpncsp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bCalcValidRects*  
 Uygulamanın geçerli istemci alanını belirtmeniz gerektiğinde TRUE; Aksi takdirde FALSE.  
  
 [in] *lpncsp*  
 İşaretçi bir `NCCALCSIZE_PARAMS` çerçeve boyut değişiklikleri içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onnchittest"></a>  CFrameWndEx::OnNcHitTest  
 İşaretçiyi hareket ettirdiğinde veya bir fare düğmesine basıldığında veya serbest framework tarafından çağırılır.  
  
```  
afx_msg LRESULT OnNcHitTest(CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *noktası*  
 İşaretçiyi ekran koordinatlarına göre konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi isabet numaralandırılmış değeri. Olası değerler listesi için bkz. [wm_nchıttest bildirim](http://msdn.microsoft.com/library/windows/desktop/ms645618).  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onncmousemove"></a>  CFrameWndEx::OnNcMouseMove  
 Bir istemci olmayan alanda işaretçiyi hareket ettirdiğinde framework tarafından çağırılır.  
  
```  
afx_msg void OnNcMouseMove(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nHitTest*  
 Bir işaretçi isabet numaralandırılmış değeri. Olası değerler listesi için bkz. [wm_nchıttest bildirim](http://msdn.microsoft.com/library/windows/desktop/ms645618).  
  
 [in] *noktası*  
 İşaretçiyi ekran koordinatlarına göre konumu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onncpaint"></a>  CFrameWndEx::OnNcPaint  
 İstemci olmayan alanın boyanan framework tarafından çağırılır.  
  
```  
afx_msg void OnNcPaint();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onpanecheck"></a>  CFrameWndEx::OnPaneCheck  
 Bir bölme görünürlüğünü denetleme için framework tarafından çağırılır.  
  
```  
afx_msg BOOL OnPaneCheck(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nID*  
 Bölme denetim kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Komut işleniyorsa TRUE; Komut işleme devam etmek için FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onpostpreviewframe"></a>  CFrameWndEx::OnPostPreviewFrame  
 Kullanıcı yazdırma Önizleme modundan değiştiğinde framework tarafından çağırılır.  
  
```  
afx_msg LRESULT OnPostPreviewFrame(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *wParam*  
 Bu parametre kullanılmaz.  
  
 [in] *lParam*  
 Çerçeve baskı önizleme modunda olduğunda TRUE; Baskı Önizleme modunu kapalı olduğunda FALSE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 0 değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onpowerbroadcast"></a>  CFrameWndEx::OnPowerBroadcast  
 Bir güç yönetimi olayının meydana geldiğinde framework tarafından çağırılır.  
  
```  
afx_msg LRESULT OnPowerBroadcast(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *wp*  
 Güç Yönetimi olayının. Olası değerler listesi için bkz. [WM_POWERBROADCAST ileti](http://msdn.microsoft.com/library/windows/desktop/aa373247).  
  
 [in] *lp*  
 Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan pencere yordamını çağırma sonucu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsetmenu"></a>  CFrameWndEx::OnSetMenu  
 Çerçeve Pencere menüsü değiştirmek için framework tarafından çağırılır.  
  
```  
afx_msg LRESULT OnSetMenu(
    WPARAM wp,  
    LPARAM lp);  
  
BOOL OnSetMenu(HMENU hmenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *wp*  
 Yeni bir çerçeve penceresi menüsüne işleyin.  
  
 [in] *lp*  
 Yeni Pencere menüsü için işler.  
  
 [in] *hmenu*  
 Yeni bir çerçeve penceresi menüsüne işleyin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 LRESULT varsayılan pencere yordamını çağırarak öğesinden oluşur.  
  
 Olay işleniyorsa BOOL değeri True'dur; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsetpreviewmode"></a>  CFrameWndEx::OnSetPreviewMode  
 Çerçeve Baskı Önizleme modunu ayarlamak için framework tarafından çağırılır.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bPreview*  
 Baskı önizlemeyi etkinleştirmek için TRUE; Baskı önizlemeyi devre dışı bırakmak için FALSE.  
  
 [in] *pState*  
 İşaretçi bir `CPrintPreviewState` çerçeve durumu yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsettext"></a>  CFrameWndEx::OnSetText  
 Pencere metnini ayarlamak için framework tarafından çağırılır.  
  
```  
afx_msg LRESULT OnSetText(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *wParam*  
 Bu parametre kullanılmaz.  
  
 [in] *lParam*  
 Pencere için metin işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir çağrıdan dönüş değeri [DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572).  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onshowcustomizepane"></a>  CFrameWndEx::OnShowCustomizePane  
 Görüntüler gerektiğinde framework tarafından çağırılır bir `QuickCustomizePane`.  
  
```  
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,  
    UINT uiToolbarID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pMenuPane*  
 Hızlı bir işaretçiye bölmesinde özelleştirin.  
  
 [in] *uiToolbarID*  
 Denetim Kimliği özelleştirme araç çubuğu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem her zaman TRUE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hızlı özelleştirme menüsünü olan tıkladığınızda görüntülenen araç çubuğunun Özelleştir düğmesi açılır menü  
  
##  <a name="onshowpanes"></a>  CFrameWndEx::OnShowPanes  
 Bölmeleri göstermek veya gizlemek için framework tarafından çağırılır.  
  
```  
virtual BOOL OnShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bBilgi Göster*  
 Uygulama bölmeleri gösteriliyorsa TRUE; FALSE Aksi takdirde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem her zaman FALSE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulamasını bölmeleri gösterir, *bBilgi Göster* true'dur ve bölmeleri gizli veya *bBilgi Göster* yanlış ve bölmeleri görülebilir.  
  
 Varsayılan uygulama, bölmeleri gizler *bBilgi Göster* true'dur ve bölmeleri görülebilir veya *bBilgi Göster* yanlış ve bölmeleri gizlenir.  
  
 Türetilen bir sınıfta framework gösterir veya gizler bölmeleri zaman özel kod yürütmek için bu yöntemi yok sayın.  
  
##  <a name="onshowpopupmenu"></a>  CFrameWndEx::OnShowPopupMenu  
 Açılır menü görüntülendiğinde framework tarafından çağırılır.  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu* pMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pMenu*  
 Açılır menü için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açılır menü görünür ise TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta framework açılır menü görüntülendiğinde özel kod yürütmek için bu yöntemi yok sayın. Örneğin, açılır menü komutlarında arka plan rengini değiştirmek için bu yöntemi yok sayın.  
  
##  <a name="onsize"></a>  CFrameWndEx::OnSize  
 Çerçeve boyutu değiştikten sonra framework tarafından çağırılır.  
  
```  
afx_msg void OnSize(
    UINT nType,  
    int cx,  
    int cy);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nTür*  
 Yeniden boyutlandırma türü. Olası değerler için parametre bkz *wParam* içinde [WM_SIZE bildirim](http://msdn.microsoft.com/library/windows/desktop/ms632646).  
  
 [in] *cx*  
 Yeni çerçevenin piksel cinsinden genişliği.  
  
 [in] *cy*  
 Yeni çerçevenin piksel cinsinden yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsizing"></a>  CFrameWndEx::OnSizing  
 Çerçeve kullanıcı yeniden boyutlandırdığında framework tarafından çağırılır.  
  
```  
afx_msg void OnSizing(
    UINT fwSide,  
    LPRECT pRect);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *fwSide*  
 Taşınan çerçevenin kenarına. Bkz. parametre *wParam* içinde [WM_SIZING bildirim](http://msdn.microsoft.com/library/windows/desktop/ms632647).  
  
 [out içinde] *pRect*  
 İşaretçi bir [CRect](../../atl-mfc-shared/reference/crect-class.md) veya [RECT](../../mfc/reference/rect-structure1.md) çerçeve koordinatları içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsyscolorchange"></a>  CFrameWndEx::OnSysColorChange  
 Sistem renkleri değiştiğinde framework tarafından çağırılır.  
  
```  
void OnSysColorChange();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ontearoffmenu"></a>  CFrameWndEx::OnTearOffMenu  
 Uygulama bir bölünmüş çubuk içeren menü görüntülendiğinde framework tarafından çağırılır.  
  
```  
virtual BOOL OnTearOffMenu(
    CMFCPopupMenu* pMenuPopup,  
    CPane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pMenuPopup*  
 Açılır menü için bir işaretçi.  
  
 [in] *pBar*  
 Bölünmüş çubuk işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açılır menü etkinleştiriliyorken çubuğuyla etkinse TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta bir denetim çubuğu framework görüntülediğinde, özel kod yürütmek için bu yöntemi yok sayın.  
  
 Varsayılan uygulama, hiçbir şey yapmaz ve TRUE döndürür.  
  
##  <a name="ontoolbarcontextmenu"></a>  CFrameWndEx::OnToolbarContextMenu  
 Araç çubuğu açılır menü oluşturmak için framework tarafından çağırılır.  
  
```  
afx_msg LRESULT OnToolbarContextMenu(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *wp*  
 Bu parametre kullanılmaz.  
  
 [in] *lp*  
 Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 1 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ontoolbarcreatenew"></a>  CFrameWndEx::OnToolbarCreateNew  
 Framework, yeni bir araç çubuğu oluşturmak için bu yöntemi çağırır.  
  
```  
afx_msg LRESULT OnToolbarCreateNew(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *wp*  
 Bu parametre kullanılmaz.  
  
 [in] *lp*  
 Başlık çubuğu araç çubuğunun metin işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni araç çubuğu işaretçi; veya NULL bir araç çubuğu oluşturulmadı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ontoolbardelete"></a>  CFrameWndEx::OnToolbarDelete  
 Araç çubuğu silindiğinde framework tarafından çağırılır.  
  
```  
afx_msg LRESULT OnToolbarDelete(
    WPARAM, 
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]  
 Bu parametre kullanılmaz.  
  
 [in] *lp*  
 Araç çubuğu için işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Araç silindiyse TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onupdateframemenu"></a>  CFrameWndEx::OnUpdateFrameMenu  
 Çerçevenin menüsünü ayarlamak için framework tarafından çağırılır.  
  
```  
virtual void OnUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *hMenuAlt*  
 Alternatif menüsüne işleyin.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onupdateframetitle"></a>  CFrameWndEx::OnUpdateFrameTitle  
 Çerçeve çerçeve penceresinin başlık çubuğunu güncellemek için bu yöntemi çağırır.  
  
```  
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bAddToTitle*  
 Çerçeve penceresinin başlık çubuğuna etkin belgenin başlığını eklemek için TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onupdatepanemenu"></a>  CFrameWndEx::OnUpdatePaneMenu  
 Bölme menüsü güncelleştirmek için framework tarafından çağırılır.  
  
```  
afx_msg void OnUpdatePaneMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pCmdUI*  
 Bölmesinde kullanıcı arabirimi nesnesi işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onwindowposchanged"></a>  CFrameWndEx::OnWindowPosChanged  
 Pencere Yönetimi yönteme bir çağrı nedeniyle çerçeve boyutu, konumu ve z düzenini değiştiğinde framework tarafından çağırılır.  
  
```  
afx_msg void OnWindowPosChanged(WINDOWPOS FAR* lpwndpos);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpwndpos*  
 İşaretçi bir [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) yeni boyutunu ve konumunu içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="panefrompoint"></a>  CFrameWndEx::PaneFromPoint  
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
 [in] *noktası*  
 Ekran koordinatları kontrol noktası.  
  
 [in] *nSensitivity*  
 Her denetim çubuğu sınırlayıcı dikdörtgenini noktası için arama yaparken bu miktarda genişletin.  
  
 [in] *bExactBar*  
 Yok saymak için TRUE *nSensitivity* parametre; Aksi takdirde FALSE.  
  
 [in] *pRTCBarType*  
 BOŞ değilse, yöntemi yalnızca denetim çubukları öğesinin belirtilen türe arar.  
  
 [out] *dwAlignment*  
 Başarılı olursa, bu parametre için belirtilen nokta en yakın olan denetim çubuğu tarafında yer alır. Aksi takdirde, bu parametre başlatılmadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi içeren bir denetim çubuğuna *noktası*; Hiçbir denetim bulunamazsa, boş.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, uygulamanız için tüm denetim çubukları arar bir *noktası*.  
  
 Kullanım *nSensitivity* arama alanının boyutunu artırmak için. Kullanım *pRTCBarType* yönteminin aradığı denetim çubukları türlerini kısıtlamak için.  
  
##  <a name="pretranslatemessage"></a>  CFrameWndEx::PreTranslateMessage  
 Belirli bir pencere iletilerini dağıtılmadan önceden işler.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pMsg*  
 Bir işaretçi bir [MSG](../../mfc/reference/msg-structure1.md) işlemek için bir ileti içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan ileti işlendiğini ve değil dağıtılması; 0 ileti işlenmedi ve dağıtılması.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="recalclayout"></a>  CFrameWndEx::RecalcLayout  
 Çerçeve ve onun alt pencereleri düzenini ayarlar.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bNotify*  
 Düzen değişikliği hakkında bir OLE istemci öğesi bildirmek belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, çerçeve penceresinin boyutu değiştiğinde veya denetim çubukları görünür veya gizli çağrılır.  
  
##  <a name="removepanefromdockmanager"></a>  CFrameWndEx::RemovePaneFromDockManager  
 Bir bölme kaydını siler ve yerleştirme Manager'dan kaldırır.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pControlBar,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide,  
    CBasePane* pBarReplacement);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pControlBar*  
 Kaldırmak için denetim çubuğu bölmesi için bir işaretçi.  
  
 [in] *bDestroy*  
 Denetim çubuğu kaldırdıktan sonra yok etmek için TRUE; FALSE Aksi takdirde.  
  
 [in] *bAdjustLayout*  
 Yerleştirme düzeni ayarlamak için TRUE; FALSE Aksi takdirde.  
  
 [in] *bAutoHide*  
 Denetim çubuğu otomatik gizleme modundaysa TRUE; FALSE Aksi takdirde.  
  
 [in] *pBarReplacement*  
 Kaldırılan bölmesinde yerini alan bir bölme için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim çubuğu çerçeve penceresinin yerleştirme düzenden kaldırmak için bu yöntemi kullanın.  
  
 [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) denetim çubukları düzenini işler. Kullanarak her denetim çubuğu yerleştirme yöneticisiyle kaydetmelisiniz [CFrameWndEx::AddPane](#addpane) yöntemi veya [CFrameWndEx::InsertPane](#insertpane) yöntemi.  
  
##  <a name="setdockstate"></a>  CFrameWndEx::SetDockState  
 Yerleştirme düzeni, kayıt defterinde depolanan yerleştirme durumuna geri yükler.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Parametreler  
 *durumu*  
 Yerleştirme durumu. Bu parametre yoksayıldı.  
  
##  <a name="setprintpreviewframe"></a>  CFrameWndEx::SetPrintPreviewFrame  
 Baskı Önizleme çerçeve penceresinin ayarlar.  
  
```  
void SetPrintPreviewFrame(CFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWnd*  
 Baskı Önizleme çerçeve işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setuptoolbarmenu"></a>  CFrameWndEx::SetupToolbarMenu  
 Ekler araç çubuğu menüsü içine komutları kullanıcı tanımlı.  
  
```  
void SetupToolbarMenu(
    CMenu& menu,  
    const UINT uiViewUserToolbarCmdFirst,  
    const UINT uiViewUserToolbarCmdLast);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *menüsü*  
 A `CMenu` değiştirilecek nesne.  
  
 [in] *uiViewUserToolbarCmdFirst*  
 İlk kullanıcı tanımlı komutu.  
  
 [in] *uiViewUserToolbarCmdLast*  
 Son kullanıcı tanımlı komutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework, kullanıcı tanımlı komutları bir listesinde de depolar. Kullanım *uiViewUserToolbarCmdFirst* ve *uiViewUserToolbarCmdList* komutları eklemek için dizinlerini belirtmek için.  
  
##  <a name="showfullscreen"></a>  CFrameWndEx::ShowFullScreen  
 Ana çerçeve tam ekran modu ve normal modu arasında geçiş yapar.  
  
```  
void ShowFullScreen();
```  
  
##  <a name="showpane"></a>  CFrameWndEx::ShowPane  
 Belirtilen bölmesini gizler veya gösterir.  
  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
 Denetim çubuğu, göstermek veya gizlemek için bir işaretçi.  
  
 [in] *bBilgi Göster*  
 TRUE ise, uygulama denetim çubuğu gösterilir. Aksi takdirde, uygulama denetim çubuğu gizler.  
  
 [in] *bDelay*  
 TRUE ise yerleştirme düzeni ayarlamayı framework çağrıları kadar gecikme [CFrameWndEx::AdjustDockingLayout](#adjustdockinglayout). Aksi takdirde, yerleştirme düzeni hemen yeniden hesaplayın.  
  
 [in] *bActivate*  
 TRUE ise denetim çubuğu etkin hale getirin. Aksi takdirde, etkin olmayan bir durumda denetim çubuğu görüntüler.  
  
##  <a name="updatecaption"></a>  CFrameWndEx::UpdateCaption  
 Pencere çerçevesi başlığı güncelleştirmek için framework tarafından çağırılır.  
  
```  
void UpdateCaption();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="winhelp"></a>  CFrameWndEx::WinHelp  
 WinHelp uygulamasını veya bağlam çağırır ilgili Yardım.  
  
```  
virtual void WinHelp(
    DWORD dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwData*  
 Bağımlı veri *nCmd* parametresi. Olası değerler listesi için bkz. [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267).  
  
 *nCmd*  
 Help komutu. Olası değerler listesi için bkz. [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267).  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)
