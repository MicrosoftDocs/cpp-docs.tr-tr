---
title: CTreeView sınıfı
ms.date: 11/04/2016
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
ms.openlocfilehash: fec8379a3944d981672754274f50dd4e60f71b61
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288876"
---
# <a name="ctreeview-class"></a>CTreeView sınıfı

Ağaç denetimi ve, basitleştirir [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), MFC'nin belge / görünüm mimarisi ile ağaç denetimi işlevini kapsayan sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CTreeView : public CCtrlView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CTreeView::CTreeView](#ctreeview)|Oluşturur bir `CTreeView` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTreeView::GetTreeCtrl](#gettreectrl)|Görünüm ile ilişkilendirilen ağaç denetimi döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu mimari hakkında daha fazla bilgi için genel bakış için bkz. [CView](../../mfc/reference/cview-class.md) sınıfı ve burada bahsedilen çapraz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CTreeView`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcview.h

##  <a name="ctreeview"></a>  CTreeView::CTreeView

Oluşturur bir `CTreeView` nesne.

```
CTreeView();
```

##  <a name="gettreectrl"></a>  CTreeView::GetTreeCtrl

Ağaç denetimi görünüm ile ilişkilendirilen bir başvuru döndürür.

```
CTreeCtrl& GetTreeCtrl() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[CTreeCtrl Sınıfı](../../mfc/reference/ctreectrl-class.md)
