---
title: "CMFCPropertyGridToolTipCtrl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Create
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Deactivate
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::GetLastRect
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Hide
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::SetTextMargin
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Track
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridToolTipCtrl [MFC], CMFCPropertyGridToolTipCtrl
- CMFCPropertyGridToolTipCtrl [MFC], Create
- CMFCPropertyGridToolTipCtrl [MFC], Deactivate
- CMFCPropertyGridToolTipCtrl [MFC], GetLastRect
- CMFCPropertyGridToolTipCtrl [MFC], Hide
- CMFCPropertyGridToolTipCtrl [MFC], SetTextMargin
- CMFCPropertyGridToolTipCtrl [MFC], Track
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a0b4a43da8943bc196a799ca4419dea7f34ed76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcpropertygridtooltipctrl-class"></a>CMFCPropertyGridToolTipCtrl sınıfı
Implements araç ipucu bir denetim [CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md) araç ipuçlarını görüntülemek için kullanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCPropertyGridToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](#cmfcpropertygridtooltipctrl)|Oluşturan bir `CMFCPropertyGridToolTipCtrl` nesnesi.|  
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCPropertyGridToolTipCtrl::Create](#create)|Araç İpucu denetimi için pencere oluşturur.|  
|[CMFCPropertyGridToolTipCtrl::Deactivate](#deactivate)|Devre dışı bırakır ve araç ipucunu denetimini gizler.|  
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|Tooltip denetiminin son konum koordinatlarını döndürür.|  
|[CMFCPropertyGridToolTipCtrl::Hide](#hide)|Araç ipucunu denetimini gizler.|  
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|Sınıfı tarafından kullanılan [CWinApp](../../mfc/reference/cwinapp-class.md) için gönderilen önce pencere iletileri çevirmek için [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows çalışır. (Geçersiz kılmaları [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|Araç İpucu metni ve araç ipucu penceresinin kenarlık arasındaki boşluğu ayarlar.|  
|[CMFCPropertyGridToolTipCtrl::Track](#track)|Araç İpucu denetimi görüntüler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Araç ipuçları, fare işaretçisini bir özellik adı getirdiğinde görüntülenir. [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) sınıfı, böylece kullanıcı tarafından kolay okunabilir bir araç ipucu görüntüler. Genellikle, bir araç ipucu konumunu işaretçinin konumu tarafından belirlenir. Bu sınıf kullanarak, araç ipucu özellik adı görüntülenir ve özellik adı tam olarak görünür olmasını sağlamak doğal özellik uzantısı benzer.  
  
 MFC otomatik olarak bu denetimi oluşturur ve bunu kullanır [CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCPropertyGridToolTipCtrl` sınıfı ve araç ipucu denetimi görüntüleme.  
  
 [!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpropertygridtooltipctrl.h  
  
##  <a name="cmfcpropertygridtooltipctrl"></a>CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl  
 Oluşturan bir `CMFCPropertyGridToolTipCtrl` nesnesi.  
  
```  
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```  
  
##  <a name="create"></a>CMFCPropertyGridToolTipCtrl::Create  
 Araç İpucu denetimi için pencere oluşturur.  
  
```  
BOOL Create(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWndParent`  
 Üst pencere için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Pencerenin başarıyla oluşturulduysa TRUE; Aksi takdirde FALSE.  
  
##  <a name="deactivate"></a>CMFCPropertyGridToolTipCtrl::Deactivate  
 Devre dışı bırakır ve araç ipucunu denetimini gizler.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Gelecekte çağrılar bu yöntem son konumunu ve metin boş değerler için ayarlar, böylece [CMFCPropertyGridToolTipCtrl::Track](#track) araç ipucunu görüntüleyebilirsiniz.  
  
##  <a name="getlastrect"></a>CMFCPropertyGridToolTipCtrl::GetLastRect  
 Tooltip denetiminin son konum koordinatlarını döndürür.  
  
```  
void GetLastRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`rect`  
 Tooltip denetim son konumunu içerir.  
  
##  <a name="hide"></a>CMFCPropertyGridToolTipCtrl::Hide  
 Araç ipucunu denetimini gizler.  
  
```  
void Hide();
```  
  
##  <a name="settextmargin"></a>CMFCPropertyGridToolTipCtrl::SetTextMargin  
 Araç İpucu metni ve araç ipucu penceresinin kenarlık arasındaki boşluğu ayarlar.  
  
```  
void SetTextMargin(int nTextMargin);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nTextMargin`  
 Araç İpucu denetimi metin ve araç ipucu penceresinin kenarlık arasındaki boşluğu belirtir. Varsayılan değer 10 pikseldir.  
  
##  <a name="track"></a>CMFCPropertyGridToolTipCtrl::Track  
 Araç İpucu denetimi görüntüler.  
  
```  
void Track(
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rect`  
 Tooltip denetim boyutunu ve konumunu belirtir.  
  
 [in]`strText`  
 Araç ipucunda gösterilecek metni belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından belirtilen boyut ve konum araç ipucu denetimi görüntüler `rect`. Konum, boyutu ve metin bu yöntemi çağrıldı en son ne zaman bu yana değişmemiştir, bu yöntem bir etkisi yoktur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
