---
title: "CMFCSpinButtonCtrl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
dev_langs: C++
helpviewer_keywords: CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6736be0cca3c7cbd95ca1a81b5dd652da8d5badb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcspinbuttonctrl-class"></a>CMFCSpinButtonCtrl sınıfı
`CMFCSpinButtonCtrl` Sınıfı, bir değer değiştirme düğmesi denetimi çizer visual Yöneticisi'ni destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCSpinButtonCtrl : public CSpinButtonCtrl  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|Varsayılan Oluşturucu.|  
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCSpinButtonCtrl::OnDraw](#ondraw)|Geçerli değer değiştirme düğmesi denetimi şekilde yeniden boyar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Değer değiştirme düğmesi denetimi uygulamanızda çizmek için görsel bir Yöneticisi'ni kullanmak için tüm örneklerinin yerine `CSpinButtonCtrl` ile sınıfı `CMFCSpinButtonCtrl` sınıfı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCSpinButtonCtrl` sınıfı ve kullanmak, `Create` yöntemi.  
  
 [!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)  
  
 [CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxspinbuttonctrl.h  
  
##  <a name="ondraw"></a>CMFCSpinButtonCtrl::OnDraw  
 Geçerli değer değiştirme düğmesi denetimi şekilde yeniden boyar.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework çağrıları `CMFCSpinButtonCtrl::OnPaint` yöntemini [CWnd::OnPaint](../../mfc/reference/cwnd-class.md#onpaint) ileti ve yöntemi sırayla bu çağırdığı `CMFCSpinButtonCtrl::OnDraw` yöntemi. Değer değiştirme düğmesi denetimi framework çizer biçimini özelleştirmek üzere bu yöntemi geçersiz kılın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager sınıfı](../../mfc/reference/cmfcvisualmanager-class.md)
