---
description: 'Daha fazla bilgi edinin: CTreeView sınıfı'
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
ms.openlocfilehash: 3e50f912f03d5214e8ec238844b3288691a4f326
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318526"
---
# <a name="ctreeview-class"></a>CTreeView sınıfı

, MFC 'nin belge görünümü mimarisi ile ağaç denetimi işlevselliğini kapsülleyen sınıf olan [Ctreecp 'nin ve Ctreecp](../../mfc/reference/ctreectrl-class.md)kullanımını basitleştirir.

## <a name="syntax"></a>Syntax

```
class CTreeView : public CCtrlView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CTreeView:: CTreeView](#ctreeview)|Bir `CTreeView` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTreeView:: Gettreeci](#gettreectrl)|Görünümle ilişkili ağaç denetimini döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu mimari hakkında daha fazla bilgi için bkz. [CView](../../mfc/reference/cview-class.md) sınıfı için genel bakış ve burada alıntı yapılan çapraz başvurular.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CTreeView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcview. h

## <a name="ctreeviewctreeview"></a><a name="ctreeview"></a> CTreeView:: CTreeView

Bir `CTreeView` nesnesi oluşturur.

```
CTreeView();
```

## <a name="ctreeviewgettreectrl"></a><a name="gettreectrl"></a> CTreeView:: Gettreeci

Görünümle ilişkili ağaç denetimine bir başvuru döndürür.

```
CTreeCtrl& GetTreeCtrl() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CView sınıfı](../../mfc/reference/cview-class.md)<br/>
[CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Ctreeckclass sınıfı](../../mfc/reference/ctreectrl-class.md)
