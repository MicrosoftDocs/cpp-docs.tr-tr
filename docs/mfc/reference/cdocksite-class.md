---
title: CDockSite sınıfı
ms.date: 10/18/2018
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
ms.openlocfilehash: 9c154fe621fb88a6dc96a9835fae95c4b86763de
ms.sourcegitcommit: bd7ddc044f9083246614b602ef6a758775313214
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68866199"
---
# <a name="cdocksite-class"></a>CDockSite sınıfı

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC\\atlmfc\\\\src MFC** klasöründe bulunan kaynak koduna bakın.

[CPane sınıfından](../../mfc/reference/cpane-class.md) türetilmiş bölmeleri satır kümelerine yerleştirmek için işlevsellik sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CDockSite: public CBasePane
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cdocksıte:: AddRow](#addrow)||
|[Cdocksıte:: AdjustDockingLayout](#adjustdockinglayout)|( [CBasePane:: AdjustDockingLayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout)geçersiz kılar.)|
|[Cdocksıte:: AdjustLayout](#adjustlayout)|( [CBasePane:: AdjustLayout](../../mfc/reference/cbasepane-class.md#adjustlayout).) öğesini geçersiz kılar|
|[Cdocksıte:: hizalaması Docksite](#aligndocksite)||
|[Cdocksıte:: CalcFixedLayout](#calcfixedlayout)|( [CBasePane:: CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).) öğesini geçersiz kılar|
|[Cdocksıte:: CanAcceptPane](#canacceptpane)|( [CBasePane:: CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane).)|
|[Cdocksıte:: CreateEx](#createex)|( [CBasePane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex)geçersiz kılar.)|
|[Cdocksıte:: CreateRow](#createrow)||
|[Cdocksıte::D ockPane](#dockpane)|( [CBasePane 'yi geçersiz kılar::D ockPane](../../mfc/reference/cbasepane-class.md#dockpane).)|
|[CDockSite::D Oesallowdynınsertbefore](#doesallowdyninsertbefore)|( [CBasePane::D Oesallowdynınsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore)geçersiz kılar.)|
|[Cdocksıte:: Findrowındex](#findrowindex)||
|[Cdocksıte:: FixupVirtualRects](#fixupvirtualrects)||
|[Cdocksıte:: Getdocksiteıd](#getdocksiteid)||
|[Cdocksıte:: Getdocksıterowslist](#getdocksiterowslist)||
|[Cdocksıte:: IsAccessibilityCompatible](#isaccessibilitycompatible)|(Geçersiz `CBasePane::IsAccessibilityCompatible`kılmalar.)|
|[Cdocksıte:: ısdragmode](#isdragmode)||
|[Cdocksıte:: ıslastrow](#islastrow)||
|[Cdocksıte:: Isrectwithındocksite](#isrectwithindocksite)||
|[Cdocksıte:: ısyeniden boyutlandırılabilir](#isresizable)|( [CBasePane:: ısyeniden boyutlandırılabilir](../../mfc/reference/cbasepane-class.md#isresizable).)|
|[Cdocksıte:: MovePane](#movepane)||
|[Cdocksıte:: Onınsertrow](#oninsertrow)||
|[Cdocksıte:: OnRemoveRow](#onremoverow)||
|[Cdocksıte:: OnResizeRow](#onresizerow)||
|[Cdocksıte:: OnSetWindowPos](#onsetwindowpos)||
|[Cdocksıte:: OnShowRow](#onshowrow)||
|[Cdocksıte:: OnSizeParent](#onsizeparent)||
|[CDockSite::P aneFromPoint](#panefrompoint)|Verilen parametre tarafından belirtilen noktada Dock sitesine yerleştirilmiş bir bölmeyi döndürür.|
|[Cdocksıte::D ockPaneLeftOf](#dockpaneleftof)|Başka bir bölmenin solunda bir bölme noktası oluşturma.|
|[Cdocksıte:: Findbölmesi Byıd](#findpanebyid)|Verilen KIMLIK tarafından tanımlanan bölmeyi döndürür.|
|[Cdocksıte:: Getbölmesi listesi](#getpanelist)|Dock sitesinde yerleştirilmiş olan bölmelerin bir listesini döndürür.|
|[Cdocksıte:: RectSideFromPoint](#rectsidefrompoint)||
|[Cdocksıte:: RemovePane](#removepane)||
|[Cdocksıte:: RemoveRow](#removerow)||
|[Cdocksıte:: ReplacePane](#replacepane)||
|[CDockSite:: Depotiona bölmeleri](#repositionpanes)||
|[Cdocksıte:: ResizeDockSite](#resizedocksite)||
|[Cdocksıte:: ResizeRow](#resizerow)||
|[Cdocksıte:: ShowPane](#showpane)|Bölmeyi gösterir.|
|[Cdocksıte:: ShowRow](#showrow)||
|[Cdocksıte:: SwapRows](#swaprows)||

## <a name="remarks"></a>Açıklamalar

Framework, `CDockSite` [CFrameWndEx:: enabletakmayı](../../mfc/reference/cframewndex-class.md#enabledocking)çağırdığınızda nesneleri otomatik olarak oluşturur. Site pencerelerini yerleştir, ana çerçeve penceresindeki istemci alanının kenarına yerleştirilir.

Bu hizmetleri, [CFrameWndEx sınıfı](../../mfc/reference/cframewndex-class.md) tarafından işletiğinden, genellikle dock sitesi tarafından sunulan hizmetleri çağırmanız gerekmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CDockSite` sınıfının bir nesnesinin nasıl oluşturulacağını gösterir.

[!code-cpp[NVC_MFC_RibbonApp#27](../../mfc/reference/codesnippet/cpp/cdocksite-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxDockSite. h

##  <a name="addrow"></a>Cdocksıte:: AddRow

```
CDockingPanesRow* AddRow(
    POSITION pos,
    int nHeight);
```

### <a name="parameters"></a>Parametreler

'ndaki *POS*<br/>

'ndaki *nHeight*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="adjustdockinglayout"></a>Cdocksıte:: AdjustDockingLayout

```
virtual void AdjustDockingLayout();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="adjustlayout"></a>Cdocksıte:: AdjustLayout

```
virtual void AdjustLayout();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="aligndocksite"></a>Cdocksıte:: hizalaması Docksite

```
void AlignDockSite(
    const CRect& rectToAlignBy,
    CRect& rectResult,
    BOOL bMoveImmediately);
```

### <a name="parameters"></a>Parametreler

'ndaki *Recttohizalaması*<br/>

'ndaki *rectResult*<br/>

'ndaki *Bmovehemen*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="calcfixedlayout"></a>Cdocksıte:: CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

'ndaki *Besnetme*<br/>

'ndaki *bHorz*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="canacceptpane"></a>Cdocksıte:: CanAcceptPane

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *pBar*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="createex"></a>Cdocksıte:: CreateEx

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

'ndaki *dwStyleEx*<br/>

'ndaki *dwStyle*<br/>

'ndaki *Rect*<br/>

'ndaki *pParentWnd*<br/>

'ndaki *dwControlBarStyle*<br/>

'ndaki *pContext*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="createrow"></a>Cdocksıte:: CreateRow

```
virtual CDockingPanesRow* CreateRow(
    CDockSite* pParentDockBar,
    int nOffset,
    int nRowHeight);
```

### <a name="parameters"></a>Parametreler

'ndaki *Pparentdockbar*<br/>

'ndaki *nKonum*<br/>

'ndaki *Nrowheight*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="dockpane"></a>Cdocksıte::D ockPane

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Parametreler

'ndaki *pWnd*<br/>

'ndaki *Dockyöntemi*<br/>

'ndaki *lpRect*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="dockpaneleftof"></a>Cdocksıte::D ockPaneLeftOf

Başka bir bölmenin solunda bir bölme noktası oluşturma.

```
virtual BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>Parametreler

*pBarToDock*<br/>
[in, out] *PTargetBar*'un soluna yerleştirilen bölmeye yönelik bir işaretçi.

*pTargetBar*<br/>
[in, out] Hedef bölmeye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bölme başarıyla sabitliyse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="doesallowdyninsertbefore"></a>CDockSite::D Oesallowdynınsertbefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="findpanebyid"></a>Cdocksıte:: Findbölmesi Byıd

Verilen KIMLIĞE sahip bölmeyi döndürür.

```
CPane* FindPaneByID(UINT nID);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
'ndaki Bulunan bölmenin komut KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen komut KIMLIĞINE sahip bölme işaretçisi veya bölme bulunamazsa NULL.

### <a name="remarks"></a>Açıklamalar

##  <a name="findrowindex"></a>Cdocksıte:: Findrowındex

```
int FindRowIndex(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>Parametreler

'ndaki *Prow*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="fixupvirtualrects"></a>Cdocksıte:: FixupVirtualRects

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="getdocksiteid"></a>Cdocksıte:: Getdocksiteıd

```
virtual UINT GetDockSiteID() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="getdocksiterowslist"></a>Cdocksıte:: Getdocksıterowslist

```
const CObList& GetDockSiteRowsList() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="getpanelist"></a>Cdocksıte:: Getbölmesi listesi

Dock sitesinde yerleştirilmiş olan bölmelerin bir listesini döndürür.

```
const CObList& GetPaneList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Takma çubuğuna yerleştirilmiş olan bölme listesine yönelik salt okunurdur bir başvuru.

##  <a name="isaccessibilitycompatible"></a>Cdocksıte:: IsAccessibilityCompatible

```
virtual BOOL IsAccessibilityCompatible();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="isdragmode"></a>Cdocksıte:: ısdragmode

```
virtual BOOL IsDragMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="islastrow"></a>Cdocksıte:: ıslastrow

```
bool IsLastRow(CDockingPanesRow* pRow) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *Prow*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="isrectwithindocksite"></a>Cdocksıte:: Isrectwithındocksite

```
BOOL IsRectWithinDockSite(
    CRect rect,
    CPoint& ptDelta);
```

### <a name="parameters"></a>Parametreler

'ndaki *Rect*<br/>

'ndaki *Ptdelta*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="isresizable"></a>Cdocksıte:: ısyeniden boyutlandırılabilir

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="movepane"></a>Cdocksıte:: MovePane

```
virtual BOOL MovePane(
    CPane* pWnd,
    UINT nFlags,
    CPoint ptOffset);
```

### <a name="parameters"></a>Parametreler

'ndaki *pWnd*<br/>

'ndaki *nFlags*<br/>

'ndaki *ptOffset*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="oninsertrow"></a>Cdocksıte:: Onınsertrow

```
virtual void OnInsertRow(POSITION pos);
```

### <a name="parameters"></a>Parametreler

'ndaki *POS*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="onremoverow"></a>Cdocksıte:: OnRemoveRow

```
virtual void OnRemoveRow(
    POSITION pos,
    BOOL bByShow = FALSE);
```

### <a name="parameters"></a>Parametreler

'ndaki *POS*<br/>

'ndaki *Bbyshow*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="onresizerow"></a>Cdocksıte:: OnResizeRow

```
virtual int OnResizeRow(
    CDockingPanesRow* pRowToResize,
    int nOffset);
```

### <a name="parameters"></a>Parametreler

'ndaki *Prowtoresize*<br/>

'ndaki *nKonum*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="onsizeparent"></a>Cdocksıte:: OnSizeParent

```
virtual void OnSizeParent(
    CRect& rectAvailable,
    UINT nSide,
    BOOL bExpand,
    int nOffset);
```

### <a name="parameters"></a>Parametreler

'ndaki *Rectavailable*<br/>

'ndaki *Nsıde*<br/>

'ndaki *Bexpand*<br/>

'ndaki *nKonum*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="onsetwindowpos"></a>Cdocksıte:: OnSetWindowPos

```
virtual BOOL OnSetWindowPos(
    const CWnd* pWndInsertAfter,
    const CRect& rectWnd,
    UINT nFlags);
```

### <a name="parameters"></a>Parametreler

'ndaki *pWndInsertAfter*<br/>

'ndaki *Rectwnd*<br/>

'ndaki *nFlags*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="onshowrow"></a>Cdocksıte:: OnShowRow

```
virtual void OnShowRow(
    POSITION pos,
    BOOL bShow);
```

### <a name="parameters"></a>Parametreler

'ndaki *POS*<br/>

'ndaki *bShow*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="panefrompoint"></a>CDockSite::P aneFromPoint

Verilen parametre tarafından belirtilen noktada Dock sitesine yerleştirilmiş bir bölmeyi döndürür.

```
virtual CPane* PaneFromPoint(CPoint pt);
```

### <a name="parameters"></a>Parametreler

*yönergelerinin*<br/>
'ndaki Bölmenin alınması için bir nokta, Ekran koordinatlarında.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen noktada bir bölme yoksa, belirtilen noktada veya NULL üzerinde bulunan bölmeye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

##  <a name="rectsidefrompoint"></a>Cdocksıte:: RectSideFromPoint

```
static int __stdcall RectSideFromPoint(
    const CRect& rect,
    const CPoint& point);
```

### <a name="parameters"></a>Parametreler

'ndaki *Rect*<br/>

'ndaki *nokta*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="removepane"></a>Cdocksıte:: RemovePane

```
virtual void RemovePane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Parametreler

'ndaki *pWnd*<br/>

'ndaki *Dockyöntemi*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="removerow"></a>Cdocksıte:: RemoveRow

```
void RemoveRow(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>Parametreler

'ndaki *Prow*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="replacepane"></a>Cdocksıte:: ReplacePane

```
BOOL ReplacePane(
    CPane* pOldBar,
    CPane* pNewBar);
```

### <a name="parameters"></a>Parametreler

'ndaki *Poldbar*<br/>

'ndaki *pNewBar*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="repositionpanes"></a>CDockSite:: Depotiona bölmeleri

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>Parametreler

'ndaki *rectNewClientArea*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="resizedocksite"></a>Cdocksıte:: ResizeDockSite

```
void ResizeDockSite(
    int nNewWidth,
    int nNewHeight);
```

### <a name="parameters"></a>Parametreler

'ndaki *Nnewwidth*<br/>

'ndaki *Nnewheight*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="resizerow"></a>Cdocksıte:: ResizeRow

```
int ResizeRow(
    CDockingPanesRow* pRow,
    int nNewSize,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>Parametreler

'ndaki *Prow*<br/>

'ndaki *Nnewsize*<br/>

'ndaki *Roztlayout*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="showpane"></a>Cdocksıte:: ShowPane

Bölmeyi gösterir.

```
virtual BOOL ShowPane(
    CBasePane* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[in, out] Görüntülenecek veya gizlenecek bölmeye yönelik bir işaretçi.

*bShow*<br/>
'ndaki Bölmenin gösterilmekte olduğunu belirtmek için TRUE; Bölmenin gizlenmeyeceğini belirtmek için FALSE.

*bDelay*<br/>
'ndaki Bölme gösterilene kadar bölmenin düzeninin geciktirileceğini belirtmek için TRUE. Aksi takdirde, FALSE.

*Bacetkinleştir*<br/>
'ndaki Bu parametre kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Bölme başarıyla gösteriliyorsa veya gizliyse doğru. Belirtilen bölme bu yerleştirme sitesine ait değilse FALSE.

### <a name="remarks"></a>Açıklamalar

Sabitlenmiş bölmeleri göstermek veya gizlemek için bu yöntemi çağırın. Normalde, üst çerçeve penceresi veya temel bölme `CDockSite::ShowPane` tarafından çağrıldığı için doğrudan çağırmanız gerekmez.

##  <a name="showrow"></a>Cdocksıte:: ShowRow

```
void ShowRow(
    CDockingPanesRow* pRow,
    BOOL bShow,
    BOOL bAdjustLayout);
```

### <a name="parameters"></a>Parametreler

'ndaki *Prow*<br/>

'ndaki *bShow*<br/>

'ndaki *Roztlayout*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="swaprows"></a>Cdocksıte:: SwapRows

```
void SwapRows(
    CDockingPanesRow* pFirstRow,
    CDockingPanesRow* pSecondRow);
```

### <a name="parameters"></a>Parametreler

'ndaki *Pfirstrow*<br/>

'ndaki *Psecondrow*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CBasePane Sınıfı](../../mfc/reference/cbasepane-class.md)
