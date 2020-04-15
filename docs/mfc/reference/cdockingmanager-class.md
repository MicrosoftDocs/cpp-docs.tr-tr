---
title: CDockingManager Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 339e5d5e464aacb51d1c4ab8fe3c2957a3afbd4e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375579"
---
# <a name="cdockingmanager-class"></a>CDockingManager Sınıfı

Ana çerçeve penceresinde yerleştirme düzenini denetleyen temel işlevselliği uygular.

## <a name="syntax"></a>Sözdizimi

```
class CDockingManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDockingManager::AddDockSite](#adddocksite)|Bir dock bölmesi oluşturur ve denetim çubukları listesine ekler.|
|[CDockingManager::AddHiddenMDITabbedBar](#addhiddenmditabbedbar)|Gizli MDI sekmeli çubuk bölmeleri listesine bir çubuk bölmesine tutamaç ekler.|
|[CDockingManager::AddMiniFrame](#addminiframe)|Mini çerçeveler listesine bir çerçeve ekler.|
|[CDockingManager::AddPane](#addpane)|Yerleştirme yöneticisine bir bölme kaydeder.|
|[CDockingManager::AdjustDockingLayout](#adjustdockinglayout)|Çerçeve penceresindeki tüm bölmelerin düzenini yeniden hesaplar ve ayarlar.|
|[CDockingManager::AdjustPaneFrames](#adjustpaneframes)|WM_NCCALCSIZE iletisinin tüm bölmelere ve `CPaneFrameWnd` pencerelere gönderilmesine neden olur.|
|[CDockingManager::AdjustRectToClientArea](#adjustrecttoclientarea)|Dikdörtgenin hizalanmasını ayarlar.|
|[CDockingManager::AlignAutoHidePane](#alignautohidepane)|Bir yerleştirme bölmesini otomatik hide modunda yeniden boyutlandırır, böylece çerçevenin istemci alanının tam genişliğini veya yüksekliğini dock siteleri ile çevrili alır.|
|[CDockingManager::AutoHidePane](#autohidepane)|Otomatik hide araç çubuğu oluşturur.|
|[CDockingManager::BringBarsToTop](#bringbarstotop)|Belirtilen hizalamayı en üste getiren sabitlenmiş çubukları getirir.|
|[CDockingManager::BuildPanesMenu](#buildpanesmenu)|Bir menüye yerleştirme bölmelerinin ve araç çubuklarının adlarını ekler.|
|[CDockingManager::CalcExpectedDockedRect](#calcexpecteddockedrect)|Kenetlenmiş bir pencerenin beklenen dikdörtgenini hesaplar.|
|[CDockingManager::Oluştur](#create)|Bir yerleştirme yöneticisi oluşturur.|
|[CDockingManager::DeterminePaneAndStatus](#determinepaneandstatus)|Belirli bir noktayı içeren bölmeyi ve yerleştirme durumunu belirler.|
|[CDockingManager::DisableRestoreDockState](#disablerestoredockstate)|Kayıt defterinden yerleştirme düzeninin yüklenmesine olanak tanır veya devre dışı kılır.|
|[CDockingManager::DockPane](#dockpane)|Bölmeyi başka bir bölmeye veya çerçeve penceresine sabitler.|
|[CDockingManager::DockPaneLeftOf](#dockpaneleftof)|Başka bir bölmenin soluna bir bölme yapıştırın.|
|[CDockingManager::EnableAutoHidePanes](#enableautohidepanes)|Bölmenin ana çerçeveye sabitlemesini sağlar, bir dock bölmesi oluşturur ve denetim çubukları listesine ekler.|
|[CDockingManager::Etkinleştirme Docking](#enabledocking)|Bir dock bölmesi oluşturur ve bölmenin ana çerçeveye sabitlemesini sağlar.|
|[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)|Tüm yerleştirme bölmelerinin alt yazılarında açılır menüyü açan ek bir düğme görüntüler.|
|[CDockingManager::EnablePaneContextMenu](#enablepanecontextmenu)|Kullanıcı sağ fare düğmesini tıklattığında ve kitaplık WM_CONTEXTMENU iletisini işlediğinde, uygulama araç çubukları ve yerleştirme bölmelerinin listesini içeren özel bir bağlam menüsünü görüntülemek için kitaplüye bildirir.|
|[CDockingManager::FindDockSite](#finddocksite)|Belirtilen konumda olan ve belirtilen hizaya sahip çubuk bölmesini alır.|
|[CDockingManager::FindDockSiteByPane](#finddocksitebypane)|Hedef çubuk bölmesinin kimliğine sahip çubuk bölmesini döndürür.|
|[CDockingManager::FindPaneByID](#findpanebyid)|Belirtilen denetim kimliğine göre bir bölme bulur.|
|[CDockingManager::FixupVirtualRects](#fixupvirtualrects)|Tüm geçerli araç çubuğu konumlarını sanal dikdörtgenlere adatır.|
|[CDockingManager::FrameFromPoint](#framefrompoint)|Verilen noktayı içeren çerçeveyi döndürür.|
|[CDockingManager::GetClientAreaBounds](#getclientareabounds)|İstemci alanının sınırlarını içeren dikdörtgeni alır.|
|[CDockingManager::GetDockingMode](#getdockingmode)|Geçerli yerleştirme modunu döndürür.|
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|Ana pencere çerçevesiiçin bir işaretçi alır.|
|[CDockingManager::GetEnabledAutoHideAlignment](#getenabledautohidealignment)|Bölmelerin etkin hizalanmasını verir.|
|[CDockingManager::GetMiniFrames](#getminiframes)|Mini çerçevelerin bir listesini alır.|
|[CDockingManager::GetOuterEdgeBounds](#getouteredgebounds)|Çerçevenin dış kenarlarını içeren bir dikdörtgen alır.|
|[CDockingManager::GetPaneList](#getpanelist)|Yerleştirme yöneticisine ait bölmelerin listesini verir. Bu, tüm kayan bölmeleri içerir.|
|[CDockingManager::GetSmartDockingManager](#getsmartdockingmanager)|Akıllı yerleştirme yöneticisine bir işaretçi alır.|
|[CDockingManager::GetSmartDockingManagerPermanent](#getsmartdockingmanagerpermanent)|Akıllı yerleştirme yöneticisine bir işaretçi alır.|
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|Yerleştirme yöneticisi için akıllı yerleştirme parametrelerini verir.|
|[CDockingManager::GetSmartDockingTheme](#getsmartdockingtheme)|Akıllı yerleştirme işaretçilerini görüntülemek için kullanılan bir tema döndüren statik bir yöntem.|
|[CDockingManager::HideAutoHidePanes](#hideautohidepanes)|Otomatik hide modunda olan bir bölmeyi gizler.|
|[CDockingManager::InsertDockSite](#insertdocksite)|Bir dock bölmesi oluşturur ve denetim çubukları listesine ekler.|
|[CDockingManager::InsertPane](#insertpane)|Denetim çubukları listesine bir denetim bölmesi ekler.|
|[CDockingManager::IsDockSiteMenu](#isdocksitemenu)|Açılır menü yürek bölmelerin alt yazılarında görüntülenip görüntülenmediğini belirtir.|
|[CDockingManager::IsInAdjustLayout](#isinadjustlayout)|Tüm bölmelerin düzenlerinin ayarlı paçüsten olup olmadığını belirler.|
|[CDockingManager::IsOLEContainerMode](#isolecontainermode)|Yerleştirme yöneticisinin OLE kapsayıcı modunda olup olmadığını belirtir.|
|[CDockingManager::IsPointNearDockSite](#ispointneardocksite)|Belirli bir noktanın dock bölgesine yakın olup olmadığını belirler.|
|[CDockingManager::IsPrintPreviewValid](#isprintpreviewvalid)|Yazdırma önizleme modunun ayarlı olup olmadığını belirler.|
|[CDockingManager::LoadState](#loadstate)|Takma yöneticisinin durumunu kayıt defterinden yükler.|
|[CDockingManager::LockUpdate](#lockupdate)|Verilen pencereyi kilitler.|
|[CDockingManager::OnActivateFrame](#onactivateframe)|Çerçeve penceresi etkin hale getirildiğinde veya devre dışı bırakıldığında çerçeve tarafından çağrılır.|
|[CDockingManager::OnClosePopupMenu](#onclosepopupmenu)|Etkin bir açılır menü bir WM_DESTROY iletisi işlediğinde çerçeve tarafından çağrılır.|
|[CDockingManager::OnMoveMiniFrame](#onmoveminiframe)|Bir mini çerçeve penceresi taşımak için çerçeve tarafından çağrılır.|
|[CDockingManager::OnPaneContextMenu](#onpanecontextmenu)|Bölmelerin bir listesini içeren bir menü oluşturduğunda çerçeve tarafından çağrılır.|
|[CDockingManager::PaneFromPoint](#panefrompoint)|Verilen noktayı içeren bölmeyi döndürür.|
|[CDockingManager::ProcessPaneContextMenuCommand](#processpanecontextmenucommand)|Belirtilen komut için bir onay kutusunu seçmek veya temizlemek ve gösterilen bölmenin düzenini yeniden hesaplamak için çerçeve tarafından çağrılır.|
|[CDockingManager::RecalcLayout](#recalclayout)|Denetimler listesinde bulunan denetimlerin iç düzenini yeniden hesaplar.|
|[CDockingManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|Boş bölme kapsayıcılarını serbest bırakır.|
|[CDockingManager::RemoveHiddenMDITabbedBar](#removehiddenmditabbedbar)|Belirtilen gizli çubuk bölmesini kaldırır.|
|[CDockingManager::RemoveMiniFrame](#removeminiframe)|Mini çerçeveler listesinden belirtilen bir çerçeveyi kaldırır.|
|[CDockingManager::RemovePaneFromDockManager](#removepanefromdockmanager)|Bölmenin kaydını kaldırır ve yerleştirme yöneticisindeki listeden kaldırır.|
|[CDockingManager::ReplacePane](#replacepane)|Bir bölmeyi diğeriyle değiştirir.|
|[CDockingManager::ResortMiniFramesForZOrder](#resortminiframesforzorder)|Mini çerçeveler listesindeki çerçeveleri tatil eder.|
|[CDockingManager::SaveState](#savestate)|Takma yöneticisinin durumunu kayıt defterine kaydeder.|
|[CDockingManager::SendMessageToMiniFrames](#sendmessagetominiframes)|Belirtilen iletiyi tüm mini çerçevelere gönderir.|
|[CDockingManager::Serialize](#serialize)|Yerleştirme yöneticisini bir arşive yazar. (CObject geçersiz [kılar::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[CDockingManager::SetAutohideZOrder](#setautohidezorder)|Denetim çubuklarının ve belirtilen bölmenin boyutunu, genişliğini ve yüksekliğini ayarlar.|
|[CDockingManager::SetDockingMode](#setdockingmode)|Yerleştirme modunu ayarlar.|
|[CDockingManager::SetDockState](#setdockstate)|Denetim çubuklarının, mini çerçevelerin ve otomatik hide çubuklarının takma durumunu ayarlar.|
|[CDockingManager::SetPrintPreviewMode](#setprintpreviewmode)|Yazdırma önizlemesinde görüntülenen çubukların yazdırma önizleme modunu ayarlar.|
|[CDockingManager::SetSmartDockingParams](#setsmartdockingparams)|Akıllı yerleştirme davranışını tanımlayan parametreleri ayarlar.|
|[CDockingManager::ShowDelayShowMiniFrames](#showdelayshowminiframes)|Mini çerçevelerin pencerelerini gösterir veya gizler.|
|[CDockingManager::ShowPanes](#showpanes)|Denetim ve otomatik hide çubukların bölmelerini gösterir veya gizler.|
|[CDockingManager::Başlangıç Docking](#startsdocking)|Akıllı yerleştirme yöneticisinin hizasına göre belirtilen pencerenin akıllı yerleştirmesini başlatır.|
|[CDockingManager::StopSDocking](#stopsdocking)|Akıllı kenetlenmeyi durdurur.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|Yerleştirme yöneticisinin bölmeleri OLE kapsayıcı modunda gizleyip gizlemediğini belirtir.|
|[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)|Genel yerleştirme modunu belirtir.|
|[CDockingManager::m_nDockSensitivity](#m_ndocksensitivity)|Yerleştirme hassasiyetini belirtir.|
|[CDockingManager::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|Yerleştirme bölmesi hemen yerleştirme modunda kenetlenmeden önce saati milisaniye cinsinden belirtir.|
|[CDockingManager::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|Araç çubuğu ana çerçeve penceresine sabitlenmeden önce saati milisaniye cinsinden belirtir.|

## <a name="remarks"></a>Açıklamalar

Ana çerçeve penceresi bu sınıfı otomatik olarak oluşturur ve başharfe ait hale tir.

Yerleştirme yöneticisi nesnesi, yerleştirme düzeninde bulunan tüm bölmelerin bir listesini ve ana çerçeve penceresine ait tüm [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) pencerelerinin listesini tutar.

Sınıf, `CDockingManager` bölme veya `CPaneFrameWnd` pencere bulmak için kullanabileceğiniz bazı hizmetleri uygular. Ana çerçeve penceresi nesnesi sarılmış çünkü genellikle doğrudan bu hizmetleri aramayın. Daha fazla bilgi için [CPaneFrameWnd Class'a](../../mfc/reference/cpaneframewnd-class.md)bakın.

## <a name="customization-tips"></a>Özelleştirme İpuçları

Aşağıdaki ipuçları nesneler `CDockingManager` için geçerlidir:

- [CDockingManager Class](../../mfc/reference/cdockingmanager-class.md) bu yerleştirme modlarını destekler:

  - `AFX_DOCK_TYPE::DT_IMMEDIATE`

  - `AFX_DOCK_TYPE::DT_STANDARD`

  - `AFX_DOCK_TYPE::DT_SMART`

  Bu yerleştirme modları [CDockingManager::m_dockModeGlobal](#m_dockmodeglobal) tarafından tanımlanır ve [CDockingManager::SetDockingMode](#setdockingmode)numaralı telefonu arayarak ayarlanır.

- Kayan olmayan, yeniden boyutlandırılamaz bir bölme oluşturmak istiyorsanız, [CDockingManager'ı arayın:AddPane](#addpane) yöntemini. Bu yöntem bölmeyi, bölmenin düzeninden sorumlu olan yerleştirme yöneticisine kaydeder.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CDockingManager` `CDockingManager` nesneyi yapılandırmak için sınıfta çeşitli yöntemlerin nasıl kullanılacağını gösterir. Örnek, tüm yerleştirme bölmelerinin altyazılarında açılır menüyü açan ek bir düğmenin nasıl görüntülanacağını ve nesnenin yerleştirme modunu nasıl ayarlanacağını gösterir. Bu kod snippet [Visual Studio Demo örnek](../../overview/visual-cpp-samples.md)parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CDockingManager](../../mfc/reference/cdockingmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxDockingManager.h

## <a name="cdockingmanageradddocksite"></a><a name="adddocksite"></a>CDockingManager::AddDockSite

Bir dock bölmesi oluşturur ve denetim çubukları listesine ekler.

```
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,
    CDockSite** ppDockBar = NULL);
```

### <a name="parameters"></a>Parametreler

*Bilgi*<br/>
[içinde] Dock bölme hizalama içeren bir bilgi yapısına başvuru.

*ppDockBar*<br/>
[çıkış] Yeni dock bölmesine işaretçi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Dock bölmesi başarıyla oluşturulduysa DOĞRU; YANLIŞ aksi takdirde.

## <a name="cdockingmanageraddhiddenmditabbedbar"></a><a name="addhiddenmditabbedbar"></a>CDockingManager::AddHiddenMDITabbedBar

Gizli MDI sekmeli çubuk bölmeleri listesine bir çubuk bölmesine tutamaç ekler.

```
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[içinde] Çubuk bölmeye işaretçi

## <a name="cdockingmanageraddpane"></a><a name="addpane"></a>CDockingManager::AddPane

Yerleştirme yöneticisine bir bölme kaydeder.

```
BOOL AddPane(
    CBasePane* pWnd,
    BOOL bTail = TRUE,
    BOOL bAutoHide = FALSE,
    BOOL bInsertForOuterEdge = FALSE);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
[içinde, dışarı] Yerleştirme yöneticisine eklemek için bölmeyi belirtir.

*bTail*<br/>
[içinde] Yerleştirme yöneticisi için bölme listesinin sonuna bölmeeklemek için TRUE; aksi takdirde, YANLIŞ.

*bAutoHide*<br/>
[içinde] Yalnızca dahili kullanım için. Her zaman varsayılan değeri FALSE kullanın.

*bInsertForOuterEdge*<br/>
[içinde] Yalnızca dahili kullanım için. Her zaman varsayılan değeri FALSE kullanın.

### <a name="return-value"></a>Dönüş Değeri

Bölme, yerleştirme yöneticisine başarıyla kaydedilmişse DOĞRUDUR; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Kayan olmayan, yeniden boyutlandırılamayan bölmeleri yerleştirme yöneticisine kaydetmek için bu yöntemi arayın. Bölmeleri kaydetmezseniz, yerleştirme yöneticisi yerleştirildiğinde bunlar doğru görünmez.

## <a name="cdockingmanageradjustdockinglayout"></a><a name="adjustdockinglayout"></a>CDockingManager::AdjustDockingLayout

Çerçeve penceresindeki tüm bölmelerin düzenini yeniden hesaplar ve ayarlar.

```
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```

### <a name="parameters"></a>Parametreler

*hdwp*<br/>
[içinde] Ertelenmiş pencere konumu yapısını belirtir. Daha fazla bilgi için [Windows Veri Türleri'ne](/windows/win32/WinProg/windows-data-types)bakın.

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingmanageraddminiframe"></a><a name="addminiframe"></a>CDockingManager::AddMiniFrame

Mini çerçeveler listesine bir çerçeve ekler.

```
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
[içinde] Çerçeve için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Çerçeve mini çerçeveler listesinde değilse ve başarıyla eklenmiştir DOĞRU; YANLIŞ aksi takdirde.

## <a name="cdockingmanageradjustpaneframes"></a><a name="adjustpaneframes"></a>CDockingManager::AdjustPaneFrames

WM_NCCALCSIZE iletisinin tüm bölmelere ve `CPaneFrameWnd` pencerelere gönderilmesine neden olur.

```
virtual void AdjustPaneFrames();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingmanageradjustrecttoclientarea"></a><a name="adjustrecttoclientarea"></a>CDockingManager::AdjustRectToClientArea

Dikdörtgenin hizalanmasını ayarlar.

```
virtual BOOL AdjustRectToClientArea(
    CRect& rectResult,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

*rektResult*<br/>
[içinde] Bir `CRect` nesneye başvuru

*dwHizalama*<br/>
[içinde] Nesnenin `CRect` hizalanması

### <a name="return-value"></a>Dönüş Değeri

Nesnenin hizalaması `CRect` ayarlanmışsa DOĞRU; YANLIŞ aksi takdirde.

### <a name="remarks"></a>Açıklamalar

*dwAlignment* parametresi aşağıdaki değerlerden birine sahip olabilir:

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

## <a name="cdockingmanageralignautohidepane"></a><a name="alignautohidepane"></a>CDockingManager::AlignAutoHidePane

Bir yerleştirme bölmesini otomatik hide modunda yeniden boyutlandırır, böylece çerçevenin istemci alanının tam genişliğini veya yüksekliğini dock siteleri ile çevrili alır.

```
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,
    BOOL bIsVisible = TRUE);
```

### <a name="parameters"></a>Parametreler

*pDefaultSlider*<br/>
[içinde] Yerleştirme kaydırıcısı bölmesi.

*bIsVisible*<br/>
[içinde] Yerleştirme bölmesi görünürse DOĞRU; YANLIŞ aksi takdirde.

## <a name="cdockingmanagerautohidepane"></a><a name="autohidepane"></a>CDockingManager::AutoHidePane

Otomatik hide araç çubuğu oluşturur.

```
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[içinde] Çubuk bölmesine bir işaretçi.

*pCurrAutoHideToolBar*<br/>
[içinde] Otomatik gizleme araç çubuğuiçin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Otomatik gizleme araç çubuğu oluşturulmamadıysa NULL; aksi takdirde yeni araç çubuğuna bir işaretçi.

## <a name="cdockingmanagerbringbarstotop"></a><a name="bringbarstotop"></a>CDockingManager::BringBarsToTop

Belirtilen hizalamayı en üste getiren sabitlenmiş çubukları getirir.

```
void BringBarsToTop(
    DWORD dwAlignment = 0,
    BOOL bExcludeDockedBars = TRUE);
```

### <a name="parameters"></a>Parametreler

*dwHizalama*<br/>
[içinde] Diğer pencerelerin üstüne getirilen dock çubuklarının hizalaması.

*bExcludeDockedBars*<br/>
[içinde] Kenetlenmiş çubukların üstte olmasını engellemek için TRUE; aksi takdirde YANLIŞ.

## <a name="cdockingmanagerbuildpanesmenu"></a><a name="buildpanesmenu"></a>CDockingManager::BuildPanesMenu

Bir menüye yerleştirme bölmelerinin ve araç çubuklarının adlarını ekler.

```
void BuildPanesMenu(
    CMenu& menu,
    BOOL bToolbarsOnly);
```

### <a name="parameters"></a>Parametreler

*Menü*<br/>
[içinde] Yerleştirme bölmelerinin ve araç çubuklarının adlarını eklemek için bir menü.

*bToolbarsSadece*<br/>
[içinde] Menüye yalnızca araç çubuğu adları eklemek için TRUE; YANLIŞ aksi takdirde.

## <a name="cdockingmanagercalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CDockingManager::CalcExpectedDockedRect

Kenetlenmiş bir pencerenin beklenen dikdörtgenini hesaplar.

```
void CalcExpectedDockedRect(
    CWnd* pWnd,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
[içinde] Kenetlenme penceresine bir işaretçi.

*ptMouse*<br/>
[içinde] Fare konumu.

*rektResult*<br/>
[çıkış] Hesaplanan dikdörtgen.

*bDrawTab*<br/>
[içinde] TRUE bir sekme çizmek için; aksi takdirde YANLIŞ.

*ppTargetBar*<br/>
[çıkış] Hedef bölmeye işaretçi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir kullanıcı pencereyi *ptMouse* tarafından belirtilen noktaya sürüklüp oraya sabitlerse, pencerenin kapalacağı dikdörtgeni hesaplar.

## <a name="cdockingmanagercreate"></a><a name="create"></a>CDockingManager::Oluştur

Bir yerleştirme yöneticisi oluşturur.

```
BOOL Create(CFrameWnd* pParentWnd);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
[içinde] Yerleştirme yöneticisinin ana çerçevesine işaretçi. Bu değer NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU her zaman.

## <a name="cdockingmanagerdeterminepaneandstatus"></a><a name="determinepaneandstatus"></a>CDockingManager::DeterminePaneAndStatus

Belirli bir noktayı içeren bölmeyi ve yerleştirme durumunu belirler.

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

*Pt*<br/>
[içinde] Denetlemek için bölmenin konumu.

*nDuyarlılık*<br/>
[içinde] Denetlenen her bölmenin pencere dikdörtgenini artırma değeri. Verilen nokta bu artan bölgedeyse, bir bölme arama ölçütlerini karşılar.

*dwEnabledAlignment*<br/>
[içinde] Yerleştirme bölmesinin hizalaması.

*ppTargetBar*<br/>
[çıkış] Hedef bölmeye işaretçi için bir işaretçi.

*pBarToIgnore*<br/>
[içinde] Yöntemin yoksaydığı bölme.

*pBarToDock*<br/>
[içinde] Kenetlenmiş bölme.

### <a name="return-value"></a>Dönüş Değeri

Yerleştirme durumu.

### <a name="remarks"></a>Açıklamalar

Yerleştirme durumu aşağıdaki değerlerden biri olabilir:

|AFX_CS_STATUS değeri|Anlamı|
|---------------------------|-------------|
|CS_NOTHING|İşaretçi bir dock sitesi üzerinde değil. Bu nedenle, bölmenin kayan tutun.|
|CS_DOCK_IMMEDIATELY|İşaretçi hemen modda dock sitesi üzerindedir (DT_IMMEDIATE stili etkindir), bu nedenle bölmenin hemen sabitlemesi gerekir.|
|CS_DELAY_DOCK|İşaretçi, başka bir yerleştirme bölmesi olan veya ana çerçevenin kenarı olan bir dock sitesi üzerindedir.|
|CS_DELAY_DOCK_TO_TAB|İşaretçi, bölmenin sekmeli bir pencerede sabitlenemesine neden olan bir dock sitesi üzerindedir. Bu, fare başka bir yerleştirme bölmesinin alt yazısının üzerinde veya sekmeli bölmenin sekme alanı nın üzerinde olduğunda oluşur.|

## <a name="cdockingmanagerdisablerestoredockstate"></a><a name="disablerestoredockstate"></a>CDockingManager::DisableRestoreDockState

Kayıt defterinden yerleştirme düzeninin yüklenmesine olanak tanır veya devre dışı kılır.

```
void DisableRestoreDockState(BOOL bDisable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bDisable*<br/>
[içinde] Kayıt defterinden yerleştirme düzeninin yüklenmesinin devre dışı sayılmak için DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Uygulama durumu yüklenirken yerleştirme bölmelerinin ve araç çubuklarının geçerli düzenini korumanız gerektiğinde bu yöntemi arayın.

## <a name="cdockingmanagerdockpane"></a><a name="dockpane"></a>CDockingManager::DockPane

Bölmeyi başka bir bölmeye veya çerçeve penceresine sabitler.

```
void DockPane(
    CBasePane* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[içinde] Bir çubuk bölmesine dock için bir işaretçi.

*nDockBarID*<br/>
[içinde] Rıhtıma demirlemek için barın kimliği.

*Lprect*<br/>
[içinde] Hedef dikdörtgen.

## <a name="cdockingmanagerdockpaneleftof"></a><a name="dockpaneleftof"></a>CDockingManager::DockPaneLeftOf

Başka bir bölmenin soluna bir bölme yapıştırın.

```
BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>Parametreler

*pBarToDock*<br/>
[içinde] bölmenin *pTargetBar'ın*soluna sabitlenecek bir işaretçi.

*pTargetBar*<br/>
[içinde] Hedef bölmeye bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bölme başarıyla kenetlenmişse DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cdockingmanagerenableautohidepanes"></a><a name="enableautohidepanes"></a>CDockingManager::EnableAutoHidePanes

Bölmenin ana çerçeveye sabitlemesini sağlar, bir dock bölmesi oluşturur ve denetim çubukları listesine ekler.

```
BOOL EnableAutoHidePanes(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
[içinde] Yerleştirme hizalaması.

### <a name="return-value"></a>Dönüş Değeri

Dock bölmesi başarıyla oluşturulduysa DOĞRU; YANLIŞ aksi takdirde.

## <a name="cdockingmanagerenabledocking"></a><a name="enabledocking"></a>CDockingManager::Etkinleştirme Docking

Bir dock bölmesi oluşturur ve bölmenin ana çerçeveye sabitlemesini sağlar.

```
BOOL EnableDocking(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
[içinde] Yerleştirme hizalaması.

### <a name="return-value"></a>Dönüş Değeri

Dock bölmesi başarıyla oluşturulduysa DOĞRU; YANLIŞ aksi takdirde.

## <a name="cdockingmanagerenabledocksitemenu"></a><a name="enabledocksitemenu"></a>CDockingManager::EnableDockSiteMenu

Tüm yerleştirme bölmelerinin alt yazılarında açılır menüyü açan ek bir düğme görüntüler.

```
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] Dock site menüsünü etkinleştirmek için TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Dock site menüsü, bölmenin yerleştirme durumunu değiştirmek için aşağıdaki seçenekleri görüntüler:

- `Floating`- Bir bölmeyi yüzdürer

- `Docking`- Bölmenin en son sabitlendiği yerdeki ana çerçeveye bir bölme yapıştırılır

- `AutoHide`- Bölmeyi otomatik hide moduna geçer

- `Hide`- Bölmeyi gizler

Varsayılan olarak, bu menü görüntülenmez.

## <a name="cdockingmanagerenablepanecontextmenu"></a><a name="enablepanecontextmenu"></a>CDockingManager::EnablePaneContextMenu

Kullanıcı sağ fare düğmesini tıklattığında ve kitaplık WM_CONTEXTMENU iletisini işlediğinde, uygulama araç çubukları ve yerleştirme bölmelerinin listesini içeren özel bir bağlam menüsünü görüntülemek için kitaplüye bildirir.

```
void EnablePaneContextMenu(
    BOOL bEnable,
    UINT uiCustomizeCmd,
    const CString& strCustomizeText,
    BOOL bToolbarsOnly = FALSE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] TRUE ise, kitaplık otomatik bağlam menüsü için desteği açar; FALSE kitaplığı otomatik bağlam menüsü için desteği kapatırsa.

*uiCustomizeCmd*<br/>
[içinde] Menüdeki **Özelleştir** öğesi için bir komut kimliği.

*strCustomizeText*<br/>
[içinde] **Özelleştir** öğesinin metni.

*bToolbarsSadece*<br/>
[içinde] TRUE ise, menü yalnızca uygulama araç çubuklarının listesini görüntüler; FALSE ise, kitaplık bu listeye uygulama yerleştirme bölmeleri ekler.

## <a name="cdockingmanagerfinddocksite"></a><a name="finddocksite"></a>CDockingManager::FindDockSite

Belirtilen konumda olan ve belirtilen hizaya sahip çubuk bölmesini alır.

```
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,
    BOOL bOuter);
```

### <a name="parameters"></a>Parametreler

*dwHizalama*<br/>
[içinde] Çubuk bölmesinin hizalanması.

*bDış*<br/>
[içinde] TRUE ise, denetim çubukları listesinde baş konumundaki çubuğu alın. Aksi takdirde, denetim çubukları listesinde kuyruk konumundaki çubuğu alın.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen hizalama olan yerleştirme bölmesi; NULL aksi takdirde.

## <a name="cdockingmanagerfindpanebyid"></a><a name="findpanebyid"></a>CDockingManager::FindPaneByID

Belirtilen denetim kimliğine göre bir bölme bulur.

```
virtual CBasePane* FindPaneByID(
    UINT uBarID,
    BOOL bSearchMiniFrames = FALSE);
```

### <a name="parameters"></a>Parametreler

*uBarID*<br/>
[içinde] Bulmak için bölmenin denetim kimliğini belirtir.

*bSearchMiniFrames*<br/>
[içinde] TRUE arama tüm kayan bölmeleri eklemek için. Yalnızca kenetlenmiş bölmeleri içerecek şekilde YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen denetim kimliğine sahip [CBasePane](../../mfc/reference/cbasepane-class.md) nesnesi veya belirtilen bölme bulunamıyorsa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingmanagerfinddocksitebypane"></a><a name="finddocksitebypane"></a>CDockingManager::FindDockSiteByPane

Hedef çubuk bölmesinin kimliğine sahip çubuk bölmesini döndürür.

```
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```

### <a name="parameters"></a>Parametreler

*pTargetBar*<br/>
[içinde] Hedef çubuk bölmesine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedef çubuk bölmesinin kimliğine sahip çubuk bölme; Böyle bir çubuk bölme yoksa NULL.

## <a name="cdockingmanagerfixupvirtualrects"></a><a name="fixupvirtualrects"></a>CDockingManager::FixupVirtualRects

Tüm geçerli araç çubuğu konumlarını sanal dikdörtgenlere adatır.

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı bir araç çubuğunu sürüklemeye başladığında, uygulama sanal *dikdörtgendeki*özgün konumunu hatırlar. Kullanıcı bir araç çubuğunu dock sitesinde taşırsa, araç çubuğu diğer araç çubuklarını değiştirebilir. Diğer araç çubuklarının özgün konumları ilgili sanal dikdörtgenlerde depolanır.

## <a name="cdockingmanagerframefrompoint"></a><a name="framefrompoint"></a>CDockingManager::FrameFromPoint

Verilen noktayı içeren çerçeveyi döndürür.

```
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,
    CPaneFrameWnd* pFrameToExclude,
    BOOL bFloatMultiOnly) const;
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
[içinde] Kontrol etmek için ekran koordinatlarında noktayı belirtir.

