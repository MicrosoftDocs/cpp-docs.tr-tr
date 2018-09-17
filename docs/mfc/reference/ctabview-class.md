---
title: CTabView sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTabView
- AFXTABVIEW/CTabView
- AFXTABVIEW/CTabView::AddView
- AFXTABVIEW/CTabView::FindTab
- AFXTABVIEW/CTabView::GetActiveView
- AFXTABVIEW/CTabView::GetTabControl
- AFXTABVIEW/CTabView::RemoveView
- AFXTABVIEW/CTabView::SetActiveView
- AFXTABVIEW/CTabView::IsScrollBar
- AFXTABVIEW/CTabView::OnActivateView
dev_langs:
- C++
helpviewer_keywords:
- CTabView [MFC], AddView
- CTabView [MFC], FindTab
- CTabView [MFC], GetActiveView
- CTabView [MFC], GetTabControl
- CTabView [MFC], RemoveView
- CTabView [MFC], SetActiveView
- CTabView [MFC], IsScrollBar
- CTabView [MFC], OnActivateView
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce47dc5fc0a1d05d2f7200539718fb11c60d810e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718867"
---
# <a name="ctabview-class"></a>CTabView sınıfı
`CTabView` Sınıfı basitleştirir sekme denetim sınıfının kullanımı ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)) MFC'nin belge/görünüm mimarisini kullanan uygulamalarda.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CTabbedView : public CView  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTabView::AddView](#addview)|Yeni bir görünüm için sekmesinde denetimi ekler.|  
|[CTabView::FindTab](#findtab)|Belirtilen Görünüm dizini içinde Sekme denetimini döndürür.|  
|[CTabView::GetActiveView](#getactiveview)|Şu anda etkin görünüm için bir işaretçi döndürür|  
|[CTabView::GetTabControl](#gettabcontrol)|Sekme denetimi görünüm ile ilişkilendirilen bir başvuru döndürür.|  
|[CTabView::RemoveView](#removeview)|Görünüm sekmesini denetiminden kaldırır.|  
|[CTabView::SetActiveView](#setactiveview)|Bir görünümü etkin hale getirir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTabView::IsScrollBar](#isscrollbar)|Sekme görünümü paylaşılan yatay kaydırma çubuğu olup olmadığını belirlemek için sekmesinde görünümü oluştururken framework tarafından çağırılır.|  
|[CTabView::OnActivateView](#onactivateview)|Etkin veya devre dışı sekmesi görünümü yapıldığında framework tarafından çağırılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, bir belge/görünüm uygulamasına sekmeler halinde görüntüleniyor koymak kolaylaştırır. `CTabView` olan bir `CView`-katıştırılmış içeren sınıf türetilmiş `CMFCTabCtrl` nesne. `CTabView` desteklemek için gereken tüm iletileri işleyen `CMFCTabCtrl` nesne. Yalnızca bir sınıftan türetilen `CTabView` ve uygulamanıza eklenir ve ardından eklemek `CView`-türetilmiş sınıfları kullanarak `AddView` yöntemi. Sekme denetimine sekmeler bu görünümleri görüntüler.  
  
 Örneğin, farklı şekilde temsil edilebilen bir belge olabilir: bir elektronik tablo, bir grafik, bir düzenlenebilir formda ve benzeri. Verileri gereken şekilde çizim tek bir görünüm oluşturun, bunları eklemek, `CTabView`-türetilmiş bir nesneye ve herhangi ek kodlama olmadan sekmeli sağlayabilirsiniz.  
  
 [TabbedView örneği: MFC sekmeli görünüm uygulaması](../../visual-cpp-samples.md) kullanımını `CTabView`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği nasıl `CTabView` TabbedView örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxTabView.h  
  
##  <a name="addview"></a>  CTabView::AddView  
 Bir görünüm için sekmesinde denetimi ekler.  
  
```  
int AddView(
    CRuntimeClass* pViewClass,  
    const CString& strViewLabel,  
    int iIndex=-1,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
*pViewClass*<br/>
[in] Eklenen görünümünün bir çalışma zamanı sınıf işaretçisi.  
  
*strViewLabel*<br/>
[in] Sekmenin metnini belirtir.  
  
*İIndex*<br/>
[in] Görünüm eklemek, sıfır tabanlı konumu belirtir. Konumu -1 olması durumunda, yeni sekmenin sonuna eklenir.  
  
*pContext*<br/>
[in] Bir işaretçi `CCreateContext` görünümün.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa görünümü dizini. Aksi durumda, -1.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir çerçevede katıştırılmış sekme denetimi için Görünüm eklemek için bu işlevi çağırın.  
  
##  <a name="findtab"></a>  CTabView::FindTab  
 Belirtilen Görünüm dizini içinde Sekme denetimini döndürür.  
  
```  
int FindTab(HWND hWndView) const;  
```  
  
### <a name="parameters"></a>Parametreler  
*hWndView*<br/>
[in] Görünümün tanıtıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bulunursa görünümün dizinini; Aksi durumda, -1.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen bir tanıtıcı olan bir görünümde dizin almak için bu işlevi çağırın.  
  
##  <a name="getactiveview"></a>  CTabView::GetActiveView  
 Şu anda etkin görünüm için bir işaretçi döndürür.  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir işaretçi etkin veya etkin görünüm yoksa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gettabcontrol"></a>  CTabView::GetTabControl  
 Sekme denetimi görünüm ile ilişkilendirilen bir başvuru döndürür.  
  
```  
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sekme denetimi görünüm ile ilişkilendirilen bir başvuru.  
  
##  <a name="isscrollbar"></a>  CTabView::IsScrollBar  
 Sekme görünümü paylaşılan yatay kaydırma çubuğu olup olmadığını belirlemek için sekmesinde görünümü oluştururken framework tarafından çağırılır.  
  
```  
virtual BOOL IsScrollBar() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sekmesi görünümü ile birlikte bir paylaşılan bir kaydırma çubuğuna oluşturulması gerekiyorsa TRUE. Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework bu yöntemi çağırır olduğunda bir *CTabView* nesnesi oluşturuluyor.  
  
 Geçersiz kılma *IsScrollBar* yönteminde bir *CTabView*-türetilmiş sınıf ve paylaşılan yatay kaydırma çubuğu içeren bir görünüm oluşturmak istiyorsanız TRUE döndürür.  
  
##  <a name="onactivateview"></a>  CTabView::OnActivateView  
 Etkin veya devre dışı sekmesi görünümü yapıldığında framework tarafından çağırılır.  
  
```  
virtual void OnActivateView(CView* view);
```  
  
### <a name="parameters"></a>Parametreler  
*Görünümü*<br/>
[in] Görünüm için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama, hiçbir şey yapmaz. Bu yöntemin bir `CTabView`-türetilmiş sınıf bu bildirimi.  
  
##  <a name="removeview"></a>  CTabView::RemoveView  
 Görünüm sekmesini denetiminden kaldırır.  
  
```  
BOOL RemoveView(int iTabNum);
```  
  
### <a name="parameters"></a>Parametreler  
*iTabNum*<br/>
[in] Dizini görünümün kaldırın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa kaldırılan görünümü dizini. Aksi takdirde-1.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setactiveview"></a>  CTabView::SetActiveView  
 Bir görünümü etkin hale getirir.  
  
```  
BOOL SetActiveView(int iTabNum);
```  
  
### <a name="parameters"></a>Parametreler  
*iTabNum*<br/>
[in] Sekme görünümü sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görünümün dizin geçersiz ise belirtilen görünümü yanlış etkin yapıldıysa TRUE.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için [CMFCTabCtrl::SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)   
 [CView Sınıfı](../../mfc/reference/cview-class.md)
