---
title: "CPaneContainer sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaneContainer
- AFXPANECONTAINER/CPaneContainer
- AFXPANECONTAINER/CPaneContainer::CPaneContainer
- AFXPANECONTAINER/CPaneContainer::AddPane
- AFXPANECONTAINER/CPaneContainer::AddRef
- AFXPANECONTAINER/CPaneContainer::AddSubPaneContainer
- AFXPANECONTAINER/CPaneContainer::CalcAvailablePaneSpace
- AFXPANECONTAINER/CPaneContainer::CalcAvailableSpace
- AFXPANECONTAINER/CPaneContainer::CalculateRecentSize
- AFXPANECONTAINER/CPaneContainer::CheckPaneDividerVisibility
- AFXPANECONTAINER/CPaneContainer::Copy
- AFXPANECONTAINER/CPaneContainer::DeletePane
- AFXPANECONTAINER/CPaneContainer::FindSubPaneContainer
- AFXPANECONTAINER/CPaneContainer::FindTabbedPane
- AFXPANECONTAINER/CPaneContainer::GetAssociatedSiblingPaneIDs
- AFXPANECONTAINER/CPaneContainer::GetLeftPane
- AFXPANECONTAINER/CPaneContainer::GetLeftPaneContainer
- AFXPANECONTAINER/CPaneContainer::GetMinSize
- AFXPANECONTAINER/CPaneContainer::GetMinSizeLeft
- AFXPANECONTAINER/CPaneContainer::GetMinSizeRight
- AFXPANECONTAINER/CPaneContainer::GetNodeCount
- AFXPANECONTAINER/CPaneContainer::GetPaneDivider
- AFXPANECONTAINER/CPaneContainer::GetParentPaneContainer
- AFXPANECONTAINER/CPaneContainer::GetRecentPaneDividerRect
- AFXPANECONTAINER/CPaneContainer::GetRecentPaneDividerStyle
- AFXPANECONTAINER/CPaneContainer::GetRecentPercent
- AFXPANECONTAINER/CPaneContainer::GetRefCount
- AFXPANECONTAINER/CPaneContainer::GetResizeStep
- AFXPANECONTAINER/CPaneContainer::GetRightPane
- AFXPANECONTAINER/CPaneContainer::GetRightPaneContainer
- AFXPANECONTAINER/CPaneContainer::GetTotalReferenceCount
- AFXPANECONTAINER/CPaneContainer::GetWindowRect
- AFXPANECONTAINER/CPaneContainer::IsDisposed
- AFXPANECONTAINER/CPaneContainer::IsEmpty
- AFXPANECONTAINER/CPaneContainer::IsLeftPane
- AFXPANECONTAINER/CPaneContainer::IsLeftPaneContainer
- AFXPANECONTAINER/CPaneContainer::IsLeftPartEmpty
- AFXPANECONTAINER/CPaneContainer::IsRightPartEmpty
- AFXPANECONTAINER/CPaneContainer::IsVisible
- AFXPANECONTAINER/CPaneContainer::Move
- AFXPANECONTAINER/CPaneContainer::OnDeleteHidePane
- AFXPANECONTAINER/CPaneContainer::OnMoveInternalPaneDivider
- AFXPANECONTAINER/CPaneContainer::OnShowPane
- AFXPANECONTAINER/CPaneContainer::Release
- AFXPANECONTAINER/CPaneContainer::ReleaseEmptyPaneContainer
- AFXPANECONTAINER/CPaneContainer::RemoveNonValidPanes
- AFXPANECONTAINER/CPaneContainer::RemovePane
- AFXPANECONTAINER/CPaneContainer::Resize
- AFXPANECONTAINER/CPaneContainer::ResizePane
- AFXPANECONTAINER/CPaneContainer::ResizePartOfPaneContainer
- AFXPANECONTAINER/CPaneContainer::Serialize
- AFXPANECONTAINER/CPaneContainer::SetPane
- AFXPANECONTAINER/CPaneContainer::SetPaneContainer
- AFXPANECONTAINER/CPaneContainer::SetPaneDivider
- AFXPANECONTAINER/CPaneContainer::SetParentPaneContainer
- AFXPANECONTAINER/CPaneContainer::SetRecentPercent
- AFXPANECONTAINER/CPaneContainer::SetUpByID
- AFXPANECONTAINER/CPaneContainer::StoreRecentDockSiteInfo
- AFXPANECONTAINER/CPaneContainer::StretchPaneContainer
dev_langs: C++
helpviewer_keywords:
- CPaneContainer [MFC], CPaneContainer
- CPaneContainer [MFC], AddPane
- CPaneContainer [MFC], AddRef
- CPaneContainer [MFC], AddSubPaneContainer
- CPaneContainer [MFC], CalcAvailablePaneSpace
- CPaneContainer [MFC], CalcAvailableSpace
- CPaneContainer [MFC], CalculateRecentSize
- CPaneContainer [MFC], CheckPaneDividerVisibility
- CPaneContainer [MFC], Copy
- CPaneContainer [MFC], DeletePane
- CPaneContainer [MFC], FindSubPaneContainer
- CPaneContainer [MFC], FindTabbedPane
- CPaneContainer [MFC], GetAssociatedSiblingPaneIDs
- CPaneContainer [MFC], GetLeftPane
- CPaneContainer [MFC], GetLeftPaneContainer
- CPaneContainer [MFC], GetMinSize
- CPaneContainer [MFC], GetMinSizeLeft
- CPaneContainer [MFC], GetMinSizeRight
- CPaneContainer [MFC], GetNodeCount
- CPaneContainer [MFC], GetPaneDivider
- CPaneContainer [MFC], GetParentPaneContainer
- CPaneContainer [MFC], GetRecentPaneDividerRect
- CPaneContainer [MFC], GetRecentPaneDividerStyle
- CPaneContainer [MFC], GetRecentPercent
- CPaneContainer [MFC], GetRefCount
- CPaneContainer [MFC], GetResizeStep
- CPaneContainer [MFC], GetRightPane
- CPaneContainer [MFC], GetRightPaneContainer
- CPaneContainer [MFC], GetTotalReferenceCount
- CPaneContainer [MFC], GetWindowRect
- CPaneContainer [MFC], IsDisposed
- CPaneContainer [MFC], IsEmpty
- CPaneContainer [MFC], IsLeftPane
- CPaneContainer [MFC], IsLeftPaneContainer
- CPaneContainer [MFC], IsLeftPartEmpty
- CPaneContainer [MFC], IsRightPartEmpty
- CPaneContainer [MFC], IsVisible
- CPaneContainer [MFC], Move
- CPaneContainer [MFC], OnDeleteHidePane
- CPaneContainer [MFC], OnMoveInternalPaneDivider
- CPaneContainer [MFC], OnShowPane
- CPaneContainer [MFC], Release
- CPaneContainer [MFC], ReleaseEmptyPaneContainer
- CPaneContainer [MFC], RemoveNonValidPanes
- CPaneContainer [MFC], RemovePane
- CPaneContainer [MFC], Resize
- CPaneContainer [MFC], ResizePane
- CPaneContainer [MFC], ResizePartOfPaneContainer
- CPaneContainer [MFC], Serialize
- CPaneContainer [MFC], SetPane
- CPaneContainer [MFC], SetPaneContainer
- CPaneContainer [MFC], SetPaneDivider
- CPaneContainer [MFC], SetParentPaneContainer
- CPaneContainer [MFC], SetRecentPercent
- CPaneContainer [MFC], SetUpByID
- CPaneContainer [MFC], StoreRecentDockSiteInfo
- CPaneContainer [MFC], StretchPaneContainer
ms.assetid: beb79e08-f611-4d66-ba04-053baa79bf86
caps.latest.revision: "32"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27193084f2232c17885d3a6ee54ea901764f3d93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cpanecontainer-class"></a>CPaneContainer sınıfı
`CPaneContainer` Sınıftır MFC tarafından uygulanan takma modeline temel bir bileşenidir. Bu sınıfın bir nesnesi işaretçileri iki yerleşik bölmeler veya iki örneğini depolar `CPaneContainer.` bölmeleri (veya kapsayıcıları) ayıran ayırıcı gösteren bir işaretçi de depolar. Kapsayıcılar içinde iç içe geçmiş kapsayıcılar tarafından framework karmaşık takma düzenleri temsil eden bir ikili ağacı oluşturabilirsiniz. İkili ağacının kök dizininde depolanmış bir [CPaneContainerManager](../../mfc/reference/cpanecontainermanager-class.md) nesnesi.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
 
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPaneContainer : public CObject    
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPaneContainer::CPaneContainer](#cpanecontainer)|Varsayılan Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPaneContainer::AddPane](#addpane)||  
|[CPaneContainer::AddRef](#addref)||  
|[CPaneContainer::AddSubPaneContainer](#addsubpanecontainer)||  
|[CPaneContainer::CalcAvailablePaneSpace](#calcavailablepanespace)||  
|[CPaneContainer::CalcAvailableSpace](#calcavailablespace)||  
|[CPaneContainer::CalculateRecentSize](#calculaterecentsize)||  
|[CPaneContainer::CheckPaneDividerVisibility](#checkpanedividervisibility)||  
|[CPaneContainer::Copy](#copy)||  
|[CPaneContainer::DeletePane](#deletepane)||  
|[CPaneContainer::FindSubPaneContainer](#findsubpanecontainer)||  
|[CPaneContainer::FindTabbedPane](#findtabbedpane)||  
|[CPaneContainer::GetAssociatedSiblingPaneIDs](#getassociatedsiblingpaneids)||  
|[CPaneContainer::GetLeftPane](#getleftpane)||  
|[CPaneContainer::GetLeftPaneContainer](#getleftpanecontainer)||  
|[CPaneContainer::GetMinSize](#getminsize)||  
|[CPaneContainer::GetMinSizeLeft](#getminsizeleft)||  
|[CPaneContainer::GetMinSizeRight](#getminsizeright)||  
|[CPaneContainer::GetNodeCount](#getnodecount)||  
|[CPaneContainer::GetPaneDivider](#getpanedivider)||  
|[CPaneContainer::GetParentPaneContainer](#getparentpanecontainer)||  
|[CPaneContainer::GetRecentPaneDividerRect](#getrecentpanedividerrect)||  
|[CPaneContainer::GetRecentPaneDividerStyle](#getrecentpanedividerstyle)||  
|[CPaneContainer::GetRecentPercent](#getrecentpercent)||  
|[CPaneContainer::GetRefCount](#getrefcount)||  
|[CPaneContainer::GetResizeStep](#getresizestep)||  
|[CPaneContainer::GetRightPane](#getrightpane)||  
|[CPaneContainer::GetRightPaneContainer](#getrightpanecontainer)||  
|[CPaneContainer::GetTotalReferenceCount](#gettotalreferencecount)||  
|[CPaneContainer::GetWindowRect](#getwindowrect)||  
|[CPaneContainer::IsDisposed](#isdisposed)||  
|[CPaneContainer::IsEmpty](#isempty)||  
|[CPaneContainer::IsLeftPane](#isleftpane)||  
|[CPaneContainer::IsLeftPaneContainer](#isleftpanecontainer)||  
|[CPaneContainer::IsLeftPartEmpty](#isleftpartempty)||  
|[CPaneContainer::IsRightPartEmpty](#isrightpartempty)||  
|[CPaneContainer::IsVisible](#isvisible)||  
|[CPaneContainer::Move](#move)||  
|[CPaneContainer::OnDeleteHidePane](#ondeletehidepane)||  
|[CPaneContainer::OnMoveInternalPaneDivider](#onmoveinternalpanedivider)||  
|[CPaneContainer::OnShowPane](#onshowpane)||  
|[CPaneContainer::Release](#release)||  
|[CPaneContainer::ReleaseEmptyPaneContainer](#releaseemptypanecontainer)||  
|[CPaneContainer::RemoveNonValidPanes](#removenonvalidpanes)||  
|[CPaneContainer::RemovePane](#removepane)||  
|[CPaneContainer::Resize](#resize)||  
|[CPaneContainer::ResizePane](#resizepane)||  
|[CPaneContainer::ResizePartOfPaneContainer](#resizepartofpanecontainer)||  
|[CPaneContainer::Serialize](#serialize)|Okur veya bir arşiv değiştirilmesine veya bu nesneyi yazar. (Geçersiz kılmaları [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CPaneContainer::SetPane](#setpane)||  
|[CPaneContainer::SetPaneContainer](#setpanecontainer)||  
|[CPaneContainer::SetPaneDivider](#setpanedivider)||  
|[CPaneContainer::SetParentPaneContainer](#setparentpanecontainer)||  
|[CPaneContainer::SetRecentPercent](#setrecentpercent)||  
|[CPaneContainer::SetUpByID](#setupbyid)||  
|[CPaneContainer::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
|[CPaneContainer::StretchPaneContainer](#stretchpanecontainer)||  
  
### <a name="remarks"></a>Açıklamalar  
 `CPaneContainer`nesneleri çerçevesi tarafından otomatik olarak oluşturulur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir örneğini oluşturmak gösterilmiştir `CPaneContainer` sınıfı. Bu kod parçacığını parçası olan [bölmesinin boyutunu Ayarla örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanecontainer-class_1.h)]  
[!code-cpp[NVC_MFC_SetPaneSize#1](../../mfc/reference/codesnippet/cpp/cpanecontainer-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CPaneContainer](../../mfc/reference/cpanecontainer-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpanecontainer.h  
  
##  <a name="addpane"></a>CPaneContainer::AddPane  

  
```  
CDockablePane* AddPane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addref"></a>CPaneContainer::AddRef  

  
```  
void AddRef();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addsubpanecontainer"></a>CPaneContainer::AddSubPaneContainer  

  
```  
BOOL AddSubPaneContainer(
    CPaneContainer* pContainer,  
    BOOL bRightNodeNew);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pContainer`  
 [in]`bRightNodeNew`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="calcavailablepanespace"></a>CPaneContainer::CalcAvailablePaneSpace  

  
```  
virtual int CalcAvailablePaneSpace(
    int nRequiredOffset,  
    CPane* pBar,  
    CPaneContainer* pContainer,  
    BOOL bLeftBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nRequiredOffset`  
 [in]`pBar`  
 [in]`pContainer`  
 [in]`bLeftBar`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="calcavailablespace"></a>CPaneContainer::CalcAvailableSpace  

  
```  
virtual CSize CalcAvailableSpace(
    CSize sizeStretch,  
    BOOL bLeftBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`sizeStretch`  
 [in]`bLeftBar`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="calculaterecentsize"></a>CPaneContainer::CalculateRecentSize  

  
```  
void CalculateRecentSize();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="checkpanedividervisibility"></a>CPaneContainer::CheckPaneDividerVisibility  

  
```  
void CheckPaneDividerVisibility();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="copy"></a>CPaneContainer::Copy  

  
```  
virtual CPaneContainer* Copy(CPaneContainer* pParentContainer);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pParentContainer`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="cpanecontainer"></a>CPaneContainer::CPaneContainer  

  
```  
CPaneContainer(
    CPaneContainerManager* pManager = NULL,  
    CDockablePane* pLeftBar = NULL,  
    CDockablePane* pRightBar = NULL,  
    CPaneDivider* pSlider = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pManager`  
 [in]`pLeftBar`  
 [in]`pRightBar`  
 [in]`pSlider`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="deletepane"></a>CPaneContainer::DeletePane  

  
```  
virtual void DeletePane(
    CDockablePane* pBar,  
    BC_FIND_CRITERIA barType);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 [in]`barType`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="findsubpanecontainer"></a>CPaneContainer::FindSubPaneContainer  

  
```  
CPaneContainer* FindSubPaneContainer(
    const CObject* pObject,  
    BC_FIND_CRITERIA findCriteria);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pObject`  
 [in]`findCriteria`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="findtabbedpane"></a>CPaneContainer::FindTabbedPane  

  
```  
CDockablePane* FindTabbedPane(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nID`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getassociatedsiblingpaneids"></a>CPaneContainer::GetAssociatedSiblingPaneIDs  

  
```  
CList<UINT, UINT>* GetAssociatedSiblingPaneIDs(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getleftpane"></a>CPaneContainer::GetLeftPane  

  
```  
const CDockablePane* GetLeftPane() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getleftpanecontainer"></a>CPaneContainer::GetLeftPaneContainer  

  
```  
const CPaneContainer* GetLeftPaneContainer() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getminsize"></a>CPaneContainer::GetMinSize  

  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`size`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getminsizeleft"></a>CPaneContainer::GetMinSizeLeft  

  
```  
virtual void GetMinSizeLeft(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`size`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getminsizeright"></a>CPaneContainer::GetMinSizeRight  

  
```  
virtual void GetMinSizeRight(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`size`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getnodecount"></a>CPaneContainer::GetNodeCount  

  
```  
int GetNodeCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanedivider"></a>CPaneContainer::GetPaneDivider  

  
```  
const CPaneDivider* GetPaneDivider() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getparentpanecontainer"></a>CPaneContainer::GetParentPaneContainer  

  
```  
CPaneContainer* GetParentPaneContainer() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrecentpanedividerrect"></a>CPaneContainer::GetRecentPaneDividerRect  

  
```  
CRect GetRecentPaneDividerRect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrecentpanedividerstyle"></a>CPaneContainer::GetRecentPaneDividerStyle  

  
```  
DWORD GetRecentPaneDividerStyle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrecentpercent"></a>CPaneContainer::GetRecentPercent  

  
```  
int GetRecentPercent();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrefcount"></a>CPaneContainer::GetRefCount  

  
```  
LONG GetRefCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getresizestep"></a>CPaneContainer::GetResizeStep  

  
```  
virtual int GetResizeStep() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrightpane"></a>CPaneContainer::GetRightPane  

  
```  
const CDockablePane* GetRightPane() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrightpanecontainer"></a>CPaneContainer::GetRightPaneContainer  

  
```  
const CPaneContainer* GetRightPaneContainer() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gettotalreferencecount"></a>CPaneContainer::GetTotalReferenceCount  

  
```  
int GetTotalReferenceCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getwindowrect"></a>CPaneContainer::GetWindowRect  

  
```  
virtual void GetWindowRect(
    CRect& rect,  
    BOOL bIgnoreVisibility = FALSE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rect`  
 [in]`bIgnoreVisibility`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isdisposed"></a>CPaneContainer::IsDisposed  

  
```  
BOOL IsDisposed() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isempty"></a>CPaneContainer::IsEmpty  

  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isleftpane"></a>CPaneContainer::IsLeftPane  

  
```  
BOOL IsLeftPane(CDockablePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isleftpanecontainer"></a>CPaneContainer::IsLeftPaneContainer  

  
```  
BOOL IsLeftPaneContainer() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isleftpartempty"></a>CPaneContainer::IsLeftPartEmpty  

  
```  
BOOL IsLeftPartEmpty(BOOL bCheckVisibility = FALSE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bCheckVisibility`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isrightpartempty"></a>CPaneContainer::IsRightPartEmpty  

  
```  
BOOL IsRightPartEmpty(BOOL bCheckVisibility = FALSE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bCheckVisibility`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isvisible"></a>CPaneContainer::IsVisible  

  
```  
BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="move"></a>CPaneContainer::Move  

  
```  
virtual void Move(CPoint ptNewLeftTop);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`ptNewLeftTop`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondeletehidepane"></a>CPaneContainer::OnDeleteHidePane  

  
```  
void OnDeleteHidePane(
    CDockablePane* pBar,  
    BOOL bHide);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 [in]`bHide`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onmoveinternalpanedivider"></a>CPaneContainer::OnMoveInternalPaneDivider  

  
```  
virtual int OnMoveInternalPaneDivider(
    int nOffset,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nOffset`  
 [in]`hdwp`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onshowpane"></a>CPaneContainer::OnShowPane  

  
```  
virtual void OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 [in]`bShow`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="release"></a>CPaneContainer::Release  

  
```  
DWORD Release();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="releaseemptypanecontainer"></a>CPaneContainer::ReleaseEmptyPaneContainer  

  
```  
void ReleaseEmptyPaneContainer();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removenonvalidpanes"></a>CPaneContainer::RemoveNonValidPanes  

  
```  
void RemoveNonValidPanes();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removepane"></a>CPaneContainer::RemovePane  

  
```  
virtual void RemovePane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="resize"></a>CPaneContainer::Resize  

  
```  
virtual void Resize(
    CRect rect,  
    HDWP& hdwp,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rect`  
 [in]`hdwp`  
 [in]`bRedraw`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="resizepane"></a>CPaneContainer::ResizePane  

  
```  
virtual void ResizePane(
    int nOffset,  
    CPane* pBar,  
    CPaneContainer* pContainer,  
    BOOL bHorz,  
    BOOL bLeftBar,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nOffset`  
 [in]`pBar`  
 [in]`pContainer`  
 [in]`bHorz`  
 [in]`bLeftBar`  
 [in]`hdwp`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="resizepartofpanecontainer"></a>CPaneContainer::ResizePartOfPaneContainer  

  
```  
virtual void ResizePartOfPaneContainer(
    int nOffset,  
    BOOL bLeftPart,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nOffset`  
 [in]`bLeftPart`  
 [in]`hdwp`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="serialize"></a>CPaneContainer::Serialize  

  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`ar`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpane"></a>CPaneContainer::SetPane  

  
```  
void SetPane(
    CDockablePane* pBar,  
    BOOL bLeft);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 [in]`bLeft`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpanecontainer"></a>CPaneContainer::SetPaneContainer  

  
```  
void SetPaneContainer(
    CPaneContainer* pContainer,  
    BOOL bLeft);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pContainer`  
 [in]`bLeft`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpanedivider"></a>CPaneContainer::SetPaneDivider  

  
```  
void SetPaneDivider(CPaneDivider* pSlider);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pSlider`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setparentpanecontainer"></a>CPaneContainer::SetParentPaneContainer  

  
```  
void SetParentPaneContainer(CPaneContainer* p);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`p`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setrecentpercent"></a>CPaneContainer::SetRecentPercent  

  
```  
void SetRecentPercent(int nRecentPercent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nRecentPercent`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setupbyid"></a>CPaneContainer::SetUpByID  

  
```  
BOOL SetUpByID(
    UINT nID,  
    CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nID`  
 [in]`pBar`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="storerecentdocksiteinfo"></a>CPaneContainer::StoreRecentDockSiteInfo  

  
```  
virtual void StoreRecentDockSiteInfo(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="stretchpanecontainer"></a>CPaneContainer::StretchPaneContainer  

  
```  
virtual int StretchPaneContainer(
    int nOffset,  
    BOOL bStretchHorz,  
    BOOL bLeftBar,  
    BOOL bMoveSlider,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nOffset`  
 [in]`bStretchHorz`  
 [in]`bLeftBar`  
 [in]`bMoveSlider`  
 [in]`hdwp`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [CPaneContainerManager Sınıfı](../../mfc/reference/cpanecontainermanager-class.md)