*pFrameToExclude*<br/>
[içinde] Dışlan bir çerçeveiçin bir işaretçi.

*bFloatMultiOnly*<br/>
[içinde] TRUE örnekleri olmayan çerçeveleri dışlamak `CMultiPaneFrameWnd`için ; YANLIŞ aksi takdirde.

### <a name="return-value"></a>Dönüş Değeri

Verilen noktayı içeren çerçeve; NULL aksi takdirde.

## <a name="cdockingmanagergetclientareabounds"></a><a name="getclientareabounds"></a>CDockingManager::GetClientAreaBounds

İstemci alanının sınırlarını içeren dikdörtgeni alır.

```
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```

### <a name="parameters"></a>Parametreler

*rcClient*<br/>
[çıkış] İstemci alanının sınırlarını içeren dikdörtgen için bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

İstemci alanının sınırlarını içeren dikdörtgen.

## <a name="cdockingmanagergetdockingmode"></a><a name="getdockingmode"></a>CDockingManager::GetDockingMode

Geçerli yerleştirme modunu döndürür.

```
static AFX_DOCK_TYPE GetDockingMode();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yerleştirme modunu temsil eden bir yerumerator değeri. Aşağıdaki değerlerden biri olabilir:

- DT_STANDARD

- DT_IMMEDIATE

- DT_SMART

### <a name="remarks"></a>Açıklamalar

Yerleştirme modunu ayarlamak için [CDockingManager'ı arayın::SetDockingMode.](#setdockingmode)

## <a name="cdockingmanagergetdocksiteframewnd"></a><a name="getdocksiteframewnd"></a>CDockingManager::GetDockSiteFrameWnd

Ana pencere çerçevesiiçin bir işaretçi alır.

```
CFrameWnd* GetDockSiteFrameWnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ana pencere çerçevesiiçin bir işaretçi.

