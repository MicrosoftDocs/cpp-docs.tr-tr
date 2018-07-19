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
ms.openlocfilehash: ab0f59604cc23f5d8cbd442fcc2a526962bdc4e9
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851426"
---
# <a name="cpane-class"></a>CPane sınıfı
`CPane` Sınıfı, bir geliştirmesini [CControlBar sınıfı](../../mfc/reference/ccontrolbar-class.md). Varolan bir MFC projesini yükseltiyorsanız tüm tekrarlamalarını `CControlBar` ile `CPane`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPane : public CBasePane  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CPane::~CPane`|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPane::AdjustSizeImmediate](#adjustsizeimmediate)|Hemen bir bölme düzenini yeniden hesaplar.|  
|[CPane::AllocElements](#allocelements)|İç kullanım için depolama alanı ayırır.|  
|[CPane::AllowShowOnPaneMenu](#allowshowonpanemenu)|Bölmeleri uygulama için çalışma zamanı tarafından oluşturulan listesinde bölmesinde listelenen olup olmadığını belirtir.|  
|[CPane::CalcAvailableSize](#calcavailablesize)|Boyutu belirtilen dikdörtgen ve geçerli pencere dikdörtgeni arasındaki farkı hesaplar.|  
|[CPane::CalcInsideRect](#calcinsiderect)|İç hesaplar kavrayıcılar ve sınırları hesaba katarak bölmesinin dikdörtgen.|  
|[CPane::CalcRecentDockedRect](#calcrecentdockedrect)|En son sabitlenmiş dikdörtgen hesaplar.|  
|[CPane::CalcSize](#calcsize)|Bölmesinin boyutunu hesaplar.|  
|[CPane::CanBeDocked](#canbedocked)|Belirtilen temel bölmesinde bölmesinde yerleştirilmiş olup olmadığını belirler.|  
|[CPane::CanBeTabbedDocument](#canbetabbeddocument)|Sekmeli belgeye bölmesinde dönüştürülüp dönüştürülemeyeceğini belirler.|  
|[CPane::ConvertToTabbedDocument](#converttotabbeddocument)|Yerleştirilebilir bir bölme sekmeli belgeye dönüştürür.|  
|[CPane::CopyState](#copystate)|Bir bölme durumu kopyalar. (Geçersiz kılmaları [CBasePane::CopyState](../../mfc/reference/cbasepane-class.md#copystate).)|  
|[CPane::Create](#create)|Denetim çubuğu oluşturur ve ona ekler `CPane` nesne.|  
|[CPane::CreateDefaultMiniframe](#createdefaultminiframe)|Bir kayan bölme için bir mini çerçeve penceresi oluşturur.|  
|[CPane::CreateEx](#createex)|Denetim çubuğu oluşturur ve ona ekler `CPane` nesne.|  
|`CPane::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|  
|[CPane::DockByMouse](#dockbymouse)|Bir bölme yöntemi yerleştirme fareyi kullanarak docks.|  
|[CPane::DockPane](#dockpane)|Kayan bölme için bir temel bölme docks.|  
|[CPane::DockPaneStandard](#dockpanestandard)|Bir bölme anahat (standart) yerleştirme kullanarak docks.|  
|[CPane::DockToFrameWindow](#docktoframewindow)|Yerleştirilebilir bir bölme için bir çerçeve docks. (Geçersiz kılmaları `CBasePane::DockToFrameWindow`.)|  
|[CPane::DoesAllowSiblingBars](#doesallowsiblingbars)|Geçerli bölmesini nereye yerleştirildiğini aynı satır başka bir bölüme yerleştirme olup olmadığını gösterir.|  
|[CPane::FloatPane](#floatpane)|Bölmesinde kayar.|  
|[CPane::GetAvailableExpandSize](#getavailableexpandsize)|Tutarı bölmeyi genişletebilirsiniz piksel cinsinden döndürür.|  
|[CPane::GetAvailableStretchSize](#getavailablestretchsize)|Tutarı bölmesinde küçültebilirsiniz piksel cinsinden döndürür.|  
|[CPane::GetBorders](#getborders)|Bölmenin genişliğini döndürür.|  
|[CPane::GetClientHotSpot](#getclienthotspot)|Döndürür *etkin nokta* bölmesi.|  
|[CPane::GetDockSiteRow](#getdocksiterow)|İçinde bölmenin yerleştirilmiş bir dock satırı döndürür.|  
|[CPane::GetExclusiveRowMode](#getexclusiverowmode)|Bölmesinde özel satır modunda olup olmadığını belirler.|  
|[CPane::GetHotSpot](#gethotspot)|Bir temel depolanan etkin nokta döndürür `CMFCDragFrameImpl` nesne.|  
|[CPane::GetMinSize](#getminsize)|Bölme boyutu izin verilen en düşük alır.|  
|[CPane::GetPaneName](#getpanename)|Bölmesinde başlığını alır.|  
|`CPane::GetResizeStep`|Dahili olarak kullanılır.|  
|`CPane::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|  
|[CPane::GetVirtualRect](#getvirtualrect)|Alır *sanal dikdörtgen* bölmesi.|  
|[CPane::IsChangeState](#ischangestate)|Bu yöntem göre diğer bölmeleri, bölmenin konumunu çözümleyen taşınan bölmesinde olduğu gibi satır ve Mini çerçeve pencereleri yerleştirme ve uygun AFX_CS_STATUS değeri döndürür.|  
|[CPane::IsDragMode](#isdragmode)|Bölmesinde sürüklenen olup olmadığını belirtir.|  
|[CPane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Bölmesinde bir çok bölmesinde çerçeve penceresinde olup olmadığını belirtir. (Geçersiz kılmaları `CBasePane::IsInFloatingMultiPaneFrameWnd`.)|  
|[CPane::IsLeftOf](#isleftof)|Bölmesi olan (veya üzeri) sola mı olduğunu belirler belirtilen dikdörtgen.|  
|[CPane::IsResizable](#isresizable)|Bölmesinde boyutlandırılabilir olup olmadığını belirler. (Geçersiz kılmaları [CBasePane::IsResizable](../../mfc/reference/cbasepane-class.md#isresizable).)|  
|[CPane::IsTabbed](#istabbed)|Sekme denetimi sekmeli pencere bölmesi eklenen olup olmadığını belirler. (Geçersiz kılmaları [CBasePane::IsTabbed](../../mfc/reference/cbasepane-class.md#istabbed).)|  
|[CPane::LoadState](#loadstate)|Kayıt defterinden bölmesinde durumunu yükler. (Geçersiz kılmaları [CBasePane::LoadState](../../mfc/reference/cbasepane-class.md#loadstate).)|  
|[CPane::MoveByAlignment](#movebyalignment)|Belirli bir miktarda bölmesinde ve sanal dikdörtgen taşır.|  
|[CPane::MovePane](#movepane)|Bölme için belirtilen dikdörtgen taşır.|  
|[CPane::OnAfterChangeParent](#onafterchangeparent)|Üst bölme değiştiğinde framework tarafından çağırılır.|  
|[CPane::OnBeforeChangeParent](#onbeforechangeparent)|Bölmenin üst değiştirilmek üzereyken framework tarafından çağırılır.|  
|[CPane::OnPressCloseButton](#onpressclosebutton)|Kullanıcı bölmesi için açıklama yazısını Kapat düğmesini seçtiğinde framework tarafından çağırılır.|  
|`CPane::OnProcessDblClk`|Dahili olarak kullanılır.|  
|[CPane::OnShowControlBarMenu](#onshowcontrolbarmenu)|Özel bölmesinde menü gösterilmek üzereyken framework tarafından çağırılır.|  
|[CPane::OnShowControlBarMenu](#onshowcontrolbarmenu)|Özel bölmesinde menü gösterilmek üzereyken framework tarafından çağırılır.|  
|`CPane::PrepareToDock`|Dahili olarak kullanılır.|  
|[CPane::RecalcLayout](#recalclayout)|Düzen bölmesi bilgilerini yeniden hesaplar. (Geçersiz kılmaları [CBasePane::RecalcLayout](../../mfc/reference/cbasepane-class.md#recalclayout).)|  
|[CPane::SaveState](#savestate)|Kayıt defterine bölmesinde durumunu kaydeder. (Geçersiz kılmaları [CBasePane::SaveState](../../mfc/reference/cbasepane-class.md#savestate).)|  
|[CPane::SetActiveInGroup](#setactiveingroup)|Bir bölme etkin olarak işaretler.|  
|[CPane::SetBorders](#setborders)|Bölmenin kenarlığının değerlerini ayarlar.|  
|[CPane::SetClientHotSpot](#setclienthotspot)|Etkin nokta bölmesi için ayarlar.|  
|[CPane::SetDockState](#setdockstate)|Yerleştirme bölmesi için durum bilgilerini yükler.|  
|[CPane::SetExclusiveRowMode](#setexclusiverowmode)|Etkinleştirir veya özel satır modunu devre dışı bırakır.|  
|[CPane::SetMiniFrameRTC](#setminiframertc)|Varsayılan Mini çerçeve penceresi için çalışma zamanı sınıf bilgileri ayarlar.|  
|[CPane::SetMinSize](#setminsize)|Bölme boyutu izin verilen en düşük ayarlar.|  
|[CPane::SetVirtualRect](#setvirtualrect)|Kümeleri *sanal dikdörtgen* bölmesi.|  
|[CPane::StretchPaneDeferWndPos](#stretchpanedeferwndpos)|Yatay veya dikey olarak yerleştirme stili tabanlı bölmesinde uzatır.|  
|[CPane::ToggleAutoHide](#toggleautohide)|Otomatik gizleme moduna geçiş yapar.|  
|[CPane::UndockPane](#undockpane)|Dock sitesiyle, varsayılan kaydırıcı veya mini çerçevenin şu anda dayandığı bölmesinde kaldırır. (Geçersiz kılmaları [CBasePane::UndockPane](../../mfc/reference/cbasepane-class.md#undockpane).)|  
|[CPane::UpdateVirtualRect](#updatevirtualrect)|Sanal dikdörtgen güncelleştirir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPane::OnAfterDock](#onafterdock)|Bir bölme yerleştirildiğinde framework tarafından çağırılır.|  
|[CPane::OnAfterFloat](#onafterfloat)|Bir bölme kaydırıldı framework tarafından çağırılır.|  
|[CPane::OnBeforeDock](#onbeforedock)|Bölmenin yerleştirilmiş olması için framework tarafından çağrılır.|  
|[CPane::OnBeforeFloat](#onbeforefloat)|Bir bölme hakkında kaydırıldı üzereyken framework tarafından çağırılır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPane::m_bHandleMinSize](#m_bhandleminsize)|En küçük boyutu bölmeleri için tutarlı işlenmesine olanak tanır.|  
|[CPane::m_recentDockInfo](#m_recentdockinfo)|Yeni takma bilgiler içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle, `CPane` nesnelerine ait olmayan örneklerin doğrudan. Yerleştirme işlevlerini içeren bir bölme ihtiyacınız varsa, bir nesneden türetmek [CDockablePane](../../mfc/reference/cdockablepane-class.md). Araç işlevselliğini ihtiyacınız varsa, bir nesneden türetmek [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md).  
  
 Türetilen bir sınıftan zaman `CPane`, içinde sabitlenebilir bir [CDockSite](../../mfc/reference/cdocksite-class.md) ve içinde kaydırıldı bir [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).  
  
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
 Otomatik olarak bölmesinde düzenini yeniden hesapla için TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme düzenini dinamik olarak değiştirdiğinizde, bu yöntemi çağırın. Örneğin, bu yöntemi çağırın araç çubuğu düğmeleri göstermek veya gizlemek isteyebilirsiniz.  
  
##  <a name="allocelements"></a>  CPane::AllocElements  
 İç kullanım için depolama alanı ayırır.  
  
```  
BOOL AllocElements(
    int nElements,  
    int cbElement);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nElements*  
 Depolama alanı ayırmak istediğiniz öğe sayısı.  
  
 [in] *cbElement*  
 Bir öğenin bayt cinsinden boyutu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek ayırma başarısız olursa FALSE; Aksi takdirde TRUE.  
  
##  <a name="allowshowonpanemenu"></a>  CPane::AllowShowOnPaneMenu  
 Bölmeleri uygulama için çalışma zamanı tarafından oluşturulan listesinde bölmesinde listelenen olup olmadığını belirtir.  
  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde listesinde görüntülenen TRUE; Aksi takdirde FALSE. Temel uygulama her zaman TRUE değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 AppWizard tarafından oluşturulan uygulama, içerdiği bölmeleri listeleyen bir menü seçeneği içerir. Bu yöntem, bölmesinde listesinde görüntülenip görüntülenmeyeceğini belirler.  
  
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
 İç hesaplar kavrayıcılar ve sınırları dahil olmak üzere bir bölme, dikdörtgen.  
  
```  
void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *dikdörtgen*  
 Boyut ve istemci alanını bölmesinin uzaklığı içerir.  
  
 [in] *bHorz*  
 Bölmeyi yatay olarak yönelimli ise TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme düzenini yeniden hesapla olduğunda bu yöntem framework tarafından çağırılır. *Rect* parametresi istemci alanını bölmesinin uzaklığı ve boyutu ile doldurulur. Bu, kavrayıcılar ve kenarlık içerir.  
  
##  <a name="calcrecentdockedrect"></a>  CPane::CalcRecentDockedRect  
 En son sabitlenmiş dikdörtgen hesaplar.  
  
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
 Bölmeyi dikey olarak, FALSE Aksi takdirde yerleştirildiğini TRUE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem varsayılan uygulaması bir boyutunu döndürür (0, 0).  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen sınıfların bu yöntemin üzerine yazması gerekir.  
  
##  <a name="canbedocked"></a>  CPane::CanBeDocked  
 Belirtilen temel bölmesinde sabitlenebilir bölme belirler.  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDockBar*  
 Bu bölme sabitlenebilir olduğu bölmesinde belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu bölme belirtilen bir yerleştirme bölmesi yuvalanabilir TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, genellikle bir bölme belirtilen yerleştirme bölmesi yerleştirilmiş olup olmadığını belirlemek için framework tarafından çağırılır. Bölmenin yerleştirilmiş olup olmadığını yöntemi bölmedeki şu anda değerlendirilen belirlemek için yerleştirme hizalama etkin.  
  
 Çerçeve penceresinin çeşitli kenarlara çağırarak yerleştirme etkinleştirme [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).  
  
##  <a name="canbetabbeddocument"></a>  CPane::CanBeTabbedDocument  
 Sekmeli belgeye dönüştürülebilir bölmesinde belirler.  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sekmeli belgeye bölmesinde dönüştürülebilir ise TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta bu yöntemi yok sayın ve sekmeli belgeye dönüştürülen bir bölme engellemek istiyorsanız false değerini döndürür. Sekmeli Belge pencere konumu menüde listelenmez.  
  
##  <a name="converttotabbeddocument"></a>  CPane::ConvertToTabbedDocument  
 Yerleştirilebilir bir bölme sekmeli belgeye dönüştürür.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bActiveTabOnly*  
 İçinde kullanılmadı `CPane::ConvertToTabbedDocument`.  
  
### <a name="remarks"></a>Açıklamalar  
 Sekmeli belgelere yalnızca yerleştirilebilir bölmeleri dönüştürülebilir. Bilgi için [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).  
  
##  <a name="copystate"></a>  CPane::CopyState  
 Bir bölme durumu kopyalar.  
  
```  
virtual void CopyState(CPane* pOrgBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pOrgBar*  
 Bir bölme için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem durumunu kopyalar *pOrgBar* geçerli bölmesine.  
  
##  <a name="create"></a>  CPane::Create  
 Denetim çubuğu oluşturur ve ona ekler [CPane](../../mfc/reference/cpane-class.md) nesne.  
  
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
 Pencere stili özniteliklerini belirtir. Daha fazla bilgi için [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] *dikdörtgen*  
 Başlangıç boyutunu ve konumunu belirtir *pParentWnd* penceresinde istemci koordinatları.  
  
 [in] [out] *pParentWnd*  
 Bu Bölmenin üst pencere belirtir.  
  
 [in] *nID*  
 Bölmenin Kimliğini belirtir.  
  
 [in] *dwControlBarStyle*  
 Bölmesinin stilini belirtir. Daha fazla bilgi için [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 [in] [out] *pContext*  
 Create bağlam bölmesi belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde başarıyla oluşturulursa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem Windows bölme oluşturur ve ona ekler `CPane` nesne.  
  
 Açıkça başlatılmadı ise [CPane::m_recentDockInfo](#m_recentdockinfo) çağırmadan önce `Create`, parametre *rect* kayan veya yerleştirme bölmesi dikdörtgen kullanılır.  
  
##  <a name="createdefaultminiframe"></a>  CPane::CreateDefaultMiniframe  
 Bir kayan bölme için bir mini çerçeve penceresi oluşturur.  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rectInitial*  
 Başlangıç boyutu ve konumu, ekran koordinatlarında oluşturmak için Mini çerçeve penceresinin belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan Mini çerçeve penceresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir bölme yüzdürülen bir mini çerçeve oluşturmak için framework tarafından çağırılır. Mini çerçeve türü olabilir [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) veya türü [CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md). Bölmesinde AFX_CBRS_FLOAT_MULTI stile sahipse, bir çoklu Mini çerçeve oluşturulur.  
  
 Mini çerçeve penceresi için çalışma zamanı sınıf bilgileri depolanan `CPane::m_pMiniFrameRTC` üyesi. Türetilmiş bir sınıf, özelleştirilmiş Mini çerçeve pencereleri oluşturmaya karar verirseniz, bu üye ayarlamak için kullanabilirsiniz.  
  
##  <a name="createex"></a>  CPane::CreateEx  
 Denetim çubuğu oluşturur ve ona ekler [CPane](../../mfc/reference/cpane-class.md) nesne.  
  
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
 Genişletilmiş pencere stili özniteliklerini belirtir. Daha fazla bilgi için [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).  
  
 [in] *lpszClassName*  
 Windows sınıfın adını belirtir.  
  
 [in] *dwStyle*  
 Pencere stili özniteliklerini belirtir. Daha fazla bilgi için [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] *dikdörtgen*  
 Başlangıç boyutunu ve konumunu belirtir *pParentWnd* penceresinde istemci koordinatları.  
  
 [in] [out] *pParentWnd*  
 Bu Bölmenin üst pencere belirtir.  
  
 [in] *nID*  
 Bölmenin Kimliğini belirtir.  
  
 [in] *dwControlBarStyle*  
 Bölmesinin stilini belirtir. Daha fazla bilgi için [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 [in] [out] *pContext*  
 Create bağlam bölmesi için belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde başarıyla oluşturulursa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem Windows bölme oluşturur ve ona ekler `CPane` nesne.  
  
 Açıkça başlatılmadı ise [CPane::m_recentDockInfo](#m_recentdockinfo) çağırmadan önce `CreateEx`, parametre *rect* kayan veya yerleştirme bölmesi dikdörtgen kullanılır.  
  
##  <a name="dockbymouse"></a>  CPane::DockByMouse  
 Fareyi kullanarak bir bölme docks.  
  
```  
virtual BOOL DockByMouse(CBasePane* pDockBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDockBar*  
 Bu bölme sabitlemek için temel bölmesine belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde başarıyla yerleştirilmiş TRUE; Aksi takdirde FALSE.  
  
##  <a name="dockpane"></a>  CPane::DockPane  
 Kayan bölme için bir temel bölme docks.  
  
```  
virtual BOOL DockPane(
    CBasePane* pDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] *pDockBar*  
 Bu bölme için sabitlemek için temel bölmesinde belirtir.  
  
 [in] *lpRect*  
 Bu bölme sabitlenebilir olduğu ana bölmede dikdörtgen belirtir.  
  
 [in] *dockMethod*  
 Yerleştirme yönteminin kullanılacağını belirtir. Kullanılabilir seçenekleri aşağıdaki gibidir:  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|DM_UNKNOWN|Yerleştirme yöntemi belirsiz olduğunda bu seçeneği çerçeve kullanır. Bölmenin en son kayan konumuna depolamaz. Bu seçeneği, son kayan konumu depolamak olmadığında program aracılığıyla bir bölme sabitlemek için de kullanabilirsiniz.|  
|DM_MOUSE|Dahili olarak kullanılır.|  
|DM_DBL_CLICK|Kavrayıcının tıklatıldığında, bu seçenek kullanılır. Bölmesinde, en son kendi yerleşik konumda'yeniden konumlandırılır. Çift tıklayarak bölmesinde akıyor, bölmesinde, en son kayan konumda yeniden konumlandırıldığında.|  
|DM_SHOW|Bu seçeneği, program aracılığıyla bölmesinde sabitlemek için kullanılabilir. Bölmenin en son kayan konumunu saklar.|  
|DM_RECT|Tarafından belirtilen bölgede bölmenin yerleştirilmiş *lpRect*.|  
|DM_STANDARD|Bu seçeneği kullandığınızda, taşınırken framework bölmesinde bir ana kare çizer.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde başarıyla yerleştirilmiş TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından belirtilen temel bölmesine bölmesinde docks *pDockBar* parametresi. Çağırarak yerleştirme önce etkinleştirmelisiniz [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).  
  
##  <a name="dockpanestandard"></a>  CPane::DockPaneStandard  
 Bir bölme anahat (standart) yerleştirme kullanarak docks.  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bWasDocked*  
 Bölmesinde başarıyla yerleştirilmiş TRUE; Aksi takdirde FALSE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem her zaman döndürür **bu** işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca türetilmiş bölmeleri için kullanılan [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md). Daha fazla bilgi için [CDockablePane::DockPaneStandard](../../mfc/reference/cdockablepane-class.md#dockpanestandard).  
  
##  <a name="docktoframewindow"></a>  CPane::DockToFrameWindow  
 Yerleştirilebilir bir bölme için bir çerçeve docks.  
  
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
 Bölmesine sabitlemek istediğiniz üst çerçevenin yanında.  
  
 [in] *lpRect*  
 Belirtilen boyutu.  
  
 [in] *dwDockFlags*  
 Yoksayıldı.  
  
 [in] *pRelativeBar*  
 Yoksayıldı.  
  
 [in] *nRelativeIndex*  
 Yoksayıldı.  
  
 [in] *bOuterEdge*  
 Diğer yerleştirilebilir bölmeler tarafından belirtilen tarafında doğru ve var olup olmadığını *dwAlignment*, diğer bölmeler dışında bölmesinde yerleştirildiğini üst çerçevenin kenarına daha yakın. FALSE ise bölmesinde yakın istemci alanını merkezine yerleştirilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 YANLIŞ bölmesinde ayırıcı ( [CPaneDivider sınıfı](../../mfc/reference/cpanedivider-class.md)) oluşturulamıyor; Aksi takdirde TRUE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="doesallowsiblingbars"></a>  CPane::DoesAllowSiblingBars  
 Geçerli bölmesini nereye yerleştirildiğini aynı satır başka bir bölüme yerleştirme olup olmadığını gösterir.  
  
```  
virtual BOOL DoesAllowSiblingBars() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu bölme kendisi olarak aynı satırda başka bir bölüme yerleştirme TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Etkinleştirebilir veya çağırarak bu davranışı devre dışı [CPane::SetExclusiveRowMode](#setexclusiverowmode).  
  
 Varsayılan olarak, araç çubukları özel satır modu devre dışı sahip ve özel satır modu etkin menü çubuğu vardır.  
  
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
 Konum, yüzdürülür bölmesinde konum için ekran koordinatları olarak belirtir.  
  
 [in] *dockMethod*  
 Bölmesinde yüzdürülür kullanılacak yerleştirme yöntemini belirtir. Olası değerler listesi için bkz. [CPane::DockPane](#dockpane).  
  
 [in] *bBilgi Göster*  
 Kaydırılmış bölmesinde göstermek için TRUE; Aksi takdirde FALSE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde başarıyla kaydırıldı veya bölmesinde, çünkü kaydırıldı olamaz doğru [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat) FALSE; Aksi takdirde FALSE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından belirtilen konumda bölmesinde kaydırmak için bu yöntemi çağıran *rectFloat* parametresi. Bu yöntem, bir üst Mini çerçeve penceresi bölmesi için otomatik olarak oluşturur.  
  
##  <a name="getavailableexpandsize"></a>  CPane::GetAvailableExpandSize  
 Tutarı bölmeyi genişletebilirsiniz piksel cinsinden döndürür.  
  
```  
virtual int GetAvailableExpandSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmeyi yatay olarak yerleştirilmişse, dönüş değeri kullanılabilir genişliğidir; Aksi takdirde, dönüş değeri kullanılabilir height ' dir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getavailablestretchsize"></a>  CPane::GetAvailableStretchSize  
 Tutarı bölmesinde küçültebilirsiniz piksel cinsinden döndürür.  
  
```  
virtual int GetAvailableStretchSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde küçültebilirsiniz piksel cinsinden tutar. Bölmeyi yatay olarak yerleştirilmişse, bu miktar kullanılabilir genişliğidir; Aksi takdirde kullanılabilir yüksekliği olur.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanılabilen uzatma boyut bölmesi boyutu izin verilen en düşük çıkarılmasıyla hesaplanır ( [CPane::GetMinSize](#getminsize)) geçerli boyutundan ( [CWnd::GetWindowRect](../../mfc/reference/cwnd-class.md#getwindowrect)).  
  
##  <a name="getborders"></a>  CPane::GetBorders  
 Bölmenin genişliğini döndürür.  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md) geçerli genişliğini piksel cinsinden bölmesinde her iki tarafındaki içeren nesne. Örneğin, değeri `left` üyesi `CRect` nesnedir sol kenarlığın kalınlığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kenarlıklar boyutunu ayarlamak için çağrı [CPane::SetBorders](#setborders).  
  
##  <a name="getclienthotspot"></a>  CPane::GetClientHotSpot  
 Döndürür *etkin nokta* bölmesi.  
  
```  
CPoint GetClientHotSpot() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 *Etkin nokta* kullanıcı seçer ve bölmesinde taşımak tutan bölmesinde noktasıdır. Yerleşik konumundan bölmesinde taşındığında etkin nokta kesintisiz animasyon için kullanılır.  
  
##  <a name="getdocksiterow"></a>  CPane::GetDockSiteRow  
 Dock satır döndürür ( [CDockingPanesRow sınıfı](../../mfc/reference/cdockingpanesrow-class.md)), bölmenin yerleştirilmiş olarak.  
  
```  
CDockingPanesRow* GetDockSiteRow() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CDockingPanesRow`* işaret eden bölmesinde yerleştirilmiştir dock satır veya NULL bölmesinde değil yerleştirilmişse.  
  
##  <a name="getexclusiverowmode"></a>  CPane::GetExclusiveRowMode  
 Bölmesinde özel satır modunda olup olmadığını belirler.  
  
```  
virtual BOOL GetExclusiveRowMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Özel satır modunda bölmesi ise TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel satır modu hakkında daha fazla bilgi için bkz. [CPane::SetExclusiveRowMode](#setexclusiverowmode).  
  
##  <a name="gethotspot"></a>  CPane::GetHotSpot  
 Bir temel depolanan etkin nokta döndürür `CMFCDragFrameImpl` nesne.  
  
```  
CPoint GetHotSpot() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 `CPane` Sınıfı içeren bir `CMFCDragFrameImpl` nesnesi `m_dragFrameImpl`, yani kullanıcı standart yerleştirme modunda bir bölmeyi getirdiğinde beliren dikdörtgen çizmek için sorumlu. Etkin noktayı, kullanıcı bölmesinde taşınırken göre geçerli farenin konumunun dikdörtgen çizmek için kullanılır.  
  
##  <a name="getminsize"></a>  CPane::GetMinSize  
 Bölme boyutu izin verilen en düşük alır.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *boyutu*  
 A `CSize` boyutu izin verilen en düşük ile doldurulan bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanename"></a>  CPane::GetPaneName  
 Bölmesinde başlığını alır.  
  
```  
virtual void GetPaneName(CString& strName) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *strName*  
 A `CString` nesnesini açıklamalı alt yazı adıyla doldurulur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmenin yerleştirilmiş veya kayan olduğunda Bölmesi Başlığı başlık alanında görüntülenir. Bölmesinde sekmeli grubunun parçasıysa, başlığın sekme alanı görüntülenir. Otomatik gizleme modundayken bölmesinde, başlık görüntülenen bir `CMFCAutoHideButton`.  
  
##  <a name="getvirtualrect"></a>  CPane::GetVirtualRect  
 Alır *sanal dikdörtgen* bölmesi.  
  
```  
void GetVirtualRect(CRect& rectVirtual) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *rectVirtual*  
 A `CRect` nesnesini sanal bir dikdörtgen ile doldurulur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme taşındığında framework bölmesinin orijinal konumlarından sanal dikdörtgene depolar. Framework sanal dikdörtgen bölmesinin özgün konumuna geri yüklemek için kullanabilirsiniz.  
  
 Bölmeleri program aracılığıyla taşıdığınız sürece sanal dikdörtgenler için ilgili yöntemlerini çağırmanız gerekmez.  
  
##  <a name="ischangestate"></a>  CPane::IsChangeState  
 Bu yöntem diğer bölmeler göreli konumunu çözümleyen taşınan bölmesinde olduğu gibi satır ve Mini çerçeve pencereleri yerleştirme ve uygun AFX_CS_STATUS değeri döndürür.  
  
```  
virtual AFX_CS_STATUS IsChangeState(
    int nOffset,  
    CBasePane** ppTargetBar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nOffset*  
 Yerleştirme duyarlılığı belirtir. Örneğin, içinde taşınan bir bölme *nOffset* dock satır piksel yerleşik.  
  
 [in] *ppTargetBar*  
 Yöntem döndürüldüğünde *ppTargetBar* hiçbir yerleştirme gerçekleşirse, geçerli bölmesi yuvalanmış nesnesine bir işaretçi veya NULL içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki AFX_CS_STATUS değerlerden biri:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|CS_NOTHING|Bölmesinde bir dock sitesine değil. Framework bölmesinin dock değil.|  
|CS_DOCK_IMMEDIATELY|İçinde bir dock sitesine bölmesidir ve DT_IMMEDIATE stili etkindir. Framework bölmesinde hemen docks.|  
|CS_DELAY_DOCK|Başka bir yerleştirme bölmesi ya da bir ana çerçeve kenarı bir dock sitesine bölmesidir. Kullanıcı taşıma bıraktığında framework bölmesinde docks.|  
|CS_DELAY_DOCK_TO_TAB|Sekmeli penceresinde yerleştirilemediğinde bölmesinde neden olan bir dock sitesine üzerinden bölmesi vardır. Bu durum, ya da başka bir yerleştirme bölmesi başlığı veya sekmeli bir bölmeye sekme alanının üzerinden bölmesidir oluşur. Kullanıcı taşıma bıraktığında framework bölmesinde docks.|  
  
##  <a name="isdragmode"></a>  CPane::IsDragMode  
 Bölmesinde taşınırken olup olmadığını belirtir.  
  
```  
virtual BOOL IsDragMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde taşınırsa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isinfloatingmultipaneframewnd"></a>  CPane::IsInFloatingMultiPaneFrameWnd  
 Bölmesinde bir çok bölmesinde çerçeve penceresinde olup olmadığını belirtir ( [CMultiPaneFrameWnd sınıfı](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir çok bölmesinde çerçeve penceresinde bölmesi ise TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca yerleştirilebilir bölmeleri çok bölmesinde çerçeve penceresinde kaydırabilirsiniz. Bu nedenle, `CPane::IsInFloatingMultiPaneFrameWnd` her zaman false değerini döndürür.  
  
##  <a name="isleftof"></a>  CPane::IsLeftOf  
 Bölmesi olan (veya üzeri) sola mı olduğunu belirler belirtilen dikdörtgen.  
  
```  
bool IsLeftOf(
    CRect rect,  
    bool bWindowRect = true) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dikdörtgen*  
 A `CRect` karşılaştırmak için kullanılan nesne.  
  
 [in] *bWindowRect*  
 TRUE ise *rect* ekran koordinatları; FALSE ise, içerdiği varsayılır *rect* istemci koordinatları içerdiği varsayılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmeyi yatay olarak yerleştirilmişse, bu yöntem, konumuna sola mı denetler *rect*. Aksi takdirde, bu yöntem konumu üzerinde olup olmadığını denetler *rect*.  
  
##  <a name="isresizable"></a>  CPane::IsResizable  
 Bölmesinde yeniden boyutlandırılabilir olup olmadığını belirtir.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeniden boyutlandırılabilir bölmesi ise TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel `CPane` nesneleri yeniden boyutlandırılabilir değildir.  
  
 Yerleştirme Yöneticisi'ni yeniden boyutlandırılabilir bayrağı bölmesi düzeni belirlemek için kullanır. Olmayan yeniden boyutlandırılabilir bölmeleri her zaman üst çerçevenin dış kenarları yer alır.  
  
 Olmayan yeniden boyutlandırılabilir bölmeleri, kapsayıcı yerleştirme içinde yer alamaz.  
  
##  <a name="istabbed"></a>  CPane::IsTabbed  
 Bölmesinde sekmeli pencerenin Sekme denetimine eklenen olup olmadığını belirler.  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde sekmeli TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Sekmeli durum kayan ayrı olarak kabul edilir, yerleşik ve durumlarını otomatik olarak gizle.  
  
##  <a name="loadstate"></a>  CPane::LoadState  
 Kayıt defterinden bölmesinde durumunu yükler.  
  
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
 Profili dizini.  
  
 [in] *uiID*  
 Bölmesinde kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde durumu başarıyla yüklendi TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework bölmesi durumu kayıt defterinden yüklenmesi için bu yöntemi çağırır. Tarafından kaydedilen ek bilgileri yüklemek için türetilen bir sınıfta geçersiz kılma [CPane::SaveState](#savestate).  
  
 Bu yöntem geçersiz kıldığınızda, ayrıca temel yöntemini çağırın ve temel yöntem false değerini döndürür, yanlış döndürür.  
  
##  <a name="m_bhandleminsize"></a>  CPane::m_bHandleMinSize  
 Minimum bölme boyutları tutarlı işlenmesine olanak tanır.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHandleMinSize;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanızdaki bir veya daha fazla yerleştirme bölmesine geçersiz kılarsanız `GetMinSize`, veya uygulamanız çağırıyorsa `SetMinSize`, bu statik üye bölmeleri nasıl boyutlandırılır tutarlı bir şekilde işlemek için framework etkinleştirmek için TRUE olarak ayarlamak isteyebilirsiniz.  
  
 Bu değer TRUE olarak ayarlanırsa, tüm bölmeleri boyutu, en az boyutun altında azaltılacak değil esnetilmiş kırpılır. Çerçeve pencere bölgeleri bölmesinde boyutlandırma amacıyla kullandığından, bu değeri TRUE olarak ayarlanırsa, yerleştirme bölmesi için pencere bölgesi boyutunu değiştirmeyin.  
  
##  <a name="m_recentdockinfo"></a>  CPane::m_recentDockInfo  
 Yeni takma bilgiler içerir.  
  
```  
CRecentDockSiteInfo m_recentDockInfo;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Framework, bu üye son yerleştirme bölmesi durumu bilgilerini depolar.  
  
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
|CBRS_ALIGN_TOP|Bir çerçeve penceresinin istemci alanına üstüne yerleştirilemediğinde bölmesinde sağlar.|  
|CBRS_ALIGN_BOTTOM|Bir çerçeve penceresinin istemci alanına altına yerleştirilemediğinde bölmesinde sağlar.|  
|CBRS_ALIGN_LEFT|Bir çerçeve penceresinin istemci alanına sol tarafına sabitlenebilir bölmesinde sağlar.|  
|CBRS_ALIGN_RIGHT|Bir çerçeve penceresinin istemci alanına sağ tarafına sabitlenebilir bölmesinde sağlar.|  
|CBRS_ALIGN_ANY|Herhangi bir çerçeve penceresinin istemci alanına tarafına sabitlenebilir bölmesinde sağlar.|  
  
 Varsa *dwAlignment* CBRS_ALIGN_LEFT veya CBRS_ALIGN_RIGHT bayrağını içeren bölmesinde ve sanal dikdörtgen yatay; Aksi takdirde, taşınan *dwAlignment* CBRS_ALIGN_TOP veya CBRS_ALIGN içerir Son_ bayrağı, bölmesi ve sanal dikdörtgen dikey olarak taşınır.  
  
##  <a name="movepane"></a>  CPane::MovePane  
 Bölme için belirtilen dikdörtgen taşır.  
  
```  
virtual CSize MovePane(
    CRect rectNew,  
    BOOL bForceMove,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rectNew*  
 Yeni dikdörtgene bölmesi için belirtir.  
  
 [in] *bForceMove*  
 TRUE ise bu yöntem, izin verilen minimum bölme boyutunu yoksayar. ( [CPane::GetMinSize](#getminsize)); Aksi takdirde, en az boyutu izin verilen en düşük olduğundan emin olmak gerekirse bölmesinde ayarlanır.  
  
 [in] *hdwp*  
 Kullanılmadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CSize` genişlik ve yükseklik yeni ve eski dikdörtgenler arasındaki farklılıkları içeren nesne (eski dikdörtgen - *rectNew*).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca yerleştirilebilir bölmeleri için kullanılır.  
  
##  <a name="onafterchangeparent"></a>  CPane::OnAfterChangeParent  
 Üst bölme değiştiğinde framework tarafından çağırılır.  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] *pWndOldParent*  
 Bölmedeki önceki üst pencere.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, yerleştirme veya kayan bir işlem nedeniyle bölmesinin üst değiştiğinde framework tarafından çağrılır.  
  
##  <a name="onafterdock"></a>  CPane::OnAfterDock  
 Bir bölme yerleştirildiğinde framework tarafından çağırılır.  
  
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
 Bir bölme gezinen sonra framework tarafından çağırılır.  
  
```  
virtual void OnAfterFloat();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme gezinen sonra herhangi bir işlem gerçekleştirmek istiyorsanız türetilen bir sınıfta bu yöntemin üzerine yazabilir.  
  
##  <a name="onbeforechangeparent"></a>  CPane::OnBeforeChangeParent  
 Bölmenin üst değiştirilmek üzereyken framework tarafından çağırılır.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] *pWndNewParent*  
 Yeni üst pencere belirtir.  
  
 [in] *bDelay*  
 Genel yerleştirme düzeni ayarlamayı geciktirmek için TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bölmesinin üst bölmesinde değiştiriliyor olduğundan değiştirilmek üzereyken framework tarafından çağırılır yerleştirilebilir ya da kaydırıldı.  
  
 Varsayılan olarak, çağırarak yerleştirme Bölmesi ile kaydı bölmesidir `CDockSite::RemovePane`.  
  
##  <a name="onbeforedock"></a>  CPane::OnBeforeDock  
 Bölme hakkında sabitlemek için çerçeve tarafından çağrılır.  
  
```  
virtual BOOL OnBeforeDock(
    CBasePane** ppDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] *ppDockBar*  
 Bu bölme için yerleştirme bölmesi belirtir.  
  
 [in] *lpRect*  
 Yerleştirme dikdörtgen belirtir.  
  
 [in] *dockMethod*  
 Yerleştirme yöntemini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmenin yerleştirilmiş olması gerekiyorsa TRUE. İşlev FALSE döndürürse, yerleştirme işlemi iptal edilecek.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem hakkında yerleştirilemediğinde bölmesidir çerçevesi tarafından çağrılır. Bir bölme son yerleştirildiğini önce herhangi bir işlem gerçekleştirmek istiyorsanız türetilen bir sınıfta bu yöntemin üzerine yazabilir.  
  
##  <a name="onbeforefloat"></a>  CPane::OnBeforeFloat  
 Kayan nokta bölme hakkında olduğunda framework tarafından çağırılır.  
  
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
 Bölmesinde kaydırıldı TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayan nokta bölme hakkında olduğunda bu yöntem framework tarafından çağırılır. Son bölmesinde gezinen önce herhangi bir işlem gerçekleştirmek istiyorsanız türetilen bir sınıfta bu yöntemin üzerine yazabilir.  
  
##  <a name="onpressclosebutton"></a>  CPane::OnPressCloseButton  
 Kullanıcı bölmesi için açıklama yazısını üzerinde Kapat düğmesine bastığında framework tarafından çağırılır.  
  
```  
virtual void OnPressCloseButton();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, kullanıcının bastığında çerçevesi tarafından çağrılır **Kapat** bölmedeki başlık çubuğunda. Hakkında bildirim almak için **Kapat** olay, türetilen bir sınıfta bu yöntemin üzerine yazabilir.  
  
##  <a name="onshowcontrolbarmenu"></a>  CPane::OnShowControlBarMenu  
 Özel bölmesinde menü gösterilmek üzereyken framework tarafından çağırılır.  
  
```  
virtual BOOL OnShowControlBarMenu(CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *noktası*  
 Menü konumu belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Menüde görüntülenen TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü bölmedeki davranışı, yani belirtmenizi sağlayan çeşitli öğeleri içerir: **kayan**, **Docking**, **AutoHide**, ve **Gizle**. Çağırarak tüm bölmeler için bu menüyü etkinleştirebilirsiniz [CDockingManager::EnableDockSiteMenu](../../mfc/reference/cdockingmanager-class.md#enabledocksitemenu).  
  
##  <a name="recalclayout"></a>  CPane::RecalcLayout  
 Düzen bölmesi bilgilerini yeniden hesaplar.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmesinde yerleştirilmişse, bu yöntem sanal dikdörtgenin bölmesi için bölmenin geçerli boyutuna boyutunu ayarlayarak güncelleştirir.  
  
 Bu yöntem, bölmesinde kayan, Mini çerçeve boyutu bölmesine boyutunu ayarlamak için üst Mini çerçevenin bildirir. Framework Mini çerçevenin en az bölmesi boyutu izin verilen en düşük olmasını sağlar ( [CPane::GetMinSize](#getminsize)) ve Mini çerçeve gerekirse yeniden boyutlandırılır.  
  
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
 Profili dizini.  
  
 [in] *uiID*  
 Bölmesinde kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durumu başarılı bir şekilde kaydedilmiş ise TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt defterine bölmesinde durumunu kaydettiğinde framework bu yöntemi çağırır. Geçersiz kılma `SaveState` ek bilgileri depolamak için türetilen bir sınıfta.  
  
 Bu yöntem geçersiz kıldığınızda, ayrıca temel yöntemini çağırın ve temel yöntem false değerini döndürür, yanlış döndürür.  
  
##  <a name="setactiveingroup"></a>  CPane::SetActiveInGroup  
 Bir bölme etkin olarak işaretler.  
  
```  
virtual void SetActiveInGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bActive*  
 BOOL bölmesinde etkin olarak işaretlenip işaretlenmediğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerleştirilebilir bölmesinde gösterilen veya Otomatik Gizle düğmesi seçildiğinde, ilgili otomatik gizleme bölmesi etkin olarak işaretlenir.  
  
 Bölmesiyle ilişkili bir Otomatik Gizle düğmesi görünümünü iki etkene dayanır. Bölmesinde etkinse ve `static BOOL CMFCAutoHideButton::m_bOverlappingTabs` true, simge ve bir etiket otomatik gizleme düğmesi framework görüntüler. Etkin olmayan bir bölmesi için framework yalnızca otomatik gizleme simgesi görüntüler.  
  
 Varsa `CMFCAutoHideButton::m_bOverlappingTabs` yanlış veya bölmesinde bir grupta yer almıyorsa, framework ilişkili otomatik gizle düğmesi bir simge ve bir etiket görüntüler.  
  
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
 Bölmenin üst kenarlığın piksel cinsinden genişliğini belirtir.  
  
 [in] *cxRight*  
 Bölmenin sağ kenarlığın piksel cinsinden genişliğini belirtir.  
  
 [in] *cyBottom*  
 Bölmesinin alt kenarlığın piksel cinsinden genişliğini belirtir.  
  
 [in] *lpRect*  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md) bölmesinin her kenarlığının piksel cinsinden genişliği içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmedeki Kenarlıklar boyutunu ayarlamak için bu işlevi çağırın.  
  
##  <a name="setclienthotspot"></a>  CPane::SetClientHotSpot  
 Kümeleri *etkin nokta* bölmesi.  
  
```  
void SetClientHotSpot(const CPoint& ptNew);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *ptNew*  
 A `CPoint` nesnesini yeni etkin nokta belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 *Etkin nokta* kullanıcı seçer ve bölmesinde taşımak tutan bölmesinde noktasıdır. Yerleşik konumundan bölmesinde sürüklendiğinde etkin nokta kesintisiz animasyon için kullanılır.  
  
##  <a name="setdockstate"></a>  CPane::SetDockState  
 Yerleştirme bölmesi için durum bilgilerini yükler.  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDockManager*  
 Ana çerçeve penceresinin yerleştirme yöneticisini işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bölmenin yerleştirme son durum bilgilerini geri yüklemek için framework tarafından çağırılır. Bir bölme son yerleştirme durum bilgilerini depolayan [CPane::m_recentDockInfo](#m_recentdockinfo). Daha fazla bilgi için [Crecentdocksiteınfo sınıfı](../../mfc/reference/crecentdocksiteinfo-class.md).  
  
 Ayrıca, bir dış kaynaktan bilgi bölmesinde yüklediğinizde takma durumunu ayarlamak için bu yöntem çağırabilirsiniz.  
  
##  <a name="setexclusiverowmode"></a>  CPane::SetExclusiveRowMode  
 Etkinleştirir veya özel satır modunu devre dışı bırakır.  
  
```  
virtual void SetExclusiveRowMode(BOOL bExclusive = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bExclusive*  
 Özel satır modunu etkinleştirmek için TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Etkinleştirmek veya özel satır modunu devre dışı bırakmak için bu yöntemi çağırın. Bir bölme özel satır modundayken diğer araç çubukları ile aynı satırda paylaşamazsınız.  
  
 Varsayılan olarak, tüm araç çubukları özel satır modu devre dışı sahip ve özel satır modu etkin menü çubuğu vardır.  
  
##  <a name="setminsize"></a>  CPane::SetMinSize  
 Bölme boyutu izin verilen en düşük ayarlar.  
  
```  
void SetMinSize(const CSize& size);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *boyutu*  
 A `CSize` bölmesi boyutu izin verilen en düşük içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setvirtualrect"></a>  CPane::SetVirtualRect  
 Kümeleri *sanal dikdörtgen* bölmesi.  
  
```  
void SetVirtualRect(
    const CRect& rect,  
    BOOL bMapToParent = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dikdörtgen*  
 A `CRect` sanal dikdörtgenin ayarlanacak belirleyen nesne.  
  
 [in] *bMapToParent*  
 TRUE ise belirtin *rect* noktalarına göre üst pencere içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 A *sanal dikdörtgen* taşındığında, bu bölme orijinal konumlarından depolar. Framework sanal dikdörtgen özgün konumuna geri yüklemek için kullanabilirsiniz.  
  
 Bölmeleri program aracılığıyla taşıdığınız sürece sanal dikdörtgenler için ilgili yöntemlerini çağırmanız gerekmez.  
  
##  <a name="setminiframertc"></a>  CPane::SetMiniFrameRTC  
 Varsayılan Mini çerçeve penceresi için çalışma zamanı sınıf bilgileri ayarlar.  
  
```  
void SetMiniFrameRTC(CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] *pClass*  
 Mini çerçeve penceresi için çalışma zamanı sınıf bilgileri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme kaydırıldı, onu konur bir [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) (mini çerçeve) penceresi. Özel bir sağlayabilir `CPaneFrameWnd`-türetilmiş sınıf olacak kullanılabilir [CPane::CreateDefaultMiniframe](#createdefaultminiframe) çağrılır.  
  
##  <a name="stretchpanedeferwndpos"></a>  CPane::StretchPaneDeferWndPos  
 Yatay veya dikey olarak yerleştirme stili tabanlı bölmesinde uzatır.  
  
```  
virtual int StretchPaneDeferWndPos(
    int nStretchSize,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nStretchSize*  
 Piksel cinsinden bölmesinde esnetme için tutar. Bölmeyi daralt için negatif bir değer kullanın.  
  
 [in] *hdwp*  
 Kullanılmadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Piksel cinsinden bölmesinde esnetilmiş gerçek tutar.  
  
### <a name="remarks"></a>Açıklamalar  
 Gerekirse, bu yöntem değiştirirse *nStretchSize* bölmesinde boyut sınırını aşmadığından emin olmak için. Bu sınırlar çağırarak elde edilen [CPane::GetAvailableStretchSize](#getavailablestretchsize) ve [CPane::GetAvailableExpandSize](#getavailableexpandsize).  
  
##  <a name="toggleautohide"></a>  CPane::ToggleAutoHide  
 Otomatik gizleme moduna geçiş yapar.  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Otomatik gizleme moduna geçiş yapmak için bu yöntemi çağırın. Bir bölme için bir ana çerçeve penceresi otomatik gizleme moduna geçiş olması için yerleştirilmiş olmalıdır.  
  
##  <a name="undockpane"></a>  CPane::UndockPane  
 Dock sitesiyle, varsayılan kaydırıcı veya mini çerçevenin şu anda dayandığı bölmesinde kaldırır.  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bDelay*  
 FALSE ise, framework çağırır [CBasePane::AdjustDockingLayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout) yerleştirme düzeni ayarlamak için.  
  
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
 A `CPoint` nesnesini bölmesinde kaydırmak, bir uzaklığını belirtir.  
  
 [in] *sizeNew*  
 A `CSize` nesnesini bölmesi için yeni bir boyut belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk aşırı yükleme, geçerli konumunu ve boyutunu kullanarak sanal bir dikdörtgen ayarlar.  
  
 İkinci aşırı yükleme tarafından belirtilen miktarda sanal dikdörtgen kaydırır *ptOffset*.  
  
 Geçerli konumunu bölmesinde ve tarafından belirtilen boyutu kullanarak sanal bir dikdörtgen üçüncü aşırı yükleme ayarlar *sizeNew*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CBasePane Sınıfı](../../mfc/reference/cbasepane-class.md)
