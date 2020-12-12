---
description: 'Daha fazla bilgi edinin: CGlobalUtils sınıfı'
title: CGlobalUtils sınıfı
ms.date: 10/18/2018
f1_keywords:
- CGlobalUtils
- AFXGLOBALUTILS/CGlobalUtils
- AFXGLOBALUTILS/CGlobalUtils::AdjustRectToWorkArea
- AFXGLOBALUTILS/CGlobalUtils::CalcExpectedDockedRect
- AFXGLOBALUTILS/CGlobalUtils::CanBeAttached
- AFXGLOBALUTILS/CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd
- AFXGLOBALUTILS/CGlobalUtils::CheckAlignment
- AFXGLOBALUTILS/CGlobalUtils::CyFromString
- AFXGLOBALUTILS/CGlobalUtils::DecimalFromString
- AFXGLOBALUTILS/CGlobalUtils::FlipRect
- AFXGLOBALUTILS/CGlobalUtils::ForceAdjustLayout
- AFXGLOBALUTILS/CGlobalUtils::GetDockingManager
- AFXGLOBALUTILS/CGlobalUtils::GetOppositeAlignment
- AFXGLOBALUTILS/CGlobalUtils::GetPaneAndAlignFromPoint
- AFXGLOBALUTILS/CGlobalUtils::GetWndIcon
- AFXGLOBALUTILS/CGlobalUtils::SetNewParent
- AFXGLOBALUTILS/CGlobalUtils::StringFromCy
- AFXGLOBALUTILS/CGlobalUtils::StringFromDecimal
helpviewer_keywords:
- CGlobalUtils [MFC], AdjustRectToWorkArea
- CGlobalUtils [MFC], CalcExpectedDockedRect
- CGlobalUtils [MFC], CanBeAttached
- CGlobalUtils [MFC], CanPaneBeInFloatingMultiPaneFrameWnd
- CGlobalUtils [MFC], CheckAlignment
- CGlobalUtils [MFC], CyFromString
- CGlobalUtils [MFC], DecimalFromString
- CGlobalUtils [MFC], FlipRect
- CGlobalUtils [MFC], ForceAdjustLayout
- CGlobalUtils [MFC], GetDockingManager
- CGlobalUtils [MFC], GetOppositeAlignment
- CGlobalUtils [MFC], GetPaneAndAlignFromPoint
- CGlobalUtils [MFC], GetWndIcon
- CGlobalUtils [MFC], SetNewParent
- CGlobalUtils [MFC], StringFromCy
- CGlobalUtils [MFC], StringFromDecimal
ms.assetid: 2c5bd1a6-f80c-4e79-a476-b4ceebabfb2f
ms.openlocfilehash: d1e2f096825d34a907afbcdb022c550b94476906
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184107"
---
# <a name="cglobalutils-class"></a>CGlobalUtils sınıfı

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

```
class CGlobalUtils
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CGlobalUtils:: AdjustRectToWorkArea](#adjustrecttoworkarea)||
|[CGlobalUtils:: CalcExpectedDockedRect](#calcexpecteddockedrect)||
|[CGlobalUtils:: Canbeekli](#canbeattached)||
|[CGlobalUtils:: Canbölmesi Beinfloatingmultikutuframewnd](#canpanebeinfloatingmultipaneframewnd)||
|[CGlobalUtils:: CheckAlignment](#checkalignment)||
|[CGlobalUtils:: CyFromString](#cyfromstring)||
|[CGlobalUtils::D ecimalFromString](#decimalfromstring)||
|[CGlobalUtils:: FlipRect](#fliprect)||
|[CGlobalUtils:: ForceAdjustLayout](#forceadjustlayout)||
|[CGlobalUtils:: GetDockingManager](#getdockingmanager)||
|[CGlobalUtils:: Getoppositehizalaması](#getoppositealignment)||
|[CGlobalUtils:: GetPaneAndAlignFromPoint](#getpaneandalignfrompoint)||
|[CGlobalUtils:: GetWndIcon](#getwndicon)||
|[CGlobalUtils:: SetNewParent](#setnewparent)||
|[CGlobalUtils:: StringFromCy](#stringfromcy)||
|[CGlobalUtils:: StringFromDecimal](#stringfromdecimal)||

## <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CGlobalUtils](../../mfc/reference/cglobalutils-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxglobalutils. h

## <a name="cglobalutilsadjustrecttoworkarea"></a><a name="adjustrecttoworkarea"></a> CGlobalUtils:: AdjustRectToWorkArea

```cpp
void AdjustRectToworkArea(
    CRect& rect,
    CRect* pRectDelta = NULL);
