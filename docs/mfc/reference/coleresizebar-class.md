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
ms.openlocfilehash: 3706521108d848535742bf2314142fedf46f1746
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852718"
---
# <a name="coleresizebar-class"></a>COleResizeBar sınıfı
Yerleşik OLE öğelerinin yeniden boyutlandırılmasını destekleyen denetim çubuğu türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleResizeBar : public CControlBar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleResizeBar::COleResizeBar](#coleresizebar)|Oluşturur bir `COleResizeBar` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleResizeBar::Create](#create)|Oluşturur ve bir Windows alt penceresi başlatır ve için ilişkilendirir `COleResizeBar` nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 `COleResizeBar` nesneler olarak görünür bir [CRectTracker](../../mfc/reference/crecttracker-class.md) taranmış kenarlıklı ve dış yeniden boyutlandırma tutamaçları.  
  
 `COleResizeBar` nesneleri, türetilen çerçeve pencere nesneleri genellikle katıştırılmış üyeleri [Coleıpframewnd](../../mfc/reference/coleipframewnd-class.md) sınıfı.  
  
 Daha fazla bilgi için bkz [etkinleştirme](../../mfc/activation-cpp.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `COleResizeBar`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="coleresizebar"></a>  COleResizeBar::COleResizeBar  
 Oluşturur bir `COleResizeBar` nesne.  
  
```  
COleResizeBar();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `Create` boyutlandırma çubuğu nesnesi oluşturulamıyor.  
  
##  <a name="create"></a>  COleResizeBar::Create  
 Bir alt pencere oluşturur ve bunu ile ilişkilendirir `COleResizeBar` nesne.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_RESIZE_BAR);
```  
  
### <a name="parameters"></a>Parametreler  
 *pParentWnd*  
 Yeniden boyutlandırma çubuğunun üst penceresine yönelik işaretçi.  
  
 *dwStyle*  
 Belirtir [pencere stili](../../mfc/reference/styles-used-by-mfc.md#window-styles) öznitelikleri.  
  
 *nID*  
 Yeniden boyutlandırma çubuğunun alt penceresi kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeniden boyutlandırma çubuğunu oluşturulduğu olursa sıfır dışı; Aksi durumda 0.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek SUPERPAD](../../visual-cpp-samples.md)   
 [CControlBar sınıfı](../../mfc/reference/ccontrolbar-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleServerDoc Sınıfı](../../mfc/reference/coleserverdoc-class.md)
