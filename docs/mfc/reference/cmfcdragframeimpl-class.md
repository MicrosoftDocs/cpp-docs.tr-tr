---
title: Cmfcdragframeımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDragFrameImpl
dev_langs:
- C++
helpviewer_keywords:
- CMFCDragFrameImpl class [MFC]
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c8cd05dc5d4cdff535b8e571e94d9033d0220ccf
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710170"
---
# <a name="cmfcdragframeimpl-class"></a>Cmfcdragframeımpl sınıfı
`CMFCDragFrameImpl` Sınıfı, kullanıcı standart dock modunda bir bölmeyi sürüklediğinde görünen sürükleme dikdörtgenini çizer.  
   Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.  
   
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCDragFrameImpl  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıfın bir nesnesi her katıştırılmış [CPane sınıfı](../../mfc/reference/cpane-class.md) nesne. Bu nedenle, kullanan her bölmede `CanFloat` kullanıcı nesneyi sürüklediğinde sürükleme dikdörtgenini yöntemini görüntüler.  
  
 Sürükleme dikdörtgenini kalınlığı kullanarak denetleyebilirsiniz [AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](afx-global-data-structure.md#m_ndragframethicknessfloat) ve [AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](afx-global-data-structure.md#m_ndragframethicknessdock).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdragframeimpl.h  
  
##  <a name="enddrawdragframe"></a>  CMFCDragFrameImpl::EndDrawDragFrame  

  
```  
void EndDrawDragFrame(BOOL bClearInternalRects = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bClearInternalRects*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="init"></a>  CMFCDragFrameImpl::Init  

  
```  
void Init(CWnd* pDraggedWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDraggedWnd*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="movedragframe"></a>  CMFCDragFrameImpl::MoveDragFrame  

  
```  
void MoveDragFrame(BOOL bForceMove = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bForceMove*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="placetabpredocking"></a>  CMFCDragFrameImpl::PlaceTabPreDocking  

  
```  
void PlaceTabPreDocking(
    CBaseTabbedPane* pTabbedBar,  
    BOOL bFirstTime);  
  
void PlaceTabPreDocking(CWnd* pCBarToPlaceOn);
```  
  
### <a name="parameters"></a>Parametreler  
*pTabbedBar*<br/>
[in] [in] *bFirstTime*  
 [in] *pCBarToPlaceOn*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removetabpredocking"></a>  CMFCDragFrameImpl::RemoveTabPreDocking  

  
```  
void RemoveTabPreDocking(CDockablePane* pOldTargetBar = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pOldTargetBar*  
  
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