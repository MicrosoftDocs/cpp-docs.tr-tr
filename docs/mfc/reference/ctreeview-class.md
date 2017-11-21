---
title: "CTreeView sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
dev_langs: C++
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6d1d8ee7d06e9926a240ca185ce36ba0b1a180af
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
##  <a name="ctreeview"></a>CTreeView::CTreeView  
 Oluşturan bir `CTreeView` nesnesi.  
  
```  
CTreeView();
```  
  
##  <a name="gettreectrl"></a>CTreeView::GetTreeCtrl  
 Ağaç denetimi görünüm ile ilişkilendirilen bir başvuru döndürür.  
  
```  
CTreeCtrl& GetTreeCtrl() const;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CView sınıfı](../../mfc/reference/cview-class.md)   
 [CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)   
 [CTreeCtrl sınıfı](../../mfc/reference/ctreectrl-class.md)
