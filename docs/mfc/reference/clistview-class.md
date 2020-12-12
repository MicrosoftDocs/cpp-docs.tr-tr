---
description: 'Daha fazla bilgi edinin: CListView sınıfı'
title: CListView sınıfı
ms.date: 11/04/2016
f1_keywords:
- CListView
- AFXCVIEW/CListView
- AFXCVIEW/CListView::CListView
- AFXCVIEW/CListView::GetListCtrl
- AFXCVIEW/CListView::RemoveImageList
helpviewer_keywords:
- CListView [MFC], CListView
- CListView [MFC], GetListCtrl
- CListView [MFC], RemoveImageList
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
ms.openlocfilehash: 5576a0997c84e8f5639911a1120a6645e720a7cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259571"
---
# <a name="clistview-class"></a>CListView sınıfı

, MFC 'nin belge görünümü mimarisi ile List-Control işlevselliğini kapsülleyen sınıf olan [CListCtrl](../../mfc/reference/clistctrl-class.md)' i ve liste denetiminin kullanımını basitleştirir.

## <a name="syntax"></a>Syntax

```
class CListView : public CCtrlView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CListView:: Clienstview](#clistview)|Bir `CListView` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CListView:: GetListCtrl](#getlistctrl)|Görünümle ilişkili liste denetimini döndürür.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CListView:: Removeımagelist](#removeimagelist)|Belirtilen görüntü listesini liste görünümünden kaldırır.|

## <a name="remarks"></a>Açıklamalar

Bu mimari hakkında daha fazla bilgi için bkz. [CView](../../mfc/reference/cview-class.md) sınıfı için genel bakış ve burada alıntı yapılan çapraz başvurular.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CListView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcview. h

## <a name="clistviewclistview"></a><a name="clistview"></a> CListView:: Clienstview

Bir `CListView` nesnesi oluşturur.

```
CListView();
```

## <a name="clistviewgetlistctrl"></a><a name="getlistctrl"></a> CListView:: GetListCtrl

Görünümle ilişkili liste denetimine bir başvuru almak için bu üye işlevini çağırın.

```
CListCtrl& GetListCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görünümle ilişkili liste denetimine başvuru.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCListView#7](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]

## <a name="clistviewremoveimagelist"></a><a name="removeimagelist"></a> CListView:: Removeımagelist

Belirtilen görüntü listesini liste görünümünden kaldırır.

```cpp
void RemoveImageList(int nImageList);
```

### <a name="parameters"></a>Parametreler

*Nımagelist*<br/>
Kaldırılacak görüntünün sıfır tabanlı dizini.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek ROWLIST](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)
