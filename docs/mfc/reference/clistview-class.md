---
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
ms.openlocfilehash: 698e37b2853a2ca3698ee0a426c8ded688c99c58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62296663"
---
# <a name="clistview-class"></a>CListView sınıfı

Liste denetimi ve, basitleştirir [CListCtrl](../../mfc/reference/clistctrl-class.md), MFC'nin belge / görünüm mimarisi ile liste denetimi işlevini kapsayan sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CListView : public CCtrlView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CListView::CListView](#clistview)|Oluşturur bir `CListView` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CListView::GetListCtrl](#getlistctrl)|Görünüm ile ilişkilendirilen liste denetimini döndürür.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CListView::RemoveImageList](#removeimagelist)|Belirtilen görüntü listesi listesinde görünümden kaldırır.|

## <a name="remarks"></a>Açıklamalar

Bu mimari hakkında daha fazla bilgi için genel bakış için bkz. [CView](../../mfc/reference/cview-class.md) sınıfı ve burada bahsedilen çapraz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CListView`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcview.h

##  <a name="clistview"></a>  CListView::CListView

Oluşturur bir `CListView` nesne.

```
CListView();
```

##  <a name="getlistctrl"></a>  CListView::GetListCtrl

Görünüm ile ilişkilendirilen liste denetimi bir başvuru almak için bu üye işlevini çağırın.

```
CListCtrl& GetListCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görünüm ile ilişkilendirilen liste denetimi başvuru.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCListView#7](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]

##  <a name="removeimagelist"></a>  CListView::RemoveImageList

Belirtilen görüntü listesi listesinde görünümden kaldırır.

```
void RemoveImageList(int nImageList);
```

### <a name="parameters"></a>Parametreler

*nImageList*<br/>
Görüntüyü kaldırmak için sıfır tabanlı dizini.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek ROWLIST](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)
