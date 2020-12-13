---
description: 'Daha fazla bilgi edinin: CMFCToolBarInfo sınıfı'
title: CMFCToolBarInfo sınıfı
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
ms.openlocfilehash: 9b85ef4f39c8b42c35975a15836a21e7cc6dd6b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331707"
---
# <a name="cmfctoolbarinfo-class"></a>CMFCToolBarInfo sınıfı

Çeşitli durumlarda Toolbar görüntülerinin kaynak kimliklerini içerir. `CMFCToolBarInfo` , [CMFCToolBar:: LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) yönteminin parametresi olarak kullanılan bir yardımcı sınıftır.

## <a name="syntax"></a>Syntax

```
class CMFCToolBarInfo
```

## <a name="members"></a>Üyeler

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarInfo:: m_uiColdResID](#m_uicoldresid)|Normal (soğuk) araç çubuğu görüntülerini içeren Toolbar bit eşlemin kaynak KIMLIĞI.|
|[CMFCToolBarInfo:: m_uiDisabledResID](#m_uidisabledresid)|Devre dışı araç çubuğu görüntülerini içeren Toolbar bit eşlemin kaynak KIMLIĞI.|
|[CMFCToolBarInfo:: m_uiHotResID](#m_uihotresid)|Seçilen (sık kullanılan) araç çubuğu görüntülerini içeren Toolbar bit eşlemin kaynak KIMLIĞI.|
|[CMFCToolBarInfo:: m_uiLargeColdResID](#m_uilargecoldresid)|Büyük, normal araç çubuğu görüntülerini içeren Toolbar bit eşlemin kaynak KIMLIĞI.|
|[CMFCToolBarInfo:: m_uiLargeDisabledResID](#m_uilargedisabledresid)|Büyük, devre dışı araç çubuğu görüntülerini içeren Toolbar bit eşlemin kaynak KIMLIĞI.|
|[CMFCToolBarInfo:: m_uiLargeHotResID](#m_uilargehotresid)|Büyük, seçili araç çubuğu görüntülerini içeren Toolbar bit eşlemin kaynak KIMLIĞI.|
|[CMFCToolBarInfo:: m_uiMenuDisabledResID](#m_uimenudisabledresid)|Devre dışı menü görüntülerini içeren Toolbar bit eşlemin kaynak KIMLIĞI.|
|[CMFCToolBarInfo:: m_uiMenuResID](#m_uimenuresid)|Menü görüntülerini içeren Toolbar bit eşlemin kaynak KIMLIĞI.|

## <a name="remarks"></a>Açıklamalar

Tam bir araç çubuğu bit eşlem, sabit boyuttaki küçük araç çubuğu görüntülerinden (düğmeler) oluşur. Bir nesne içinde depolanan her kaynak KIMLIĞI `CMFCToolBarInfo` , tek bir durumda araç çubuğu görüntülerinin tam kümesini içeren bir bit eşlemdir (örneğin, seçili, devre dışı, büyük veya menü görüntüleri).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbar. h

## <a name="cmfctoolbarinfom_uicoldresid"></a><a name="m_uicoldresid"></a> CMFCToolBarInfo:: m_uiColdResID

Bir araç çubuğunun tüm normal düğme görüntüleri için bir kaynak KIMLIĞI belirtir.

```
UINT m_uiColdResID;
```

## <a name="cmfctoolbarinfom_uidisabledresid"></a><a name="m_uidisabledresid"></a> CMFCToolBarInfo:: m_uiDisabledResID

Bir araç çubuğunun düğme için kullanılamayan görüntülerinin kaynak KIMLIĞINI belirtir.

```
UINT m_uiDisabledResID;
```

## <a name="cmfctoolbarinfom_uihotresid"></a><a name="m_uihotresid"></a> CMFCToolBarInfo:: m_uiHotResID

Bir araç çubuğunun tüm vurgulanmış düğme görüntülerinin kaynak KIMLIĞINI belirtir.

```
UINT m_uiHotResID
```

## <a name="cmfctoolbarinfom_uilargecoldresid"></a><a name="m_uilargecoldresid"></a> CMFCToolBarInfo:: m_uiLargeColdResID

Bir araç çubuğunun tüm büyük normal düğme görüntüleri için bir kaynak KIMLIĞI belirtir.

```
UINT m_uiLargeColdResID
```

## <a name="cmfctoolbarinfom_uilargedisabledresid"></a><a name="m_uilargedisabledresid"></a> CMFCToolBarInfo:: m_uiLargeDisabledResID

Bir araç çubuğunun tüm büyük devre dışı düğme görüntüleri için bir kaynak KIMLIĞI belirtir.

```
UINT m_uiLargeDisabledResID;
```

## <a name="cmfctoolbarinfom_uilargehotresid"></a><a name="m_uilargehotresid"></a> CMFCToolBarInfo:: m_uiLargeHotResID

Bir araç çubuğunun tüm büyük vurgulanmış görüntülerinin kaynak KIMLIĞINI belirtir.

```
UINT m_uiLargeHotResID;
```

## <a name="cmfctoolbarinfom_uimenudisabledresid"></a><a name="m_uimenudisabledresid"></a> CMFCToolBarInfo:: m_uiMenuDisabledResID

Bir araç çubuğunun komut için kullanılamayan görüntülerinin kaynak KIMLIĞINI belirtir.

```
UINT m_uiMenuDisabledResID;
```

## <a name="cmfctoolbarinfom_uimenuresid"></a><a name="m_uimenuresid"></a> CMFCToolBarInfo:: m_uiMenuResID

Bir araç çubuğunun tüm normal menü öğesi görüntüleri için bir kaynak KIMLIĞI belirtir.

```
UINT m_uiMenuResID;
```

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)
