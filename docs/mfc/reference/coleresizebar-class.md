---
title: COleResizeBar sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
dev_langs:
- C++
helpviewer_keywords:
- COleResizeBar [MFC], COleResizeBar
- COleResizeBar [MFC], Create
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf000b45e2bd24ec40e1ae15001c3df46d1b12c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="coleresizebar-class"></a>COleResizeBar sınıfı
Yerinde OLE öğeleri yeniden boyutlandırılmasını destekler denetim çubuğu türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleResizeBar : public CControlBar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleResizeBar::COleResizeBar](#coleresizebar)|Oluşturan bir `COleResizeBar` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleResizeBar::Create](#create)|Oluşturur ve Windows alt pencere başlatır ve kendisine ilişkilendirir `COleResizeBar` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `COleResizeBar` nesneler görünür olarak bir [CRectTracker](../../mfc/reference/crecttracker-class.md) taranmış kenarlık ve dış tanıtıcıları yeniden boyutlandırın.  
  
 `COleResizeBar` nesneleri türetilmiş çerçeve pencere nesneleri genellikle katıştırılmış üyeleri olan [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) sınıfı.  
  
 Daha fazla bilgi için bkz: [etkinleştirme](../../mfc/activation-cpp.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `COleResizeBar`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="coleresizebar"></a>  COleResizeBar::COleResizeBar  
 Oluşturan bir `COleResizeBar` nesnesi.  
  
```  
COleResizeBar();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı **oluşturma** yeniden boyutlandırma çubuğu nesnesi oluşturulamıyor.  
  
##  <a name="create"></a>  COleResizeBar::Create  
 Alt pencere oluşturur ve bunu ile ilişkilendirir `COleResizeBar` nesnesi.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_RESIZE_BAR);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentWnd`  
 Yeniden boyutlandırma çubuğunun üst pencere işaretçi.  
  
 `dwStyle`  
 Belirtir [pencere stili](../../mfc/reference/styles-used-by-mfc.md#window-styles) öznitelikleri.  
  
 `nID`  
 Yeniden boyutlandırma çubuğunun alt pencere kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeniden boyutlandırma çubuğunu oluşturduysanız sıfır olmayan; Aksi takdirde 0.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek SUPERPAD](../../visual-cpp-samples.md)   
 [CControlBar sınıfı](../../mfc/reference/ccontrolbar-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleServerDoc Sınıfı](../../mfc/reference/coleserverdoc-class.md)
