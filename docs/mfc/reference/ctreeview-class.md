---
title: CTreeView sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
dev_langs:
- C++
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d19d4958de2f7909f2072b2ae2f59c00e63d65a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373631"
---
# <a name="ctreeview-class"></a>CTreeView sınıfı
Ağaç denetimi'nin ve kullanım basitleştirir [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), MFC'nin belge görünüm mimarisi ile ağaç denetimi işlevselliği kapsar sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CTreeView : public CCtrlView  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTreeView::CTreeView](#ctreeview)|Oluşturan bir `CTreeView` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTreeView::GetTreeCtrl](#gettreectrl)|Görünüm ile ilişkilendirilen ağaç denetimini döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu mimari ile ilgili daha fazla bilgi için bkz: genel bakış için [CView](../../mfc/reference/cview-class.md) sınıfı ve çapraz olmadığını bildirdi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CTreeView`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcview.h  
  
##  <a name="ctreeview"></a>  CTreeView::CTreeView  
 Oluşturan bir `CTreeView` nesnesi.  
  
```  
CTreeView();
```  
  
##  <a name="gettreectrl"></a>  CTreeView::GetTreeCtrl  
 Ağaç denetimi görünüm ile ilişkilendirilen bir başvuru döndürür.  
  
```  
CTreeCtrl& GetTreeCtrl() const;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CView sınıfı](../../mfc/reference/cview-class.md)   
 [CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)   
 [CTreeCtrl Sınıfı](../../mfc/reference/ctreectrl-class.md)