## <a name="cdockingmanagergetenabledautohidealignment"></a><a name="getenabledautohidealignment"></a>CDockingManager::GetEnabledAutoHideAlignment

Bölmelerin etkin hizalanmasını verir.

```
DWORD GetEnabledAutoHideAlignment() const;
```

### <a name="return-value"></a>Dönüş Değeri

CBRS_ALIGN_ bayraklarının bityiş li bir leşimi veya otomatik hide bölmeleri etkinleştirilmezse 0. Daha fazla bilgi için [Bkz. CFrameWnd::EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking).

### <a name="remarks"></a>Açıklamalar

Yöntem, otomatik hide denetim çubukları için etkin hizalama döndürür. Otomatik hide çubukları etkinleştirmek için [CFrameWndEx'i arayın::Otomatik HidePanes'i etkinleştirin.](../../mfc/reference/cframewndex-class.md#enableautohidepanes)

## <a name="cdockingmanagergetminiframes"></a><a name="getminiframes"></a>CDockingManager::GetMiniFrames

Mini çerçevelerin bir listesini alır.

```
const CObList& GetMiniFrames() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yerleştirme yöneticisine ait denetim çubuklarını içeren mini çerçevelerin listesi.

## <a name="cdockingmanagergetouteredgebounds"></a><a name="getouteredgebounds"></a>CDockingManager::GetOuterEdgeBounds

Çerçevenin dış kenarlarını içeren bir dikdörtgen alır.

```
CRect GetOuterEdgeBounds() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çerçevenin dış kenarlarını içeren bir dikdörtgen.

## <a name="cdockingmanagergetpanelist"></a><a name="getpanelist"></a>CDockingManager::GetPaneList

Yerleştirme yöneticisine ait bölmelerin listesini verir. Bu, tüm kayan bölmeleri içerir.

```
void GetPaneList(
    CObList& lstBars,
    BOOL bIncludeAutohide = FALSE,
    CRuntimeClass* pRTCFilter = NULL,
    BOOL bIncludeTabs = FALSE);
```

### <a name="parameters"></a>Parametreler

*lstBars*<br/>
[içinde, dışarı] Geçerli yerleştirme yöneticisinin tüm bölmelerini içerir.

*bIncludeAutohide*<br/>
[içinde] Autohide modunda olan bölmeleri eklemek için TRUE; aksi takdirde, YANLIŞ.

*pRTCFiltre*<br/>
[içinde] NULL değilse, döndürülen liste yalnızca belirtilen çalışma zamanı sınıfının bölmelerini içerir.

*bIncludeTabs*<br/>
[içinde] SEKMELER eklemek için TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Yerleştirme yöneticisinde sekmeli bölmeler varsa, yöntem işaretçileri [CBaseTabbedPane Sınıfı](../../mfc/reference/cbasetabbedpane-class.md) nesnelerine döndürür ve sekmeleri açıkça düzeltmeniz gerekir.

Belirli bir bölme sınıfı elde etmek için *pRTCFilter'i* kullanın. Örneğin, bu değeri uygun şekilde ayarlayarak yalnızca araç çubukları elde edebilirsiniz.

## <a name="cdockingmanagergetsmartdockingmanager"></a><a name="getsmartdockingmanager"></a>CDockingManager::GetSmartDockingManager

Akıllı yerleştirme yöneticisine bir işaretçi alır.

```
CSmartDockingManager* GetSmartDockingManager();
```

### <a name="return-value"></a>Dönüş Değeri

Akıllı yerleştirme yöneticisiiçin bir işaretçi.

## <a name="cdockingmanagergetsmartdockingmanagerpermanent"></a><a name="getsmartdockingmanagerpermanent"></a>CDockingManager::GetSmartDockingManagerPermanent

Akıllı yerleştirme yöneticisine bir işaretçi alır.

```
CSmartDockingManager* GetSmartDockingManagerPermanent() const;
```

### <a name="return-value"></a>Dönüş Değeri

Akıllı yerleştirme yöneticisiiçin bir işaretçi.

## <a name="cdockingmanagergetsmartdockingparams"></a><a name="getsmartdockingparams"></a>CDockingManager::GetSmartDockingParams

Yerleştirme yöneticisi için akıllı yerleştirme parametrelerini verir.

```
static CSmartDockingInfo& GetSmartDockingParams();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yerleştirme yöneticisi için akıllı yerleştirme parametrelerini içeren sınıf. Daha fazla bilgi için [CSmartDockingInfo Sınıfı'na](../../mfc/reference/csmartdockinginfo-class.md)bakın.

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingmanagerhideautohidepanes"></a><a name="hideautohidepanes"></a>CDockingManager::HideAutoHidePanes

Otomatik hide modunda olan bir bölmeyi gizler.

```
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,
    BOOL bImmediately = FALSE);
