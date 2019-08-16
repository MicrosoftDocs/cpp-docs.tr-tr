---
title: CDockingManager sınıfı
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
ms.openlocfilehash: 8709b3a4eb3f57a3d2700ad7aaed16df994245c5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506865"
---
# <a name="cdockingmanager-class"></a>CDockingManager sınıfı

Ana çerçeve penceresinde yerleştirme yerleşimini denetleyen temel işlevselliği uygular.

## <a name="syntax"></a>Sözdizimi

```
class CDockingManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDockingManager:: AddDockSite](#adddocksite)|Bir yerleştirme bölmesi oluşturur ve denetim çubukları listesine ekler.|
|[CDockingManager:: Addhiddenmdıtabbedbar](#addhiddenmditabbedbar)|Bir çubuk bölmesine gizli MDI sekmeli çubuk bölmeleri listesine bir işleyici ekler.|
|[CDockingManager:: AddMiniFrame](#addminiframe)|Mini kareler listesine bir çerçeve ekler.|
|[CDockingManager:: AddPane](#addpane)|Yerleştirme yöneticisiyle bir bölme kaydeder.|
|[CDockingManager:: AdjustDockingLayout](#adjustdockinglayout)|Bir çerçeve penceresinde tüm bölmelerin yerleşimini yeniden hesaplar ve ayarlar.|
|[CDockingManager:: Adjustbölmesi çerçeveleri](#adjustpaneframes)|WM_NCCALCSIZE iletisinin tüm bölmelere ve `CPaneFrameWnd` pencerelere gönderilmesine neden olur.|
|[CDockingManager:: AdjustRectToClientArea](#adjustrecttoclientarea)|Bir dikdörtgenin hizalamasını ayarlar.|
|[CDockingManager:: AlignAutoHidePane](#alignautohidepane)|Bir yerleştirme bölmesini otomatik olarak yeniden boyutlandırır ve bu sayede, sitelerin Dock 'ın istemci alanının tam genişliğini veya yüksekliğini sitelere yerleştir.|
|[CDockingManager:: oto Hidepane](#autohidepane)|Otomatik gizleme araç çubuğu oluşturur.|
|[CDockingManager:: BringBarsToTop](#bringbarstotop)|Belirtilen hizalamayı en üste getiren sabitlenmiş çubukları getirir.|
|[CDockingManager:: BuildPanesMenu](#buildpanesmenu)|Bir menüye yerleştirme bölmeleri ve araç çubuklarının adlarını ekler.|
|[CDockingManager:: CalcExpectedDockedRect](#calcexpecteddockedrect)|Yerleşik pencerenin beklenen dikdörtgenini hesaplar.|
|[CDockingManager:: Create](#create)|Bir yerleştirme Yöneticisi oluşturur.|
|[CDockingManager::D Eterminebölmesi Andstatus](#determinepaneandstatus)|Belirli bir noktayı ve yerleştirme durumunu içeren bölmeyi belirler.|
|[CDockingManager::D isableRestoreDockState](#disablerestoredockstate)|Kayıt defterinden yerleştirme düzeninin yüklenmesine izin vermez veya devre dışı bırakır.|
|[CDockingManager::D ockPane](#dockpane)|Bir bölmeyi başka bir bölmeye veya bir çerçeve penceresine göre oluşturma.|
|[CDockingManager::D ockPaneLeftOf](#dockpaneleftof)|Başka bir bölmenin solunda bir bölme noktası oluşturma.|
|[CDockingManager:: Enableoto Hidebölmeleri](#enableautohidepanes)|Bölmenin ana çerçeveye yerleştirmeyi sağlar, bir dock bölmesi oluşturur ve denetim çubukları listesine ekler.|
|[CDockingManager:: EnableDocking](#enabledocking)|Bir yerleştirme bölmesi oluşturur ve bölmenin ana çerçeveye yerleştirmeyi sağlar.|
|[CDockingManager:: EnableDockSiteMenu](#enabledocksitemenu)|Tüm yerleştirme bölmelerindeki açıklamalı alt yazıların açılan menüyü açan ek bir düğme görüntüler.|
|[CDockingManager:: Enablebölmesi ContextMenu](#enablepanecontextmenu)|Kitaplığa, Kullanıcı sağ fare düğmesine tıkladığında ve kitaplık WM_CONTEXTMENU iletisini işlerken, uygulama araç çubukları ve yerleştirme bölmeleri listesine sahip özel bir bağlam menüsü görüntülemesini söyler.|
|[CDockingManager:: FindDockSite](#finddocksite)|Belirtilen konumdaki ve belirtilen hizalamaya sahip olan çubuk bölmesini alır.|
|[CDockingManager:: FindDockSiteByPane](#finddocksitebypane)|Hedef çubuk bölmesinin kimliği olan çubuk bölmesini döndürür.|
|[CDockingManager:: Findbölmesi Byıd](#findpanebyid)|Belirtilen denetim KIMLIĞIYLE bir bölme bulur.|
|[CDockingManager:: FixupVirtualRects](#fixupvirtualrects)|Tüm geçerli araç çubuğu konumlarını sanal dikdörtgenlere kaydeder.|
|[CDockingManager:: FrameFromPoint](#framefrompoint)|Verilen noktayı içeren çerçeveyi döndürür.|
|[CDockingManager:: Getclientareasýnýrlarý](#getclientareabounds)|İstemci alanının sınırlarını içeren dikdörtgeni alır.|
|[CDockingManager:: GetDockingMode](#getdockingmode)|Geçerli yerleştirme modunu döndürür.|
|[CDockingManager:: GetDockSiteFrameWnd](#getdocksiteframewnd)|Üst pencere çerçevesine bir işaretçi alır.|
|[CDockingManager:: Getenabledadutohidehizalaması](#getenabledautohidealignment)|Bölmelerin etkin hizalamasını döndürür.|
|[CDockingManager:: Getminiframe 'Ler](#getminiframes)|Miniframe 'ler listesini alır.|
|[CDockingManager:: Getouteredgesınırlara](#getouteredgebounds)|Çerçevenin dış kenarlarını içeren bir dikdörtgen alır.|
|[CDockingManager:: Getbölmesi listesi](#getpanelist)|Yerleşik yöneticiye ait olan bölmelerin listesini döndürür. Bu, tüm kayan bölmeleri içerir.|
|[CDockingManager:: GetSmartDockingManager](#getsmartdockingmanager)|Akıllı yerleştirme Yöneticisi için bir işaretçi alır.|
|[CDockingManager:: Getsmartdockingmanagerkalıcı](#getsmartdockingmanagerpermanent)|Akıllı yerleştirme Yöneticisi için bir işaretçi alır.|
|[CDockingManager:: GetSmartDockingParams](#getsmartdockingparams)|Yerleşik yöneticinin akıllı yerleştirme parametrelerini döndürür.|
|[CDockingManager:: GetSmartDockingTheme](#getsmartdockingtheme)|Akıllı yerleştirme işaretleyicilerini göstermek için kullanılan bir temayı döndüren statik bir yöntem.|
|[CDockingManager:: Hideoto Hidebölmeleri](#hideautohidepanes)|Otomatik gizleme modundaki bir bölmeyi gizler.|
|[CDockingManager:: ınsertdocksite](#insertdocksite)|Bir yerleştirme bölmesi oluşturur ve denetim çubukları listesine ekler.|
|[CDockingManager:: InsertPane](#insertpane)|Denetim çubukları listesine bir denetim bölmesi ekler.|
|[CDockingManager:: IsDockSiteMenu](#isdocksitemenu)|Tüm bölmelerin resim yazılarında bir açılır menünün görüntülenip görüntülenmeyeceğini belirtir.|
|[CDockingManager:: ısınadjustlayout](#isinadjustlayout)|Tüm bölmelerin düzenlerin ayarlanacağını belirler.|
|[CDockingManager:: ısolecontainermode](#isolecontainermode)|Yerleşik yöneticinin OLE kapsayıcı modunda olup olmadığını belirtir.|
|[CDockingManager:: Ispointyaklaştığında Docksite](#ispointneardocksite)|Belirtilen noktanın Dock sitesine yakın olup olmadığını belirler.|
|[CDockingManager:: ısprintönizlemesi geçerli](#isprintpreviewvalid)|Baskı Önizleme modunun ayarlanmış olup olmadığını belirler.|
|[CDockingManager:: LoadState](#loadstate)|Kayıt defterindeki yerleştirme yöneticisinin durumunu yükler.|
|[CDockingManager:: LockUpdate](#lockupdate)|Verilen pencereyi kilitler.|
|[CDockingManager:: OnActivateFrame](#onactivateframe)|Çerçeve penceresi etkin hale getirildiğinde veya devre dışı bırakıldığında Framework tarafından çağırılır.|
|[CDockingManager:: OnClosePopupMenu](#onclosepopupmenu)|Etkin bir açılır menü bir WM_DESTROY iletisini işlediğinde Framework tarafından çağırılır.|
|[CDockingManager:: OnMoveMiniFrame](#onmoveminiframe)|Bir mini çerçeve penceresini taşımak için Framework tarafından çağırılır.|
|[CDockingManager:: Onbölmesi ContextMenu](#onpanecontextmenu)|Bir bölme listesi olan bir menü oluşturduğunda Framework tarafından çağırılır.|
|[CDockingManager::P aneFromPoint](#panefrompoint)|Verilen noktayı içeren bölmeyi döndürür.|
|[CDockingManager::P rocessPaneContextMenuCommand](#processpanecontextmenucommand)|Belirtilen komutun onay kutusunu seçmek veya temizlemek ve gösterilen bölmenin yerleşimini yeniden hesaplamak için Framework tarafından çağırılır.|
|[CDockingManager:: RecalcLayout](#recalclayout)|Denetimler listesinde bulunan denetimlerin iç yerleşimini yeniden hesaplar.|
|[CDockingManager:: ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|Boş bölme kapsayıcılarını serbest bırakır.|
|[CDockingManager:: Removehiddenmdıtabbedbar](#removehiddenmditabbedbar)|Belirtilen gizli çubuk bölmesini kaldırır.|
|[CDockingManager:: RemoveMiniFrame](#removeminiframe)|Belirtilen çerçeveyi mini çerçeveler listesinden kaldırır.|
|[CDockingManager:: RemovePaneFromDockManager](#removepanefromdockmanager)|Bir bölmenin kaydını siler ve yerleştirme yöneticisindeki listeden kaldırır.|
|[CDockingManager:: ReplacePane](#replacepane)|Bir bölmeyi diğeri ile değiştirir.|
|[CDockingManager:: Resortminifoymesforzorder](#resortminiframesforzorder)|Mini çerçeveler listesindeki çerçeveleri yeniden ölçeklendirin.|
|[CDockingManager:: Savemlak](#savestate)|Yerleştirme yöneticisinin durumunu kayıt defterine kaydeder.|
|[CDockingManager:: Sendmessagetominiframe](#sendmessagetominiframes)|Belirtilen iletiyi tüm mini çerçevelere gönderir.|
|[CDockingManager:: serileştirme](#serialize)|Yerleştirme yöneticisini bir arşive yazar. ( [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize)geçersiz kılar.)|
|[CDockingManager:: SetAutohideZOrder](#setautohidezorder)|Denetim çubuklarının boyutunu, genişliğini ve yüksekliğini, belirtilen bölmeyi ayarlar.|
|[CDockingManager:: SetDockingMode](#setdockingmode)|Yerleştirme modunu ayarlar.|
|[CDockingManager:: SetDockState](#setdockstate)|Denetim çubuklarının, Mini karelerin ve otomatik gizleme çubuklarının yerleştirme durumunu ayarlar.|
|[CDockingManager:: Setprintönizleme modu](#setprintpreviewmode)|Baskı önizlemede görüntülenen çubukların Baskı Önizleme modunu ayarlar.|
|[CDockingManager:: SetSmartDockingParams](#setsmartdockingparams)|Akıllı yerleştirme davranışını tanımlayan parametreleri ayarlar.|
|[CDockingManager:: Showdelayshowminiframe](#showdelayshowminiframes)|Mini çerçevelerin pencerelerini gösterir veya gizler.|
|[CDockingManager:: Showbölmeler](#showpanes)|Denetim ve otomatik gizleme çubuklarının bölmelerini gösterir veya gizler.|
|[CDockingManager:: StartSDocking](#startsdocking)|Akıllı yerleşik yöneticinin hizalamasına göre belirtilen pencerenin akıllı olarak yuvalanmasına başlar.|
|[CDockingManager:: StopSDocking](#stopsdocking)|Akıllı yerleştirmeyi durdur.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDockingManager:: m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|Yerleştirme yöneticisinin, OLE kapsayıcı modundaki bölmeleri gizleyemeyeceğini belirtir.|
|[CDockingManager:: m_dockModeGlobal](#m_dockmodeglobal)|Genel yerleştirme modunu belirtir.|
|[CDockingManager:: m_nDockSensitivity](#m_ndocksensitivity)|Yerleştirme hassasiyetini belirtir.|
|[CDockingManager:: m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|Takma bölmesinin anında yerleştirme moduna yerleştirilme süresini milisaniye olarak belirtir.|
|[CDockingManager:: m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|Bir araç çubuğunun ana çerçeve penceresine yerleştirilme süresini milisaniye olarak belirtir.|

## <a name="remarks"></a>Açıklamalar

Ana çerçeve penceresi bu sınıfı otomatik olarak oluşturur ve başlatır.

Docking Manager nesnesi, yerleştirme düzeninde olan tüm bölmelerin bir listesini ve ayrıca ana çerçeve penceresine ait olan tüm [Cpgframewnd](../../mfc/reference/cpaneframewnd-class.md) pencerelerinin bir listesini tutar.

Sınıfı `CDockingManager` , bir bölmeyi `CPaneFrameWnd` veya pencereyi bulmak için kullanabileceğiniz bazı hizmetleri uygular. Genellikle bu hizmetleri, ana çerçeve pencere nesnesine sarmalandıklarından doğrudan çağırmayın. Daha fazla bilgi için bkz. [Cbölmesi Framewnd sınıfı](../../mfc/reference/cpaneframewnd-class.md).

## <a name="customization-tips"></a>Özelleştirme Ipuçları

Aşağıdaki ipuçları nesneler için `CDockingManager` geçerlidir:

- [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md) bu yerleştirme modlarını destekler:

  - `AFX_DOCK_TYPE::DT_IMMEDIATE`

  - `AFX_DOCK_TYPE::DT_STANDARD`

  - `AFX_DOCK_TYPE::DT_SMART`

  Bu yerleştirme modları [CDockingManager:: m_dockModeGlobal](#m_dockmodeglobal) tarafından tanımlanır ve [CDockingManager:: SetDockingMode](#setdockingmode)çağırarak ayarlanır.

- Kayan olmayan, yeniden boyutlandırılabilir bir bölme oluşturmak istiyorsanız [CDockingManager:: AddPane](#addpane) yöntemini çağırın. Bu yöntem, bölmeyi bölmenin düzeninden sorumlu olan yerleştirme Yöneticisi ile kaydeder.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CDockingManager` `CDockingManager` nesneyi yapılandırmak için sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir. Örnek, tüm yerleştirme bölmelerindeki açıklamalı alt yazıların açılan menüyü açan ve nesnenin yerleştirme modunun nasıl ayarlanacağı hakkında ek bir düğmenin nasıl görüntüleneceğini gösterir. Bu kod parçacığı, [Visual Studio Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CDockingManager](../../mfc/reference/cdockingmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxDockingManager. h

##  <a name="adddocksite"></a>CDockingManager:: AddDockSite

Bir yerleştirme bölmesi oluşturur ve denetim çubukları listesine ekler.

```
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,
    CDockSite** ppDockBar = NULL);
```

### <a name="parameters"></a>Parametreler

*bilgisine*<br/>
'ndaki Dock bölmesi hizalamasını içeren bir bilgi yapısına başvuru.

*ppDockBar*<br/>
dışı Yeni yerleştirme bölmesi işaretçisi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Dock bölmesi başarıyla oluşturulduysa TRUE; Aksi takdirde FALSE.

##  <a name="addhiddenmditabbedbar"></a>CDockingManager:: Addhiddenmdıtabbedbar

Bir çubuk bölmesine gizli MDI sekmeli çubuk bölmeleri listesine bir işleyici ekler.

```
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
'ndaki Çubuk bölmesi işaretçisi

##  <a name="addpane"></a>CDockingManager:: AddPane

Yerleştirme yöneticisiyle bir bölme kaydeder.

```
BOOL AddPane(
    CBasePane* pWnd,
    BOOL bTail = TRUE,
    BOOL bAutoHide = FALSE,
    BOOL bInsertForOuterEdge = FALSE);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
[in, out] Yerleştirme yöneticisine eklenecek bölmeyi belirtir.

*bTail*<br/>
'ndaki Bölmeyi yerleştirme yöneticisinin bölme listesinin sonuna eklemek için TRUE; Aksi takdirde, FALSE.

*bAutoHide*<br/>
'ndaki Yalnızca iç kullanım içindir. Her zaman varsayılan değeri FALSE kullanın.

*bInsertForOuterEdge*<br/>
'ndaki Yalnızca iç kullanım içindir. Her zaman varsayılan değeri FALSE kullanın.

### <a name="return-value"></a>Dönüş Değeri

Bölme, yerleşik yöneticiye başarıyla kaydettirilirse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Yerleştirme Yöneticisi ile kayan olmayan, yeniden boyutlandırılabilir bölmeleri kaydetmek için bu yöntemi çağırın. Bölmeleri kaydetmeyin, yerleştirme Yöneticisi yerleştirildiğinde doğru görünmez.

##  <a name="adjustdockinglayout"></a>CDockingManager:: AdjustDockingLayout

Bir çerçeve penceresinde tüm bölmelerin yerleşimini yeniden hesaplar ve ayarlar.

```
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```

### <a name="parameters"></a>Parametreler

*hdwp*<br/>
'ndaki Ertelenmiş pencere konumu yapısını belirtir. Daha fazla bilgi için bkz. [Windows veri türleri](/windows/win32/WinProg/windows-data-types).

### <a name="remarks"></a>Açıklamalar

##  <a name="addminiframe"></a>CDockingManager:: AddMiniFrame

Mini kareler listesine bir çerçeve ekler.

```
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
'ndaki Çerçeve işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Çerçeve, Mini çerçeveler listesinde değilse ve başarıyla eklendiyse doğru; Aksi takdirde FALSE.

##  <a name="adjustpaneframes"></a>CDockingManager:: Adjustbölmesi çerçeveleri

WM_NCCALCSIZE iletisinin tüm bölmelere ve `CPaneFrameWnd` pencerelere gönderilmesine neden olur.

```
virtual void AdjustPaneFrames();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="adjustrecttoclientarea"></a>CDockingManager:: AdjustRectToClientArea

Bir dikdörtgenin hizalamasını ayarlar.

```
virtual BOOL AdjustRectToClientArea(
    CRect& rectResult,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

*rectResult*<br/>
'ndaki Bir `CRect` nesneye başvuru

*Dwhizalaması*<br/>
'ndaki `CRect` Nesnenin hizalaması

### <a name="return-value"></a>Dönüş Değeri

`CRect` Nesnenin hizalaması ayarlanmışsa doğru; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

*Dwhizalaması* parametresi aşağıdaki değerlerden birine sahip olabilir:

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

##  <a name="alignautohidepane"></a>CDockingManager:: AlignAutoHidePane

Bir yerleştirme bölmesini otomatik olarak yeniden boyutlandırır ve bu sayede, sitelerin Dock 'ın istemci alanının tam genişliğini veya yüksekliğini sitelere yerleştir.

```
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,
    BOOL bIsVisible = TRUE);
