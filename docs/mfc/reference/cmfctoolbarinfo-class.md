---
title: CMFCToolBarInfo Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo::m_uiColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuResID
helpviewer_keywords:
- CMFCToolBarInfo [MFC], m_uiColdResID
- CMFCToolBarInfo [MFC], m_uiDisabledResID
- CMFCToolBarInfo [MFC], m_uiHotResID
- CMFCToolBarInfo [MFC], m_uiLargeColdResID
- CMFCToolBarInfo [MFC], m_uiLargeDisabledResID
- CMFCToolBarInfo [MFC], m_uiLargeHotResID
- CMFCToolBarInfo [MFC], m_uiMenuDisabledResID
- CMFCToolBarInfo [MFC], m_uiMenuResID
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
ms.openlocfilehash: 593d1665751f7322fc2a9cee307620df88d46876
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376187"
---
# <a name="cmfctoolbarinfo-class"></a>CMFCToolBarInfo Sınıfı

Çeşitli eyaletlerdeki araç çubuğu görüntülerinin kaynak eklerini içerir. `CMFCToolBarInfo`CMFCToolBar parametresi olarak kullanılan bir yardımcı [sınıftır::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) yöntemi.

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolBarInfo
```

## <a name="members"></a>Üyeler

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolBarInfo::m_uiColdResID](#m_uicoldresid)|Normal (soğuk) araç çubuğu görüntüleri içeren araç çubuğu bit eşlemi kaynak kimliği.|
|[CMFCToolBarInfo::m_uiDisabledResID](#m_uidisabledresid)|Devre dışı bırakılmış araç çubuğu görüntüleri içeren araç çubuğu bit eşlemi kaynak kimliği.|
|[CMFCToolBarInfo::m_uiHotResID](#m_uihotresid)|Seçili (sıcak) araç çubuğu görüntüleri içeren araç çubuğu bit eşlemi kaynak kimliği.|
|[CMFCToolBarInfo::m_uiLargeColdResID](#m_uilargecoldresid)|Büyük, normal araç çubuğu görüntüleri içeren araç çubuğu bit eşlemi kaynak kimliği.|
|[CMFCToolBarInfo::m_uiLargeDisabledResID](#m_uilargedisabledresid)|Büyük, devre dışı araç çubuğu görüntüleri içeren araç çubuğu bit eşlemi kaynak kimliği.|
|[CMFCToolBarInfo::m_uiLargeHotResID](#m_uilargehotresid)|Büyük, seçili araç çubuğu görüntüleri içeren araç çubuğu bit eşlemi kaynak kimliği.|
|[CMFCToolBarInfo::m_uiMenuDisabledResID](#m_uimenudisabledresid)|Devre dışı bırakılmış menü görüntüleri içeren araç çubuğu bit eşlemi kaynak kimliği.|
|[CMFCToolBarInfo::m_uiMenuResID](#m_uimenuresid)|Menü görüntüleri içeren araç çubuğu biteşsinin kaynak kimliği.|

## <a name="remarks"></a>Açıklamalar

Tam araç çubuğu bit eşlemi, sabit boyuttaki küçük araç çubuğu görüntülerinden (düğmeler) oluşur. `CMFCToolBarInfo` Bir nesnede depolanan her kaynak kimliği, tek bir durumda (örneğin, seçili, devre dışı bırakılmış, büyük veya menü görüntüleri) tam araç çubuğu görüntüleri kümesini içeren bir bit eşlemidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbar.h

## <a name="cmfctoolbarinfom_uicoldresid"></a><a name="m_uicoldresid"></a>CMFCToolBarInfo::m_uiColdResID

Araç çubuğunun tüm normal düğme görüntüleri için bir kaynak kimliği belirtir.

```
UINT m_uiColdResID;
```

## <a name="cmfctoolbarinfom_uidisabledresid"></a><a name="m_uidisabledresid"></a>CMFCToolBarInfo::m_uiDisabledResID

Araç çubuğunun düğme kullanılamayan görüntüleri için bir kaynak kimliği belirtir.

```
UINT m_uiDisabledResID;
```

## <a name="cmfctoolbarinfom_uihotresid"></a><a name="m_uihotresid"></a>CMFCToolBarInfo::m_uiHotResID

Araç çubuğunun vurgulanan tüm düğme görüntüleri için bir kaynak kimliği belirtir.

```
UINT m_uiHotResID
```

## <a name="cmfctoolbarinfom_uilargecoldresid"></a><a name="m_uilargecoldresid"></a>CMFCToolBarInfo::m_uiLargeColdResID

Araç çubuğunun tüm büyük normal düğme görüntüleri için bir kaynak kimliği belirtir.

```
UINT m_uiLargeColdResID
```

## <a name="cmfctoolbarinfom_uilargedisabledresid"></a><a name="m_uilargedisabledresid"></a>CMFCToolBarInfo::m_uiLargeDisabledResID

Araç çubuğunun tüm büyük devre dışı bırakılmış düğme görüntüleri için bir kaynak kimliği belirtir.

```
UINT m_uiLargeDisabledResID;
```

## <a name="cmfctoolbarinfom_uilargehotresid"></a><a name="m_uilargehotresid"></a>CMFCToolBarInfo::m_uiLargeHotResID

Araç çubuğunun tüm büyük vurgulanmış görüntüleri için bir kaynak kimliği belirtir.

```
UINT m_uiLargeHotResID;
```

## <a name="cmfctoolbarinfom_uimenudisabledresid"></a><a name="m_uimenudisabledresid"></a>CMFCToolBarInfo::m_uiMenuDisabledResID

Araç çubuğunun komut kullanılamayan görüntüleri için bir kaynak kimliği belirtir.

```
UINT m_uiMenuDisabledResID;
```

## <a name="cmfctoolbarinfom_uimenuresid"></a><a name="m_uimenuresid"></a>CMFCToolBarInfo::m_uiMenuResID

Araç çubuğunun tüm normal menü öğesi görüntüleri için kaynak kimliği belirtir.

```
UINT m_uiMenuResID;
```

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)