```

### <a name="parameters"></a>Parametreler

*pBarToExclude*<br/>
[içinde] Bir çubuğun gizlenmemasını engellemek için işaretçi.

*bHemen*<br/>
[içinde] Hemen bölmeyi gizlemek için TRUE; Otohide etkisi ile bölmeyi gizlemek için FALSE.

## <a name="cdockingmanagerinsertdocksite"></a><a name="insertdocksite"></a>CDockingManager::InsertDockSite

Bir dock bölmesi oluşturur ve denetim çubukları listesine ekler.

```
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,
    DWORD dwAlignToInsertAfter,
    CDockSite** ppDockBar = NULL);
```

### <a name="parameters"></a>Parametreler

*Bilgi*<br/>
[içinde] Dock bölmesi hakkında hizalama bilgilerini içeren bir yapı.

*dwAlignToInsertAfter*<br/>
[içinde] Dock bölmesinin hizalanması.

*ppDockBar*<br/>
[çıkış] Dock bölmesine işaretçi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Dock bölmesi başarıyla oluşturulduysa DOĞRU; YANLIŞ aksi takdirde.

## <a name="cdockingmanagerinsertpane"></a><a name="insertpane"></a>CDockingManager::InsertPane

Denetim çubukları listesine bir denetim bölmesi ekler.

```
BOOL InsertPane(
    CBasePane* pControlBar,
    CBasePane* pTarget,
    BOOL bAfter = TRUE);