```

### <a name="parameters"></a>Parametreler

*pDefaultSlider*<br/>
'ndaki Takma kaydırıcı bölmesi.

*bIsVisible*<br/>
'ndaki Takma bölmesi görünür durumdaysa doğru; Aksi takdirde FALSE.

##  <a name="autohidepane"></a>CDockingManager:: oto Hidepane

Otomatik gizleme araç çubuğu oluşturur.

```
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
'ndaki Çubuk bölmesine yönelik bir işaretçi.

*Pcuroyutohidetoolbar*<br/>
'ndaki Otomatik gizleme araç çubuğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Otomatik gizle araç çubuğu oluşturulmadıysa NULL; Aksi takdirde yeni araç çubuğuna yönelik bir işaretçi.

##  <a name="bringbarstotop"></a>CDockingManager:: BringBarsToTop

Belirtilen hizalamayı en üste getiren sabitlenmiş çubukları getirir.

```
void BringBarsToTop(
    DWORD dwAlignment = 0,
    BOOL bExcludeDockedBars = TRUE);
```

### <a name="parameters"></a>Parametreler

*Dwhizalaması*<br/>
'ndaki Diğer pencerelerin üst kısmına getirilen yerleştirme çubuklarının hizalaması.

*Bexcludedockedçubuklarının*<br/>
'ndaki Yerleşik çubukların üstte olmasını hariç tutmak için TRUE; Aksi halde yanlış.

