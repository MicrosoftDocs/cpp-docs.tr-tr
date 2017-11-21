---
title: "CTabbedPane sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTabbedPane
- AFXTABBEDPANE/CTabbedPane
- AFXTABBEDPANE/CTabbedPane::DetachPane
- AFXTABBEDPANE/CTabbedPane::EnableTabAutoColor
- AFXTABBEDPANE/CTabbedPane::FloatTab
- AFXTABBEDPANE/CTabbedPane::GetTabArea
- AFXTABBEDPANE/CTabbedPane::GetTabWnd
- AFXTABBEDPANE/CTabbedPane::HasAutoHideMode
- AFXTABBEDPANE/CTabbedPane::IsTabLocationBottom
- AFXTABBEDPANE/CTabbedPane::ResetTabs
- AFXTABBEDPANE/CTabbedPane::SetTabAutoColors
- AFXTABBEDPANE/CTabbedPane::m_bTabsAlwaysTop
- AFXTABBEDPANE/CTabbedPane::m_pTabWndRTC
dev_langs: C++
helpviewer_keywords:
- CTabbedPane [MFC], DetachPane
- CTabbedPane [MFC], EnableTabAutoColor
- CTabbedPane [MFC], FloatTab
- CTabbedPane [MFC], GetTabArea
- CTabbedPane [MFC], GetTabWnd
- CTabbedPane [MFC], HasAutoHideMode
- CTabbedPane [MFC], IsTabLocationBottom
- CTabbedPane [MFC], ResetTabs
- CTabbedPane [MFC], SetTabAutoColors
- CTabbedPane [MFC], m_bTabsAlwaysTop
- CTabbedPane [MFC], m_pTabWndRTC
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 00bb0d4bcecd40260dd0ce453736e78996309b29
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ctabbedpane-class"></a>CTabbedPane sınıfı
Çıkarılabilir sekmeleri bölmesiyle işlevlerini uygular.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CTabbedPane : public CBaseTabbedPane  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CTabbedPane::CTabbedPane`|Varsayılan Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTabbedPane::DetachPane](#detachpane)|(Geçersiz kılmaları [CBaseTabbedPane::DetachPane](../../mfc/reference/cbasetabbedpane-class.md#detachpane).)|  
|[CTabbedPane::EnableTabAutoColor](#enabletabautocolor)|Etkinleştirir veya sekmelerinin otomatik renklendirme devre dışı bırakır.|  
|[CTabbedPane::FloatTab](#floattab)|Bölmesinde şu anda çıkarılabilir bir sekmede bulunuyorsa ancak yalnızca bir bölme kayar. (Geçersiz kılmaları [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|  
|[CTabbedPane::GetTabArea](#gettabarea)|Sekmeli penceresinde sekme alanı konumu ve boyutu döndürür.|  
|[CTabbedPane::GetTabWnd](#gettabwnd)||  
|[CTabbedPane::HasAutoHideMode](#hasautohidemode)|Sekmeli bölmesinde autohide moduna geçiş olup olmadığını belirler. (Geçersiz kılmaları [CBaseTabbedPane::HasAutoHideMode](../../mfc/reference/cbasetabbedpane-class.md#hasautohidemode).)|  
|[CTabbedPane::IsTabLocationBottom](#istablocationbottom)|Sekmeleri penceresinin alt kısmında bulunan olup olmadığını belirler.|  
|[CTabbedPane::ResetTabs](#resettabs)|Tüm sekmeli bölmeleri varsayılan durumuna sıfırlar.|  
|[CTabbedPane::SetTabAutoColors](#settabautocolors)|Otomatik Renk özelliği etkinleştirilmişse, kullanılabilen özel renk listesi ayarlar.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTabbedPane::m_bTabsAlwaysTop](#m_btabsalwaystop)|Uygulamadaki sekmeler için varsayılan konum.|  
|[CTabbedPane::m_pTabWndRTC](#m_ptabwndrtc)|Özel bir çalışma zamanı sınıf bilgileri `CMFCTabCtrl`-türetilmiş bir nesne içermelidir.|  
  
## <a name="remarks"></a>Açıklamalar  
 İkinci bölümde resim yazısı işaret eden bir kullanıcı bir bölme iliştirir framework otomatik olarak bu sınıfının bir örneğini oluşturur. Tüm çerçevesi tarafından oluşturulan sekmeli bölmeleri-1 bir Kimliğe sahip.  
  
 Outlook stil sekmeleri yerine normal sekme belirtmek için geçirmek `AFX_CBRS_REGULAR_TABS` için stil [CDockablePane::CreateEx](../../mfc/reference/cdockablepane-class.md#createex) yöntemi.  
  
 Sekmeli bölmesinde çıkarılabilir sekmelerle oluşturursanız, işaretçi depolamamayı şekilde bölmesinde otomatik olarak çerçevesi tarafından yok edilmesi. Sekmeli bölmesine bir işaretçi almak için arama `CBasePane::GetParentTabbedPane` yöntemi.  
  
## <a name="example"></a>Örnek  
 Bu örnekte oluşturuyoruz bir `CTabbedPane` nesnesi. Ardından, kullandığımız [CBaseTabbedPane::AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) ek sekmeler eklemek için.  
  
```  
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);