```

### <a name="parameters"></a>Parametreler

*pControlBar*<br/>
[içinde] Denetim bölmesine işaretçi.

*pTarget*<br/>
[içinde] Hedef bölmeye işaretçi.

*bAfter*<br/>
[içinde] Hedef bölmenin konumundan sonra bölmeyi eklemek için DOĞRU; YANLIŞ aksi takdirde.

### <a name="return-value"></a>Dönüş Değeri

Denetim bölmesi denetim çubukları listesine başarıyla eklenirse DOĞRU; YANLIŞ aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Denetim bölmesi denetim çubukları listesinde zaten yse veya hedef bölme denetim çubukları listesinde yoksa bu yöntem yanlış döndürür.

## <a name="cdockingmanagerisdocksitemenu"></a><a name="isdocksitemenu"></a>CDockingManager::IsDockSiteMenu

Açılır menü yürek bölmelerin alt yazılarında görüntülenip görüntülenmediğini belirtir.

```
static BOOL IsDockSiteMenu();
```

### <a name="return-value"></a>Dönüş Değeri

Bir dock site menüsü tüm yerleştirme bölmelerinin altyazılarında görüntülenirse DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

[CDockingManager::EnableDockSiteMenu'yi](#enabledocksitemenu)arayarak dock site menüsünü etkinleştirebilirsiniz.

## <a name="cdockingmanagerisinadjustlayout"></a><a name="isinadjustlayout"></a>CDockingManager::IsInAdjustLayout

Tüm bölmelerin düzenlerinin ayarlı paçüsten olup olmadığını belirler.

```
BOOL IsInAdjustLayout() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tüm bölmelerin düzenleri ayarlanırsa DOĞRU; YANLIŞ aksi takdirde.