##  <a name="buildpanesmenu"></a>CDockingManager:: BuildPanesMenu

Bir menüye yerleştirme bölmeleri ve araç çubuklarının adlarını ekler.

```
void BuildPanesMenu(
    CMenu& menu,
    BOOL bToolbarsOnly);
```

### <a name="parameters"></a>Parametreler

*Menü*<br/>
'ndaki Yerleştirme bölmeleri ve araç çubuklarının adlarını eklemek için bir menü.

*bToolbarsOnly*<br/>
'ndaki Menüye yalnızca araç çubuğu adlarını eklemek için TRUE; Aksi takdirde FALSE.

##  <a name="calcexpecteddockedrect"></a>CDockingManager:: CalcExpectedDockedRect

Yerleşik pencerenin beklenen dikdörtgenini hesaplar.

```
void CalcExpectedDockedRect(
    CWnd* pWnd,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
'ndaki Sabitlemek üzere pencereye yönelik bir işaretçi.

*ptMouse*<br/>
'ndaki Fare konumu.

*rectResult*<br/>
dışı Hesaplanan dikdörtgen.

*bDrawTab*<br/>
'ndaki Bir sekme çizmek için TRUE; Aksi halde yanlış.

*ppTargetBar*<br/>
dışı Hedef bölmeye bir işaretçi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir Kullanıcı pencereyi *ptMouse* tarafından belirtilen noktaya sürüklediyseniz ve üzerine yerleştirildiğinde bir pencerenin kaplayacağı dikdörtgeni hesaplar.

##  <a name="create"></a>CDockingManager:: Create

Bir yerleştirme Yöneticisi oluşturur.

```
BOOL Create(CFrameWnd* pParentWnd);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
'ndaki Yerleştirme yöneticisinin üst çerçevesine yönelik bir işaretçi. Bu değer NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE.

