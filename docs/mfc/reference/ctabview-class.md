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
ms.openlocfilehash: 08c0cff2f6586ab5e385808fb806ed435b00bfc9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="ctabview-class"></a>CTabView sınıfı
`CTabView` Sınıfı basitleştirir sekmesi denetim sınıfı kullanımını ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)) MFC'nin belge/görünüm mimarisi kullanan uygulamalarda.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CTabbedView : public CView  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTabView::AddView](#addview)|Yeni bir görünüm sekme denetimi ekler.|  
|[CTabView::FindTab](#findtab)|Belirtilen Görünüm dizini içinde Sekme denetimini döndürür.|  
|[CTabView::GetActiveView](#getactiveview)|Şu anda etkin görünümün bir işaretçi döndürür|  
|[CTabView::GetTabControl](#gettabcontrol)|Sekme denetimi görünüm ile ilişkilendirilen bir başvuru döndürür.|  
|[CTabView::RemoveView](#removeview)|Görünüm sekmesini denetiminden kaldırır.|  
|[CTabView::SetActiveView](#setactiveview)|Bir görünümü etkin hale getirir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTabView::IsScrollBar](#isscrollbar)|Sekmesi görünümü paylaşılan yatay kaydırma çubuğu olup olmadığını belirlemek için sekme görünüm oluşturulurken çerçevesi tarafından çağrılır.|  
|[CTabView::OnActivateView](#onactivateview)|Etkin veya devre dışı sekmesi görünümü yapıldığında çerçevesi tarafından çağrılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, bir belge/görünüm uygulamasına sekmeli bir görünüm yerleştirilecek kolaylaştırır. `CTabView` olan bir `CView`-katıştırılmış içeren sınıf türetilmiş `CMFCTabCtrl` nesnesi. `CTabView` desteklemek için gereken tüm iletileri işleme `CMFCTabCtrl` nesnesi. Yalnızca öğesinden bir sınıf türetin `CTabView` ve uygulamanıza takın, ardından ekleyin `CView`-türetilmiş sınıfları kullanarak `AddView` yöntemi. Sekme denetimi bu görünümler sekmeleri... olarak görüntüler.  
  
 Örneğin, farklı şekillerde temsil edilebilir bir belge olabilir: bir elektronik tablo, grafik bir düzenlenebilir bir forma ve benzeri. Verileri gerektiğinde çizim tek bir görünüm oluşturun, bunların içine yerleştirin, `CTabView`-türetilen nesnesini ve bunları ek hiçbir kodlama olmadan sekmeli.  
  
 [TabbedView örnek: MFC sekmeli görünüm uygulama](../../visual-cpp-samples.md) kullanımını göstermektedir `CTabView`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği nasıl `CTabView` TabbedView örnek kullanılır.  
  
 [!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxTabView.h  
  
##  <a name="addview"></a>  CTabView::AddView  
 Bir görünüm sekme denetimi ekler.  
  
```  
int AddView(
    CRuntimeClass* pViewClass,  
    const CString& strViewLabel,  
    int iIndex=-1,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pViewClass`  
 Eklenen görünümünün bir çalışma zamanı sınıf için bir işaretçi.  
  
 [in] `strViewLabel`  
 Sekmenin metnini belirtir.  
  
 [in] `iIndex`  
 Görünüm eklenecek sıfır tabanlı konumunda belirtir. Konumu -1 olması durumunda yeni sekmede sonuna eklenir.  
  
 [in] `pContext`  
 Bir işaretçi `CCreateContext` görünüm.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa Görünüm dizini. Aksi durumda, -1.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçevede katıştırılmış sekme denetimi bir görünüm eklemek için bu işlevini çağırın.  
  
##  <a name="findtab"></a>  CTabView::FindTab  
 Belirtilen Görünüm dizini içinde Sekme denetimini döndürür.  
  
```  
int FindTab(HWND hWndView) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `hWndView`  
 Görünüm işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bulunursa görünümün dizinini; Aksi durumda, -1.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen tanıtıcı olan bir görünümde dizin almak için bu işlevini çağırın.  
  
##  <a name="getactiveview"></a>  CTabView::GetActiveView  
 Bir işaretçi şu anda etkin görünümüne döndürür.  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Etkin görünüm için geçerli bir işaretçi veya `NULL` etkin görünüm ise.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gettabcontrol"></a>  CTabView::GetTabControl  
 Sekme denetimi görünüm ile ilişkilendirilen bir başvuru döndürür.  
  
```  
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görünüm ile ilişkilendirilen sekme denetimi referansı.  
  
##  <a name="isscrollbar"></a>  CTabView::IsScrollBar  
 Sekmesi görünümü paylaşılan yatay kaydırma çubuğu olup olmadığını belirlemek için sekme görünüm oluşturulurken çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL IsScrollBar() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` sekmesi görünümü ile birlikte bir paylaşılan kaydırma çubuğunun oluşturuluyorsa. Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem framework çağırır olduğunda bir `CTabView` nesnesi oluşturuluyor.  
  
 Geçersiz kılma `IsScrollBar` yönteminde bir `CTabView`-türetilmiş sınıf ve return `TRUE` paylaşılan yatay kaydırma çubuğu sahip bir görünüm oluşturmak istiyorsanız.  
  
##  <a name="onactivateview"></a>  CTabView::OnActivateView  
 Etkin veya devre dışı sekmesi görünümü yapıldığında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnActivateView(CView* view);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `view`  
 Görünüm için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama hiçbir şey yapmaz. Bu yöntemi geçersiz kılın bir `CTabView`-türetilmiş sınıf bu bildirim işleyemedi.  
  
##  <a name="removeview"></a>  CTabView::RemoveView  
 Görünüm sekmesini denetiminden kaldırır.  
  
```  
BOOL RemoveView(int iTabNum);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iTabNum`  
 Kaldırmak için Görünüm dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa kaldırılan Görünüm dizini. Aksi takdirde-1.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setactiveview"></a>  CTabView::SetActiveView  
 Bir görünümü etkin hale getirir.  
  
```  
BOOL SetActiveView(int iTabNum);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iTabNum`  
 Sekmesi görünümü sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Belirtilen görünüm etkin yapılmışsa `FALSE` görünümün dizin geçersizse.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [CMFCTabCtrl::SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)   
 [CView Sınıfı](../../mfc/reference/cview-class.md)
