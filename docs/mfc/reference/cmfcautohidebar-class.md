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
ms.openlocfilehash: 7d9c60ee3601cd4055e963997a6cd4f8bbd48b14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcautohidebar-class"></a>CMFCAutoHideBar sınıfı
`CMFCAutoHideBar` Sınıftır otomatik gizleme özelliğini uygulayan bir özel araç.  

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
|[CMFCAutoHideBar::Create](#create)|Denetim çubuğu oluşturur ve ona ekler [CPane](../../mfc/reference/cpane-class.md) nesnesi. (Geçersiz kılmaları [CPane::Create](../../mfc/reference/cpane-class.md#create).)|  
|[CMFCAutoHideBar::GetFirstAHWindow](#getfirstahwindow)||  
|[CMFCAutoHideBar::GetVisibleCount](#getvisiblecount)||  
|[CMFCAutoHideBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|Özel bölmesi menüsünde görüntülenmek üzere olduğunda çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|  
|[CMFCAutoHideBar::RemoveAutoHideWindow](#removeautohidewindow)||  
|[CMFCAutoHideBar::SetActiveInGroup](#setactiveingroup)|(Geçersiz kılmaları [CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).)|  
|[CMFCAutoHideBar::SetRecentVisibleState](#setrecentvisiblestate)||  
|[CMFCAutoHideBar::ShowAutoHideWindow](#showautohidewindow)||  
|[CMFCAutoHideBar::StretchPane](#stretchpane)|Dikey veya yatay bölme uzatır. (Geçersiz kılmaları [CBasePane::StretchPane](../../mfc/reference/cbasepane-class.md#stretchpane).)|  
|[CMFCAutoHideBar::UnSetAutoHideMode](#unsetautohidemode)||  
|[CMFCAutoHideBar::UpdateVisibleState](#updatevisiblestate)||  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCAutoHideBar::m_nShowAHWndDelay](#m_nshowahwnddelay)|Ne zaman kullanıcı yerleştirir fare imlecini üzerinde şu anda arasındaki gecikme süresini bir [CMFCAutoHideButton sınıfı](../../mfc/reference/cmfcautohidebutton-class.md) ve ne zaman framework gösterir ilişkili pencere süre.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanıcı bir yerleştirme bölmesinde otomatik olarak gizle moduna geçirildiğinde framework otomatik olarak oluşturur bir `CMFCAutoHideBar` nesnesi. Ayrıca gerekli oluşturur [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) ve [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) nesneleri. Her `CAutoHideDockSite` nesnesidir ile tek bir ilişkili `CMFCAutoHideButton`.  
  
 `CMFCAutoHideBar` Sınıfı görüntüsünü uygulayan bir `CAutoHideDockSite` , kullanıcının fare gezinen üzerinden bir `CMFCAutoHideButton`. Araç çubuğu bir WM_MOUSEMOVE iletisi aldığında `CMFCAutoHideBar` bir süreölçer başlatır. Zamanlayıcı sona erdiğinde, araç WM_TIMER olay bildirim gönderir. Araç, fare işaretçisini Zamanlayıcı başlatıldığında üzerine yerleştirilmiş aynı otomatik gizleme düğmenin üzerine yerleştirilmiş olup olmadığını kontrol ederek bu olayını işler. Bu durumda, ekli `CAutoHideDockSite` görüntülenir.  
  
 Zamanlayıcı'nın gecikme uzunluğunu ayarlayarak denetleyebilirsiniz `m_nShowAHWndDelay`. 400 ms varsayılan değerdir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösteren bir `CMFCAutoHideBar` nesne ve kullanmak, `GetDockSiteRow` yöntemi.  
  
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
 İşlevlerini ekler bir `CDockablePane` penceresi otomatik olarak gizle sağlar.  
  
```  
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pAutoHideWnd`  
 Gizlemek istediğiniz penceresini açın.  
  
 [in] `dwAlignment`  
 Uygulama penceresi ile otomatik olarak gizle düğmesi hizalamasını belirten bir değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 `dwAlignment` Parametre, otomatik olarak gizle düğmesi uygulamada bulunduğu belirtir. Parametresi şu değerlerden biri olabilir:  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
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
 [in] `bStretch`  
 [in] `bHorz`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="cmfcautohidebar"></a>  CMFCAutoHideBar::CMFCAutoHideBar  
 CMFCAutoHideBar nesnesi oluşturur.  
  
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
 [in] `lpszClassName`  
 [in] `dwStyle`  
 [in] `rect`  
 [in] `pParentWnd`  
 [in] `nID`  
 [in] `dwControlBarStyle`  
 [in] `pContext`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getfirstahwindow"></a>  CMFCAutoHideBar::GetFirstAHWindow  
 Uygulamayı ilk otomatik gizleme penceresinde bir işaretçi döndürür.  
  
```  
CDockablePane* GetFirstAHWindow();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk otomatik gizleme penceresinde uygulama veya hiç yoksa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getvisiblecount"></a>  CMFCAutoHideBar::GetVisibleCount  
 Görünür otomatik olarak gizle düğmeleri sayısını alır.  
  
```  
int GetVisibleCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görünür otomatik olarak gizle düğmeleri sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_nshowahwnddelay"></a>  CMFCAutoHideBar::m_nShowAHWndDelay  
 Ne zaman kullanıcı yerleştirir fare imlecini üzerinde şu anda arasındaki gecikme süresini bir [CMFCAutoHideButton sınıfı](../../mfc/reference/cmfcautohidebutton-class.md) ve ne zaman framework gösterir ilişkili pencere süre.  
  
```  
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ne zaman kullanıcı yerleştirir fare imlecini üzerinden bir `CMFCAutoHideButton`, ilişkili pencere çerçevesi görüntülemeden önce küçük bir gecikme olur. Bu parametre, milisaniye cinsinden gecikme uzunluğunu belirler.  
  
##  <a name="onshowcontrolbarmenu"></a>  CMFCAutoHideBar::OnShowControlBarMenu  

  
```  
virtual BOOL OnShowControlBarMenu(CPoint);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `CPoint`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removeautohidewindow"></a>  CMFCAutoHideBar::RemoveAutoHideWindow  
 Kaldırır ve otomatik olarak gizle penceresi yok eder.  
  
```  
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 CDockablePane * `pAutoHideWnd`  
 Kaldırmak için otomatik olarak gizle penceresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setactiveingroup"></a>  CMFCAutoHideBar::SetActiveInGroup  
 Bir otomatik olarak gizle Çubuğu etkin olarak işaretler.  
  
```  
virtual void SetActiveInGroup(BOOL bActive);  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] BOOL `bActive`  
 Etkin olarak için TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).  
  
##  <a name="setrecentvisiblestate"></a>  CMFCAutoHideBar::SetRecentVisibleState  

  
```  
void SetRecentVisibleState(BOOL bState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bState`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="showautohidewindow"></a>  CMFCAutoHideBar::ShowAutoHideWindow  
 Otomatik olarak gizle penceresi gösterir.  
  
```  
BOOL ShowAutoHideWindow(
        CDockablePane* pAutoHideWnd,  
        BOOL bShow,  
        BOOL bDelay);  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] CDockablePane * `pAutoHideWnd`  
 [in] BOOL `bShow`  
 Pencereyi göstermek için TRUE.  
  
 [in] BOOL `bDelay`  
 Bu parametre yoksayıldı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="stretchpane"></a>  CMFCAutoHideBar::StretchPane  
 Daraltılmış durumuna sığması için otomatik olarak gizle çubuğunda yeniden boyutlandırır `CMFCAutoHideButton` nesnesi.  
  
```  
virtual CSize StretchPane(
    int nLength,   
    BOOL bVert);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nLength`  
 Değer taban uygulamasında kullanılmıyor. Türetilen uygulamalarında, bu değer yeniden boyutlandırılan bölmesinde uzunluğunu belirtmek için kullanın.  
  
 [in] `bVert`  
 Değer taban uygulamasında kullanılmıyor. Türetilen uygulamalarında kullanımı `TRUE` burada çubuğunu otomatik gizle daraltıldığında dikey olarak durumu işlemek için ve `FALSE` nerede çubuğunu otomatik gizle daraltıldığında yatay olarak çalışması için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeniden boyutlandırılan bölmesinde elde edilen boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen sınıflar davranışını özelleştirmek için bu yöntemi geçersiz kılabilirsiniz.  
  
##  <a name="unsetautohidemode"></a>  CMFCAutoHideBar::UnSetAutoHideMode  
 Devre dışı bırakır otomatik modu otomatik olarak gizle çubukları grubu için Gizle.  
  
```  
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)  
```  
  
### <a name="parameters"></a>Parametreler  
 pFirstBarInGroup [in]  
 Çubuğunu otomatik gizle grubundaki bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="updatevisiblestate"></a>  CMFCAutoHideBar::UpdateVisibleState  
 Otomatik olarak gizle çubuğu çizilmesi gerektiğinde çerçevesi tarafından çağrılır.  
  
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
