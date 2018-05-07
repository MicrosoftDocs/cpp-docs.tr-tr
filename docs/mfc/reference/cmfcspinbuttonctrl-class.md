---
title: CMFCSpinButtonCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
dev_langs:
- C++
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b8c602882036d77105bb619069a6e43d73ceeb6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
  
##  <a name="ondraw"></a>  CMFCSpinButtonCtrl::OnDraw  
 Geçerli değer değiştirme düğmesi denetimi şekilde yeniden boyar.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework çağrıları `CMFCSpinButtonCtrl::OnPaint` yöntemini [CWnd::OnPaint](../../mfc/reference/cwnd-class.md#onpaint) ileti ve yöntemi sırayla bu çağırdığı `CMFCSpinButtonCtrl::OnDraw` yöntemi. Değer değiştirme düğmesi denetimi framework çizer biçimini özelleştirmek üzere bu yöntemi geçersiz kılın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager Sınıfı](../../mfc/reference/cmfcvisualmanager-class.md)
