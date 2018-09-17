---
title: CDockingPanesRow sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDockingPanesRow
- AFXDOCKINGPANESROW/CDockingPanesRow
- AFXDOCKINGPANESROW/CDockingPanesRow::AddPane
- AFXDOCKINGPANESROW/CDockingPanesRow::AddPaneFromRow
- AFXDOCKINGPANESROW/CDockingPanesRow::ArrangePanes
- AFXDOCKINGPANESROW/CDockingPanesRow::CalcFixedLayout
- AFXDOCKINGPANESROW/CDockingPanesRow::Create
- AFXDOCKINGPANESROW/CDockingPanesRow::ExpandStretchedPanes
- AFXDOCKINGPANESROW/CDockingPanesRow::ExpandStretchedPanesRect
- AFXDOCKINGPANESROW/CDockingPanesRow::FixupVirtualRects
- AFXDOCKINGPANESROW/CDockingPanesRow::GetAvailableLength
- AFXDOCKINGPANESROW/CDockingPanesRow::GetAvailableSpace
- AFXDOCKINGPANESROW/CDockingPanesRow::GetClientRect
- AFXDOCKINGPANESROW/CDockingPanesRow::GetDockSite
- AFXDOCKINGPANESROW/CDockingPanesRow::GetExtraSpace
- AFXDOCKINGPANESROW/CDockingPanesRow::GetGroupFromPane
- AFXDOCKINGPANESROW/CDockingPanesRow::GetID
- AFXDOCKINGPANESROW/CDockingPanesRow::GetMaxPaneSize
- AFXDOCKINGPANESROW/CDockingPanesRow::GetPaneCount
- AFXDOCKINGPANESROW/CDockingPanesRow::GetPaneList
- AFXDOCKINGPANESROW/CDockingPanesRow::GetRowAlignment
- AFXDOCKINGPANESROW/CDockingPanesRow::GetRowHeight
- AFXDOCKINGPANESROW/CDockingPanesRow::GetRowOffset
- AFXDOCKINGPANESROW/CDockingPanesRow::GetVisibleCount
- AFXDOCKINGPANESROW/CDockingPanesRow::GetWindowRect
- AFXDOCKINGPANESROW/CDockingPanesRow::HasPane
- AFXDOCKINGPANESROW/CDockingPanesRow::IsEmpty
- AFXDOCKINGPANESROW/CDockingPanesRow::IsExclusiveRow
- AFXDOCKINGPANESROW/CDockingPanesRow::IsHorizontal
- AFXDOCKINGPANESROW/CDockingPanesRow::IsVisible
- AFXDOCKINGPANESROW/CDockingPanesRow::Move
- AFXDOCKINGPANESROW/CDockingPanesRow::MovePane
- AFXDOCKINGPANESROW/CDockingPanesRow::OnResizePane
- AFXDOCKINGPANESROW/CDockingPanesRow::RedrawAll
- AFXDOCKINGPANESROW/CDockingPanesRow::RemovePane
- AFXDOCKINGPANESROW/CDockingPanesRow::ReplacePane
- AFXDOCKINGPANESROW/CDockingPanesRow::RepositionPanes
- AFXDOCKINGPANESROW/CDockingPanesRow::Resize
- AFXDOCKINGPANESROW/CDockingPanesRow::ResizeByPaneDivider
- AFXDOCKINGPANESROW/CDockingPanesRow::ScreenToClient
- AFXDOCKINGPANESROW/CDockingPanesRow::SetExtra
- AFXDOCKINGPANESROW/CDockingPanesRow::ShowDockSiteRow
- AFXDOCKINGPANESROW/CDockingPanesRow::ShowPane
- AFXDOCKINGPANESROW/CDockingPanesRow::UpdateVisibleState
dev_langs:
- C++
helpviewer_keywords:
- CDockingPanesRow [MFC], AddPane
- CDockingPanesRow [MFC], AddPaneFromRow
- CDockingPanesRow [MFC], ArrangePanes
- CDockingPanesRow [MFC], CalcFixedLayout
- CDockingPanesRow [MFC], Create
- CDockingPanesRow [MFC], ExpandStretchedPanes
- CDockingPanesRow [MFC], ExpandStretchedPanesRect
- CDockingPanesRow [MFC], FixupVirtualRects
- CDockingPanesRow [MFC], GetAvailableLength
- CDockingPanesRow [MFC], GetAvailableSpace
- CDockingPanesRow [MFC], GetClientRect
- CDockingPanesRow [MFC], GetDockSite
- CDockingPanesRow [MFC], GetExtraSpace
- CDockingPanesRow [MFC], GetGroupFromPane
- CDockingPanesRow [MFC], GetID
- CDockingPanesRow [MFC], GetMaxPaneSize
- CDockingPanesRow [MFC], GetPaneCount
- CDockingPanesRow [MFC], GetPaneList
- CDockingPanesRow [MFC], GetRowAlignment
- CDockingPanesRow [MFC], GetRowHeight
- CDockingPanesRow [MFC], GetRowOffset
- CDockingPanesRow [MFC], GetVisibleCount
- CDockingPanesRow [MFC], GetWindowRect
- CDockingPanesRow [MFC], HasPane
- CDockingPanesRow [MFC], IsEmpty
- CDockingPanesRow [MFC], IsExclusiveRow
- CDockingPanesRow [MFC], IsHorizontal
- CDockingPanesRow [MFC], IsVisible
- CDockingPanesRow [MFC], Move
- CDockingPanesRow [MFC], MovePane
- CDockingPanesRow [MFC], OnResizePane
- CDockingPanesRow [MFC], RedrawAll
- CDockingPanesRow [MFC], RemovePane
- CDockingPanesRow [MFC], ReplacePane
- CDockingPanesRow [MFC], RepositionPanes
- CDockingPanesRow [MFC], Resize
- CDockingPanesRow [MFC], ResizeByPaneDivider
- CDockingPanesRow [MFC], ScreenToClient
- CDockingPanesRow [MFC], SetExtra
- CDockingPanesRow [MFC], ShowDockSiteRow
- CDockingPanesRow [MFC], ShowPane
- CDockingPanesRow [MFC], UpdateVisibleState
ms.assetid: e7a17832-0ebb-4bce-b799-cec9b60f76fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d98940ffbd1c6ff021712ee50721908d7760abee
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712133"
---
# <a name="cdockingpanesrow-class"></a>CDockingPanesRow sınıfı
Aynı yatay veya dikey satırda dock sitesiyle (sütun) bulunan bölmeleri listesini yönetir.  

 Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDockingPanesRow : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CDockingPanesRow::CDockingPanesRow`|Varsayılan Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDockingPanesRow::AddPane](#addpane)||  
|[CDockingPanesRow::AddPaneFromRow](#addpanefromrow)||  
|[CDockingPanesRow::ArrangePanes](#arrangepanes)|Bir satır aralığı parametreleri ve belirtilen kenar boşluğu göre bölmelerinde düzenler.|  
|[CDockingPanesRow::CalcFixedLayout](#calcfixedlayout)||  
|[CDockingPanesRow::Create](#create)||  
|[CDockingPanesRow::ExpandStretchedPanes](#expandstretchedpanes)||  
|[CDockingPanesRow::ExpandStretchedPanesRect](#expandstretchedpanesrect)||  
|[CDockingPanesRow::FixupVirtualRects](#fixupvirtualrects)||  
|[CDockingPanesRow::GetAvailableLength](#getavailablelength)||  
|[CDockingPanesRow::GetAvailableSpace](#getavailablespace)||  
|[CDockingPanesRow::GetClientRect](#getclientrect)||  
|[CDockingPanesRow::GetDockSite](#getdocksite)||  
|[CDockingPanesRow::GetExtraSpace](#getextraspace)||  
|[CDockingPanesRow::GetGroupFromPane](#getgroupfrompane)||  
|[CDockingPanesRow::GetID](#getid)||  
|[CDockingPanesRow::GetMaxPaneSize](#getmaxpanesize)||  
|[CDockingPanesRow::GetPaneCount](#getpanecount)||  
|[CDockingPanesRow::GetPaneList](#getpanelist)||  
|[CDockingPanesRow::GetRowAlignment](#getrowalignment)||  
|[CDockingPanesRow::GetRowHeight](#getrowheight)||  
|[CDockingPanesRow::GetRowOffset](#getrowoffset)||  
|[CDockingPanesRow::GetVisibleCount](#getvisiblecount)||  
|[CDockingPanesRow::GetWindowRect](#getwindowrect)||  
|[CDockingPanesRow::HasPane](#haspane)||  
|[CDockingPanesRow::IsEmpty](#isempty)||  
|[CDockingPanesRow::IsExclusiveRow](#isexclusiverow)||  
|[CDockingPanesRow::IsHorizontal](#ishorizontal)||  
|[CDockingPanesRow::IsVisible](#isvisible)||  
|[CDockingPanesRow::Move](#move)||  
|[CDockingPanesRow::MovePane](#movepane)||  
|[CDockingPanesRow::OnResizePane](#onresizepane)||  
|[CDockingPanesRow::RedrawAll](#redrawall)||  
|[CDockingPanesRow::RemovePane](#removepane)||  
|[CDockingPanesRow::ReplacePane](#replacepane)||  
|[CDockingPanesRow::RepositionPanes](#repositionpanes)||  
|[CDockingPanesRow::Resize](#resize)||  
|[CDockingPanesRow::ResizeByPaneDivider](#resizebypanedivider)||  
|[CDockingPanesRow::ScreenToClient](#screentoclient)||  
|[CDockingPanesRow::SetExtra](#setextra)||  
|[CDockingPanesRow::ShowDockSiteRow](#showdocksiterow)||  
|[CDockingPanesRow::ShowPane](#showpane)||  
|[CDockingPanesRow::UpdateVisibleState](#updatevisiblestate)||  
  
## <a name="remarks"></a>Açıklamalar  
 `CDockingPanesRow` nesneler, dock sitesine nesneler tarafından dahili olarak oluşturulur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl alındığını anlatan bir `CDockingPanesRow` nesnesinden bir `CMFCAutoHideBar` nesne.  
  
 [!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cdockingpanesrow-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxDockingPanesRow.h  
  
##  <a name="addpane"></a>  CDockingPanesRow::AddPane  

  
```  
virtual void AddPane(
    CPane* pControlBar,  
    AFX_DOCK_METHOD dockMethod,  
    LPCRECT lpRect = NULL,  
    BOOL bAddLast = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
*pControlBar*<br/>
[in] [in] *dockMethod*  
*lpRect*<br/>
[in] [in] *bAddLast*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addpanefromrow"></a>  CDockingPanesRow::AddPaneFromRow  

  
```  
virtual void AddPaneFromRow(
    CPane* pControlBar,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parametreler  
*pControlBar*<br/>
[in] [in] *dockMethod*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="arrangepanes"></a>  CDockingPanesRow::ArrangePanes  
 Belirtilen kenar boşluğuna göre bir satır bölmelerinde yerleştirme ve parametreleri aralık düzenler.  
  
```  
virtual void ArrangePanes(
    int nMargin,  
    int nSpacing);
```  
  
### <a name="parameters"></a>Parametreler  
*nMargin*<br/>
[in] İlk bölmesinin sol üst köşedeki satırın piksel cinsinden uzaklığı belirtir.  
  
*nSpacing*<br/>
[in] Piksel cinsinden bölmeleri arasındaki boşluğu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Nereye sabitleneceğini sıradaki bölmeleri düzenlemek için bu yöntemi çağırın. Bu yöntemi çağrıldıktan sonra çağırmanız gerekir `CDockingPanesRow::FixupVirtualRects(FALSE, NULL)`.  
  
##  <a name="calcfixedlayout"></a>  CDockingPanesRow::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parametreler  
*bStretch*<br/>
[in] [in] *bHorz*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="cdockingpanesrow"></a>  CDockingPanesRow::CDockingPanesRow  

  
```  
CDockingPanesRow(
    CDockSite* pParentDockBar,  
    int nOffset,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parametreler  
*pParentDockBar*<br/>
[in] [in] *nOffset*  
 [in] *nHeight*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="create"></a>  CDockingPanesRow::Create  

  
```  
virtual BOOL Create();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="expandstretchedpanes"></a>  CDockingPanesRow::ExpandStretchedPanes  

  
```  
void ExpandStretchedPanes();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="expandstretchedpanesrect"></a>  CDockingPanesRow::ExpandStretchedPanesRect  

  
```  
void ExpandStretchedPanesRect();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="fixupvirtualrects"></a>  CDockingPanesRow::FixupVirtualRects  

  
```  
void FixupVirtualRects(
    bool bMoveBackToVirtualRect,  
    CPane* pBarToExclude = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
*bMoveBackToVirtualRect*<br/>
[in] [in] *pBarToExclude*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getavailablelength"></a>  CDockingPanesRow::GetAvailableLength  

  
```  
virtual int GetAvailableLength(BOOL bUseVirtualRect = FALSE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bUseVirtualRect*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getavailablespace"></a>  CDockingPanesRow::GetAvailableSpace  

  
```  
virtual void GetAvailableSpace(CRect& rect);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dikdörtgen*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getclientrect"></a>  CDockingPanesRow::GetClientRect  

  
```  
void GetClientRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dikdörtgen*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getdocksite"></a>  CDockingPanesRow::GetDockSite  

  
```  
CDockSite* GetDockSite() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getextraspace"></a>  CDockingPanesRow::GetExtraSpace  

  
```  
int GetExtraSpace() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getgroupfrompane"></a>  CDockingPanesRow::GetGroupFromPane  

  
```  
void GetGroupFromPane(
    CPane* pBar,  
    CObList& lst);
```  
  
### <a name="parameters"></a>Parametreler  
*pBar*<br/>
[in] [in] *lst*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getid"></a>  CDockingPanesRow::GetID  

  
```  
int GetID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getmaxpanesize"></a>  CDockingPanesRow::GetMaxPaneSize  

  
```  
int GetMaxPaneSize(BOOL bSkipHiddenBars = TRUE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSkipHiddenBars*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanecount"></a>  CDockingPanesRow::GetPaneCount  

  
```  
int GetPaneCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanelist"></a>  CDockingPanesRow::GetPaneList  

  
```  
const CObList& GetPaneList() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrowalignment"></a>  CDockingPanesRow::GetRowAlignment  

  
```  
DWORD GetRowAlignment() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrowheight"></a>  CDockingPanesRow::GetRowHeight  

  
```  
int GetRowHeight() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrowoffset"></a>  CDockingPanesRow::GetRowOffset  

  
```  
int GetRowOffset() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getvisiblecount"></a>  CDockingPanesRow::GetVisibleCount  

  
```  
virtual int GetVisibleCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getwindowrect"></a>  CDockingPanesRow::GetWindowRect  

  
```  
void GetWindowRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dikdörtgen*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="haspane"></a>  CDockingPanesRow::HasPane  

  
```  
BOOL HasPane(CBasePane* pControlBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pControlBar*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isempty"></a>  CDockingPanesRow::IsEmpty  

  
```  
virtual BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isexclusiverow"></a>  CDockingPanesRow::IsExclusiveRow  

  
```  
virtual BOOL IsExclusiveRow() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ishorizontal"></a>  CDockingPanesRow::IsHorizontal  

  
```  
bool IsHorizontal() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isvisible"></a>  CDockingPanesRow::IsVisible  

  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="move"></a>  CDockingPanesRow::Move  

  
```  
virtual void Move(int nOffset);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nOffset*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="movepane"></a>  CDockingPanesRow::MovePane  

  
```  
void MovePane(
    CPane* pControlBar,  
    CPoint ptOffset,  
    BOOL bSwapControlBars,  
    HDWP& hdwp);

 
void MovePane(
    CPane* pControlBar,  
    CRect rectTarget,  
    HDWP& hdwp);

 
void MovePane(
    CPane* pControlBar,  
    int nOffset,  
    bool bForward,  
    HDWP& hdwp);

 
void MovePane(
    CPane* pControlBar,  
    int nAbsolutOffset,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parametreler  
*pControlBar*<br/>
[in] [in] *ptOffset*  
*bSwapControlBars*<br/>
[in] [in] *hdwp*  
*rectTarget*<br/>
[in] [in] *nOffset*  
*bForward*<br/>
[in] [in] *nAbsolutOffset*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onresizepane"></a>  CDockingPanesRow::OnResizePane  

  
```  
virtual void OnResizePane(CBasePane* pControlBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pControlBar*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="redrawall"></a>  CDockingPanesRow::RedrawAll  

  
```  
void RedrawAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removepane"></a>  CDockingPanesRow::RemovePane  

  
```  
virtual void RemovePane(CPane* pControlBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pControlBar*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="replacepane"></a>  CDockingPanesRow::ReplacePane  

  
```  
virtual BOOL ReplacePane(
    CPane* pBarOld,  
    CPane* pBarNew);
```  
  
### <a name="parameters"></a>Parametreler  
*pBarOld*<br/>
[in] [in] *pBarNew*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="repositionpanes"></a>  CDockingPanesRow::RepositionPanes  

  
```  
virtual void RepositionPanes(
    CRect& rectNewParentBarArea,  
    UINT nSide = (UINT)-1,  
    BOOL bExpand = FALSE,  
    int nOffset = 0);
```  
  
### <a name="parameters"></a>Parametreler  
*rectNewParentBarArea*<br/>
[in] [in] *nSide*  
*bExpand*<br/>
[in] [in] *nOffset*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="resize"></a>  CDockingPanesRow::Resize  

  
```  
virtual int Resize(int nOffset);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nOffset*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="resizebypanedivider"></a>  CDockingPanesRow::ResizeByPaneDivider  

  
```  
virtual int ResizeByPaneDivider(int);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *int*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="screentoclient"></a>  CDockingPanesRow::ScreenToClient  

  
```  
void ScreenToClient(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dikdörtgen*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setextra"></a>  CDockingPanesRow::SetExtra  

  
```  
void SetExtra(
    int nExtraSpace,  
    AFX_ROW_ALIGNMENT rowExtraAlign);
```  
  
### <a name="parameters"></a>Parametreler  
*nExtraSpace*<br/>
[in] [in] *rowExtraAlign*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="showdocksiterow"></a>  CDockingPanesRow::ShowDockSiteRow  

  
```  
virtual void ShowDockSiteRow(
    BOOL bShow,  
    BOOL bDelay);
```  
  
### <a name="parameters"></a>Parametreler  
*bBilgi Göster*<br/>
[in] [in] *bDelay*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="showpane"></a>  CDockingPanesRow::ShowPane  

  
```  
virtual BOOL ShowPane(
    CPane* pControlBar,  
    BOOL bShow,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
*pControlBar*<br/>
[in] [in] *bBilgi Göster*  
 [in] *bDelay*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="updatevisiblestate"></a>  CDockingPanesRow::UpdateVisibleState  

  
```  
virtual void UpdateVisibleState(BOOL bDelay);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bDelay*  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [CDockSite sınıfı](../../mfc/reference/cdocksite-class.md)   
 [CPane Sınıfı](../../mfc/reference/cpane-class.md)
