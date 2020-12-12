---
description: 'Daha fazla bilgi edinin: CMFCTabToolTipInfo yapısı'
title: CMFCTabToolTipInfo yapısı
ms.date: 11/04/2016
f1_keywords:
- CMFCTabToolTipInfo
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
ms.openlocfilehash: ce9e9f4fdbcf367921e7f0559a4d04e66f4303dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164074"
---
# <a name="cmfctabtooltipinfo-structure"></a>CMFCTabToolTipInfo yapısı

Bu yapı, kullanıcının üzerine gelindiğinde MDI sekmesi hakkında bilgi sağlar.

## <a name="syntax"></a>Syntax

```
struct CMFCTabToolTipInfo
```

## <a name="members"></a>Üyeler

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCTabToolTipInfo:: m_nTabIndex](#m_ntabindex)|Sekme denetiminin dizinini belirtir.|
|[CMFCTabToolTipInfo:: m_pTabWnd](#m_ptabwnd)|Sekme denetimine yönelik bir işaretçi.|
|[CMFCTabToolTipInfo:: m_strText](#m_strtext)|Araç ipucu metni.|

## <a name="remarks"></a>Açıklamalar

Yapı işaretçisi, `CMFCTabToolTipInfo` AFX_WM_ON_GET_TAB_TOOLTIP iletisinin parametresi olarak geçirilir. Bu ileti, MDI sekmeleri etkinleştirildiğinde ve Kullanıcı bir sekme denetiminin üzerine geldiğinde oluşturulur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCTabToolTipInfo` [MDITabsDemo ÖRNEĞI: mfc sekmeli MDI uygulamasında](../../overview/visual-cpp-samples.md)nasıl kullanıldığını gösterir.

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxbasetabctrl. h

## <a name="cmfctabtooltipinfom_ntabindex"></a><a name="m_ntabindex"></a> CMFCTabToolTipInfo:: m_nTabIndex

Sekme denetiminin dizinini belirtir.

```
int m_nTabIndex;
```

### <a name="remarks"></a>Açıklamalar

Kullanıcının üzerine gelindiğinde bulunan sekmenin dizini.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `m_nTabIndex` [MDITabsDemo ÖRNEĞI: mfc sekmeli MDI uygulamasında](../../overview/visual-cpp-samples.md)nasıl kullanıldığını gösterir.

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="cmfctabtooltipinfom_ptabwnd"></a><a name="m_ptabwnd"></a> CMFCTabToolTipInfo:: m_pTabWnd

Sekme denetimine yönelik bir işaretçi.

```
CMFCBaseTabCtrl* m_pTabWnd;
```

### <a name="example"></a>Örnek

Aşağıdaki örnek, `m_pTabWnd` [MDITabsDemo ÖRNEĞI: mfc sekmeli MDI uygulamasında](../../overview/visual-cpp-samples.md)nasıl kullanıldığını gösterir.

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="cmfctabtooltipinfom_strtext"></a><a name="m_strtext"></a> CMFCTabToolTipInfo:: m_strText

Araç ipucu metni.

```
CString m_strText;
```

### <a name="remarks"></a>Açıklamalar

Dize boşsa Araç İpucu görüntülenmez.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `m_strText` [MDITabsDemo ÖRNEĞI: mfc sekmeli MDI uygulamasında](../../overview/visual-cpp-samples.md)nasıl kullanıldığını gösterir.

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
