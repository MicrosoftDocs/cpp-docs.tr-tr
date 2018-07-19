---
title: CMFCAutoHideBar sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AddAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AllowShowOnPaneMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CalcFixedLayout
- AFXAUTOHIDEBAR/CMFCAutoHideBar::Create
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetFirstAHWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetVisibleCount
- AFXAUTOHIDEBAR/CMFCAutoHideBar::OnShowControlBarMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::RemoveAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetActiveInGroup
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetRecentVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::ShowAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::StretchPane
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UnSetAutoHideMode
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UpdateVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::m_nShowAHWndDelay
dev_langs:
- C++
helpviewer_keywords:
- CMFCAutoHideBar [MFC], CMFCAutoHideBar
- CMFCAutoHideBar [MFC], AddAutoHideWindow
- CMFCAutoHideBar [MFC], AllowShowOnPaneMenu
- CMFCAutoHideBar [MFC], CalcFixedLayout
- CMFCAutoHideBar [MFC], Create
- CMFCAutoHideBar [MFC], GetFirstAHWindow
- CMFCAutoHideBar [MFC], GetVisibleCount
- CMFCAutoHideBar [MFC], OnShowControlBarMenu
- CMFCAutoHideBar [MFC], RemoveAutoHideWindow
- CMFCAutoHideBar [MFC], SetActiveInGroup
- CMFCAutoHideBar [MFC], SetRecentVisibleState
- CMFCAutoHideBar [MFC], ShowAutoHideWindow
- CMFCAutoHideBar [MFC], StretchPane
- CMFCAutoHideBar [MFC], UnSetAutoHideMode
- CMFCAutoHideBar [MFC], UpdateVisibleState
- CMFCAutoHideBar [MFC], m_nShowAHWndDelay
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3278824e565f34a61943b466ccc6ffef9c4f0be0
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337029"
---
# <a name="cmfcautohidebar-class"></a>CMFCAutoHideBar sınıfı
`CMFCAutoHideBar` Otomatik gizleme özelliğini uygulayan bir özel araç sınıfı.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCAutoHideBar : public CPane  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCAutoHideBar::CMFCAutoHideBar](#cmfcautohidebar)||  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCAutoHideBar::AddAutoHideWindow](#addautohidewindow)||  
|[CMFCAutoHideBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Geçersiz kılmaları `CPane::AllowShowOnPaneMenu`.)|  
|[CMFCAutoHideBar::CalcFixedLayout](#calcfixedlayout)|(Geçersiz kılmaları [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCAutoHideBar::Create](#create)|Denetim çubuğu oluşturur ve ona ekler [CPane](../../mfc/reference/cpane-class.md) nesne. (Geçersiz kılmaları [CPane::Create](../../mfc/reference/cpane-class.md#create).)|  
|[CMFCAutoHideBar::GetFirstAHWindow](#getfirstahwindow)||  
|[CMFCAutoHideBar::GetVisibleCount](#getvisiblecount)||  
|[CMFCAutoHideBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|Özel bölmesinde menü gösterilmek üzereyken framework tarafından çağırılır. (Geçersiz kılmaları [CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|  
|[CMFCAutoHideBar::RemoveAutoHideWindow](#removeautohidewindow)||  
|[CMFCAutoHideBar::SetActiveInGroup](#setactiveingroup)|(Geçersiz kılmaları [CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).)|  
|[CMFCAutoHideBar::SetRecentVisibleState](#setrecentvisiblestate)||  
|[CMFCAutoHideBar::ShowAutoHideWindow](#showautohidewindow)||  
|[CMFCAutoHideBar::StretchPane](#stretchpane)|Bir bölme, yatay veya dikey olarak genişletir. (Geçersiz kılmaları [CBasePane::StretchPane](../../mfc/reference/cbasepane-class.md#stretchpane).)|  
|[CMFCAutoHideBar::UnSetAutoHideMode](#unsetautohidemode)||  
|[CMFCAutoHideBar::UpdateVisibleState](#updatevisiblestate)||  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCAutoHideBar::m_nShowAHWndDelay](#m_nshowahwnddelay)|Ne zaman kullanıcı yerleştirir fare imleci üzerinde şu arasındaki gecikme süresini bir [CMFCAutoHideButton sınıfı](../../mfc/reference/cmfcautohidebutton-class.md) ve ilişkili pencere görüntülendiğinde framework şu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanıcı bir yerleştirme bölmesi otomatik gizleme moduna geçirildiğinde, çerçeve otomatik olarak oluşturur bir `CMFCAutoHideBar` nesne. Ayrıca gerekli oluşturur [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) ve [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) nesneleri. Her `CAutoHideDockSite` nesnesi olan bir kişi ile ilişkili `CMFCAutoHideButton`.  
  
 `CMFCAutoHideBar` Sınıfın uyguladığı görüntüsünü bir `CAutoHideDockSite` kullanıcının fare geldiğinde üzerinden bir `CMFCAutoHideButton`. Araç bir WM_MOUSEMOVE iletisi aldığında `CMFCAutoHideBar` bir süreölçer başlatır. Zamanlayıcı sona erdiğinde, araç WM_TIMER olay bildirimi gönderir. Araç, fare işaretçisini Zamanlayıcı başlatıldığında üzerine yerleştirilmiş aynı otomatik gizleme düğmenin üzerine yerleştirilmiş olup olmadığını kontrol ederek bu olayını işler. Bu durumda, ekli `CAutoHideDockSite` görüntülenir.  
  
 Ayarlayarak Zamanlayıcının gecikme uzunluğunu kontrol edebilirsiniz `m_nShowAHWndDelay`. 400 ms varsayılan değerdir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `CMFCAutoHideBar` nesne ve kullanmak, `GetDockSiteRow` yöntemi.  
  
 [!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cmfcautohidebar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxautohidebar.h  
  
##  <a name="addautohidewindow"></a>  CMFCAutoHideBar::AddAutoHideWindow  
 İşlevsellik ekler bir `CDockablePane` pencere otomatik gizleme etkinleştirir.  
  
```  
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pAutoHideWnd*  
 Gizlemek istediğiniz penceresi.  
  
 [in] *dwAlignment*  
 Uygulama penceresiyle birlikte otomatik gizle düğmesi hizalamasını belirten bir değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 *DwAlignment* parametresi gösterir otomatik gizle düğmesi uygulamayı bulunduğu. Parametre aşağıdaki değerlerden biri olabilir:  
  
- CBRS_ALIGN_LEFT  
  
- CBRS_ALIGN_RIGHT  
  
- CBRS_ALIGN_TOP  
  
- CBRS_ALIGN_BOTTOM  
  
##  <a name="allowshowonpanemenu"></a>  CMFCAutoHideBar::AllowShowOnPaneMenu  

  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="calcfixedlayout"></a>  CMFCAutoHideBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bStretch*  
 [in] *bHorz*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="cmfcautohidebar"></a>  CMFCAutoHideBar::CMFCAutoHideBar  
 CMFCAutoHideBar bir nesne oluşturur.  
  
```  
CMFCAutoHideBar();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="create"></a>  CMFCAutoHideBar::Create  

  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszClassName*  
 [in] *dwStyle*  
 [in] *dikdörtgen*  
 [in] *pParentWnd*  
 [in] *nID*  
 [in] *dwControlBarStyle*  
 [in] *pContext*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getfirstahwindow"></a>  CMFCAutoHideBar::GetFirstAHWindow  
 Uygulamadaki ilk otomatik gizleme penceresine bir işaretçi döndürür.  
  
```  
CDockablePane* GetFirstAHWindow();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk otomatik gizleme penceresi uygulama ya da mevcut değilse NULL.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getvisiblecount"></a>  CMFCAutoHideBar::GetVisibleCount  
 Görünür otomatik gizleme düğmeleri sayısını alır.  
  
```  
int GetVisibleCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görünür otomatik gizleme düğmeleri sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_nshowahwnddelay"></a>  CMFCAutoHideBar::m_nShowAHWndDelay  
 Ne zaman kullanıcı yerleştirir fare imleci üzerinde şu arasındaki gecikme süresini bir [CMFCAutoHideButton sınıfı](../../mfc/reference/cmfcautohidebutton-class.md) ve ilişkili pencere görüntülendiğinde framework şu.  
  
```  
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ne zaman kullanıcı yerleştirir fare imleci üzerine bir `CMFCAutoHideButton`, ilişkili pencere çerçevesi görüntülemeden önce hafif bir gecikme olur. Bu parametre, milisaniye cinsinden gecikme uzunluğunu belirler.  
  
##  <a name="onshowcontrolbarmenu"></a>  CMFCAutoHideBar::OnShowControlBarMenu  

  
```  
virtual BOOL OnShowControlBarMenu(CPoint);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *CPoint*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removeautohidewindow"></a>  CMFCAutoHideBar::RemoveAutoHideWindow  
 Kaldırır ve otomatik gizleme penceresini yok eder.  
  
```  
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 CDockablePane * *pAutoHideWnd*  
 Kaldırmak için otomatik gizleme penceresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setactiveingroup"></a>  CMFCAutoHideBar::SetActiveInGroup  
 Bir otomatik gizleme Çubuğu etkin olarak işaretler.  
  
```  
virtual void SetActiveInGroup(BOOL bActive);  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] BOOL *bActive*  
 Etkin olarak için TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).  
  
##  <a name="setrecentvisiblestate"></a>  CMFCAutoHideBar::SetRecentVisibleState  

  
```  
void SetRecentVisibleState(BOOL bState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bState*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="showautohidewindow"></a>  CMFCAutoHideBar::ShowAutoHideWindow  
 Pencere otomatik gizleme gösterir.  
  
```  
BOOL ShowAutoHideWindow(
        CDockablePane* pAutoHideWnd,  
        BOOL bShow,  
        BOOL bDelay);  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] CDockablePane * *pAutoHideWnd*  
 [in] BOOL *bBilgi Göster*  
 Penceresini görüntülemek için TRUE.  
  
 [in] BOOL *bDelay*  
 Bu parametre yoksayıldı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="stretchpane"></a>  CMFCAutoHideBar::StretchPane  
 Otomatik gizleme çubuğu sığdırmak için daraltılmış durumunda yeniden boyutlandırır `CMFCAutoHideButton` nesne.  
  
```  
virtual CSize StretchPane(
    int nLength,   
    BOOL bVert);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nLength*  
 Temel uygulamada değer kullanılmıyor. Türetilmiş uygulamalarında, yeniden boyutlandırılan bölmesinde uzunluğunu belirtmek için bu değeri kullanın.  
  
 [in] *bVert*  
 Temel uygulamada değer kullanılmıyor. Türetilmiş uygulamalarında, tanıtıcı burada otomatik gizleme çubuk dikey daraltılmış durumda ve FALSE true nerede otomatik gizleme çubuk yatay olarak daraltılmıştır çalışması için kullanın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeniden boyutlandırılan bölmesinde elde edilen boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen sınıfların davranışını özelleştirmek için bu yöntemin üzerine yazabilir.  
  
##  <a name="unsetautohidemode"></a>  CMFCAutoHideBar::UnSetAutoHideMode  
 Devre dışı bırakır otomatik bir grubu otomatik gizleme çubuk modunu gizleme.  
  
```  
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] pFirstBarInGroup  
 İlk otomatik gizleme çubuğunda bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="updatevisiblestate"></a>  CMFCAutoHideBar::UpdateVisibleState  
 Otomatik gizleme çubuğu çizilmesi gerektiğinde framework tarafından çağırılır.  
  
```  
void UpdateVisibleState();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CPane sınıfı](../../mfc/reference/cpane-class.md)   
 [CAutoHideDockSite sınıfı](../../mfc/reference/cautohidedocksite-class.md)   
 [CMFCAutoHideButton Sınıfı](../../mfc/reference/cmfcautohidebutton-class.md)
