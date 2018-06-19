---
title: CMFCTabToolTipInfo yapısı | Microsoft Docs
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
ms.openlocfilehash: fb2d1a139a5bc61d665a28f21ab10979802045b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373735"
---
# <a name="cmfctabtooltipinfo-structure"></a>CMFCTabToolTipInfo yapısı
Bu yapı kullanıcı üzerine getirildiğinde MDI sekmesi hakkında bilgi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CMFCTabToolTipInfo  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCTabToolTipInfo::m_nTabIndex](#m_ntabindex)|Sekme denetimi dizinini belirtir.|  
|[CMFCTabToolTipInfo::m_pTabWnd](#m_ptabwnd)|Sekme denetimi için bir işaretçi.|  
|[CMFCTabToolTipInfo::m_strText](#m_strtext)|Araç İpucu metni.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir işaretçi bir `CMFCTabToolTipInfo` yapısı bir parametre olarak geçirilen `AFX_WM_ON_GET_TAB_TOOLTIP` ileti. Bu ileti MDI sekmeleri etkinleştirilir ve kullanıcı bir sekme denetimi gezinen oluşturulur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği nasıl `CMFCTabToolTipInfo` kullanılan [MDITabsDemo örnek: MFC sekmeli MDI uygulaması](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxbasetabctrl.h  
  
##  <a name="m_ntabindex"></a>  CMFCTabToolTipInfo::m_nTabIndex  
 Sekme denetimi dizinini belirtir.  
  
```  
int m_nTabIndex;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı getirildiğinde sekmesini dizini.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği nasıl `m_nTabIndex` kullanılan [MDITabsDemo örnek: MFC sekmeli MDI uygulaması](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="m_ptabwnd"></a>  CMFCTabToolTipInfo::m_pTabWnd  
 Sekme denetimi için bir işaretçi.  
  
```  
CMFCBaseTabCtrl* m_pTabWnd;  
```  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği nasıl `m_pTabWnd` kullanılan [MDITabsDemo örnek: MFC sekmeli MDI uygulaması](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="m_strtext"></a>  CMFCTabToolTipInfo::m_strText  
 Araç İpucu metni.  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dize boşsa, araç ipucu görüntülenmez.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği nasıl `m_strText` kullanılan [MDITabsDemo örnek: MFC sekmeli MDI uygulaması](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
