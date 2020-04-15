---
title: CDockSite Sınıfı
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
ms.openlocfilehash: a95ee024d9df835102eeffc8443ae6225775aff7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375548"
---
# <a name="cdocksite-class"></a>CDockSite Sınıfı

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

[CPane Sınıfı'ndan](../../mfc/reference/cpane-class.md) türetilen bölmeleri satır kümelerine düzenlemek için işlevsellik sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CDockSite: public CBasePane
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDockSite::AddRow](#addrow)||
|[CDockSite::AyarlamaDockingDüzeni](#adjustdockinglayout)|[(CBasePane geçersiz kılar::AyarlamaDockingDüzeni](../../mfc/reference/cbasepane-class.md#adjustdockinglayout).)|
|[CDockSite::Düzeni Ayarlama](#adjustlayout)|[(Overrides CBasePane::Düzeni ayarla](../../mfc/reference/cbasepane-class.md#adjustlayout).)|
|[CDockSite::AlignDockSite](#aligndocksite)||
|[CDockSite::CalcFixedLayout](#calcfixedlayout)|[(Overrides CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CDockSite::CanAcceptPane](#canacceptpane)|[(Overrides CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane).)|
|[CDockSite::CreateEx](#createex)|[(CBasePane geçersiz kılar::CreateEx](../../mfc/reference/cbasepane-class.md#createex).)|
|[CDockSite::CreateRow](#createrow)||
|[CDockSite::DockPane](#dockpane)|[(Overrides CBasePane::DockPane](../../mfc/reference/cbasepane-class.md#dockpane).)|
|[CDockSite::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|[(Overrides CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CDockSite::FindRowIndex](#findrowindex)||
|[CDockSite::FixupVirtualRects](#fixupvirtualrects)||
|[CDockSite::GetDockSiteID](#getdocksiteid)||
|[CDockSite::GetDockSiteRowsList](#getdocksiterowslist)||
|[CDockSite::ErişilebilirlikUyumlu](#isaccessibilitycompatible)|(Geçersiz `CBasePane::IsAccessibilityCompatible`kılar .)|
|[CdockSite::IsdragMode](#isdragmode)||
|[Cdocksite::IslastRow](#islastrow)||
|[CDockSite::IsRectWithinDockSite](#isrectwithindocksite)||
|[CDockSite::IsResizable](#isresizable)|(Geçersiz kılar [CBasePane::IsResizable](../../mfc/reference/cbasepane-class.md#isresizable).)|
|[CDockSite::MovePane](#movepane)||
|[CDockSite::OnInsertRow](#oninsertrow)||
|[Cdocksite::OnRemoveRow](#onremoverow)||
|[CDockSite::OnResizeRow](#onresizerow)||
|[CDockSite::OnsetwindowPos](#onsetwindowpos)||
|[Cdocksite::OnShowRow](#onshowrow)||
|[CDockSite::OnsizeParent](#onsizeparent)||
|[CDockSite::PaneFromPoint](#panefrompoint)|Verilen parametre tarafından belirtilen noktada dock sitesinde kenetlenmiş bir bölme döndürür.|
|[CDockSite::DockPaneLeftOf](#dockpaneleftof)|Başka bir bölmenin soluna bir bölme yapıştırın.|
|[CDockSite::FindPaneByID](#findpanebyid)|Verilen kimlikle tanımlanan bölmeyi döndürür.|
|[CDockSite::GetPaneList](#getpanelist)|Rıhtım yerinde kenetlenmiş bölmelerin listesini verir.|
|[CDockSite::RectSideFromPoint](#rectsidefrompoint)||
|[CDockSite::RemovePane](#removepane)||
|[CDockSite::RemoveRow](#removerow)||
|[CDockSite::ReplacePane](#replacepane)||
|[CDockSite::RepositionPanes](#repositionpanes)||
|[CDockSite::ResizeDockSite](#resizedocksite)||
|[CDockSite::ResizeRow](#resizerow)||
|[CDockSite::ShowPane](#showpane)|Bölmeyi gösterir.|
|[CDockSite::ShowRow](#showrow)||
|[CDockSite::SwapRows](#swaprows)||

## <a name="remarks"></a>Açıklamalar

`CDockSite` [Çerçeve, CFrameWndEx'i](../../mfc/reference/cframewndex-class.md#enabledocking)aradiğinizde nesneleri otomatik olarak oluşturur::EtkinleştirDocking. Dock site pencereleri ana çerçeve penceresinde istemci alanının kenarına konumlandırılmış.

[CFrameWndEx Class](../../mfc/reference/cframewndex-class.md) bu hizmetleri işlediği için genellikle dock sitesi tarafından sağlanan hizmetleri aramak zorunda kalmamanız gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CDockSite` nasıl oluşturulacak olduğunu gösterir.

[!code-cpp[NVC_MFC_RibbonApp#27](../../mfc/reference/codesnippet/cpp/cdocksite-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)\
•&nbsp;[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;•&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;•&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;•&nbsp;[CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxDockSite.h

## <a name="cdocksiteaddrow"></a><a name="addrow"></a>CDockSite::AddRow

```
CDockingPanesRow* AddRow(
    POSITION pos,
    int nHeight);
```

### <a name="parameters"></a>Parametreler

[içinde] *pos*<br/>

[içinde] *nYükseklik*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteadjustdockinglayout"></a><a name="adjustdockinglayout"></a>CDockSite::AyarlamaDockingDüzeni

```
virtual void AdjustDockingLayout();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteadjustlayout"></a><a name="adjustlayout"></a>CDockSite::Düzeni Ayarlama

```
virtual void AdjustLayout();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitealigndocksite"></a><a name="aligndocksite"></a>CDockSite::AlignDockSite

```
void AlignDockSite(
    const CRect& rectToAlignBy,
    CRect& rectResult,
    BOOL bMoveImmediately);
```

### <a name="parameters"></a>Parametreler

[içinde] *rectToAlignBy*<br/>

[içinde] *rektResult*<br/>

[içinde] *bMoveImmediately*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitecalcfixedlayout"></a><a name="calcfixedlayout"></a>CDockSite::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

[içinde] *bStretch*<br/>

[içinde] *bHorz*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitecanacceptpane"></a><a name="canacceptpane"></a>CDockSite::CanAcceptPane

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *pBar*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitecreateex"></a><a name="createex"></a>CDockSite::CreateEx

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

[içinde] *dwStyleEx*<br/>

[içinde] *dwStyle*<br/>

[içinde] *rekt*<br/>

[içinde] *pParentWnd*<br/>

[içinde] *dwControlBarStyle*<br/>

[içinde] *pContext*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitecreaterow"></a><a name="createrow"></a>CDockSite::CreateRow

```
virtual CDockingPanesRow* CreateRow(
    CDockSite* pParentDockBar,
    int nOffset,
    int nRowHeight);
```

### <a name="parameters"></a>Parametreler

[içinde] *pParentDockBar*<br/>

[içinde] *nOffset*<br/>

[içinde] *nRowHeight*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitedockpane"></a><a name="dockpane"></a>CDockSite::DockPane

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Parametreler

[içinde] *pWnd*<br/>

[içinde] *dockMethod*<br/>

[içinde] *lpRect*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitedockpaneleftof"></a><a name="dockpaneleftof"></a>CDockSite::DockPaneLeftOf

Başka bir bölmenin soluna bir bölme yapıştırın.

```
virtual BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>Parametreler

*pBarToDock*<br/>
[içinde, dışarı] bölmenin *pTargetBar'ın*soluna sabitlenecek bir işaretçi.

*pTargetBar*<br/>
[içinde, dışarı] Hedef bölmeye bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bölme başarıyla sabitlenirse DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitedoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CDockSite::DoesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitefindpanebyid"></a><a name="findpanebyid"></a>CDockSite::FindPaneByID

Bölmeyi verilen kimlikle birlikte döndürür.

```
CPane* FindPaneByID(UINT nID);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
[içinde] Bulunacak bölmenin komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen komut kimliğiyle bölmeye işaretçi veya bölme bulunamazsa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitefindrowindex"></a><a name="findrowindex"></a>CDockSite::FindRowIndex

```
int FindRowIndex(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>Parametreler

[içinde] *pRow*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitefixupvirtualrects"></a><a name="fixupvirtualrects"></a>CDockSite::FixupVirtualRects

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitegetdocksiteid"></a><a name="getdocksiteid"></a>CDockSite::GetDockSiteID

```
virtual UINT GetDockSiteID() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitegetdocksiterowslist"></a><a name="getdocksiterowslist"></a>CDockSite::GetDockSiteRowsList

```
const CObList& GetDockSiteRowsList() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitegetpanelist"></a><a name="getpanelist"></a>CDockSite::GetPaneList

Dock alanına sabitlenmiş bölmelerin listesini verir.

```
const CObList& GetPaneList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda yerleştirme çubuğuna kenetlenmiş olan bölmeler listesine salt okunur başvurusu.

## <a name="cdocksiteisaccessibilitycompatible"></a><a name="isaccessibilitycompatible"></a>CDockSite::ErişilebilirlikUyumlu

```
virtual BOOL IsAccessibilityCompatible();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteisdragmode"></a><a name="isdragmode"></a>CdockSite::IsdragMode

```
virtual BOOL IsDragMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteislastrow"></a><a name="islastrow"></a>Cdocksite::IslastRow

```
bool IsLastRow(CDockingPanesRow* pRow) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *pRow*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteisrectwithindocksite"></a><a name="isrectwithindocksite"></a>CDockSite::IsRectWithinDockSite

```
BOOL IsRectWithinDockSite(
    CRect rect,
    CPoint& ptDelta);
```

### <a name="parameters"></a>Parametreler

[içinde] *rekt*<br/>

[içinde] *ptDelta*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteisresizable"></a><a name="isresizable"></a>CDockSite::IsResizable

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitemovepane"></a><a name="movepane"></a>CDockSite::MovePane

```
virtual BOOL MovePane(
    CPane* pWnd,
    UINT nFlags,
    CPoint ptOffset);
```

### <a name="parameters"></a>Parametreler

[içinde] *pWnd*<br/>

[içinde] *nBayraklar*<br/>

[içinde] *ptOffset*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteoninsertrow"></a><a name="oninsertrow"></a>CDockSite::OnInsertRow

```
virtual void OnInsertRow(POSITION pos);
```

### <a name="parameters"></a>Parametreler

[içinde] *pos*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteonremoverow"></a><a name="onremoverow"></a>Cdocksite::OnRemoveRow

```
virtual void OnRemoveRow(
    POSITION pos,
    BOOL bByShow = FALSE);
```

### <a name="parameters"></a>Parametreler

[içinde] *pos*<br/>

[içinde] *bByShow*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteonresizerow"></a><a name="onresizerow"></a>CDockSite::OnResizeRow

```
virtual int OnResizeRow(
    CDockingPanesRow* pRowToResize,
    int nOffset);
```

### <a name="parameters"></a>Parametreler

[içinde] *pRowToResize*<br/>

[içinde] *nOffset*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteonsizeparent"></a><a name="onsizeparent"></a>CDockSite::OnsizeParent

```
virtual void OnSizeParent(
    CRect& rectAvailable,
    UINT nSide,
    BOOL bExpand,
    int nOffset);
```

### <a name="parameters"></a>Parametreler

[içinde] *rectKullanılabilir*<br/>

[içinde] *nSide*<br/>

[içinde] *bGenişletin*<br/>

[içinde] *nOffset*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteonsetwindowpos"></a><a name="onsetwindowpos"></a>CDockSite::OnsetwindowPos

```
virtual BOOL OnSetWindowPos(
    const CWnd* pWndInsertAfter,
    const CRect& rectWnd,
    UINT nFlags);
```

### <a name="parameters"></a>Parametreler

[içinde] *pWndInsertAfter*<br/>

[içinde] *rektWnd*<br/>

[içinde] *nBayraklar*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteonshowrow"></a><a name="onshowrow"></a>Cdocksite::OnShowRow

```
virtual void OnShowRow(
    POSITION pos,
    BOOL bShow);
```

### <a name="parameters"></a>Parametreler

[içinde] *pos*<br/>

[içinde] *bGöster*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitepanefrompoint"></a><a name="panefrompoint"></a>CDockSite::PaneFromPoint

Verilen parametre tarafından belirtilen noktada dock sitesinde kenetlenmiş bir bölme döndürür.

```
virtual CPane* PaneFromPoint(CPoint pt);
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
[içinde] Bölmenin alması için ekran koordinatlarında bir nokta.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen noktada bölme yoksa, belirtilen noktada bulunan bölmeye işaretçi veya NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiterectsidefrompoint"></a><a name="rectsidefrompoint"></a>CDockSite::RectSideFromPoint

```
static int __stdcall RectSideFromPoint(
    const CRect& rect,
    const CPoint& point);
```

### <a name="parameters"></a>Parametreler

[içinde] *rekt*<br/>

[içinde] *nokta*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteremovepane"></a><a name="removepane"></a>CDockSite::RemovePane

```
virtual void RemovePane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Parametreler

[içinde] *pWnd*<br/>

[içinde] *dockMethod*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteremoverow"></a><a name="removerow"></a>CDockSite::RemoveRow

```
void RemoveRow(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>Parametreler

[içinde] *pRow*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksitereplacepane"></a><a name="replacepane"></a>CDockSite::ReplacePane

```
BOOL ReplacePane(
    CPane* pOldBar,
    CPane* pNewBar);
```

### <a name="parameters"></a>Parametreler

[içinde] *pOldBar*<br/>

[içinde] *pNewBar*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiterepositionpanes"></a><a name="repositionpanes"></a>CDockSite::RepositionPanes

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>Parametreler

[içinde] *rectNewClientArea*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteresizedocksite"></a><a name="resizedocksite"></a>CDockSite::ResizeDockSite

```
void ResizeDockSite(
    int nNewWidth,
    int nNewHeight);
```

### <a name="parameters"></a>Parametreler

[içinde] *nNewWidth*<br/>

[içinde] *nNewHeight*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteresizerow"></a><a name="resizerow"></a>CDockSite::ResizeRow

```
int ResizeRow(
    CDockingPanesRow* pRow,
    int nNewSize,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>Parametreler

[içinde] *pRow*<br/>

[içinde] *nNewSize*<br/>

[içinde] *bAdjustLayout*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteshowpane"></a><a name="showpane"></a>CDockSite::ShowPane

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
[içinde, dışarı] Bölmesi gösterilecek veya gizlenecek bir işaretçi.

*bGöster*<br/>
[içinde] Bölmenin gösterilen olduğunu belirtmek için TRUE; Bölmenin gizleneceğini belirtmek için FALSE.

*bGecikme*<br/>
[içinde] Bölmenin düzeninin bölme gösterilene kadar geciktirilmesi gerektiğini belirtmek için DOĞRU; aksi takdirde, YANLIŞ.

*bEtkinleştir*<br/>
[içinde] Bu parametre kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Bölme başarılı bir şekilde gösteriliyorsa veya gizlendiyse DOĞRU. Belirtilen bölme bu dock sitesine ait değilse YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Kenetlenmiş bölmeleri göstermek veya gizlemek için bu yöntemi arayın. Normalde, ana çerçeve penceresi `CDockSite::ShowPane` veya temel bölme tarafından çağrıldığı için doğrudan aramayapmanız gerekmez.

## <a name="cdocksiteshowrow"></a><a name="showrow"></a>CDockSite::ShowRow

```
void ShowRow(
    CDockingPanesRow* pRow,
    BOOL bShow,
    BOOL bAdjustLayout);
```

### <a name="parameters"></a>Parametreler

[içinde] *pRow*<br/>

[içinde] *bGöster*<br/>

[içinde] *bAdjustLayout*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdocksiteswaprows"></a><a name="swaprows"></a>CDockSite::SwapRows

```
void SwapRows(
    CDockingPanesRow* pFirstRow,
    CDockingPanesRow* pSecondRow);
```

### <a name="parameters"></a>Parametreler

[içinde] *pFirstRow*<br/>

[içinde] *pSecondRow*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CBasePane Sınıfı](../../mfc/reference/cbasepane-class.md)
