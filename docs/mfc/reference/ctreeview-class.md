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
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421431"
---
# <a name="ctreeview-class"></a>CTreeView sınıfı

, MFC 'nin belge görünümü mimarisi ile ağaç denetimi işlevselliğini kapsülleyen sınıf olan [Ctreecp 'nin ve Ctreecp](../../mfc/reference/ctreectrl-class.md)kullanımını basitleştirir.

## <a name="syntax"></a>Sözdizimi

```
class CTreeView : public CCtrlView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CTreeView:: CTreeView](#ctreeview)|`CTreeView` nesnesi oluşturur.|

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
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

##  <a name="ctreeview"></a>CTreeView:: CTreeView

`CTreeView` nesnesi oluşturur.

```
CTreeView();
```

##  <a name="gettreectrl"></a>CTreeView:: Gettreeci

Görünümle ilişkili ağaç denetimine bir başvuru döndürür.

```
CTreeCtrl& GetTreeCtrl() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[CTreeCtrl Sınıfı](../../mfc/reference/ctreectrl-class.md)