if (!pTabbededBar->Create (_T(""),
    this,
    CRect (0,
    0,
    200,
    200),  
    TRUE, 
 (UINT) -1,  
    WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |  
    WS_CLIPCHILDREN | CBRS_LEFT |    
    CBRS_FLOAT_MULTI)) 
{  
    TRACE0("Failed to create Solution Explorer bar\n");

    return FALSE;      // fail to create  
}  
 
pTabbededBar->AddTab (&m_wndClassView);
pTabbededBar->AddTab (&m_wndResourceView);

pTabbededBar->AddTab (&m_wndFileView);
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);

DockPane(pTabbededBar);
```  
  
## <a name="example"></a>Örnek  
 Sekmeli denetim çubuğu nesnesi oluşturmak için başka bir yolu kullanmaktır [CDockablePane::AttachToTabWnd](../../mfc/reference/cdockablepane-class.md#attachtotabwnd). `AttachToTabWnd` Yöntemi tarafından belirlenen çalışma zamanı sınıf bilgileri kullanarak bir sekmeli bölmesinde nesnesi dinamik olarak oluşturur [CDockablePane::SetTabbedPaneRTC](../../mfc/reference/cdockablepane-class.md#settabbedpanertc).  
  
 Bu örnekte, dinamik olarak oluşturuyoruz sekmeli bölmesi iki sekme ekleme ve ikinci sekmesinde çıkarılabilir olmayan olun.  
  
```  
DockPane(&m_wndClassView);

CTabbedPane* pTabbedBar = NULL;  
m_wndResourceView.AttachToTabWnd (&m_wndClassView,
    DM_SHOW,
    TRUE,  
 (CDockablePane**) &pTabbedBar);

m_wndFileView.AttachToTabWnd (pTabbedBar,
    DM_SHOW,
    TRUE,  
 (CDockablePane**) &pTabbedBar);

pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1,
    FALSE);
