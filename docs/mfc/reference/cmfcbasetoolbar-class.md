---
title: CMFCBaseToolBar Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCBaseToolBar
- AFXBASETOOLBAR/CMFCBaseToolBar
- AFXBASETOOLBAR/CMFCBaseToolBar::GetDockingMode
- AFXBASETOOLBAR/CMFCBaseToolBar::GetMinSize
- AFXBASETOOLBAR/CMFCBaseToolBar::OnAfterChangeParent
helpviewer_keywords:
- CMFCBaseToolBar [MFC], GetDockingMode
- CMFCBaseToolBar [MFC], GetMinSize
- CMFCBaseToolBar [MFC], OnAfterChangeParent
ms.assetid: 5d79206d-55e4-46f8-b1b8-042e34d7f9da
ms.openlocfilehash: 027fe8569ff133bb3f348c9d0607f19c6d778c4e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367836"
---
# <a name="cmfcbasetoolbar-class"></a>CMFCBaseToolBar Sınıfı

Araç çubukları için taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CMFCBaseToolBar : public CPane
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMFCBaseToolBar::CMFCBaseToolBar`|Varsayılan oluşturucu.|
|`CMFCBaseToolBar::~CMFCBaseToolBar`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|`CMFCBaseToolBar::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|[CMFCBaseToolBar::GetDockingMode](#getdockingmode)|Yerleştirme modunu döndürür. [(CBasePane geçersiz kılar::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).)|
|[CMFCBaseToolBar::GetMinSize](#getminsize)|Araç çubuğunun minimum boyutunu döndürür. (CPane geçersiz [kılar::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|
|[CMFCBaseToolBar::OnafterchangeParent](#onafterchangeparent)|Bölmenin üst öğesi değiştikten sonra çerçeve tarafından çağrılır. [(Overrides CBasePane::OnAfterChangeParent](../../mfc/reference/cbasepane-class.md#onafterchangeparent).)|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[Cpane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxbasetoolbar.h

## <a name="cmfcbasetoolbargetdockingmode"></a><a name="getdockingmode"></a>CMFCBaseToolBar::GetDockingMode

Yerleştirme modunu döndürür.

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yerleştirme modu.

## <a name="cmfcbasetoolbargetminsize"></a><a name="getminsize"></a>CMFCBaseToolBar::GetMinSize

Araç çubuğunun minimum boyutunu döndürür.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
[çıkış] Araç çubuğunun minimum boyutu.

## <a name="cmfcbasetoolbaronafterchangeparent"></a><a name="onafterchangeparent"></a>CMFCBaseToolBar::OnafterchangeParent

Bölmenin üst öğesi değiştikten sonra çerçeve tarafından çağrılır.

```
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```

### <a name="parameters"></a>Parametreler

*pWndOldParent*<br/>
[içinde] Önceki üst pencereiçin bir işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
