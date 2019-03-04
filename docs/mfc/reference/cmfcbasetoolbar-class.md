---
title: CMFCBaseToolBar sınıfı
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
ms.openlocfilehash: 7a6ccdaf3d78b9973505dd4e90ca76f671fce889
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265385"
---
# <a name="cmfcbasetoolbar-class"></a>CMFCBaseToolBar sınıfı

Araç çubukları için temel sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CMFCBaseToolBar : public CPane
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMFCBaseToolBar::CMFCBaseToolBar`|Varsayılan Oluşturucu.|
|`CMFCBaseToolBar::~CMFCBaseToolBar`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCBaseToolBar::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|
|[CMFCBaseToolBar::GetDockingMode](#getdockingmode)|Yerleştirme modunu döndürür. (Geçersiz kılmaları [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).)|
|[CMFCBaseToolBar::GetMinSize](#getminsize)|En az bir araç çubuğu boyutunu döndürür. (Geçersiz kılmaları [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|
|[CMFCBaseToolBar::OnAfterChangeParent](#onafterchangeparent)|Bölmedeki üst değiştikten sonra framework tarafından çağırılır. (Geçersiz kılmaları [CBasePane::OnAfterChangeParent](../../mfc/reference/cbasepane-class.md#onafterchangeparent).)|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxbasetoolbar.h

##  <a name="getdockingmode"></a>  CMFCBaseToolBar::GetDockingMode

Yerleştirme modunu döndürür.

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yerleştirme modu.

##  <a name="getminsize"></a>  CMFCBaseToolBar::GetMinSize

En az bir araç çubuğu boyutunu döndürür.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
[out] Araç çubuğu için en küçük boyut.

##  <a name="onafterchangeparent"></a>  CMFCBaseToolBar::OnAfterChangeParent

Bölmedeki üst değiştikten sonra framework tarafından çağırılır.

```
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```

### <a name="parameters"></a>Parametreler

*pWndOldParent*<br/>
[in] Önceki üst penceresine bir işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