##  <a name="determinepaneandstatus"></a>CDockingManager::D Eterminebölmesi Andstatus

Belirli bir noktayı ve yerleştirme durumunu içeren bölmeyi belirler.

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

*yönergelerinin*<br/>
'ndaki Denetlenecek bölmenin konumu.

*Duyarlılık*<br/>
'ndaki İşaretlenen her bölmenin pencere dikdörtgenini artırma değeri. Verilen nokta bu daha fazla bölgede ise, bir bölme arama ölçütlerini karşılar.

*Dwenabledhizalaması*<br/>
'ndaki Yerleştirme bölmesinin hizalaması.

*ppTargetBar*<br/>
dışı Hedef bölmeye bir işaretçi işaretçisi.

*Pbartoıgnore*<br/>
'ndaki Yöntemin yok saydığı bölme.

*pBarToDock*<br/>
'ndaki Yerleştirilmiş pencere.

### <a name="return-value"></a>Dönüş Değeri

Yerleştirme durumu.

### <a name="remarks"></a>Açıklamalar

Takma durumu aşağıdaki değerlerden biri olabilir:

|AFX_CS_STATUS değeri|Açıklama|
|---------------------------|-------------|
|CS_NOTHING|İşaretçi bir dock sitesi üzerinde değil. Bu nedenle, bölmeyi yüzer durumda tutun.|
|CS_DOCK_IMMEDIATELY|İşaretçi, yerleştirme sitesinin hemen modunda (DT_IMMEDIATE Style etkin) bulunur, bu nedenle bölme hemen yerleştirilmelidir.|
|CS_DELAY_DOCK|İşaretçi, başka bir yerleştirme bölmesi olan veya ana çerçevenin bir kenarı olan bir dock sitesi üzerinde bulunur.|
|CS_DELAY_DOCK_TO_TAB|İşaretçi, bölmenin sekmeli pencereye yerleştirilmesine neden olan bir dock sitesi üzerinde bulunur. Bu, fare başka bir yerleştirme bölmesinin bir açıklamalı alt yazısının üzerindeyken veya sekmeli bölmenin sekme alanında olduğunda gerçekleşir.|

##  <a name="disablerestoredockstate"></a>CDockingManager::D isableRestoreDockState

Kayıt defterinden yerleştirme düzeninin yüklenmesine izin vermez veya devre dışı bırakır.

```
void DisableRestoreDockState(BOOL bDisable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bWindows*<br/>
'ndaki Kayıt defterinden yerleştirme düzeninin yüklenmesini devre dışı bırakmak için TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Uygulama durumu yüklenirken yerleştirme bölmeleri ve araç çubuklarının geçerli yerleşimini korumanız gerektiğinde bu yöntemi çağırın.

##  <a name="dockpane"></a>CDockingManager::D ockPane

Bir bölmeyi başka bir bölmeye veya bir çerçeve penceresine göre oluşturma.

```
void DockPane(
    CBasePane* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
'ndaki Bir çubuk bölmesine yerleştirmek için bir işaretçi.

*nDockBarID*<br/>
'ndaki Sabitlemek için çubuğun kimliği.

*lpRect*<br/>
'ndaki Hedef dikdörtgen.

##  <a name="dockpaneleftof"></a>CDockingManager::D ockPaneLeftOf

Başka bir bölmenin solunda bir bölme noktası oluşturma.

```
BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>Parametreler

*pBarToDock*<br/>
'ndaki *PTargetBar*'un soluna yerleştirilen bölmeye yönelik bir işaretçi.

*pTargetBar*<br/>
'ndaki Hedef bölmeye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bölme başarıyla yerleştirilmişse doğru; Aksi takdirde, FALSE.

##  <a name="enableautohidepanes"></a>CDockingManager:: Enableoto Hidebölmeleri

Bölmenin ana çerçeveye yerleştirmeyi sağlar, bir dock bölmesi oluşturur ve denetim çubukları listesine ekler.

```
BOOL EnableAutoHidePanes(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
'ndaki Yerleştirme hizalaması.

### <a name="return-value"></a>Dönüş Değeri

Dock bölmesi başarıyla oluşturulduysa TRUE; Aksi takdirde FALSE.

##  <a name="enabledocking"></a>CDockingManager:: EnableDocking

Bir yerleştirme bölmesi oluşturur ve bölmenin ana çerçeveye yerleştirmeyi sağlar.

```
BOOL EnableDocking(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
'ndaki Yerleştirme hizalaması.

### <a name="return-value"></a>Dönüş Değeri

Dock bölmesi başarıyla oluşturulduysa TRUE; Aksi takdirde FALSE.

##  <a name="enabledocksitemenu"></a>CDockingManager:: EnableDockSiteMenu

Tüm yerleştirme bölmelerindeki açıklamalı alt yazıların açılan menüyü açan ek bir düğme görüntüler.

```
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Site yerleştir menüsünü etkinleştirmek için TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Site Yerleştir menüsünde, bölmenin yerleştirme durumunu değiştirmek için aşağıdaki seçenekler görüntülenir:

- `Floating`-Bir bölmeyi aşağı kayarak

- `Docking`-Bölmenin en son yerleştirildiği konumdaki ana çerçevede bölme noktası oluşturma

- `AutoHide`-Bölmeyi otomatik gizleme moduna geçirir

- `Hide`-Bölmeyi gizler

Varsayılan olarak, bu menü gösterilmez.

##  <a name="enablepanecontextmenu"></a>CDockingManager:: Enablebölmesi ContextMenu

Kitaplığa, Kullanıcı sağ fare düğmesine tıkladığında ve kitaplık WM_CONTEXTMENU iletisini işlerken, uygulama araç çubukları ve yerleştirme bölmeleri listesine sahip özel bir bağlam menüsü görüntülemesini söyler.

```
void EnablePaneContextMenu(
    BOOL bEnable,
    UINT uiCustomizeCmd,
    const CString& strCustomizeText,
    BOOL bToolbarsOnly = FALSE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki TRUE ise, kitaplık otomatik bağlam menüsü desteğini etkinleştirir; FALSE ise, kitaplık otomatik bağlam menüsü desteğini devre dışı bırakır.

*uiCustomizeCmd*<br/>
'ndaki Menüdeki **Özelleştirme** öğesi için bir komut kimliği.

*strCustomizeText*<br/>
'ndaki **Özelleştirme** öğesi metni.

*bToolbarsOnly*<br/>
'ndaki TRUE ise, menü yalnızca uygulama araç çubuklarının bir listesini görüntüler; FALSE ise, kitaplık uygulama yerleştirme bölmelerini bu listeye ekler.

##  <a name="finddocksite"></a>CDockingManager:: FindDockSite

Belirtilen konumdaki ve belirtilen hizalamaya sahip olan çubuk bölmesini alır.

```
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,
    BOOL bOuter);
```

### <a name="parameters"></a>Parametreler

*Dwhizalaması*<br/>
'ndaki Çubuk bölmesinin hizalaması.

*bOuter*<br/>
'ndaki DOĞRU ise, denetim çubukları listesindeki baş konumdaki çubuğu alın. Aksi takdirde, denetim çubukları listesindeki kuyruk konumundaki çubuğu alın.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen hizalamayı içeren yerleştirme bölmesi; Aksi takdirde NULL.

##  <a name="findpanebyid"></a>CDockingManager:: Findbölmesi Byıd

Belirtilen denetim KIMLIĞIYLE bir bölme bulur.

```
virtual CBasePane* FindPaneByID(
    UINT uBarID,
    BOOL bSearchMiniFrames = FALSE);
```

### <a name="parameters"></a>Parametreler

*uBarID*<br/>
'ndaki Bulunacak bölmenin denetim KIMLIĞINI belirtir.

*Bsearchminiframe 'Ler*<br/>
'ndaki Aramaya tüm kayan bölmeleri dahil etmek için TRUE. Yalnızca sabitlenmiş bölmeleri dahil etmek için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen denetim KIMLIĞINE sahip [CBasePane](../../mfc/reference/cbasepane-class.md) nesnesi veya belirtilen bölme bulunamazsa null.

### <a name="remarks"></a>Açıklamalar

##  <a name="finddocksitebypane"></a>CDockingManager:: FindDockSiteByPane

Hedef çubuk bölmesinin kimliği olan çubuk bölmesini döndürür.

```
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```

### <a name="parameters"></a>Parametreler

*pTargetBar*<br/>
'ndaki Hedef çubuk bölmesine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedef çubuk bölmesinin kimliğine sahip olan çubuk bölmesi; Böyle bir çubuk bölmesi yoksa NULL.

##  <a name="fixupvirtualrects"></a>CDockingManager:: FixupVirtualRects

Tüm geçerli araç çubuğu konumlarını sanal dikdörtgenlere kaydeder.

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı bir araç çubuğunu sürüklemeye başladığında, uygulama *sanal dikdörtgenin*orijinal konumunu anımsar. Kullanıcı bir araç çubuğunu dock sitesinde taşırken, araç çubuğu diğer araç çubuklarına kayabilir. Diğer araç çubuklarının özgün konumları ilgili sanal dikdörtgenlerde depolanır.

##  <a name="framefrompoint"></a>CDockingManager:: FrameFromPoint

Verilen noktayı içeren çerçeveyi döndürür.

```
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,
    CPaneFrameWnd* pFrameToExclude,
    BOOL bFloatMultiOnly) const;