## <a name="cdockingmanagerisolecontainermode"></a><a name="isolecontainermode"></a>CDockingManager::IsOLEContainerMode

Yerleştirme yöneticisinin OLE kapsayıcı modunda olup olmadığını belirtir.

```
BOOL IsOLEContainerMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yerleştirme yöneticisi OLE kapsayıcı modundaysa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

OLE kapsayıcı modunda, tüm yerleştirme bölmeleri ve uygulama araç çubukları gizlenir. [CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode) to TRUE'yu ayarladıysanız bölmeler de bu modda gizlenir.

## <a name="cdockingmanagerispointneardocksite"></a><a name="ispointneardocksite"></a>CDockingManager::IsPointNearDockSite

Belirli bir noktanın dock bölgesine yakın olup olmadığını belirler.

```
BOOL IsPointNearDockSite(
    CPoint point,
    DWORD& dwBarAlignment,
    BOOL& bOuterEdge) const;
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
[içinde] Belirtilen nokta.

*dwBarAlignment*<br/>
[çıkış] Noktanın hangi kenarın yakın olduğunu belirtir. Olası değerler CBRS_ALIGN_LEFT, CBRS_ALIGN_RIGHT, CBRS_ALIGN_TOP ve CBRS_ALIGN_BOTTOM.

*bOuterEdge*<br/>
[çıkış] Nokta rıhtım alanının dış sınırına yakınsa DOĞRU; YANLIŞ aksi takdirde.

### <a name="return-value"></a>Dönüş Değeri

Nokta rıhtım alanına yakınsa DOĞRU; aksi takdirde YANLIŞ.

## <a name="cdockingmanagerisprintpreviewvalid"></a><a name="isprintpreviewvalid"></a>CDockingManager::IsPrintPreviewValid

Yazdırma önizleme modunun ayarlı olup olmadığını belirler.

```
BOOL IsPrintPreviewValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırma önizleme modu ayarlanmışsa TRUE; YANLIŞ aksi takdirde.

## <a name="cdockingmanagerloadstate"></a><a name="loadstate"></a>CDockingManager::LoadState

Takma yöneticisinin durumunu kayıt defterinden yükler.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[içinde] Profil adı.

*uiID*<br/>
[içinde] Yanaşma yöneticisinin kimliği.

### <a name="return-value"></a>Dönüş Değeri

Yerleştirme yöneticisi durumu başarıyla yüklenmişse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cdockingmanagerlockupdate"></a><a name="lockupdate"></a>CDockingManager::LockUpdate

Verilen pencereyi kilitler.

```
void LockUpdate(BOOL bLock);
```

### <a name="parameters"></a>Parametreler

*Blok*<br/>
[içinde] Pencere kilitliyse DOĞRU; YANLIŞ aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bir pencere kilitlendiğinde, hareket ettirilemez ve yeniden çizilemez.

## <a name="cdockingmanagerm_bhidedockingbarsincontainermode"></a><a name="m_bhidedockingbarsincontainermode"></a>CDockingManager::m_bHideDockingBarsInContainerMode

Yerleştirme yöneticisinin bölmeleri OLE kapsayıcı modunda gizleyip gizlemediğini belirtir.

```
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;
```

### <a name="remarks"></a>Açıklamalar

Uygulama OLE kapsayıcı modundayken ana çerçeveye sabitlenmiş tüm bölmeleri görünür tutmak istiyorsanız bu değeri FALSE olarak ayarlayın. Varsayılan olarak, bu değer TRUE'dur.

## <a name="cdockingmanagerm_dockmodeglobal"></a><a name="m_dockmodeglobal"></a>CDockingManager::m_dockModeGlobal

Genel yerleştirme modunu belirtir.

```
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, her yerleştirme bölmesi bu yerleştirme modunu kullanır. Bu alanın ayarlanabileceği değerler hakkında daha fazla bilgi için [Bkz. CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).

## <a name="cdockingmanagerm_ndocksensitivity"></a><a name="m_ndocksensitivity"></a>CDockingManager::m_nDockSensitivity

Yerleştirme hassasiyetini belirtir.

```
AFX_IMPORT_DATA static int m_nDockSensitivity;
```

### <a name="remarks"></a>Açıklamalar

Yerleştirme duyarlılığı, kayan bölmenin, çerçeve nin durumunu kenetlenmiş olarak değiştirmeden önce bir yerleştirme bölmesine, yerleştirme alanına veya başka bir bölmeye ne kadar yaklaşabileceğini tanımlar.

## <a name="cdockingmanagerm_ntimeoutbeforedockingbardock"></a><a name="m_ntimeoutbeforedockingbardock"></a>CDockingManager::m_nTimeOutBeforeDockingBarDock

Yerleştirme bölmesi hemen yerleştirme modunda kenetlenmeden önce saati milisaniye cinsinden belirtir.

```
static UINT m_nTimeOutBeforeDockingBarDock;
```

### <a name="remarks"></a>Açıklamalar

Bölme kenetlenmeden önce, çerçeve belirtilen süreyi bekler. Bu, kullanıcı hala sürüklerken bölmenin yanlışlıkla bir konuma sabitlemesini önler.

## <a name="cdockingmanagerm_ntimeoutbeforetoolbardock"></a><a name="m_ntimeoutbeforetoolbardock"></a>CDockingManager::m_nTimeOutBeforeToolBarDock

Araç çubuğu ana çerçeve penceresine sabitlenmeden önce saati milisaniye cinsinden belirtir.

```
static UINT m_nTimeOutBeforeToolBarDock;
```

### <a name="remarks"></a>Açıklamalar

