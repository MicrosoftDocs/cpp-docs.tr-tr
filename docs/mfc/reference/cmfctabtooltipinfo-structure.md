---
title: Cmfctabtooltipınfo yapısı
ms.date: 11/04/2016
f1_keywords:
- CMFCTabToolTipInfo
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
ms.openlocfilehash: 87c8820bc33f3a344933faa797a9fc60d2422b13
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252964"
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

Aşağıdaki örnekte gösterildiği nasıl `CMFCTabToolTipInfo` kullanılır [MDITabsDemo örnek: MFC sekmeli MDI uygulaması](../../overview/visual-cpp-samples.md).

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

Aşağıdaki örnekte gösterildiği nasıl `m_nTabIndex` kullanılır [MDITabsDemo örnek: MFC sekmeli MDI uygulaması](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

##  <a name="m_ptabwnd"></a>  CMFCTabToolTipInfo::m_pTabWnd

Sekme denetimine yönelik işaretçi.

```
CMFCBaseTabCtrl* m_pTabWnd;
```

### <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği nasıl `m_pTabWnd` kullanılır [MDITabsDemo örnek: MFC sekmeli MDI uygulaması](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

##  <a name="m_strtext"></a>  CMFCTabToolTipInfo::m_strText

Araç İpucu metni.

```
CString m_strText;
```

### <a name="remarks"></a>Açıklamalar

Dize boşsa, araç ipucu görüntülenmez.

### <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği nasıl `m_strText` kullanılır [MDITabsDemo örnek: MFC sekmeli MDI uygulaması](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
