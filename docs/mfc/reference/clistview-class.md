---
title: CListView Sınıfı
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
ms.openlocfilehash: ae1a76e4cdd052ff44dcbd69d467c51741bcc2ff
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370145"
---
# <a name="clistview-class"></a>CListView Sınıfı

Liste denetiminin ve MFC'nin belge görünümü mimarisiyle liste denetimi işlevini kapsayan sınıf [Olan CListCtrl'in](../../mfc/reference/clistctrl-class.md)kullanımını kolaylaştırır.

## <a name="syntax"></a>Sözdizimi

```
class CListView : public CCtrlView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CListView::CListView](#clistview)|Bir `CListView` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CListView::GetListCtrl](#getlistctrl)|Görünümle ilişkili liste denetimini döndürür.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CListView::RemoveImageList](#removeimagelist)|Belirtilen resim listesini liste görünümünden kaldırır.|

## <a name="remarks"></a>Açıklamalar

Bu mimari hakkında daha fazla bilgi için [CView](../../mfc/reference/cview-class.md) sınıfına genel bakışve burada atıfta bulunulan çapraz referanslar bölümüne bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cview](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CListView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcview.h

## <a name="clistviewclistview"></a><a name="clistview"></a>CListView::CListView

Bir `CListView` nesne inşa eder.

```
CListView();
```

## <a name="clistviewgetlistctrl"></a><a name="getlistctrl"></a>CListView::GetListCtrl

Görünümle ilişkili liste denetimine başvuru almak için bu üye işlevini arayın.

```
CListCtrl& GetListCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görünümle ilişkili liste denetimine bir başvuru.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCListView#7](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]

## <a name="clistviewremoveimagelist"></a><a name="removeimagelist"></a>CListView::RemoveImageList

Belirtilen resim listesini liste görünümünden kaldırır.

```
void RemoveImageList(int nImageList);
```

### <a name="parameters"></a>Parametreler

*nImageList*<br/>
Kaldırılacak görüntünün sıfır tabanlı dizini.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek ROWLIST](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)
