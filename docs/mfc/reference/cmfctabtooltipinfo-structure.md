---
title: CMFCTabToolTipInfo Yapısı
ms.date: 11/04/2016
f1_keywords:
- CMFCTabToolTipInfo
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
ms.openlocfilehash: a507d1e69b3524074e50fde0e87fc5ebb6e5ca03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367337"
---
# <a name="cmfctabtooltipinfo-structure"></a>CMFCTabToolTipInfo Yapısı

Bu yapı, kullanıcının üzerinde gezinen MDI sekmesi hakkında bilgi sağlar.

## <a name="syntax"></a>Sözdizimi

```
struct CMFCTabToolTipInfo
```

## <a name="members"></a>Üyeler

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMFCTabToolTipInfo::m_nTabIndex](#m_ntabindex)|Sekme denetiminin dizinini belirtir.|
|[CMFCTabToolTipInfo::m_pTabWnd](#m_ptabwnd)|Sekme denetimi için bir işaretçi.|
|[CMFCTabToolTipInfo::m_strText](#m_strtext)|Araç ipucu metni.|

## <a name="remarks"></a>Açıklamalar

Bir `CMFCTabToolTipInfo` yapının işaretçisi, AFX_WM_ON_GET_TAB_TOOLTIP iletisinin parametresi olarak geçirilir. Bu ileti, MDI sekmeleri etkinleştirildiğinde ve kullanıcı bir sekme denetiminin üzerinde gezindiğinde oluşturulur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCTabToolTipInfo` [MDITabsDemo Örnek: MFC Sekmeli MDI Uygulamasında](../../overview/visual-cpp-samples.md)nasıl kullanıldığını gösterir.

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxbasetabctrl.h

## <a name="cmfctabtooltipinfom_ntabindex"></a><a name="m_ntabindex"></a>CMFCTabToolTipInfo::m_nTabIndex

Sekme denetiminin dizinini belirtir.

```
int m_nTabIndex;
```

### <a name="remarks"></a>Açıklamalar

Kullanıcının üzerinde gezindiği sekme dizini.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `m_nTabIndex` [MDITabsDemo Örnek: MFC Sekmeli MDI Uygulamasında](../../overview/visual-cpp-samples.md)nasıl kullanıldığını gösterir.

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="cmfctabtooltipinfom_ptabwnd"></a><a name="m_ptabwnd"></a>CMFCTabToolTipInfo::m_pTabWnd

Sekme denetimi için bir işaretçi.

```
CMFCBaseTabCtrl* m_pTabWnd;
```

### <a name="example"></a>Örnek

Aşağıdaki örnek, `m_pTabWnd` [MDITabsDemo Örnek: MFC Sekmeli MDI Uygulamasında](../../overview/visual-cpp-samples.md)nasıl kullanıldığını gösterir.

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="cmfctabtooltipinfom_strtext"></a><a name="m_strtext"></a>CMFCTabToolTipInfo::m_strText

Araç ipucu metni.

```
CString m_strText;
```

### <a name="remarks"></a>Açıklamalar

Dize boşsa, araç ucu görüntülenmez.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `m_strText` [MDITabsDemo Örnek: MFC Sekmeli MDI Uygulamasında](../../overview/visual-cpp-samples.md)nasıl kullanıldığını gösterir.

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
