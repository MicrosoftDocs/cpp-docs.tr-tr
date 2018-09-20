---
title: Cmfctabtooltipınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCTabToolTipInfo
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21e612615110370922d71e1acaebcda56b2e692e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435460"
---
# <a name="cmfctabtooltipinfo-structure"></a>Cmfctabtooltipınfo yapısı

Bu yapı, kullanıcının üzerine geldiği MDI sekmesi hakkında bilgi sağlar.

## <a name="syntax"></a>Sözdizimi

```
struct CMFCTabToolTipInfo
```

## <a name="members"></a>Üyeler

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCTabToolTipInfo::m_nTabIndex](#m_ntabindex)|Sekme denetimi dizinini belirtir.|
|[CMFCTabToolTipInfo::m_pTabWnd](#m_ptabwnd)|Sekme denetimine yönelik işaretçi.|
|[CMFCTabToolTipInfo::m_strText](#m_strtext)|Araç İpucu metni.|

## <a name="remarks"></a>Açıklamalar

Bir işaretçi bir `CMFCTabToolTipInfo` yapısı AFX_WM_ON_GET_TAB_TOOLTIP iletisinin parametre olarak geçirilir. MDI sekmeleri etkinleştirilir ve kullanıcı bir sekme denetimin üzerine geldiğinde bu iletiyi üretilir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği nasıl `CMFCTabToolTipInfo` kullanılır [MDITabsDemo örnek: MFC sekmeli MDI uygulaması](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cmfctabtooltipınfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxbasetabctrl.h

##  <a name="m_ntabindex"></a>  CMFCTabToolTipInfo::m_nTabIndex

Sekme denetimi dizinini belirtir.

```
int m_nTabIndex;
```

### <a name="remarks"></a>Açıklamalar

Kullanıcının üzerine geldiği sekme dizini.

### <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği nasıl `m_nTabIndex` kullanılır [MDITabsDemo örnek: MFC sekmeli MDI uygulaması](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

##  <a name="m_ptabwnd"></a>  CMFCTabToolTipInfo::m_pTabWnd

Sekme denetimine yönelik işaretçi.

```
CMFCBaseTabCtrl* m_pTabWnd;
```

### <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği nasıl `m_pTabWnd` kullanılır [MDITabsDemo örnek: MFC sekmeli MDI uygulaması](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

##  <a name="m_strtext"></a>  CMFCTabToolTipInfo::m_strText

Araç İpucu metni.

```
CString m_strText;
```

### <a name="remarks"></a>Açıklamalar

Dize boşsa, araç ipucu görüntülenmez.

### <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği nasıl `m_strText` kullanılır [MDITabsDemo örnek: MFC sekmeli MDI uygulaması](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