```

### <a name="parameters"></a>Parametreler

*yönergelerinin*<br/>
'ndaki Denetlenecek işaretçiyi ekran koordinatları olarak belirtir.

*pFrameToExclude*<br/>
'ndaki Dışlanacak çerçeveye yönelik bir işaretçi.

*bFloatMultiOnly*<br/>
'ndaki Örneği olmayan kareleri hariç tutmak için TRUE `CMultiPaneFrameWnd`. Aksi takdirde FALSE.

### <a name="return-value"></a>Dönüş Değeri

Verilen noktayı içeren çerçeve; Aksi takdirde NULL.

##  <a name="getclientareabounds"></a>CDockingManager:: Getclientareasýnýrlarý

İstemci alanının sınırlarını içeren dikdörtgeni alır.

```
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```

### <a name="parameters"></a>Parametreler

*rcClient*<br/>
dışı İstemci alanının sınırlarını içeren dikdörtgene bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

İstemci alanının sınırlarını içeren dikdörtgen.

##  <a name="getdockingmode"></a>CDockingManager:: GetDockingMode

Geçerli yerleştirme modunu döndürür.

```
static AFX_DOCK_TYPE GetDockingMode();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yerleştirme modunu temsil eden bir Numaralandırıcı değeri. Aşağıdaki değerlerden biri olabilir:

- DT_STANDARD

- DT_IMMEDIATE

- DT_SMART

### <a name="remarks"></a>Açıklamalar