Araç çubuğu kenetlenmeden önce, çerçeve belirtilen süreyi bekler. Bu, kullanıcı hala sürüklerken araç çubuğunun yanlışlıkla bir konuma sabitlemesini önler.

## <a name="cdockingmanageronactivateframe"></a><a name="onactivateframe"></a>CDockingManager::OnActivateFrame

Çerçeve penceresi etkin hale getirildiğinde veya devre dışı bırakıldığında çerçeve tarafından çağrılır.

```
virtual void OnActivateFrame(BOOL bActivate);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] TRUE ise, çerçeve penceresi etkin hale getirilir; FALSE ise, çerçeve penceresi devre dışı bırakılır.

## <a name="cdockingmanageronclosepopupmenu"></a><a name="onclosepopupmenu"></a>CDockingManager::OnClosePopupMenu

Etkin bir açılır menü bir WM_DESTROY iletisi işlediğinde çerçeve tarafından çağrılır.

```
void OnClosePopupMenu();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, geçerli ana pencereyi kapatmak üzereyken WM_DESTROY bir ileti gönderir. Bir `CMFCPopupMenu` nesne WM_DESTROY iletisi `CMFCPopupMenu` işlerken çerçeve penceresine ait nesnelerden bildirimleri işlemek için bu yöntemi geçersiz kılın.

## <a name="cdockingmanageronmoveminiframe"></a><a name="onmoveminiframe"></a>CDockingManager::OnMoveMiniFrame

Bir mini çerçeve penceresi taşımak için çerçeve tarafından çağrılır.

```
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```

### <a name="parameters"></a>Parametreler

*pFrame*<br/>
[içinde] Mini çerçeve penceresi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa DOĞRU; aksi takdirde YANLIŞ.

## <a name="cdockingmanageronpanecontextmenu"></a><a name="onpanecontextmenu"></a>CDockingManager::OnPaneContextMenu

Bölmelerin bir listesini içeren bir menü oluşturduğunda çerçeve tarafından çağrılır.

