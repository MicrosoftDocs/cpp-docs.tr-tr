---
title: "CMFCTabCtrl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabCtrl
- AFXTABCTRL/CMFCTabCtrl
- AFXTABCTRL/CMFCTabCtrl::ActivateMDITab
- AFXTABCTRL/CMFCTabCtrl::AllowDestroyEmptyTabbedPane
- AFXTABCTRL/CMFCTabCtrl::AutoSizeWindow
- AFXTABCTRL/CMFCTabCtrl::CalcRectEdit
- AFXTABCTRL/CMFCTabCtrl::Create
- AFXTABCTRL/CMFCTabCtrl::EnableActiveTabCloseButton
- AFXTABCTRL/CMFCTabCtrl::EnableInPlaceEdit
- AFXTABCTRL/CMFCTabCtrl::EnableTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::EnsureVisible
- AFXTABCTRL/CMFCTabCtrl::GetDocumentIcon
- AFXTABCTRL/CMFCTabCtrl::GetFirstVisibleTabNum
- AFXTABCTRL/CMFCTabCtrl::GetResizeMode
- AFXTABCTRL/CMFCTabCtrl::GetScrollBar
- AFXTABCTRL/CMFCTabCtrl::GetTabArea
- AFXTABCTRL/CMFCTabCtrl::GetTabMaxWidth
- AFXTABCTRL/CMFCTabCtrl::GetTabsHeight
- AFXTABCTRL/CMFCTabCtrl::GetTabsRect
- AFXTABCTRL/CMFCTabCtrl::GetWndArea
- AFXTABCTRL/CMFCTabCtrl::HideActiveWindowHorzScrollBar
- AFXTABCTRL/CMFCTabCtrl::HideInactiveWindow
- AFXTABCTRL/CMFCTabCtrl::HideNoTabs
- AFXTABCTRL/CMFCTabCtrl::HideSingleTab
- AFXTABCTRL/CMFCTabCtrl::IsActiveInMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::IsActiveTabBoldFont
- AFXTABCTRL/CMFCTabCtrl::IsActiveTabCloseButton
- AFXTABCTRL/CMFCTabCtrl::IsDrawFrame
- AFXTABCTRL/CMFCTabCtrl::IsFlatFrame
- AFXTABCTRL/CMFCTabCtrl::IsFlatTab
- AFXTABCTRL/CMFCTabCtrl::IsLeftRightRounded
- AFXTABCTRL/CMFCTabCtrl::IsMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::IsOneNoteStyle
- AFXTABCTRL/CMFCTabCtrl::IsSharedScroll
- AFXTABCTRL/CMFCTabCtrl::IsTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::IsVS2005Style
- AFXTABCTRL/CMFCTabCtrl::ModifyTabStyle
- AFXTABCTRL/CMFCTabCtrl::OnDragEnter
- AFXTABCTRL/CMFCTabCtrl::OnDragOver
- AFXTABCTRL/CMFCTabCtrl::OnShowTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::SetActiveInMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::SetActiveTab
- AFXTABCTRL/CMFCTabCtrl::SetActiveTabBoldFont
- AFXTABCTRL/CMFCTabCtrl::SetDrawFrame
- AFXTABCTRL/CMFCTabCtrl::SetFlatFrame
- AFXTABCTRL/CMFCTabCtrl::SetImageList
- AFXTABCTRL/CMFCTabCtrl::SetResizeMode
- AFXTABCTRL/CMFCTabCtrl::SetTabMaxWidth
- AFXTABCTRL/CMFCTabCtrl::StopResize
- AFXTABCTRL/CMFCTabCtrl::SynchronizeScrollBar
- AFXTABCTRL/CMFCTabCtrl::m_bEnableActivate
dev_langs: C++
helpviewer_keywords:
- CMFCTabCtrl [MFC], ActivateMDITab
- CMFCTabCtrl [MFC], AllowDestroyEmptyTabbedPane
- CMFCTabCtrl [MFC], AutoSizeWindow
- CMFCTabCtrl [MFC], CalcRectEdit
- CMFCTabCtrl [MFC], Create
- CMFCTabCtrl [MFC], EnableActiveTabCloseButton
- CMFCTabCtrl [MFC], EnableInPlaceEdit
- CMFCTabCtrl [MFC], EnableTabDocumentsMenu
- CMFCTabCtrl [MFC], EnsureVisible
- CMFCTabCtrl [MFC], GetDocumentIcon
- CMFCTabCtrl [MFC], GetFirstVisibleTabNum
- CMFCTabCtrl [MFC], GetResizeMode
- CMFCTabCtrl [MFC], GetScrollBar
- CMFCTabCtrl [MFC], GetTabArea
- CMFCTabCtrl [MFC], GetTabMaxWidth
- CMFCTabCtrl [MFC], GetTabsHeight
- CMFCTabCtrl [MFC], GetTabsRect
- CMFCTabCtrl [MFC], GetWndArea
- CMFCTabCtrl [MFC], HideActiveWindowHorzScrollBar
- CMFCTabCtrl [MFC], HideInactiveWindow
- CMFCTabCtrl [MFC], HideNoTabs
- CMFCTabCtrl [MFC], HideSingleTab
- CMFCTabCtrl [MFC], IsActiveInMDITabGroup
- CMFCTabCtrl [MFC], IsActiveTabBoldFont
- CMFCTabCtrl [MFC], IsActiveTabCloseButton
- CMFCTabCtrl [MFC], IsDrawFrame
- CMFCTabCtrl [MFC], IsFlatFrame
- CMFCTabCtrl [MFC], IsFlatTab
- CMFCTabCtrl [MFC], IsLeftRightRounded
- CMFCTabCtrl [MFC], IsMDITabGroup
- CMFCTabCtrl [MFC], IsOneNoteStyle
- CMFCTabCtrl [MFC], IsSharedScroll
- CMFCTabCtrl [MFC], IsTabDocumentsMenu
- CMFCTabCtrl [MFC], IsVS2005Style
- CMFCTabCtrl [MFC], ModifyTabStyle
- CMFCTabCtrl [MFC], OnDragEnter
- CMFCTabCtrl [MFC], OnDragOver
- CMFCTabCtrl [MFC], OnShowTabDocumentsMenu
- CMFCTabCtrl [MFC], SetActiveInMDITabGroup
- CMFCTabCtrl [MFC], SetActiveTab
- CMFCTabCtrl [MFC], SetActiveTabBoldFont
- CMFCTabCtrl [MFC], SetDrawFrame
- CMFCTabCtrl [MFC], SetFlatFrame
- CMFCTabCtrl [MFC], SetImageList
- CMFCTabCtrl [MFC], SetResizeMode
- CMFCTabCtrl [MFC], SetTabMaxWidth
- CMFCTabCtrl [MFC], StopResize
- CMFCTabCtrl [MFC], SynchronizeScrollBar
- CMFCTabCtrl [MFC], m_bEnableActivate
ms.assetid: d441385d-2c72-4203-96fa-deae2273da35
caps.latest.revision: "33"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6675a7b9130a87be9be36c158e5716cc1afe3d55
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfctabctrl-class"></a>CMFCTabCtrl sınıfı
`CMFCTabCtrl` Sınıfı bir sekme denetimi için işlevsellik sağlar. Sekme denetimi kendi üstüne veya altına yuvalanabilir pencere düz ya da üç boyutlu sekmelerle görüntüler. Sekmeleri metin ve resim görüntüleyebilir ve renk etkin olduğunda değiştirebilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCTabCtrl::CMFCTabCtrl`|Varsayılan Oluşturucu.|  
|`CMFCTabCtrl::~CMFCTabCtrl`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCTabCtrl::ActivateMDITab](#activatemditab)|Geçerli sekme denetimi belirtilen sekmesini görüntüler ve bu sekmede odağı ayarlar.|  
|[CMFCTabCtrl::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)||  
|[CMFCTabCtrl::AutoSizeWindow](#autosizewindow)|Tüm Sekme denetimini windows sekme denetim değişiklikleri, bir kullanıcı arabirimi öğesi, istemci alanını yeniden boyutlandırmak için framework olup olmadığını belirtir.|  
|[CMFCTabCtrl::CalcRectEdit](#calcrectedit)|Belirtilen sekme alanı boyutunu Söndür. (Geçersiz kılmaları `CMFCBaseTabCtrl::CalcRectEdit`.)|  
|[CMFCTabCtrl::Create](#create)|Sekme denetimi oluşturur ve ona ekler `CMFCTabCtrl` nesnesi.|  
|`CMFCTabCtrl::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|[CMFCTabCtrl::EnableActiveTabCloseButton](#enableactivetabclosebutton)|Gösterir veya gizler Kapat düğmesi ( **X**) etkin sekmede.|  
|[CMFCTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Etkinleştirir veya düzenlenebilir sekme etiketleri devre dışı bırakır. (Geçersiz kılmaları [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|  
|[CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu)|Sekmeli windows menüsü açılır bir düğme penceresi sekmelerle kaydırma iki düğme yerini alır.|  
|[CMFCTabCtrl::EnsureVisible](#ensurevisible)|Sekme görünür olmasını sağlar.|  
|[CMFCTabCtrl::GetDocumentIcon](#getdocumenticon)|Bir sekmede sekmeli windows içeren bir açılır menü ile ilişkili simgeyi alır.|  
|[CMFCTabCtrl::GetFirstVisibleTabNum](#getfirstvisibletabnum)|Geçerli sekme denetimi görünür ilk sekme dizinini alır.|  
|[CMFCTabCtrl::GetResizeMode](#getresizemode)|Geçerli sekme denetimi nasıl boyutlandırılabileceğini belirten bir değeri alır.|  
|[CMFCTabCtrl::GetScrollBar](#getscrollbar)|Sekme denetimiyle ilişkili kaydırma çubuğu nesnesine bir işaretçi alır.|  
|[CMFCTabCtrl::GetTabArea](#gettabarea)|Üst veya alt kısmındaki sekme denetimi sekmesini etiket alanının sınırlayıcı dikdörtgenini alır. (Geçersiz kılmaları [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|  
|`CMFCTabCtrl::GetTabFromPoint`|Belirtilen bir nokta içeren sekmeyi alır. (Geçersiz kılmaları [CMFCBaseTabCtrl::GetTabFromPoint](../../mfc/reference/cmfcbasetabctrl-class.md#gettabfrompoint).)|  
|[CMFCTabCtrl::GetTabMaxWidth](#gettabmaxwidth)|Sekme en büyük genişliğini alır.|  
|[CMFCTabCtrl::GetTabsHeight](#gettabsheight)|Geçerli sekme denetimi sekmesini alanının yüksekliğini alır.|  
|[CMFCTabCtrl::GetTabsRect](#gettabsrect)|Geçerli sekme denetimi sekme alanı bounds dikdörtgene alır. (Geçersiz kılmaları [CMFCBaseTabCtrl::GetTabsRect](../../mfc/reference/cmfcbasetabctrl-class.md#gettabsrect).)|  
|`CMFCTabCtrl::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCTabCtrl::GetWndArea](#getwndarea)|Geçerli sekme denetimi istemci alanının sınır alır.|  
|[CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar)|Yatay kaydırma çubuğu varsa etkin pencereyi gizler.|  
|[CMFCTabCtrl::HideInactiveWindow](#hideinactivewindow)|Etkin olmayan sekme denetimi windows görüntülenecek framework olup olmadığını belirtir.|  
|[CMFCTabCtrl::HideNoTabs](#hidenotabs)|Etkinleştirir veya hiçbir görünür sekmeleri varsa sekme alanı çizim devre dışı bırakır.|  
|[CMFCTabCtrl::HideSingleTab](#hidesingletab)|Etkinleştirir veya tek bir sekmeli pencere olduğunda bir sekme çizim devre dışı bırakır. (Geçersiz kılmaları [CMFCBaseTabCtrl::HideSingleTab](../../mfc/reference/cmfcbasetabctrl-class.md#hidesingletab).)|  
|[CMFCTabCtrl::IsActiveInMDITabGroup](#isactiveinmditabgroup)|Sekme denetimi geçerli sekmesinde bir birden çok belge arabirimi sekmesini grubunda active sekmesi olup olmadığını gösterir.|  
|[CMFCTabCtrl::IsActiveTabBoldFont](#isactivetabboldfont)|Etkin sekme metni kalın yazı tipiyle görüntülenip görüntülenmeyeceğini belirtir.|  
|[CMFCTabCtrl::IsActiveTabCloseButton](#isactivetabclosebutton)|Gösterir olup olmadığını Kapat düğmesini ( **X**) etkin bir sekme veya sekmesinde alanın sağ üst köşesinde görüntülenir.|  
|[CMFCTabCtrl::IsDrawFrame](#isdrawframe)|Sekmeli pencere çerçevesi dikdörtgeni katıştırılmış bölmeleri geçici çizer olup olmadığını gösterir.|  
|[CMFCTabCtrl::IsFlatFrame](#isflatframe)|Sekme alanı etrafındaki çerçevenin düz veya 3B olup olmadığını gösterir.|  
|[CMFCTabCtrl::IsFlatTab](#isflattab)|Geçerli sekme denetimi sekmeleri görünümünü düz olup olmadığını gösterir.|  
|[CMFCTabCtrl::IsLeftRightRounded](#isleftrightrounded)|Sol ve sağ tarafındaki bir sekmede geçerli sekme denetiminin görünümünü yuvarlanır olup olmadığını gösterir.|  
|[CMFCTabCtrl::IsMDITabGroup](#ismditabgroup)|Geçerli sekme denetimi Çok Belgeli Arabirim penceresinin istemci alanında bulunup bulunmadığını gösterir.|  
|[CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle)|Geçerli sekme denetimi Microsoft OneNote stilinde görüntülenip görüntülenmeyeceğini belirtir.|  
|`CMFCTabCtrl::IsPtInTabArea`|Bir noktayı sekme alanı içinde olup olmadığını belirler. (Geçersiz kılmaları [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|  
|[CMFCTabCtrl::IsSharedScroll](#issharedscroll)|Geçerli sekme denetimi sekmelerinin grup olarak kaydırabilirsiniz bir kaydırma çubuğunun olup olmadığını gösterir.|  
|[CMFCTabCtrl::IsTabDocumentsMenu](#istabdocumentsmenu)|Sekme denetimi kaydırma düğmelerini veya sekmeli windows menüsünü görüntüler düğmesi görüntülenip görüntülenmeyeceğini belirtir.|  
|[CMFCTabCtrl::IsVS2005Style](#isvs2005style)|Visual Studio .NET 2005 stilde sekmeleri görüntülenip görüntülenmeyeceğini gösterir.|  
|[CMFCTabCtrl::ModifyTabStyle](#modifytabstyle)|Geçerli sekme denetimi sekmeler görünümünü belirtir.|  
|`CMFCTabCtrl::MoveTab`|Sekme başka bir sekmesinde konuma taşır. (Geçersiz kılmaları [CMFCBaseTabCtrl::MoveTab](../../mfc/reference/cmfcbasetabctrl-class.md#movetab).)|  
|[CMFCTabCtrl::OnDragEnter](#ondragenter)|İmleç ilk sekme denetimi penceresine sürüklendiğinde çerçevesi tarafından çağrılır.|  
|[CMFCTabCtrl::OnDragOver](#ondragover)|Fare açılan hedef pencere üzerinde taşındığında bir sürükleme işlemi sırasında çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCBaseTabCtrl::OnDragOver](../../mfc/reference/cmfcbasetabctrl-class.md#ondragover).)|  
|[CMFCTabCtrl::OnShowTabDocumentsMenu](#onshowtabdocumentsmenu)|Sekmeli windows açılan menüsünü görüntüler, kullanıcı bir sekme seçer ve etkin sekme seçilen sekme yapar kadar bekler.|  
|`CMFCTabCtrl::PreTranslateMessage`|Pencere iletileri için gönderilen önce çevirir [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows çalışır. (Geçersiz kılmaları [CMFCBaseTabCtrl::PreTranslateMessage](../../mfc/reference/cmfcbasetabctrl-class.md#pretranslatemessage).)|  
|`CMFCTabCtrl::RecalcLayout`|Sekme denetimi iç düzenini yeniden hesaplar. (Geçersiz kılmaları [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|  
|[CMFCTabCtrl::SetActiveInMDITabGroup](#setactiveinmditabgroup)|Sekme denetimi geçerli sekmesinde bir birden çok belge arabirimi sekmesini grubundaki etkin sekme olarak ayarlar.|  
|[CMFCTabCtrl::SetActiveTab](#setactivetab)|Sekme etkinleştirir. (Geçersiz kılmaları [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|  
|[CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont)|Etkinleştirir veya bir kalın yazı tipiyle etkin sekmelerde kullanımını devre dışı bırakır.|  
|[CMFCTabCtrl::SetDrawFrame](#setdrawframe)|Etkinleştirir veya katıştırılmış bir çubuğu etrafında drawinga çerçeve dikdörtgen devre dışı bırakır.|  
|[CMFCTabCtrl::SetFlatFrame](#setflatframe)|Düz veya 3B çerçeve sekmesini etrafına çizmek belirtir.|  
|[CMFCTabCtrl::SetImageList](#setimagelist)|Görüntü listesi belirtir. (Geçersiz kılmaları [CMFCBaseTabCtrl::SetImageList](../../mfc/reference/cmfcbasetabctrl-class.md#setimagelist).)|  
|[CMFCTabCtrl::SetResizeMode](#setresizemode)|Geçerli sekme denetimi nasıl boyutlandırılabilir belirtir ve denetim görüntüler.|  
|[CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth)|En fazla sekme genişliği sekmeli penceresinde belirtir.|  
|[CMFCTabCtrl::StopResize](#stopresize)|Sekme denetimi geçerli yeniden boyutlandırma işlemi sonlandırır.|  
|`CMFCTabCtrl::SwapTabs`|Sekmeleri çifti değiştirir. (Geçersiz kılmaları [CMFCBaseTabCtrl::SwapTabs](../../mfc/reference/cmfcbasetabctrl-class.md#swaptabs).)|  
|[CMFCTabCtrl::SynchronizeScrollBar](#synchronizescrollbar)|Yatay kaydırma çubuğu düz sekmeleri görüntüleyen bir sekme denetimi çizer.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCTabCtrl::m_bEnableActivate](#m_benableactivate)|Etkin görünüm, yeni bir sekme eklenir ve etkin olduğunda odak kaybetmesini engeller.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCTabCtrl` Sınıfı destekler:  
  
-   3B, düz ve düz bir paylaşılan yatay kaydırma çubuğu içeren denetim stilleri sekmesinde.  
  
-   Üst veya alt kısmında bulunan sekmeler.  
  
-   Metin, görüntüler veya metin ve resim görüntüleme sekmeleri.  
  
-   Sekme etkin olduğunda rengini değiştirmek sekmeleri.  
  
-   Kenarlık boyutu değişiklikler ayarlanabilir sekmeler için.  
  
-   Sekmeli windows çıkarılabilir.  
  
 `CMFCTabCtrl` Sınıfı içeren bir iletişim kutusu, kullanılabilir ancak yerleştirme kullanan uygulamalar gibi çubukları denetim için tasarlanmıştır [!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)] ve [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]. Daha fazla bilgi için bkz: [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md).  
  
 Sekme denetimi uygulamanızda yerleştirme yeniden boyutlandırılabilir, eklemek için aşağıdaki adımları izleyin:  
  
1.  Bir örneğini oluşturmak [CTabbedPane sınıfı](../../mfc/reference/ctabbedpane-class.md).  
  
2.  Çağrı [CDockablePane::Create](../../mfc/reference/cdockablepane-class.md#create).  
  
3.  Kullanım [CBaseTabbedPane::AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) veya [CMFCBaseTabCtrl::InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) yeni sekmeler eklemek için.  
  
4.  Çağrı [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking) böylece geçerli takma sekme denetimi sırasında ana çerçeve penceresi sabitleyebilirsiniz.  
  
5.  Çağrı [CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane) ana kare sekmeli pencere sabitlemek için.  
  
 Yerleştirme denetim çubuğu olarak sekmeli bir pencere oluşturma örneği için bkz: [CTabbedPane sınıfı](../../mfc/reference/ctabbedpane-class.md). Kullanılacak `CMFCTabCtrl` yerleştirme olmayan bir denetim olarak oluşturmak bir `CMFCTabCtrl` nesnesi ve ardından arama [CMFCTabCtrl::Create](#create).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CMFCTabCtrl` yapılandırmak için sınıf bir `CMFCTabCtrl` nesnesi. Örneğin, sekme ekleme, Kapat düğmesi etkin sekmesinde gösterilecek, düzenlenebilir sekme etiketleri etkinleştirmek ve açılır menü sekmeli pencere etiketleri görüntülemek açıklanmaktadır. Bu örneğin parçasıdır [durumu toplama örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection#1](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection#3](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_2.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtabctrl.h  
  
##  <a name="activatemditab"></a>CMFCTabCtrl::ActivateMDITab  
 Geçerli sekme denetimi belirtilen sekmesini görüntüler ve bu sekmede odağı ayarlar.  
  
```  
void ActivateMDITab(int nTab = -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nTab`  
 Bir sekmeye görüntülemek ya da şu anda etkin sekme belirtmek için -1 sıfır tabanlı dizini.  
  
##  <a name="allowdestroyemptytabbedpane"></a>CMFCTabCtrl::AllowDestroyEmptyTabbedPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="autosizewindow"></a>CMFCTabCtrl::AutoSizeWindow  
 Tüm Sekme denetimini windows sekme denetim değişiklikleri, bir kullanıcı arabirimi öğesi, istemci alanını yeniden boyutlandırmak için framework olup olmadığını belirtir.  
  
```  
void AutoSizeWindow(BOOL bAutoSize = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bAutoSize`  
 `TRUE`sekme denetimi windows otomatik olarak yeniden boyutlandırmak için; Aksi takdirde `FALSE`. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="create"></a>CMFCTabCtrl::Create  
 Sekme denetimi oluşturur ve ona ekler `CMFCTabCtrl` nesnesi.  
  
```  
BOOL Create(
    Style style,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    Location location=LOCATION_BOTTOM,  
    BOOL bCloseBtn=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`style`  
 Sekme denetimi stili. Daha fazla bilgi için açıklamalar bakın.  
  
 [in]`rect`  
 Sekme denetimi bounds dikdörtgen.  
  
 [in]`pParentWnd`  
 Bir üst penceresi için bir işaretçi. Olmamalıdır `NULL`.  
  
 [in]`nID`  
 Sekme denetimi kimliği.  
  
 [in]`location`  
 Sekmeleri konumu. Varsayılan değer `LOCATION_BOTTOM` şeklindedir. Daha fazla bilgi için açıklamalar bakın.  
  
 [in]`bCloseBtn`  
 `TRUE`Kapat düğmesi sekmesinde görüntülemek için; Aksi takdirde `FALSE`. Varsayılan değer `FALSE` şeklindedir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin belirttiğiniz değerleri aşağıdaki tabloda açıklanmaktadır `style` parametresi.  
  
|Stil|Açıklama|  
|-----------|-----------------|  
|STYLE_3D|Sekme denetimi ile üç boyutlu bir görünüm oluşturur.|  
|STYLE_FLAT|Sekme denetimi düz sekmelerle oluşturur.|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|Sekme denetimi düz sekmeler ve bir üst pencere tarafından kırpılır, sekmeler kaydırabilirsiniz bir kaydırma çubuğunun oluşturur.|  
|STYLE_3D_ONENOTE|Sekme denetimi Microsoft OneNote stilde oluşturur.|  
|STYLE_3D_VS2005|Sekme denetimi Microsoft Visual Studio 2005 stilde oluşturur.|  
|STYLE_3D_ROUNDED|Microsoft Visual Studio 2005 stili yuvarlatılmış sekmelerle sekme denetimi oluşturur.|  
|STYLE_3D_ROUNDED_SCROLL|Sekme denetimi yuvarlatılmış sekmeler ve Microsoft Visual Studio 2005 stilde kaydırma düğmelerini oluşturur.|  
  
 Aşağıdaki tablo için belirttiğiniz değerleri listeler `location` parametresi.  
  
|Konum|Açıklama|  
|--------------|-----------------|  
|LOCATION_BOTTOM|Sekme denetimi alt kısmındaki sekmeleri bulunur.|  
|LOCATION_TOP|Sekmeler sekme denetimi en üstte yer alır.|  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `Create` yönteminde `CMFCTabCtrl` sınıfı. Bu örneğin parçasıdır [durumu toplama örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection#1](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection#2](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_3.cpp)]  
  
##  <a name="calcrectedit"></a>CMFCTabCtrl::CalcRectEdit  
 Belirtilen sekme alanı boyutunu Söndür.  
  
```  
virtual void CalcRectEdit(CRect& rectEdit);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rectEdit`  
 Sekme alanı belirtir dikdörtgen.  
  
### <a name="remarks"></a>Açıklamalar  
 Sekmenin etiketi değiştirdiğinizde, bu yöntem çağrılır. Bu yöntem tarafından elipsin geçerli sekme yükseklik ve sol tarafında belirtilen dikdörtgenin Söndür ve üst ve alt bir birim Söndür.  
  
##  <a name="enableactivetabclosebutton"></a>CMFCTabCtrl::EnableActiveTabCloseButton  
 Gösterir veya gizler Kapat düğmesi ( **X**) etkin sekmede.  
  
```  
void EnableActiveTabCloseButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
 `TRUE`Kapat düğmesi etkin sekmesinde görüntülemek için; `FALSE` sekme alanı sağ üst köşesindeki kapat düğmesini görüntülemek için. Varsayılan değer `TRUE` şeklindedir.  
  
##  <a name="enableinplaceedit"></a>CMFCTabCtrl::EnableInPlaceEdit  
 Etkinleştirir veya düzenlenebilir sekme etiketleri devre dışı bırakır.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
 `TRUE`düzenlenebilir sekme etiketleri etkinleştirmek için; `FALSE` düzenlenebilir sekme etiketleri devre dışı bırakmak için.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enabletabdocumentsmenu"></a>CMFCTabCtrl::EnableTabDocumentsMenu  
 Pencere sekmeleri kaydırmak için iki düğmeleri kullanan bir kullanıcı arabirimi ve sekmeli Windows açılır menü görüntüleyen bir arabirim arasında geçiş yapar.  
  
```  
void EnableTabDocumentsMenu(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
 `TRUE`açılır menü sekmeli pencere etiketleri görüntülemek için; `FALSE` ileriye ve geriye doğru kaydırma düğmeleri görüntülemek için. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı bir sekme etiketi tıklattığında framework karşılık gelen sekmeli pencere görüntüler. Sekme etiketi görünür durumdaysa konumunu değiştirmeden sekmeli penceresi açılır. Kullanıcı bir belge açılır menüden seçer ve karşılık gelen sekmeli penceresi ekran ise, sekmeli pencere ilk sekme olur.  
  
##  <a name="ensurevisible"></a>CMFCTabCtrl::EnsureVisible  
 Sekme görünür olmasını sağlar.  
  
```  
virtual BOOL EnsureVisible(int iTab);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`iTab`  
 Sekme sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`başarılı olursa; `FALSE` varsa `iTab` parametre dizini geçersiz.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen sekme görünür olduğunu güvence altına almak için bu yöntemi kullanın. Gerekli olduğunda sekme denetimi kayar.  
  
##  <a name="getdocumenticon"></a>CMFCTabCtrl::GetDocumentIcon  
 Bir sekmede sekmeli Windows açılır menü ile ilişkili görüntüsünü alır.  
  
```  
static HICON __stdcall GetDocumentIcon(UINT nCmdID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nCmdID`  
 Bir sekmede açılır menü sekmeli Windows Komut kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir bit eşlem resim işleci.  
  
##  <a name="getfirstvisibletabnum"></a>CMFCTabCtrl::GetFirstVisibleTabNum  
 Geçerli sekme denetimi görünür ilk sekme dizinini alır.  
  
```  
virtual int GetFirstVisibleTabNum() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sekme denetimi bir sekmede sıfır tabanlı dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca Microsoft OneNote stilde sekme denetimi görüntülendiğinde bu yöntemi kullanın. Kullanım [CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle) stilini belirlemek için yöntem.  
  
##  <a name="getresizemode"></a>CMFCTabCtrl::GetResizeMode  
 Geçerli sekme denetimi nasıl boyutlandırılabileceğini belirten bir değeri alır.  
  
```  
ResizeMode GetResizeMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdakilerden birini `CMFCTabCtrl::ResizeMode` nasıl sekme denetimi yeniden boyutlandırılabilir belirten numaralandırma değerlerinin. Olası değerler listesi için Açıklamalar bölümüne bakın [CMFCTabCtrl::SetResizeMode](#setresizemode) yöntemi.  
  
##  <a name="getscrollbar"></a>CMFCTabCtrl::GetScrollBar  
 Sekme denetimiyle ilişkili kaydırma çubuğu nesnesine bir işaretçi alır.  
  
```  
CScrollBar* GetScrollBar();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Scrollbar nesnesine işaretçi bir ya da bir `NULL` sekme denetimi kullanarak oluşturulmamışsa `STYLE_FLAT_SHARED_HORZ_SCROLL` stili.  
  
### <a name="remarks"></a>Açıklamalar  
 Sekme denetiminin katıştırılmış kaydırma çubuğu erişmek için bu yöntemi kullanın. Sekme denetimi yalnızca sahip bir kaydırma çubuğunun nesnesi oluşturulduğunda `STYLE_FLAT_SHARED_HORZ_SCROLL` stili.  
  
##  <a name="gettabarea"></a>CMFCTabCtrl::GetTabArea  
 Üst veya alt kısmındaki sekme denetimi sekmesini etiket alanının sınırlayıcı dikdörtgenini alır.  
  
```  
void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`rectTabAreaTop`  
 Bu yöntem döndürüldüğünde, bu başvuru üst sekme etiket alanı bounds bir dikdörtgen içerir. Dikdörtgen istemci koordinatlarında ' dir. Sekme denetimi üstünde hiçbir sekme etiket alanı varsa, bu başvuru boştur.  
  
 [out]`rectTabAreaBottom`  
 Bu yöntem döndürüldüğünde, bu başvuru alt sekme etiket alanı bounds bir dikdörtgen içerir. Dikdörtgen istemci koordinatlarında ' dir. Sekme denetimi altındaki hiçbir sekme etiket alanı varsa, bu başvuru boştur.  
  
### <a name="remarks"></a>Açıklamalar  
 Sekmeli penceresinde sekme alanı konumunu ve boyutunu belirlemek için bu yöntemi kullanın.  
  
##  <a name="gettabmaxwidth"></a>CMFCTabCtrl::GetTabMaxWidth  
 Sekme en büyük genişliğini alır.  
  
```  
int GetTabMaxWidth() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 En büyük genişliği. piksel cinsinden bir sekmesi. Dönüş değeri 0 ise, sekme genişliği sınırsız olur.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth) en fazla sekme genişliği ayarlamak için yöntem.  
  
##  <a name="gettabsheight"></a>CMFCTabCtrl::GetTabsHeight  
 Geçerli sekme denetimi sekmesini alanının yüksekliğini alır.  
  
```  
virtual int GetTabsHeight() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tüm sekme görünür olur ya da sıfır sekme görünür olması sekme alanı yüksekliği.  
  
##  <a name="gettabsrect"></a>CMFCTabCtrl::GetTabsRect  
 Geçerli sekme denetimi sekme alanı bounds dikdörtgene alır.  
  
```  
virtual void GetTabsRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`rect`  
 Bu yöntem döndürüldüğünde, `rect` parametresi sekme alanı bounds bir dikdörtgen içerir.  
  
##  <a name="getwndarea"></a>CMFCTabCtrl::GetWndArea  
 Geçerli sekme denetimi istemci alanının sınır alır.  
  
```  
void GetWndArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [içinde out]`rect`  
 Bu yöntem döndürüldüğünde, bu parametre geçerli sekme denetimi bounds bir dikdörtgen içerir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hideactivewindowhorzscrollbar"></a>CMFCTabCtrl::HideActiveWindowHorzScrollBar  
 Yatay kaydırma çubuğu varsa Etkin pencerede gizler.  
  
```  
void HideActiveWindowHorzScrollBar();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sekme denetimi kullanıcı sekme denetimi sayfaları arasında geçiş yaptığında yanıp sönen önlemek için bu yöntemi kullanın.  
  
##  <a name="hideinactivewindow"></a>CMFCTabCtrl::HideInactiveWindow  
 Framework etkin olmayan sekme denetimi windows görüntülenip görüntülenmeyeceğini belirtir.  
  
```  
void HideInactiveWindow(BOOL bHide = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bHide`  
 `TRUE`Etkin olmayan bir pencere görüntülememek üzere; `FALSE` etkin penceresini görüntülemek için. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hidenotabs"></a>CMFCTabCtrl::HideNoTabs  
 Etkinleştirir veya hiçbir görünür sekmeleri varsa sekme alanı çizim devre dışı bırakır.  
  
```  
void HideNoTabs(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bHide`  
 `TRUE`Sekme alanı çizim etkinleştirmek için; `FALSE` çizim devre dışı bırakmak için. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hidesingletab"></a>CMFCTabCtrl::HideSingleTab  
 Etkinleştirir veya tek bir sekmeli pencere ise sekmesini çizim devre dışı bırakır.  
  
```  
virtual void HideSingleTab(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bHide`  
 `TRUE`Sekmeli tek bir pencere için bir sekme değil çizileceğini; `FALSE` tek sekme çizmek için. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isactiveinmditabgroup"></a>CMFCTabCtrl::IsActiveInMDITabGroup  
 Sekme denetimi geçerli sekmesinde birden çok belge arabirimi sekmesini grubundaki etkin sekme olup olmadığını gösterir.  
  
```  
BOOL IsActiveInMDITabGroup() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`sekme denetimi geçerli sekmesinde bir MDI sekmesini grubundaki etkin sekme Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Birden çok belge windows ya da dikey veya yatay sekme gruplar halinde düzenlemek ve kolayca belgeleri bir sekme grubundan diğerine karışık.  
  
##  <a name="isactivetabboldfont"></a>CMFCTabCtrl::IsActiveTabBoldFont  
 Etkin sekme metni kalın yazı tipiyle görüntülenip görüntülenmeyeceğini belirtir.  
  
```  
BOOL IsActiveTabBoldFont() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`kalın yazı tipiyle kullanılarak etkin sekme görüntülenir Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont) etkin sekme yazı tipini değiştirmek için yöntem.  
  
##  <a name="isactivetabclosebutton"></a>CMFCTabCtrl::IsActiveTabCloseButton  
 Gösterir olup olmadığını Kapat düğmesini ( **X**) etkin bir sekme veya sekmesinde alanın sağ üst köşesinde görüntülenir.  
  
```  
virtual BOOL IsActiveTabCloseButton() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Kapat düğmesi etkin sekmesinde görüntülenir `FALSE` Kapat düğmesi sekme alanı sağ üst köşesindeki görüntüleniyorsa.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isdrawframe"></a>CMFCTabCtrl::IsDrawFrame  
 Sekmeli pencere çerçevesi dikdörtgeni katıştırılmış bölmeleri geçici çizer olup olmadığını gösterir.  
  
```  
BOOL IsDrawFrame() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bir çerçeve dikdörtgen çizilir Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCTabCtrl::SetDrawFrame](#setdrawframe) etkinleştirme veya devre dışı bir çerçeve dikdörtgen çizme yöntemi.  
  
##  <a name="isflatframe"></a>CMFCTabCtrl::IsFlatFrame  
 Sekme alanı etrafındaki çerçevenin düz veya 3B olup olmadığını gösterir.  
  
```  
BOOL IsFlatFrame() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Sekme alanı etrafındaki çerçevenin düz ise; `FALSE` çerçeve üç boyutlu ise.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCTabCtrl::SetFlatFrame](#setflatframe) çerçeve nasıl çizilir değiştirmek için yöntem.  
  
##  <a name="isflattab"></a>CMFCTabCtrl::IsFlatTab  
 Geçerli sekme denetimi sekmeleri görünümünü düz olup olmadığını gösterir.  
  
```  
virtual BOOL IsFlatTab() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Geçerli sekme denetimi sekmeleri görünümünü düz ise; Aksi takdirde `FALSE`.  
  
##  <a name="isleftrightrounded"></a>CMFCTabCtrl::IsLeftRightRounded  
 Sol ve sağ tarafındaki bir sekmede geçerli sekme denetiminin görünümünü yuvarlanır olup olmadığını gösterir.  
  
```  
virtual BOOL IsLeftRightRounded() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Her sekme yanlarından yuvarlanır; Aksi takdirde `FALSE`.  
  
##  <a name="ismditabgroup"></a>CMFCTabCtrl::IsMDITabGroup  
 Geçerli sekme denetimi Çok Belgeli Arabirim penceresinin istemci alanında bulunup bulunmadığını gösterir.  
  
```  
virtual BOOL IsMDITabGroup() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Geçerli sekme denetimi bir MDI istemci alanı penceresinde ise; Aksi takdirde `FALSE`.  
  
##  <a name="isonenotestyle"></a>CMFCTabCtrl::IsOneNoteStyle  
 Geçerli sekme denetimi Microsoft OneNote stilinde görüntülenip görüntülenmeyeceğini belirtir.  
  
```  
virtual BOOL IsOneNoteStyle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`sekme denetimi Microsoft OneNote stilde görüntülenir Aksi takdirde `FALSE`.  
  
##  <a name="issharedscroll"></a>CMFCTabCtrl::IsSharedScroll  
 Geçerli sekme denetimi sekmelerinin grup olarak kaydırabilirsiniz bir kaydırma çubuğunun olup olmadığını gösterir.  
  
```  
BOOL IsSharedScroll() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`sekme denetimi bir paylaşılan kaydırma çubuğu varsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem `TRUE` varsa `style` parametresinin [CMFCTabCtrl::Create](#create) STYLE_FLAT_SHARED_HORZ_SCROLL bir yöntemdir.  
  
##  <a name="istabdocumentsmenu"></a>CMFCTabCtrl::IsTabDocumentsMenu  
 Sekme denetimi kaydırma düğmelerini veya sekmeli windows menüsünü görüntüler düğmesi görüntülenip görüntülenmeyeceğini belirtir.  
  
```  
BOOL IsTabDocumentsMenu() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Sekmeli windows sekmeli pencere etiketleri açılan menüsünü kullanarak kaydırırsanız; `FALSE` ileriye ve geriye doğru kaydırma düğmelerini kullanarak sekmeli windows kaydırılan durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu) kaydırma yöntemini belirtmek için yöntemi windows sekmeli.  
  
##  <a name="isvs2005style"></a>CMFCTabCtrl::IsVS2005Style  
 Visual Studio 2005 stili kullanılarak sekmeleri çizilir olup olmadığını gösterir.  
  
```  
virtual BOOL IsVS2005Style() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Visual Studio 2005 stili kullanılarak sekmeleri çizilir Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `style` parametresinin [CMFCTabCtrl::Create](#create) yöntemi sekmeleri nasıl çizilir belirtin.  
  
##  <a name="m_benableactivate"></a>CMFCTabCtrl::m_bEnableActivate  
 Etkin görünüm, yeni bir sekme eklenir ve etkin olduğunda odak kaybetmesini engeller.  
  
```  
static BOOL m_bEnableActivate;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sekme eklenen ve etkin yaptıktan sonra odağı genellikle yeni bir sekmeli pencere tarafından alınır. Ayarlama `CMFCTabCtrl::m_bEnableActivate` üye değişkeni `FALSE` özgün odak korumak için. Varsayılan değer `TRUE` şeklindedir.  
  
##  <a name="modifytabstyle"></a>CMFCTabCtrl::ModifyTabStyle  
 Geçerli sekme denetimi sekmeler görünümünü belirtir.  
  
```  
BOOL ModifyTabStyle(Style style);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`style`  
 Sekme denetimi görünümünü belirten numaralandırma değerlerinden biri. Daha fazla bilgi için açıklamalar tabloya bakın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Değeri `style` parametresi şunlardan biri olabilir `CMFCTabCtrl::Style` numaralandırmalar.  
  
|Ad|Açıklama|  
|----------|-----------------|  
|STYLE_3D|Yuvarlak köşeleri sahip üç boyutlu, dikdörtgen sekmeleri görüntüler.|  
|STYLE_3D_ONENOTE|Dikey sütunlardan ve eğimli sütunlardan sahip ve yuvarlanmış köşeleri üç boyutlu sekmeleri görüntüler.|  
|STYLE_3D_ROUNDED|Kenara Eğimli ve yuvarlanmış köşeleri üç boyutlu sekmeleri görüntüler.|  
|STYLE_3D_ROUNDED_SCROLL|Kenara Eğimli ve yuvarlanmış köşeleri üç boyutlu sekmeleri görüntüler. Aynı anda görüntülenebilenden daha fazla sekme varsa, framework açılır okuna ve etkin hale getirmek için sekme menüsünü görüntüler.|  
|STYLE_3D_SCROLLED|Üç boyutlu, dikdörtgen sekmeleri görüntüler. Aynı anda görüntülenebilenden daha fazla sekme varsa, framework açılır okuna ve etkin hale getirmek için sekme menüsünü görüntüler.|  
|STYLE_3D_VS2005|Görüntüler üç boyutlu, Eğimli sütunlardan ve dikey sütunlardan sekmeleri yuvarlanır.|  
|STYLE_FLAT|Sol ve sağ tarafa Eğimli iki boyutlu sekmeleri görüntüler.|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|İki boyutlu sekmeleri görüntüler. Aynı anda görüntülenebilenden daha fazla sekme varsa, framework kaydırma oklarının sekme alanı ucunda görüntüler.|  
  
##  <a name="ondragenter"></a>CMFCTabCtrl::OnDragEnter  
 İmleci geçerli sekme denetimi penceresi ilk girdiğinde bir Sürükle ve bırak işlemi sırasında çerçevesi tarafından çağrılır.  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDataObject`  
 Kullanıcının sürüklediği verileri içeren bir veri nesnesi noktalarına.  
  
 [in]`dwKeyState`  
 Değiştirici tuşları durumunu içerir. Aşağıdaki değerlerin Bitsel bir birleşimi (veya) bu parametredir: `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, ve `MK_RBUTTON`. Daha fazla bilgi için bkz: **ileti parametrelerinin** bölümünü [hakkında fare girdisi](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
 [in]`point`  
 İstemci koordinatları imleci geçerli konumunu içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman `DROPEFFECT_NONE`, yani bırakma hedefi verileri kabul edemez.  
  
### <a name="remarks"></a>Açıklamalar  
 Sürükle ve bırak işlemi desteklemek için bu yöntemi kullanın. Kendi özel davranışı uygulamak için bu yöntemi geçersiz kılın.  
  
 Varsayılan olarak, bu yöntem yalnızca çağırır `CMFCTabCtrl::OnDragOver`, hangi her zaman döndürür `DROPEFFECT_NONE`.  
  
##  <a name="ondragover"></a>CMFCTabCtrl::OnDragOver  
 Fare açılan hedef pencere üzerinde taşındığında bir sürükleme işlemi sırasında çerçevesi tarafından çağrılır.  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDataObject`  
 İşaretçi bir [COleDataObject](../../mfc/reference/coledataobject-class.md) bırakma hedefi sürüklediğiniz nesne.  
  
 [in]`dwKeyState`  
 Bitsel bir birleşimi olan değiştirici tuşları (veya durumunu) `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, ve `MK_RBUTTON`. Daha fazla bilgi için "İletisi parametreleri" bölümüne bakın. [hakkında fare girdisi](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
 [in]`point`  
 Geçerli fare konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman `DROPEFFECT_NONE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel uygulamanızı ile bu yöntemi geçersiz kılın. Daha fazla bilgi için bkz: [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover) yöntemi.  
  
##  <a name="onshowtabdocumentsmenu"></a>CMFCTabCtrl::OnShowTabDocumentsMenu  
 Sekmeli windows açılan menüsünü görüntüler, kullanıcı bir sekme seçer ve etkin sekme seçilen sekme yapar kadar bekler.  
  
```  
virtual void OnShowTabDocumentsMenu(CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`point`  
 Açılır menüyü görüntülemek nereye koordinatları.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setactiveinmditabgroup"></a>CMFCTabCtrl::SetActiveInMDITabGroup  
 Sekme denetimi geçerli sekmesinde birden çok belge arabirimi sekmesini grubundaki etkin sekme olarak ayarlar.  
  
```  
void SetActiveInMDITabGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bActive`  
 `TRUE`Geçerli sekme etkin sekme yapmak için; `FALSE` geçerli sekme devre dışı yapma.  
  
### <a name="remarks"></a>Açıklamalar  
 Birden çok belge windows ya da dikey veya yatay sekme gruplar halinde düzenlemek ve kolayca belgeleri bir sekme grubundan diğerine karışık.  
  
##  <a name="setactivetab"></a>CMFCTabCtrl::SetActiveTab  
 Sekme etkinleştirir.  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`iTab`  
 Etkinleştirmek için sekmesini sıfır tabanlı dizini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Belirtilen sekme etkin yapılmışsa; `FALSE` , belirtilen `iTab` parametresi değeri geçersiz.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem göndermemek `AFX_WM_CHANGE_ACTIVE_TAB` üst penceresine sekme denetimi bildirim.  
  
 `SetActiveTab` Yöntemi otomatik olarak çağırır [CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar) ekranda yanıp sönen gelen önlemek için yöntem.  
  
##  <a name="setactivetabboldfont"></a>CMFCTabCtrl::SetActiveTabBoldFont  
 Etkinleştirir veya bir kalın yazı tipiyle etkin sekmelerde kullanımını devre dışı bırakır.  
  
```  
void SetActiveTabBoldFont(BOOL bIsBold=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bIsBold`  
 `TRUE`kalın yazı tipiyle etkin sekme etiketini görüntülemek için kullanılacak; `FALSE` etiketi görüntülemek için standart yazı tipi kullanılacak. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setdrawframe"></a>CMFCTabCtrl::SetDrawFrame  
 Bir çerçeve dikdörtgeni katıştırılmış bir çubuğu çizilip çizilmeyeceğini belirler.  
  
```  
void SetDrawFrame(BOOL bDraw=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bDraw`  
 `TRUE`bir çerçeve dikdörtgeni katıştırılmış bir çubuğu geçici görüntülemek için; Aksi takdirde `FALSE`. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setflatframe"></a>CMFCTabCtrl::SetFlatFrame  
 Düz veya 3B çerçeve sekmesini etrafına çizmek belirtir.  
  
```  
void SetFlatFrame(
    BOOL bFlat=TRUE,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bFlat`  
 `TRUE`Sekme etrafına bir düz (2D) çerçevesi çizmek için; `FALSE` üç boyutlu (3B) çerçevesi çizmek için. Varsayılan değer `TRUE` şeklindedir.  
  
 [in]`bRepaint`  
 `TRUE`penceresini hemen yeniden boyutlandırmaya için; Aksi takdirde `FALSE`. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setimagelist"></a>CMFCTabCtrl::SetImageList  
 Görüntü listesi belirtir.  
  
```  
virtual BOOL SetImageList(
    UINT uiID,  
    int cx=15,  
    COLORREF clrTransp=RGB(255, 0, 255));  
  
virtual BOOL SetImageList(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiID`  
 Resim listesi içeren bir bit eşlem kaynak kimliği.  
  
 [in]`cx`  
 Her görüntüsünün piksel cinsinden genişliği. Varsayılan değer 15'tir.  
  
 [in]`clrTransp`  
 Saydam Görüntü rengi. Bu renk olan bölümleri resminin saydam olacaktır. Renk Eflatun, RGB(255,0,255) varsayılan değerdir.  
  
 [in]`hImageList`  
 Önceden yüklenen görüntü listesi için bir tanıtıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem başarılı olursa. `FALSE`sekme denetimi düz bir stil kullanarak oluşturduysanız veya ilk yöntemi aşırı yüklemesini tarafından belirtilen bit eşlem yüklerseniz `uiID` parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Sekme denetimi için bir resim listesi ayarlamak için bu yöntemi kullanın. Resim listesi görüntülerden yanındaki sekme etiketi görüntülenir. Böylece resim ve metin içerecek şekilde sekmesini boyuta sahip olmadığından bu yöntem sekmesini yüksekliği yeniden hesaplar.  
  
 Kullanım [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) görüntülenecek resim dizinini belirtmek için sekme denetimi tarafından devralınır yöntemi.  
  
##  <a name="setresizemode"></a>CMFCTabCtrl::SetResizeMode  
 Geçerli sekme denetimi nasıl boyutlandırılabilir belirtir ve denetim görüntüler.  
  
```  
void SetResizeMode(ResizeMode resizeMode);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`resizeMode`  
 Aşağıdakilerden birini `CMFCTabCtrl::ResizeMode` nasıl sekme denetimi yeniden boyutlandırılabilir belirten numaralandırma değerlerinin. Olası değerler listesi için açıklamalar bölümündeki tabloya bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 `resizeMode` Parametresi şunlardan biri olabilir `ResizeMode` numaralandırma değerleri.  
  
|Ad|Açıklama|  
|----------|-----------------|  
|RESIZE_NO|Sekme denetimi boyutlandırılamaz.|  
|RESIZE_VERT|Sekme denetimi dikey ancak değil yatay olarak yeniden boyutlandırılabilir.|  
|RESIZE_HORIZ|Sekme denetimi yatay ancak değil dikey yeniden boyutlandırılabilir.|  
  
##  <a name="settabmaxwidth"></a>CMFCTabCtrl::SetTabMaxWidth  
 En fazla sekme genişliği sekmeli penceresinde belirtir.  
  
```  
void SetTabMaxWidth(int nTabMaxWidth);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nTabMaxWidth`  
 En fazla sekme piksel cinsinden genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Sekmeli bir pencere her bir sekmede genişliğini sınırlamak için bu yöntemi kullanın. Sekmeleri çok uzun etiketleri varsa, bu yöntem kullanışlıdır. [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md) sınıf oluşturucu başlatır en fazla sekme genişliği 0'dır, ama aslında genişliği sınırlı olmadığı anlamına gelir.  
  
##  <a name="stopresize"></a>CMFCTabCtrl::StopResize  
 Sekme denetimi geçerli yeniden boyutlandırma işlemi sonlandırır.  
  
```  
void StopResize(BOOL bCancel);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bCancel`  
 `TRUE`Geçerli yeniden boyutlandırma işlemi iptal etmek için; `FALSE` geçerli tamamlamak için işlemi yeniden boyutlandırın. Her iki durumda da, yeniden boyutlandırma dikdörtgen çizme framework durdurur.  
  
##  <a name="synchronizescrollbar"></a>CMFCTabCtrl::SynchronizeScrollBar  
 Yatay kaydırma çubuğu düz sekmeleri görüntüleyen bir sekme denetimi çizer.  
  
```  
BOOL SynchronizeScrollBar(SCROLLINFO* pScrollInfo = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`pScrollInfo`  
 İşaretçi bir [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) yapısı veya `NULL`. Bu yöntem döndürüldüğünde ve bu parametre değilse `NULL`, yapı kaydırma çubuğunun tüm parametreler içeriyor. Varsayılan değer `NULL` şeklindedir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca düz sekmeleri görüntüleyen bir sekme denetimi etkiler. Kaydırma çubuğu aynı anda tüm sekmeleri etkiler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md)   
 [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md)   
 [CMFCBaseTabCtrl sınıfı](../../mfc/reference/cmfcbasetabctrl-class.md)
