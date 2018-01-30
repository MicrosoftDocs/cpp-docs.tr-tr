---
title: "CMFCDragFrameImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDragFrameImpl
dev_langs:
- C++
helpviewer_keywords:
- CMFCDragFrameImpl class [MFC]
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2fe293a8fa64cb323771db4f0f2929204790d210
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="cmfcdragframeimpl-class"></a>CMFCDragFrameImpl Class
`CMFCDragFrameImpl` Sınıfı kullanıcı bir bölme standart yerleştirme modunda sürüklendiğinde görüntülenen Sürükle dikdörtgen çizer.  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
   
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCDragFrameImpl  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıfın bir nesnesi her katıştırılmış [CPane sınıfı](../../mfc/reference/cpane-class.md) nesnesi. Bu nedenle, kullanan her bölme `CanFloat` yöntemi kullanıcı sürüklendiğinde sürükleyin dikdörtgen görüntüler.  
  
 Sürükleme dikdörtgen kalınlığı kullanarak denetleyebilirsiniz [AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](afx-global-data-structure.md#m_ndragframethicknessfloat) ve [AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](afx-global-data-structure.md#m_ndragframethicknessdock).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdragframeimpl.h  
  
##  <a name="enddrawdragframe"></a>CMFCDragFrameImpl::EndDrawDragFrame  

  
```  
void EndDrawDragFrame(BOOL bClearInternalRects = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bClearInternalRects`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="init"></a>  CMFCDragFrameImpl::Init  

  
```  
void Init(CWnd* pDraggedWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDraggedWnd`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="movedragframe"></a>  CMFCDragFrameImpl::MoveDragFrame  

  
```  
void MoveDragFrame(BOOL bForceMove = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bForceMove`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="placetabpredocking"></a>  CMFCDragFrameImpl::PlaceTabPreDocking  

  
```  
void PlaceTabPreDocking(
    CBaseTabbedPane* pTabbedBar,  
    BOOL bFirstTime);  
  
void PlaceTabPreDocking(CWnd* pCBarToPlaceOn);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pTabbedBar`  
 [in]`bFirstTime`  
 [in]`pCBarToPlaceOn`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removetabpredocking"></a>  CMFCDragFrameImpl::RemoveTabPreDocking  

  
```  
void RemoveTabPreDocking(CDockablePane* pOldTargetBar = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pOldTargetBar`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="resetstate"></a>  CMFCDragFrameImpl::ResetState  

  
```  
void ResetState();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CPane Sınıfı](../../mfc/reference/cpane-class.md)