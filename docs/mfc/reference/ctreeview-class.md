---
title: CTreeView sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
dev_langs:
- C++
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a760e567718ad7a485ebe469903c7cbd566daccc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375404"
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

## <a name="see-also"></a>Ayrıca Bkz.

[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[CTreeCtrl Sınıfı](../../mfc/reference/ctreectrl-class.md)
