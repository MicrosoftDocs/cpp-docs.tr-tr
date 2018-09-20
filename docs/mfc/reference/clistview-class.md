---
title: CListView sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CListView
- AFXCVIEW/CListView
- AFXCVIEW/CListView::CListView
- AFXCVIEW/CListView::GetListCtrl
- AFXCVIEW/CListView::RemoveImageList
dev_langs:
- C++
helpviewer_keywords:
- CListView [MFC], CListView
- CListView [MFC], GetListCtrl
- CListView [MFC], RemoveImageList
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5fbb9561111a75011f934aeb0ce972829132cb87
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423409"
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

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek ROWLIST](../../visual-cpp-samples.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)