```
void OnPaneContextMenu(CPoint point);
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
[içinde] Menünün konumunu belirtir.

## <a name="cdockingmanagerpanefrompoint"></a><a name="panefrompoint"></a>CDockingManager::PaneFromPoint

Verilen noktayı içeren bölmeyi döndürür.

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

*Nokta*<br/>
[içinde] Kontrol etmek için ekran koordinatlarında noktayı belirtir.

*nDuyarlılık*<br/>
[içinde] Denetlenen her bölmenin pencere dikdörtgenini şişirme değeri. Verilen nokta bu şişirilmiş bölgedeyse, bölme arama ölçütlerini karşılar.

*bExactBar*<br/>
[içinde] *NSensitivity* parametresini yoksaymak için DOĞRU; aksi takdirde, YANLIŞ.

*pRTCBarType*<br/>
[içinde] NULL değilse, yöntem yalnızca belirtilen türdeki bölmeleri arar.

*bCheckGörünürlük*<br/>
[içinde] True sadece görünür bölmeleri kontrol etmek için; aksi takdirde, YANLIŞ.

*dwHizalama*<br/>
[çıkış] Belirtilen noktada bir bölme bulunursa, bu parametre bölmenin belirtilen noktaya en yakın tarafını içerir. Daha fazla bilgi için Açıklamalar bölümüne bakın.

*pBarToIgnore*<br/>
[içinde] NULL değilse, yöntem bu parametre tarafından belirtilen bölmeleri yoksa.

### <a name="return-value"></a>Dönüş Değeri

Verilen noktayı içeren [CBasePane](../../mfc/reference/cbasepane-class.md)türetilmiş nesne veya bölme bulunamadıysa NULL.

### <a name="remarks"></a>Açıklamalar

İşlev döndürdüğünde ve bir bölme bulunduğunda, *dwAlignment* belirtilen noktanın hizalanmasını içerir. Örneğin, nokta bölmenin en üstüne en yakın sayılsaydı, *dwAlignment* CBRS_ALIGN_TOP olarak ayarlanır.

## <a name="cdockingmanagerprocesspanecontextmenucommand"></a><a name="processpanecontextmenucommand"></a>CDockingManager::ProcessPaneContextMenuCommand

Belirtilen komut için bir onay kutusunu seçmek veya temizlemek ve gösterilen bölmenin düzenini yeniden hesaplamak için çerçeve tarafından çağrılır.

```
BOOL ProcessPaneContextMenuCommand(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
[içinde] Menüdeki bir kontrol çubuğunun kimliği.

*Ncode*<br/>
[içinde] Komut bildirim kodu.

*pEkstra*<br/>
[içinde] `CCmdUI` *nCode'un* CN_UPDATE_COMMAND_UI olup olmadığını işaretçiye atan geçersiz kılma işaretçisi.

*pHandlerInfo*<br/>
[içinde] Bilgi yapısına işaretçi. Bu parametre kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

*pEXtra* NULL değilse ve *nCode* CN_UPDATE_COMMAND_UI eşitse veya belirtilen *nID'ye*sahip bir kontrol çubuğu varsa DOĞRU.

## <a name="cdockingmanagerrecalclayout"></a><a name="recalclayout"></a>CDockingManager::RecalcLayout

Denetimler listesinde bulunan denetimlerin iç düzenini yeniden hesaplar.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Parametreler

*bNotify*<br/>
[içinde] Bu parametre kullanılmaz.

## <a name="cdockingmanagerreleaseemptypanecontainers"></a><a name="releaseemptypanecontainers"></a>CDockingManager::ReleaseEmptyPaneContainers

Boş bölme kapsayıcılarını serbest bırakır.

```
void ReleaseEmptyPaneContainers();
```

## <a name="cdockingmanagerremovehiddenmditabbedbar"></a><a name="removehiddenmditabbedbar"></a>CDockingManager::RemoveHiddenMDITabbedBar

Belirtilen gizli çubuk bölmesini kaldırır.

```
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[içinde] Kaldırmak için bir çubuk bölmeiçin bir işaretçi.

## <a name="cdockingmanagerremoveminiframe"></a><a name="removeminiframe"></a>CDockingManager::RemoveMiniFrame

Mini çerçeveler listesinden belirtilen bir çerçeveyi kaldırır.

```
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
[içinde] Kaldırılacak bir çerçeveiçin işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen çerçeve kaldırılırsa DOĞRU; YANLIŞ aksi takdirde.

## <a name="cdockingmanagerremovepanefromdockmanager"></a><a name="removepanefromdockmanager"></a>CDockingManager::RemovePaneFromDockManager

Bölmenin kaydını kaldırır ve yerleştirme yöneticisindeki listeden kaldırır.

```
void RemovePaneFromDockManager(
    CBasePane* pWnd,
    BOOL bDestroy,
    BOOL bAdjustLayout,
    BOOL bAutoHide = FALSE,
    CBasePane* pBarReplacement = NULL);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
[içinde] Kaldırılacak bölmeiçin bir işaretçi.

*bYok et*<br/>
[içinde] TRUE ise, kaldırılan bölme yok edilir.

*bAdjustLayout*<br/>
[içinde] TRUE ise, yerleştirme düzenini hemen ayarlayın.

*bAutoHide*<br/>
[içinde] TRUE ise bölme otomatik hide çubukları listesinden kaldırılır. FALSE ise, bölme normal bölmeler listesinden kaldırılır.

*pBarReplacement*<br/>
[içinde] Kaldırılan bölmenin yerini alan bölmeye işaretçi.

## <a name="cdockingmanagerreplacepane"></a><a name="replacepane"></a>CDockingManager::ReplacePane

Bir bölmeyi diğeriyle değiştirir.

```
BOOL ReplacePane(
    CDockablePane* pOriginalBar,
    CDockablePane* pNewBar);
```

### <a name="parameters"></a>Parametreler

*pOriginalBar*<br/>
[içinde] Özgün bölmeye işaretçi.

*pNewBar*<br/>
[içinde] Özgün bölmenin yerini alan bölmeye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bölme başarıyla değiştirilirse DOĞRU; YANLIŞ aksi takdirde.

## <a name="cdockingmanagerresortminiframesforzorder"></a><a name="resortminiframesforzorder"></a>CDockingManager::ResortMiniFramesForZOrder

Mini çerçeveler listesindeki çerçeveleri tatil eder.

```
void ResortMiniFramesForZOrder();
```

## <a name="cdockingmanagersavestate"></a><a name="savestate"></a>CDockingManager::SaveState

Takma yöneticisinin durumunu kayıt defterine kaydeder.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[içinde] Kayıt defteri anahtarına giden yol.

*uiID*<br/>
[içinde] Yerleştirme yöneticisi kimliği.

### <a name="return-value"></a>Dönüş Değeri

Devlet başarıyla kaydedildiyse DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Takma yöneticisinin durumunu kayıt defterine kaydetmek, denetim çubuklarının durumlarını, otomatik hide çubuklarının durumlarını ve yerleştirme yöneticisinde bulunan mini çerçevelerin durumlarını kaydetmeyi içerir.

## <a name="cdockingmanagersendmessagetominiframes"></a><a name="sendmessagetominiframes"></a>CDockingManager::SendMessageToMiniFrames

Belirtilen iletiyi tüm mini çerçevelere gönderir.

```
BOOL SendMessageToMiniFrames(
    UINT uMessage,
    WPARAM wParam = 0,
    LPARAM lParam = 0);
```

### <a name="parameters"></a>Parametreler

*uMessage*<br/>
[içinde] Gönderilecek ileti.

*Wparam*<br/>
[içinde] Ek ileti bağımlı bilgiler.

*Lparam*<br/>
[içinde] Ek ileti bağımlı bilgiler.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU her zaman.

## <a name="cdockingmanagerserialize"></a><a name="serialize"></a>CDockingManager::Serialize

Yerleştirme yöneticisini bir arşive yazar.

```
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
[içinde] Arşiv nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

Yerleştirme yöneticisinin bir arşive yazılması, yerleştirme denetim çubukları nın ve kaydırıcılarının sayısını belirlemeyi ve denetim çubuklarını, mini çerçeveleri, otomatik hide çubuklarını ve MDI sekmeli çubuklarını arşive yazmayı içerir.

## <a name="cdockingmanagersetautohidezorder"></a><a name="setautohidezorder"></a>CDockingManager::SetAutohideZOrder

Denetim çubuklarının ve belirtilen bölmenin boyutunu, genişliğini ve yüksekliğini ayarlar.

```
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```

### <a name="parameters"></a>Parametreler

*pAHDockingBar*<br/>
[içinde] Takılabilir bölmeiçin bir işaretçi.

## <a name="cdockingmanagersetdockingmode"></a><a name="setdockingmode"></a>CDockingManager::SetDockingMode

Yerleştirme modunu ayarlar.

```
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```

### <a name="parameters"></a>Parametreler

*dockMode*<br/>
Yeni yerleştirme modunu belirtir. Daha fazla bilgi için Açıklamalar bölümüne bakın.

*Tema*<br/>
Akıllı yerleştirme işaretleri için kullanılacak temayı belirtir. Aşağıdaki numaralandırılmış değerlerden biri olabilir: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.

### <a name="remarks"></a>Açıklamalar

Yerleştirme modunu ayarlamak için bu statik yöntemi çağırın.

*dockMode* aşağıdaki değerlerden biri olabilir:

- DT_STANDARD - Visual Studio .NET 2003'te uygulanan standart yerleştirme modu. Bölmeler sürükleme bağlamı olmadan sürüklenir.

- DT_IMMEDIATE - Microsoft Visio'da uygulandığı gibi anında yerleştirme modu. Bölmeler sürükleme bağlamıyla sürüncemede kalır, ancak işaretçiler görüntülenmez.

- DT_SMART - Visual Studio 2005'te uygulanan akıllı yerleştirme modu. Bölmeler sürükleme bağlamıyla sürüklenir ve bölmenin nerede sabitlenebileceğini gösteren akıllı işaretçiler görüntülenir.

## <a name="cdockingmanagersetdockstate"></a><a name="setdockstate"></a>CDockingManager::SetDockState

Denetim çubuklarının, mini çerçevelerin ve otomatik hide çubuklarının takma durumunu ayarlar.

```
virtual void SetDockState();
```

## <a name="cdockingmanagersetprintpreviewmode"></a><a name="setprintpreviewmode"></a>CDockingManager::SetPrintPreviewMode

Yazdırma önizlemesinde görüntülenen çubukların yazdırma önizleme modunu ayarlar.

```
void SetPrintPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>Parametreler

*bÖnizleme*<br/>
[içinde] Yazdırma önizleme modu ayarlanmışsa TRUE; YANLIŞ aksi takdirde.

*pDevlet*<br/>
[içinde] Önizleme durumuna işaretçi. Bu parametre kullanılmaz.

## <a name="cdockingmanagersetsmartdockingparams"></a><a name="setsmartdockingparams"></a>CDockingManager::SetSmartDockingParams

Akıllı yerleştirme davranışını tanımlayan parametreleri ayarlar.

```
static void SetSmartDockingParams(CSmartDockingInfo& params);
```

### <a name="parameters"></a>Parametreler

*params*<br/>
[içinde, dışarı] Akıllı yerleştirme parametrelerini tanımlar.

### <a name="remarks"></a>Açıklamalar

Akıllı yerleştirme işaretçilerinin görünümünü, rengini veya şeklini özelleştirmek istiyorsanız bu yöntemi arayın.

Akıllı yerleştirme işaretleri için varsayılan görünümü kullanmak için, [csmartDockingInfo Sınıfı'nın](../../mfc/reference/csmartdockinginfo-class.md) başharflenmemiş bir örneğini *paramlara*geçirin.

## <a name="cdockingmanagershowdelayshowminiframes"></a><a name="showdelayshowminiframes"></a>CDockingManager::ShowDelayShowMiniFrames

Mini çerçevelerin pencerelerini gösterir veya gizler.

```
void ShowDelayShowMiniFrames(BOOL bshow);
```

### <a name="parameters"></a>Parametreler

*bGöster*<br/>
[içinde] Gösterilen çerçevenin penceresini etkin kılmak için TRUE; ÇERÇEVEPENCERESI gizlemek için FALSE.

## <a name="cdockingmanagershowpanes"></a><a name="showpanes"></a>CDockingManager::ShowPanes

Denetim ve otomatik hide çubukların bölmelerini gösterir veya gizler.

```
virtual BOOL ShowPanes(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bGöster*<br/>
[içinde] DOĞRU bölmeleri göstermek için; Bölmeleri gizlemek için YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

Her zaman FALSE.

## <a name="cdockingmanagerstartsdocking"></a><a name="startsdocking"></a>CDockingManager::Başlangıç Docking

Akıllı yerleştirme yöneticisinin hizasına göre belirtilen pencerenin akıllı yerleştirmesini başlatır.

```
void StartSDocking(CWnd* pDockingWnd);
```

### <a name="parameters"></a>Parametreler

*pDockingWnd*<br/>
[içinde] Kenetlenme penceresi için bir işaretçi.

## <a name="cdockingmanagerstopsdocking"></a><a name="stopsdocking"></a>CDockingManager::StopSDocking

Akıllı kenetlenmeyi durdurur.

```
void StopSDocking();
```

## <a name="cdockingmanagergetsmartdockingtheme"></a><a name="getsmartdockingtheme"></a>CDockingManager::GetSmartDockingTheme

Akıllı yerleştirme işaretçilerini görüntülemek için kullanılan bir tema döndüren statik bir yöntem.

```
static AFX_SMARTDOCK_THEME __stdcall GetSmartDockingTheme();
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki numaralandırılmış değerlerden birini döndürür: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[CFrameWndEx Sınıfı](../../mfc/reference/cframewndex-class.md)<br/>
[CDockablePane Sınıfı](../../mfc/reference/cdockablepane-class.md)<br/>
[CPaneFrameWnd Sınıf](../../mfc/reference/cpaneframewnd-class.md)
