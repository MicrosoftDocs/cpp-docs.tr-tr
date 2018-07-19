---
title: CDockingManager sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 87fcaf93823e504f3631d50de4f981ae30e882e9
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027832"
---
# <a name="cdockingmanager-class"></a>CDockingManager sınıfı
Ana çerçeve penceresindeki yerleştirme düzeni denetleyen temel işlevselliğini uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDockingManager : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDockingManager::AddDockSite](#adddocksite)|Bir yerleştirme bölmesi oluşturur ve denetim çubukları listesine ekler.|  
|[CDockingManager::AddHiddenMDITabbedBar](#addhiddenmditabbedbar)|Bir çubuğu için bir tanıtıcı ekler gizli MDI sekmeli bölme listesi bölmesinde.|  
|[CDockingManager::AddMiniFrame](#addminiframe)|Bir çerçeve mini çerçeve listesine ekler.|  
|[CDockingManager::AddPane](#addpane)|Bir bölme yerleştirme Yöneticisi ile kaydeder.|  
|[CDockingManager::AdjustDockingLayout](#adjustdockinglayout)|Yeniden hesaplar ve bir çerçeve penceresi tüm bölmelerde düzenini ayarlar.|  
|[CDockingManager::AdjustPaneFrames](#adjustpaneframes)|Tüm bölmeler için gönderilecek WM_NCCALCSIZE iletisi neden olur ve `CPaneFrameWnd` windows.|  
|[CDockingManager::AdjustRectToClientArea](#adjustrecttoclientarea)|Bir dikdörtgen hizalamasını ayarlar.|  
|[CDockingManager::AlignAutoHidePane](#alignautohidepane)|Otomatik Gizle modunda bir yerleştirme bölmesi tam genişliğini alır veya çevrelenerek çerçevenin istemci alanının yüksekliğini dock siteleri göre yeniden boyutlandırır.|  
|[CDockingManager::AutoHidePane](#autohidepane)|Otomatik Gizle araç oluşturur.|  
|[CDockingManager::BringBarsToTop](#bringbarstotop)|Üst belirtilen hizalamaya sahip yerleşik çubukları getirir.|  
|[CDockingManager::BuildPanesMenu](#buildpanesmenu)|Bir menü adları takma bölme ve araç çubukları ekler.|  
|[CDockingManager::CalcExpectedDockedRect](#calcexpecteddockedrect)|Yerleşik pencere beklenen dikdörtgen hesaplar.|  
|[CDockingManager::Create](#create)|Yerleştirme Yöneticisi oluşturur.|  
|[CDockingManager::DeterminePaneAndStatus](#determinepaneandstatus)|Belirli bir noktaya ve yerleştirme durumunu içeren bölme belirler.|  
|[CDockingManager::DisableRestoreDockState](#disablerestoredockstate)|Etkinleştirir veya kayıt defterinden yerleştirme düzeni yüklenmesini devre dışı bırakır.|  
|[CDockingManager::DockPane](#dockpane)|Bir bölme, başka bir bölme ya da bir çerçeve penceresi docks.|  
|[CDockingManager::DockPaneLeftOf](#dockpaneleftof)|Bir bölme, başka bir bölmesinin solunda docks.|  
|[CDockingManager::EnableAutoHidePanes](#enableautohidepanes)|Yerleştirme bölmesi ana kareye sağlar, bir yerleştirme bölmesi oluşturur ve denetim çubukları listesine ekler.|  
|[CDockingManager::EnableDocking](#enabledocking)|Bir yerleştirme bölmesi oluşturur ve bölmesinde ana çerçevenin takma sağlar.|  
|[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)|Açılır menüde tüm yerleştirme bölmesine Resim yazılarının açan bir düğme görüntülenir.|  
|[CDockingManager::EnablePaneContextMenu](#enablepanecontextmenu)|Kullanıcının sağ fare düğmesine tıkladığında ve kitaplık WM_CONTEXTMENU iletisi işliyor uygulama araç çubukları ve yerleştirme bölmesine bir listesi olan bir özel bağlam menüsünü görüntülemek için kitaplık söyler.|  
|[CDockingManager::FindDockSite](#finddocksite)|Çubuk alır bölmesinde belirtilen konumda olan ve belirtilen hizalamaya sahip.|  
|[CDockingManager::FindDockSiteByPane](#finddocksitebypane)|Çubuk döndürür kimliğinin hedef çubuğu bölmesinin bölmesi.|  
|[CDockingManager::FindPaneByID](#findpanebyid)|Belirtilen denetim kimliğe göre bir bölme bulur|  
|[CDockingManager::FixupVirtualRects](#fixupvirtualrects)|Sanal dikdörtgenler tüm geçerli araç konumlara kaydeder.|  
|[CDockingManager::FrameFromPoint](#framefrompoint)|Belirtilen noktasını içeren çerçeveyi döndürür.|  
|[CDockingManager::GetClientAreaBounds](#getclientareabounds)|İstemci alanı sınırları içeren dikdörtgeni alır.|  
|[CDockingManager::GetDockingMode](#getdockingmode)|Geçerli yerleştirme modunu döndürür.|  
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|Ana pencere çerçevesi için bir işaretçi alır.|  
|[CDockingManager::GetEnabledAutoHideAlignment](#getenabledautohidealignment)|Bölmeleri etkin hizalamasını döndürür.|  
|[CDockingManager::GetMiniFrames](#getminiframes)|Miniframes listesini alır.|  
|[CDockingManager::GetOuterEdgeBounds](#getouteredgebounds)|Çerçeve dış kenarları içeren dikdörtgen alır.|  
|[CDockingManager::GetPaneList](#getpanelist)|Yerleştirme yöneticiye ait bölmeleri listesini döndürür. Bu, tüm kayan bölme içerir.|  
|[CDockingManager::GetSmartDockingManager](#getsmartdockingmanager)|Akıllı Yerleştirme Yöneticisi için bir işaretçi alır.|  
|[CDockingManager::GetSmartDockingManagerPermanent](#getsmartdockingmanagerpermanent)|Akıllı Yerleştirme Yöneticisi için bir işaretçi alır.|  
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|Akıllı Yerleştirme parametrelerini, sabitleme yöneticisini döndürür.|  
|[CDockingManager::GetSmartDockingTheme](#getsmartdockingtheme)|Akıllı Yerleştirme işaretçilerinin görüntülemek için kullanılan bir tema döndüren statik yöntem.|  
|[CDockingManager::HideAutoHidePanes](#hideautohidepanes)|Autohide modunda olan bir bölmesini gizler.|  
|[CDockingManager::InsertDockSite](#insertdocksite)|Bir yerleştirme bölmesi oluşturur ve denetim çubukları listesine ekler.|  
|[CDockingManager::InsertPane](#insertpane)|Denetim Masası, Denetim çubuklarını listesine ekler.|  
|[CDockingManager::IsDockSiteMenu](#isdocksitemenu)|Açılır menü tüm bölmeleri açıklamalı alt yazılar açık görüntülenip görüntülenmeyeceğini belirtir.|  
|[CDockingManager::IsInAdjustLayout](#isinadjustlayout)|Tüm bölmeler düzenleri düzeltilir belirler.|  
|[CDockingManager::IsOLEContainerMode](#isolecontainermode)|Yerleştirme manager OLE kapsayıcı modunda olup olmadığını belirtir.|  
|[CDockingManager::IsPointNearDockSite](#ispointneardocksite)|Belirli bir noktaya dock sitesine olup olmadığını belirler.|  
|[CDockingManager::IsPrintPreviewValid](#isprintpreviewvalid)|Baskı Önizleme modunu ayarlanmış olup olmadığını belirler.|  
|[CDockingManager::LoadState](#loadstate)|Kayıt defterinden yerleştirme Yöneticisi'nin durumunu yükler.|  
|[CDockingManager::LockUpdate](#lockupdate)|Belirtilen pencere kilitler.|  
|[CDockingManager::OnActivateFrame](#onactivateframe)|Çerçeve penceresi etkinleştirilir veya devre dışı olduğunda framework tarafından çağırılır.|  
|[CDockingManager::OnClosePopupMenu](#onclosepopupmenu)|Etkin bir açılan menü WM_DESTROY iletiyi işleyen framework tarafından çağırılır.|  
|[CDockingManager::OnMoveMiniFrame](#onmoveminiframe)|Bir mini çerçeve taşımak için framework tarafından çağırılır.|  
|[CDockingManager::OnPaneContextMenu](#onpanecontextmenu)|Bölmeleri listesini içeren bir menü oluşturduğunda framework tarafından çağırılır.|  
|[CDockingManager::PaneFromPoint](#panefrompoint)|Belirtilen noktasını içeren bölme döndürür.|  
|[CDockingManager::ProcessPaneContextMenuCommand](#processpanecontextmenucommand)|Seçin veya belirtilen komut için bir onay kutusunu temizleyin ve gösterilen bölmesinin düzenini yeniden hesapla için framework tarafından çağırılır.|  
|[CDockingManager::RecalcLayout](#recalclayout)|Denetim listesinde mevcut denetimlerin iç düzenini yeniden hesaplar.|  
|[CDockingManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|Boş bölmesinde kapsayıcıları serbest bırakır.|  
|[CDockingManager::RemoveHiddenMDITabbedBar](#removehiddenmditabbedbar)|Belirtilen bölmesinde gizlenmiş kaldırır.|  
|[CDockingManager::RemoveMiniFrame](#removeminiframe)|Belirtilen bir çerçeve mini çerçeve listesinden kaldırır.|  
|[CDockingManager::RemovePaneFromDockManager](#removepanefromdockmanager)|Bir bölme kaydını siler ve yerleştirme manager listesinden kaldırır.|  
|[CDockingManager::ReplacePane](#replacepane)|Bir bölme birbiriyle değiştirir.|  
|[CDockingManager::ResortMiniFramesForZOrder](#resortminiframesforzorder)|Mini çerçeve listesinde çerçeveleri resorts.|  
|[CDockingManager::SaveState](#savestate)|Yerleştirme yöneticisinin durumu kayıt defterine kaydeder.|  
|[CDockingManager::SendMessageToMiniFrames](#sendmessagetominiframes)|Belirtilen iletiyi için tüm mini çerçeve gönderir.|  
|[CDockingManager::Serialize](#serialize)|Yerleştirme manager arşive yazar. (Geçersiz kılmaları [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CDockingManager::SetAutohideZOrder](#setautohidezorder)|Boyut, genişliğini ve yüksekliğini denetim çubuklarını ve belirtilen bölmesinde ayarlar.|  
|[CDockingManager::SetDockingMode](#setdockingmode)|Yerleştirme modunu ayarlar.|  
|[CDockingManager::SetDockState](#setdockstate)|Denetim çubukları, mini çerçeve ve autohide çubukları yerleştirme durumunu ayarlar.|  
|[CDockingManager::SetPrintPreviewMode](#setprintpreviewmode)|Baskı Önizlemede görüntülenen çubukları Baskı Önizleme modunu ayarlar.|  
|[CDockingManager::SetSmartDockingParams](#setsmartdockingparams)|Akıllı Yerleştirme davranışını tanımlayan parametreler ayarlar.|  
|[CDockingManager::ShowDelayShowMiniFrames](#showdelayshowminiframes)|Windows mini çerçeve gizler veya gösterir.|  
|[CDockingManager::ShowPanes](#showpanes)|Denetim ve autohide çubukların bölmeleri gizler veya gösterir.|  
|[CDockingManager::StartSDocking](#startsdocking)|Belirtilen pencere akıllı yerleştirme manager hizalamasını göre akıllı yerleştirme başlar.|  
|[CDockingManager::StopSDocking](#stopsdocking)|Yerleştirme durur akıllı.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|Yerleştirme manager OLE kapsayıcı modunda bölmeleri gizler olup olmadığını belirtir.|  
|[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)|Genel yerleştirme modunu belirtir.|  
|[CDockingManager::m_nDockSensitivity](#m_ndocksensitivity)|Yerleştirme duyarlılığı belirtir.|  
|[CDockingManager::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|Bir yerleştirme bölmesi hemen yerleştirme modunda yerleştirildiğini önce milisaniye cinsinden süreyi belirtir.|  
|[CDockingManager::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|Ana çerçeve penceresine araç çubuğu yerleştirildiğini önce milisaniye cinsinden süreyi belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ana çerçeve penceresi oluşturur ve bu sınıf otomatik olarak başlatır.  
  
 Yerleştirme Yöneticisi nesnesi yerleştirme düzende olan tüm bölmeleri listesini ve tüm listesini tutar [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) ana çerçeve penceresine ait windows.  
  
 `CDockingManager` Sınıfın uyguladığı bir bölme bulmak için kullanabileceğiniz bazı hizmetler veya `CPaneFrameWnd` penceresi. Ana çerçeve penceresi nesnesinde sarmalanır ve nedeni, genellikle bu hizmetleri doğrudan çağırmaz. Daha fazla bilgi için [CPaneFrameWnd sınıfı](../../mfc/reference/cpaneframewnd-class.md).  
  
## <a name="customization-tips"></a>Özelleştirme ipuçları  
 Aşağıdaki ipuçları uygulamak `CDockingManager` nesneler:  
  
- [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) bu yerleştirme modunu destekler:  
  
    - `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    - `AFX_DOCK_TYPE::DT_STANDARD`  
  
    - `AFX_DOCK_TYPE::DT_SMART`  
  
     Bu takma modları tarafından tanımlanan [CDockingManager::m_dockModeGlobal](#m_dockmodeglobal) çağırarak ayarlayın [CDockingManager::SetDockingMode](#setdockingmode).  
  
-   Değişken olmayan, yeniden boyutlandırılabilir olmayan bir bölme oluşturmak istiyorsanız, çağrı [CDockingManager::AddPane](#addpane) yöntemi. Bu yöntem bölmesinde bölmesinin düzenini sorumlu yerleştirme Yöneticisi ile kaydeder.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CDockingManager` yapılandırmak için sınıf bir `CDockingManager` nesne. Örneğin, nesnesinin yerleştirme modunu ayarlama ve açılır menüde tüm yerleştirme bölmesine Resim yazılarının açan bir düğme görüntülemek nasıl gösterir. Bu kod parçacığı parçasıdır [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxDockingManager.h  
  
##  <a name="adddocksite"></a>  CDockingManager::AddDockSite  
 Bir yerleştirme bölmesi oluşturur ve denetim çubukları listesine ekler.  
  
```  
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bilgileri*  
 Bir başvuru içeren bir bilgi yapısı yerleştirme bölmesi hizalama.  
  
 [out] *ppDockBar*  
 Yeni bir yerleştirme bölmesi için bir işaretçi işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerleştirme bölmesi başarıyla oluşturulursa TRUE; FALSE Aksi takdirde.  
  
##  <a name="addhiddenmditabbedbar"></a>  CDockingManager::AddHiddenMDITabbedBar  
 Bir çubuğu için bir tanıtıcı ekler gizli MDI sekmeli bölme listesi bölmesinde.  
  
```  
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
 İşaretçi çubuk bölmesi  
  
##  <a name="addpane"></a>  CDockingManager::AddPane  
 Bir bölme yerleştirme Yöneticisi ile kaydeder.  
  
```  
BOOL AddPane(
    CBasePane* pWnd,  
    BOOL bTail = TRUE,  
    BOOL bAutoHide = FALSE,  
    BOOL bInsertForOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [out içinde] *pWnd*  
 Yerleştirme Manager'a eklenecek bölmesinde belirtir.  
  
 [in] *bTail*  
 Bölmenin yerleştirme yöneticisini bölmeleri listesinin sonuna eklemek için TRUE; Aksi takdirde FALSE.  
  
 [in] *bAutoHide*  
 Yalnızca iç kullanım içindir. Her zaman varsayılan değeri FALSE kullanın.  
  
 [in] *bInsertForOuterEdge*  
 Yalnızca iç kullanım içindir. Her zaman varsayılan değeri FALSE kullanın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmenin yerleştirme yöneticisiyle başarıyla kaydedildi TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Değişken olmayan, yeniden boyutlandırılabilir olmayan bölmeleri yerleştirme Yöneticisi ile kaydetmek için bu yöntemi çağırın. Bölmeleri kaydetmezseniz, yerleştirme manager düzenlendiğini, bunların doğru şekilde görünmez.  
  
##  <a name="adjustdockinglayout"></a>  CDockingManager::AdjustDockingLayout  
 Yeniden hesaplar ve bir çerçeve penceresi tüm bölmelerde düzenini ayarlar.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *hdwp*  
 Ertelenmiş pencere konumu yapısı belirtir. Daha fazla bilgi için [Windows veri türleri](http://msdn.microsoft.com/library/windows/desktop/aa383751).  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addminiframe"></a>  CDockingManager::AddMiniFrame  
 Bir çerçeve mini çerçeve listesine ekler.  
  
```  
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWnd*  
 Çerçeve işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çerçeve mini çerçeve listesinde değilse ve başarılı bir şekilde eklendiğinde TRUE; FALSE Aksi takdirde.  
  
##  <a name="adjustpaneframes"></a>  CDockingManager::AdjustPaneFrames  
 Tüm bölmeler için gönderilecek WM_NCCALCSIZE iletisi neden olur ve `CPaneFrameWnd` windows.  
  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="adjustrecttoclientarea"></a>  CDockingManager::AdjustRectToClientArea  
 Bir dikdörtgen hizalamasını ayarlar.  
  
```  
virtual BOOL AdjustRectToClientArea(
    CRect& rectResult,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rectResult*  
 Bir başvuru bir `CRect` nesnesi  
  
 [in] *dwAlignment*  
 Hizalama `CRect` nesnesi  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE ise hizalamasını `CRect` nesne ayarlandı; FALSE Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 *DwAlignment* parametre aşağıdaki değerlerden biri olabilir:  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="alignautohidepane"></a>  CDockingManager::AlignAutoHidePane  
 Otomatik Gizle modunda bir yerleştirme bölmesi tam genişliğini alır veya çevrelenerek çerçevenin istemci alanının yüksekliğini dock siteleri göre yeniden boyutlandırır.  
  
```  
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,  
    BOOL bIsVisible = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDefaultSlider*  
 Yerleştirme kaydırıcı bölmesi.  
  
 [in] *bIsVisible*  
 Yerleştirme bölmesi görünür ise TRUE; FALSE Aksi takdirde.  
  
##  <a name="autohidepane"></a>  CDockingManager::AutoHidePane  
 Otomatik Gizle araç oluşturur.  
  
```  
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,  
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
 İşaretçi çubuk bölmesi.  
  
 [in] *pCurrAutoHideToolBar*  
 Bir Otomatik Gizle araç için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Otomatik Gizle araç oluşturulmadı yoksa NULL; Aksi halde yeni araç için bir işaretçi.  
  
##  <a name="bringbarstotop"></a>  CDockingManager::BringBarsToTop  
 Üst belirtilen hizalamaya sahip yerleşik çubukları getirir.  
  
```  
void BringBarsToTop(
    DWORD dwAlignment = 0,  
    BOOL bExcludeDockedBars = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwAlignment*  
 Diğer windows üstüne ulaşırlar dock çubukları hizalaması.  
  
 [in] *bExcludeDockedBars*  
 Yerleşik çubukları üstte dışında bırakmak için TRUE; Aksi durumda FALSE.  
  
##  <a name="buildpanesmenu"></a>  CDockingManager::BuildPanesMenu  
 Bir menü adları takma bölme ve araç çubukları ekler.  
  
```  
void BuildPanesMenu(
    CMenu& menu,  
    BOOL bToolbarsOnly);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *menüsü*  
 Yerleştirme bölmesi ve araç çubukları adları eklemek için bir menü.  
  
 [in] *bToolbarsOnly*  
 Menüyü tek araç adları eklemek için TRUE; FALSE Aksi takdirde.  
  
##  <a name="calcexpecteddockedrect"></a>  CDockingManager::CalcExpectedDockedRect  
 Yerleşik pencere beklenen dikdörtgen hesaplar.  
  
```  
void CalcExpectedDockedRect(
    CWnd* pWnd,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWnd*  
 Pencere sabitlemek için bir işaretçi.  
  
 [in] *ptMouse*  
 Fare konumu.  
  
 [out] *rectResult*  
 Hesaplanan dikdörtgen.  
  
 [in] *bDrawTab*  
 Bir sekme çizim için true; Aksi durumda FALSE.  
  
 [out] *ppTargetBar*  
 Hedef bölmesine bir işaretçi işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir kullanıcı tarafından belirtilen noktasına penceresi Sürüklediyseniz, bir pencere kaplayabilir dikdörtgen hesaplar *ptMouse* ve yerleştirilmiş vardır.  
  
##  <a name="create"></a>  CDockingManager::Create  
 Yerleştirme Yöneticisi oluşturur.  
  
```  
BOOL Create(CFrameWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pParentWnd*  
 Üst çerçevenin takma Yöneticisi için bir işaretçi. Bu değer NULL olmamalıdır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman TRUE.  
  
##  <a name="determinepaneandstatus"></a>  CDockingManager::DeterminePaneAndStatus  
 Belirli bir noktaya ve yerleştirme durumunu içeren bölme belirler.  
  
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
 [in] *pt*  
 Denetlenecek bölmenin konumu.  
  
 [in] *nSensitivity*  
 Her işaretli bölmesinin Pencere dikdörtgeni artırmak için değer. Belirtilen noktasını artan bu bölgede değilse bir bölmesinde arama ölçütlerini karşılar.  
  
 [in] *dwEnabledAlignment*  
 Yerleştirme bölmesi hizalaması.  
  
 [out] *ppTargetBar*  
 Hedef bölmesine bir işaretçi işaretçisi.  
  
 [in] *pBarToIgnore*  
 Yöntem yoksayar bölme.  
  
 [in] *pBarToDock*  
 Sabitlenmiş bölme.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerleştirme durumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerleştirme durumu aşağıdaki değerlerden biri olabilir:  
  
|AFX_CS_STATUS değeri|Açıklama|  
|---------------------------|-------------|  
|CS_NOTHING|İşaretçiyi bir dock sitesine üzerinde değil. Bu nedenle, bölmesinde tutmak kayan.|  
|CS_DOCK_IMMEDIATELY|Anlık mod dock sitesine üzerinden işaretçisidir (DT_IMMEDIATE stili etkindir), hemen bölmenin yerleştirilmiş şekilde.|  
|CS_DELAY_DOCK|Ana çerçevenin kenarına başka bir yerleştirme bölmesi olan veya bir dock sitesine işaretçisidir.|  
|CS_DELAY_DOCK_TO_TAB|Sekmeli penceresinde yerleştirilemediğinde bölmesinde neden olan bir dock sitesine üzerinden işaretçisidir. Fare başka bir yerleştirme bölmesi açıklamalı alt yazı veya sekmeli bir bölmeye sekme alanının üzerinden olduğunda gerçekleşir.|  
  
##  <a name="disablerestoredockstate"></a>  CDockingManager::DisableRestoreDockState  
 Etkinleştirir veya kayıt defterinden yerleştirme düzeni yüklenmesini devre dışı bırakır.  
  
```  
void DisableRestoreDockState(BOOL bDisable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *devre dışı bırakın*  
 Kayıt defterinden yerleştirme düzeni yüklenmesini devre dışı bırakma için true; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama durumu yüklenirken geçerli düzen bölmeleri ve araç çubukları yerleştirme korumaya aldığınızda bu yöntemi çağırın.  
  
##  <a name="dockpane"></a>  CDockingManager::DockPane  
 Bir bölme, başka bir bölme ya da bir çerçeve penceresi docks.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
 İşaretçi çubuk bölmesi için yerleştirmek için.  
  
 [in] *nDockBarID*  
 Sabitlemek için çubuğu kimliği.  
  
 [in] *lpRect*  
 Hedef dikdörtgenin.  
  
##  <a name="dockpaneleftof"></a>  CDockingManager::DockPaneLeftOf  
 Bir bölme, başka bir bölmesinin solunda docks.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBarToDock,  
    CPane* pTargetBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBarToDock*  
 Bir işaretçi solunda yerleştirilemediğinde bölmesine *pTargetBar*.  
  
 [in] *pTargetBar*  
 Hedef bölmesi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde başarıyla yerleştirilmiş TRUE; Aksi takdirde FALSE.  
  
##  <a name="enableautohidepanes"></a>  CDockingManager::EnableAutoHidePanes  
 Yerleştirme bölmesi ana kareye sağlar, bir yerleştirme bölmesi oluşturur ve denetim çubukları listesine ekler.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwStyle*  
 Yerleştirme hizalaması.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerleştirme bölmesi başarıyla oluşturulursa TRUE; FALSE Aksi takdirde.  
  
##  <a name="enabledocking"></a>  CDockingManager::EnableDocking  
 Bir yerleştirme bölmesi oluşturur ve bölmesinde ana çerçevenin takma sağlar.  
  
```  
BOOL EnableDocking(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwStyle*  
 Yerleştirme hizalaması.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerleştirme bölmesi başarıyla oluşturulursa TRUE; FALSE Aksi takdirde.  
  
##  <a name="enabledocksitemenu"></a>  CDockingManager::EnableDockSiteMenu  
 Açılır menüde tüm yerleştirme bölmesine Resim yazılarının açan bir düğme görüntülenir.  
  
```  
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSistemlerde*  
 Dock sitesine menüsünü etkinleştirmek için TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmenin yerleştirme durumunu değiştirmek için aşağıdaki seçeneklerden dock sitesine menü görüntüler:  
  
- `Floating` -Bir bölme kaydırmalar  
  
- `Docking` -Bir ana çerçeve burada bölmesinde son sabitlenmiş konumda bölmesinde docks  
  
- `AutoHide` -Bölmesinde autohide moda geçer  
  
- `Hide` -Bir bölmesini gizler  
  
 Varsayılan olarak, bu menüyü görüntülenmez.  
  
##  <a name="enablepanecontextmenu"></a>  CDockingManager::EnablePaneContextMenu  
 Kullanıcının sağ fare düğmesine tıkladığında ve kitaplık WM_CONTEXTMENU iletisi işliyor uygulama araç çubukları ve yerleştirme bölmesine bir listesi olan bir özel bağlam menüsünü görüntülemek için kitaplık söyler.  
  
```  
void EnablePaneContextMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeText,  
    BOOL bToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSistemlerde*  
 TRUE ise, kitaplık otomatik bağlam menüsü için desteği etkinleştirir; FALSE ise otomatik bağlam menüsü için destek kitaplığı kapatır.  
  
 [in] *uiCustomizeCmd*  
 Bir komut kimliği **Özelleştir** menüsünde öğesi.  
  
 [in] *strCustomizeText*  
 Metnin **Özelleştir** öğesi.  
  
 [in] *bToolbarsOnly*  
 TRUE ise, menü yalnızca uygulama araç çubukları listesini görüntüler; FALSE ise, kitaplık bu listeye uygulama yerleştirme bölmesine ekler.  
  
##  <a name="finddocksite"></a>  CDockingManager::FindDockSite  
 Çubuk alır bölmesinde belirtilen konumda olan ve belirtilen hizalamaya sahip.  
  
```  
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,  
    BOOL bOuter);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwAlignment*  
 Hizalama çubuğu bölmesi.  
  
 [in] *bOuter*  
 TRUE ise denetim çubuklarını baş konumu listesinde çubuğunda alın. Aksi takdirde, Denetim çubuklarını kuyruk konumu listesinde çubuğunda alın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen hizalamaya sahip yerleştirme bölmesi; Bulunmazsa null değerini DÖNDÜRÜR.  
  
##  <a name="findpanebyid"></a>  CDockingManager::FindPaneByID  
 Belirtilen denetim kimliğe göre bir bölme bulur  
  
```  
virtual CBasePane* FindPaneByID(
    UINT uBarID,  
    BOOL bSearchMiniFrames = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uBarID*  
 Bulunacak bölmesi denetim Kimliğini belirtir.  
  
 [in] *bSearchMiniFrames*  
 Tüm kayan bölmeleri aramaya dahil edilmesi için TRUE. Yalnızca yerleşik bölmeler dahil etmek için FALSE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 [CBasePane](../../mfc/reference/cbasepane-class.md) belirtilen bölmesinde bulunamazsa, belirtilen denetim kimliği ya da NULL olan nesne.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="finddocksitebypane"></a>  CDockingManager::FindDockSiteByPane  
 Çubuk döndürür kimliğinin hedef çubuğu bölmesinin bölmesi.  
  
```  
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pTargetBar*  
 Hedef çubuğu bölmesi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çubuk hedef çubuğu bölmesinin; kimliğine sahip bölmesi Hiçbir gibi bölmesinde çubuk yoksa null değerini DÖNDÜRÜR.  
  
##  <a name="fixupvirtualrects"></a>  CDockingManager::FixupVirtualRects  
 Sanal dikdörtgenler tüm geçerli araç konumlara kaydeder.  
  
```  
virtual void FixupVirtualRects();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı araç çubuğunu sürükleyin başladığında, uygulamanın orijinal konumunda hatırlar *sanal dikdörtgen*. Kullanıcı, dock site genelindeki bir araç çubuğu taşındığında, araç diğer araç çubukları kaydırır. Diğer araç çubuklarının özgün konumlarına karşılık gelen sanal dikdörtgenler depolanır.  
  
##  <a name="framefrompoint"></a>  CDockingManager::FrameFromPoint  
 Belirtilen noktasını içeren çerçeveyi döndürür.  
  
```  
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,  
    CPaneFrameWnd* pFrameToExclude,  
    BOOL bFloatMultiOnly) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pt*  
 Noktasını denetlemek için ekran koordinatları olarak belirtir.  
  
 [in] *pFrameToExclude*  
 Dışlamak için bir çerçeve işaretçisi.  
  
 [in] *bFloatMultiOnly*  
 Örneklerini olmayan dışlama çerçeveler için true `CMultiPaneFrameWnd`; FALSE Aksi takdirde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen noktasını içeren çerçeveyi; Bulunmazsa null değerini DÖNDÜRÜR.  
  
##  <a name="getclientareabounds"></a>  CDockingManager::GetClientAreaBounds  
 İstemci alanı sınırları içeren dikdörtgeni alır.  
  
```  
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *rcClient*  
 İstemci alanı sınırları içeren dikdörtgen bir başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İstemci alanı sınırları içeren dikdörtgen.  
  
##  <a name="getdockingmode"></a>  CDockingManager::GetDockingMode  
 Geçerli yerleştirme modunu döndürür.  
  
```  
static AFX_DOCK_TYPE GetDockingMode();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli yerleştirme modunu temsil eden bir numaralandırıcı değeri. Aşağıdaki değerlerden biri olabilir:  
  
- DT_STANDARD  
  
- DT_IMMEDIATE  
  
- DT_SMART  
  
### <a name="remarks"></a>Açıklamalar  
 Yerleştirme modunu ayarlamak için çağrı [CDockingManager::SetDockingMode](#setdockingmode).  
  
##  <a name="getdocksiteframewnd"></a>  CDockingManager::GetDockSiteFrameWnd  
 Ana pencere çerçevesi için bir işaretçi alır.  
  
```  
CFrameWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ana pencere çerçevesi için bir işaretçi.  
  
##  <a name="getenabledautohidealignment"></a>  CDockingManager::GetEnabledAutoHideAlignment  
 Bölmeleri etkin hizalamasını döndürür.  
  
```  
DWORD GetEnabledAutoHideAlignment() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 CBRS_ALIGN_ bayrakları veya autohide bölmeleri etkin değilse 0 Bitsel bir birleşimi. Daha fazla bilgi için [CFrameWnd::EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking).  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem autohide denetim çubukları etkin hizalamasını döndürür. Otomatik Gizle çubuklarını etkinleştirmek için çağrı [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes).  
  
##  <a name="getminiframes"></a>  CDockingManager::GetMiniFrames  
 Miniframes listesini alır.  
  
```  
const CObList& GetMiniFrames() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerleştirme yöneticiye ait denetim çubukları içeren miniframes listesi.  
  
##  <a name="getouteredgebounds"></a>  CDockingManager::GetOuterEdgeBounds  
 Çerçeve dış kenarları içeren dikdörtgen alır.  
  
```  
CRect GetOuterEdgeBounds() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çerçeve dış kenarları içeren bir dikdörtgen.  
  
##  <a name="getpanelist"></a>  CDockingManager::GetPaneList  
 Yerleştirme yöneticiye ait bölmeleri listesini döndürür. Bu, tüm kayan bölme içerir.  
  
```  
void GetPaneList(
    CObList& lstBars,  
    BOOL bIncludeAutohide = FALSE,  
    CRuntimeClass* pRTCFilter = NULL,  
    BOOL bIncludeTabs = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [out içinde] *lstBars*  
 Geçerli yerleştirme manager'ın tüm bölme içerir.  
  
 [in] *bIncludeAutohide*  
 Otomatik Gizle modundaki bölmeleri dahil edilmesi için TRUE; Aksi takdirde FALSE.  
  
 [in] *pRTCFilter*  
 BOŞ değilse, döndürülen liste belirtilen çalışma zamanı sınıfının yalnızca bölme içerir.  
  
 [in] *bIncludeTabs*  
 Sekmeleri dahil edilmesi için TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerleştirme Yöneticisi'nde herhangi bir sekmeli bölmelerde varsa, yöntem işaretçileri döndürür [CBaseTabbedPane sınıfı](../../mfc/reference/cbasetabbedpane-class.md) nesneleri ve gerekir listeleme sekmeleri açıkça.  
  
 Kullanım *pRTCFilter* bölmeleri, belirli bir sınıfın elde edilir. Örneğin, bu değeri uygun şekilde ayarlayarak yalnızca araç çubukları elde edebilirsiniz.  
  
##  <a name="getsmartdockingmanager"></a>  CDockingManager::GetSmartDockingManager  
 Akıllı Yerleştirme Yöneticisi için bir işaretçi alır.  
  
```  
CSmartDockingManager* GetSmartDockingManager();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [akıllı yerleştirme manager](http://msdn.microsoft.com/f537a1a6-fb9e-41d7-952f-0f25d5ee7534).  
  
##  <a name="getsmartdockingmanagerpermanent"></a>  CDockingManager::GetSmartDockingManagerPermanent  
 Akıllı Yerleştirme Yöneticisi için bir işaretçi alır.  
  
```  
CSmartDockingManager* GetSmartDockingManagerPermanent() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akıllı Yerleştirme Yöneticisi için bir işaretçi.  
  
##  <a name="getsmartdockingparams"></a>  CDockingManager::GetSmartDockingParams  
 Akıllı Yerleştirme parametrelerini, sabitleme yöneticisini döndürür.  
  
```  
static CSmartDockingInfo& GetSmartDockingParams();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli yerleştirme Yöneticisi için akıllı yerleştirme parametreleri içeren sınıf. Daha fazla bilgi için [Csmartdockingınfo sınıfı](../../mfc/reference/csmartdockinginfo-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hideautohidepanes"></a>  CDockingManager::HideAutoHidePanes  
 Autohide modunda olan bir bölmesini gizler.  
  
```  
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,  
    BOOL bImmediately = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBarToExclude*  
 Bir çubuk gizleme hariç tutmak için bir işaretçi.  
  
 [in] *bImmediately*  
 Bölmeyi hemen gizlemek için TRUE; Otomatik Gizle etkisi bölmesiyle gizlemek için FALSE.  
  
##  <a name="insertdocksite"></a>  CDockingManager::InsertDockSite  
 Bir yerleştirme bölmesi oluşturur ve denetim çubukları listesine ekler.  
  
```  
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,  
    DWORD dwAlignToInsertAfter,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bilgileri*  
 Yerleştirme bölmesi hizalama bilgilerini içeren yapısı.  
  
 [in] *dwAlignToInsertAfter*  
 Yerleştirme bölmesinin hizalaması.  
  
 [out] *ppDockBar*  
 Yerleştirme bölmesine bir işaretçi işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerleştirme bölmesi başarıyla oluşturulursa TRUE; FALSE Aksi takdirde.  
  
##  <a name="insertpane"></a>  CDockingManager::InsertPane  
 Denetim Masası, Denetim çubuklarını listesine ekler.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pControlBar*  
 Bir denetim bölmesi için bir işaretçi.  
  
 [in] *pTarget*  
 Bir hedef bölmesi için bir işaretçi.  
  
 [in] *bBu*  
 Hedef bölmenin konumunu sonra bölmesine eklemek için TRUE; FALSE Aksi takdirde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim Masası'nı Denetim çubukları listesine başarıyla eklenirse TRUE; FALSE Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, Denetim Masası'nı Denetim çubukları listesinde değilse veya hedef bölmesi denetim çubukları listesinde mevcut değilse false döndürür.  
  
##  <a name="isdocksitemenu"></a>  CDockingManager::IsDockSiteMenu  
 Açılır menü tüm bölmeleri açıklamalı alt yazılar açık görüntülenip görüntülenmeyeceğini belirtir.  
  
```  
static BOOL IsDockSiteMenu();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tüm yerleştirme bölmesine açıklamalı alt yazılar açık bir dock sitesine menü görüntüleniyorsa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Dock sitesine menü çağrı yaparak etkinleştirebilirsiniz [CDockingManager::EnableDockSiteMenu](#enabledocksitemenu).  
  
##  <a name="isinadjustlayout"></a>  CDockingManager::IsInAdjustLayout  
 Tüm bölmeler düzenleri düzeltilir belirler.  
  
```  
BOOL IsInAdjustLayout() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tüm bölmeler düzenleri değiştirdiyseniz TRUE; FALSE Aksi takdirde.  
  
##  <a name="isolecontainermode"></a>  CDockingManager::IsOLEContainerMode  
 Yerleştirme manager OLE kapsayıcı modunda olup olmadığını belirtir.  
  
```  
BOOL IsOLEContainerMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerleştirme manager OLE kapsayıcı modunda ise TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 OLE kapsayıcı modunda tüm takma bölme ve uygulama araç çubukları gizli. Ayarladıysanız bölmeleri aynı zamanda bu modda gizli [CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode) true.  
  
##  <a name="ispointneardocksite"></a>  CDockingManager::IsPointNearDockSite  
 Belirli bir noktaya dock sitesine olup olmadığını belirler.  
  
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
 Hangi uç noktaya yaklaştı belirtir. Olası değerler şunlardır: CBRS_ALIGN_LEFT, CBRS_ALIGN_RIGHT, CBRS_ALIGN_TOP ve CBRS_ALIGN_BOTTOM.  
  
 [out] *bOuterEdge*  
 Dock sitesiyle dış kenarlığı noktası ise TRUE; FALSE Aksi takdirde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dock sitesiyle noktası ise TRUE; Aksi durumda FALSE.  
  
##  <a name="isprintpreviewvalid"></a>  CDockingManager::IsPrintPreviewValid  
 Baskı Önizleme modunu ayarlanmış olup olmadığını belirler.  
  
```  
BOOL IsPrintPreviewValid() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Baskı Önizleme modunu ayarlanmışsa TRUE; FALSE Aksi takdirde.  
  
##  <a name="loadstate"></a>  CDockingManager::LoadState  
 Kayıt defterinden yerleştirme Yöneticisi'nin durumunu yükler.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszProfileName*  
 Profil adı.  
  
 [in] *uiID*  
 Yerleştirme manager kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerleştirme manager durumu başarıyla yüklendi TRUE; Aksi durumda FALSE.  
  
##  <a name="lockupdate"></a>  CDockingManager::LockUpdate  
 Belirtilen pencere kilitler.  
  
```  
void LockUpdate(BOOL bLock);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bloğu*  
 Pencerenin kilitlenmesi durumunda TRUE; FALSE Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir pencere kilitliyken taşınamaz ve onu düzenlenemez.  
  
##  <a name="m_bhidedockingbarsincontainermode"></a>  CDockingManager::m_bHideDockingBarsInContainerMode  
 Yerleştirme manager OLE kapsayıcı modunda bölmeleri gizler olup olmadığını belirtir.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama OLE kapsayıcı modunda olduğunda görünür ana çerçeve sabitlenmiş tüm bölmeleri tutmak istiyorsanız bu değeri yanlış olarak ayarlayın. Varsayılan olarak, bu değer TRUE şeklindedir.  
  
##  <a name="m_dockmodeglobal"></a>  CDockingManager::m_dockModeGlobal  
 Genel yerleştirme modunu belirtir.  
  
```  
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, her bir yerleştirme bölmesi bu yerleştirme modunu kullanır. Bu alan için ayarlanabilir değerler hakkında daha fazla bilgi için bkz. [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).  
  
##  <a name="m_ndocksensitivity"></a>  CDockingManager::m_nDockSensitivity  
 Yerleştirme duyarlılığı belirtir.  
  
```  
AFX_IMPORT_DATA static int m_nDockSensitivity;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ne kadar yakın kayan yerleştirme duyarlılık tanımlar bölmesi yaklaşan bir yerleştirme bölmesi, yerleştirme sitesi ya da başka bir bölme framework yerleşik durumuna değiştirmeden önce.  
  
##  <a name="m_ntimeoutbeforedockingbardock"></a>  CDockingManager::m_nTimeOutBeforeDockingBarDock  
 Bir yerleştirme bölmesi hemen yerleştirme modunda yerleştirildiğini önce milisaniye cinsinden süreyi belirtir.  
  
```  
static UINT m_nTimeOutBeforeDockingBarDock;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme yerleştirildiğini önce framework belirtilen sürenin uzunluğunu bekler. Bu, kullanıcı hala sürükleme sırasında yanlışlıkla bir konuma sabitlenmiş gelen bölmesinde engeller.  
  
##  <a name="m_ntimeoutbeforetoolbardock"></a>  CDockingManager::m_nTimeOutBeforeToolBarDock  
 Ana çerçeve penceresine araç çubuğu yerleştirildiğini önce milisaniye cinsinden süreyi belirtir.  
  
```  
static UINT m_nTimeOutBeforeToolBarDock;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Araç çubuğu yerleştirildiğini önce framework belirtilen sürenin uzunluğunu bekler. Bu araç, kullanıcı hala sürükleme sırasında yanlışlıkla bir konuma sabitlenmiş gelen engeller.  
  
##  <a name="onactivateframe"></a>  CDockingManager::OnActivateFrame  
 Çerçeve penceresi etkinleştirilir veya devre dışı olduğunda framework tarafından çağırılır.  
  
```  
virtual void OnActivateFrame(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bActivate*  
 TRUE ise, çerçeve penceresi etkinleştirilir; FALSE ise, çerçeve penceresi devre dışı bırakılır.  
  
##  <a name="onclosepopupmenu"></a>  CDockingManager::OnClosePopupMenu  
 Etkin bir açılan menü WM_DESTROY iletiyi işleyen framework tarafından çağırılır.  
  
```  
void OnClosePopupMenu();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli ana pencere kapanmak üzere olduğunda framework WM_DESTROY ileti gönderir. Bildirimler işlemek için bu yöntemi yok sayın `CMFCPopupMenu` çerçeve penceresine ait nesneleri, bir `CMFCPopupMenu` nesnesini WM_DESTROY ileti işler.  
  
##  <a name="onmoveminiframe"></a>  CDockingManager::OnMoveMiniFrame  
 Bir mini çerçeve taşımak için framework tarafından çağırılır.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pFrame*  
 Bir mini çerçeve işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE; Aksi durumda FALSE.  
  
##  <a name="onpanecontextmenu"></a>  CDockingManager::OnPaneContextMenu  
 Bölmeleri listesini içeren bir menü oluşturduğunda framework tarafından çağırılır.  
  
```  
void OnPaneContextMenu(CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *noktası*  
 Menü konumunu belirtir.  
  
##  <a name="panefrompoint"></a>  CDockingManager::PaneFromPoint  
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
 [in] *noktası*  
 Noktasını denetlemek için ekran koordinatları olarak belirtir.  
  
 [in] *nSensitivity*  
 Her işaretli bölmesinin Pencere dikdörtgeni Şişir değer. Belirtilen noktasını inflated bu bölgede değilse bir bölmesinde arama ölçütlerini karşılar.  
  
 [in] *bExactBar*  
 Yok saymak için TRUE *nSensitivity* parametre; Aksi takdirde FALSE.  
  
 [in] *pRTCBarType*  
 BOŞ değilse, yalnızca belirtilen türün bölmeleri yöntemi arar.  
  
 [in] *bCheckVisibility*  
 Yalnızca görünür bölmeleri denetlemek için TRUE; Aksi takdirde FALSE.  
  
 [out] *dwAlignment*  
 Belirli bir noktada bir bölme bulunursa, bu parametre için belirtilen nokta en yakın bölmesinde tarafında yer alır. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
 [in] *pBarToIgnore*  
 Yöntemi, boş değilse bu parametre tarafından belirtilen bölmeleri yok sayar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 [CBasePane](../../mfc/reference/cbasepane-class.md)-hiçbir bölmesinde bulunduysa belirtilen noktasını ya da NULL içeren türetilmiş nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevi döndürür ve bir bölme bulundu, *dwAlignment* belirtilen nokta hizalamasını içerir. Örneğin, noktası bölmesinde üstüne yakın *dwAlignment* CBRS_ALIGN_TOP için ayarlanır.  
  
##  <a name="processpanecontextmenucommand"></a>  CDockingManager::ProcessPaneContextMenuCommand  
 Seçin veya belirtilen komut için bir onay kutusunu temizleyin ve gösterilen bölmesinin düzenini yeniden hesapla için framework tarafından çağırılır.  
  
```  
BOOL ProcessPaneContextMenuCommand(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nID*  
 Bir denetim çubuğuna menü kimliği.  
  
 [in] *nCode*  
 Komut bildirim kodu.  
  
 [in] *pExtra*  
 Void bir işaretçi işaretçisi Integer `CCmdUI` varsa *nCode* CN_UPDATE_COMMAND_UI olduğu.  
  
 [in] *pHandlerInfo*  
 Bir bilgi yapısına yönelik işaretçi. Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE ise *pEXtra* NULL değil ve *nCode* CN_UPDATE_COMMAND_UI, eşittir veya varsa belirli bir denetim çubuğu *nID*.  
  
##  <a name="recalclayout"></a>  CDockingManager::RecalcLayout  
 Denetim listesinde mevcut denetimlerin iç düzenini yeniden hesaplar.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bNotify*  
 Bu parametre kullanılmaz.  
  
##  <a name="releaseemptypanecontainers"></a>  CDockingManager::ReleaseEmptyPaneContainers  
 Boş bölmesinde kapsayıcıları serbest bırakır.  
  
```  
void ReleaseEmptyPaneContainers();
```  
  
##  <a name="removehiddenmditabbedbar"></a>  CDockingManager::RemoveHiddenMDITabbedBar  
 Belirtilen bölmesinde gizlenmiş kaldırır.  
  
```  
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
 İşaretçi çubuk bölmesinde kaldırmak için.  
  
##  <a name="removeminiframe"></a>  CDockingManager::RemoveMiniFrame  
 Belirtilen bir çerçeve mini çerçeve listesinden kaldırır.  
  
```  
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWnd*  
 Kaldırmak için bir çerçeve işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen çerçeve kaldırılırsa TRUE; FALSE Aksi takdirde.  
  
##  <a name="removepanefromdockmanager"></a>  CDockingManager::RemovePaneFromDockManager  
 Bir bölme kaydını siler ve yerleştirme manager listesinden kaldırır.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pWnd,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWnd*  
 Kaldırılacak bir bölme için bir işaretçi.  
  
 [in] *bDestroy*  
 TRUE ise, kaldırılan bölmesinde yok edilir.  
  
 [in] *bAdjustLayout*  
 TRUE ise yerleştirme düzeni hemen ayarlayın.  
  
 [in] *bAutoHide*  
 TRUE ise bölmesinde autohide çubukları listesinden kaldırılır. FALSE ise bölmesinde normal bölmeleri listesinden kaldırılır.  
  
 [in] *pBarReplacement*  
 Kaldırılan bölmesinde yerini alan bir bölme için bir işaretçi.  
  
##  <a name="replacepane"></a>  CDockingManager::ReplacePane  
 Bir bölme birbiriyle değiştirir.  
  
```  
BOOL ReplacePane(
    CDockablePane* pOriginalBar,  
    CDockablePane* pNewBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pOriginalBar*  
 Özgün bölmesi için bir işaretçi.  
  
 [in] *pNewBar*  
 Özgün bölmesinde değiştirir bölmesi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde başarıyla değiştirildi TRUE; FALSE Aksi takdirde.  
  
##  <a name="resortminiframesforzorder"></a>  CDockingManager::ResortMiniFramesForZOrder  
 Mini çerçeve listesinde çerçeveleri resorts.  
  
```  
void ResortMiniFramesForZOrder();
```  
  
##  <a name="savestate"></a>  CDockingManager::SaveState  
 Yerleştirme yöneticisinin durumu kayıt defterine kaydeder.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszProfileName*  
 Bir kayıt defteri anahtarı bir yolu.  
  
 [in] *uiID*  
 Yerleştirme manager kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durumu başarılı bir şekilde kaydedilmiş ise TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt defterine yerleştirme yöneticisinin durumu kaydetmeyi kaydetme denetim çubukları durumlarını, durumlarını autohide çubukları ve yerleştirme yöneticisinde mini çerçeve durumlarını içerir.  
  
##  <a name="sendmessagetominiframes"></a>  CDockingManager::SendMessageToMiniFrames  
 Belirtilen iletiyi için tüm mini çerçeve gönderir.  
  
```  
BOOL SendMessageToMiniFrames(
    UINT uMessage,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uMessage*  
 Gönderilecek ileti.  
  
 [in] *wParam*  
 Ek ileti bağımlı bilgileri.  
  
 [in] *lParam*  
 Ek ileti bağımlı bilgileri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman TRUE.  
  
##  <a name="serialize"></a>  CDockingManager::Serialize  
 Yerleştirme manager arşive yazar.  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *ar*  
 Bir arşiv nesnesine bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir arşiv yerleştirme manager yazma, Denetim çubuklarını ve kaydırıcılar yerleştirme ve denetim çubukları, mini çerçeve, Otomatik Gizle'yi çubukları ve sekmeli MDI çubukları arşive yazma sayısını belirleyen içerir.  
  
##  <a name="setautohidezorder"></a>  CDockingManager::SetAutohideZOrder  
 Boyut, genişliğini ve yüksekliğini denetim çubuklarını ve belirtilen bölmesinde ayarlar.  
  
```  
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pAHDockingBar*  
 Yerleştirilebilir bir bölme için bir işaretçi.  
  
##  <a name="setdockingmode"></a>  CDockingManager::SetDockingMode  
 Yerleştirme modunu ayarlar.  
  
```  
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,  
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```  
  
### <a name="parameters"></a>Parametreler  
 *dockMode*  
 Yeni takma modunu belirtir. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
 *Tema*  
 Tema için akıllı yerleştirme işaretçilerinin kullanılacak belirtir. Aşağıdaki numaralandırılmış değerlerden biri olabilir: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerleştirme modu ayarlamak için statik bu yöntemi çağırın.  
  
 *dockMode* aşağıdaki değerlerden biri olabilir:  
  
- DT_STANDARD - Visual Studio .NET 2003'te uygulanmış olarak standart yerleştirme modu. Bölmeleri sürükleyerek bir bağlam sürüklediğiniz.  
  
- DT_IMMEDIATE - Microsoft Visio uygulanan olarak anlık yerleştirme mod. Bölmeleri sürükleyerek bağlamıyla sürüklediğiniz, ancak bir işaretleyici yok görüntülenir.  
  
- DT_SMART - Visual Studio 2005 uygulanmış olarak akıllı yerleştirme modu. Bölmeleri sürükleyerek bağlamıyla sürüklediğiniz ve akıllı işaretçileri görüntülenir gösteren burada bölmenin yerleştirilmiş olabilir.  
  
##  <a name="setdockstate"></a>  CDockingManager::SetDockState  
 Denetim çubukları, mini çerçeve ve autohide çubukları yerleştirme durumunu ayarlar.  
  
```  
virtual void SetDockState();
```  
  
##  <a name="setprintpreviewmode"></a>  CDockingManager::SetPrintPreviewMode  
 Baskı Önizlemede görüntülenen çubukları Baskı Önizleme modunu ayarlar.  
  
```  
void SetPrintPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bPreview*  
 Baskı Önizleme modunu ayarlanmışsa TRUE; FALSE Aksi takdirde.  
  
 [in] *pState*  
 Bir önizleme durumuna yönelik bir işaretçi. Bu parametre kullanılmaz.  
  
##  <a name="setsmartdockingparams"></a>  CDockingManager::SetSmartDockingParams  
 Akıllı Yerleştirme davranışını tanımlayan parametreler ayarlar.  
  
```  
static void SetSmartDockingParams(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>Parametreler  
 [out içinde] *params*  
 Akıllı yerleştirme için parametreleri tanımlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Görünüm, renk ve akıllı yerleştirme işaretçilerinin şeklini özelleştirmek istiyorsanız bu yöntemi çağırın.  
  
 Varsayılan görünüm için akıllı yerleştirme işaretçilerinin kullanmak için başlatılmamış bir örneğini geçirin [Csmartdockingınfo sınıfı](../../mfc/reference/csmartdockinginfo-class.md) için *params*.  
  
##  <a name="showdelayshowminiframes"></a>  CDockingManager::ShowDelayShowMiniFrames  
 Windows mini çerçeve gizler veya gösterir.  
  
```  
void ShowDelayShowMiniFrames(BOOL bshow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bBilgi Göster*  
 Gösterilen çerçeve penceresini etkinleştirmek için TRUE; Pencerenin çerçevesinin gizlemek için FALSE.  
  
##  <a name="showpanes"></a>  CDockingManager::ShowPanes  
 Denetim ve autohide çubukların bölmeleri gizler veya gösterir.  
  
```  
virtual BOOL ShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bBilgi Göster*  
 Bölmelerini göstermek için TRUE; Bölmeleri gizlemek için FALSE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman FALSE.  
  
##  <a name="startsdocking"></a>  CDockingManager::StartSDocking  
 Belirtilen pencere akıllı yerleştirme manager hizalamasını göre akıllı yerleştirme başlar.  
  
```  
void StartSDocking(CWnd* pDockingWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDockingWnd*  
 Bir pencere sabitlemek için bir işaretçi.  
  
##  <a name="stopsdocking"></a>  CDockingManager::StopSDocking  
 Yerleştirme durur akıllı.  
  
```  
void StopSDocking();
```  
  
##  <a name="getsmartdockingtheme"></a>  CDockingManager::GetSmartDockingTheme  
 Akıllı Yerleştirme işaretçilerinin görüntülemek için kullanılan bir tema döndüren statik yöntem.  
  
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
