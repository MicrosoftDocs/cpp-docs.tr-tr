---
title: CPane sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPane
- AFXPANE/CPane
- AFXPANE/CPane::AdjustSizeImmediate
- AFXPANE/CPane::AllocElements
- AFXPANE/CPane::AllowShowOnPaneMenu
- AFXPANE/CPane::CalcAvailableSize
- AFXPANE/CPane::CalcInsideRect
- AFXPANE/CPane::CalcRecentDockedRect
- AFXPANE/CPane::CalcSize
- AFXPANE/CPane::CanBeDocked
- AFXPANE/CPane::CanBeTabbedDocument
- AFXPANE/CPane::ConvertToTabbedDocument
- AFXPANE/CPane::CopyState
- AFXPANE/CPane::Create
- AFXPANE/CPane::CreateDefaultMiniframe
- AFXPANE/CPane::CreateEx
- AFXPANE/CPane::DockByMouse
- AFXPANE/CPane::DockPane
- AFXPANE/CPane::DockPaneStandard
- AFXPANE/CPane::DockToFrameWindow
- AFXPANE/CPane::DoesAllowSiblingBars
- AFXPANE/CPane::FloatPane
- AFXPANE/CPane::GetAvailableExpandSize
- AFXPANE/CPane::GetAvailableStretchSize
- AFXPANE/CPane::GetBorders
- AFXPANE/CPane::GetClientHotSpot
- AFXPANE/CPane::GetDockSiteRow
- AFXPANE/CPane::GetExclusiveRowMode
- AFXPANE/CPane::GetHotSpot
- AFXPANE/CPane::GetMinSize
- AFXPANE/CPane::GetPaneName
- AFXPANE/CPane::GetVirtualRect
- AFXPANE/CPane::IsChangeState
- AFXPANE/CPane::IsDragMode
- AFXPANE/CPane::IsInFloatingMultiPaneFrameWnd
- AFXPANE/CPane::IsLeftOf
- AFXPANE/CPane::IsResizable
- AFXPANE/CPane::IsTabbed
- AFXPANE/CPane::LoadState
- AFXPANE/CPane::MoveByAlignment
- AFXPANE/CPane::MovePane
- AFXPANE/CPane::OnAfterChangeParent
- AFXPANE/CPane::OnBeforeChangeParent
- AFXPANE/CPane::OnPressCloseButton
- AFXPANE/CPane::OnShowControlBarMenu
- AFXPANE/CPane::RecalcLayout
- AFXPANE/CPane::SaveState
- AFXPANE/CPane::SetActiveInGroup
- AFXPANE/CPane::SetBorders
- AFXPANE/CPane::SetClientHotSpot
- AFXPANE/CPane::SetDockState
- AFXPANE/CPane::SetExclusiveRowMode
- AFXPANE/CPane::SetMiniFrameRTC
- AFXPANE/CPane::SetMinSize
- AFXPANE/CPane::SetVirtualRect
- AFXPANE/CPane::StretchPaneDeferWndPos
- AFXPANE/CPane::ToggleAutoHide
- AFXPANE/CPane::UndockPane
- AFXPANE/CPane::UpdateVirtualRect
- AFXPANE/CPane::OnAfterDock
- AFXPANE/CPane::OnAfterFloat
- AFXPANE/CPane::OnBeforeDock
- AFXPANE/CPane::OnBeforeFloat
- AFXPANE/CPane::m_bHandleMinSize
- AFXPANE/CPane::m_recentDockInfo
dev_langs:
- C++
helpviewer_keywords:
- CPane [MFC], AdjustSizeImmediate
- CPane [MFC], AllocElements
- CPane [MFC], AllowShowOnPaneMenu
- CPane [MFC], CalcAvailableSize
- CPane [MFC], CalcInsideRect
- CPane [MFC], CalcRecentDockedRect
- CPane [MFC], CalcSize
- CPane [MFC], CanBeDocked
- CPane [MFC], CanBeTabbedDocument
- CPane [MFC], ConvertToTabbedDocument
- CPane [MFC], CopyState
- CPane [MFC], Create
- CPane [MFC], CreateDefaultMiniframe
- CPane [MFC], CreateEx
- CPane [MFC], DockByMouse
- CPane [MFC], DockPane
- CPane [MFC], DockPaneStandard
- CPane [MFC], DockToFrameWindow
- CPane [MFC], DoesAllowSiblingBars
- CPane [MFC], FloatPane
- CPane [MFC], GetAvailableExpandSize
- CPane [MFC], GetAvailableStretchSize
- CPane [MFC], GetBorders
- CPane [MFC], GetClientHotSpot
- CPane [MFC], GetDockSiteRow
- CPane [MFC], GetExclusiveRowMode
- CPane [MFC], GetHotSpot
- CPane [MFC], GetMinSize
- CPane [MFC], GetPaneName
- CPane [MFC], GetVirtualRect
- CPane [MFC], IsChangeState
- CPane [MFC], IsDragMode
- CPane [MFC], IsInFloatingMultiPaneFrameWnd
- CPane [MFC], IsLeftOf
- CPane [MFC], IsResizable
- CPane [MFC], IsTabbed
- CPane [MFC], LoadState
- CPane [MFC], MoveByAlignment
- CPane [MFC], MovePane
- CPane [MFC], OnAfterChangeParent
- CPane [MFC], OnBeforeChangeParent
- CPane [MFC], OnPressCloseButton
- CPane [MFC], OnShowControlBarMenu
- CPane [MFC], OnShowControlBarMenu
- CPane [MFC], RecalcLayout
- CPane [MFC], SaveState
- CPane [MFC], SetActiveInGroup
- CPane [MFC], SetBorders
- CPane [MFC], SetClientHotSpot
- CPane [MFC], SetDockState
- CPane [MFC], SetExclusiveRowMode
- CPane [MFC], SetMiniFrameRTC
- CPane [MFC], SetMinSize
- CPane [MFC], SetVirtualRect
- CPane [MFC], StretchPaneDeferWndPos
- CPane [MFC], ToggleAutoHide
- CPane [MFC], UndockPane
- CPane [MFC], UpdateVirtualRect
- CPane [MFC], OnAfterDock
- CPane [MFC], OnAfterFloat
- CPane [MFC], OnBeforeDock
- CPane [MFC], OnBeforeFloat
- CPane [MFC], m_bHandleMinSize
- CPane [MFC], m_recentDockInfo
ms.assetid: 5c651a64-3c79-4d94-9676-45f6402a6bc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8de4afadd51d9446a57b8d68fbcda337a650e984
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079922"
---
# <a name="cpane-class"></a>CPane sınıfı
`CPane` Sınıfı, bir geliştirmesini [CControlBar sınıfı](../../mfc/reference/ccontrolbar-class.md). Varolan bir MFC projesine yükseltiyorsanız, tüm oluşumlarını Değiştir `CControlBar` ile `CPane`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPane : public CBasePane  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CPane::~CPane`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPane::AdjustSizeImmediate](#adjustsizeimmediate)|Hemen bir bölme düzenini yeniden hesaplar.|  
|[CPane::AllocElements](#allocelements)|Depolama iç kullanımı için ayırır.|  
|[CPane::AllowShowOnPaneMenu](#allowshowonpanemenu)|Bölmesinde bölmeleri uygulamanın çalışma zamanı modülü tarafından oluşturulan listesinde listelenen olup olmadığını belirtir.|  
|[CPane::CalcAvailableSize](#calcavailablesize)|Boyutu belirtilen dikdörtgen ve geçerli pencere dikdörtgeni arasındaki farkı hesaplar.|  
|[CPane::CalcInsideRect](#calcinsiderect)|İç hesaplar Kenarlıklar ve kavrayıcılar dikkate alarak, bir bölme dikdörtgen.|  
|[CPane::CalcRecentDockedRect](#calcrecentdockedrect)|Yakın zamanda yerleşik dikdörtgen hesaplar.|  
|[CPane::CalcSize](#calcsize)|Bölmesinin boyutunu hesaplar.|  
|[CPane::CanBeDocked](#canbedocked)|Belirtilen temel bölmesinde bölmesinde yerleştirilmiş olup olmadığını belirler.|  
|[CPane::CanBeTabbedDocument](#canbetabbeddocument)|Sekmeli belge bölmesinde dönüştürülüp dönüştürülemeyeceğini belirler.|  
|[CPane::ConvertToTabbedDocument](#converttotabbeddocument)|Sekmeli Belge dockable bölmesinde dönüştürür.|  
|[CPane::CopyState](#copystate)|Bir bölme durumunu kopyalar. (Geçersiz kılmaları [CBasePane::CopyState](../../mfc/reference/cbasepane-class.md#copystate).)|  
|[CPane::Create](#create)|Denetim çubuğu oluşturur ve ona ekler `CPane` nesnesi.|  
|[CPane::CreateDefaultMiniframe](#createdefaultminiframe)|Kayan bölmesi için bir kısa çerçeve penceresi oluşturur.|  
|[CPane::CreateEx](#createex)|Denetim çubuğu oluşturur ve ona ekler `CPane` nesnesi.|  
|`CPane::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|[CPane::DockByMouse](#dockbymouse)|Bir bölme yöntemi yerleştirme fare kullanarak docks.|  
|[CPane::DockPane](#dockpane)|Kayan bölmesinde bir temel bölmesine docks.|  
|[CPane::DockPaneStandard](#dockpanestandard)|Bir bölme anahat (standart) yerleştirme kullanarak docks.|  
|[CPane::DockToFrameWindow](#docktoframewindow)|Dockable bölmesinde çerçeveye docks. (Geçersiz kılmaları `CBasePane::DockToFrameWindow`.)|  
|[CPane::DoesAllowSiblingBars](#doesallowsiblingbars)|Geçerli bölmesini nereye yerleştirilir aynı satırındaki başka bir bölüme yerleştirme olup olmadığını gösterir.|  
|[CPane::FloatPane](#floatpane)|Bölmesinde kayar.|  
|[CPane::GetAvailableExpandSize](#getavailableexpandsize)|Tutar bölmeyi genişletebilirsiniz piksel cinsinden döndürür.|  
|[CPane::GetAvailableStretchSize](#getavailablestretchsize)|Tutar bölmesinde küçültebilirsiniz piksel cinsinden döndürür.|  
|[CPane::GetBorders](#getborders)|Bölmenin kenarlık genişliğini döndürür.|  
|[CPane::GetClientHotSpot](#getclienthotspot)|Döndürür *etkin nokta* bölmesi.|  
|[CPane::GetDockSiteRow](#getdocksiterow)|Bölmenin yerleştirilmiş olup yerleştirme satır döndürür.|  
|[CPane::GetExclusiveRowMode](#getexclusiverowmode)|Bölmesi Dışlayıcı row modunda olup olmadığını belirler.|  
|[CPane::GetHotSpot](#gethotspot)|Bir temel depolanan etkin nokta döndürür `CMFCDragFrameImpl` nesnesi.|  
|[CPane::GetMinSize](#getminsize)|Bölmesinde boyutu izin verilen en düşük alır.|  
|[CPane::GetPaneName](#getpanename)|Bölmesinde başlığını alır.|  
|`CPane::GetResizeStep`|Dahili olarak kullanılır.|  
|`CPane::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CPane::GetVirtualRect](#getvirtualrect)|Alır *sanal dikdörtgen* bölmesinin.|  
|[CPane::IsChangeState](#ischangestate)|Bölmesinde taşınmış gibi bu yöntem bölmesinde diğer bölmeleri, yerleştirme satırları ve kısa çerçeve pencereleri göreli konumunu analiz eder ve uygun döndürür `AFX_CS_STATUS` değeri.|  
|[CPane::IsDragMode](#isdragmode)|Bölmesinde sürüklenen olup olmadığını belirtir.|  
|[CPane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Bölmesinde çok bölmesi çerçeve penceresinde olup olmadığını belirtir. (Geçersiz kılmaları `CBasePane::IsInFloatingMultiPaneFrameWnd`.)|  
|[CPane::IsLeftOf](#isleftof)|Bölmesinde, (veya üstü) sola mı olduğunu belirler belirtilen dikdörtgen.|  
|[CPane::IsResizable](#isresizable)|Bölmesinde boyutlandırılabilir olup olmadığını belirler. (Geçersiz kılmaları [CBasePane::IsResizable](../../mfc/reference/cbasepane-class.md#isresizable).)|  
|[CPane::IsTabbed](#istabbed)|Sekmeli penceresinin sekme denetimi bölmesinde eklenmiş olup olmadığını belirler. (Geçersiz kılmaları [CBasePane::IsTabbed](../../mfc/reference/cbasepane-class.md#istabbed).)|  
|[CPane::LoadState](#loadstate)|Bölmesinde durumunu kayıt defterinden yükler. (Geçersiz kılmaları [CBasePane::LoadState](../../mfc/reference/cbasepane-class.md#loadstate).)|  
|[CPane::MoveByAlignment](#movebyalignment)|Belirli bir miktarda bölmesinde ve sanal dikdörtgen taşır.|  
|[CPane::MovePane](#movepane)|Bölme belirtilen dikdörtgenin taşır.|  
|[CPane::OnAfterChangeParent](#onafterchangeparent)|Bölmesinin üst değiştiğinde çerçevesi tarafından çağrılır.|  
|[CPane::OnBeforeChangeParent](#onbeforechangeparent)|Bölmesinin üst değiştirilmek üzereyken çerçevesi tarafından çağrılır.|  
|[CPane::OnPressCloseButton](#onpressclosebutton)|Kullanıcı bölmenin başlık çubuğundaki kapat düğmesini seçtiğinde çerçevesi tarafından çağrılır.|  
|`CPane::OnProcessDblClk`|Dahili olarak kullanılır.|  
|[CPane::OnShowControlBarMenu](#onshowcontrolbarmenu)|Özel bölmesi menüsünde görüntülenmek üzere olduğunda çerçevesi tarafından çağrılır.|  
|[CPane::OnShowControlBarMenu](#onshowcontrolbarmenu)|Özel bölmesi menüsünde görüntülenmek üzere olduğunda çerçevesi tarafından çağrılır.|  
|`CPane::PrepareToDock`|Dahili olarak kullanılır.|  
|[CPane::RecalcLayout](#recalclayout)|Bölmesinin düzeni bilgileri yeniden hesaplar. (Geçersiz kılmaları [CBasePane::RecalcLayout](../../mfc/reference/cbasepane-class.md#recalclayout).)|  
|[CPane::SaveState](#savestate)|Kayıt defterine bölmesinde durumunu kaydeder. (Geçersiz kılmaları [CBasePane::SaveState](../../mfc/reference/cbasepane-class.md#savestate).)|  
|[CPane::SetActiveInGroup](#setactiveingroup)|Bir bölme etkin olarak işaretler.|  
|[CPane::SetBorders](#setborders)|Bölmenin kenarlığının değerlerini ayarlar.|  
|[CPane::SetClientHotSpot](#setclienthotspot)|Etkin nokta bölmesi için ayarlar.|  
|[CPane::SetDockState](#setdockstate)|Bölme için durum bilgilerini yerleştirme geri yükler.|  
|[CPane::SetExclusiveRowMode](#setexclusiverowmode)|Etkinleştirir veya özel satır modunu devre dışı bırakır.|  
|[CPane::SetMiniFrameRTC](#setminiframertc)|Varsayılan kısa çerçeve penceresi için çalışma zamanı sınıf bilgileri ayarlar.|  
|[CPane::SetMinSize](#setminsize)|Bölmesi için izin verilen en düşük düzeyde ayarlar.|  
|[CPane::SetVirtualRect](#setvirtualrect)|Ayarlar *sanal dikdörtgen* bölmesinin.|  
|[CPane::StretchPaneDeferWndPos](#stretchpanedeferwndpos)|Stil yerleştirme dikey veya yatay olarak dayalı bölmesinde uzatır.|  
|[CPane::ToggleAutoHide](#toggleautohide)|Otomatik olarak gizle modu değiştirir.|  
|[CPane::UndockPane](#undockpane)|Bölmenin yerleştirme site, varsayılan kaydırıcı veya şu anda dayandığı kısa çerçeve penceresi kaldırır. (Geçersiz kılmaları [CBasePane::UndockPane](../../mfc/reference/cbasepane-class.md#undockpane).)|  
|[CPane::UpdateVirtualRect](#updatevirtualrect)|Sanal dikdörtgen güncelleştirir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPane::OnAfterDock](#onafterdock)|Bir bölme yerleştirildiğinde çerçevesi tarafından çağrılır.|  
|[CPane::OnAfterFloat](#onafterfloat)|Bir bölme kaydırılmış çerçevesi tarafından çağrılır.|  
|[CPane::OnBeforeDock](#onbeforedock)|Bölmesi hakkında yerleşik olduğunda çerçevesi tarafından çağrılır.|  
|[CPane::OnBeforeFloat](#onbeforefloat)|Bir bölme hakkında kaydırılmış zaman çerçevesi tarafından çağrılır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPane::m_bHandleMinSize](#m_bhandleminsize)|En az boyutunu bölmeleri için tutarlı işlenmesini sağlar.|  
|[CPane::m_recentDockInfo](#m_recentdockinfo)|Son takma bilgilerini içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle, `CPane` nesnelerine ait olmayan örneklerin doğrudan. Yerleştirme işlevselliği bulunduğu bir bölme ihtiyacınız varsa, nesnesinden türetilen [CDockablePane](../../mfc/reference/cdockablepane-class.md). Araç çubuğu işlevsellik gerektiriyorsa, nesnesinden türetilen [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md).  
  
 Öğesinden bir sınıf türetin zaman `CPane`, içinde yuvalanmış bir [CDockSite](../../mfc/reference/cdocksite-class.md) ve içinde kaydırılmış bir [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxPane.h  
  
##  <a name="adjustsizeimmediate"></a>  CPane::AdjustSizeImmediate  
 Hemen bir bölme düzenini yeniden hesaplar.  
  
```  
virtual void AdjustSizeImmediate(BOOL bRecalcLayout = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bRecalcLayout*  
 `TRUE` otomatik olarak bölmesinde düzenini yeniden hesaplamak için; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme düzenini dinamik olarak değiştirdiğinizde, bu yöntemi çağırın. Örneğin, araç çubuğu düğmeleri göstermek veya gizlemek olduğunda bu yöntemi çağırmak isteyebilirsiniz.  
  
##  <a name="allocelements"></a>  CPane::AllocElements  
 Depolama iç kullanımı için ayırır.  
  
```  
BOOL AllocElements(
    int nElements,  
    int cbElement);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nElements*  
 Depolama alanı ayırmak üzere öğe sayısı.  
  
 [in] *cbElement*  
 Bir öğenin bayt cinsinden boyutu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `FALSE` bellek ayırma başarısız olursa; Aksi takdirde `TRUE`.  
  
##  <a name="allowshowonpanemenu"></a>  CPane::AllowShowOnPaneMenu  
 Bölmesinde bölmeleri uygulamanın çalışma zamanı modülü tarafından oluşturulan listesinde listelenen olup olmadığını belirtir.  
  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde listesinde görüntülenir Aksi takdirde `FALSE`. Temel uygulama her zaman döndürür `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 AppWizard oluşturulan uygulama içerdiği bölmeleri listeleyen bir menü seçeneği içerir. Bu yöntem bölmesinde listesinde görüntülenip görüntülenmeyeceğini belirler.  
  
##  <a name="calcavailablesize"></a>  CPane::CalcAvailableSize  
 Boyutu belirtilen dikdörtgen ve geçerli pencere dikdörtgeni arasındaki farkı hesaplar.  
  
```  
virtual CSize CalcAvailableSize(CRect rectRequired);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rectRequired*  
 Gerekli dikdörtgen.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Genişlik ve yükseklik arasındaki farkı *rectRequired* ve geçerli pencere dikdörtgeni.  
  
##  <a name="calcinsiderect"></a>  CPane::CalcInsideRect  
 İç hesaplar kavrayıcılar ve sınırları dahil olmak üzere bir bölme dikdörtgen.  
  
```  
void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *rect*  
 Boyut ve istemci alanını bölmesinin uzaklığını içerir.  
  
 [in] *bHorz*  
 `TRUE` bölmesinde yatay yönlendirmeli ise; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme düzenini yeniden hesapla olduğunda bu yöntem çerçevesi tarafından çağrılır. *Rect* parametresi bölmesinin istemci alanını uzaklığı ve boyutu ile doldurulur. Bu, kendi Kenarlıklar ve kavrayıcılar içerir.  
  
##  <a name="calcrecentdockedrect"></a>  CPane::CalcRecentDockedRect  
 Yakın zamanda yerleşik dikdörtgen hesaplar.  
  
```  
void CalcRecentDockedRect();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem güncelleştirmeleri [CPane::m_recentDockInfo](#m_recentdockinfo).  
  
##  <a name="calcsize"></a>  CPane::CalcSize  
 Bölmesinin boyutunu hesaplar.  
  
```  
virtual CSize CalcSize(BOOL bVertDock);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bVertDock*  
 `TRUE` bölmesinde dikey yerleştirilmişse `FALSE` Aksi takdirde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem varsayılan uygulaması bir boyutu döndüren (0, 0).  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen sınıflar bu yöntemin üzerine yazması gerekir.  
  
##  <a name="canbedocked"></a>  CPane::CanBeDocked  
 Belirtilen temel bölmesinde bölmesi yuvalanmış varsa belirler.  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDockBar*  
 Bu bölmenin yerleştirilmiş olduğu bölmesinde belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Bu bölme belirtilen takma bölmesinde; yerleşik, Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, genellikle bir bölme belirtilen takma bölmesinde yerleştirilmiş olup olmadığını belirlemek için framework tarafından çağrılır. Bölmenin yerleştirilmiş olup olmadığını yöntemi Bölmesi'nin şu anda değerlendirir belirlemek için takma hizalama etkin.  
  
 Çerçeve penceresi çeşitli kenarlara çağırarak yerleştirme etkinleştirmek [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).  
  
##  <a name="canbetabbeddocument"></a>  CPane::CanBeTabbedDocument  
 Sekmeli belge bölmesinde dönüştürülüp dönüştürülemeyeceğini belirler.  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` sekmeli belge bölmesinde dönüştürülebilir ise; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir türetilmiş sınıfta bu yöntemi geçersiz kılın ve dönüş `FALSE` sekmeli belge dönüştürülen bir bölme engellemek istiyorsanız. Sekmeli Belge pencere konumunu menüde listelenmez.  
  
##  <a name="converttotabbeddocument"></a>  CPane::ConvertToTabbedDocument  
 Sekmeli Belge dockable bölmesinde dönüştürür.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bActiveTabOnly*  
 Kullanılan değil `CPane::ConvertToTabbedDocument`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca dockable bölmeleri Sekmeli belgeler dönüştürülebilir. Bilgi için bkz: [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).  
  
##  <a name="copystate"></a>  CPane::CopyState  
 Bir bölme durumunu kopyalar.  
  
```  
virtual void CopyState(CPane* pOrgBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pOrgBar*  
 Bölme için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem durumunu kopyalar *pOrgBar* geçerli bölmesine.  
  
##  <a name="create"></a>  CPane::Create  
 Denetim çubuğu oluşturur ve ona ekler [CPane](../../mfc/reference/cpane-class.md) nesnesi.  
  
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
 Windows sınıfın adını belirtir.  
  
 [in] *dwStyle*  
 Pencere stili özniteliklerini belirtir. Daha fazla bilgi için bkz: [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] *rect*  
 İlk boyutunu ve konumunu belirtir *pParentWnd* penceresinde istemci koordinatları.  
  
 [in] [out] *pParentWnd*  
 Bu bölmesinin üst pencere belirtir.  
  
 [in] *nID*  
 Bölmesinde Kimliğini belirtir.  
  
 [in] *dwControlBarStyle*  
 Bölmesinin stilini belirtir. Daha fazla bilgi için bkz: [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 [in] [out] *pContext*  
 Bölmesinde oluşturma bağlamında belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde başarıyla oluşturulduysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem Windows bölmesini oluşturur ve ekler `CPane` nesnesi.  
  
 Açıkça başlatılmadı, [CPane::m_recentDockInfo](#m_recentdockinfo) çağırmadan önce `Create`, parametre *rect* kayan veya bölmesinde yerleştirme dikdörtgen kullanılır.  
  
##  <a name="createdefaultminiframe"></a>  CPane::CreateDefaultMiniframe  
 Kayan bölmesi için bir kısa çerçeve penceresi oluşturur.  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rectInitial*  
 İlk boyutunu ve konumunu, ekran koordinatları oluşturmak için kısa çerçeve penceresi belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan kısa çerçeve penceresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir bölme yüzdürülen bir kısa çerçeve penceresi oluşturduğunuzda çerçevesi tarafından çağrılır. Kısa çerçeve penceresi türde olabilir [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) veya türünde [CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md). Bölmesinde varsa, birden çok kısa çerçeve penceresi oluşturulur `AFX_CBRS_FLOAT_MULTI` stili.  
  
 Kısa çerçeve penceresi için çalışma zamanı sınıf bilgileri depolanan `CPane::m_pMiniFrameRTC` üyesi. Özelleştirilmiş kısa çerçeve pencereleri oluşturmaya karar verirseniz bu üye ayarlamak için türetilmiş bir sınıf kullanabilirsiniz.  
  
##  <a name="createex"></a>  CPane::CreateEx  
 Denetim çubuğu oluşturur ve ona ekler [CPane](../../mfc/reference/cpane-class.md) nesnesi.  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszClassName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwStyleEx*  
 Genişletilmiş pencere stili özniteliklerini belirtir. Daha fazla bilgi için bkz: [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).  
  
 [in] *lpszClassName*  
 Windows sınıfın adını belirtir.  
  
 [in] *dwStyle*  
 Pencere stili özniteliklerini belirtir. Daha fazla bilgi için bkz: [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] *rect*  
 İlk boyutunu ve konumunu belirtir *pParentWnd* penceresinde istemci koordinatları.  
  
 [in] [out] *pParentWnd*  
 Bu bölmesinin üst pencere belirtir.  
  
 [in] *nID*  
 Bölmesinde Kimliğini belirtir.  
  
 [in] *dwControlBarStyle*  
 Bölmesinin stilini belirtir. Daha fazla bilgi için bkz: [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 [in] [out] *pContext*  
 Bölmesinde oluşturma bağlamının belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde başarıyla oluşturulduysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem Windows bölmesini oluşturur ve ekler `CPane` nesnesi.  
  
 Açıkça başlatılmadı, [CPane::m_recentDockInfo](#m_recentdockinfo) çağırmadan önce `CreateEx`, parametre *rect* kayan veya bölmesinde yerleştirme dikdörtgen kullanılır.  
  
##  <a name="dockbymouse"></a>  CPane::DockByMouse  
 Bir bölme fareyi kullanarak docks.  
  
```  
virtual BOOL DockByMouse(CBasePane* pDockBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDockBar*  
 Bu bölme sabitlemek için temel bölmesine belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesi başarıyla; yuvalanmış varsa Aksi takdirde `FALSE`.  
  
##  <a name="dockpane"></a>  CPane::DockPane  
 Kayan bölmesinde bir temel bölmesine docks.  
  
```  
virtual BOOL DockPane(
    CBasePane* pDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] *pDockBar*  
 Bu bölme sabitlemek için temel bölmesinde belirtir.  
  
 [in] *lpRect*  
 Dikdörtgen bu bölme yerleşik olduğu temel bölmesinde belirtir.  
  
 [in] *dockMethod*  
 Yerleştirme yönteminin kullanılacağını belirtir. Kullanılabilir seçenekler aşağıdaki gibidir:  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|`DM_UNKNOWN`|Yerleştirme yöntemi bilinmeyen olduğunda bu seçeneği çerçevesi kullanır. Bölmenin en son kayan konumuna depolamaz. Bu seçeneği, son kayan konumu depolamak olmadığında bir bölme program aracılığıyla sabitlemek için de kullanabilirsiniz.|  
|`DM_MOUSE`|Dahili olarak kullanılır.|  
|`DM_DBL_CLICK`|Kavrayıcının tıklatıldığında bu seçenek kullanılır. Bölmesinde, en son yerleştirme konumunu yeniden konumlandırılır. Çift tıklatarak bölmesinde takılı, bölmesinde, en son kayan konumunda yeniden konumlandırılır.|  
|`DM_SHOW`|Bu seçenek, program aracılığıyla bölmesinde yerleştirme için kullanılabilir. Bölmenin en son kayan konumuna depolar.|  
|`DM_RECT`|Tarafından belirtilen bölgede bölmesi yuvalanmış *lpRect*.|  
|`DM_STANDARD`|Bu seçeneği kullandığınızda, framework anahat çerçeve olarak bölmesinde çizer taşındığı.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesi başarıyla; yuvalanmış varsa Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından belirtilen temel bölmesine bölmesinde docks *pDockBar* parametresi. Çağırarak yerleştirme önce etkinleştirmelisiniz [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).  
  
##  <a name="dockpanestandard"></a>  CPane::DockPaneStandard  
 Bir bölme anahat (standart) yerleştirme kullanarak docks.  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bWasDocked*  
 `TRUE` bölmesi başarıyla yuvalanmış; Aksi takdirde `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem her zaman **bu** işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca türetilmiş bölmeleri için kullanılan [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md). Daha fazla bilgi için bkz: [CDockablePane::DockPaneStandard](../../mfc/reference/cdockablepane-class.md#dockpanestandard).  
  
##  <a name="docktoframewindow"></a>  CPane::DockToFrameWindow  
 Dockable bölmesinde çerçeveye docks.  
  
```  
virtual BOOL DockToFrameWindow(
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL,  
    DWORD dwDockFlags = DT_DOCK_LAST,  
    CBasePane* pRelativeBar = NULL,  
    int nRelativeIndex = -1,  
    BOOL bOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwAlignment*  
 Bölmesine sabitlemek istediğiniz üst çerçeve tarafında.  
  
 [in] *lpRect*  
 Belirtilen boyut.  
  
 [in] *dwDockFlags*  
 Yoksayıldı.  
  
 [in] *pRelativeBar*  
 Yoksayıldı.  
  
 [in] *nRelativeIndex*  
 Yoksayıldı.  
  
 [in] *bOuterEdge*  
 Varsa `TRUE` ve diğer dockable bölmeler tarafından belirtilen tarafındaki *dwAlignment*, bölmesi diğer bölmeler dışında yuvalanmış üst çerçeve köşesine yakın. Varsa `FALSE`, bölmesinde yakın istemci alanını merkezine yerleştirilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `FALSE` bölmesinde ayırıcı varsa ( [CPaneDivider sınıfı](../../mfc/reference/cpanedivider-class.md)) oluşturulan; Aksi takdirde olamaz `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="doesallowsiblingbars"></a>  CPane::DoesAllowSiblingBars  
 Geçerli bölmesini nereye yerleştirilir aynı satırındaki başka bir bölüme yerleştirme olup olmadığını gösterir.  
  
```  
virtual BOOL DoesAllowSiblingBars() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Bu bölme kendisini aynı sırada bulunan başka bir bölüme yerleştirme Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Etkinleştirmek veya çağırarak bu davranışı devre dışı [CPane::SetExclusiveRowMode](#setexclusiverowmode).  
  
 Varsayılan olarak, araç çubukları özel satır modu devre dışı olması ve menü çubuğu özel satır modu etkin olan.  
  
##  <a name="floatpane"></a>  CPane::FloatPane  
 Bölmesinde kayar.  
  
```  
virtual BOOL FloatPane(
    CRect rectFloat,  
    AFX_DOCK_METHOD dockMethod = DM_UNKNOWN,  
    bool bShow = true);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rectFloat*  
 Konum, yüzdürülen zaman bölmesindeki konumlandırmak için ekran koordinatları olarak belirtir.  
  
 [in] *dockMethod*  
 Bölmesinde yüzdürülen kullanılacak yerleştirme yöntemi belirtir. Olası değerler listesi için bkz: [CPane::DockPane](#dockpane).  
  
 [in] *bBilgi Göster*  
 `TRUE` kaydırılmış bölmesinde göstermek için; Aksi takdirde `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde başarıyla kaydırılmış veya bölmesi, çünkü kaydırılmış olamaz [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat) döndürür `FALSE`; Aksi halde, `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından belirtilen bir konumda bölmesinde float için bu yöntemi çağırın *rectFloat* parametresi. Bu yöntem, bir üst kısa çerçeve penceresi bölmesi için otomatik olarak oluşturur.  
  
##  <a name="getavailableexpandsize"></a>  CPane::GetAvailableExpandSize  
 Tutar bölmeyi genişletebilirsiniz piksel cinsinden döndürür.  
  
```  
virtual int GetAvailableExpandSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde yatay yerleştirilmişse dönüş değeri kullanılabilir genişliği değeridir; Aksi takdirde, dönüş değeri kullanılabilir Yükseklik ' dir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getavailablestretchsize"></a>  CPane::GetAvailableStretchSize  
 Tutar bölmesinde küçültebilirsiniz piksel cinsinden döndürür.  
  
```  
virtual int GetAvailableStretchSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde küçültebilirsiniz piksel cinsinden tutar. Bölmesinin yatay olarak yerleştirilmiş olup, bu miktar kullanılabilir genişliği ise; Aksi takdirde, kullanılabilir yüksekliği olur.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanılabilen uzatma boyut bölmesinde boyutu izin verilen en düşük çıkarılmasıyla hesaplanır ( [CPane::GetMinSize](#getminsize)) geçerli boyutundan ( [CWnd::GetWindowRect](../../mfc/reference/cwnd-class.md#getwindowrect)).  
  
##  <a name="getborders"></a>  CPane::GetBorders  
 Bölmenin kenarlık genişliğini döndürür.  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md) geçerli genişliğini piksel cinsinden bölmesinin her iki tarafı içeren nesne. Örneğin, değeri `left` üyesi `CRect` nesnesidir sol kenarlığın kalınlığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kenarlıkları boyutunu ayarlamak için arama [CPane::SetBorders](#setborders).  
  
##  <a name="getclienthotspot"></a>  CPane::GetClientHotSpot  
 Döndürür *etkin nokta* bölmesi.  
  
```  
CPoint GetClientHotSpot() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 *Etkin nokta* kullanıcı seçer ve bölmesini taşımak için tutan bölmede noktasıdır. Bölmenin yerleştirilmiş bir konumdan taşındığında etkin nokta kesintisiz animasyon için kullanılır.  
  
##  <a name="getdocksiterow"></a>  CPane::GetDockSiteRow  
 Yerleştirme satır döndürür ( [CDockingPanesRow sınıfı](../../mfc/reference/cdockingpanesrow-class.md)) bölmenin yerleştirilmiş olup içinde.  
  
```  
CDockingPanesRow* GetDockSiteRow() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CDockingPanesRow`* içinde bölmesinde yerleştirilmiştir, yerleştirme satır noktaları veya `NULL` bölmesinde yerleştirilmemişse.  
  
##  <a name="getexclusiverowmode"></a>  CPane::GetExclusiveRowMode  
 Bölmesi Dışlayıcı row modunda olup olmadığını belirler.  
  
```  
virtual BOOL GetExclusiveRowMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesi Dışlayıcı satır modundaysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel satır modu hakkında daha fazla bilgi için bkz: [CPane::SetExclusiveRowMode](#setexclusiverowmode).  
  
##  <a name="gethotspot"></a>  CPane::GetHotSpot  
 Bir temel depolanan etkin nokta döndürür `CMFCDragFrameImpl` nesnesi.  
  
```  
CPoint GetHotSpot() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 `CPane` Sınıfı içeren bir `CMFCDragFrameImpl` nesnesi `m_dragFrameImpl`, yani kullanıcı standart takma modda bir bölme getirdiğinde görüntülenen dikdörtgen çizme sorumlu. Etkin nokta kullanıcı bölmesinde taşınırken geçerli fare konumuna göre dikdörtgen çizmek için kullanılır.  
  
##  <a name="getminsize"></a>  CPane::GetMinSize  
 Bölmesinde boyutu izin verilen en düşük alır.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *boyutu*  
 A `CSize` boyutu izin verilen en düşük girilir nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanename"></a>  CPane::GetPaneName  
 Bölmesinde başlığını alır.  
  
```  
virtual void GetPaneName(CString& strName) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *strName*  
 A `CString` resim yazısı adıyla doldurulur nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmenin yerleştirilmiş veya kayan olduğunda Bölmesi Başlığı resim yazısını alanında görüntülenir. Bölmesinde sekmeli grubunun bir parçası ise, başlık sekme alanı görüntülenir. Bölmesinde otomatik olarak gizle modundaysa başlık gösterilir bir `CMFCAutoHideButton`.  
  
##  <a name="getvirtualrect"></a>  CPane::GetVirtualRect  
 Alır *sanal dikdörtgen* bölmesinin.  
  
```  
void GetVirtualRect(CRect& rectVirtual) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *rectVirtual*  
 A `CRect` sanal dikdörtgen girilir nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme taşındığında framework bölmesinin özgün konumuna sanal dikdörtgene depolar. Framework sanal dikdörtgen bölmesinin özgün konumuna geri yüklemek için kullanabilirsiniz.  
  
 Program aracılığıyla bölmeleri taşıyor sürece sanal dikdörtgenler için ilgili yöntemleri çağırmayın.  
  
##  <a name="ischangestate"></a>  CPane::IsChangeState  
 Bölmesinde taşınmış gibi bu yöntem diğer bölmeleri, yerleştirme satırları ve kısa çerçeve pencereleri göreli konumunu analiz eder ve uygun döndürür `AFX_CS_STATUS` değeri.  
  
```  
virtual AFX_CS_STATUS IsChangeState(
    int nOffset,  
    CBasePane** ppTargetBar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nOffset*  
 Yerleştirme duyarlılığını belirtir. Örneğin, içinde taşınan bir bölme *nOffset* yerleştirme satır piksel yerleşik.  
  
 [in] *ppTargetBar*  
 Yöntem döndüğünde *ppTargetBar* için geçerli bölmesi yuvalanmış, nesne için bir ya da bir işaretçi içeriyor veya `NULL` hiçbir yerleştirme gerçekleşirse.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdakilerden birini `AFX_CS_STATUS` değerler:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`CS_NOTHING`|Bölmenin yerleştirme site değil. Framework bölmesinde yerleştirme değil.|  
|`CS_DOCK_IMMEDIATELY`|Bir yuva sitesi bölmesidir ve `DT_IMMEDIATE` stili etkindir. Framework bölmesinde hemen docks.|  
|`CS_DELAY_DOCK`|Başka bir takma bölme ya da bir ana çerçeve kenarı bir yerleştirme sitesi bölmesidir. Kullanıcı taşıma bıraktığında framework bölmesinde docks.|  
|`CS_DELAY_DOCK_TO_TAB`|Sekmeli penceresinde yerleşik için bölmesinde neden olan bir yerleştirme sitesi üzerinden bölmesi vardır. Bu durum, ya da başka bir takma bölmesinde resim yazısını veya sekmeli bölmesinin sekme alanı üzerinden bölmesidir oluşur. Kullanıcı taşıma bıraktığında framework bölmesinde docks.|  
  
##  <a name="isdragmode"></a>  CPane::IsDragMode  
 Bölmesinde taşındığı olup olmadığını belirtir.  
  
```  
virtual BOOL IsDragMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde taşınır Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isinfloatingmultipaneframewnd"></a>  CPane::IsInFloatingMultiPaneFrameWnd  
 Bölmesinde çok bölmesi çerçeve penceresinde olup olmadığını belirtir ( [CMultiPaneFrameWnd sınıfı](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bir çok bölmesi çerçeve penceresinde bölmesidir Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca dockable bölmeleri çok bölmesi çerçeve penceresinde float. Bu nedenle, `CPane::IsInFloatingMultiPaneFrameWnd` her zaman döndürür `FALSE`.  
  
##  <a name="isleftof"></a>  CPane::IsLeftOf  
 Bölmesinde, (veya üstü) sola mı olduğunu belirler belirtilen dikdörtgen.  
  
```  
bool IsLeftOf(
    CRect rect,  
    bool bWindowRect = true) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rect*  
 A `CRect` karşılaştırma için kullanılan nesne.  
  
 [in] *bWindowRect*  
 Varsa `TRUE`, *rect* ekran koordinatları; içerecek şekilde varsayılır `FALSE`, *rect* istemci koordinatları içeren varsayılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmesinde yatay yerleştirilmişse bu yöntem konumunu, sol olup olmadığını denetler *rect*. Aksi takdirde, bu yöntem konumu yukarıda olup olmadığını denetler *rect*.  
  
##  <a name="isresizable"></a>  CPane::IsResizable  
 Bölmesinde yeniden boyutlandırılabilir olup olmadığını belirtir.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yeniden boyutlandırılabilir bölmesidir Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel `CPane` nesneleri yeniden boyutlandırılabilir değildir.  
  
 Yerleştirme Yöneticisi'ni yeniden boyutlandırılabilir bayrağı bölmesinde düzenini belirlemek için kullanır. Olmayan yeniden boyutlandırılabilir bölmeleri her zaman üst çerçeve dış kenarlarında bulunur.  
  
 Olmayan yeniden boyutlandırılabilir bölmeleri kapsayıcıları yerleştirme yer alamaz.  
  
##  <a name="istabbed"></a>  CPane::IsTabbed  
 Sekmeli bir pencere Sekme denetimine bölmesinde eklenmiş olup olmadığını belirler.  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde sekmeli; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Sekmeli durum kayan noktadan ayrı olarak kabul edilir, yerleşik ve durumlarını otomatik olarak gizle.  
  
##  <a name="loadstate"></a>  CPane::LoadState  
 Bölmesinde durumunu kayıt defterinden yükler.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszProfileName*  
 Profil adı.  
  
 [in] *nIndex*  
 Profil dizini.  
  
 [in] *uiID*  
 Bölmesinde kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde durumu başarıyla yüklendiyse; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework kayıt defterinden bölmesinde durumu yüklemek için bu yöntemi çağırır. Tarafından kaydedilen ek bilgileri yüklemek için türetilmiş bir sınıf içinde geçersiz kılma [CPane::SaveState](#savestate).  
  
 Bu yöntem geçersiz kıldığınızda, ayrıca temel yöntemini çağırın ve geri dönüp `FALSE` temel yöntemi döndürürse `FALSE`.  
  
##  <a name="m_bhandleminsize"></a>  CPane::m_bHandleMinSize  
 Minimum bölmesinde boyutları tutarlı işlenmesini sağlar.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHandleMinSize;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir veya daha fazla takma bölmeleri, uygulamanızda geçersiz kılarsanız `GetMinSize`, veya uygulamanızın çağırırsa `SetMinSize`, bu statik üye ayarlamak isteyebilirsiniz `TRUE` framework bölmeleri nasıl boyuta sahip tutarlı bir şekilde işlemek üzere etkinleştirmek için.  
  
 Bu değer ayarlanırsa `TRUE`, değil uzatılmış büyüklüğü kendi az boyutun altında azaltılmış tüm bölmeleri kırpılır. Framework bölmesinde boyutlandırma amacıyla pencere bölgeleri kullandığından, bu değer ayarlanırsa bölmeleri yerleştirme penceresi bölge boyutunu değiştirmeyin `TRUE`.  
  
##  <a name="m_recentdockinfo"></a>  CPane::m_recentDockInfo  
 Son takma bilgilerini içerir.  
  
```  
CRecentDockSiteInfo m_recentDockInfo;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Framework bu üye bölmesi için son takma durum bilgilerini depolar.  
  
##  <a name="movebyalignment"></a>  CPane::MoveByAlignment  
 Belirli bir miktarda bölmesinde ve sanal dikdörtgen taşır.  
  
```  
BOOL MoveByAlignment(
    DWORD dwAlignment,  
    int nOffset);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwAlignment*  
 Bölmesinde hizalamasını belirtir.  
  
 [in] *nOffset*  
 Piksel cinsinden, bölme ve sanal dikdörtgen taşımak tutar.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 *dwAlignment* aşağıdaki değerlerden biri olabilir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|Bölmesinde en çok bir çerçeve penceresinde istemci alanının yerleşik sağlar.|  
|`CBRS_ALIGN_BOTTOM`|Çerçeve penceresi istemci alanını altına yerleştirilmiş için bölmesinde sağlar.|  
|`CBRS_ALIGN_LEFT`|Çerçeve penceresi istemci sayfasının sol tarafındaki için yerleşik için bölmesinde sağlar.|  
|`CBRS_ALIGN_RIGHT`|İstemci alanını bir çerçeve penceresinin sağ tarafındaki yerleşik için bölmesinde sağlar.|  
|`CBRS_ALIGN_ANY`|Herhangi bir çerçeve penceresinde istemci alanını tarafına yerleşik için bölmesinde sağlar.|  
  
 Varsa *dwAlignment* içeren `CBRS_ALIGN_LEFT` veya `CBRS_ALIGN_RIGHT` bayrağı, bölmesinde sanal dikdörtgen taşıdıysanız ve yatay; Aksi halde, *dwAlignment* içeren `CBRS_ALIGN_TOP` veya `CBRS_ALIGN_BOTTOM` bayrağı, bölmesi ve sanal dikdörtgen taşınır dikey olarak.  
  
##  <a name="movepane"></a>  CPane::MovePane  
 Bölme belirtilen dikdörtgenin taşır.  
  
```  
virtual CSize MovePane(
    CRect rectNew,  
    BOOL bForceMove,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rectNew*  
 Bölme için yeni dikdörtgen belirtir.  
  
 [in] *bForceMove*  
 Varsa `TRUE`, izin verilen en düşük bölmesinin boyutunu bu yöntemi yok sayıyor ( [CPane::GetMinSize](#getminsize)); Aksi halde, gerekirse, en az boyutu izin verilen en düşük olduğundan emin olmak bölmesinde ayarlanır.  
  
 [in] *hdwp*  
 Kullanılmadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CSize` genişlik ve yükseklik yeni ve eski dikdörtgenler arasındaki farkları içeren nesne (eski dikdörtgen - *rectNew*).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca dockable bölmeleri için kullanılır.  
  
##  <a name="onafterchangeparent"></a>  CPane::OnAfterChangeParent  
 Bölmesinin üst değiştiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] *pWndOldParent*  
 Bölmesi'nin önceki üst pencere.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bölmesinin üst takma veya kayan işlemi nedeniyle değiştiğinde çerçevesi tarafından çağrılır.  
  
##  <a name="onafterdock"></a>  CPane::OnAfterDock  
 Bir bölme yerleştirildiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnAfterDock(
    CBasePane* pBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
 Bu parametre kullanılmaz.  
  
 [in] *lpRect*  
 Bu parametre kullanılmaz.  
  
 [in] *dockMethod*  
 Bu parametre kullanılmaz.  
  
##  <a name="onafterfloat"></a>  CPane::OnAfterFloat  
 Bir bölme gezinen sonra çerçevesi tarafından çağrılır.  
  
```  
virtual void OnAfterFloat();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme gezinen sonra herhangi bir işlem gerçekleştirmek istiyorsanız bir türetilmiş sınıfta bu yöntemin üzerine yazabilir.  
  
##  <a name="onbeforechangeparent"></a>  CPane::OnBeforeChangeParent  
 Bölmesinin üst değiştirilmek üzereyken çerçevesi tarafından çağrılır.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] *pWndNewParent*  
 Yeni üst pencere belirtir.  
  
 [in] *bDelay*  
 `TRUE` Genel yerleştirme düzenini ayarlama geciktirmek için; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bölmesinin üst bölmesi değiştiriliyor olduğundan değiştirilmek üzereyken çerçevesi tarafından çağrılır yerleşik veya kaydırılmış.  
  
 Varsayılan olarak, çağırarak takma bölmesiyle kaydı bölmesidir `CDockSite::RemovePane`.  
  
##  <a name="onbeforedock"></a>  CPane::OnBeforeDock  
 Bölmesi hakkında sabitlemek için olduğunda çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnBeforeDock(
    CBasePane** ppDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] *ppDockBar*  
 Bu bölme için yerleştirme bölmesinde belirtir.  
  
 [in] *lpRect*  
 Yerleştirme dikdörtgen belirtir.  
  
 [in] *dockMethod*  
 Takma yöntemini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Bölmenin yerleştirilmiş durumunda. İşlev döndürürse `FALSE`, yerleştirme işlemi durdurulacak.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme hakkında yerleşik olduğunda bu yöntem çerçevesi tarafından çağrılır. Bir bölme son yerleşik önce herhangi bir işlem gerçekleştirmek istiyorsanız bir türetilmiş sınıfta bu yöntemin üzerine yazabilir.  
  
##  <a name="onbeforefloat"></a>  CPane::OnBeforeFloat  
 Kayana bölme hakkında olduğunda çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rectFloat*  
 Kayan bir durumda olduğunda bölmesinin boyutunu ve konumunu belirtir.  
  
 [in] *dockMethod*  
 Bölmenin yerleştirme yöntemini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde kaydırılmış Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayana bölme hakkında olduğunda bu yöntem çerçevesi tarafından çağrılır. Bölmesinde son gezinen önce herhangi bir işlem gerçekleştirmek istiyorsanız bir türetilmiş sınıfta bu yöntemin üzerine yazabilir.  
  
##  <a name="onpressclosebutton"></a>  CPane::OnPressCloseButton  
 Kullanıcı, bölmenin başlık çubuğunda Kapat düğmesine bastığında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnPressCloseButton();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir kullanıcı bastığında çerçevesi tarafından çağrılır **Kapat** Bölmesi'nin başlık çubuğunda. Hakkında bildirim almak için **Kapat** olay, bir türetilmiş sınıfta bu yöntemin üzerine yazabilir.  
  
##  <a name="onshowcontrolbarmenu"></a>  CPane::OnShowControlBarMenu  
 Özel bölmesi menüsünde görüntülenmek üzere olduğunda çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnShowControlBarMenu(CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *noktası*  
 Menü konumu belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Menü görüntülenebilir Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü Bölmesi'nin davranışını, yani belirtmenizi sağlayan birkaç öğeleri içerir: **kayan**, **Docking**, **AutoHide**, ve **gizleme**. Çağırarak tüm bölmeleri için bu menüyü etkinleştirebilirsiniz [CDockingManager::EnableDockSiteMenu](../../mfc/reference/cdockingmanager-class.md#enabledocksitemenu).  
  
##  <a name="recalclayout"></a>  CPane::RecalcLayout  
 Bölmesinin düzeni bilgileri yeniden hesaplar.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmesinde yerleştirilmişse, bu yöntem bölmesinde geçerli boyutuna boyutuna ayarlayarak bölmesi için sanal dikdörtgen güncelleştirir.  
  
 Bölmesinde kayan açtıysanız, bu yöntem kısa çerçeve boyutunu bölmesine boyutunu ayarlamak için üst kısa çerçeve bildirir. Framework kısa çerçeve en az bölmesinde boyutu izin verilen en düşük olmasını sağlar ( [CPane::GetMinSize](#getminsize)) ve gerekirse kısa çerçeve yeniden boyutlandırır.  
  
##  <a name="savestate"></a>  CPane::SaveState  
 Kayıt defterine bölmesinde durumunu kaydeder.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszProfileName*  
 Profil adı.  
  
 [in] *nIndex*  
 Profil dizini.  
  
 [in] *uiID*  
 Bölmesinde kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` durumu başarıyla kaydedildi Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt defterine bölmesinde durumunu kaydettiğinde framework bu yöntemi çağırır. Geçersiz kılma `SaveState` ek bilgileri depolamak için bir türetilmiş sınıfta.  
  
 Bu yöntem geçersiz kıldığınızda, ayrıca temel yöntemini çağırın ve geri dönüp `FALSE` temel yöntemi döndürürse `FALSE`.  
  
##  <a name="setactiveingroup"></a>  CPane::SetActiveInGroup  
 Bir bölme etkin olarak işaretler.  
  
```  
virtual void SetActiveInGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bActive*  
 A `BOOL` bölmesinde etkin olarak işaretlenmiş olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Dockable bölmesinde gösterilen veya bir otomatik olarak gizle düğmesi seçilir, karşılık gelen Bölmesini Gizle otomatik etkin olarak işaretlenir.  
  
 Bölmesiyle ilişkili bir otomatik olarak gizle düğmesi görünümünü iki etmenlere dayanır. Bölmesinde etkinse ve `static BOOL CMFCAutoHideButton::m_bOverlappingTabs` olan `TRUE`, framework Otomatik Gizle düğmesini bir simge ve bir etiket görüntüler. Etkin olmayan bir bölmesi için yalnızca otomatik olarak Gizle simgesi framework görüntüler.  
  
 Varsa `CMFCAutoHideButton::m_bOverlappingTabs` olan `FALSE`, veya bölmesinde bir grupta bulunmuyorsa, framework ilişkili Otomatik Gizle düğmesini bir simge ve bir etiket görüntüler.  
  
##  <a name="setborders"></a>  CPane::SetBorders  
 Bölmenin kenarlığının değerlerini ayarlar.  
  
```  
void SetBorders(
    int cxLeft = 0,  
    int cyTop = 0,  
    int cxRight = 0,  
    int cyBottom = 0);  
  
void SetBorders(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *cxLeft*  
 Bölmenin sol kenarlığın piksel cinsinden genişliğini belirtir.  
  
 [in] *cyTop*  
 Genişlik bölmesinin üst kenarlığın piksel cinsinden belirtir.  
  
 [in] *cxRight*  
 Bölmenin sağ kenarlığın piksel cinsinden genişliğini belirtir.  
  
 [in] *cyBottom*  
 Genişlik bölmesinin alt kenarlığın piksel cinsinden belirtir.  
  
 [in] *lpRect*  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md) bölmesinin her kenarlığının piksel cinsinden genişliği içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölme 's kenarlıklarını boyutunu ayarlamak için bu işlevini çağırın.  
  
##  <a name="setclienthotspot"></a>  CPane::SetClientHotSpot  
 Ayarlar *etkin nokta* bölmesi.  
  
```  
void SetClientHotSpot(const CPoint& ptNew);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *ptNew*  
 A `CPoint` yeni etkin nokta belirtir nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 *Etkin nokta* kullanıcı seçer ve bölmesini taşımak için tutan bölmede noktasıdır. Bölmenin yerleştirilmiş bir konumdan sürüklendiğinde etkin nokta kesintisiz animasyon için kullanılır.  
  
##  <a name="setdockstate"></a>  CPane::SetDockState  
 Bölme için durum bilgilerini yerleştirme geri yükler.  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDockManager*  
 Ana çerçeve penceresi için takma Yöneticisi işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bölmesi için son takma durum bilgilerini geri yüklemek için çerçevesi tarafından çağrılır. Bir bölme son takma durumu bilgilerini depolar [CPane::m_recentDockInfo](#m_recentdockinfo). Daha fazla bilgi için bkz: [CRecentDockSiteInfo sınıfı](../../mfc/reference/crecentdocksiteinfo-class.md).  
  
 Ayrıca, bir dış kaynaktan bölmesi bilgilerini yüklediğinizde takma durumunu ayarlamak için bu yöntemi çağırabilirsiniz.  
  
##  <a name="setexclusiverowmode"></a>  CPane::SetExclusiveRowMode  
 Etkinleştirir veya özel satır modunu devre dışı bırakır.  
  
```  
virtual void SetExclusiveRowMode(BOOL bExclusive = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bExclusive*  
 `TRUE` özel satır modunu etkinleştirmek için; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Etkinleştirmek veya özel satır modu devre dışı bırakmak için bu yöntemi çağırın. Bir bölmesi Dışlayıcı satır modundayken ile başka bir araç çubukları aynı satır paylaşamaz.  
  
 Varsayılan olarak, tüm araç çubuklarını özel satır modu devre dışı olması ve menü çubuğu özel satır modu etkin olan.  
  
##  <a name="setminsize"></a>  CPane::SetMinSize  
 Bölmesi için izin verilen en düşük düzeyde ayarlar.  
  
```  
void SetMinSize(const CSize& size);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *boyutu*  
 A `CSize` bölmesinde boyutu izin verilen en düşük içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setvirtualrect"></a>  CPane::SetVirtualRect  
 Ayarlar *sanal dikdörtgen* bölmesinin.  
  
```  
void SetVirtualRect(
    const CRect& rect,  
    BOOL bMapToParent = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rect*  
 A `CRect` ayarlanacak sanal dikdörtgen belirtir nesnesi.  
  
 [in] `bMapToParent`  
 Belirtin `TRUE` varsa *rect* üst pencere göre noktalarını içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 A *sanal dikdörtgen* onu taşındığında bölmesinin özgün konumuna depolar. Framework sanal dikdörtgen özgün konumuna geri yüklemek için kullanabilirsiniz.  
  
 Program aracılığıyla bölmeleri taşıyor sürece sanal dikdörtgenler için ilgili yöntemleri çağırmayın.  
  
##  <a name="setminiframertc"></a>  CPane::SetMiniFrameRTC  
 Varsayılan kısa çerçeve penceresi için çalışma zamanı sınıf bilgileri ayarlar.  
  
```  
void SetMiniFrameRTC(CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] *pClass*  
 Kısa çerçeve penceresi için çalışma zamanı sınıf bilgileri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme yüzdürülen, onu konur bir [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) (kısa çerçeve) penceresi. Özel bir sağlayabilir `CPaneFrameWnd`-türetilen olacaktır sınıfı kullanılır [CPane::CreateDefaultMiniframe](#createdefaultminiframe) olarak adlandırılır.  
  
##  <a name="stretchpanedeferwndpos"></a>  CPane::StretchPaneDeferWndPos  
 Stil yerleştirme dikey veya yatay olarak dayalı bölmesinde uzatır.  
  
```  
virtual int StretchPaneDeferWndPos(
    int nStretchSize,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nStretchSize*  
 Bölmesinde uzatmak için piksel cinsinden tutar. Bölmesinde daraltmak için negatif bir değer kullanın.  
  
 [in] *hdwp*  
 Kullanılmadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Piksel cinsinden bölmesinde uzatılmış gerçek tutar.  
  
### <a name="remarks"></a>Açıklamalar  
 Gerekirse, bu yöntem değiştirir, *nStretchSize* bölmesinde boyut sınırını aşmadığından emin olmak için. Bu sınırlar çağırarak elde edilen [CPane::GetAvailableStretchSize](#getavailablestretchsize) ve [CPane::GetAvailableExpandSize](#getavailableexpandsize).  
  
##  <a name="toggleautohide"></a>  CPane::ToggleAutoHide  
 Otomatik olarak gizle modu değiştirir.  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Otomatik olarak gizle moduna geçiş yapmak için bu yöntemi çağırın. Bir bölme bir ana çerçeve penceresi otomatik olarak gizle moda geç olması için yerleşik gerekir.  
  
##  <a name="undockpane"></a>  CPane::UndockPane  
 Bölmenin yerleştirme site, varsayılan kaydırıcı veya şu anda dayandığı kısa çerçeve penceresi kaldırır.  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bDelay*  
 Varsa `FALSE`, framework çağrıları [CBasePane::AdjustDockingLayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout) yerleştirme düzeni ayarlamak için.  
  
### <a name="remarks"></a>Açıklamalar  
 Program aracılığıyla bir bölme çıkarmak için bu yöntemi kullanın.  
  
##  <a name="updatevirtualrect"></a>  CPane::UpdateVirtualRect  
 Sanal dikdörtgen güncelleştirir.  
  
```  
void UpdateVirtualRect();  
void UpdateVirtualRect(CPoint ptOffset);  
  void UpdateVirtualRect(CSize sizeNew);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *ptOffset*  
 A `CPoint` , bölmesinde kaydırılacak belirtir nesnesi.  
  
 [in] *sizeNew*  
 A `CSize` bölmesinde yeni boyutunu belirleyen nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk aşırı bölmesinin boyutunu ve geçerli konumu kullanarak sanal dikdörtgen ayarlar.  
  
 İkinci aşırı tarafından belirtilen miktar sanal dikdörtgen kaydırır *ptOffset*.  
  
 Geçerli konumunu bölmesinde ve tarafından belirtilen boyutu kullanarak sanal dikdörtgen üçüncü aşırı ayarlar *sizeNew*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CBasePane Sınıfı](../../mfc/reference/cbasepane-class.md)
