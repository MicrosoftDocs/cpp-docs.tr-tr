---
title: CMFCPropertyGridToolTipCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 574da3d370a403aa74ba8c438b7c175bee19f198
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211971"
---
# <a name="cmfcpropertygridtooltipctrl-class"></a>CMFCPropertyGridToolTipCtrl sınıfı
Uygulayan bir araç ipucu denetimi [CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md) araç ipuçlarını görüntülemek için kullanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCPropertyGridToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](#cmfcpropertygridtooltipctrl)|Oluşturur bir `CMFCPropertyGridToolTipCtrl` nesne.|  
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCPropertyGridToolTipCtrl::Create](#create)|Araç İpucu denetimi için bir pencere oluşturur.|  
|[CMFCPropertyGridToolTipCtrl::Deactivate](#deactivate)|Devre dışı bırakır ve araç ipucu denetimi gizler.|  
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|Araç İpucu denetimi son konum koordinatlarını döndürür.|  
|[CMFCPropertyGridToolTipCtrl::Hide](#hide)|Araç İpucu denetimi gizler.|  
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|Sınıfı tarafından kullanılan [CWinApp](../../mfc/reference/cwinapp-class.md) için dağıtılmadan önce pencere iletilerini çevrilecek [TranslateMessage](https://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](https://msdn.microsoft.com/library/windows/desktop/ms644934) Windows işlevleri. (Geçersiz kılmaları [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|Araç İpucu metni ve araç ipucu penceresinin kenarlığı arasındaki boşluğu ayarlar.|  
|[CMFCPropertyGridToolTipCtrl::Track](#track)|Araç İpucu denetimi görüntüler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Araç ipuçları, fare işaretçisini bir özellik adı getirdiğinde görüntülenir. [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) sınıfı, böylece kullanıcı tarafından kolay okunabilir bir araç ipucu görüntüler. Genellikle, bir araç ipucunun konumunu işaretçinin konumu tarafından belirlenir. Bu sınıfı kullanarak, araç ipucu özellik adı görüntülenir ve özellik adı tam olarak görünür olması, doğal özelliği uzantısı benzer.  
  
 MFC otomatik olarak bu denetimi oluşturur ve onu kullanan [CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
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
  
##  <a name="cmfcpropertygridtooltipctrl"></a>  CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl  
 Oluşturur bir `CMFCPropertyGridToolTipCtrl` nesne.  
  
```  
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```  
  
##  <a name="create"></a>  CMFCPropertyGridToolTipCtrl::Create  
 Araç İpucu denetimi için bir pencere oluşturur.  
  
```  
BOOL Create(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWndParent*  
 Üst penceresine bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Pencerenin başarıyla oluşturulursa TRUE; Aksi takdirde FALSE.  
  
##  <a name="deactivate"></a>  CMFCPropertyGridToolTipCtrl::Deactivate  
 Devre dışı bırakır ve araç ipucu denetimi gizler.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Gelecekteki çağrılar, bu yöntem son konum ve metin boş değerler için ayarlar [CMFCPropertyGridToolTipCtrl::Track](#track) araç ipucunu görüntülemek.  
  
##  <a name="getlastrect"></a>  CMFCPropertyGridToolTipCtrl::GetLastRect  
 Araç İpucu denetimi son konum koordinatlarını döndürür.  
  
```  
void GetLastRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *dikdörtgen*  
 Araç İpucu denetimi son konumunu içerir.  
  
##  <a name="hide"></a>  CMFCPropertyGridToolTipCtrl::Hide  
 Araç İpucu denetimi gizler.  
  
```  
void Hide();
```  
  
##  <a name="settextmargin"></a>  CMFCPropertyGridToolTipCtrl::SetTextMargin  
 Araç İpucu metni ve araç ipucu penceresinin kenarlığı arasındaki boşluğu ayarlar.  
  
```  
void SetTextMargin(int nTextMargin);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nTextMargin*  
 Araç ipucunu denetimini araç ipucu penceresinin kenarlığı arasındaki boşluğu belirtir. Varsayılan değer 10 pikseldir.  
  
##  <a name="track"></a>  CMFCPropertyGridToolTipCtrl::Track  
 Araç İpucu denetimi görüntüler.  
  
```  
void Track(
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dikdörtgen*  
 Araç İpucu denetiminin boyutunu ve konumunu belirtir.  
  
 [in] *strText*  
 Araç ipucunda gösterilecek olan metni belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından belirtilen boyut ve konum araç ipucu denetimi görüntüler *rect*. Konum, boyut ve metin bu yöntemi çağrıldı son saatinden itibaren değişmiş değil, bu yöntem etkisizdir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
