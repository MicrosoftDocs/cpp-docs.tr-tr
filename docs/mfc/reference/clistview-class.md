---
title: "CListView sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CListView
- AFXCVIEW/CListView
- AFXCVIEW/CListView::CListView
- AFXCVIEW/CListView::GetListCtrl
- AFXCVIEW/CListView::RemoveImageList
dev_langs: C++
helpviewer_keywords:
- CListView [MFC], CListView
- CListView [MFC], GetListCtrl
- CListView [MFC], RemoveImageList
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a54a66efdaa6589628812a60292767a0e42c2e97
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="clistview-class"></a>CListView sınıfı
Liste denetimi'nin ve kullanım basitleştirir [CListCtrl](../../mfc/reference/clistctrl-class.md), MFC'nin belge görünüm mimarisi ile liste denetimi işlevselliği kapsar sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CListView : public CCtrlView  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CListView::CListView](#clistview)|Oluşturan bir `CListView` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CListView::GetListCtrl](#getlistctrl)|Görünüm ile ilişkilendirilen liste denetimini döndürür.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CListView::RemoveImageList](#removeimagelist)|Belirtilen resim listesi listesinde görünümden kaldırır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu mimari ile ilgili daha fazla bilgi için bkz: genel bakış için [CView](../../mfc/reference/cview-class.md) sınıfı ve çapraz olmadığını bildirdi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CListView`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcview.h  
  
##  <a name="clistview"></a>CListView::CListView  
 Oluşturan bir `CListView` nesnesi.  
  
```  
CListView();
```  
  
##  <a name="getlistctrl"></a>CListView::GetListCtrl  
 Görünüm ile ilişkilendirilen liste denetimi için bir başvuru almak için bu üye işlevini çağırın.  
  
```  
CListCtrl& GetListCtrl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görünüm ile ilişkilendirilen liste denetimi referansı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCListView#7](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]  
  
##  <a name="removeimagelist"></a>CListView::RemoveImageList  
 Belirtilen resim listesi listesinde görünümden kaldırır.  
  
```  
void RemoveImageList(int nImageList);
```  
  
### <a name="parameters"></a>Parametreler  
 `nImageList`  
 Görüntünün kaldırmak için sıfır tabanlı dizini.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek ROWLIST](../../visual-cpp-samples.md)   
 [CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)
