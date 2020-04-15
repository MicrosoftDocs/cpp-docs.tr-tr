---
title: CTreeView Sınıfı
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
ms.openlocfilehash: 2ef93152c83d3bbec2b89ada0596ee612b24701b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373290"
---
# <a name="ctreeview-class"></a>CTreeView Sınıfı

MFC'nin belge görünümü mimarisiyle ağaç denetimi işlevini kapsülleyen sınıf [Olan CTreeCtrl'in](../../mfc/reference/ctreectrl-class.md)ve ağaç denetiminin kullanımını kolaylaştırır.

## <a name="syntax"></a>Sözdizimi

```
class CTreeView : public CCtrlView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CTreeView::CTreeView](#ctreeview)|Bir `CTreeView` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CTreeView::GetTreeCtrl](#gettreectrl)|Görünümle ilişkili ağaç denetimini döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu mimari hakkında daha fazla bilgi için [CView](../../mfc/reference/cview-class.md) sınıfına genel bakışve burada atıfta bulunulan çapraz referanslar bölümüne bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cview](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CTreeView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcview.h

## <a name="ctreeviewctreeview"></a><a name="ctreeview"></a>CTreeView::CTreeView

Bir `CTreeView` nesne inşa eder.

```
CTreeView();
```

## <a name="ctreeviewgettreectrl"></a><a name="gettreectrl"></a>CTreeView::GetTreeCtrl

Görünümle ilişkili ağaç denetimine bir başvuru verir.

```
CTreeCtrl& GetTreeCtrl() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[CTreeCtrl Sınıfı](../../mfc/reference/ctreectrl-class.md)
