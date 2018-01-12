---
title: "CPaneContainerManager sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaneContainerManager
- AFXPANECONTAINERMANAGER/CPaneContainerManager
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneContainerManager
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneContainerManagerToDockablePane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPanesToList
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneToList
- AFXPANECONTAINERMANAGER/CPaneContainerManager::AddPaneToRecentPaneContainer
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CalcRects
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CanBeAttached
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CheckAndRemoveNonValidPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::CheckForMiniFrameAndCaption
- AFXPANECONTAINERMANAGER/CPaneContainerManager::Create
- AFXPANECONTAINERMANAGER/CPaneContainerManager::DoesAllowDynInsertBefore
- AFXPANECONTAINERMANAGER/CPaneContainerManager::DoesContainFloatingPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::EnableGrippers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::FindPaneContainer
- AFXPANECONTAINERMANAGER/CPaneContainerManager::FindTabbedPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetAvailableSpace
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetDefaultPaneDivider
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetDockSiteFrameWnd
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetFirstPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetFirstVisiblePane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetMinMaxOffset
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetMinSize
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetNodeCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetPaneContainerRTC
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetPaneCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetTotalRefCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetVisiblePaneCount
- AFXPANECONTAINERMANAGER/CPaneContainerManager::GetWindowRect
- AFXPANECONTAINERMANAGER/CPaneContainerManager::HideAll
- AFXPANECONTAINERMANAGER/CPaneContainerManager::InsertPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::IsAutoHideMode
- AFXPANECONTAINERMANAGER/CPaneContainerManager::IsEmpty
- AFXPANECONTAINERMANAGER/CPaneContainerManager::IsRootPaneContainerVisible
- AFXPANECONTAINERMANAGER/CPaneContainerManager::NotifyPaneDivider
- AFXPANECONTAINERMANAGER/CPaneContainerManager::OnPaneDividerMove
- AFXPANECONTAINERMANAGER/CPaneContainerManager::OnShowPane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::PaneFromPoint
- AFXPANECONTAINERMANAGER/CPaneContainerManager::ReleaseEmptyPaneContainers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemoveAllPanesAndPaneDividers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemoveNonValidPanes
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemovePaneDivider
- AFXPANECONTAINERMANAGER/CPaneContainerManager::RemovePaneFromPaneContainer
- AFXPANECONTAINERMANAGER/CPaneContainerManager::ReplacePane
- AFXPANECONTAINERMANAGER/CPaneContainerManager::ResizePaneContainers
- AFXPANECONTAINERMANAGER/CPaneContainerManager::Serialize
- AFXPANECONTAINERMANAGER/CPaneContainerManager::SetDefaultPaneDividerForPanes
- AFXPANECONTAINERMANAGER/CPaneContainerManager::SetPaneContainerRTC
- AFXPANECONTAINERMANAGER/CPaneContainerManager::SetResizeMode
- AFXPANECONTAINERMANAGER/CPaneContainerManager::StoreRecentDockSiteInfo
dev_langs: C++
helpviewer_keywords:
- CPaneContainerManager [MFC], AddPane
- CPaneContainerManager [MFC], AddPaneContainerManager
- CPaneContainerManager [MFC], AddPaneContainerManagerToDockablePane
- CPaneContainerManager [MFC], AddPanesToList
- CPaneContainerManager [MFC], AddPaneToList
- CPaneContainerManager [MFC], AddPaneToRecentPaneContainer
- CPaneContainerManager [MFC], CalcRects
- CPaneContainerManager [MFC], CanBeAttached
- CPaneContainerManager [MFC], CheckAndRemoveNonValidPane
- CPaneContainerManager [MFC], CheckForMiniFrameAndCaption
- CPaneContainerManager [MFC], Create
- CPaneContainerManager [MFC], DoesAllowDynInsertBefore
- CPaneContainerManager [MFC], DoesContainFloatingPane
- CPaneContainerManager [MFC], EnableGrippers
- CPaneContainerManager [MFC], FindPaneContainer
- CPaneContainerManager [MFC], FindTabbedPane
- CPaneContainerManager [MFC], GetAvailableSpace
- CPaneContainerManager [MFC], GetDefaultPaneDivider
- CPaneContainerManager [MFC], GetDockSiteFrameWnd
- CPaneContainerManager [MFC], GetFirstPane
- CPaneContainerManager [MFC], GetFirstVisiblePane
- CPaneContainerManager [MFC], GetMinMaxOffset
- CPaneContainerManager [MFC], GetMinSize
- CPaneContainerManager [MFC], GetNodeCount
- CPaneContainerManager [MFC], GetPaneContainerRTC
- CPaneContainerManager [MFC], GetPaneCount
- CPaneContainerManager [MFC], GetTotalRefCount
- CPaneContainerManager [MFC], GetVisiblePaneCount
- CPaneContainerManager [MFC], GetWindowRect
- CPaneContainerManager [MFC], HideAll
- CPaneContainerManager [MFC], InsertPane
- CPaneContainerManager [MFC], IsAutoHideMode
- CPaneContainerManager [MFC], IsEmpty
- CPaneContainerManager [MFC], IsRootPaneContainerVisible
- CPaneContainerManager [MFC], NotifyPaneDivider
- CPaneContainerManager [MFC], OnPaneDividerMove
- CPaneContainerManager [MFC], OnShowPane
- CPaneContainerManager [MFC], PaneFromPoint
- CPaneContainerManager [MFC], ReleaseEmptyPaneContainers
- CPaneContainerManager [MFC], RemoveAllPanesAndPaneDividers
- CPaneContainerManager [MFC], RemoveNonValidPanes
- CPaneContainerManager [MFC], RemovePaneDivider
- CPaneContainerManager [MFC], RemovePaneFromPaneContainer
- CPaneContainerManager [MFC], ReplacePane
- CPaneContainerManager [MFC], ResizePaneContainers
- CPaneContainerManager [MFC], Serialize
- CPaneContainerManager [MFC], SetDefaultPaneDividerForPanes
- CPaneContainerManager [MFC], SetPaneContainerRTC
- CPaneContainerManager [MFC], SetResizeMode
- CPaneContainerManager [MFC], StoreRecentDockSiteInfo
ms.assetid: 3d974c15-a62f-4648-bb5b-cc31ab7950af
caps.latest.revision: "29"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9185aee3b8a6750260549d5d180fa7e30e1fc321
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cpanecontainermanager-class"></a>CPaneContainerManager sınıfı
`CPaneContainerManager` Sınıfı, depolama ve geçerli yerleştirme düzeni görüntüsünü yönetir.  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPaneContainerManager : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPaneContainerManager::AddPane](#addpane)||  
|[CPaneContainerManager::AddPaneContainerManager](#addpanecontainermanager)||  
|[CPaneContainerManager::AddPaneContainerManagerToDockablePane](#addpanecontainermanagertodockablepane)||  
|[CPaneContainerManager::AddPanesToList](#addpanestolist)||  
|[CPaneContainerManager::AddPaneToList](#addpanetolist)||  
|[CPaneContainerManager::AddPaneToRecentPaneContainer](#addpanetorecentpanecontainer)||  
|[CPaneContainerManager::CalcRects](#calcrects)||  
|[CPaneContainerManager::CanBeAttached](#canbeattached)||  
|[CPaneContainerManager::CheckAndRemoveNonValidPane](#checkandremovenonvalidpane)||  
|[CPaneContainerManager::CheckForMiniFrameAndCaption](#checkforminiframeandcaption)||  
|[CPaneContainerManager::Create](#create)||  
|[CPaneContainerManager::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)||  
|[CPaneContainerManager::DoesContainFloatingPane](#doescontainfloatingpane)||  
|[CPaneContainerManager::EnableGrippers](#enablegrippers)||  
|[CPaneContainerManager::FindPaneContainer](#findpanecontainer)||  
|[CPaneContainerManager::FindTabbedPane](#findtabbedpane)||  
|[CPaneContainerManager::GetAvailableSpace](#getavailablespace)||  
|[CPaneContainerManager::GetDefaultPaneDivider](#getdefaultpanedivider)||  
|[CPaneContainerManager::GetDockSiteFrameWnd](#getdocksiteframewnd)||  
|[CPaneContainerManager::GetFirstPane](#getfirstpane)||  
|[CPaneContainerManager::GetFirstVisiblePane](#getfirstvisiblepane)||  
|[CPaneContainerManager::GetMinMaxOffset](#getminmaxoffset)||  
|[CPaneContainerManager::GetMinSize](#getminsize)||  
|[CPaneContainerManager::GetNodeCount](#getnodecount)||  
|[CPaneContainerManager::GetPaneContainerRTC](#getpanecontainerrtc)||  
|[CPaneContainerManager::GetPaneCount](#getpanecount)||  
|[CPaneContainerManager::GetTotalRefCount](#gettotalrefcount)||  
|[CPaneContainerManager::GetVisiblePaneCount](#getvisiblepanecount)||  
|[CPaneContainerManager::GetWindowRect](#getwindowrect)||  
|[CPaneContainerManager::HideAll](#hideall)||  
|[CPaneContainerManager::InsertPane](#insertpane)||  
|[CPaneContainerManager::IsAutoHideMode](#isautohidemode)||  
|[CPaneContainerManager::IsEmpty](#isempty)||  
|[CPaneContainerManager::IsRootPaneContainerVisible](#isrootpanecontainervisible)||  
|[CPaneContainerManager::NotifyPaneDivider](#notifypanedivider)||  
|[CPaneContainerManager::OnPaneDividerMove](#onpanedividermove)||  
|[CPaneContainerManager::OnShowPane](#onshowpane)||  
|[CPaneContainerManager::PaneFromPoint](#panefrompoint)||  
|[CPaneContainerManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)||  
|[CPaneContainerManager::RemoveAllPanesAndPaneDividers](#removeallpanesandpanedividers)||  
|[CPaneContainerManager::RemoveNonValidPanes](#removenonvalidpanes)||  
|[CPaneContainerManager::RemovePaneDivider](#removepanedivider)||  
|[CPaneContainerManager::RemovePaneFromPaneContainer](#removepanefrompanecontainer)||  
|[CPaneContainerManager::ReplacePane](#replacepane)||  
|[CPaneContainerManager::ResizePaneContainers](#resizepanecontainers)||  
|[CPaneContainerManager::Serialize](#serialize)|Okur veya bir arşiv değiştirilmesine veya bu nesneyi yazar. (Geçersiz kılmaları [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CPaneContainerManager::SetDefaultPaneDividerForPanes](#setdefaultpanedividerforpanes)||  
|[CPaneContainerManager::SetPaneContainerRTC](#setpanecontainerrtc)||  
|[CPaneContainerManager::SetResizeMode](#setresizemode)||  
|[CPaneContainerManager::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
  
### <a name="remarks"></a>Açıklamalar  
 Framework örneklerini otomatik olarak oluşturur `CPaneContainerManager` nesneleri ve ya da katıştırır içine [CPaneDivider sınıfı](../../mfc/reference/cpanedivider-class.md) nesneleri veya [CMultiPaneFrameWnd sınıfı](../../mfc/reference/cmultipaneframewnd-class.md) nesneleri.  
  
 `CPaneContainerManager` Sınıfı depolar oluşturulur bir ikili ağacı kök gösteren bir işaretçi [CPaneContainer](../../mfc/reference/cpanecontainer-class.md) nesneleri.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl başvuru alındığını anlatan bir `CPaneContainerManager` nesnesi. Bu kod parçacığını parçası olan [bölmesinin boyutunu Ayarla örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize#5](../../mfc/reference/codesnippet/cpp/cpanecontainermanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CPaneContainerManager](../../mfc/reference/cpanecontainermanager-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpanecontainermanager.h  
  
##  <a name="addpane"></a>CPaneContainerManager::AddPane  

  
```  
virtual void AddPane(CDockablePane* pControlBarToAdd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pControlBarToAdd`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addpanecontainermanager"></a>CPaneContainerManager::AddPaneContainerManager  

  
```  
virtual BOOL AddPaneContainerManager(
    CPaneContainerManager& srcManager,  
    BOOL bOuterEdge);

 
virtual BOOL AddPaneContainerManager(
    CDockablePane* pTargetControlBar,  
    DWORD dwAlignment,  
    CPaneContainerManager& srcManager,  
    BOOL bCopy);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`srcManager`  
 [in]`bOuterEdge`  
 [in]`pTargetControlBar`  
 [in]`dwAlignment`  
 [in]`bCopy`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addpanecontainermanagertodockablepane"></a>CPaneContainerManager::AddPaneContainerManagerToDockablePane  

  
```  
virtual BOOL AddPaneContainerManagerToDockablePane(
    CDockablePane* pTargetControlBar,  
    CPaneContainerManager& srcManager);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pTargetControlBar`  
 [in]`srcManager`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addpanestolist"></a>CPaneContainerManager::AddPanesToList  

  
```  
void AddPanesToList(
    CObList* plstControlBars,  
    CObList* plstSliders);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`plstControlBars`  
 [in]`plstSliders`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addpanetolist"></a>CPaneContainerManager::AddPaneToList  

  
```  
void AddPaneToList(CDockablePane* pControlBarToAdd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pControlBarToAdd`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addpanetorecentpanecontainer"></a>CPaneContainerManager::AddPaneToRecentPaneContainer  

  
```  
virtual CDockablePane* AddPaneToRecentPaneContainer(
    CDockablePane* pBarToAdd,  
    CPaneContainer* pRecentContainer);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBarToAdd`  
 [in]`pRecentContainer`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="calcrects"></a>CPaneContainerManager::CalcRects  

  
```  
void CalcRects(
    CRect& rectOriginal,  
    CRect& rectInserted,  
    CRect& rectSlider,  
    DWORD& dwSliderStyle,  
    DWORD dwAlignment,  
    CSize sizeMinOriginal,  
    CSize sizeMinInserted);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rectOriginal`  
 [in]`rectInserted`  
 [in]`rectSlider`  
 [in]`dwSliderStyle`  
 [in]`dwAlignment`  
 [in]`sizeMinOriginal`  
 [in]`sizeMinInserted`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="canbeattached"></a>CPaneContainerManager::CanBeAttached  

  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="checkandremovenonvalidpane"></a>CPaneContainerManager::CheckAndRemoveNonValidPane  

  
```  
BOOL CheckAndRemoveNonValidPane(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWnd`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="checkforminiframeandcaption"></a>CPaneContainerManager::CheckForMiniFrameAndCaption  

  
```  
virtual BOOL CheckForMiniFrameAndCaption(
    CPoint point,  
    CDockablePane** ppTargetControlBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`point`  
 [in]`ppTargetControlBar`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="create"></a>CPaneContainerManager::Create  

  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    CPaneDivider* pDefaultSlider,  
    CRuntimeClass* pContainerRTC = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pParentWnd`  
 [in]`pDefaultSlider`  
 [in]`pContainerRTC`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="doesallowdyninsertbefore"></a>CPaneContainerManager::DoesAllowDynInsertBefore  

  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="doescontainfloatingpane"></a>CPaneContainerManager::DoesContainFloatingPane  

  
```  
virtual BOOL DoesContainFloatingPane();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enablegrippers"></a>CPaneContainerManager::EnableGrippers  

  
```  
virtual void EnableGrippers(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="findpanecontainer"></a>CPaneContainerManager::FindPaneContainer  

  
```  
virtual CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,  
    BOOL& bLeftBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 [in]`bLeftBar`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="findtabbedpane"></a>CPaneContainerManager::FindTabbedPane  

  
```  
CDockablePane* FindTabbedPane(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nID`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getavailablespace"></a>CPaneContainerManager::GetAvailableSpace  

  
```  
virtual void GetAvailableSpace(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rect`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getdefaultpanedivider"></a>CPaneContainerManager::GetDefaultPaneDivider  

  
```  
CPaneDivider* GetDefaultPaneDivider() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getdocksiteframewnd"></a>CPaneContainerManager::GetDockSiteFrameWnd  

  
```  
virtual CWnd* GetDockSiteFrameWnd();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getfirstpane"></a>CPaneContainerManager::GetFirstPane  

  
```  
virtual CBasePane* GetFirstPane() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getfirstvisiblepane"></a>CPaneContainerManager::GetFirstVisiblePane  

  
```  
virtual CWnd* GetFirstVisiblePane() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getminmaxoffset"></a>CPaneContainerManager::GetMinMaxOffset  

  
```  
virtual void GetMinMaxOffset(
    CPaneDivider* pSlider,  
    int& nMinOffset,  
    int& nMaxOffset,  
    int& nStep);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pSlider`  
 [in]`nMinOffset`  
 [in]`nMaxOffset`  
 [in]`nStep`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getminsize"></a>CPaneContainerManager::GetMinSize  

  
```  
virtual void GetMinSize(CSize& size);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`size`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getnodecount"></a>CPaneContainerManager::GetNodeCount  

  
```  
int GetNodeCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanecontainerrtc"></a>CPaneContainerManager::GetPaneContainerRTC  

  
```  
CRuntimeClass* GetPaneContainerRTC() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanecount"></a>CPaneContainerManager::GetPaneCount  

  
```  
int GetPaneCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gettotalrefcount"></a>CPaneContainerManager::GetTotalRefCount  

  
```  
int GetTotalRefCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getvisiblepanecount"></a>CPaneContainerManager::GetVisiblePaneCount  

  
```  
virtual int GetVisiblePaneCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getwindowrect"></a>CPaneContainerManager::GetWindowRect  

  
```  
virtual void GetWindowRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rect`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hideall"></a>CPaneContainerManager::HideAll  

  
```  
virtual void HideAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="insertpane"></a>CPaneContainerManager::InsertPane  

  
```  
virtual BOOL InsertPane(
    CDockablePane* pControlBarToInsert,  
    CDockablePane* pTargetControlBar,  
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL,  
    AFX_DOCK_METHOD dockMethod = DM_UNKNOWN);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pControlBarToInsert`  
 [in]`pTargetControlBar`  
 [in]`dwAlignment`  
 [in]`lpRect`  
 [in]`dockMethod`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isautohidemode"></a>CPaneContainerManager::IsAutoHideMode  

  
```  
BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isempty"></a>CPaneContainerManager::IsEmpty  

  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isrootpanecontainervisible"></a>CPaneContainerManager::IsRootPaneContainerVisible  

  
```  
virtual BOOL IsRootPaneContainerVisible() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="notifypanedivider"></a>CPaneContainerManager::NotifyPaneDivider  

  
```  
void NotifyPaneDivider();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onpanedividermove"></a>CPaneContainerManager::OnPaneDividerMove  

  
```  
virtual int OnPaneDividerMove(
    CPaneDivider* pSlider,  
    UINT uFlags,  
    int nOffset,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pSlider`  
 [in]`uFlags`  
 [in]`nOffset`  
 [in]`hdwp`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onshowpane"></a>CPaneContainerManager::OnShowPane  

  
```  
virtual BOOL OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 [in]`bShow`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="panefrompoint"></a>CPaneContainerManager::PaneFromPoint  

  
```  
virtual CDockablePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    BOOL bExactBar,  
    BOOL& bIsTabArea,  
    BOOL& bCaption);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`point`  
 [in]`nSensitivity`  
 [in]`bExactBar`  
 [in]`bIsTabArea`  
 [in]`bCaption`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="releaseemptypanecontainers"></a>CPaneContainerManager::ReleaseEmptyPaneContainers  

  
```  
void ReleaseEmptyPaneContainers();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removeallpanesandpanedividers"></a>CPaneContainerManager::RemoveAllPanesAndPaneDividers  

  
```  
void RemoveAllPanesAndPaneDividers();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removenonvalidpanes"></a>CPaneContainerManager::RemoveNonValidPanes  

  
```  
void RemoveNonValidPanes();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removepanedivider"></a>CPaneContainerManager::RemovePaneDivider  

  
```  
virtual void RemovePaneDivider(CPaneDivider* pSlider);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pSlider`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removepanefrompanecontainer"></a>CPaneContainerManager::RemovePaneFromPaneContainer  

  
```  
virtual BOOL RemovePaneFromPaneContainer(CDockablePane* pControlBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pControlBar`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="replacepane"></a>CPaneContainerManager::ReplacePane  

  
```  
virtual BOOL ReplacePane(
    CDockablePane* pBarOld,  
    CDockablePane* pBarNew);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBarOld`  
 [in]`pBarNew`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="resizepanecontainers"></a>CPaneContainerManager::ResizePaneContainers  

  
```  
virtual void ResizePaneContainers(
    UINT nSide,  
    BOOL bExpand,  
    int nOffset,  
    HDWP& hdwp);

 
virtual void ResizePaneContainers(
    CRect rect,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nSide`  
 [in]`bExpand`  
 [in]`nOffset`  
 [in]`hdwp`  
 [in]`rect`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="serialize"></a>CPaneContainerManager::Serialize  

  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`ar`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setdefaultpanedividerforpanes"></a>CPaneContainerManager::SetDefaultPaneDividerForPanes  

  
```  
void SetDefaultPaneDividerForPanes(CPaneDivider* pSlider);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pSlider`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpanecontainerrtc"></a>CPaneContainerManager::SetPaneContainerRTC  

  
```  
void SetPaneContainerRTC(CRuntimeClass* pContainerRTC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pContainerRTC`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setresizemode"></a>CPaneContainerManager::SetResizeMode  

  
```  
virtual void SetResizeMode(BOOL bResize);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bResize`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="storerecentdocksiteinfo"></a>CPaneContainerManager::StoreRecentDockSiteInfo  

  
```  
virtual void StoreRecentDockSiteInfo(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [CPaneContainer sınıfı](../../mfc/reference/cpanecontainer-class.md)   
 [CPaneDivider Sınıfı](../../mfc/reference/cpanedivider-class.md)
