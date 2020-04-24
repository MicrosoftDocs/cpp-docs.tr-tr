---
title: CMFCDragFrameImpl Sınıfı
ms.date: 10/18/2018
f1_keywords:
- CMFCDragFrameImpl
helpviewer_keywords:
- CMFCDragFrameImpl class [MFC]
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
ms.openlocfilehash: 527fd089962e05c44a7e47b1ae52345116da4470
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752447"
---
# <a name="cmfcdragframeimpl-class"></a>CMFCDragFrameImpl Sınıfı

Sınıf, `CMFCDragFrameImpl` kullanıcı standart dock modunda bir bölme sürüklediğinde görünen sürükleme dikdörtgenini çizer.
Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDragFrameImpl
```

## <a name="remarks"></a>Açıklamalar

Bu sınıfın bir nesnesi her [CPane Sınıfı](../../mfc/reference/cpane-class.md) nesnesine katıştırılır. Bu nedenle, `CanFloat` yöntemi kullanan her bölme, kullanıcı sürüncemede kaldığında bir sürükleme dikdörtgeni görüntüler.

[AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](afx-global-data-structure.md#m_ndragframethicknessfloat) ve [AFX_GLOBAL_DATA::m_nDragFrameThicknessDock'](afx-global-data-structure.md#m_ndragframethicknessdock)yi kullanarak sürükleme dikdörtgeninin kalınlığını kontrol edebilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdragframeimpl.h

## <a name="cmfcdragframeimplenddrawdragframe"></a><a name="enddrawdragframe"></a>CMFCDragFrameImpl::EndDrawDragFrame

```cpp
void EndDrawDragFrame(BOOL bClearInternalRects = TRUE);
```

### <a name="parameters"></a>Parametreler

[içinde] *bClearInternalRects*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdragframeimplinit"></a><a name="init"></a>CMFCDragFrameImpl::Init

```cpp
void Init(CWnd* pDraggedWnd);
```

### <a name="parameters"></a>Parametreler

[içinde] *pDraggedWnd*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdragframeimplmovedragframe"></a><a name="movedragframe"></a>CMFCDragFrameImpl::MoveDragFrame

```cpp
void MoveDragFrame(BOOL bForceMove = FALSE);
```

### <a name="parameters"></a>Parametreler

[içinde] *bForceMove*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdragframeimplplacetabpredocking"></a><a name="placetabpredocking"></a>CMFCDragFrameImpl::PlaceTabPreDocking

```cpp
void PlaceTabPreDocking(
    CBaseTabbedPane* pTabbedBar,
    BOOL bFirstTime);

void PlaceTabPreDocking(CWnd* pCBarToPlaceOn);
```

### <a name="parameters"></a>Parametreler

[içinde] *pTabbedBar*<br/>

[içinde] *bFirstTime*<br/>

[içinde] *pCBarToPlaceOn*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdragframeimplremovetabpredocking"></a><a name="removetabpredocking"></a>CMFCDragFrameImpl::RemoveTabPreDocking

```cpp
void RemoveTabPreDocking(CDockablePane* pOldTargetBar = NULL);
```

### <a name="parameters"></a>Parametreler

[içinde] *pOldTargetBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdragframeimplresetstate"></a><a name="resetstate"></a>CMFCDragFrameImpl::ResetState

```cpp
void ResetState();
```

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CPane Sınıfı](../../mfc/reference/cpane-class.md)
