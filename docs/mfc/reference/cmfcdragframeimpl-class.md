---
description: 'Daha fazla bilgi edinin: CMFCDragFrameImpl sınıfı'
title: CMFCDragFrameImpl sınıfı
ms.date: 10/18/2018
f1_keywords:
- CMFCDragFrameImpl
helpviewer_keywords:
- CMFCDragFrameImpl class [MFC]
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
ms.openlocfilehash: 9885b750ace86d11ca573f23c7ee1c03d8926921
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294060"
---
# <a name="cmfcdragframeimpl-class"></a>CMFCDragFrameImpl sınıfı

`CMFCDragFrameImpl`Sınıfı, Kullanıcı Standart yerleştirme modunda bir bölme sürüklediğinde görüntülenen sürükleme dikdörtgenini çizer.
Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

```
class CMFCDragFrameImpl
```

## <a name="remarks"></a>Açıklamalar

Bu sınıfın bir nesnesi her [CPane sınıfı](../../mfc/reference/cpane-class.md) nesnesine katıştırılır. Bu nedenle, yöntemini kullanan her bölme `CanFloat` Kullanıcı nesneyi sürüklediğinde bir sürükle dikdörtgeni görüntüler.

Sürükleme dikdörtgeninin kalınlığını, [AFX_GLOBAL_DATA:: m_nDragFrameThicknessFloat](afx-global-data-structure.md#m_ndragframethicknessfloat) ve [AFX_GLOBAL_DATA:: m_nDragFrameThicknessDock](afx-global-data-structure.md#m_ndragframethicknessdock)kullanarak kontrol edebilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdragframeımpl. h

## <a name="cmfcdragframeimplenddrawdragframe"></a><a name="enddrawdragframe"></a> CMFCDragFrameImpl:: EndDrawDragFrame

```cpp
void EndDrawDragFrame(BOOL bClearInternalRects = TRUE);
```

### <a name="parameters"></a>Parametreler

'ndaki *Bclearınternalrects*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdragframeimplinit"></a><a name="init"></a> CMFCDragFrameImpl:: Init

```cpp
void Init(CWnd* pDraggedWnd);
```

### <a name="parameters"></a>Parametreler

'ndaki *Pdraggedwnd*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdragframeimplmovedragframe"></a><a name="movedragframe"></a> CMFCDragFrameImpl:: MoveDragFrame

```cpp
void MoveDragFrame(BOOL bForceMove = FALSE);
```

### <a name="parameters"></a>Parametreler

'ndaki *Bforcemove*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdragframeimplplacetabpredocking"></a><a name="placetabpredocking"></a> CMFCDragFrameImpl::P laceTabPreDocking

```cpp
void PlaceTabPreDocking(
    CBaseTabbedPane* pTabbedBar,
    BOOL bFirstTime);

void PlaceTabPreDocking(CWnd* pCBarToPlaceOn);
```

### <a name="parameters"></a>Parametreler

'ndaki *Ptabbedbar*<br/>

'ndaki *Bfirsttime*<br/>

'ndaki *pCBarToPlaceOn*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdragframeimplremovetabpredocking"></a><a name="removetabpredocking"></a> CMFCDragFrameImpl:: RemoveTabPreDocking

```cpp
void RemoveTabPreDocking(CDockablePane* pOldTargetBar = NULL);
```

### <a name="parameters"></a>Parametreler

'ndaki *Poldtargetbar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdragframeimplresetstate"></a><a name="resetstate"></a> CMFCDragFrameImpl:: ResetState

```cpp
void ResetState();
```

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CPane sınıfı](../../mfc/reference/cpane-class.md)