```

### <a name="parameters"></a>Parametreler

[in, out] *Rect*<br/>
'ndaki *ön Delta*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cglobalutilscalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a> CGlobalUtils:: CalcExpectedDockedRect

```cpp
void CalcExpectedDockedRect(
    CPaneContainerManager& barContainerManager,
    CWnd* pWndTodock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>Parametreler

'ndaki *Barcontainermanager*<br/>

'ndaki *Pwndtodock*<br/>

'ndaki *ptMouse*<br/>

dışı *rectResult*<br/>

dışı *bDrawTab*<br/>

dışı *ppTargetBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cglobalutilscanbeattached"></a><a name="canbeattached"></a> CGlobalUtils:: Canbeekli

```
BOOL CanBeAttached(CWnd* pWnd) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *pWnd*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cglobalutilscanpanebeinfloatingmultipaneframewnd"></a><a name="canpanebeinfloatingmultipaneframewnd"></a> CGlobalUtils:: Canbölmesi Beinfloatingmultikutuframewnd

```
BOOL CanPaneBeInFloatingMultiPaneFrameWnd(CWnd* pWnd) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *pWnd*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cglobalutilscheckalignment"></a><a name="checkalignment"></a> CGlobalUtils:: CheckAlignment

```
BOOL CheckAlignment(
    CPoint point,
    CBasePane* pBar,
    int nSensitivity,
    const CDockingManager* pDockManager,
    BOOL bOuterEdge,
    DWORD& dwAlignment,
    DWORD dwEnabledDockBars = CBRS_ALIGN_ANY,
    LPCRECT lpRectBounds = NULL) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *nokta*<br/>

'ndaki *pBar*<br/>

'ndaki *duyarlılık*<br/>

'ndaki *pDockManager*<br/>

'ndaki *Bukenar*<br/>

dışı *Dwhizalaması*<br/>

'ndaki *Dwenableddockçubuklar*<br/>

'ndaki *Lprectsınır*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cglobalutilscyfromstring"></a><a name="cyfromstring"></a> CGlobalUtils:: CyFromString

```
BOOL CyFromString(
    CY& cy,
    LPCTSTR psz);
```

### <a name="parameters"></a>Parametreler

dışı *Cy*<br/>

'ndaki *PSZ*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cglobalutilsdecimalfromstring"></a><a name="decimalfromstring"></a> CGlobalUtils::D ecimalFromString

```
BOOL DecimalFromString(
    DECIMAL& decimal,
    LPCTSTR psz);
```

### <a name="parameters"></a>Parametreler

dışı *ondalık*<br/>

'ndaki *PSZ*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cglobalutilsfliprect"></a><a name="fliprect"></a> CGlobalUtils:: FlipRect

```cpp
void FlipRect(
    CRect& rect,
    int nDegrees);
```

### <a name="parameters"></a>Parametreler

[in, out] *Rect*<br/>
'ndaki *Nderece*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cglobalutilsforceadjustlayout"></a><a name="forceadjustlayout"></a> CGlobalUtils:: ForceAdjustLayout

```cpp
void ForceAdjustLayout(
    CDockingManager* pDockManager,
    BOOL bForce = FALSE,
    BOOL bForceInvisible = FALSE);
```

### <a name="parameters"></a>Parametreler

[in, out] *pDockManager*<br/>

'ndaki *Bzorla*<br/>

'ndaki *Bforcegörünmez*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cglobalutilsgetdockingmanager"></a><a name="getdockingmanager"></a> CGlobalUtils:: GetDockingManager

```
CDockingManager* GetDockingManager(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

'ndaki *pWnd*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cglobalutilsgetoppositealignment"></a><a name="getoppositealignment"></a> CGlobalUtils:: Getoppositehizalaması

```
DWORD GetOppositeAlignment(DWORD dwAlign);
```

### <a name="parameters"></a>Parametreler

'ndaki *Dwalign*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cglobalutilsgetpaneandalignfrompoint"></a><a name="getpaneandalignfrompoint"></a> CGlobalUtils:: GetPaneAndAlignFromPoint

```
BOOL GetPaneAndAlignFromPoint(
    CPaneContainerManager& barContainerManager,
    CPoint pt,
    CDockablePane** ppTargetControlBar,
    DWORD& dwAlignment,
    BOOL& bTabArea,
    BOOL& bCaption);
```

### <a name="parameters"></a>Parametreler

'ndaki *Barcontainermanager*<br/>

'ndaki *PT*<br/>

dışı *ppTargetControlBar*<br/>

dışı *Dwhizalaması*<br/>

dışı *bTabArea*<br/>

dışı *bCaption*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cglobalutilsgetwndicon"></a><a name="getwndicon"></a> CGlobalUtils:: GetWndIcon

```
HICON GetWndIcon(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

'ndaki *pWnd*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cglobalutilssetnewparent"></a><a name="setnewparent"></a> CGlobalUtils:: SetNewParent

```cpp
void SetNewParent(
    CObList& lstControlBars,
    CWnd* pNewParent,
    BOOL bCheckVisibility = TRUE);
```

### <a name="parameters"></a>Parametreler

'ndaki *Lstcontrolçubuklar*<br/>

'ndaki *Pnewparent*<br/>

'ndaki *Bcheckvisibility*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cglobalutilsstringfromcy"></a><a name="stringfromcy"></a> CGlobalUtils:: StringFromCy

```
BOOL StringFromCy(
    CString& str,
    CY& cy);
```

### <a name="parameters"></a>Parametreler

dışı *Str*<br/>

'ndaki *Cy*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cglobalutilsstringfromdecimal"></a><a name="stringfromdecimal"></a> CGlobalUtils:: StringFromDecimal

```
BOOL StringFromDecimal(
    CString& str,
    DECIMAL& decimal);
```

### <a name="parameters"></a>Parametreler

dışı *Str*<br/>

'ndaki *ondalık*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
