---
description: 'Daha fazla bilgi edinin: CDockingPanesRow sınıfı'
title: CDockingPanesRow sınıfı
ms.date: 10/18/2018
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
ms.openlocfilehash: bf031b19c25cde36705333feb3baa3af9e1932ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185017"
---
# <a name="cdockingpanesrow-class"></a>CDockingPanesRow sınıfı

Bir dock sitesinin aynı yatay veya dikey satırında (sütun) bulunan bölmeler listesini yönetir.

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

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
|[CDockingPanesRow:: AddPane](#addpane)||
|[CDockingPanesRow:: AddPaneFromRow](#addpanefromrow)||
|[CDockingPanesRow:: Arrangebölmelerini](#arrangepanes)|Bir satırdaki bölmeleri belirtilen kenar boşluğu ve Aralık parametrelerine göre düzenler.|
|[CDockingPanesRow:: CalcFixedLayout](#calcfixedlayout)||
|[CDockingPanesRow:: Create](#create)||
|[CDockingPanesRow:: Expandıdiedbölmeler](#expandstretchedpanes)||
|[CDockingPanesRow:: Expandıdiedpanesrect](#expandstretchedpanesrect)||
|[CDockingPanesRow:: FixupVirtualRects](#fixupvirtualrects)||
|[CDockingPanesRow:: GetAvailableLength](#getavailablelength)||
|[CDockingPanesRow:: GetAvailableSpace](#getavailablespace)||
|[CDockingPanesRow:: GetClientRect](#getclientrect)||
|[CDockingPanesRow:: GetDockSite](#getdocksite)||
|[CDockingPanesRow:: GetExtraSpace](#getextraspace)||
|[CDockingPanesRow:: GetGroupFromPane](#getgroupfrompane)||
|[CDockingPanesRow:: GetId](#getid)||
|[CDockingPanesRow:: GetMaxPaneSize](#getmaxpanesize)||
|[CDockingPanesRow:: Getbölmesi sayısı](#getpanecount)||
|[CDockingPanesRow:: Getbölmesi listesi](#getpanelist)||
|[CDockingPanesRow:: Getrowhizalaması](#getrowalignment)||
|[CDockingPanesRow:: GetRowHeight](#getrowheight)||
|[CDockingPanesRow:: Getrowkayması](#getrowoffset)||
|[CDockingPanesRow:: GetVisibleCount](#getvisiblecount)||
|[CDockingPanesRow:: GetWindowRect](#getwindowrect)||
|[CDockingPanesRow:: HasPane](#haspane)||
|[CDockingPanesRow:: IsEmpty](#isempty)||
|[CDockingPanesRow:: ısexclusiverow](#isexclusiverow)||
|[CDockingPanesRow:: ısyatay](#ishorizontal)||
|[CDockingPanesRow:: IsVisible](#isvisible)||
|[CDockingPanesRow:: Move](#move)||
|[CDockingPanesRow:: MovePane](#movepane)||
|[CDockingPanesRow:: OnResizePane](#onresizepane)||
|[CDockingPanesRow:: RedrawAll](#redrawall)||
|[CDockingPanesRow:: RemovePane](#removepane)||
|[CDockingPanesRow:: ReplacePane](#replacepane)||
|[CDockingPanesRow:: kayıt bölmeleri](#repositionpanes)||
|[CDockingPanesRow:: Resize](#resize)||
|[CDockingPanesRow:: ResizeByPaneDivider](#resizebypanedivider)||
|[CDockingPanesRow:: ScreenToClient](#screentoclient)||
|[CDockingPanesRow:: SetExtra](#setextra)||
|[CDockingPanesRow:: Showdocksıterow](#showdocksiterow)||
|[CDockingPanesRow:: ShowPane](#showpane)||
|[CDockingPanesRow:: UpdateVisibleState](#updatevisiblestate)||

## <a name="remarks"></a>Açıklamalar

`CDockingPanesRow` nesneler, site nesneleri Dock tarafından dahili olarak oluşturulur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, nesnesinden bir nesnenin nasıl alınacağını gösterir `CDockingPanesRow` `CMFCAutoHideBar` .

[!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cdockingpanesrow-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxDockingPanesRow. h

## <a name="cdockingpanesrowaddpane"></a><a name="addpane"></a> CDockingPanesRow:: AddPane

```
virtual void AddPane(
    CPane* pControlBar,
    AFX_DOCK_METHOD dockMethod,
    LPCRECT lpRect = NULL,
    BOOL bAddLast = FALSE);
```

### <a name="parameters"></a>Parametreler

'ndaki *pControlBar*<br/>

'ndaki *Dockyöntemi*<br/>

'ndaki *lpRect*<br/>

'ndaki *Baddlast*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowaddpanefromrow"></a><a name="addpanefromrow"></a> CDockingPanesRow:: AddPaneFromRow

```
virtual void AddPaneFromRow(
    CPane* pControlBar,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Parametreler

'ndaki *pControlBar*<br/>

'ndaki *Dockyöntemi*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowarrangepanes"></a><a name="arrangepanes"></a> CDockingPanesRow:: Arrangebölmelerini

Yerleştirme bölmelerini, belirtilen kenar boşluğu ve Aralık parametrelerine göre bir satırda yerleştirir.

```
virtual void ArrangePanes(
    int nMargin,
    int nSpacing);
```

### <a name="parameters"></a>Parametreler

*nMargin*<br/>
'ndaki Satırın sol üst köşesinden ilk bölmenin aralığını piksel cinsinden belirtir.

*nSpacing*<br/>
'ndaki Bölmeler arasındaki aralığı piksel cinsinden belirtir.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, yerleştirme yapılacak sırada bölmeleri düzenlemek için çağırın. Bu yöntemi çağırdıktan sonra çağrısı yapmanız gerekir `CDockingPanesRow::FixupVirtualRects(FALSE, NULL)` .

## <a name="cdockingpanesrowcalcfixedlayout"></a><a name="calcfixedlayout"></a> CDockingPanesRow:: CalcFixedLayout

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

## <a name="cdockingpanesrowcdockingpanesrow"></a><a name="cdockingpanesrow"></a> CDockingPanesRow:: CDockingPanesRow

```
CDockingPanesRow(
    CDockSite* pParentDockBar,
    int nOffset,
    int nHeight);
```

### <a name="parameters"></a>Parametreler

'ndaki *Pparentdockbar*<br/>

'ndaki *nKonum*<br/>

'ndaki *nHeight*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowcreate"></a><a name="create"></a> CDockingPanesRow:: Create

```
virtual BOOL Create();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowexpandstretchedpanes"></a><a name="expandstretchedpanes"></a> CDockingPanesRow:: Expandıdiedbölmeler

```cpp
void ExpandStretchedPanes();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowexpandstretchedpanesrect"></a><a name="expandstretchedpanesrect"></a> CDockingPanesRow:: Expandıdiedpanesrect

```cpp
void ExpandStretchedPanesRect();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowfixupvirtualrects"></a><a name="fixupvirtualrects"></a> CDockingPanesRow:: FixupVirtualRects

```cpp
void FixupVirtualRects(
    bool bMoveBackToVirtualRect,
    CPane* pBarToExclude = NULL);
```

### <a name="parameters"></a>Parametreler

'ndaki *Bmovebacktovirtualrect*<br/>

'ndaki *Pbartoexclude*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowgetavailablelength"></a><a name="getavailablelength"></a> CDockingPanesRow:: GetAvailableLength

```
virtual int GetAvailableLength(BOOL bUseVirtualRect = FALSE) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *Busevirtualrect*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowgetavailablespace"></a><a name="getavailablespace"></a> CDockingPanesRow:: GetAvailableSpace

```
virtual void GetAvailableSpace(CRect& rect);
```

### <a name="parameters"></a>Parametreler

'ndaki *Rect*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowgetclientrect"></a><a name="getclientrect"></a> CDockingPanesRow:: GetClientRect

```cpp
void GetClientRect(CRect& rect) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *Rect*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowgetdocksite"></a><a name="getdocksite"></a> CDockingPanesRow:: GetDockSite

```
CDockSite* GetDockSite() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowgetextraspace"></a><a name="getextraspace"></a> CDockingPanesRow:: GetExtraSpace

```
int GetExtraSpace() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowgetgroupfrompane"></a><a name="getgroupfrompane"></a> CDockingPanesRow:: GetGroupFromPane

```cpp
void GetGroupFromPane(
    CPane* pBar,
    CObList& lst);
```

### <a name="parameters"></a>Parametreler

'ndaki *pBar*<br/>

'ndaki *lst*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowgetid"></a><a name="getid"></a> CDockingPanesRow:: GetId

```
int GetID() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowgetmaxpanesize"></a><a name="getmaxpanesize"></a> CDockingPanesRow:: GetMaxPaneSize

```
int GetMaxPaneSize(BOOL bSkipHiddenBars = TRUE) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *Bskiphiddenbar çubukları*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowgetpanecount"></a><a name="getpanecount"></a> CDockingPanesRow:: Getbölmesi sayısı

```
int GetPaneCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowgetpanelist"></a><a name="getpanelist"></a> CDockingPanesRow:: Getbölmesi listesi

```
const CObList& GetPaneList() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowgetrowalignment"></a><a name="getrowalignment"></a> CDockingPanesRow:: Getrowhizalaması

```
DWORD GetRowAlignment() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowgetrowheight"></a><a name="getrowheight"></a> CDockingPanesRow:: GetRowHeight

```
int GetRowHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowgetrowoffset"></a><a name="getrowoffset"></a> CDockingPanesRow:: Getrowkayması

```
int GetRowOffset() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowgetvisiblecount"></a><a name="getvisiblecount"></a> CDockingPanesRow:: GetVisibleCount

```
virtual int GetVisibleCount();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowgetwindowrect"></a><a name="getwindowrect"></a> CDockingPanesRow:: GetWindowRect

```cpp
void GetWindowRect(CRect& rect) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *Rect*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowhaspane"></a><a name="haspane"></a> CDockingPanesRow:: HasPane

```
BOOL HasPane(CBasePane* pControlBar);
```

### <a name="parameters"></a>Parametreler

'ndaki *pControlBar*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowisempty"></a><a name="isempty"></a> CDockingPanesRow:: IsEmpty

```
virtual BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowisexclusiverow"></a><a name="isexclusiverow"></a> CDockingPanesRow:: ısexclusiverow

```
virtual BOOL IsExclusiveRow() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowishorizontal"></a><a name="ishorizontal"></a> CDockingPanesRow:: ısyatay

```
bool IsHorizontal() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowisvisible"></a><a name="isvisible"></a> CDockingPanesRow:: IsVisible

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowmove"></a><a name="move"></a> CDockingPanesRow:: Move

```
virtual void Move(int nOffset);
```

### <a name="parameters"></a>Parametreler

'ndaki *nKonum*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowmovepane"></a><a name="movepane"></a> CDockingPanesRow:: MovePane

```cpp
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

'ndaki *pControlBar*<br/>

'ndaki *ptOffset*<br/>

'ndaki *Bswapcontrolçubuklar*<br/>

'ndaki *hdwp*<br/>

'ndaki *Recttarget*<br/>

'ndaki *nKonum*<br/>

'ndaki *bilet*<br/>

'ndaki *Nabsolutoffset*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowonresizepane"></a><a name="onresizepane"></a> CDockingPanesRow:: OnResizePane

```
virtual void OnResizePane(CBasePane* pControlBar);
```

### <a name="parameters"></a>Parametreler

'ndaki *pControlBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowredrawall"></a><a name="redrawall"></a> CDockingPanesRow:: RedrawAll

```cpp
void RedrawAll();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowremovepane"></a><a name="removepane"></a> CDockingPanesRow:: RemovePane

```
virtual void RemovePane(CPane* pControlBar);
```

### <a name="parameters"></a>Parametreler

'ndaki *pControlBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowreplacepane"></a><a name="replacepane"></a> CDockingPanesRow:: ReplacePane

```
virtual BOOL ReplacePane(
    CPane* pBarOld,
    CPane* pBarNew);
```

### <a name="parameters"></a>Parametreler

'ndaki *Pbarold*<br/>

'ndaki *Pbarnew*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowrepositionpanes"></a><a name="repositionpanes"></a> CDockingPanesRow:: kayıt bölmeleri

```
virtual void RepositionPanes(
    CRect& rectNewParentBarArea,
    UINT nSide = (UINT)-1,
    BOOL bExpand = FALSE,
    int nOffset = 0);
```

### <a name="parameters"></a>Parametreler

'ndaki *Rectnewparentbararea*<br/>

'ndaki *Nsıde*<br/>

'ndaki *Bexpand*<br/>

'ndaki *nKonum*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowresize"></a><a name="resize"></a> CDockingPanesRow:: Resize

```
virtual int Resize(int nOffset);
```

### <a name="parameters"></a>Parametreler

'ndaki *nKonum*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowresizebypanedivider"></a><a name="resizebypanedivider"></a> CDockingPanesRow:: ResizeByPaneDivider

```
virtual int ResizeByPaneDivider(int /*ignored*/);
```

### <a name="parameters"></a>Parametreler

'ndaki *yoksayıldı*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowscreentoclient"></a><a name="screentoclient"></a> CDockingPanesRow:: ScreenToClient

```cpp
void ScreenToClient(CRect& rect) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *Rect*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowsetextra"></a><a name="setextra"></a> CDockingPanesRow:: SetExtra

```cpp
void SetExtra(
    int nExtraSpace,
    AFX_ROW_ALIGNMENT rowExtraAlign);
```

### <a name="parameters"></a>Parametreler

'ndaki *Nextraspace*<br/>

'ndaki *Rowextraalign*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowshowdocksiterow"></a><a name="showdocksiterow"></a> CDockingPanesRow:: Showdocksıterow

```
virtual void ShowDockSiteRow(
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>Parametreler

'ndaki *bShow*<br/>

'ndaki *bDelay*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowshowpane"></a><a name="showpane"></a> CDockingPanesRow:: ShowPane

```
virtual BOOL ShowPane(
    CPane* pControlBar,
    BOOL bShow,
    BOOL bDelay = FALSE);
```

### <a name="parameters"></a>Parametreler

'ndaki *pControlBar*<br/>

'ndaki *bShow*<br/>

'ndaki *bDelay*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockingpanesrowupdatevisiblestate"></a><a name="updatevisiblestate"></a> CDockingPanesRow:: UpdateVisibleState

```
virtual void UpdateVisibleState(BOOL bDelay);
```

### <a name="parameters"></a>Parametreler

'ndaki *bDelay*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[CDockSite sınıfı](../../mfc/reference/cdocksite-class.md)<br/>
[CPane sınıfı](../../mfc/reference/cpane-class.md)