```  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CTabbedPane](../../mfc/reference/ctabbedpane-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxTabbedPane.h  
  
##  <a name="detachpane"></a>CTabbedPane::DetachPane  

  
```  
virtual BOOL DetachPane(
    CWnd* pBar,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 [in]`bHide`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enabletabautocolor"></a>CTabbedPane::EnableTabAutoColor  
 Etkinleştirir veya sekmelerinin otomatik renklendirme devre dışı bırakır.  
  
```  
static void EnableTabAutoColor(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
 `TRUE`Sekme otomatik renklendirme etkinleştirmek için; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Etkinleştirmek veya uygulamadaki tüm sekmeli bölmelerinde sekmelerinin otomatik renklendirme devre dışı bırakmak için statik bu yöntemi kullanın. Bu özellik etkinleştirildiğinde, her sekme kendi renge göre doldurulur. Sekmeleri çağırarak renk için kullanılan renk listesi bulabilirsiniz [CMFCBaseTabCtrl::GetAutoColors](../../mfc/reference/cmfcbasetabctrl-class.md#getautocolors) yöntemi.  
  
 Sekmeleri çağırarak kullanılacak renk listesi belirtebilirsiniz [CTabbedPane::SetTabAutoColors](#settabautocolors).  
  
 Varsayılan olarak, bu seçenek devre dışıdır.  
  
##  <a name="floattab"></a>CTabbedPane::FloatTab  

  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 [in]`nTabID`  
 [in]`dockMethod`  
 [in]`bHide`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gettabarea"></a>CTabbedPane::GetTabArea  
 Sekmeli penceresinde sekme alanı konumu ve boyutu döndürür.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`rectTabAreaTop`  
 Boyutunu ve konumunu, ekran koordinatları üst sekme alanı içerir.  
  
 [out]`rectTabAreaBottom`  
 Boyutunu ve konumunu, ekran koordinatları alt sekme alanı içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework'te kullanıcı sürükleyerek bir bölme sabitlemek nasıl belirlemek için bu yöntemi çağırır. Kullanıcı hedef bölmesinde sekme alanı bir bölme sürüklendiğinde framework hedef bölmesinde yeni bir sekme eklemeyi dener. Aksi takdirde, yeni bir bölmesinde kapsayıcı iki bölmeyi ayıran bir bölmesinde ayırıcı oluşturursunuz hedef bölmesinde tarafına bölmesinde sabitlemek çalışır.  
  
 Bu yöntemi geçersiz kılın bir `CTabbedPane`-türetilmiş sınıf bu davranışı değiştirmek için.  
  
##  <a name="gettabwnd"></a>CTabbedPane::GetTabWnd  

  
```  
CMFCTabCtrl* GetTabWnd() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hasautohidemode"></a>CTabbedPane::HasAutoHideMode  

  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="istablocationbottom"></a>CTabbedPane::IsTabLocationBottom  
 Sekmeleri penceresinin alt kısmında bulunan olup olmadığını belirler.  
  
```  
virtual BOOL IsTabLocationBottom() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Sekme alanı sekmeli penceresinin alt kısmında bulunur Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_btabsalwaystop"></a>CTabbedPane::m_bTabsAlwaysTop  
 Uygulamadaki sekmeler için varsayılan konum.  
  
```  
AFX_IMPORT_DATA static BOOL m_bTabsAlwaysTop;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu statik üye kümesine `TRUE` sekmeli bölmenin en üstünde görüntülenecek uygulamadaki tüm sekmeler zorlamak için.  
  
 Sekmeli bölmesinde oluşturulmadan önce bu değer ayarlamanız gerekir.  
  
 Varsayılan değer `FALSE` şeklindedir.  
  
##  <a name="m_ptabwndrtc"></a>CTabbedPane::m_pTabWndRTC  
 Özel bir çalışma zamanı sınıf bilgileri `CMFCTabCtrl`-türetilmiş bir nesne içermelidir.  
  
```  
AFX_IMPORT_DATA static CRuntimeClass* m_pTabWndRTC;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı sınıf bilgileri için bir işaretçi bu statik üye değişkeni koymak bir `CMFCTabCtrl`-sekmeli bölmesinde özel sekmeli penceresine kullanıyorsanız, nesne türetilmiş.  
  
##  <a name="resettabs"></a>CTabbedPane::ResetTabs  
 Tüm sekmeli bölmeleri varsayılan durumuna sıfırlar.  
  
```  
static void ResetTabs();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm sekmeli bölmeleri varsayılan durumlarına döndürmek için bu yöntemi çağırın. Çağrıldığında, bu yöntem kenarlık boyutları ve otomatik renk tüm sekmeli bölmeleri durumunu sıfırlar.  
  
##  <a name="settabautocolors"></a>CTabbedPane::SetTabAutoColors  
 Otomatik Renk özelliği etkinleştirilmişse, kullanılan özel renk listesi ayarlar.  
  
```  
static void SetTabAutoColors(const CArray<COLORREF, COLORREF>& arColors);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`arColors`  
 Ayarlamak için renk dizisi içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Otomatik Renk özelliği etkinleştirilmişse, kullanılan renk listesi özelleştirmek için bu yöntemi kullanın. Bu statik işlev ve uygulamanızdaki tüm sekmeli bölmeleri etkiler.  
  
 Kullanım [CTabbedPane::EnableTabAutoColor](#enabletabautocolor) etkinleştirmek veya otomatik renk özelliğini devre dışı bırakmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md)   
 [CBaseTabbedPane sınıfı](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)