Takma modunu ayarlamak için [CDockingManager:: SetDockingMode](#setdockingmode)komutunu çağırın.

##  <a name="getdocksiteframewnd"></a>CDockingManager:: GetDockSiteFrameWnd

Üst pencere çerçevesine bir işaretçi alır.

```
CFrameWnd* GetDockSiteFrameWnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Üst pencere çerçevesine yönelik bir işaretçi.

##  <a name="getenabledautohidealignment"></a>CDockingManager:: Getenabledadutohidehizalaması

Bölmelerin etkin hizalamasını döndürür.

```
DWORD GetEnabledAutoHideAlignment() const;
```

### <a name="return-value"></a>Dönüş Değeri

CBRS_ALIGN_ bayraklarının bit düzeyinde birleşimi veya otomatik gizleme bölmeleri etkinleştirilmemişse 0. Daha fazla bilgi için bkz. [CFrameWnd:: EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking).

### <a name="remarks"></a>Açıklamalar

Yöntemi otomatik gizleme denetim çubukları için etkinleştirilmiş hizalamayı döndürür. Otomatik gizleme çubuklarını etkinleştirmek için [CFrameWndEx:: Enableotomatik Hidebölmelerini](../../mfc/reference/cframewndex-class.md#enableautohidepanes)çağırın.

##  <a name="getminiframes"></a>CDockingManager:: Getminiframe 'Ler

Miniframe 'ler listesini alır.

```
const CObList& GetMiniFrames() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yerleşik yöneticiye ait olan denetim çubuklarını içeren miniframe 'ler listesi.

##  <a name="getouteredgebounds"></a>CDockingManager:: Getouteredgesınırlara

Çerçevenin dış kenarlarını içeren bir dikdörtgen alır.

```
CRect GetOuterEdgeBounds() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çerçevenin dış kenarlarını içeren bir dikdörtgen.

##  <a name="getpanelist"></a>CDockingManager:: Getbölmesi listesi

Yerleşik yöneticiye ait olan bölmelerin listesini döndürür. Bu, tüm kayan bölmeleri içerir.

```
void GetPaneList(
    CObList& lstBars,
    BOOL bIncludeAutohide = FALSE,
    CRuntimeClass* pRTCFilter = NULL,
    BOOL bIncludeTabs = FALSE);
```

### <a name="parameters"></a>Parametreler

*Lstbar çubukları*<br/>
[in, out] Geçerli yerleşik yöneticinin tüm bölmelerini içerir.

*Bincludeotomatik gizle*<br/>
'ndaki Otomatik gizleme modunda olan bölmeleri dahil etmek için TRUE; Aksi takdirde, FALSE.

*pRTCFilter*<br/>
'ndaki NULL değilse, döndürülen listede yalnızca belirtilen çalışma zamanı sınıfının bölmeleri bulunur.

*Bincludesekmeleri*<br/>
'ndaki Sekmeleri dahil etmek için doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Yerleştirme yöneticisinde sekmeli bölmeler varsa, yöntem [CBaseTabbedPane sınıfı](../../mfc/reference/cbasetabbedpane-class.md) nesnelerine işaretçiler döndürür ve sekmeleri açıkça numaralandırabilirsiniz.

Belirli bir bölme sınıfı elde etmek için *pRTCFilter* kullanın. Örneğin, bu değeri uygun şekilde ayarlayarak yalnızca araç çubuklarını elde edebilirsiniz.

##  <a name="getsmartdockingmanager"></a>CDockingManager:: GetSmartDockingManager

Akıllı yerleştirme Yöneticisi için bir işaretçi alır.

```
CSmartDockingManager* GetSmartDockingManager();
```

### <a name="return-value"></a>Dönüş Değeri

Akıllı yerleştirme Yöneticisi işaretçisi.

##  <a name="getsmartdockingmanagerpermanent"></a>CDockingManager:: Getsmartdockingmanagerkalıcı

Akıllı yerleştirme Yöneticisi için bir işaretçi alır.

```
CSmartDockingManager* GetSmartDockingManagerPermanent() const;
```

### <a name="return-value"></a>Dönüş Değeri

Akıllı yerleştirme Yöneticisi işaretçisi.

##  <a name="getsmartdockingparams"></a>CDockingManager:: GetSmartDockingParams

Yerleşik yöneticinin akıllı yerleştirme parametrelerini döndürür.

```
static CSmartDockingInfo& GetSmartDockingParams();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yerleşik yöneticinin akıllı yerleştirme parametrelerini içeren sınıf. Daha fazla bilgi için bkz. [CSmartDockingInfo sınıfı](../../mfc/reference/csmartdockinginfo-class.md).

### <a name="remarks"></a>Açıklamalar

##  <a name="hideautohidepanes"></a>CDockingManager:: Hideoto Hidebölmeleri

Otomatik gizleme modundaki bir bölmeyi gizler.

```
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,
    BOOL bImmediately = FALSE);
```

### <a name="parameters"></a>Parametreler

*pBarToExclude*<br/>
'ndaki Gizlenerek dışlanacak bir çubuğa yönelik işaretçi.

*banında*<br/>
'ndaki Bölmeyi hemen gizlemek için TRUE; Bölmeyi otomatik gizleme efektiyle gizlemek için FALSE.

##  <a name="insertdocksite"></a>CDockingManager:: ınsertdocksite

Bir yerleştirme bölmesi oluşturur ve denetim çubukları listesine ekler.

```
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,
    DWORD dwAlignToInsertAfter,
    CDockSite** ppDockBar = NULL);
```

### <a name="parameters"></a>Parametreler

*bilgisine*<br/>
'ndaki Dock bölmesi hakkında hizalama bilgilerini içeren bir yapı.

*dwAlignToInsertAfter*<br/>
'ndaki Dock bölmesinin hizalaması.

*ppDockBar*<br/>
dışı Dock bölmesine yönelik bir işaretçi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Dock bölmesi başarıyla oluşturulduysa TRUE; Aksi takdirde FALSE.

##  <a name="insertpane"></a>CDockingManager:: InsertPane

Denetim çubukları listesine bir denetim bölmesi ekler.

```
BOOL InsertPane(
    CBasePane* pControlBar,
    CBasePane* pTarget,
    BOOL bAfter = TRUE);
```

### <a name="parameters"></a>Parametreler

*pControlBar*<br/>
'ndaki Denetim bölmesine yönelik bir işaretçi.

*pTarget*<br/>
'ndaki Hedef bölmeye yönelik bir işaretçi.

*bAfter*<br/>
'ndaki Hedef bölmenin konumundan sonra bölmeyi eklemek için TRUE; Aksi takdirde FALSE.

### <a name="return-value"></a>Dönüş Değeri

Denetim bölmesi denetim çubukları listesine başarıyla eklendiyse TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Denetim bölmesi zaten denetim çubukları listesinde ise veya hedef bölme denetim çubukları listesinde yoksa, bu yöntem false döndürür.

##  <a name="isdocksitemenu"></a>CDockingManager:: IsDockSiteMenu

Tüm bölmelerin resim yazılarında bir açılır menünün görüntülenip görüntülenmeyeceğini belirtir.

```
static BOOL IsDockSiteMenu();
```

### <a name="return-value"></a>Dönüş Değeri

Tüm yerleştirme bölmelerindeki resim yazılarında bir Yerleştir sitesi menüsü görüntüleniyorsa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

[CDockingManager:: EnableDockSiteMenu](#enabledocksitemenu)' i çağırarak site menüsünü Yerleştir ' i etkinleştirebilirsiniz.

##  <a name="isinadjustlayout"></a>CDockingManager:: ısınadjustlayout

Tüm bölmelerin düzenlerin ayarlanacağını belirler.

```
BOOL IsInAdjustLayout() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tüm bölmelerin düzenleri ayarlanıyorsa doğru; Aksi takdirde FALSE.

##  <a name="isolecontainermode"></a>CDockingManager:: ısolecontainermode

Yerleşik yöneticinin OLE kapsayıcı modunda olup olmadığını belirtir.

```
BOOL IsOLEContainerMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yerleştirme Yöneticisi OLE kapsayıcı modundaysa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

OLE kapsayıcı modunda, tüm yerleştirme bölmeleri ve uygulama araç çubukları gizlidir. [CDockingManager:: m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode) ' i true olarak ayarlarsanız bölmeler da bu modda gizlenir.

##  <a name="ispointneardocksite"></a>CDockingManager:: Ispointyaklaştığında Docksite

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
dışı Noktanın yakınında olduğunu belirtir. Olası değerler şunlardır CBRS_ALIGN_LEFT, CBRS_ALIGN_RIGHT, CBRS_ALIGN_TOP ve CBRS_ALIGN_BOTTOM.

*Bukenar*<br/>
dışı Nokta, dock sitesinin dış kenarlığına yaklaşmışsa TRUE; Aksi takdirde FALSE.

### <a name="return-value"></a>Dönüş Değeri

Nokta dock sitesinin yakınında ise doğru; Aksi halde yanlış.

##  <a name="isprintpreviewvalid"></a>CDockingManager:: ısprintönizlemesi geçerli

Baskı Önizleme modunun ayarlanmış olup olmadığını belirler.

```
BOOL IsPrintPreviewValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Baskı önizleme modu ayarlandıysa doğru; Aksi takdirde FALSE.

##  <a name="loadstate"></a>CDockingManager:: LoadState

Kayıt defterindeki yerleştirme yöneticisinin durumunu yükler.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
'ndaki Profil adı.

*Uııd*<br/>
'ndaki Yerleştirme yöneticisinin kimliği.

### <a name="return-value"></a>Dönüş Değeri

Yerleştirme Yöneticisi durumu başarıyla yüklenmişse, doğru; Aksi halde yanlış.

##  <a name="lockupdate"></a>CDockingManager:: LockUpdate

Verilen pencereyi kilitler.

```
void LockUpdate(BOOL bLock);
```

### <a name="parameters"></a>Parametreler

*Engelleyin*<br/>
'ndaki Pencere kilitliyse doğru; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bir pencere kilitlendiğinde, taşınamaz ve yeniden çizilmez.

##  <a name="m_bhidedockingbarsincontainermode"></a>CDockingManager:: m_bHideDockingBarsInContainerMode

Yerleştirme yöneticisinin, OLE kapsayıcı modundaki bölmeleri gizleyemeyeceğini belirtir.

```
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;
```

### <a name="remarks"></a>Açıklamalar

Uygulama OLE kapsayıcı modundayken görünen ana çerçeveye yerleştirilmiş tüm bölmeleri tutmak istiyorsanız bu değeri FALSE olarak ayarlayın. Bu değer varsayılan olarak TRUE 'dur.

##  <a name="m_dockmodeglobal"></a>CDockingManager:: m_dockModeGlobal

Genel yerleştirme modunu belirtir.

```
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, her takma bölmesi bu yerleştirme modunu kullanır. Bu alanın ayarlandığı değerler hakkında daha fazla bilgi için bkz. [CBasePane:: GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).

##  <a name="m_ndocksensitivity"></a>CDockingManager:: m_nDockSensitivity

Yerleştirme hassasiyetini belirtir.

```
AFX_IMPORT_DATA static int m_nDockSensitivity;
```

### <a name="remarks"></a>Açıklamalar

Yerleştirme duyarlılığı, çerçeve durumunu sabitlenmiş olarak değiştirmeden önce bir kayan bölmenin bir yerleştirme bölmesine, yerleştirme sitesine veya başka bir bölmeye Nasıl yaklaşabileceğini tanımlar.

##  <a name="m_ntimeoutbeforedockingbardock"></a>CDockingManager:: m_nTimeOutBeforeDockingBarDock

Takma bölmesinin anında yerleştirme moduna yerleştirilme süresini milisaniye olarak belirtir.

```
static UINT m_nTimeOutBeforeDockingBarDock;
```

### <a name="remarks"></a>Açıklamalar

Bir bölme yerleştirilmadan önce, çerçeve belirtilen süreyi bekler. Bu, Kullanıcı hala sürüklerken bölmenin bir konuma yanlışlıkla yerleştirilmelerini önler.

##  <a name="m_ntimeoutbeforetoolbardock"></a>CDockingManager:: m_nTimeOutBeforeToolBarDock

Bir araç çubuğunun ana çerçeve penceresine yerleştirilme süresini milisaniye olarak belirtir.

```
static UINT m_nTimeOutBeforeToolBarDock;
```

### <a name="remarks"></a>Açıklamalar

Bir araç çubuğu yerleştirilmadan önce, çerçeve belirtilen süreyi bekler. Bu, Kullanıcı hala sürüklerken araç çubuğunun bir konuma yanlışlıkla yerleştirilmelerini önler.

##  <a name="onactivateframe"></a>CDockingManager:: OnActivateFrame

Çerçeve penceresi etkin hale getirildiğinde veya devre dışı bırakıldığında Framework tarafından çağırılır.

```
virtual void OnActivateFrame(BOOL bActivate);
```

### <a name="parameters"></a>Parametreler

*Bacetkinleştir*<br/>
'ndaki TRUE ise çerçeve penceresi etkin hale getirilir; YANLıŞSA, çerçeve penceresi devre dışı bırakılır.

##  <a name="onclosepopupmenu"></a>CDockingManager:: OnClosePopupMenu

Etkin bir açılır menü bir WM_DESTROY iletisini işlediğinde Framework tarafından çağırılır.

```
void OnClosePopupMenu();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, geçerli ana pencereyi kapatmak üzere olduğunda bir WM_DESTROY iletisi gönderir. `CMFCPopupMenu` Bir`CMFCPopupMenu` nesne bir wm_destroy iletisini işlediğinde çerçeve penceresine ait olan nesnelerdeki bildirimleri işlemek için bu yöntemi geçersiz kılın.

##  <a name="onmoveminiframe"></a>CDockingManager:: OnMoveMiniFrame

Bir mini çerçeve penceresini taşımak için Framework tarafından çağırılır.

```
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```

### <a name="parameters"></a>Parametreler

*pFrame*<br/>
'ndaki Mini çerçeve penceresine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa doğru; Aksi halde yanlış.

##  <a name="onpanecontextmenu"></a>CDockingManager:: Onbölmesi ContextMenu

Bir bölme listesi olan bir menü oluşturduğunda Framework tarafından çağırılır.

```
void OnPaneContextMenu(CPoint point);
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
'ndaki Menünün konumunu belirtir.

##  <a name="panefrompoint"></a>CDockingManager::P aneFromPoint

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

*seçeneğinin*<br/>
'ndaki Denetlenecek işaretçiyi ekran koordinatları olarak belirtir.

*Duyarlılık*<br/>
'ndaki İşaretlenen her bölmenin pencere dikdörtgenini Şişir değeri. Söz konusu nokta bu anormal bölgede ise, bir bölme arama ölçütlerini karşılar.

*bExactBar*<br/>
'ndaki *Nduyarlılık* parametresini YOKSAYMAK için true; Aksi takdirde, FALSE.

*pRTCBarType*<br/>
'ndaki NULL değilse, yöntemi yalnızca belirtilen türdeki bölmeleri arar.

*bCheckVisibility*<br/>
'ndaki Yalnızca görünür bölmeleri denetlemek için TRUE; Aksi takdirde, FALSE.

*Dwhizalaması*<br/>
dışı Belirtilen noktada bir bölme bulunursa, bu parametre belirtilen noktaya en yakın bölmenin tarafını içerir. Daha fazla bilgi için, açıklamalar bölümüne bakın.

*Pbartoıgnore*<br/>
'ndaki NULL değilse, yöntemi bu parametre tarafından belirtilen bölmeleri yoksayar.

### <a name="return-value"></a>Dönüş Değeri

[CBasePane](../../mfc/reference/cbasepane-class.md)-verilen noktayı içeren türetilmiş nesne veya hiçbir bölme bulunmazsa null.

### <a name="remarks"></a>Açıklamalar

İşlev döndürüldüğünde ve bir bölme bulunduğunda *dwhizalaması* belirtilen noktanın hizalamasını içerir. Örneğin, nokta bölmenin en üstüne yakın ise *Dwhizalaması* CBRS_ALIGN_TOP olarak ayarlanır.

##  <a name="processpanecontextmenucommand"></a>CDockingManager::P rocessPaneContextMenuCommand

Belirtilen komutun onay kutusunu seçmek veya temizlemek ve gösterilen bölmenin yerleşimini yeniden hesaplamak için Framework tarafından çağırılır.

```
BOOL ProcessPaneContextMenuCommand(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
'ndaki Menüdeki bir denetim çubuğunun kimliği.

*nCode*<br/>
'ndaki Komut bildirim kodu.

*pExtra*<br/>
'ndaki Void için bir işaretçi, *nCode* CN_UPDATE_COMMAND_UI ise bir işaretçiye `CCmdUI` işaret edilir.

*pHandlerInfo*<br/>
'ndaki Bilgi yapısına yönelik bir işaretçi. Bu parametre kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

*PExtra* null değilse ve *nCode* eşitse ya da belirtilen *NID*'ye sahip bir denetim çubuğu varsa true.

##  <a name="recalclayout"></a>CDockingManager:: RecalcLayout

Denetimler listesinde bulunan denetimlerin iç yerleşimini yeniden hesaplar.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Parametreler

*bNotify*<br/>
'ndaki Bu parametre kullanılmaz.

##  <a name="releaseemptypanecontainers"></a>CDockingManager:: ReleaseEmptyPaneContainers

Boş bölme kapsayıcılarını serbest bırakır.

```
void ReleaseEmptyPaneContainers();
```

##  <a name="removehiddenmditabbedbar"></a>CDockingManager:: Removehiddenmdıtabbedbar

Belirtilen gizli çubuk bölmesini kaldırır.

```
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
'ndaki Kaldırılacak çubuk bölmesine yönelik bir işaretçi.

##  <a name="removeminiframe"></a>CDockingManager:: RemoveMiniFrame

Belirtilen çerçeveyi mini çerçeveler listesinden kaldırır.

```
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
'ndaki Kaldırılacak çerçeveye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen çerçeve kaldırılırsa doğru; Aksi takdirde FALSE.

##  <a name="removepanefromdockmanager"></a>CDockingManager:: RemovePaneFromDockManager

Bir bölmenin kaydını siler ve yerleştirme yöneticisindeki listeden kaldırır.

```
void RemovePaneFromDockManager(
    CBasePane* pWnd,
    BOOL bDestroy,
    BOOL bAdjustLayout,
    BOOL bAutoHide = FALSE,
    CBasePane* pBarReplacement = NULL);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
'ndaki Kaldırılacak bölmeye yönelik bir işaretçi.

*bDestroy*<br/>
'ndaki TRUE ise kaldırılan bölme yok edilir.

*Roztlayout*<br/>
'ndaki DOĞRU ise, yerleştirme yerleşimini hemen ayarlayın.

*bAutoHide*<br/>
'ndaki TRUE ise bölme otomatik gizleme çubukları listesinden kaldırılır. YANLıŞSA, bölme normal bölmeler listesinden kaldırılır.

*Pbardeğiştirme*<br/>
'ndaki Kaldırılan bölmenin yerini alan bölme işaretçisi.

##  <a name="replacepane"></a>CDockingManager:: ReplacePane

Bir bölmeyi diğeri ile değiştirir.

```
BOOL ReplacePane(
    CDockablePane* pOriginalBar,
    CDockablePane* pNewBar);
```

### <a name="parameters"></a>Parametreler

*pOriginalBar*<br/>
'ndaki Özgün bölmeye yönelik bir işaretçi.

*pNewBar*<br/>
'ndaki Orijinal bölmenin yerini alan bölmeye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bölme başarıyla değiştirildiyse doğru; Aksi takdirde FALSE.

##  <a name="resortminiframesforzorder"></a>CDockingManager:: Resortminifoymesforzorder

Mini çerçeveler listesindeki çerçeveleri yeniden ölçeklendirin.

```
void ResortMiniFramesForZOrder();
```

##  <a name="savestate"></a>CDockingManager:: Savemlak

Yerleştirme yöneticisinin durumunu kayıt defterine kaydeder.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
'ndaki Kayıt defteri anahtarının yolu.

*Uııd*<br/>
'ndaki Yerleştirme Yöneticisi KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Durum başarıyla kaydedilmişse doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Yerleştirme yöneticisinin durumunu kayıt defterine kaydetmek, denetim çubuklarının durumlarının, otomatik gizleme çubuklarının durumlarının ve yerleştirme yöneticisinde bulunan mini çerçevelerin durumlarının kaydedilmesini içerir.

##  <a name="sendmessagetominiframes"></a>CDockingManager:: Sendmessagetominiframe

Belirtilen iletiyi tüm mini çerçevelere gönderir.

```
BOOL SendMessageToMiniFrames(
    UINT uMessage,
    WPARAM wParam = 0,
    LPARAM lParam = 0);
```

### <a name="parameters"></a>Parametreler

*uMessage*<br/>
'ndaki Gönderilecek ileti.

*wParam*<br/>
'ndaki Ek ileti bağımlı bilgileri.

*lParam*<br/>
'ndaki Ek ileti bağımlı bilgileri.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE.

##  <a name="serialize"></a>CDockingManager:: serileştirme

Yerleştirme yöneticisini bir arşive yazar.

```
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
'ndaki Bir arşiv nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Yerleştirme yöneticisini bir arşive yazmak, yerleştirme denetim çubuklarının ve kaydırıcılarının sayısını belirlemeyi ve denetim çubukları, Mini kareler, otomatik gizleme çubukları ve MDI sekmeli çubuklarını arşive yazmak için gerekir.

##  <a name="setautohidezorder"></a>CDockingManager:: SetAutohideZOrder

Denetim çubuklarının boyutunu, genişliğini ve yüksekliğini, belirtilen bölmeyi ayarlar.

```
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```

### <a name="parameters"></a>Parametreler

*pAHDockingBar*<br/>
'ndaki Bir yerleştirilebilir bölmesi işaretçisi.

##  <a name="setdockingmode"></a>CDockingManager:: SetDockingMode

Yerleştirme modunu ayarlar.

```
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```

### <a name="parameters"></a>Parametreler

*dockMode*<br/>
Yeni yerleştirme modunu belirtir. Daha fazla bilgi için, açıklamalar bölümüne bakın.

*Tema*<br/>
Akıllı yerleştirme işaretçileri için kullanılacak temayı belirtir. Bu, aşağıdaki numaralandırılmış değerlerden biri olabilir: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.

### <a name="remarks"></a>Açıklamalar

Yerleştirme modunu ayarlamak için bu statik yöntemi çağırın.

*Dockmode* aşağıdaki değerlerden biri olabilir:

- Visual Studio .NET 2003 ' de uygulanan DT_STANDARD-Standart yerleştirme modu. Bölmeler, sürükleme bağlamı olmadan sürüklenir.

- DT_IMMEDIATE-Microsoft Visio 'da uygulanan şekilde anında yerleştirme modu. Bölmeler bir sürükleme bağlamı ile sürüklenir, ancak hiçbir işaretleyici gösterilmez.

- DT_SMART-Visual Studio 2005 ' de uygulanan akıllı yerleştirme modu. Bölmeler bir sürükleme bağlamı ile sürüklenir ve bölmenin nerede yerleştirildiğini gösteren akıllı işaretleyiciler görüntülenir.

##  <a name="setdockstate"></a>CDockingManager:: SetDockState

Denetim çubuklarının, Mini karelerin ve otomatik gizleme çubuklarının yerleştirme durumunu ayarlar.

```
virtual void SetDockState();
```

##  <a name="setprintpreviewmode"></a>CDockingManager:: Setprintönizleme modu

Baskı önizlemede görüntülenen çubukların Baskı Önizleme modunu ayarlar.

```
void SetPrintPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>Parametreler

*bPreview*<br/>
'ndaki Baskı önizleme modu ayarlandıysa doğru; Aksi takdirde FALSE.

*pState*<br/>
'ndaki Önizleme durumuna yönelik bir işaretçi. Bu parametre kullanılmaz.

##  <a name="setsmartdockingparams"></a>CDockingManager:: SetSmartDockingParams

Akıllı yerleştirme davranışını tanımlayan parametreleri ayarlar.

```
static void SetSmartDockingParams(CSmartDockingInfo& params);
```

### <a name="parameters"></a>Parametreler

*params*<br/>
[in, out] Akıllı yerleştirme parametrelerini tanımlar.

### <a name="remarks"></a>Açıklamalar

Akıllı yerleştirme işaretlerinin görünümünü, rengini veya şeklini özelleştirmek istiyorsanız bu yöntemi çağırın.

Akıllı yerleştirme işaretçileri için varsayılan görünümü kullanmak için, bir [CSmartDockingInfo sınıfının](../../mfc/reference/csmartdockinginfo-class.md) başlatılmamış örneğini *params*'e geçirin.

##  <a name="showdelayshowminiframes"></a>CDockingManager:: Showdelayshowminiframe

Mini çerçevelerin pencerelerini gösterir veya gizler.

```
void ShowDelayShowMiniFrames(BOOL bshow);
```

### <a name="parameters"></a>Parametreler

*bShow*<br/>
'ndaki Gösterilen çerçevenin penceresini etkin hale getirmek için TRUE; Çerçevenin penceresini gizlemek için FALSE.

##  <a name="showpanes"></a>CDockingManager:: Showbölmeler

Denetim ve otomatik gizleme çubuklarının bölmelerini gösterir veya gizler.

```
virtual BOOL ShowPanes(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bShow*<br/>
'ndaki Bölmeleri göstermek için TRUE; Bölmeleri gizlemek için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Her zaman FALSE.

##  <a name="startsdocking"></a>CDockingManager:: StartSDocking

Akıllı yerleşik yöneticinin hizalamasına göre belirtilen pencerenin akıllı olarak yuvalanmasına başlar.

```
void StartSDocking(CWnd* pDockingWnd);
```

### <a name="parameters"></a>Parametreler

*pDockingWnd*<br/>
'ndaki Sabitlemek üzere bir pencere işaretçisi.

##  <a name="stopsdocking"></a>CDockingManager:: StopSDocking

Akıllı yerleştirmeyi durdur.

```
void StopSDocking();
```

##  <a name="getsmartdockingtheme"></a>CDockingManager:: GetSmartDockingTheme

Akıllı yerleştirme işaretleyicilerini göstermek için kullanılan bir temayı döndüren statik bir yöntem.

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
[CPaneFrameWnd Sınıfı](../../mfc/reference/cpaneframewnd-class.md)
