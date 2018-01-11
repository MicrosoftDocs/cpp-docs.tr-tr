---
title: "CDockingManager sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockingManager
- AFXDOCKINGMANAGER/CDockingManager
- AFXDOCKINGMANAGER/CDockingManager::AddDockSite
- AFXDOCKINGMANAGER/CDockingManager::AddHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::AddMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::AddPane
- AFXDOCKINGMANAGER/CDockingManager::AdjustDockingLayout
- AFXDOCKINGMANAGER/CDockingManager::AdjustPaneFrames
- AFXDOCKINGMANAGER/CDockingManager::AdjustRectToClientArea
- AFXDOCKINGMANAGER/CDockingManager::AlignAutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::AutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::BringBarsToTop
- AFXDOCKINGMANAGER/CDockingManager::BuildPanesMenu
- AFXDOCKINGMANAGER/CDockingManager::CalcExpectedDockedRect
- AFXDOCKINGMANAGER/CDockingManager::Create
- AFXDOCKINGMANAGER/CDockingManager::DeterminePaneAndStatus
- AFXDOCKINGMANAGER/CDockingManager::DisableRestoreDockState
- AFXDOCKINGMANAGER/CDockingManager::DockPane
- AFXDOCKINGMANAGER/CDockingManager::DockPaneLeftOf
- AFXDOCKINGMANAGER/CDockingManager::EnableAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::EnableDocking
- AFXDOCKINGMANAGER/CDockingManager::EnableDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::EnablePaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::FindDockSite
- AFXDOCKINGMANAGER/CDockingManager::FindDockSiteByPane
- AFXDOCKINGMANAGER/CDockingManager::FindPaneByID
- AFXDOCKINGMANAGER/CDockingManager::FixupVirtualRects
- AFXDOCKINGMANAGER/CDockingManager::FrameFromPoint
- AFXDOCKINGMANAGER/CDockingManager::GetClientAreaBounds
- AFXDOCKINGMANAGER/CDockingManager::GetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::GetDockSiteFrameWnd
- AFXDOCKINGMANAGER/CDockingManager::GetEnabledAutoHideAlignment
- AFXDOCKINGMANAGER/CDockingManager::GetMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::GetOuterEdgeBounds
- AFXDOCKINGMANAGER/CDockingManager::GetPaneList
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManager
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManagerPermanent
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingTheme
- AFXDOCKINGMANAGER/CDockingManager::HideAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::InsertDockSite
- AFXDOCKINGMANAGER/CDockingManager::InsertPane
- AFXDOCKINGMANAGER/CDockingManager::IsDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::IsInAdjustLayout
- AFXDOCKINGMANAGER/CDockingManager::IsOLEContainerMode
- AFXDOCKINGMANAGER/CDockingManager::IsPointNearDockSite
- AFXDOCKINGMANAGER/CDockingManager::IsPrintPreviewValid
- AFXDOCKINGMANAGER/CDockingManager::LoadState
- AFXDOCKINGMANAGER/CDockingManager::LockUpdate
- AFXDOCKINGMANAGER/CDockingManager::OnActivateFrame
- AFXDOCKINGMANAGER/CDockingManager::OnClosePopupMenu
- AFXDOCKINGMANAGER/CDockingManager::OnMoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::OnPaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::PaneFromPoint
- AFXDOCKINGMANAGER/CDockingManager::ProcessPaneContextMenuCommand
- AFXDOCKINGMANAGER/CDockingManager::RecalcLayout
- AFXDOCKINGMANAGER/CDockingManager::ReleaseEmptyPaneContainers
- AFXDOCKINGMANAGER/CDockingManager::RemoveHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::RemoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::RemovePaneFromDockManager
- AFXDOCKINGMANAGER/CDockingManager::ReplacePane
- AFXDOCKINGMANAGER/CDockingManager::ResortMiniFramesForZOrder
- AFXDOCKINGMANAGER/CDockingManager::SaveState
- AFXDOCKINGMANAGER/CDockingManager::SendMessageToMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::Serialize
- AFXDOCKINGMANAGER/CDockingManager::SetAutohideZOrder
- AFXDOCKINGMANAGER/CDockingManager::SetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::SetDockState
- AFXDOCKINGMANAGER/CDockingManager::SetPrintPreviewMode
- AFXDOCKINGMANAGER/CDockingManager::SetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::ShowDelayShowMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::ShowPanes
- AFXDOCKINGMANAGER/CDockingManager::StartSDocking
- AFXDOCKINGMANAGER/CDockingManager::StopSDocking
- AFXDOCKINGMANAGER/CDockingManager::m_bHideDockingBarsInContainerMode
- AFXDOCKINGMANAGER/CDockingManager::m_dockModeGlobal
- AFXDOCKINGMANAGER/CDockingManager::m_nDockSensitivity
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeDockingBarDock
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeToolBarDock
dev_langs: C++
helpviewer_keywords:
- CDockingManager [MFC], AddDockSite
- CDockingManager [MFC], AddHiddenMDITabbedBar
- CDockingManager [MFC], AddMiniFrame
- CDockingManager [MFC], AddPane
- CDockingManager [MFC], AdjustDockingLayout
- CDockingManager [MFC], AdjustPaneFrames
- CDockingManager [MFC], AdjustRectToClientArea
- CDockingManager [MFC], AlignAutoHidePane
- CDockingManager [MFC], AutoHidePane
- CDockingManager [MFC], BringBarsToTop
- CDockingManager [MFC], BuildPanesMenu
- CDockingManager [MFC], CalcExpectedDockedRect
- CDockingManager [MFC], Create
- CDockingManager [MFC], DeterminePaneAndStatus
- CDockingManager [MFC], DisableRestoreDockState
- CDockingManager [MFC], DockPane
- CDockingManager [MFC], DockPaneLeftOf
- CDockingManager [MFC], EnableAutoHidePanes
- CDockingManager [MFC], EnableDocking
- CDockingManager [MFC], EnableDockSiteMenu
- CDockingManager [MFC], EnablePaneContextMenu
- CDockingManager [MFC], FindDockSite
- CDockingManager [MFC], FindDockSiteByPane
- CDockingManager [MFC], FindPaneByID
- CDockingManager [MFC], FixupVirtualRects
- CDockingManager [MFC], FrameFromPoint
- CDockingManager [MFC], GetClientAreaBounds
- CDockingManager [MFC], GetDockingMode
- CDockingManager [MFC], GetDockSiteFrameWnd
- CDockingManager [MFC], GetEnabledAutoHideAlignment
- CDockingManager [MFC], GetMiniFrames
- CDockingManager [MFC], GetOuterEdgeBounds
- CDockingManager [MFC], GetPaneList
- CDockingManager [MFC], GetSmartDockingManager
- CDockingManager [MFC], GetSmartDockingManagerPermanent
- CDockingManager [MFC], GetSmartDockingParams
- CDockingManager [MFC], GetSmartDockingTheme
- CDockingManager [MFC], HideAutoHidePanes
- CDockingManager [MFC], InsertDockSite
- CDockingManager [MFC], InsertPane
- CDockingManager [MFC], IsDockSiteMenu
- CDockingManager [MFC], IsInAdjustLayout
- CDockingManager [MFC], IsOLEContainerMode
- CDockingManager [MFC], IsPointNearDockSite
- CDockingManager [MFC], IsPrintPreviewValid
- CDockingManager [MFC], LoadState
- CDockingManager [MFC], LockUpdate
- CDockingManager [MFC], OnActivateFrame
- CDockingManager [MFC], OnClosePopupMenu
- CDockingManager [MFC], OnMoveMiniFrame
- CDockingManager [MFC], OnPaneContextMenu
- CDockingManager [MFC], PaneFromPoint
- CDockingManager [MFC], ProcessPaneContextMenuCommand
- CDockingManager [MFC], RecalcLayout
- CDockingManager [MFC], ReleaseEmptyPaneContainers
- CDockingManager [MFC], RemoveHiddenMDITabbedBar
- CDockingManager [MFC], RemoveMiniFrame
- CDockingManager [MFC], RemovePaneFromDockManager
- CDockingManager [MFC], ReplacePane
- CDockingManager [MFC], ResortMiniFramesForZOrder
- CDockingManager [MFC], SaveState
- CDockingManager [MFC], SendMessageToMiniFrames
- CDockingManager [MFC], Serialize
- CDockingManager [MFC], SetAutohideZOrder
- CDockingManager [MFC], SetDockingMode
- CDockingManager [MFC], SetDockState
- CDockingManager [MFC], SetPrintPreviewMode
- CDockingManager [MFC], SetSmartDockingParams
- CDockingManager [MFC], ShowDelayShowMiniFrames
- CDockingManager [MFC], ShowPanes
- CDockingManager [MFC], StartSDocking
- CDockingManager [MFC], StopSDocking
- CDockingManager [MFC], m_bHideDockingBarsInContainerMode
- CDockingManager [MFC], m_dockModeGlobal
- CDockingManager [MFC], m_nDockSensitivity
- CDockingManager [MFC], m_nTimeOutBeforeDockingBarDock
- CDockingManager [MFC], m_nTimeOutBeforeToolBarDock
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
caps.latest.revision: "37"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2f1a436ab6bfbc5e21e43267d3992310ed6f6a20
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdockingmanager-class"></a>CDockingManager sınıfı
Bir ana çerçeve penceresi takma düzende denetimleri çekirdek işlevselliğini uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDockingManager : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDockingManager::AddDockSite](#adddocksite)|Bir yuva bölmesi oluşturur ve denetim çubukları listesine ekler.|  
|[CDockingManager::AddHiddenMDITabbedBar](#addhiddenmditabbedbar)|Bir çubuğuna tanıtıcı ekler bölmeler sekmeli gizli MDI listesi bölmesine.|  
|[CDockingManager::AddMiniFrame](#addminiframe)|Bir çerçeve mini çerçeveler listesine ekler.|  
|[CDockingManager::AddPane](#addpane)|Bir bölme takma Yöneticisi ile kaydeder.|  
|[CDockingManager::AdjustDockingLayout](#adjustdockinglayout)|Yeniden hesaplar ve tüm bölmeleri bir çerçeve penceresinde düzenini ayarlar.|  
|[CDockingManager::AdjustPaneFrames](#adjustpaneframes)|Neden `WM_NCCALCSIZE` tüm bölmeleri gönderilecek ileti ve `CPaneFrameWnd` windows.|  
|[CDockingManager::AdjustRectToClientArea](#adjustrecttoclientarea)|Dikdörtgene hizalamasını ayarlar.|  
|[CDockingManager::AlignAutoHidePane](#alignautohidepane)|Autohide modu takma bölmesinde tam genişliğini alır veya tarafından çevrelenen çerçeve istemci alanının yüksekliğini yerleştirme siteleri göre yeniden boyutlandırır.|  
|[CDockingManager::AutoHidePane](#autohidepane)|Autohide araç oluşturur.|  
|[CDockingManager::BringBarsToTop](#bringbarstotop)|Belirtilen hizalama üstüne sahip yerleşik çubukları getirir.|  
|[CDockingManager::BuildPanesMenu](#buildpanesmenu)|Yerleştirme bölmeleri ve araç çubuklarını adları menüye ekler.|  
|[CDockingManager::CalcExpectedDockedRect](#calcexpecteddockedrect)|Yerleşik pencerenin beklenen dikdörtgen hesaplar.|  
|[CDockingManager::Create](#create)|Yerleşik yönetici oluşturur.|  
|[CDockingManager::DeterminePaneAndStatus](#determinepaneandstatus)|Verilen bir noktaya ve takma durumunu içeren bölme belirler.|  
|[CDockingManager::DisableRestoreDockState](#disablerestoredockstate)|Etkinleştirir veya kayıt defterinden yerleştirme düzeni yüklenmesini devre dışı bırakır.|  
|[CDockingManager::DockPane](#dockpane)|Bir bölme başka bir bölme ya da bir çerçeve penceresinde docks.|  
|[CDockingManager::DockPaneLeftOf](#dockpaneleftof)|Bir bölme başka bir bölme soluna docks.|  
|[CDockingManager::EnableAutoHidePanes](#enableautohidepanes)|Ana çerçeve bölmesinde yerleştirme sağlar, yerleştirme bölmesini oluşturur ve denetim çubukları listesine ekler.|  
|[CDockingManager::EnableDocking](#enabledocking)|Yerleştirme bölmesini oluşturur ve ana çerçeve bölmesinde yerleştirme sağlar.|  
|[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)|Tüm takma bölmeleri etiketlerinin açılır menüde açar ek bir düğme görüntülenir.|  
|[CDockingManager::EnablePaneContextMenu](#enablepanecontextmenu)|Kullanıcı farenin sağ düğmesiyle tıkladığında ve kitaplık WM_CONTEXTMENU iletiyi işlemeyi uygulama araç çubukları yerleştirme bölmeleri bir listesine sahip bir özel bağlam menüsünü görüntülemek için kitaplık söyler.|  
|[CDockingManager::FindDockSite](#finddocksite)|Çubuğu alır, belirtilen konumda olan ve belirtilen hizalama olan bölmesi.|  
|[CDockingManager::FindDockSiteByPane](#finddocksitebypane)|Çubuğu döndürür hedef çubuğu bölmesinin kimliğine sahip bölmesi.|  
|[CDockingManager::FindPaneByID](#findpanebyid)|Bir bölme belirtilen denetim kimliğe göre bulur|  
|[CDockingManager::FixupVirtualRects](#fixupvirtualrects)|Sanal dikdörtgenler tüm geçerli araç konumlara kaydeder.|  
|[CDockingManager::FrameFromPoint](#framefrompoint)|Belirtilen noktasını içeren çerçeveyi döndürür.|  
|[CDockingManager::GetClientAreaBounds](#getclientareabounds)|İstemci alanını sınırlarına içeren dikdörtgen alır.|  
|[CDockingManager::GetDockingMode](#getdockingmode)|Geçerli yerleştirme modu döndürür.|  
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|Bir işaretçi üst pencere çerçevesi için alır.|  
|[CDockingManager::GetEnabledAutoHideAlignment](#getenabledautohidealignment)|Bölmeleri etkin hizalamasını döndürür.|  
|[CDockingManager::GetMiniFrames](#getminiframes)|Miniframes listesini alır.|  
|[CDockingManager::GetOuterEdgeBounds](#getouteredgebounds)|Çerçeve dış kenarlarını içeren bir dikdörtgen alır.|  
|[CDockingManager::GetPaneList](#getpanelist)|Yerleştirme Manager'a ait bölmeleri listesini döndürür. Bu, tüm kayan bölmeleri içerir.|  
|[CDockingManager::GetSmartDockingManager](#getsmartdockingmanager)|Akıllı Yerleştirme Yöneticisi için bir işaretçi alır.|  
|[CDockingManager::GetSmartDockingManagerPermanent](#getsmartdockingmanagerpermanent)|Akıllı Yerleştirme Yöneticisi için bir işaretçi alır.|  
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|Akıllı Yerleştirme parametreleri için takma Yöneticisi döndürür.|  
|[CDockingManager::GetSmartDockingTheme](#getsmartdockingtheme)|Akıllı Yerleştirme işaretçileri görüntülemek için kullanılan tema döndüren bir statik yöntem.|  
|[CDockingManager::HideAutoHidePanes](#hideautohidepanes)|Autohide modunda olan bir bölmesini gizler.|  
|[CDockingManager::InsertDockSite](#insertdocksite)|Bir yuva bölmesi oluşturur ve denetim çubukları listesine ekler.|  
|[CDockingManager::InsertPane](#insertpane)|Denetim Masası denetim çubukları listesine ekler.|  
|[CDockingManager::IsDockSiteMenu](#isdocksitemenu)|Açılır menü tüm bölmeleri etiketlerinin görüntülenip görüntülenmeyeceğini belirtir.|  
|[CDockingManager::IsInAdjustLayout](#isinadjustlayout)|Tüm bölmeleri düzenleri ayarlanır belirler.|  
|[CDockingManager::IsOLEContainerMode](#isolecontainermode)|Yerleştirme Yöneticisi OLE kapsayıcı modunda olup olmadığını belirtir.|  
|[CDockingManager::IsPointNearDockSite](#ispointneardocksite)|Belirli bir noktaya yerleştirme site olup olmadığını belirler.|  
|[CDockingManager::IsPrintPreviewValid](#isprintpreviewvalid)|Baskı Önizleme modunu ayarlanmış olup olmadığını belirler.|  
|[CDockingManager::LoadState](#loadstate)|Yerleştirme yöneticinin durum kayıt defterinden yükler.|  
|[CDockingManager::LockUpdate](#lockupdate)|Belirtilen pencere kilitler.|  
|[CDockingManager::OnActivateFrame](#onactivateframe)|Çerçeve penceresi etkinleştirilir veya devre dışı olduğunda çerçevesi tarafından çağrılır.|  
|[CDockingManager::OnClosePopupMenu](#onclosepopupmenu)|Etkin bir açılır menü WM_DESTROY ileti işlediğinde çerçevesi tarafından çağrılır.|  
|[CDockingManager::OnMoveMiniFrame](#onmoveminiframe)|Bir kısa çerçeve penceresi taşımak için çerçevesi tarafından çağrılır.|  
|[CDockingManager::OnPaneContextMenu](#onpanecontextmenu)|Bölmeleri listesini içeren bir menü oluşturduğunda çerçevesi tarafından çağrılır.|  
|[CDockingManager::PaneFromPoint](#panefrompoint)|Belirtilen noktasını içeren bölme döndürür.|  
|[CDockingManager::ProcessPaneContextMenuCommand](#processpanecontextmenucommand)|Seçin veya belirtilen komut bir onay kutusunu temizleyin ve gösterilen bölmesinin düzenini yeniden hesapla çerçevesi tarafından çağrılır.|  
|[CDockingManager::RecalcLayout](#recalclayout)|Denetimleri listesinde denetimlerin iç düzenini yeniden hesaplar.|  
|[CDockingManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|Boş bölmesinde kapsayıcıları serbest bırakır.|  
|[CDockingManager::RemoveHiddenMDITabbedBar](#removehiddenmditabbedbar)|Belirtilen bölmesinde gizli kaldırır.|  
|[CDockingManager::RemoveMiniFrame](#removeminiframe)|Belirtilen çerçeve mini çerçeveler listesinden kaldırır.|  
|[CDockingManager::RemovePaneFromDockManager](#removepanefromdockmanager)|Bir bölme kaydını siler ve yerleştirme Yöneticisi listesinden kaldırır.|  
|[CDockingManager::ReplacePane](#replacepane)|Bir bölme birbiriyle değiştirir.|  
|[CDockingManager::ResortMiniFramesForZOrder](#resortminiframesforzorder)|Mini çerçeveler listesi çerçevelere resorts.|  
|[CDockingManager::SaveState](#savestate)|Kayıt defterine takma Yöneticisi'nin durumunu kaydeder.|  
|[CDockingManager::SendMessageToMiniFrames](#sendmessagetominiframes)|Belirtilen iletiyi tüm mini çerçevelerine gönderir.|  
|[CDockingManager::Serialize](#serialize)|Yerleştirme Yöneticisi arşive yazar. (Geçersiz kılmaları [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CDockingManager::SetAutohideZOrder](#setautohidezorder)|Boyutu, genişlik ve yükseklik denetim çubukları ve belirtilen bölmesinin ayarlar.|  
|[CDockingManager::SetDockingMode](#setdockingmode)|Yerleştirme modunu ayarlar.|  
|[CDockingManager::SetDockState](#setdockstate)|Denetim çubukları, mini çerçeveler ve autohide çubukları yerleştirme durumunu ayarlar.|  
|[CDockingManager::SetPrintPreviewMode](#setprintpreviewmode)|Baskı Önizlemede görüntülenen çubukları Baskı Önizleme modunu ayarlar.|  
|[CDockingManager::SetSmartDockingParams](#setsmartdockingparams)|Akıllı Yerleştirme davranışını tanımlayan parametreleri ayarlar.|  
|[CDockingManager::ShowDelayShowMiniFrames](#showdelayshowminiframes)|Gösterir veya gizler windows mini çerçeve.|  
|[CDockingManager::ShowPanes](#showpanes)|Gösterir veya gizler denetimi ve autohide çubukları bölmeleri.|  
|[CDockingManager::StartSDocking](#startsdocking)|Belirtilen pencere akıllı yerleştirme Yöneticisi hizalamasını göre akıllı yerleştirme başlatır.|  
|[CDockingManager::StopSDocking](#stopsdocking)|Yerleştirme durakları akıllı.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|Yerleştirme Yöneticisi OLE kapsayıcı modu bölmelerinde gizler olup olmadığını belirtir.|  
|[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)|Genel takma modunu belirtir.|  
|[CDockingManager::m_nDockSensitivity](#m_ndocksensitivity)|Yerleştirme duyarlılığını belirtir.|  
|[CDockingManager::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|Yerleştirme bölmesi hemen yerleştirme modunda yuvalanmış önce süreyi milisaniye cinsinden belirtir.|  
|[CDockingManager::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|Bir araç çubuğunun ana çerçeve penceresi sabit önce süreyi milisaniye cinsinden belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ana çerçeve penceresi oluşturur ve bu sınıfın otomatik olarak başlatır.  
  
 Yerleştirme Yöneticisi nesnesi takma düzende olan tüm bölmeleri listesini ve tüm listesini tutar [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) ana çerçeve penceresi ait windows.  
  
 `CDockingManager` Sınıfı uygulayan bir bölme bulmak için kullanabileceğiniz bazı hizmetler veya `CPaneFrameWnd` penceresi. Ana çerçeve penceresi nesnesinde sarılır olduğundan, genellikle bu hizmetleri doğrudan çağırmanız gerekmez. Daha fazla bilgi için bkz: [CPaneFrameWnd sınıfı](../../mfc/reference/cpaneframewnd-class.md).  
  
## <a name="customization-tips"></a>Özelleştirme ipuçları  
 Aşağıdaki ipuçları uygulamak `CDockingManager` nesneler:  
  
- [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) bu takma modlarını destekler:  
  
    - `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    - `AFX_DOCK_TYPE::DT_STANDARD`  
  
    - `AFX_DOCK_TYPE::DT_SMART`  
  
     Bu yerleşik modları tarafından tanımlanan [CDockingManager::m_dockModeGlobal](#m_dockmodeglobal) ve çağırarak ayarlanır [CDockingManager::SetDockingMode](#setdockingmode).  
  
-   Bir değişken olmayan, yeniden boyutlandırılabilir olmayan bölmesi oluşturmak istiyorsanız, çağrı [CDockingManager::AddPane](#addpane) yöntemi. Bu yöntem bölmesinde bölmesinin düzenini sorumludur takma Yöneticisi ile kaydeder.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CDockingManager` yapılandırmak için sınıf bir `CDockingManager` nesnesi. Örnek nesnesinin takma modunu ayarlama ve tüm takma bölmeleri etiketlerinin açılır menüde açar ek bir düğmesi görüntülemek nasıl gösterir. Bu kod parçacığını parçası olan [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxDockingManager.h  
  
##  <a name="adddocksite"></a>CDockingManager::AddDockSite  
 Bir yuva bölmesi oluşturur ve denetim çubukları listesine ekler.  
  
```  
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`info`  
 Bir başvuru içeren bir bilgi yapısı bölmesinde hizalama sabitleyin.  
  
 [out]`ppDockBar`  
 Yeni bir yuva bölmesi için bir işaretçi bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yerleştirme bölmesinde başarıyla oluşturulduysa; `FALSE` Aksi takdirde.  
  
##  <a name="addhiddenmditabbedbar"></a>CDockingManager::AddHiddenMDITabbedBar  
 Bir çubuğuna tanıtıcı ekler bölmeler sekmeli gizli MDI listesi bölmesine.  
  
```  
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 Bir işaretçi bir çubuğuna bölmesi  
  
##  <a name="addpane"></a>CDockingManager::AddPane  
 Bir bölme takma Yöneticisi ile kaydeder.  
  
```  
BOOL AddPane(
    CBasePane* pWnd,  
    BOOL bTail = TRUE,  
    BOOL bAutoHide = FALSE,  
    BOOL bInsertForOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [içinde out]`pWnd`  
 Yerleştirme Yöneticisi eklemek için bölmesinde belirtir.  
  
 [in]`bTail`  
 `TRUE`bölmesinde takma yöneticisini bölmeleri listesinin sonuna eklemek için; Aksi takdirde `FALSE`.  
  
 [in]`bAutoHide`  
 Yalnızca dahili kullanım için. Varsayılan değer her zaman kullanmak `FALSE`.  
  
 [in]`bInsertForOuterEdge`  
 Yalnızca dahili kullanım için. Varsayılan değer her zaman kullanmak `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bölmenin yerleştirme yöneticisiyle; başarıyla kaydedildiyse Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayan olmayan, yeniden boyutlandırılabilir olmayan bölmeleri takma Yöneticisi ile kaydetmek için bu yöntemi çağırın. Bölmeleri kaydettirmezseniz takma Yöneticisi düzenlendiğini, bunların doğru görünmez.  
  
##  <a name="adjustdockinglayout"></a>CDockingManager::AdjustDockingLayout  
 Yeniden hesaplar ve tüm bölmeleri bir çerçeve penceresinde düzenini ayarlar.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`hdwp`  
 Ertelenmiş penceresi konumu yapısı belirtir. Daha fazla bilgi için bkz: [Windows veri türleri](http://msdn.microsoft.com/library/windows/desktop/aa383751).  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addminiframe"></a>CDockingManager::AddMiniFrame  
 Bir çerçeve mini çerçeveler listesine ekler.  
  
```  
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWnd`  
 Bir çerçeve işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Çerçeve mini çerçeveler listesinde olmadığından ve başarıyla eklendi `FALSE` Aksi takdirde.  
  
##  <a name="adjustpaneframes"></a>CDockingManager::AdjustPaneFrames  
 Neden `WM_NCCALCSIZE` tüm bölmeleri gönderilecek ileti ve `CPaneFrameWnd` windows.  
  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="adjustrecttoclientarea"></a>CDockingManager::AdjustRectToClientArea  
 Dikdörtgene hizalamasını ayarlar.  
  
```  
virtual BOOL AdjustRectToClientArea(
    CRect& rectResult,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rectResult`  
 Bir başvuru bir `CRect` nesnesi  
  
 [in]`dwAlignment`  
 Hizalamasını `CRect` nesnesi  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`varsa hizalamasını `CRect` nesne ayarlandı; `FALSE` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 `dwAlignment` Parametresi şu değerlerden biri olabilir:  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="alignautohidepane"></a>CDockingManager::AlignAutoHidePane  
 Autohide modu takma bölmesinde tam genişliğini alır veya tarafından çevrelenen çerçeve istemci alanının yüksekliğini yerleştirme siteleri göre yeniden boyutlandırır.  
  
```  
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,  
    BOOL bIsVisible = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDefaultSlider`  
 Yerleştirme kaydırıcı bölmesi.  
  
 [in]`bIsVisible`  
 `TRUE`yerleştirme bölmesinde görünür durumdaysa; `FALSE` Aksi takdirde.  
  
##  <a name="autohidepane"></a>CDockingManager::AutoHidePane  
 Autohide araç oluşturur.  
  
```  
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,  
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 Bir işaretçi çubuğuna bölmesi.  
  
 [in]`pCurrAutoHideToolBar`  
 Bir Otomatik Gizle araç için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `NULL`araç çubuğu otomatik gizlemek oluşturulmadı; Aksi halde yeni araç için bir işaretçi.  
  
##  <a name="bringbarstotop"></a>CDockingManager::BringBarsToTop  
 Belirtilen hizalama üstüne sahip yerleşik çubukları getirir.  
  
```  
void BringBarsToTop(
    DWORD dwAlignment = 0,  
    BOOL bExcludeDockedBars = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`dwAlignment`  
 Diğer windows üst kısmına yönlendirilirsiniz yerleştirme çubukları hizalaması.  
  
 [in]`bExcludeDockedBars`  
 `TRUE`Yerleşik çubukları üstte dışında bırakmak için; Aksi takdirde `FALSE`.  
  
##  <a name="buildpanesmenu"></a>CDockingManager::BuildPanesMenu  
 Yerleştirme bölmeleri ve araç çubuklarını adları menüye ekler.  
  
```  
void BuildPanesMenu(
    CMenu& menu,  
    BOOL bToolbarsOnly);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`menu`  
 Yerleştirme bölmeleri ve araç çubukları adları eklemek için bir menü.  
  
 [in]`bToolbarsOnly`  
 `TRUE`yalnızca araç çubuğu adları menüsüne eklemek için; `FALSE` Aksi takdirde.  
  
##  <a name="calcexpecteddockedrect"></a>CDockingManager::CalcExpectedDockedRect  
 Yerleşik pencerenin beklenen dikdörtgen hesaplar.  
  
```  
void CalcExpectedDockedRect(
    CWnd* pWnd,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWnd`  
 Pencere sabitlemek için bir işaretçi.  
  
 [in]`ptMouse`  
 Fare konumu.  
  
 [out]`rectResult`  
 Hesaplanan dikdörtgen.  
  
 [in]`bDrawTab`  
 `TRUE`Sekme çizmek için; Aksi takdirde `FALSE`.  
  
 [out]`ppTargetBar`  
 Hedef bölmesi için bir işaretçi bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir kullanıcı tarafından belirtilen noktasına penceresi Sürüklediyseniz, bir pencere kaplar dikdörtgen hesaplar `ptMouse` ve var. yerleştirildi.  
  
##  <a name="create"></a>CDockingManager::Create  
 Yerleşik yönetici oluşturur.  
  
```  
BOOL Create(CFrameWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pParentWnd`  
 Yerleştirme Yöneticisi'nin üst çerçeve için bir işaretçi. Bu değer olmamalıdır `NULL`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`her zaman.  
  
##  <a name="determinepaneandstatus"></a>CDockingManager::DeterminePaneAndStatus  
 Verilen bir noktaya ve takma durumunu içeren bölme belirler.  
  
```  
virtual AFX_CS_STATUS DeterminePaneAndStatus(
    CPoint pt,  
    int nSensitivity,  
    DWORD dwEnabledAlignment,  
    CBasePane** ppTargetBar,  
    const CBasePane* pBarToIgnore,  
    const CBasePane* pBarToDock);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pt`  
 Denetlenecek bölmesi konumu.  
  
 [in]`nSensitivity`  
 Her checked bölmesinin Pencere dikdörtgeni artırmak için değer. Belirtilen noktasını artan bu bölgede ise bir bölmesi arama ölçütleri karşılar.  
  
 [in]`dwEnabledAlignment`  
 Yerleştirme bölmesinde hizalaması.  
  
 [out]`ppTargetBar`  
 Hedef bölmesi için bir işaretçi bir işaretçi.  
  
 [in]`pBarToIgnore`  
 Yöntemi yok sayıyor bölme.  
  
 [in]`pBarToDock`  
 Yerleşik olduğunda bölme.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Takma durumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerleştirme durum aşağıdaki değerlerden biri olabilir:  
  
|AFX_CS_STATUS değeri|Açıklama|  
|---------------------------|-------------|  
|CS_NOTHING|İşaretçinin yerleştirme site değil. Bu nedenle, bölmesinde tutmak kayan.|  
|CS_DOCK_IMMEDIATELY|Anlık mod yerleştirme sitede üzerinden işaretçidir (DT_IMMEDIATE stili etkinleştirildi) hemen bölmesi yuvalanmış şekilde.|  
|CS_DELAY_DOCK|Başka bir takma bölmesi olan veya bir ana çerçeve kenarı bir yerleştirme sitesi işaretçidir.|  
|CS_DELAY_DOCK_TO_TAB|Sekmeli penceresinde yerleşik için bölmesinde neden olan bir yerleştirme sitesi üzerinden işaretçidir. Fare başka bir takma bölmesinde bir resim yazısını veya sekmeli bölmesinin sekme alanı üzerinden bu oluşur.|  
  
##  <a name="disablerestoredockstate"></a>CDockingManager::DisableRestoreDockState  
 Etkinleştirir veya kayıt defterinden yerleştirme düzeni yüklenmesini devre dışı bırakır.  
  
```  
void DisableRestoreDockState(BOOL bDisable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bDisable`  
 `TRUE`kayıt defterinden yerleştirme düzeni yüklenmesini devre dışı bırakmak için; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama durumu yüklenirken takma bölmeleri ve araç çubuklarını geçerli düzenini korumaya aldığınızda bu yöntemi çağırın.  
  
##  <a name="dockpane"></a>CDockingManager::DockPane  
 Bir bölme başka bir bölme ya da bir çerçeve penceresinde docks.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 Bir işaretçi bir çubuğuna için sabitlemek için bölmesi.  
  
 [in]`nDockBarID`  
 Yerleştirme için çubuğunda kimliği.  
  
 [in]`lpRect`  
 Hedef dikdörtgen.  
  
##  <a name="dockpaneleftof"></a>CDockingManager::DockPaneLeftOf  
 Bir bölme başka bir bölme soluna docks.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBarToDock,  
    CPane* pTargetBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBarToDock`  
 Bir işaretçi solunda yerleşik bölmesine `pTargetBar`.  
  
 [in]`pTargetBar`  
 Hedef bölmesi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bölmesi başarıyla; yuvalanmış varsa Aksi takdirde `FALSE`.  
  
##  <a name="enableautohidepanes"></a>CDockingManager::EnableAutoHidePanes  
 Ana çerçeve bölmesinde yerleştirme sağlar, yerleştirme bölmesini oluşturur ve denetim çubukları listesine ekler.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`dwStyle`  
 Yerleştirme hizalaması.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yerleştirme bölmesinde başarıyla oluşturulduysa; `FALSE` Aksi takdirde.  
  
##  <a name="enabledocking"></a>CDockingManager::EnableDocking  
 Yerleştirme bölmesini oluşturur ve ana çerçeve bölmesinde yerleştirme sağlar.  
  
```  
BOOL EnableDocking(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`dwStyle`  
 Yerleştirme hizalaması.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yerleştirme bölmesinde başarıyla oluşturulduysa; `FALSE` Aksi takdirde.  
  
##  <a name="enabledocksitemenu"></a>CDockingManager::EnableDockSiteMenu  
 Tüm takma bölmeleri etiketlerinin açılır menüde açar ek bir düğme görüntülenir.  
  
```  
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
 `TRUE`yerleştirme site menü etkinleştirmek için; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerleştirme site menü bölmesinde takma durumunu değiştirmek için aşağıdaki seçenekleri görüntüler:  
  
- `Floating`-Bir bölme gezinen  
  
- `Docking`-Bölmesinde bölmesinde en son ne nerede yerleşik konumdaki ana kare docks  
  
- `AutoHide`-Bölmesinde autohide moduna geçer  
  
- `Hide`-Bir bölmesini gizler  
  
 Varsayılan olarak, bu menü gösterilmez.  
  
##  <a name="enablepanecontextmenu"></a>CDockingManager::EnablePaneContextMenu  
 Kullanıcı farenin sağ düğmesiyle tıkladığında ve kitaplık WM_CONTEXTMENU iletiyi işlemeyi uygulama araç çubukları yerleştirme bölmeleri bir listesine sahip bir özel bağlam menüsünü görüntülemek için kitaplık söyler.  
  
```  
void EnablePaneContextMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeText,  
    BOOL bToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
 Varsa `TRUE`, kitaplık otomatik bağlam menüsü; desteği, açar `FALSE` otomatik bağlam menüsü desteği kitaplığı kapatır.  
  
 [in]`uiCustomizeCmd`  
 Komut kimliği için **Özelleştir** menü öğesi.  
  
 [in]`strCustomizeText`  
 Metnin **Özelleştir** öğesi.  
  
 [in]`bToolbarsOnly`  
 Varsa `TRUE`, menü uygulama araç çubukları; yalnızca bir listesini görüntüler `FALSE`, kitaplık uygulaması takma bölmeleri bu listeye ekler.  
  
##  <a name="finddocksite"></a>CDockingManager::FindDockSite  
 Çubuğu alır, belirtilen konumda olan ve belirtilen hizalama olan bölmesi.  
  
```  
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,  
    BOOL bOuter);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`dwAlignment`  
 Çubuğu hizalamasını bölmesi.  
  
 [in]`bOuter`  
 Varsa `TRUE`, Denetim çubukları baş konumunu listesinde çubuğunda alın. Aksi takdirde, Denetim çubukları listesinde tail konumunu çubuğunda alın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen hizalama sahip ve yerleştirme bölmesinde; `NULL` Aksi takdirde.  
  
##  <a name="findpanebyid"></a>CDockingManager::FindPaneByID  
 Bir bölme belirtilen denetim kimliğe göre bulur  
  
```  
virtual CBasePane* FindPaneByID(
    UINT uBarID,  
    BOOL bSearchMiniFrames = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uBarID`  
 Bulunacak bölmesinde denetim Kimliğini belirtir.  
  
 [in]`bSearchMiniFrames`  
 `TRUE`tüm kayan bölmeleri aramasına dahil etmek için. `FALSE`yalnızca yerleşik bölmeler eklemek için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 [CBasePane](../../mfc/reference/cbasepane-class.md) belirtilen denetim Kimliğine sahip nesne veya `NULL` belirtilen bölmesinde bulunamazsa.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="finddocksitebypane"></a>CDockingManager::FindDockSiteByPane  
 Çubuğu döndürür hedef çubuğu bölmesinin kimliğine sahip bölmesi.  
  
```  
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pTargetBar`  
 Hedef çubuğu bölmesi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çubuğu hedef çubuğu bölmesinin; kimliğine sahip bölmesi `NULL` yok gibi bölmesinde çubuğu varsa.  
  
##  <a name="fixupvirtualrects"></a>CDockingManager::FixupVirtualRects  
 Sanal dikdörtgenler tüm geçerli araç konumlara kaydeder.  
  
```  
virtual void FixupVirtualRects();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı bir araç sürükleyin başladığında, uygulama içindeki özgün konumuna hatırlıyor *sanal dikdörtgen*. Kullanıcı kendi yerleştirme site bir araç çubuğu geçtiğinde, araç diğer araç çubukları değişebilir. Diğer araç çubuklarını özgün konumlarına karşılık gelen sanal dikdörtgenlerin içinde depolanır.  
  
##  <a name="framefrompoint"></a>CDockingManager::FrameFromPoint  
 Belirtilen noktasını içeren çerçeveyi döndürür.  
  
```  
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,  
    CPaneFrameWnd* pFrameToExclude,  
    BOOL bFloatMultiOnly) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pt`  
 Noktası denetlemek için ekran koordinatları olarak belirtir.  
  
 [in]`pFrameToExclude`  
 Dışlamak için bir çerçeve işaretçisi.  
  
 [in]`bFloatMultiOnly`  
 `TRUE`örneklerini olmayan çerçeveleri dışlamak için `CMultiPaneFrameWnd`; `FALSE` Aksi takdirde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen noktasını içeren çerçeveyi; `NULL` Aksi takdirde.  
  
##  <a name="getclientareabounds"></a>CDockingManager::GetClientAreaBounds  
 İstemci alanını sınırlarına içeren dikdörtgen alır.  
  
```  
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`rcClient`  
 İstemci alanını sınırlarına içeren dikdörtgen bir başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İstemci alanını sınırlarına içeren dikdörtgen.  
  
##  <a name="getdockingmode"></a>CDockingManager::GetDockingMode  
 Geçerli yerleştirme modu döndürür.  
  
```  
static AFX_DOCK_TYPE GetDockingMode();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli takma modunu temsil eden bir numaralandırıcı değer. Aşağıdaki değerlerden biri olabilir:  
  
- `DT_STANDARD`  
  
- `DT_IMMEDIATE`  
  
- `DT_SMART`  
  
### <a name="remarks"></a>Açıklamalar  
 Yerleştirme modunu ayarlamak için arama [CDockingManager::SetDockingMode](#setdockingmode).  
  
##  <a name="getdocksiteframewnd"></a>CDockingManager::GetDockSiteFrameWnd  
 Bir işaretçi üst pencere çerçevesi için alır.  
  
```  
CFrameWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üst pencere çerçevesi için bir işaretçi.  
  
##  <a name="getenabledautohidealignment"></a>CDockingManager::GetEnabledAutoHideAlignment  
 Bölmeleri etkin hizalamasını döndürür.  
  
```  
DWORD GetEnabledAutoHideAlignment() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit düzeyinde bileşimini `CBRS_ALIGN_` bayrakları veya autohide bölmeleri etkin olmayan yoksa 0. Daha fazla bilgi için bkz: [CFrameWnd::EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking).  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem autohide denetim çubukları etkin hizalamasını döndürür. AutoHide çubuklarını etkinleştirmek için arama [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes).  
  
##  <a name="getminiframes"></a>CDockingManager::GetMiniFrames  
 Miniframes listesini alır.  
  
```  
const CObList& GetMiniFrames() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerleştirme Manager'a ait denetim çubukları içeren miniframes listesi.  
  
##  <a name="getouteredgebounds"></a>CDockingManager::GetOuterEdgeBounds  
 Çerçeve dış kenarlarını içeren bir dikdörtgen alır.  
  
```  
CRect GetOuterEdgeBounds() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çerçeve dış kenarlarını içeren bir dikdörtgen.  
  
##  <a name="getpanelist"></a>CDockingManager::GetPaneList  
 Yerleştirme Manager'a ait bölmeleri listesini döndürür. Bu, tüm kayan bölmeleri içerir.  
  
```  
void GetPaneList(
    CObList& lstBars,  
    BOOL bIncludeAutohide = FALSE,  
    CRuntimeClass* pRTCFilter = NULL,  
    BOOL bIncludeTabs = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [içinde out]`lstBars`  
 Geçerli takma Yöneticisi'nin tüm bölmeleri içerir.  
  
 [in]`bIncludeAutohide`  
 `TRUE`autohide modda bölmeleri dahil etmek için; Aksi takdirde `FALSE`.  
  
 [in]`pRTCFilter`  
 Aksi takdirde `NULL`, döndürülen liste bölmeleri yalnızca belirtilen çalışma zamanı sınıfı içerir.  
  
 [in]`bIncludeTabs`  
 `TRUE`sekmeler dahil etmek için; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerleştirme Yöneticisi'nde herhangi sekmeli bölmeleri varsa, işaretçileri yöntem [CBaseTabbedPane sınıfı](../../mfc/reference/cbasetabbedpane-class.md) nesneleri ve gerekir listeleme sekmeleri açıkça.  
  
 Kullanım `pRTCFilter` bölmeleri, belirli bir sınıfın elde edilir. Örneğin, bu değeri uygun şekilde ayarlayarak yalnızca araç çubukları elde edebilirsiniz.  
  
##  <a name="getsmartdockingmanager"></a>CDockingManager::GetSmartDockingManager  
 Akıllı Yerleştirme Yöneticisi için bir işaretçi alır.  
  
```  
CSmartDockingManager* GetSmartDockingManager();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [akıllı yerleştirme Yöneticisi](http://msdn.microsoft.com/en-us/f537a1a6-fb9e-41d7-952f-0f25d5ee7534).  
  
##  <a name="getsmartdockingmanagerpermanent"></a>CDockingManager::GetSmartDockingManagerPermanent  
 Akıllı Yerleştirme Yöneticisi için bir işaretçi alır.  
  
```  
CSmartDockingManager* GetSmartDockingManagerPermanent() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akıllı Yerleştirme Yöneticisi için bir işaretçi.  
  
##  <a name="getsmartdockingparams"></a>CDockingManager::GetSmartDockingParams  
 Akıllı Yerleştirme parametreleri için takma Yöneticisi döndürür.  
  
```  
static CSmartDockingInfo& GetSmartDockingParams();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli takma Yöneticisi için akıllı yerleştirme parametreleri içeren sınıf. Daha fazla bilgi için bkz: [CSmartDockingInfo sınıfı](../../mfc/reference/csmartdockinginfo-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hideautohidepanes"></a>CDockingManager::HideAutoHidePanes  
 Autohide modunda olan bir bölmesini gizler.  
  
```  
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,  
    BOOL bImmediately = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBarToExclude`  
 Bir işaretçi gizleme dışlanacak çubuğuna.  
  
 [in]`bImmediately`  
 `TRUE`bölmesini hemen gizlemek için; `FALSE` autohide etkisi bölmesiyle gizlemek için.  
  
##  <a name="insertdocksite"></a>CDockingManager::InsertDockSite  
 Bir yuva bölmesi oluşturur ve denetim çubukları listesine ekler.  
  
```  
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,  
    DWORD dwAlignToInsertAfter,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`info`  
 Yerleştirme bölmesinde hizalama bilgilerini içeren yapısı.  
  
 [in]`dwAlignToInsertAfter`  
 Yerleştirme bölmesinde hizalaması.  
  
 [out]`ppDockBar`  
 Bir yuva bölmesi için bir işaretçi bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yerleştirme bölmesinde başarıyla oluşturulduysa; `FALSE` Aksi takdirde.  
  
##  <a name="insertpane"></a>CDockingManager::InsertPane  
 Denetim Masası denetim çubukları listesine ekler.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pControlBar`  
 Bir denetim bölmesi için bir işaretçi.  
  
 [in]`pTarget`  
 Bir hedef bölmesi için bir işaretçi.  
  
 [in]`bAfter`  
 `TRUE`Hedef bölmesinde konumundan sonra bölmesi eklemek için; `FALSE` Aksi takdirde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Denetim Masası denetim çubukları listesine başarıyla eklendi `FALSE` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, Denetim Masası zaten denetim çubukları listesinde ise veya hedef bölmesinde denetim çubukları listesinde mevcut değilse false döndürür.  
  
##  <a name="isdocksitemenu"></a>CDockingManager::IsDockSiteMenu  
 Açılır menü tüm bölmeleri etiketlerinin görüntülenip görüntülenmeyeceğini belirtir.  
  
```  
static BOOL IsDockSiteMenu();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bir yuva site menü tüm takma bölmeleri başlıkları görüntüleniyorsa, Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırarak yerleştirme site menüsünden etkinleştirebilirsiniz [CDockingManager::EnableDockSiteMenu](#enabledocksitemenu).  
  
##  <a name="isinadjustlayout"></a>CDockingManager::IsInAdjustLayout  
 Tüm bölmeleri düzenleri ayarlanır belirler.  
  
```  
BOOL IsInAdjustLayout() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Tüm bölmeleri düzenleri değiştirdiyseniz; `FALSE` Aksi takdirde.  
  
##  <a name="isolecontainermode"></a>CDockingManager::IsOLEContainerMode  
 Yerleştirme Yöneticisi OLE kapsayıcı modunda olup olmadığını belirtir.  
  
```  
BOOL IsOLEContainerMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yerleştirme Yöneticisi OLE kapsayıcı modundaysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 OLE kapsayıcı modunda tüm takma bölmeleri ve uygulama araç çubukları gizli. Ayarladığınız bölmeleri aynı zamanda bu modda gizlenir [CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode) için `TRUE`.  
  
##  <a name="ispointneardocksite"></a>CDockingManager::IsPointNearDockSite  
 Belirli bir noktaya yerleştirme site olup olmadığını belirler.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`point`  
 Belirtilen nokta.  
  
 [out]`dwBarAlignment`  
 Hangi uç noktasıdır yakın belirtir. Olası değerler şunlardır: `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP`, ve `CBRS_ALIGN_BOTTOM`.  
  
 [out]`bOuterEdge`  
 `TRUE`yerleştirme site dış kenarlık noktasıdır `FALSE` Aksi takdirde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`noktası yerleştirme sitesiyse; Aksi takdirde `FALSE`.  
  
##  <a name="isprintpreviewvalid"></a>CDockingManager::IsPrintPreviewValid  
 Baskı Önizleme modunu ayarlanmış olup olmadığını belirler.  
  
```  
BOOL IsPrintPreviewValid() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Baskı Önizleme modunu ayarlarsanız; `FALSE` Aksi takdirde.  
  
##  <a name="loadstate"></a>CDockingManager::LoadState  
 Yerleştirme yöneticinin durum kayıt defterinden yükler.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszProfileName`  
 Profil adı.  
  
 [in]`uiID`  
 Yerleştirme Yöneticisi kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Yuva Yöneticisi durumu başarıyla yüklendiyse; Aksi takdirde `FALSE`.  
  
##  <a name="lockupdate"></a>CDockingManager::LockUpdate  
 Belirtilen pencere kilitler.  
  
```  
void LockUpdate(BOOL bLock);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bLock`  
 `TRUE`pencerenin kilitliyse; `FALSE` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir pencere kilitlendiğinde taşınamaz ve onu düzenlenemez.  
  
##  <a name="m_bhidedockingbarsincontainermode"></a>CDockingManager::m_bHideDockingBarsInContainerMode  
 Yerleştirme Yöneticisi OLE kapsayıcı modu bölmelerinde gizler olup olmadığını belirtir.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer ayarlanırsa `FALSE` görünür ana çerçeve yerleşik tüm bölmeleri tutmak istiyorsanız uygulama olduğunda OLE kapsayıcı modunda. Varsayılan olarak, bu değer `TRUE`.  
  
##  <a name="m_dockmodeglobal"></a>CDockingManager::m_dockModeGlobal  
 Genel takma modunu belirtir.  
  
```  
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, her takma bölmesinde bu takma modunu kullanır. Bu alan için ayarlanabilir değerleri hakkında daha fazla bilgi için bkz: [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).  
  
##  <a name="m_ndocksensitivity"></a>CDockingManager::m_nDockSensitivity  
 Yerleştirme duyarlılığını belirtir.  
  
```  
AFX_IMPORT_DATA static int m_nDockSensitivity;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ne kadar yakın bir kayan takma duyarlılık tanımlar bölmesinde yaklaşan bir takma bölmesi, yerleştirme sitesi ya da başka bir bölme framework yerleşik durumunu değiştirmeden önce.  
  
##  <a name="m_ntimeoutbeforedockingbardock"></a>CDockingManager::m_nTimeOutBeforeDockingBarDock  
 Yerleştirme bölmesi hemen yerleştirme modunda yuvalanmış önce süreyi milisaniye cinsinden belirtir.  
  
```  
static UINT m_nTimeOutBeforeDockingBarDock;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme yerleşik önce framework belirtilen süreyi bekler. Bu, kullanıcı hala sürükleyerek sırada yanlışlıkla bir konuma yerleşik gelen bölmesinde önler.  
  
##  <a name="m_ntimeoutbeforetoolbardock"></a>CDockingManager::m_nTimeOutBeforeToolBarDock  
 Bir araç çubuğunun ana çerçeve penceresi sabit önce süreyi milisaniye cinsinden belirtir.  
  
```  
static UINT m_nTimeOutBeforeToolBarDock;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir araç çubuğunun sabit önce framework belirtilen süreyi bekler. Bu araç, kullanıcı hala sürükleyerek sırada yanlışlıkla bir konuma yerleşik gelen önler.  
  
##  <a name="onactivateframe"></a>CDockingManager::OnActivateFrame  
 Çerçeve penceresi etkinleştirilir veya devre dışı olduğunda çerçevesi tarafından çağrılır.  
  
```  
virtual void OnActivateFrame(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bActivate`  
 Varsa `TRUE`, çerçeve penceresi etkin hale if `FALSE`, çerçeve penceresi devre dışı bırakılır.  
  
##  <a name="onclosepopupmenu"></a>CDockingManager::OnClosePopupMenu  
 Etkin bir açılır menü WM_DESTROY ileti işlediğinde çerçevesi tarafından çağrılır.  
  
```  
void OnClosePopupMenu();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli ana pencereyi kapanmak üzere olduğunda framework WM_DESTROY ileti gönderir. Bildirimler işlemek için bu yöntemi geçersiz kılın `CMFCPopupMenu` çerçeve penceresi ait nesneleri olduğunda bir `CMFCPopupMenu` nesne işlemleri bir `WM_DESTROY` ileti.  
  
##  <a name="onmoveminiframe"></a>CDockingManager::OnMoveMiniFrame  
 Bir kısa çerçeve penceresi taşımak için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pFrame`  
 Bir kısa çerçeve penceresi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
##  <a name="onpanecontextmenu"></a>CDockingManager::OnPaneContextMenu  
 Bölmeleri listesini içeren bir menü oluşturduğunda çerçevesi tarafından çağrılır.  
  
```  
void OnPaneContextMenu(CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`point`  
 Menü konumunu belirtir.  
  
##  <a name="panefrompoint"></a>CDockingManager::PaneFromPoint  
 Belirtilen noktasını içeren bölme döndürür.  
  
```  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar = false,  
    CRuntimeClass* pRTCBarType = NULL,  
    BOOL bCheckVisibility = FALSE,  
    const CBasePane* pBarToIgnore = NULL) const;  
  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType = NULL,  
    const CBasePane* pBarToIgnore = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`point`  
 Noktası denetlemek için ekran koordinatları olarak belirtir.  
  
 [in]`nSensitivity`  
 Checked her bölmesinin Pencere dikdörtgeni Şişir değeri. Belirtilen noktasını inflated bu bölgede ise bir bölmesi arama ölçütleri karşılar.  
  
 [in]`bExactBar`  
 `TRUE`yoksaymak için `nSensitivity` parametresi; Aksi halde, `FALSE`.  
  
 [in]`pRTCBarType`  
 Aksi takdirde `NULL`, yalnızca belirtilen türde bölmeleri yöntemi arar.  
  
 [in]`bCheckVisibility`  
 `TRUE`Yalnızca görünür bölmeleri denetlemek için; Aksi takdirde `FALSE`.  
  
 [out]`dwAlignment`  
 Bir bölme belirtilen noktada bulunursa, bu parametre belirtilen noktasına en yakın bölmesinin tarafına içerir. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
 [in]`pBarToIgnore`  
 Aksi takdirde `NULL`, yöntem bu parametresi tarafından belirtilen bölmeleri yok sayar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 [CBasePane](../../mfc/reference/cbasepane-class.md)-belirtilen noktasını içeren nesne türetilmiş veya `NULL` hiçbir bölmesinde bulunduysa.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevi döndürür ve bir bölme bulundu, `dwAlignment` belirtilen noktası hizalamasını içerir. Örneğin, noktası bölmesinde, üst kısmına yakın `dwAlignment` ayarlanır `CBRS_ALIGN_TOP`.  
  
##  <a name="processpanecontextmenucommand"></a>CDockingManager::ProcessPaneContextMenuCommand  
 Seçin veya belirtilen komut bir onay kutusunu temizleyin ve gösterilen bölmesinin düzenini yeniden hesapla çerçevesi tarafından çağrılır.  
  
```  
BOOL ProcessPaneContextMenuCommand(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nID`  
 Denetim çubuğu menüsünden kimliği.  
  
 [in]`nCode`  
 Komut bildirim kodu.  
  
 [in]`pExtra`  
 Bir işaretçi, geçersiz bir işaretçi için Integer `CCmdUI` varsa `nCode` CN_UPDATE_COMMAND_UI değil.  
  
 [in]`pHandlerInfo`  
 Bir bilgi yapısına yönelik işaretçinin. Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`varsa `pEXtra` NULL olmayan ve `nCode` CN_UPDATE_COMMAND_UI, eşittir veya belirtilen bir denetim çubuğu ise `nID`.  
  
##  <a name="recalclayout"></a>CDockingManager::RecalcLayout  
 Denetimleri listesinde denetimlerin iç düzenini yeniden hesaplar.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bNotify`  
 Bu parametre kullanılmaz.  
  
##  <a name="releaseemptypanecontainers"></a>CDockingManager::ReleaseEmptyPaneContainers  
 Boş bölmesinde kapsayıcıları serbest bırakır.  
  
```  
void ReleaseEmptyPaneContainers();
```  
  
##  <a name="removehiddenmditabbedbar"></a>CDockingManager::RemoveHiddenMDITabbedBar  
 Belirtilen bölmesinde gizli kaldırır.  
  
```  
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 Bir işaretçi bir çubuğuna bölmesini kaldırın.  
  
##  <a name="removeminiframe"></a>CDockingManager::RemoveMiniFrame  
 Belirtilen çerçeve mini çerçeveler listesinden kaldırır.  
  
```  
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWnd`  
 Kaldırmak için bir çerçeve işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Belirtilen çerçeve kaldırılırsa; `FALSE` Aksi takdirde.  
  
##  <a name="removepanefromdockmanager"></a>CDockingManager::RemovePaneFromDockManager  
 Bir bölme kaydını siler ve yerleştirme Yöneticisi listesinden kaldırır.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pWnd,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWnd`  
 Bir işaretçi bir bölmesine kaldırılacak.  
  
 [in]`bDestroy`  
 Varsa `TRUE`, kaldırılan bölmesinde yok.  
  
 [in]`bAdjustLayout`  
 Varsa `TRUE`, yerleştirme düzenini hemen ayarlayın.  
  
 [in]`bAutoHide`  
 Varsa `TRUE`, bölmesinde autohide çubukları listesinden kaldırılır. Varsa `FALSE`, bölmesinde normal bölmeleri listesinden kaldırılır.  
  
 [in]`pBarReplacement`  
 Bir işaretçi bir bölmesine kaldırılan bölmesinde yerini alır.  
  
##  <a name="replacepane"></a>CDockingManager::ReplacePane  
 Bir bölme birbiriyle değiştirir.  
  
```  
BOOL ReplacePane(
    CDockablePane* pOriginalBar,  
    CDockablePane* pNewBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pOriginalBar`  
 Özgün bölmesi için bir işaretçi.  
  
 [in]`pNewBar`  
 Bir işaretçi bölmesine özgün bölmesinde yerini alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bölmesinde başarıyla değiştirildi `FALSE` Aksi takdirde.  
  
##  <a name="resortminiframesforzorder"></a>CDockingManager::ResortMiniFramesForZOrder  
 Mini çerçeveler listesi çerçevelere resorts.  
  
```  
void ResortMiniFramesForZOrder();
```  
  
##  <a name="savestate"></a>CDockingManager::SaveState  
 Kayıt defterine takma Yöneticisi'nin durumunu kaydeder.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszProfileName`  
 Bir kayıt defteri anahtarı bir yolu.  
  
 [in]`uiID`  
 Yerleştirme manager kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`durumu başarıyla kaydedildi Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt defteri takma Yöneticisi'nin durumu kaydetmeyi kaydetme denetim çubukları durumlarını, autohide çubukları durumlarını ve yerleştirme Yöneticisi'nde mevcut mini çerçeveler durumlarını içerir.  
  
##  <a name="sendmessagetominiframes"></a>CDockingManager::SendMessageToMiniFrames  
 Belirtilen iletiyi tüm mini çerçevelerine gönderir.  
  
```  
BOOL SendMessageToMiniFrames(
    UINT uMessage,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uMessage`  
 Gönderilecek ileti.  
  
 [in]`wParam`  
 Ek ileti bağımlı bilgileri.  
  
 [in]`lParam`  
 Ek ileti bağımlı bilgileri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`her zaman.  
  
##  <a name="serialize"></a>CDockingManager::Serialize  
 Yerleştirme Yöneticisi arşive yazar.  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`ar`  
 Bir arşiv nesneye bir başvurusu.  
  
### <a name="remarks"></a>Açıklamalar  
 Arşive takma manager yazma, Denetim çubuklarını ve kaydırıcılar yerleştirme ve denetim çubukları, mini çerçeveleri, autohide çubukları ve MDI sekmeli çubukları arşive yazma sayısını belirleme içerir.  
  
##  <a name="setautohidezorder"></a>CDockingManager::SetAutohideZOrder  
 Boyutu, genişlik ve yükseklik denetim çubukları ve belirtilen bölmesinin ayarlar.  
  
```  
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pAHDockingBar`  
 Bir işaretçi dockable bölmesine.  
  
##  <a name="setdockingmode"></a>CDockingManager::SetDockingMode  
 Yerleştirme modunu ayarlar.  
  
```  
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,  
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```  
  
### <a name="parameters"></a>Parametreler  
 `dockMode`  
 Yeni takma modunu belirtir. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
 `theme`  
 İçin akıllı yerleştirme işaretçileri kullanılacak tema belirtir. Aşağıdaki numaralandırılmış değerlerden biri olabilir: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerleştirme modu ayarlamak için statik bu yöntemi çağırın.  
  
 `dockMode`Aşağıdaki değerlerden biri olabilir:  
  
- `DT_STANDARD`-Standart mod Visual Studio .NET 2003'te uygulanan yerleştirme. Bölmeleri sürükleyerek bir bağlam olmadan sürüklenen.  
  
- `DT_IMMEDIATE`-Hemen yerleştirme modu olarak Microsoft Visio uygulanmadı. Bölmeleri sürükleme bağlamla sürüklenen, ancak hiçbir işaretçileri görüntülenir.  
  
- `DT_SMART`-Visual Studio 2005'te uygulanan yerleştirme modu akıllı. Bölmeleri sürükleme bağlamla sürüklenen ve akıllı işaretçiler görüntülenir gösterin bölmesi nerede yuvalanmış.  
  
##  <a name="setdockstate"></a>CDockingManager::SetDockState  
 Denetim çubukları, mini çerçeveler ve autohide çubukları yerleştirme durumunu ayarlar.  
  
```  
virtual void SetDockState();
```  
  
##  <a name="setprintpreviewmode"></a>CDockingManager::SetPrintPreviewMode  
 Baskı Önizlemede görüntülenen çubukları Baskı Önizleme modunu ayarlar.  
  
```  
void SetPrintPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bPreview`  
 `TRUE`Baskı Önizleme modunu ayarlarsanız; `FALSE` Aksi takdirde.  
  
 [in]`pState`  
 Önizleme durumunu gösteren bir işaretçi. Bu parametre kullanılmaz.  
  
##  <a name="setsmartdockingparams"></a>CDockingManager::SetSmartDockingParams  
 Akıllı Yerleştirme davranışını tanımlayan parametreleri ayarlar.  
  
```  
static void SetSmartDockingParams(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>Parametreler  
 [içinde out]`params`  
 Akıllı yerleştirme için parametreleri tanımlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Görünüm, renk veya akıllı yerleştirme işaretçileri şeklini özelleştirmek istiyorsanız bu yöntemi çağırın.  
  
 Varsayılan görünüm için akıllı yerleştirme işaretçileri kullanmak için başlatılmamış örneği geçirmek [CSmartDockingInfo sınıfı](../../mfc/reference/csmartdockinginfo-class.md) için `params`.  
  
##  <a name="showdelayshowminiframes"></a>CDockingManager::ShowDelayShowMiniFrames  
 Gösterir veya gizler windows mini çerçeve.  
  
```  
void ShowDelayShowMiniFrames(BOOL bshow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bShow`  
 `TRUE`gösterilen çerçeve penceresi etkin hale getirmek için; `FALSE to` çerçeve penceresi gizle.  
  
##  <a name="showpanes"></a>CDockingManager::ShowPanes  
 Gösterir veya gizler denetimi ve autohide çubukları bölmeleri.  
  
```  
virtual BOOL ShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bShow`  
 `TRUE`bölmeleri göstermek için; `FALSE to` bölmeleri gizle.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman `FALSE`.  
  
##  <a name="startsdocking"></a>CDockingManager::StartSDocking  
 Belirtilen pencere akıllı yerleştirme Yöneticisi hizalamasını göre akıllı yerleştirme başlatır.  
  
```  
void StartSDocking(CWnd* pDockingWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDockingWnd`  
 Yerleştirme için bir pencere için bir işaretçi.  
  
##  <a name="stopsdocking"></a>CDockingManager::StopSDocking  
 Yerleştirme durakları akıllı.  
  
```  
void StopSDocking();
```  
  
##  <a name="getsmartdockingtheme"></a>CDockingManager::GetSmartDockingTheme  
 Akıllı Yerleştirme işaretçileri görüntülemek için kullanılan tema döndüren bir statik yöntem.  
  
```  
static AFX_SMARTDOCK_THEME __stdcall GetSmartDockingTheme();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki numaralandırılmış değerlerden birini döndürür: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [CFrameWndEx sınıfı](../../mfc/reference/cframewndex-class.md)   
 [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md)   
 [CPaneFrameWnd Sınıfı](../../mfc/reference/cpaneframewnd-class.md)
