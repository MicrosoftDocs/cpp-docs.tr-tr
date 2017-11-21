---
title: "CDockablePane sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockablePane
- AFXDOCKABLEPANE/CDockablePane
- AFXDOCKABLEPANE/CDockablePane::CDockablePane
- AFXDOCKABLEPANE/CDockablePane::AttachToTabWnd
- AFXDOCKABLEPANE/CDockablePane::CalcFixedLayout
- AFXDOCKABLEPANE/CDockablePane::CanAcceptMiniFrame
- AFXDOCKABLEPANE/CDockablePane::CanAcceptPane
- AFXDOCKABLEPANE/CDockablePane::CanAutoHide
- AFXDOCKABLEPANE/CDockablePane::CanBeAttached
- AFXDOCKABLEPANE/CDockablePane::ConvertToTabbedDocument
- AFXDOCKABLEPANE/CDockablePane::CopyState
- AFXDOCKABLEPANE/CDockablePane::Create
- AFXDOCKABLEPANE/CDockablePane::CreateDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::CreateEx
- AFXDOCKABLEPANE/CDockablePane::CreateTabbedPane
- AFXDOCKABLEPANE/CDockablePane::DockPaneContainer
- AFXDOCKABLEPANE/CDockablePane::DockPaneStandard
- AFXDOCKABLEPANE/CDockablePane::DockToRecentPos
- AFXDOCKABLEPANE/CDockablePane::DockToWindow
- AFXDOCKABLEPANE/CDockablePane::EnableAutohideAll
- AFXDOCKABLEPANE/CDockablePane::EnableGripper
- AFXDOCKABLEPANE/CDockablePane::GetAHRestoredRect
- AFXDOCKABLEPANE/CDockablePane::GetAHSlideMode
- AFXDOCKABLEPANE/CDockablePane::GetCaptionHeight
- AFXDOCKABLEPANE/CDockablePane::GetDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::GetDockingStatus
- AFXDOCKABLEPANE/CDockablePane::GetDragSensitivity
- AFXDOCKABLEPANE/CDockablePane::GetLastPercentInPaneContainer
- AFXDOCKABLEPANE/CDockablePane::GetTabArea
- AFXDOCKABLEPANE/CDockablePane::GetTabbedPaneRTC
- AFXDOCKABLEPANE/CDockablePane::HasAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::HitTest
- AFXDOCKABLEPANE/CDockablePane::IsAutohideAllEnabled
- AFXDOCKABLEPANE/CDockablePane::IsAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::IsDocked
- AFXDOCKABLEPANE/CDockablePane::IsHideInAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::IsInFloatingMultiPaneFrameWnd
- AFXDOCKABLEPANE/CDockablePane::IsResizable
- AFXDOCKABLEPANE/CDockablePane::IsTabLocationBottom
- AFXDOCKABLEPANE/CDockablePane::IsTracked
- AFXDOCKABLEPANE/CDockablePane::IsVisible
- AFXDOCKABLEPANE/CDockablePane::OnAfterChangeParent
- AFXDOCKABLEPANE/CDockablePane::OnAfterDockFromMiniFrame
- AFXDOCKABLEPANE/CDockablePane::OnBeforeChangeParent
- AFXDOCKABLEPANE/CDockablePane::OnBeforeFloat
- AFXDOCKABLEPANE/CDockablePane::RemoveFromDefaultPaneDividier
- AFXDOCKABLEPANE/CDockablePane::ReplacePane
- AFXDOCKABLEPANE/CDockablePane::RestoreDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::SetAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::SetAutoHideParents
- AFXDOCKABLEPANE/CDockablePane::SetLastPercentInPaneContainer
- AFXDOCKABLEPANE/CDockablePane::SetRestoredDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::SetTabbedPaneRTC
- AFXDOCKABLEPANE/CDockablePane::ShowPane
- AFXDOCKABLEPANE/CDockablePane::Slide
- AFXDOCKABLEPANE/CDockablePane::ToggleAutoHide
- AFXDOCKABLEPANE/CDockablePane::UndockPane
- AFXDOCKABLEPANE/CDockablePane::CheckAutoHideCondition
- AFXDOCKABLEPANE/CDockablePane::CheckStopSlideCondition
- AFXDOCKABLEPANE/CDockablePane::DrawCaption
- AFXDOCKABLEPANE/CDockablePane::OnPressButtons
- AFXDOCKABLEPANE/CDockablePane::OnSlide
- AFXDOCKABLEPANE/CDockablePane::m_bDisableAnimation
- AFXDOCKABLEPANE/CDockablePane::m_bHideInAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::m_nSlideSteps
dev_langs: C++
helpviewer_keywords:
- CDockablePane [MFC], CDockablePane
- CDockablePane [MFC], AttachToTabWnd
- CDockablePane [MFC], CalcFixedLayout
- CDockablePane [MFC], CanAcceptMiniFrame
- CDockablePane [MFC], CanAcceptPane
- CDockablePane [MFC], CanAutoHide
- CDockablePane [MFC], CanBeAttached
- CDockablePane [MFC], ConvertToTabbedDocument
- CDockablePane [MFC], CopyState
- CDockablePane [MFC], Create
- CDockablePane [MFC], CreateDefaultPaneDivider
- CDockablePane [MFC], CreateEx
- CDockablePane [MFC], CreateTabbedPane
- CDockablePane [MFC], DockPaneContainer
- CDockablePane [MFC], DockPaneStandard
- CDockablePane [MFC], DockToRecentPos
- CDockablePane [MFC], DockToWindow
- CDockablePane [MFC], EnableAutohideAll
- CDockablePane [MFC], EnableGripper
- CDockablePane [MFC], GetAHRestoredRect
- CDockablePane [MFC], GetAHSlideMode
- CDockablePane [MFC], GetCaptionHeight
- CDockablePane [MFC], GetDefaultPaneDivider
- CDockablePane [MFC], GetDockingStatus
- CDockablePane [MFC], GetDragSensitivity
- CDockablePane [MFC], GetLastPercentInPaneContainer
- CDockablePane [MFC], GetTabArea
- CDockablePane [MFC], GetTabbedPaneRTC
- CDockablePane [MFC], HasAutoHideMode
- CDockablePane [MFC], HitTest
- CDockablePane [MFC], IsAutohideAllEnabled
- CDockablePane [MFC], IsAutoHideMode
- CDockablePane [MFC], IsDocked
- CDockablePane [MFC], IsHideInAutoHideMode
- CDockablePane [MFC], IsInFloatingMultiPaneFrameWnd
- CDockablePane [MFC], IsResizable
- CDockablePane [MFC], IsTabLocationBottom
- CDockablePane [MFC], IsTracked
- CDockablePane [MFC], IsVisible
- CDockablePane [MFC], OnAfterChangeParent
- CDockablePane [MFC], OnAfterDockFromMiniFrame
- CDockablePane [MFC], OnBeforeChangeParent
- CDockablePane [MFC], OnBeforeFloat
- CDockablePane [MFC], RemoveFromDefaultPaneDividier
- CDockablePane [MFC], ReplacePane
- CDockablePane [MFC], RestoreDefaultPaneDivider
- CDockablePane [MFC], SetAutoHideMode
- CDockablePane [MFC], SetAutoHideParents
- CDockablePane [MFC], SetLastPercentInPaneContainer
- CDockablePane [MFC], SetRestoredDefaultPaneDivider
- CDockablePane [MFC], SetTabbedPaneRTC
- CDockablePane [MFC], ShowPane
- CDockablePane [MFC], Slide
- CDockablePane [MFC], ToggleAutoHide
- CDockablePane [MFC], UndockPane
- CDockablePane [MFC], CheckAutoHideCondition
- CDockablePane [MFC], CheckStopSlideCondition
- CDockablePane [MFC], DrawCaption
- CDockablePane [MFC], OnPressButtons
- CDockablePane [MFC], OnSlide
- CDockablePane [MFC], m_bDisableAnimation
- CDockablePane [MFC], m_bHideInAutoHideMode
- CDockablePane [MFC], m_nSlideSteps
ms.assetid: e2495f4c-765f-48f9-a2e2-e45e47608d91
caps.latest.revision: "34"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3072e4504fc70e75888607d4f263b39532f69b51
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdockablepane-class"></a>CDockablePane sınıfı
Ya da bir yerleştirme sitede yerleştirilebilir ya da sekmeli bölmesinde yer bölme uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDockablePane : public CPane  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDockablePane::CDockablePane](#cdockablepane)|Oluşturur ve başlatır bir `CDockablePane` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDockablePane::AttachToTabWnd](#attachtotabwnd)|Bir bölme başka bir bölüme ekler. Sekmeli bölmesini oluşturur.|  
|[CDockablePane::CalcFixedLayout](#calcfixedlayout)|Bölmesinde dikdörtgen boyutu döndürür.|  
|[CDockablePane::CanAcceptMiniFrame](#canacceptminiframe)|Belirtilen mini çerçeve bölmesine yerleştirilmiş olup olmadığını belirler.|  
|[CDockablePane::CanAcceptPane](#canacceptpane)|Başka bir bölme geçerli bölmesine yerleştirilmiş olup olmadığını belirler.|  
|[CDockablePane::CanAutoHide](#canautohide)|Bölmesinde otomatik olarak Gizle modunu destekleyip desteklemediğini belirler. (Geçersiz kılmaları [CBasePane::CanAutoHide](../../mfc/reference/cbasepane-class.md#canautohide).)|  
|[CDockablePane::CanBeAttached](#canbeattached)|Başka bir bölüme geçerli bölmesini yerleştirilmiş olup olmadığını belirler.|  
|[CDockablePane::ConvertToTabbedDocument](#converttotabbeddocument)|Bir veya daha fazla dockable bölmeleri MDI sekmeli belgelere dönüştürür.|  
|[CDockablePane::CopyState](#copystate)|Dockable bölme durumunu kopyalar.|  
|[CDockablePane::Create](#create)|Windows Denetim oluşturur ve ona ekler `CDockablePane` nesnesi.|  
|[CDockablePane::CreateDefaultPaneDivider](#createdefaultpanedivider)|Varsayılan bölücüyü bölmesi için bir çerçeve penceresinde yerleşik olduğunda olarak oluşturur.|  
|[CDockablePane::CreateEx](#createex)|Windows Denetim oluşturur ve ona ekler `CDockablePane` nesnesi.|  
|[CDockablePane::CreateTabbedPane](#createtabbedpane)|Sekmeli bölmesinde geçerli bölmesinden oluşturur.|  
|[CDockablePane::DockPaneContainer](#dockpanecontainer)|Bir kapsayıcı bölmesine docks.|  
|[CDockablePane::DockPaneStandard](#dockpanestandard)|Bir bölme anahat (standart) yerleştirme kullanarak docks.|  
|`CDockablePane::DockToFrameWindow`|Dahili olarak kullanılır. Bir bölme sabitlemek için kullanmak [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) veya [CDockablePane::DockToWindow](#docktowindow).|  
|[CDockablePane::DockToRecentPos](#docktorecentpos)|Bir bölme saklı son yerleştirme konumuna docks.|  
|[CDockablePane::DockToWindow](#docktowindow)|Başka bir takma bölmesine bir takma bölme noktalarını.|  
|[CDockablePane::EnableAutohideAll](#enableautohideall)|Etkinleştirir veya diğer bölmeleri kapsayıcısında birlikte bu bölme için otomatik olarak Gizle modunu devre dışı bırakır.|  
|[CDockablePane::EnableGripper](#enablegripper)|Gösterir veya gizler resim yazısı (kavrayıcının).|  
|[CDockablePane::GetAHRestoredRect](#getahrestoredrect)|Görünür zaman otomatik olarak gizle modunda bölmesinde konumunu belirtir.|  
|[CDockablePane::GetAHSlideMode](#getahslidemode)|Bölme için Otomatik Gizle slayt modunu alır.|  
|`CDockablePane::GetAutoHideButton`|Dahili olarak kullanılır.|  
|`CDockablePane::GetAutoHideToolBar`|Dahili olarak kullanılır.|  
|[CDockablePane::GetCaptionHeight](#getcaptionheight)|Geçerli resim yazısı yüksekliğini döndürür.|  
|[CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)|Bölmesinde ait kapsayıcı için varsayılan bölmesinde ayırıcı döndürür.|  
|[CDockablePane::GetDockingStatus](#getdockingstatus)|Bir bölme yerleşik yeteneğini sağlanan işaretçi konum temelinde belirler.|  
|[CDockablePane::GetDragSensitivity](#getdragsensitivity)|Yerleştirme bölmesine sürükleyin duyarlılığını döndürür.|  
|[CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)|Bir bölme kapsayıcısının içinde kapladığı alanı yüzdesini alır.|  
|[CDockablePane::GetTabArea](#gettabarea)|Bölmesinde sekme alanı alır.|  
|[CDockablePane::GetTabbedPaneRTC](#gettabbedpanertc)|Başka bir bölme geçerli bölmesine noktalarını kaydedildiğinde sekmeli bir pencere ilgili çalışma zamanı sınıf bilgileri döndürür.|  
|[CDockablePane::HasAutoHideMode](#hasautohidemode)|Yerleştirme bölmesinde otomatik olarak gizle moduna geçiş olup olmadığını belirtir.|  
|[CDockablePane::HitTest](#hittest)|Belirli bir konuma fare burada kullanıcı bölmesinde belirtir.|  
|`CDockablePane::IsAccessibilityCompatible`|Dahili olarak kullanılır.|  
|[CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)|Yerleştirme bölmesinde ve kapsayıcıdaki tüm diğer bölmeleri otomatik gizleme modunda yerleştirilebilir olup olmadığını gösterir.|  
|[CDockablePane::IsAutoHideMode](#isautohidemode)|Bir bölme otomatik gizleme modunda olup olmadığını belirler.|  
|`CDockablePane::IsChangeState`|Dahili olarak kullanılır.|  
|[CDockablePane::IsDocked](#isdocked)|Geçerli bölmesini yerleştirilmiş olup olmadığını belirler.|  
|[CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode)|Otomatik olarak gizle modunda, gösterilen (gizli çağırarak veya varsa) olan bir bölme davranışını belirler `ShowPane`.|  
|[CDockablePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Bölmesinde çok bölmesi çerçeve penceresinde olup olmadığını belirtir.|  
|[CDockablePane::IsResizable](#isresizable)|Bölmesinde yeniden boyutlandırılabilir olup olmadığını belirtir.|  
|[CDockablePane::IsTabLocationBottom](#istablocationbottom)|Sekmeleri üstüne veya altına bölmesinin bulunduğu olup olmadığını belirtir.|  
|[CDockablePane::IsTracked](#istracked)|Kullanıcı tarafından bir bölme sürüklenen olup olmadığını belirtir.|  
|[CDockablePane::IsVisible](#isvisible)|Geçerli bölmesinde görünür olup olmadığını belirler.|  
|[CDockablePane::LoadState](http://msdn.microsoft.com/en-us/96110136-4f46-4764-8a76-3b4abaf77917)|Dahili olarak kullanılır.|  
|[CDockablePane::OnAfterChangeParent](#onafterchangeparent)|Bölmesinin üst değiştiğinde çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CPane::OnAfterChangeParent](../../mfc/reference/cpane-class.md#onafterchangeparent).)|  
|[CDockablePane::OnAfterDockFromMiniFrame](#onafterdockfromminiframe)|Kayan bir takma çubuğu bir çerçeve penceresinde noktalarını çerçevesi tarafından çağrılır.|  
|[CDockablePane::OnBeforeChangeParent](#onbeforechangeparent)|Bölmesinin üst değiştirilmek üzereyken çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CPane::OnBeforeChangeParent](../../mfc/reference/cpane-class.md#onbeforechangeparent).)|  
|[CDockablePane::OnBeforeFloat](#onbeforefloat)|Kayana bölme hakkında olduğunda çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|  
|[CDockablePane::RemoveFromDefaultPaneDividier](#removefromdefaultpanedividier)|Bir bölme takılı olduğunda framework bu yöntemi çağırır.|  
|[CDockablePane::ReplacePane](#replacepane)|Bölmesinde belirtilen bölmesiyle değiştirir.|  
|[CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider)|Varsayılan bölmesinde ayırıcı geri yüklemek için bir bölme seri olarak framework bu yöntemi çağırır.|  
|`CDockablePane::SaveState`|Dahili olarak kullanılır.|  
|`CDockablePane::Serialize`|Bölmesinde serileştirir. (Geçersiz kılmaları `CBasePane::Serialize`.)|  
|[CDockablePane::SetAutoHideMode](#setautohidemode)|Yerleştirme bölmesinde görünür arasında geçiş yapar ve otomatik olarak gizle modu.|  
|[CDockablePane::SetAutoHideParents](#setautohideparents)|Otomatik olarak gizle düğmesi ve otomatik olarak gizle araç bölmesini için ayarlar.|  
|`CDockablePane::SetDefaultPaneDivider`|Dahili olarak kullanılır.|  
|[CDockablePane::SetLastPercentInPaneContainer](#setlastpercentinpanecontainer)|Bir bölme kapsayıcısının içinde kapladığı alanı yüzdesi ayarlar.|  
|`CDockablePane::SetResizeMode`|Dahili olarak kullanılır.|  
|[CDockablePane::SetRestoredDefaultPaneDivider](#setrestoreddefaultpanedivider)|Geri yüklenen varsayılan bölmesinde ayırıcı ayarlar.|  
|[CDockablePane::SetTabbedPaneRTC](#settabbedpanertc)|İki bölme birlikte yerleştirme kaydedildiğinde sekmeli bir pencere için çalışma zamanı sınıf bilgileri ayarlar.|  
|[CDockablePane::ShowPane](#showpane)|Gösterir veya gizler bir bölme.|  
|[CDockablePane::Slide](#slide)|Gösterir veya yalnızca bölmesinde otomatik olarak gizle modundayken görüntüleyen bir kayan animasyon bölmesiyle gizler.|  
|[CDockablePane::ToggleAutoHide](#toggleautohide)|Otomatik olarak gizle modu değiştirir. (Geçersiz kılmaları [CPane::ToggleAutoHide](../../mfc/reference/cpane-class.md#toggleautohide) .)|  
|[CDockablePane::UndockPane](#undockpane)|Ana çerçeve penceresi veya miniframe pencere kapsayıcı bölmesinden çıkarabilirsiniz.|  
|`CDockablePane::UnSetAutoHideMode`|Dahili olarak kullanılır. Otomatik olarak gizle modu ayarlamak için kullanın [CDockablePane::SetAutoHideMode](#setautohidemode)|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDockablePane::CheckAutoHideCondition](#checkautohidecondition)|(Otomatik olarak gizle modunda) takma bölmenin gizli olup olmadığını belirler.|  
|[CDockablePane::CheckStopSlideCondition](#checkstopslidecondition)|Yerleştirme Bölmesini Gizle otomatik kayan zaman durması gerektiğini belirler.|  
|[CDockablePane::DrawCaption](#drawcaption)|Yerleştirme Bölmesi Başlığı (kavrayıcının) çizer.|  
|[CDockablePane::OnPressButtons](#onpressbuttons)|Kullanıcının bir resim yazısı düğmesine dışında bastığında adlı `AFX_HTCLOSE` ve `AFX_HTMAXBUTTON` düğmeler.|  
|[CDockablePane::OnSlide](#onslide)|Bölmesinde da gösterilen gizli ya da zaman otomatik olarak gizle slayt etkisi işlenecek çerçevesi tarafından çağrılır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDockablePane::m_bDisableAnimation](#m_bdisableanimation)|Otomatik olarak gizle animasyon dockable bölmesinin etkinleştirilip etkinleştirilmeyeceğini belirtir.|  
|[CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)|Bölmesinde otomatik olarak gizle modundayken bölmesinde davranışını belirler.|  
|[CDockablePane::m_nSlideSteps](#m_nslidesteps)|Yüklenmekte olan bölmesinin animasyon hızı belirtir gösterilen veya otomatik olarak gizle modunda gizli.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDockablePane`aşağıdaki işlevleri gerçekleştirir:  
  
-   Bir bölme bir ana çerçeve penceresi yerleştirme.  
  
-   Bir bölme otomatik gizleme moduna geçiriliyor.  
  
-   Bir bölme sekmeli pencere ekleniyor.  
  
-   Bir miniframe pencere bölmesinde kayan.  
  
-   Bir bölme miniframe penceresinde kayan başka bir bölüme yerleştirme.  
  
-   Bir bölmesini yeniden boyutlandırma.  
  
-   Yükleme ve durumu takma bölmesi için kaydetme.  
  
    > [!NOTE]
    >  Durum bilgileri Windows kayıt defterine kaydedilir.  
  
-   Bir bölmesi olan veya olmayan bir başlık oluşturma. Resim yazısını bir metin etiketi olabilir ve bir gradyan renkle doldurulur.  
  
-   Bir bölme bölmesinin içeriğini görüntülenirken sürükleme  
  
-   Bir bölme dikdörtgeni Sürükle görüntülenirken sürükleyerek.  
  
 Bir takma bölmesi, uygulamanızda kullanmak için bölmesinde sınıfından türetilen `CDockablePane` sınıfı. Ana çerçeve pencere nesnesi veya, bölmesinin örneğini denetleyen bir pencere nesnesi ya da türetilmiş nesne ekleyin. ' I çağırın [CDockablePane::Create](#create) yöntemi veya [CDockablePane::CreateEx](#createex) , işlerken yöntemi `WM_CREATE` ana çerçeve penceresindeki ileti. Son olarak, arayarak bölmesini nesnesi belirleme [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking), [CBasePane::DockPane](../../mfc/reference/cbasepane-class.md#dockpane), veya [CDockablePane::AttachToTabWnd](#attachtotabwnd).  
  
## <a name="customization-tips"></a>Özelleştirme ipuçları  
 Aşağıdaki ipuçları uygulamak `CDockablePane` nesneler:  
  
-   Çağırırsanız [CDockablePane::AttachToTabWnd](#attachtotabwnd) iki sekmeli olmayan, dockable bölmeleri için sekmeli bir pencere için bir işaretçi olarak döndüreceği `ppTabbedControlBar` parametresi. Bu parametre kullanarak sekmeli penceresine sekme eklemeye devam edebilirsiniz.  
  
-   Tarafından oluşturulan sekmeli bölmesinde tür [CDockablePane::AttachToTabWnd](#attachtotabwnd) tarafından belirlenen `CDockablePane` nesnesinde `pTabControlBarAttachTo` parametresi. Çağırabilirsiniz [CDockablePane::SetTabbedPaneRTC](#settabbedpanertc) için sekmeli bölmesinde tür kümesi `CDockablePane` oluşturur. Varsayılan türü tarafından belirlenen `dwTabbedStyle` , [CDockablePane::Create](#create) ilk oluşturduğunuzda `CDockablePane`. Varsa `dwTabbedStyle` AFX_CBRS_OUTLOOK_TABS varsayılan türü olan [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)if `dwTabbedStyle` AFX_CBRS_REGULAR_TABS varsayılan türü olan [CTabbedPane sınıfı](../../mfc/reference/ctabbedpane-class.md).  
  
-   Başka bir dockable bölmesinde yerleştirme istiyorsanız, çağrı [CDockablePane::DockToWindow](#docktowindow) yöntemi. Bu yöntemi çağırmadan önce başka bir yere özgün bölmesi yuvalanmış gerekir.  
  
-   Üye değişkeni [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode) denetimlerini dockable bölmeleri otomatik davranır nasıl Gizle modu çağırdığınızda [CDockablePane::ShowPane](#showpane). Bu üye değişkeni ayarlanmışsa `TRUE`, dockable bölmeleri ve kendi otomatik gizle düğmeleri gizli. Aksi takdirde, bunlar içeri ve dışarı slayt.  
  
-   Ayarlayarak otomatik gizleme animasyon devre dışı bırakabilirsiniz [CDockablePane::m_bDisableAnimation](#m_bdisableanimation) üye değişkeni `TRUE`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl yapılandırılacağını göstermektedir bir `CDockablePane` çeşitli yöntemlerle kullanarak nesne `CDockablePane` sınıfı. Örneğin, otomatik olarak gizle dockable bölmesinin tüm özelliği etkinleştirmek, resim yazısını veya kavrama etkinleştirmek, otomatik olarak Gizle modunu etkinleştirmek, bölmesini göster ve otomatik olarak gizle modunda bir bölme animasyon göstermektedir. Bu kod parçacığını parçası olan [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#27](../../mfc/codesnippet/cpp/cdockablepane-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#28](../../mfc/codesnippet/cpp/cdockablepane-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxDockablePane.h  
  
##  <a name="attachtotabwnd"></a>CDockablePane::AttachToTabWnd  
 Geçerli bölmesini sekmeli bölmesi oluşturma bir hedef bölmesine ekler.  
  
```  
virtual CDockablePane* AttachToTabWnd(
    CDockablePane* pTabControlBarAttachTo,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bSetActive= TRUE,  
    CDockablePane** ppTabbedControlBar = NULL);  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out]`pTabControlBarAttachTo`  
 Geçerli bölmesini ekler hedef bölmesinde belirtir. Hedef bölmesinde dockable bölmesinde olması gerekir.  
  
 [in]`dockMethod`  
 Takma yöntemini belirtir.  
  
 [in]`bSetActive`  
 `TRUE`Sekmeli bölmesinde sonra ekleme işlemi etkinleştirmek için; Aksi takdirde `FALSE`.  
  
 [out]`ppTabbedControlBar`  
 Ekleme işlemi sonuçları sekmeli bölmesi içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi geçerli bölmesine sekmeli bölmesi değilse; Aksi takdirde attach işleminin sonuçları sekmeli bölmesi için bir işaretçi. Dönüş değeri `NULL` geçerli bölmesini bağlıysa ya da bir hata oluşur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi kullanarak başka bir bölüme bir dockable bölmesinde ekler, aşağıdakiler gerçekleşir:  
  
1.  Framework denetimleri olup olmadığını hedef bölmesinde `pTabControlBarAttachTo` olan bir normal yerleştirme bölmesinde veya öğesinden türetilmiş varsa [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md).  
  
2.  Hedef bölmesinde sekmeli bölmesinde ise, framework geçerli bölmesini bir sekme eklenir.  
  
3.  Hedef bölmesinde normal bir takma bölmesi ise, framework sekmeli bölmesini oluşturur.  
  
    -   Framework çağrıları `pTabControlBarAttachTo->CreateTabbedPane`. Yeni sekmeli bölmesinin stilini bağlıdır `m_pTabbedControlBarRTC` üyesi. Varsayılan olarak, bu üye için çalışma zamanı sınıfının ayarlanır [CTabbedPane](../../mfc/reference/ctabbedpane-class.md). Geçirirseniz `AFX_CBRS_OUTLOOK_TABS` olarak stil `dwTabbedStyle` parametresi [CDockablePane::Create](#create) yöntemi, çalışma zamanı sınıf nesnesi için çalışma zamanı sınıfının ayarlanır [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md). Bu üye yeni bölmesinin stilini değiştirmek için istediğiniz zaman değiştirebilirsiniz.  
  
    -   Bu yöntem sekmeli bölmesinde oluşturduğunda, framework işaretçisine değiştirir `pTabControlBarAttachTo` (bölmesinde bir çoklu miniframe penceresinde yerleşik veya kayan ise) yeni sekmeli bölmesine işaretçiyle.  
  
    -   Framework ekler `pTabControlBarAttachTo` ilk sekme sekmeli bölmesine bölmesi. Framework geçerli bölmesini sonra ikinci bir sekme ekler.  
  
4.  Geçerli bölmesini türetilir varsa `CBaseTabbedPane`, tüm sekmelerinin taşınması `pTabControlBarAttachTo` ve geçerli bölmesini yok. Bu yöntemi çağırdığınızda yöntem döndüğünde geçerli bölmesini gösteren bir işaretçi geçersiz olabilir çünkü bu nedenle dikkatli olun.  
  
 Bir bölme başka bir takma düzeni oluştururken eklerseniz, ayarlamak `dockMethod` için `DM_SHOW`.  
  
 Başka bir bölme eklemeden önce ilk bölmesinde yerleştirme.  
  
##  <a name="calcfixedlayout"></a>CDockablePane::CalcFixedLayout  
 Bölmesinde dikdörtgen boyutu döndürür.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bStretch`  
 Kullanılmadı.  
  
 [in]`bHorz`  
 Kullanılmadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CSize` bölmesinde dikdörtgen boyutunu içeren nesne.  
  
##  <a name="canacceptminiframe"></a>CDockablePane::CanAcceptMiniFrame  
 Belirtilen kısa çerçeve bölmesine yerleştirilmiş olup olmadığını belirler.  
  
```  
virtual BOOL CanAcceptMiniFrame(CPaneFrameWnd* pMiniFrame) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pMiniFrame`  
 İşaretçi bir `CPaneFrameWnd` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`varsa `pMiniFrame` bölmesine yerleşik; Aksi takdirde olabilir `FALSE`.  
  
##  <a name="canacceptpane"></a>CDockablePane::CanAcceptPane  
 Başka bir bölme geçerli bölmesine yerleştirilmiş olup olmadığını belirler.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 Geçerli bölmesine sabitlemek için bölmesinde belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Belirtilen bölmesinde bu bölmesine; yerleşik, Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme geçerli bölmesine yerleştirilir önce framework bu yöntemi çağırır.  
  
 Bu işlevi etkinleştirmek veya belirli bir bölmesine yerleştirme devre dışı bırakmak için bir türetilmiş sınıfta geçersiz kılar.  
  
 Varsayılan olarak, bu yöntem `TRUE` her iki `pBar` veya üst türü `CDockablePane`.  
  
##  <a name="canautohide"></a>CDockablePane::CanAutoHide  
 Bölmesinde otomatik olarak gizle olup olmadığını belirler.  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bölmesinde otomatik olarak gizle varsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 `CDockablePane::CanAutoHide`döndürür `FALSE` aşağıdaki durumlardan birinde:  
  
-   Bölmesinde üst öğeye sahip.  
  
-   Yerleştirme Yöneticisi otomatik gizleme bölmeleri izin vermiyor.  
  
-   Bölmesinde sabitlenmiş değildir.  
  
##  <a name="canbeattached"></a>CDockablePane::CanBeAttached  
 Başka bir bölüme geçerli bölmesini yerleştirilmiş olup olmadığını belirler.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`dockable bölmesinde başka bir bölme veya ana çerçeve penceresi; yerleşik varsa Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem her zaman döndürür `TRUE`. Etkinleştirmek veya arama olmadan yerleştirme devre dışı bırakmak için bir türetilmiş sınıfta bu yöntemin üzerine [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).  
  
##  <a name="cdockablepane"></a>CDockablePane::CDockablePane  
 Oluşturur ve başlatır bir [CDockablePane](../../mfc/reference/cdockablepane-class.md) nesnesi.  
  
```  
CDockablePane();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dockable bölmesinde nesneyi oluşturduktan sonra arama [CDockablePane::Create](#create) veya [CDockablePane::CreateEx](#createex) oluşturabilirsiniz.  
  
##  <a name="converttotabbeddocument"></a>CDockablePane::ConvertToTabbedDocument  
 Bir veya daha fazla dockable bölmeleri MDI sekmeli belgelere dönüştürür.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bActiveTabOnly`  
 Dönüştürürken bir `CTabbedPane`, belirtin `TRUE` yalnızca etkin sekme dönüştürülemiyor. Belirtin `FALSE` bölmesinde tüm sekmeler dönüştürülemiyor.  
  
##  <a name="checkautohidecondition"></a>CDockablePane::CheckAutoHideCondition  
 (Autohide modu olarak da bilinir) takma bölmenin gizli olup olmadığını belirler.  
  
```  
virtual BOOL CheckAutoHideCondition();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Gizle koşul karşılandığında; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve bir süreölçer düzenli aralıklarla autohide dockable bölmesinde gizlenip gizlenmeyeceğini denetlemek için kullanılır. Yöntem `TRUE` bölmesinde etkin değil, bölmesinde değil boyutlandırılır ve fare işaretçisini bölmesinde değil.  
  
 Önceki tüm koşullar karşılanıyorsa framework çağırması [CDockablePane::Slide](#slide) bölmesini gizlemek için.  
  
##  <a name="checkstopslidecondition"></a>CDockablePane::CheckStopSlideCondition  
 Autohide takma bölmesinde kayan zaman durması gerektiğini belirler.  
  
```  
virtual BOOL CheckStopSlideCondition(BOOL bDirection);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bDirection`  
 `TRUE`bölmesinde görünür durumdaysa; `FALSE` bölmesinde gizli değilse.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`durdurma koşulu karşılandığında; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Dockable bölmesinde autohide moda ayarlandığında, çerçeve kayan etkileri bölmesini göster veya gizle için kullanır. Bölmesinde kayan zaman çerçevesi bu işlevi çağırır. `CheckStopSlideCondition`döndürür `TRUE` bölmesinde tam olarak görünür olduğunda veya onu tam olarak ne zaman gizlenir.  
  
 Özel autohide efektler uygulamak için bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="copystate"></a>CDockablePane::CopyState  
 Dockable bölme durumunu kopyalar.  
  
```  
virtual void CopyState(CDockablePane* pOrgBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pOrgBar`  
 Bir işaretçi dockable bölmesine.  
  
### <a name="remarks"></a>Açıklamalar  
 `CDockablePane::CopyState`durumu kopyalar `pOrgBar` aşağıdaki yöntemlerden çağırarak geçerli bölmesine:  
  
- [CPane::CopyState](../../mfc/reference/cpane-class.md#copystate)  
  
- [CDockablePane::GetAHRestoredRect](#getahrestoredrect)  
  
- [CDockablePane::GetAHSlideMode](#getahslidemode)  
  
- [CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)  
  
- [CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)  
  
##  <a name="create"></a>CDockablePane::Create  
 Windows Denetim oluşturur ve ona ekler [CDockablePane](../../mfc/reference/cdockablepane-class.md) nesnesi.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE,  
    CCreateContext* pContext = NULL);

 
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    CSize sizeDefault,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle = WS_CHILD|WS_VISIBLE|CBRS_TOP|CBRS_HIDE_INPLACE,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszCaption`  
 Pencere adı belirtir.  
  
 [in] [out]`pParentWnd`  
 Üst pencere belirtir.  
  
 [in]`rect`  
 İstemci koordinatları boyutunu ve pencere konumunu belirtir `pParentWnd`.  
  
 [in]`bHasGripper`  
 `TRUE`bir resim yazısı bölmesi oluşturmak için; Aksi takdirde `FALSE`.  
  
 [in]`nID`  
 Alt pencere Kimliğini belirtir. Bu değer bu takma bölme takma durumunu kaydetmek istiyorsanız, benzersiz olması gerekir.  
  
 [in]`dwStyle`  
 Pencere stili özniteliklerini belirtir.  
  
 [in]`dwTabbedStyle`  
 Kullanıcı bu bölme başlık bir bölme sürüklendiğinde oluşturduğunuz sekmeli bir pencere sekmeli stilini belirtir.  
  
 [in]`dwControlBarStyle`  
 Ek stil özniteliklerini belirtir.  
  
 [in] [out]`pContext`  
 Pencere oluşturma bağlamında belirtir.  
  
 [in]`lpszWindowName`  
 Pencere adı belirtir.  
  
 [in]`sizeDefault`  
 Pencere boyutunu belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`dockable bölmesinde başarıyla oluşturulduysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir Windows bölmesini oluşturur ve ona ekler `CDockablePane` nesnesi.  
  
 Varsa `dwStyle` pencere stili sahip `CBRS_FLOAT_MULTI` miniframe penceresi bayrak float miniframe penceresinde diğer bölmeleri içeren. Varsayılan olarak, bölmeleri yerleştirme yalnızca tek tek float.  
  
 Varsa `dwTabbedStyle` parametresine sahip `AFX_CBRS_OUTLOOK_TABS` bayrağı belirtilmiş, başka bir bölmesini kullanarak bu bölmesinde iliştirildiğinde bölmesinde oluşturur Outlook stili sekmeli bölmeleri [CDockablePane::AttachToTabWnd](#attachtotabwnd) yöntemi. Varsayılan olarak, dockable bölmeleri türü normal sekmeli panolar oluşturma [CTabbedPane](../../mfc/reference/ctabbedpane-class.md).  
  
##  <a name="createdefaultpanedivider"></a>CDockablePane::CreateDefaultPaneDivider  
 Varsayılan bölücüyü bölmesi için bir çerçeve penceresinde yerleşik olduğunda olarak oluşturur.  
  
```  
static CPaneDivider* __stdcall CreateDefaultPaneDivider(
    DWORD dwAlignment,  
    CWnd* pParent,  
    CRuntimeClass* pSliderRTC = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`dwAlignment`  
 Bölmenin yerleştirilmiş olup ana çerçeve tarafında belirtir. Varsa `dwAlignment` içeren `CBRS_ALIGN_LEFT` veya `CBRS_ALIGN_RIGHT` bayrağı, bu yöntem, dikey oluşturur ( `CPaneDivider::SS_VERT`) ayırıcı; Aksi takdirde, bu yöntem yatay oluşturur ( `CPaneDivider::SS_HORZ`) ayırıcı.  
  
 [in]`pParent`  
 Üst çerçeve işaretçisi.  
  
 [in]`pSliderRTC`  
 Kullanılmadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem, yeni oluşturulan ayırıcı için bir işaretçi döndürür veya `NULL` ayırıcı oluşturma başarısız olursa.  
  
### <a name="remarks"></a>Açıklamalar  
 `dwAlignment`Aşağıdaki değerlerden biri olabilir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|Bölmesinde bir çerçeve penceresinde istemci alanının üst kısmına yerleştirilir.|  
|`CBRS_ALIGN_BOTTOM`|Bölmesinde bir çerçeve penceresinde istemci alanını alt kısmına yerleştirilir.|  
|`CBRS_ALIGN_LEFT`|Bölmesinde bir çerçeve penceresinde istemci alanını sol tarafına yerleştirilir.|  
|`CBRS_ALIGN_RIGHT`|Bölmesinde bir çerçeve penceresinde istemci sayfasının sağ tarafında yerleştirilir.|  
  
##  <a name="createex"></a>CDockablePane::CreateEx  
 Windows Denetim oluşturur ve ona ekler [CDockablePane](../../mfc/reference/cdockablepane-class.md) nesnesi.  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`dwStyleEx`  
 Yeni pencere için genişletilmiş stili özniteliklerini belirtir.  
  
 [in]`lpszCaption`  
 Pencere adı belirtir.  
  
 [in] [out]`pParentWnd`  
 Üst pencere belirtir.  
  
 [in]`rect`  
 İstemci koordinatları boyutunu ve pencere konumunu belirtir `pParentWnd`.  
  
 [in]`bHasGripper`  
 `TRUE`bir resim yazısı bölmesi oluşturmak için; Aksi takdirde `FALSE`.  
  
 [in]`nID`  
 Alt pencere Kimliğini belirtir. Bu değer bu takma bölme takma durumunu kaydetmek istiyorsanız, benzersiz olması gerekir.  
  
 [in]`dwStyle`  
 Pencere stili özniteliklerini belirtir.  
  
 [in]`dwTabbedStyle`  
 Kullanıcı bu bölme başlık bir bölme sürüklendiğinde oluşturduğunuz sekmeli bir pencere sekmeli stilini belirtir.  
  
 [in]`dwControlBarStyle`  
 Ek stil özniteliklerini belirtir.  
  
 [in] [out]`pContext`  
 Pencere oluşturma bağlamında belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`dockable bölmesinde başarıyla oluşturulduysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir Windows bölmesini oluşturur ve ona ekler `CDockablePane` nesnesi.  
  
 Varsa `dwStyle` pencere stili sahip `CBRS_FLOAT_MULTI` miniframe penceresi bayrak float miniframe penceresinde diğer bölmeleri içeren. Varsayılan olarak, bölmeleri yerleştirme yalnızca tek tek float.  
  
 Varsa `dwTabbedStyle` parametresine sahip `AFX_CBRS_OUTLOOK_TABS` bayrağı belirtilmiş, başka bir bölmesini kullanarak bu bölmesinde iliştirildiğinde bölmesinde oluşturur Outlook stili sekmeli bölmeleri [CDockablePane::AttachToTabWnd](#attachtotabwnd) yöntemi. Varsayılan olarak, dockable bölmeleri türü normal sekmeli panolar oluşturma [CTabbedPane](../../mfc/reference/ctabbedpane-class.md).  
  
##  <a name="createtabbedpane"></a>CDockablePane::CreateTabbedPane  
 Sekmeli bölmesinde geçerli bölmesinden oluşturur.  
  
```  
virtual CTabbedPane* CreateTabbedPane();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni sekmeli bölmesi veya `NULL` oluşturma işlemi başarısız olursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bölme değiştirmek için bir sekmeli bölmesi oluşturduğunda framework bu yöntemi çağırır. Daha fazla bilgi için bkz: [CDockablePane::AttachToTabWnd](#attachtotabwnd).  
  
 Bu yöntem nasıl sekmeli bölmeleri özelleştirmek için bir türetilmiş sınıfta oluşturuldu ve başlatıldı geçersiz kılma.  
  
 Sekmeli bölmesinde depolanan çalışma zamanı sınıf bilgileri göre oluşturulan `m_pTabbedControlBarRTC` tarafından başlatılan üye [CDockablePane::CreateEx](#createex) yöntemi.  
  
##  <a name="dockpanecontainer"></a>CDockablePane::DockPaneContainer  
 Bir kapsayıcı bölmesine docks.  
  
```  
virtual BOOL DockPaneContainer(
    CPaneContainerManager& barContainerManager,  
    DWORD dwAlignment,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`barContainerManager`  
 Yerleşik olduğunda kapsayıcısının kapsayıcı Yöneticisi referansı.  
  
 [in]`dwAlignment`  
 `DWORD`kapsayıcı yerleşik olduğunda bölmesinin tarafına belirtir.  
  
 [in]`dockMethod`  
 Kullanılmadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`kapsayıcı, başarılı bir şekilde bölmesine; yerleşik varsa Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 `dwAlignment`Aşağıdaki değerlerden biri olabilir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|Kapsayıcı bölmesinde üst kısmına yerleştirilir.|  
|`CBRS_ALIGN_BOTTOM`|Kapsayıcı bölmesinde alt kısmına yerleştirilir.|  
|`CBRS_ALIGN_LEFT`|Kapsayıcı bölmesinin sola yerleştirilir.|  
|`CBRS_ALIGN_RIGHT`|Kapsayıcı bölmesinde sağına yerleştirilir.|  
  
##  <a name="dockpanestandard"></a>CDockablePane::DockPaneStandard  
 Bir bölme anahat (standart) yerleştirme kullanarak docks.  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bWasDocked`  
 Yöntem döndüğünde, bu değeri içeren `TRUE` bölmesinde varsa başarıyla yerleşik; Aksi takdirde, içerdiği `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesi sekmeli pencere yuvalanmış ya da sekmeli bir pencere yerleştirme sonucunda oluşturduysanız, bu yöntem bir işaretçi sekmeli penceresine döndürür. Bölmesinde başarıyla yerleşik aksi varsa, bu yöntem `this` işaretçi. Yerleştirme başarısız olduysa, bu yöntem `NULL`.  
  
##  <a name="docktorecentpos"></a>CDockablePane::DockToRecentPos  
 Bir bölme saklı yerleştirme konumuna docks.  
  
```  
BOOL CDockablePane::DockToRecentPos();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bölmesinde başarıyla yerleştirilmişse; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Dockable bölmeleri içinde son takma bilgilerini depolayan bir [CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md) nesnesi.  
  
##  <a name="docktowindow"></a>CDockablePane::DockToWindow  
 Başka bir takma bölmesine bir takma bölme noktalarını.  
  
```  
virtual BOOL DockToWindow(
    CDockablePane* pTargetWindow,  
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out]`pTargetWindow`  
 Bu bölme sabitlemek için dockable bölmesinde belirtir.  
  
 [in]`dwAlignment`  
 Bölmenin yerleştirme hizalamasını belirtir. CBRS_ALIGN_LEFT CBRS_ALIGN_TOP, CBRS_ALIGN_RIGHT CBRS_ALIGN_BOTTOM veya cbrs_alıgn_any biri olabilir. (Afxres.h içinde tanımlanmıştır.)  
  
 [in]`lpRect`  
 Bölmenin yerleştirme dikdörtgen belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bölmesi başarıyla; yuvalanmış varsa Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme tarafından belirtilen hizalama ile başka bir bölüme yerleştirme için bu yöntemi çağırın `dwAlignment`.  
  
##  <a name="drawcaption"></a>CDockablePane::DrawCaption  
 (Kavrayıcının olarak da bilinir) başlık yerleştirme bölmesinin çizer.  
  
```  
virtual void DrawCaption(
    CDC* pDC,  
    CRect rectCaption);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Çizim için kullanılan cihaz bağlamı temsil eder.  
  
 [in]`rectCaption`  
 Bölmesi'nin başlığı sınırlayıcı dikdörtgenini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework dockable bölmesinde resim yazısını çizmek için bu yöntemi çağırır.  
  
 Resim yazısını görünümünü özelleştirmek için bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="enableautohideall"></a>CDockablePane::EnableAutohideAll  
 Etkinleştirir veya diğer bölmeleri kapsayıcısındaki ve bu bölme için otomatik olarak Gizle modunu devre dışı bırakır.  
  
```  
void EnableAutohideAll(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
 `TRUE`autohide dockable bölmesinin tüm özelliğini etkinleştirmek için; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcının ne zaman tutan `Ctrl` anahtarı ve bir bölme autohide modu, diğer tüm bölmelerde aynı kapsayıcı geçmek için PIN düğmesi de autohide moduna geçiş tıklar.  
  
 Bu yöntem çağrısı `bEnable` kümesine `FALSE` belirli bölmesi için bu özelliği devre dışı.  
  
##  <a name="enablegripper"></a>CDockablePane::EnableGripper  
 Gösterir veya gizler (kavrayıcının olarak da bilinir) açıklamalı alt yazı.  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
 `TRUE`Resim yazısını etkinleştirmek için; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework dockable bölmeleri oluşturduğunda, bunlar olmadığı **WS_STYLE** belirtilen olsa bile pencere stili. Bu Bölmesi'nin başlık çerçevesi tarafından denetlenen bir istemci dışı alan olduğunu, ancak bu alan standart pencere resim yazısı farklı anlamına gelir.  
  
 Gösterebilir veya herhangi bir zamanda resim yazısını gizleyebilirsiniz. Bir bölme bir sekme sekmeli bir pencere için veya bir bölme miniframe penceresinde yüzdürülen eklendiğinde framework resim yazısını gizler.  
  
##  <a name="getahrestoredrect"></a>CDockablePane::GetAHRestoredRect  
 Otomatik olarak gizle modundayken bölmesinde konumunu belirtir.  
  
```  
CRect GetAHRestoredRect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CRect` otomatik olarak gizle modunda olduğunda bölmesinde konumunu içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getahslidemode"></a>CDockablePane::GetAHSlideMode  
 Bölme için otomatik olarak gizle slayt modunu alır.  
  
```  
virtual UINT GetAHSlideMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `UINT` bölmesinde otomatik olarak gizle slayt modunu belirtir. Dönüş değeri olabilir `AFX_AHSM_MOVE` veya `AFX_AHSM_STRETCH`, ancak uygulama yalnızca kullanır `AFX_AHSM_MOVE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcaptionheight"></a>CDockablePane::GetCaptionHeight  
 Geçerli resim yazısı piksel cinsinden yüksekliği döndürür.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Resim yazısını piksel cinsinden yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Resim yazısı yükseklik resim yazısını tarafından gizlenmiş 0 ise [CDockablePane::EnableGripper](#enablegripper) yöntemini veya bölmesinde bir resim yazısı yoksa.  
  
##  <a name="getdefaultpanedivider"></a>CDockablePane::GetDefaultPaneDivider  
 Bölmesinde ait kapsayıcı için varsayılan bölmesinde ayırıcı döndürür.  
  
```  
CPaneDivider* GetDefaultPaneDivider() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir [CPaneDivider](../../mfc/reference/cpanedivider-class.md) dockable bölmesi ana çerçeve penceresine yerleştirilmişse nesne veya `NULL` dockable bölmesinde yerleştirilmemişse veya onu kayan.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmesinde Bölücü hakkında daha fazla bilgi için bkz: [CPaneDivider sınıfı](../../mfc/reference/cpanedivider-class.md).  
  
##  <a name="getdockingstatus"></a>CDockablePane::GetDockingStatus  
 Bir bölme yerleşik yeteneğini sağlanan işaretçi konum temelinde belirler.  
  
```  
virtual AFX_CS_STATUS GetDockingStatus(
    CPoint pt,  
    int nSensitivity);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pt`  
 Ekran koordinatları işaretçinin konumu.  
  
 [in]`nSensitivity`  
 Piksel cinsinden uzaklığı dikdörtgen kenar çıktığınızda, yerleştirme etkinleştirmek için işaretçiyi olması gerekir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki durum değerlerden biri:  
  
|`AFX_CS_STATUS`değer|Açıklama|  
|---------------------------|-------------|  
|`CS_NOTHING`|İşaretçinin yerleştirme site değil. Framework bölmesinde yerleştirme değil.|  
|`CS_DOCK_IMMEDIATELY`|İşaretçinin anlık modda yerleştirme site bulunur (bölmesinde kullanan `DT_IMMEDIATE` yerleştirme modu). Framework bölmesinde hemen docks.|  
|`CS_DELAY_DOCK`|Başka bir takma bölmesi olan veya bir ana çerçeve kenarı bir yerleştirme sitesi işaretçidir. Framework bölmesinde bir gecikmeden sonra docks. Bu gecikme hakkında daha fazla bilgi için Açıklamalar bölümüne bakın.|  
|`CS_DELAY_DOCK_TO_TAB`|İşaretçinin sekmeli penceresinde yerleşik için bölmesinde neden olan bir yerleştirme sitesi üzerinde yer alır. Bu durum, başka bir takma bölmesinde resim yazısını veya sekmeli bölmesinin sekme alanı üzerinden işaretçinin bulunduğu oluşur.|  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve bir kayan bölmesinde yerleştirme işlemek için bu yöntemi çağırır.  
  
 Kayan araç çubukları veya kullanmak bölmeleri yerleştirme `DT_IMMEDIATE` modu yerleştirme, framework yerleştirme oluşmadan önce pencereyi üst çerçeve istemci alanı dışına taşımak kullanıcı etkinleştirmek için yerleştirme komutu geciktirir. Bekleme süresini milisaniye olarak ölçülür ve tarafından denetlenen [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) veri üyesi... Varsayılan değer olan [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) 200'dür. Bu davranış yerleştirme davranışını taklit eden [!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)] 2007.  
  
 Durumları yerleştirme Gecikmeli için ( `CS_DELAY_DOCK` ve `CS_DELAY_DOCK_TO_TAB`), kullanıcının fare düğmesini serbest kadar yerleştirme framework gerçekleştirmez. Bir bölme kullanıyorsa `DT_STANDARD` modu yerleştirme, framework dikdörtgen tahmini takma konumda görüntüler. Bir bölme kullanıyorsa `DT_SMART` modu yerleştirme, framework akıllı yerleştirme işaretçileri ve yarı saydam dikdörtgenler tahmini takma konumda görüntüler. Bölmenin yerleştirme modunu belirtmek için arama [CBasePane::SetDockingMode](../../mfc/reference/cbasepane-class.md#setdockingmode) yöntemi. Akıllı yerleştirme hakkında daha fazla bilgi için bkz: [CDockingManager::GetSmartDockingParams](../../mfc/reference/cdockingmanager-class.md#getsmartdockingparams).  
  
##  <a name="getdragsensitivity"></a>CDockablePane::GetDragSensitivity  
 Yerleştirme bölmesine sürükleyin duyarlılığını döndürür.  
  
```  
static const CSize& GetDragSensitivity();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) genişlik ve yükseklik piksel cinsinden bir Sürükle noktasında ortalanmış dikdörtgeni içeren nesne. Fare işaretçisi bu dikdörtgenin dışında hareket kadar sürükleme işlemi başlamaz.  
  
##  <a name="getlastpercentinpanecontainer"></a>CDockablePane::GetLastPercentInPaneContainer  
 Bir bölme kapsayıcısının içinde kapladığı alanı yüzdesini alır ( [CPaneContainer sınıfı](../../mfc/reference/cpanecontainer-class.md)).  
  
```  
int GetLastPercentInPaneContainer() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `int` kapsayıcısı içinde bölmesinin kapladığı alanı yüzdesini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, kapsayıcı düzenini ayarlar kullanılır.  
  
##  <a name="gettabarea"></a>CDockablePane::GetTabArea  
 Bölmesinde sekme alanı alır.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rectTabAreaTop`  
 `GetTabArea`Bu değişken sekmeleri bölmenin en üstünde bulunan sekme alanı ile doldurur. Sekmeleri bölmesinin altında bulunuyorsa, bu değişken boş bir dikdörtgen ile doldurulur.  
  
 [in]`rectTabAreaBottom`  
 `GetTabArea`Bu değişken sekmeleri bölmesinin altında bulunan sekme alanı ile doldurur. Bölmenin en üstünde sekmeleri bulunuyorsa, bu değişken boş bir dikdörtgen ile doldurulur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca türetilmiş sınıflardaki kullanılır `CDockablePane` ve sekmeler bulunmaz. Daha fazla bilgi için bkz: [CTabbedPane::GetTabArea](../../mfc/reference/ctabbedpane-class.md#gettabarea) ve [CMFCOutlookBar::GetTabArea](../../mfc/reference/cmfcoutlookbar-class.md#gettabarea).  
  
##  <a name="gettabbedpanertc"></a>CDockablePane::GetTabbedPaneRTC  
 Başka bir bölme geçerli bölmesine noktalarını kaydedildiğinde sekmeli bir pencere ilgili çalışma zamanı sınıf bilgileri döndürür.  
  
```  
CRuntimeClass* GetTabbedPaneRTC() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çalışma zamanı sınıf bilgileri dockable bölmesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Dinamik olarak oluşturulan sekmeli bölmeleri için çalışma zamanı sınıf bilgileri almak için bu yöntemi çağırın. Bu kullanıcı başka bir bölme resim yazısı için bir bölme sürüklendiğinde veya çağırırsanız oluşabilir [CDockablePane::AttachToTabWnd](#attachtotabwnd) program aracılığıyla iki dockable bölmeleri sekmeli bir bölme oluşturmak için yöntemi.  
  
 Çalışma zamanı sınıf bilgileri çağırarak ayarlayabileceğiniz [CDockablePane::SetTabbedPaneRTC](#settabbedpanertc) yöntemi.  
  
##  <a name="hasautohidemode"></a>CDockablePane::HasAutoHideMode  
 Yerleştirme bölmesinde autohide moduna geçiş olup olmadığını belirtir.  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`dockable bölmesinde autohide moduna Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli bir dockable bölmesi autohide modunu devre dışı bırakmak için bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="hittest"></a>CDockablePane::HitTest  
 Burada kullanıcının bir fare tıklamaları bölmesinde konumu belirtir.  
  
```  
virtual int HitTest(
    CPoint point,  
    BOOL bDetectCaption = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`point`  
 Test etmek için noktasını belirtir.  
  
 [in]`bDetectCaption`  
 `TRUE`varsa `HTCAPTION` noktası Bölmesi'nin resim yazısını; olup olmadığını döndürülmelidir Aksi halde, `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden biri:  
  
- `HTNOWHERE`varsa `point` dockable bölmesinde değil.  
  
- `HTCLIENT`varsa `point` dockable bölmesinde istemci alanındadır.  
  
- `HTCAPTION`varsa `point` dockable bölmesinde resim yazısı alanındadır.  
  
- `AFX_HTCLOSE`varsa `point` Kapat düğmesine değil.  
  
- `HTMAXBUTTON`varsa `point` PIN düğme.  
  
##  <a name="isautohideallenabled"></a>CDockablePane::IsAutohideAllEnabled  
 Yerleştirme bölmesinde ve tüm kapsayıcı bölmelerinde autohide moduna değiştirilebilir olup olmadığını gösterir.  
  
```  
virtual BOOL IsAutohideAllEnabled() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`dockable bölmesinde ve tüm kapsayıcı bölmelerinde autohide moduna Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı tutarken takma PIN düğmesine tıklayarak autohide modunu etkinleştirir **Ctrl** anahtarı  
  
 Etkinleştirmek veya bu davranışı devre dışı bırakmak için arama [CDockablePane::EnableAutohideAll](#enableautohideall) yöntemi.  
  
##  <a name="isautohidemode"></a>CDockablePane::IsAutoHideMode  
 Bir bölme autohide modunda olup olmadığını belirler.  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`dockable bölmesinde autohide modundaysa; Aksi takdirde `FALSE`.  
  
##  <a name="isdocked"></a>CDockablePane::IsDocked  
 Geçerli bölmesini yerleştirilmiş olup olmadığını belirler.  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`dockable bölmesinde bir miniframe pencereye ait değil veya başka bir bölmesiyle miniframe penceresinde kayan. `FALSE`miniframe pencerenin alt öğesi bölmesidir ve miniframe pencereye ait herhangi bir bölmeleri varsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Ana çerçeve penceresi bölmenin yerleştirilmiş olup olmadığını belirlemek için arama [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider). Yöntemi bir NULL olmayan işaretçi döndürürse, bölmesi ana çerçeve penceresinde yerleştirilir.  
  
##  <a name="ishideinautohidemode"></a>CDockablePane::IsHideInAutoHideMode  
 Autohide modunda, gösterilen (gizli çağırarak veya varsa) olan bir bölme davranışını belirler [CDockablePane::ShowPane](#showpane).  
  
```  
virtual BOOL IsHideInAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`autohide modundayken; dockable bölmesinde gizli Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Dockable bölmesinde autohide modundayken farklı çağırdığınızda davranır `ShowPane` bölmesinde göstermek veya gizlemek için. Bu davranış statik üyesi tarafından denetlenen [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode). Bu üye ise `TRUE`, dockable bölmesi ve ilgili autohide araç veya autohide düğmesi gizli veya çağırdığınızda gösterilen `ShowPane`. Aksi takdirde dockable bölmesi etkinleştirilmiş veya devre dışı ve her zaman kendi ilgili autohide araç veya autohide düğmesi görülebilir.  
  
 Tek tek bölmeleri varsayılan davranışı değiştirmek için bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
 İçin varsayılan değer `m_bHideInAutoHideMode` olan `FALSE`.  
  
##  <a name="isinfloatingmultipaneframewnd"></a>CDockablePane::IsInFloatingMultiPaneFrameWnd  
 Bölmesinde çok bölmesi çerçeve penceresinde olup olmadığını belirtir ( [CMultiPaneFrameWnd sınıfı](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bir çok bölmesi çerçeve penceresinde bölmesidir Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isresizable"></a>CDockablePane::IsResizable  
 Bölmesinde yeniden boyutlandırılabilir olup olmadığını belirtir.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yeniden boyutlandırılabilir bölmesidir Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, dockable bölmeleri yeniden boyutlandırılabilir. Yeniden boyutlandırma önlemek için türetilmiş bir sınıf bu yöntemi geçersiz kılın ve dönüş `FALSE`. Unutmayın bir `FALSE` değeri müşteri adayları başarısız bir `ASSERT` içinde [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane). Kullanım [CDockingManager::AddPane](../../mfc/reference/cdockingmanager-class.md#addpane) bunun yerine bir bölme bir üst çerçevesinde sabitlemek için.  
  
 Yeniden boyutlandırılamıyor bölmeleri ne yapabilirsiniz float ya da otomatik olarak gizle moduna ve her zaman üst çerçeve dış ucunun bulunur.  
  
##  <a name="istablocationbottom"></a>CDockablePane::IsTabLocationBottom  
 Sekmeleri üstüne veya altına bölmesinin bulunduğu olup olmadığını belirtir.  
  
```  
virtual BOOL IsTabLocationBottom() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`sekmeleri bölmesinin altında bulunur `FALSE` sekmeleri bölmenin en üstünde bulunan.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [CTabbedPane::IsTabLocationBottom](../../mfc/reference/ctabbedpane-class.md#istablocationbottom).  
  
##  <a name="istracked"></a>CDockablePane::IsTracked  
 Bir kullanıcı tarafından taşınan olup olmadığını belirtir.  
  
```  
BOOL IsTracked() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bölmesinde taşınır Aksi takdirde `FALSE`.  
  
##  <a name="isvisible"></a>CDockablePane::IsVisible  
 Geçerli bölmesinde görünür olup olmadığını belirler.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`dockable bölmesinde görünür durumdaysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Dockable bölmesinde görünür olup olmadığını belirlemek için bu yöntemi çağırın. Bu yöntemi çağırmak yerine kullanabileceğiniz [CWnd::IsWindowVisible](../../mfc/reference/cwnd-class.md#iswindowvisible) veya sınama `WS_VISIBLE` stili. Autohide modu etkin veya devre dışı olduğunu ve değerini döndürülen görünürlük durumu bağlıdır [CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode) özelliği.  
  
 Dockable bölmesinde autohide modundaysa ve `IsHideInAutoHideMode` döndürür `FALSE` görünürlük durumu her zaman olduğu `FALSE`.  
  
 Dockable bölmesinde autohide modundaysa ve `IsHideInAutoHideMode` döndürür `TRUE` görünürlük durumu ilgili autohide araç çubuğunun görünürlüğünü durumuna bağlıdır.  
  
 Dockable bölmesi autohide modunda değilse görünürlük durumu tarafından belirlenir [CBasePane::IsVisible](../../mfc/reference/cbasepane-class.md#isvisible) yöntemi.  
  
##  <a name="m_bdisableanimation"></a>CDockablePane::m_bDisableAnimation  
 AutoHide animasyon dockable bölmesinin etkinleştirilip etkinleştirilmeyeceğini belirtir.  
  
```  
AFX_IMPORT_DATA static BOOL m_bDisableAnimation;  
```  
  
##  <a name="m_bhideinautohidemode"></a>CDockablePane::m_bHideInAutoHideMode  
 Bölmesinde autohide modundayken bölmesinde davranışını belirler.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideInAutoHideMode;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer, uygulamadaki tüm takma bölmeleri etkiler.  
  
 Bu üye ayarlarsanız `TRUE`, gizli ya da kendi ilgili autohide araç çubukları ve düğmeleri çağırdığınızda gösterilen dockable bölmeleri [CDockablePane::ShowPane](#showpane).  
  
 Bu üye ayarlarsanız `FALSE`, dockable bölmeleri etkin veya çağırdığınızda devre dışı [CDockablePane::ShowPane](#showpane).  
  
##  <a name="m_nslidesteps"></a>CDockablePane::m_nSlideSteps  
 Autohide modunda olduğunda bölmesinin animasyon hızı belirtir.  
  
```  
AFX_IMPORT_DATA static int m_nSlideSteps;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha hızlı bir animasyon efekti bu değerini azaltın. Yavaş bir animasyon efekti bu değerini artırın.  
  
##  <a name="onafterchangeparent"></a>CDockablePane::OnAfterChangeParent  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWndOldParent`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onafterdockfromminiframe"></a>CDockablePane::OnAfterDockFromMiniFrame  
 Kayan bir takma çubuğu bir çerçeve penceresinde noktalarını çerçevesi tarafından çağrılır.  
  
```  
virtual void OnAfterDockFromMiniFrame();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem hiçbir şey yapmaz.  
  
##  <a name="onbeforechangeparent"></a>CDockablePane::OnBeforeChangeParent  
 Framework bölmesinin üst değiştirmeden önce bu yöntemi çağırır.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWndNewParent`  
 Yeni üst pencere için bir işaretçi.  
  
 [in]`bDelay`  
 `BOOL`bölmesinde kilitli ise yerleştirme düzenini yeniden hesaplanması gecikme görüntülenmeyeceğini belirtir. Daha fazla bilgi için bkz: [CDockablePane::UndockPane](#undockpane).  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmenin yerleştirilmiş ve yeni üst yerleştirme izin vermez, bu yöntem bölmesinde çıkarabilirsiniz.  
  
 Sekmeli belge bölmesinde dönüştürülecek, bu yöntem son yerleştirme konumunu depolar. Çerçeve, yerleşik bir duruma geri dönüştürüldüğünde bölmesinde konumunu geri yüklemek için son yerleştirme konumunu kullanır.  
  
##  <a name="onbeforefloat"></a>CDockablePane::OnBeforeFloat  
 Framework kayan durumuna geçişleri bölme önce bu yöntemi çağırır.  
  
```  
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rectFloat`  
 Kayan bir durumda olduğunda bölmesinin boyutunu ve konumunu belirtir.  
  
 [in]`dockMethod`  
 Takma yöntemini belirtir. Bkz: [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) olası değerler listesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bölmesinde kaydırılmış Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayana bölme hakkında olduğunda bu yöntem çerçevesi tarafından çağrılır. Bölmesinde gezinen önce herhangi bir işlem gerçekleştirmek istiyorsanız bir türetilmiş sınıfta bu yöntemin üzerine yazabilir.  
  
##  <a name="onpressbuttons"></a>CDockablePane::OnPressButtons  
 Kullanıcının bir resim yazısı düğmesine dışında bastığında adlı `AFX_HTCLOSE` ve `AFX_HTMAXBUTTON` düğmeler.  
  
```  
virtual void OnPressButtons(UINT nHit);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nHit`  
 Bu parametre kullanılmaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel bir düğme dockable bölmesinde resim yazısı eklerseniz, bir kullanıcı düğmesine bastığında bildirimleri almak için bu yöntemi geçersiz kılın.  
  
##  <a name="onslide"></a>CDockablePane::OnSlide  
 Autohide modunda olduğunda bölmesinde animasyon çerçevesi tarafından çağrılır.  
  
```  
virtual void OnSlide(BOOL bSlideOut);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bSlideOut`  
 `TRUE`bölmesini göstermek için; `FALSE` bölmesini gizlemek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel autohide efektler uygulamak için bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="removefromdefaultpanedividier"></a>CDockablePane::RemoveFromDefaultPaneDividier  
 Bir bölme takılı olduğunda framework bu yöntemi çağırır.  
  
```  
void RemoveFromDefaultPaneDividier();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem varsayılan bölmesinde ayırıcı ayarlar `NULL` ve kendi kapsayıcıdan bölmesinde kaldırır.  
  
##  <a name="replacepane"></a>CDockablePane::ReplacePane  
 Bölmesinde belirtilen bölmesiyle değiştirir.  
  
```  
BOOL ReplacePane(
    CDockablePane* pBarToReplaceWith,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bRegisterWithFrame = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBarToReplaceWith`  
 Bir işaretçi dockable bölmesine.  
  
 [in]`dockMethod`  
 Kullanılmadı.  
  
 [in]`bRegisterWithFrame`  
 Varsa `TRUE`, yeni bölmesi eski bölmesinin üst takma Yöneticisi ile kayıtlı değil. Yeni bölmesi takma Yöneticisi tarafından tutulan bölmeleri listesinde eski bölmesinin dizinindeki eklenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`değiştirme başarılı olduğunda; Aksi takdirde `FALSE`.  
  
##  <a name="restoredefaultpanedivider"></a>CDockablePane::RestoreDefaultPaneDivider  
 Bir bölme serisi, framework varsayılan bölmesinde ayırıcı geri yüklemek için bu yöntemi çağırır.  
  
```  
void RestoreDefaultPaneDivider();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Geri yüklenen varsayılan bölmesinde ayırıcı varsa geçerli varsayılan bölmesinde ayırıcı yerini alır.  
  
##  <a name="setautohidemode"></a>CDockablePane::SetAutoHideMode  
 Yerleştirme bölmesinde görünür arasında geçiş yapar ve autohide modu.  
  
```  
virtual CMFCAutoHideBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bMode`  
 `TRUE`AutoHide modunu etkinleştirmek için; `FALSE` normal takma modunu etkinleştirmek için.  
  
 [in]`dwAlignment`  
 Oluşturmak için autohide bölmenin hizalamasını belirtir.  
  
 [in] [out]`pCurrAutoHideBar`  
 Geçerli autohide araç için bir işaretçi. Olabilir `NULL`.  
  
 [in]`bUseTimer`  
 Kullanıcı bölmesinde autohide moduna geçirildiğinde autohide etkisi kullanmak mı, yoksa bölmesini hemen gizlemek için belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Autohide moduna geçiş sonucu olarak oluşturulan otomatik olarak gizle araç çubuğunu veya `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı dockable bölmesinde autohide modu veya normal takma moduna geçiş için PIN düğmesine tıkladığında framework bu yöntemi çağırır.  
  
 Program aracılığıyla dockable bölmesinde autohide moduna geçmek için bu yöntemi çağırın. Bölmesi ana çerçeve penceresi yuvalanmış gerekir ( [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider) için geçerli bir işaretçi döndürmelidir [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).  
  
##  <a name="setautohideparents"></a>CDockablePane::SetAutoHideParents  
 Otomatik olarak gizle düğmesi ve otomatik olarak gizle araç bölmesini için ayarlar.  
  
```  
void SetAutoHideParents(
    CMFCAutoHideBar* pToolBar,  
    CMFCAutoHideButton* pBtn);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pToolBar`  
 Bir otomatik olarak gizle araç çubuğunu işaretçi.  
  
 [in]`pBtn`  
 Bir otomatik olarak gizle düğmesi işaretçi.  
  
##  <a name="setlastpercentinpanecontainer"></a>CDockablePane::SetLastPercentInPaneContainer  
 Bir bölme kapsayıcısının içinde kapladığı alanı yüzdesi ayarlar.  
  
```  
void SetLastPercentInPaneContainer(int n);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`n`  
 Bir `int` kapsayıcısı içinde bölmesinin kapladığı alanı yüzdesini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework düzeni hesaplandığında yeni değer kullanması için bölmesinde ayarlar.  
  
##  <a name="setrestoreddefaultpanedivider"></a>CDockablePane::SetRestoredDefaultPaneDivider  
 Geri yüklenen varsayılan bölmesinde ayırıcı ayarlar.  
  
```  
void SetRestoredDefaultPaneDivider(HWND hRestoredSlider);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`hRestoredSlider`  
 Bölmesinde ayırıcı (kaydırıcı) için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme serisi, geri yüklenen varsayılan bölmesinde ayırıcı elde edilir. Daha fazla bilgi için bkz: [CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider).  
  
##  <a name="settabbedpanertc"></a>CDockablePane::SetTabbedPaneRTC  
 İki bölme birlikte yerleştirme kaydedildiğinde sekmeli bir pencere için çalışma zamanı sınıf bilgileri ayarlar.  
  
```  
void SetTabbedPaneRTC(CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pRTC`  
 Sekmeli bölmesi için çalışma zamanı sınıf bilgileri.  
  
### <a name="remarks"></a>Açıklamalar  
 Dinamik olarak oluşturulan sekmeli bölmeleri için çalışma zamanı sınıf bilgileri ayarlamak için bu yöntemi çağırın. Bu kullanıcı başka bir bölme resim yazısı için bir bölme sürüklendiğinde veya çağırırsanız oluşabilir [CDockablePane::AttachToTabWnd](#attachtotabwnd) program aracılığıyla iki dockable bölmeleri sekmeli bir bölme oluşturmak için yöntemi.  
  
 Varsayılan çalışma zamanı sınıf göre ayarlanır `dwTabbedStyle` parametresinin [CDockablePane::Create](#create) ve [CDockablePane::CreateEx](#createex). Yeni sekmeli bölmeleri özelleştirmek için aşağıdaki sınıflar birinden, sınıf türetin:  
  
- [CBaseTabbedPane sınıfı](../../mfc/reference/cbasetabbedpane-class.md)  
  
- [CTabbedPane sınıfı](../../mfc/reference/ctabbedpane-class.md)  
  
- [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Ardından, kendi çalışma zamanı sınıf bilgileri işaretçisine ile bu yöntemi çağırın.  
  
##  <a name="showpane"></a>CDockablePane::ShowPane  
 Gösterir veya gizler bir bölme.  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bShow`  
 `TRUE`bölmesini göstermek için; `FALSE` bölmesini gizlemek için.  
  
 [in]`bDelay`  
 `TRUE`Yerleştirme düzenini ayarlama geciktirmek için; `FALSE` yerleştirme düzeni hemen ayarlamak için.  
  
 [in]`bActivate`  
 `TRUE`gösterilen bölmesinde etkinleştirmek için; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerine bu yöntemi çağırabilmeniz [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) gösterirken veya dockable bölmelerini gizleme.  
  
##  <a name="slide"></a>CDockablePane::Slide  
 Autohide modunda bir bölme canlandırır.  
  
```  
virtual void Slide(
    BOOL bSlideOut,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bSlideOut`  
 `TRUE`bölmesini göstermek için; `FALSE` bölmesini gizlemek için.  
  
 [in]`bUseTimer`  
 `TRUE`autohide etkisi olmadan bölmesini göster veya gizle için; `FALSE` göstermek veya bölmesinde hemen gizlemek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework autohide modunda bir bölme animasyon uygulamak için bu yöntemi çağırır.  
  
 Bu yöntem `CDockablePane::m_nSlideDefaultTimeOut` slayt etkisi için zaman aşımını belirlemek için değeri. Zaman aşımı için varsayılan değer 1'dir. Autohide algoritması özelleştirirseniz, zaman aşımı değiştirmek için bu üye değiştirin.  
  
##  <a name="toggleautohide"></a>CDockablePane::ToggleAutoHide  
 Her zaman arasında bölmesinde görünür ve otomatik olarak gizle modu arasında geçiş yapar.  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağrılarak bölme için otomatik olarak gizle modu arasında geçiş yapar [CDockablePane::SetAutoHideMode](#setautohidemode).  
  
##  <a name="undockpane"></a>CDockablePane::UndockPane  
 Ana çerçeve penceresi veya miniframe pencere kapsayıcı bölmesinden çıkarabilirsiniz.  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bDelay`  
 `TRUE`yerleştirme düzeni hesaplama geciktirmek için; `FALSE` yerleştirme düzeni hemen yeniden hesaplamak için.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme ana çerçeve penceresinden veya çoklu miniframe pencere kapsayıcı (diğer bölmeleri içeren bir tek miniframe penceresinde kayan bölme) çıkarmak için bu yöntemi çağırın.  
  
 Tarafından gerçekleştirilen olmayan herhangi bir dış işlemi gerçekleştirmeden önce bir bölme yuvadan [CDockingManager](../../mfc/reference/cdockingmanager-class.md). Örneğin, bir bölme taşımak için program aracılığıyla bir konumdan diğerine yuvadan gerekir.  
  
 Bunlar yok önce framework bölmeleri otomatik olarak çıkarabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CPane sınıfı](../../mfc/reference/cpane-class.md)
