---
title: "CDockSite sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockSite
- AFXDOCKSITE/CDockSite
- AFXDOCKSITE/CDockSite::AddRow
- AFXDOCKSITE/CDockSite::AdjustDockingLayout
- AFXDOCKSITE/CDockSite::AdjustLayout
- AFXDOCKSITE/CDockSite::AlignDockSite
- AFXDOCKSITE/CDockSite::CalcFixedLayout
- AFXDOCKSITE/CDockSite::CanAcceptPane
- AFXDOCKSITE/CDockSite::CreateEx
- AFXDOCKSITE/CDockSite::CreateRow
- AFXDOCKSITE/CDockSite::DockPane
- AFXDOCKSITE/CDockSite::DoesAllowDynInsertBefore
- AFXDOCKSITE/CDockSite::FindRowIndex
- AFXDOCKSITE/CDockSite::FixupVirtualRects
- AFXDOCKSITE/CDockSite::GetDockSiteID
- AFXDOCKSITE/CDockSite::GetDockSiteRowsList
- AFXDOCKSITE/CDockSite::IsAccessibilityCompatible
- AFXDOCKSITE/CDockSite::IsDragMode
- AFXDOCKSITE/CDockSite::IsLastRow
- AFXDOCKSITE/CDockSite::IsRectWithinDockSite
- AFXDOCKSITE/CDockSite::IsResizable
- AFXDOCKSITE/CDockSite::MovePane
- AFXDOCKSITE/CDockSite::OnInsertRow
- AFXDOCKSITE/CDockSite::OnRemoveRow
- AFXDOCKSITE/CDockSite::OnResizeRow
- AFXDOCKSITE/CDockSite::OnSetWindowPos
- AFXDOCKSITE/CDockSite::OnShowRow
- AFXDOCKSITE/CDockSite::OnSizeParent
- AFXDOCKSITE/CDockSite::PaneFromPoint
- AFXDOCKSITE/CDockSite::DockPaneLeftOf
- AFXDOCKSITE/CDockSite::FindPaneByID
- AFXDOCKSITE/CDockSite::GetPaneList
- AFXDOCKSITE/CDockSite::RectSideFromPoint
- AFXDOCKSITE/CDockSite::RemovePane
- AFXDOCKSITE/CDockSite::RemoveRow
- AFXDOCKSITE/CDockSite::ReplacePane
- AFXDOCKSITE/CDockSite::RepositionPanes
- AFXDOCKSITE/CDockSite::ResizeDockSite
- AFXDOCKSITE/CDockSite::ResizeRow
- AFXDOCKSITE/CDockSite::ShowPane
- AFXDOCKSITE/CDockSite::ShowRow
- AFXDOCKSITE/CDockSite::SwapRows
dev_langs:
- C++
helpviewer_keywords:
- CDockSite [MFC], AddRow
- CDockSite [MFC], AdjustDockingLayout
- CDockSite [MFC], AdjustLayout
- CDockSite [MFC], AlignDockSite
- CDockSite [MFC], CalcFixedLayout
- CDockSite [MFC], CanAcceptPane
- CDockSite [MFC], CreateEx
- CDockSite [MFC], CreateRow
- CDockSite [MFC], DockPane
- CDockSite [MFC], DoesAllowDynInsertBefore
- CDockSite [MFC], FindRowIndex
- CDockSite [MFC], FixupVirtualRects
- CDockSite [MFC], GetDockSiteID
- CDockSite [MFC], GetDockSiteRowsList
- CDockSite [MFC], IsAccessibilityCompatible
- CDockSite [MFC], IsDragMode
- CDockSite [MFC], IsLastRow
- CDockSite [MFC], IsRectWithinDockSite
- CDockSite [MFC], IsResizable
- CDockSite [MFC], MovePane
- CDockSite [MFC], OnInsertRow
- CDockSite [MFC], OnRemoveRow
- CDockSite [MFC], OnResizeRow
- CDockSite [MFC], OnSetWindowPos
- CDockSite [MFC], OnShowRow
- CDockSite [MFC], OnSizeParent
- CDockSite [MFC], PaneFromPoint
- CDockSite [MFC], DockPaneLeftOf
- CDockSite [MFC], FindPaneByID
- CDockSite [MFC], GetPaneList
- CDockSite [MFC], RectSideFromPoint
- CDockSite [MFC], RemovePane
- CDockSite [MFC], RemoveRow
- CDockSite [MFC], ReplacePane
- CDockSite [MFC], RepositionPanes
- CDockSite [MFC], ResizeDockSite
- CDockSite [MFC], ResizeRow
- CDockSite [MFC], ShowPane
- CDockSite [MFC], ShowRow
- CDockSite [MFC], SwapRows
ms.assetid: 0fcfff79-5f50-4281-b2de-a55653bbea40
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e2492738914062be692c1ddd02fd04bc461cd6b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdocksite-class"></a>CDockSite sınıfı
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Türetilmiş bölmeleri düzenleme için işlevsellik sağlar [CPane sınıfı](../../mfc/reference/cpane-class.md) satır kümeleri içine.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDockSite: public CBasePane  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDockSite::AddRow](#addrow)||  
|[CDockSite::AdjustDockingLayout](#adjustdockinglayout)|(Geçersiz kılmaları [CBasePane::AdjustDockingLayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout).)|  
|[CDockSite::AdjustLayout](#adjustlayout)|(Geçersiz kılmaları [CBasePane::AdjustLayout](../../mfc/reference/cbasepane-class.md#adjustlayout).)|  
|[CDockSite::AlignDockSite](#aligndocksite)||  
|[CDockSite::CalcFixedLayout](#calcfixedlayout)|(Geçersiz kılmaları [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CDockSite::CanAcceptPane](#canacceptpane)|(Geçersiz kılmaları [CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane).)|  
|[CDockSite::CreateEx](#createex)|(Geçersiz kılmaları [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).)|  
|[CDockSite::CreateRow](#createrow)||  
|[CDockSite::DockPane](#dockpane)|(Geçersiz kılmaları [CBasePane::DockPane](../../mfc/reference/cbasepane-class.md#dockpane).)|  
|[CDockSite::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(Geçersiz kılmaları [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CDockSite::FindRowIndex](#findrowindex)||  
|[CDockSite::FixupVirtualRects](#fixupvirtualrects)||  
|[CDockSite::GetDockSiteID](#getdocksiteid)||  
|[CDockSite::GetDockSiteRowsList](#getdocksiterowslist)||  
|[CDockSite::IsAccessibilityCompatible](#isaccessibilitycompatible)|(Geçersiz kılmaları `CBasePane::IsAccessibilityCompatible`.)|  
|[CDockSite::IsDragMode](#isdragmode)||  
|[CDockSite::IsLastRow](#islastrow)||  
|[CDockSite::IsRectWithinDockSite](#isrectwithindocksite)||  
|[CDockSite::IsResizable](#isresizable)|(Geçersiz kılmaları [CBasePane::IsResizable](../../mfc/reference/cbasepane-class.md#isresizable).)|  
|[CDockSite::MovePane](#movepane)||  
|[CDockSite::OnInsertRow](#oninsertrow)||  
|[CDockSite::OnRemoveRow](#onremoverow)||  
|[CDockSite::OnResizeRow](#onresizerow)||  
|[CDockSite::OnSetWindowPos](#onsetwindowpos)||  
|[CDockSite::OnShowRow](#onshowrow)||  
|[CDockSite::OnSizeParent](#onsizeparent)||  
|[CDockSite::PaneFromPoint](#panefrompoint)|Verilen parametresi tarafından belirtilen bir noktada yerleştirme sitedeki yerleşik bir bölme döndürür.|  
|[CDockSite::DockPaneLeftOf](#dockpaneleftof)|Bir bölme başka bir bölme soluna docks.|  
|[CDockSite::FindPaneByID](#findpanebyid)|Verilen kimliğe tarafından tanımlanan bölmesinde döndürür|  
|[CDockSite::GetPaneList](#getpanelist)|Yerleştirme sitede yerleşik bölmeler listesini döndürür.|  
|[CDockSite::RectSideFromPoint](#rectsidefrompoint)||  
|[CDockSite::RemovePane](#removepane)||  
|[CDockSite::RemoveRow](#removerow)||  
|[CDockSite::ReplacePane](#replacepane)||  
|[CDockSite::RepositionPanes](#repositionpanes)||  
|[CDockSite::ResizeDockSite](#resizedocksite)||  
|[CDockSite::ResizeRow](#resizerow)||  
|[CDockSite::ShowPane](#showpane)|Bölmesinde gösterilir.|  
|[CDockSite::ShowRow](#showrow)||  
|[CDockSite::SwapRows](#swaprows)||  
  
## <a name="remarks"></a>Açıklamalar  
 Framework oluşturur `CDockSite` çağırdığınızda otomatik olarak nesneleri [CFrameWndEx::EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking). Yerleştirme site windows ana çerçeve penceresi istemci alanına kenarında konumlandırılır.  
  
 Genellikle çünkü yuva site tarafından sağlanan hizmetlerin çağrı gerekmez [CFrameWndEx sınıfı](../../mfc/reference/cframewndex-class.md) hizmetlerin işler.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CDockSite` sınıfı.  
  
 [!code-cpp[NVC_MFC_RibbonApp#27](../../mfc/reference/codesnippet/cpp/cdocksite-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxDockSite.h  
  
##  <a name="addrow"></a>CDockSite::AddRow  

  
```  
CDockingPanesRow* AddRow(
    POSITION pos,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pos`  
 [in]`nHeight`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="adjustdockinglayout"></a>CDockSite::AdjustDockingLayout  

  
```  
virtual void AdjustDockingLayout();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="adjustlayout"></a>CDockSite::AdjustLayout  

  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="aligndocksite"></a>CDockSite::AlignDockSite  

  
```  
void AlignDockSite(
    const CRect& rectToAlignBy,  
    CRect& rectResult,  
    BOOL bMoveImmediately);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rectToAlignBy`  
 [in]`rectResult`  
 [in]`bMoveImmediately`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="calcfixedlayout"></a>CDockSite::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bStretch`  
 [in]`bHorz`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="canacceptpane"></a>CDockSite::CanAcceptPane  

  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="createex"></a>CDockSite::CreateEx  

  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    DWORD dwControlBarStyle,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`dwStyleEx`  
 [in]`dwStyle`  
 [in]`rect`  
 [in]`pParentWnd`  
 [in]`dwControlBarStyle`  
 [in]`pContext`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="createrow"></a>CDockSite::CreateRow  

  
```  
virtual CDockingPanesRow* CreateRow(
    CDockSite* pParentDockBar,  
    int nOffset,  
    int nRowHeight);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pParentDockBar`  
 [in]`nOffset`  
 [in]`nRowHeight`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="dockpane"></a>CDockSite::DockPane  

  
```  
virtual void DockPane(
    CPane* pWnd,  
    AFX_DOCK_METHOD dockMethod,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWnd`  
 [in]`dockMethod`  
 [in]`lpRect`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="dockpaneleftof"></a>CDockSite::DockPaneLeftOf  
 Bir bölme başka bir bölme soluna docks.  
  
```  
virtual BOOL DockPaneLeftOf(
    CPane* pBarToDock,  
    CPane* pTargetBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out]`pBarToDock`  
 Bir işaretçi solunda yerleşik bölmesine `pTargetBar`.  
  
 [in] [out]`pTargetBar`  
 Hedef bölmesi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bölmesinde başarıyla; yerleştirilmişse Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="doesallowdyninsertbefore"></a>CDockSite::DoesAllowDynInsertBefore  

  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="findpanebyid"></a>CDockSite::FindPaneByID  
 Verilen kimliğe bölmesiyle döndürür  
  
```  
CPane* FindPaneByID(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nID`  
 Komut Kimliği bulunamadı bölmesinin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen komut kimliği bölmesiyle gösteren bir işaretçi veya `NULL` bölmesinde bulunmazsa.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="findrowindex"></a>CDockSite::FindRowIndex  

  
```  
int FindRowIndex(CDockingPanesRow* pRow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pRow`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="fixupvirtualrects"></a>CDockSite::FixupVirtualRects  

  
```  
virtual void FixupVirtualRects();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getdocksiteid"></a>CDockSite::GetDockSiteID  

  
```  
virtual UINT GetDockSiteID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getdocksiterowslist"></a>CDockSite::GetDockSiteRowsList  

  
```  
const CObList& GetDockSiteRowsList() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanelist"></a>CDockSite::GetPaneList  
 Yerleştirme sitede yerleşik bölmeler listesini döndürür.  
  
```  
const CObList& GetPaneList() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Salt okunur başvuru bölmeleri listesi için şu anda takma çubuğunda yerleştirildi.  
  
##  <a name="isaccessibilitycompatible"></a>CDockSite::IsAccessibilityCompatible  

  
```  
virtual BOOL IsAccessibilityCompatible();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isdragmode"></a>CDockSite::IsDragMode  

  
```  
virtual BOOL IsDragMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="islastrow"></a>CDockSite::IsLastRow  

  
```  
bool IsLastRow(CDockingPanesRow* pRow) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pRow`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isrectwithindocksite"></a>CDockSite::IsRectWithinDockSite  

  
```  
BOOL IsRectWithinDockSite(
    CRect rect,  
    CPoint& ptDelta);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rect`  
 [in]`ptDelta`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isresizable"></a>CDockSite::IsResizable  

  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="movepane"></a>CDockSite::MovePane  

  
```  
virtual BOOL MovePane(
    CPane* pWnd,  
    UINT nFlags,  
    CPoint ptOffset);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWnd`  
 [in]`nFlags`  
 [in]`ptOffset`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="oninsertrow"></a>CDockSite::OnInsertRow  

  
```  
virtual void OnInsertRow(POSITION pos);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pos`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onremoverow"></a>CDockSite::OnRemoveRow  

  
```  
virtual void OnRemoveRow(
    POSITION pos,  
    BOOL bByShow = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pos`  
 [in]`bByShow`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onresizerow"></a>CDockSite::OnResizeRow  

  
```  
virtual int OnResizeRow(
    CDockingPanesRow* pRowToResize,  
    int nOffset);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pRowToResize`  
 [in]`nOffset`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsizeparent"></a>CDockSite::OnSizeParent  

  
```  
virtual void OnSizeParent(
    CRect& rectAvailable,  
    UINT nSide,  
    BOOL bExpand,  
    int nOffset);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rectAvailable`  
 [in]`nSide`  
 [in]`bExpand`  
 [in]`nOffset`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsetwindowpos"></a>CDockSite::OnSetWindowPos  

  
```  
virtual BOOL OnSetWindowPos(
    const CWnd* pWndInsertAfter,  
    const CRect& rectWnd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWndInsertAfter`  
 [in]`rectWnd`  
 [in]`nFlags`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onshowrow"></a>CDockSite::OnShowRow  

  
```  
virtual void OnShowRow(
    POSITION pos,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pos`  
 [in]`bShow`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="panefrompoint"></a>CDockSite::PaneFromPoint  
 Verilen parametresi tarafından belirtilen bir noktada yerleştirme sitedeki yerleşik bir bölme döndürür.  
  
```  
virtual CPane* PaneFromPoint(CPoint pt);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pt`  
 Alınacak bölmesinin ekran koordinatları bir nokta.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bölmesine bulunan belirli bir noktada veya `NULL` hiçbir bölmesinde belirtilen noktada mevcut olduğunda.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="rectsidefrompoint"></a>CDockSite::RectSideFromPoint  

  
```  
static int __stdcall RectSideFromPoint(
    const CRect& rect,  
    const CPoint& point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rect`  
 [in]`point`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removepane"></a>CDockSite::RemovePane  

  
```  
virtual void RemovePane(
    CPane* pWnd,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWnd`  
 [in]`dockMethod`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removerow"></a>CDockSite::RemoveRow  

  
```  
void RemoveRow(CDockingPanesRow* pRow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pRow`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="replacepane"></a>CDockSite::ReplacePane  

  
```  
BOOL ReplacePane(
    CPane* pOldBar,  
    CPane* pNewBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pOldBar`  
 [in]`pNewBar`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="repositionpanes"></a>CDockSite::RepositionPanes  

  
```  
virtual void RepositionPanes(CRect& rectNewClientArea);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rectNewClientArea`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="resizedocksite"></a>CDockSite::ResizeDockSite  

  
```  
void ResizeDockSite(
    int nNewWidth,  
    int nNewHeight);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nNewWidth`  
 [in]`nNewHeight`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="resizerow"></a>CDockSite::ResizeRow  

  
```  
int ResizeRow(
    CDockingPanesRow* pRow,  
    int nNewSize,  
    BOOL bAdjustLayout = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pRow`  
 [in]`nNewSize`  
 [in]`bAdjustLayout`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="showpane"></a>CDockSite::ShowPane  
 Bölmesinde gösterilir.  
  
```  
virtual BOOL ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out]`pBar`  
 Bir işaretçi gösterileceğini veya gizleneceğini için bölmesine.  
  
 [in]`bShow`  
 `TRUE`bölmesinde gösterilecek olduğunu belirtmek için; `FALSE` bölmesinde gizlenecek olduğunu belirtmek için.  
  
 [in]`bDelay`  
 `TRUE`bölmesinde düzenini kadar bölmesinde sonra Gecikmeli belirtmek için gösterilir; Aksi takdirde `FALSE`.  
  
 [in]`bActivate`  
 Bu parametre kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bölmesinde gösterilen veya başarıyla gizli. `FALSE`Belirtilen bölmesinde bu dock siteye ait değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerleşik bölmeleri göstermek veya gizlemek için bu yöntemi çağırın. Normalde, çağrı gerekmez `CDockSite::ShowPane` doğrudan üst çerçeve penceresi veya temel bölmesinde tarafından çağrıldığı için.  
  
##  <a name="showrow"></a>CDockSite::ShowRow  

  
```  
void ShowRow(
    CDockingPanesRow* pRow,  
    BOOL bShow,  
    BOOL bAdjustLayout);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pRow`  
 [in]`bShow`  
 [in]`bAdjustLayout`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="swaprows"></a>CDockSite::SwapRows  

  
```  
void SwapRows(
    CDockingPanesRow* pFirstRow,  
    CDockingPanesRow* pSecondRow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pFirstRow`  
 [in]`pSecondRow`  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CBasePane Sınıfı](../../mfc/reference/cbasepane-class.md)
