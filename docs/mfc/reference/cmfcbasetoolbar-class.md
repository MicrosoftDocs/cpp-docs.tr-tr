---
description: 'Daha fazla bilgi edinin: CMFCBaseToolBar sınıfı'
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
ms.openlocfilehash: 37597e4cb300e0d6d16c92f105e332c18c5beda7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247923"
---
# <a name="cmfcbasetoolbar-class"></a>CMFCBaseToolBar sınıfı

Araç çubukları için temel sınıf.

## <a name="syntax"></a>Syntax

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
|`CMFCBaseToolBar::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|[CMFCBaseToolBar:: GetDockingMode](#getdockingmode)|Yerleştirme modunu döndürür. ( [CBasePane:: GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode)öğesini geçersiz kılar.)|
|[CMFCBaseToolBar:: GetMinSize](#getminsize)|Bir araç çubuğunun en küçük boyutunu döndürür. ( [CPane:: GetMinSize](../../mfc/reference/cpane-class.md#getminsize).) öğesini geçersiz kılar|
|[CMFCBaseToolBar:: OnAfterChangeParent](#onafterchangeparent)|Bölmenin üst değişikliklerinden sonra Framework tarafından çağırılır. ( [CBasePane:: OnAfterChangeParent](../../mfc/reference/cbasepane-class.md#onafterchangeparent)geçersiz kılar.)|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxbasetoolbar. h

## <a name="cmfcbasetoolbargetdockingmode"></a><a name="getdockingmode"></a> CMFCBaseToolBar:: GetDockingMode

Yerleştirme modunu döndürür.

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yerleştirme modu.

## <a name="cmfcbasetoolbargetminsize"></a><a name="getminsize"></a> CMFCBaseToolBar:: GetMinSize

Bir araç çubuğunun en küçük boyutunu döndürür.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
dışı Bir araç çubuğunun en küçük boyutu.

## <a name="cmfcbasetoolbaronafterchangeparent"></a><a name="onafterchangeparent"></a> CMFCBaseToolBar:: OnAfterChangeParent

Bölmenin üst değişikliklerinden sonra Framework tarafından çağırılır.

```
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```

### <a name="parameters"></a>Parametreler

*pWndOldParent*<br/>
'ndaki Önceki üst pencereye yönelik bir işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
