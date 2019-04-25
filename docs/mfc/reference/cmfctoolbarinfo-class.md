---
title: Cmfctoolbarınfo sınıfı
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
ms.openlocfilehash: b2f8af439a2534f24cdba9b0ccdb12b150db6d0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62217819"
---
# <a name="cmfctoolbarinfo-class"></a>Cmfctoolbarınfo sınıfı

Kaynak araç çubuğu görüntülerinin çeşitli durumlarda kimliklerini içerir. `CMFCToolBarInfo` bir parametre olarak kullanılan bir yardımcı sınıftır [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) yöntemi.

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolBarInfo
```

## <a name="members"></a>Üyeler

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarInfo::m_uiColdResID](#m_uicoldresid)|Normal (durağan) araç çubuğu görüntülerini içeren araç çubuğu bit eşlemi kaynak kimliği.|
|[CMFCToolBarInfo::m_uiDisabledResID](#m_uidisabledresid)|Devre dışı bırakılmış bir araç çubuğu görüntülerini içeren araç çubuğu bit eşlemi kaynak kimliği.|
|[CMFCToolBarInfo::m_uiHotResID](#m_uihotresid)|Seçili (etkin) araç çubuğu görüntülerini içeren araç çubuğu bit eşlemi kaynak kimliği.|
|[CMFCToolBarInfo::m_uiLargeColdResID](#m_uilargecoldresid)|Büyük, normal bir araç çubuğu görüntülerini içeren araç çubuğu bit eşlemi kaynak kimliği.|
|[CMFCToolBarInfo::m_uiLargeDisabledResID](#m_uilargedisabledresid)|Büyük içeren araç çubuğu bit eşlemi Kaynak Kimliğine araç çubuğu görüntülerini devre dışı.|
|[CMFCToolBarInfo::m_uiLargeHotResID](#m_uilargehotresid)|Büyük, seçilen araç çubuğu görüntülerini içeren araç çubuğu bit eşlemi kaynak kimliği.|
|[CMFCToolBarInfo::m_uiMenuDisabledResID](#m_uimenudisabledresid)|Devre dışı bırakılmış menü görüntüsü yer araç çubuğu bit eşlemi kaynak kimliği.|
|[CMFCToolBarInfo::m_uiMenuResID](#m_uimenuresid)|Menü görüntüsü yer araç çubuğu bit eşlemi kaynak kimliği.|

## <a name="remarks"></a>Açıklamalar

Tam araç çubuğu bit eşlem küçük araç çubuğu görüntülerini sabit bir boyuta (düğme) oluşur. Depolanan her kaynak kimliği bir `CMFCToolBarInfo` araç çubuğu görüntülerini tek bir durumda (örneğin, seçili, devre dışı, büyük veya menü görüntüsü için) tam bir dizi içeren bir bit eşlem nesnedir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cmfctoolbarınfo](../../mfc/reference/cmfctoolbarinfo-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtoolbar.h

##  <a name="m_uicoldresid"></a>  CMFCToolBarInfo::m_uiColdResID

Bir kaynak kimliği için bir araç çubuğu tüm normal bir düğme görüntülerini belirtir.

```
UINT m_uiColdResID;
```

##  <a name="m_uidisabledresid"></a>  CMFCToolBarInfo::m_uiDisabledResID

Bir kaynak kimliği için bir araç çubuğu düğmesi kullanılamıyor görüntülerini belirtir.

```
UINT m_uiDisabledResID;
```

##  <a name="m_uihotresid"></a>  CMFCToolBarInfo::m_uiHotResID

Bir araç çubuğunun tüm vurgulanan düğmesi görüntüler için bir kaynak Kimliğini belirtir.

```
UINT m_uiHotResID
```

##  <a name="m_uilargecoldresid"></a>  CMFCToolBarInfo::m_uiLargeColdResID

Bir kaynak kimliği için bir araç tüm büyük normal düğme görüntülerini belirtir.

```
UINT m_uiLargeColdResID
```

##  <a name="m_uilargedisabledresid"></a>  CMFCToolBarInfo::m_uiLargeDisabledResID

Bir kaynak kimliği için bir araç tüm büyük devre dışı düğme görüntülerini belirtir.

```
UINT m_uiLargeDisabledResID;
```

##  <a name="m_uilargehotresid"></a>  CMFCToolBarInfo::m_uiLargeHotResID

Bir kaynak kimliği için tüm büyük vurgulanan görüntüleri bir araç çubuğunun belirtir.

```
UINT m_uiLargeHotResID;
```

##  <a name="m_uimenudisabledresid"></a>  CMFCToolBarInfo::m_uiMenuDisabledResID

Bir kaynak kimliği için bir araç çubuğu komut kullanılamaz görüntülerini belirtir.

```
UINT m_uiMenuDisabledResID;
```

##  <a name="m_uimenuresid"></a>  CMFCToolBarInfo::m_uiMenuResID

Bir kaynak kimliği için bir araç çubuğunun tüm normal menü öğesi resimlerinin belirtir.

```
UINT m_uiMenuResID;
```

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)
