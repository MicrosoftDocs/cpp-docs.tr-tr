---
title: "CMFCOutlookBar sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar::AllowDestroyEmptyTabbedPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanAcceptPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanSetCaptionTextToTabName
- AFXOUTLOOKBAR/CMFCOutlookBar::Create
- AFXOUTLOOKBAR/CMFCOutlookBar::CreateCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::DoesAllowDynInsertBefore
- AFXOUTLOOKBAR/CMFCOutlookBar::FloatTab
- AFXOUTLOOKBAR/CMFCOutlookBar::GetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::GetTabArea
- AFXOUTLOOKBAR/CMFCOutlookBar::IsMode2003
- AFXOUTLOOKBAR/CMFCOutlookBar::OnAfterAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnBeforeAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnScroll
- AFXOUTLOOKBAR/CMFCOutlookBar::RemoveCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::SetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::SetMode2003
dev_langs: C++
helpviewer_keywords:
- CMFCOutlookBar [MFC], AllowDestroyEmptyTabbedPane
- CMFCOutlookBar [MFC], CanAcceptPane
- CMFCOutlookBar [MFC], CanSetCaptionTextToTabName
- CMFCOutlookBar [MFC], Create
- CMFCOutlookBar [MFC], CreateCustomPage
- CMFCOutlookBar [MFC], DoesAllowDynInsertBefore
- CMFCOutlookBar [MFC], FloatTab
- CMFCOutlookBar [MFC], GetButtonsFont
- CMFCOutlookBar [MFC], GetTabArea
- CMFCOutlookBar [MFC], IsMode2003
- CMFCOutlookBar [MFC], OnAfterAnimation
- CMFCOutlookBar [MFC], OnBeforeAnimation
- CMFCOutlookBar [MFC], OnScroll
- CMFCOutlookBar [MFC], RemoveCustomPage
- CMFCOutlookBar [MFC], SetButtonsFont
- CMFCOutlookBar [MFC], SetMode2003
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
caps.latest.revision: "34"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 00988ef4a0b70561ec3a5687502ddae95508dad5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcoutlookbar-class"></a>CMFCOutlookBar sınıfı
Görsel görünümünü sekmeli bölmesiyle **Gezinti Bölmesi** Microsoft Outlook 2000 veya Outlook 2003'te. `CMFCOutlookBar` Nesnesini içeren bir [CMFCOutlookBarTabCtrl sınıfı](../../mfc/reference/cmfcoutlookbartabctrl-class.md) nesne ve bir dizi sekme. Sekmeleri birini kullanabilir [CMFCOutlookBarPane sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md) nesneleri veya `CWnd`-türetilmiş nesneleri. Kullanıcı için Outlook çubuğu düğmeleri ve görüntüleme alanı bir dizi olarak görünür. Kullanıcı bir düğmesine tıkladığında, ilgili denetim veya düğmesi bölmesinde görüntülenir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCOutlookBar : public CBaseTabbedPane  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCOutlookBar::CMFCOutlookBar`|Varsayılan Oluşturucu.|  
|`CMFCOutlookBar::~CMFCOutlookBar`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Boş bir sekmeli bölmesinde yok edilmesi belirtir. (Geçersiz kılmaları [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|  
|[CMFCOutlookBar::CanAcceptPane](#canacceptpane)|Başka bir bölme Outlook Çubuğu bölmesine yerleştirilmiş olup olmadığını belirler. (CDockablePane::CanAcceptPane geçersiz kılar.)|  
|[CMFCOutlookBar::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Sekmeli bölmesi için başlığı etkin sekme aynı metin görüntülenip görüntülenmeyeceğini belirler. (Geçersiz kılmaları [CBaseTabbedPane::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname).)|  
|[CMFCOutlookBar::Create](#create)|Outlook Çubuğu denetimi oluşturur.|  
|[CMFCOutlookBar::CreateCustomPage](#createcustompage)|Özel bir Outlook Çubuğu sekme oluşturur.|  
|`CMFCOutlookBar::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|[CMFCOutlookBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Bir kullanıcı Outlook Çubuğu dış kenarında denetim çubuğu yerleştirme olup olmadığını belirler.|  
|[CMFCOutlookBar::FloatTab](#floattab)|Bölmesinde şu anda çıkarılabilir bir sekmede bulunuyorsa ancak yalnızca bir bölme kayar. (Geçersiz kılmaları [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|  
|[CMFCOutlookBar::GetButtonsFont](#getbuttonsfont)|Metnin yazı tipini Outlook çubuğu düğmelerini döndürür.|  
|[CMFCOutlookBar::GetTabArea](#gettabarea)|Boyutunu ve konumunu sekmesini alanlarının Outlook çubuğunda döndürür. (Geçersiz kılmaları [CBaseTabbedPane::GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea).)|  
|`CMFCOutlookBar::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCOutlookBar::IsMode2003](#ismode2003)|Outlook Çubuğu davranışını (açıklamalar bakın) Microsoft Office Outlook 2003 taklit olup olmadığını belirler.|  
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|Tarafından çağrılır [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) etkin sekme animasyon kullanarak ayarlandıktan sonra.|  
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|Tarafından çağrılır [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) önce bir sekme sayfası animasyon kullanarak etkin sekme ayarlanır.|  
|[CMFCOutlookBar::OnScroll](#onscroll)|Outlook çubuğu yukarı veya aşağı kaydırma varsa çerçevesi tarafından çağrılır.|  
|[CMFCOutlookBar::RemoveCustomPage](#removecustompage)|Özel bir Outlook Çubuğu sekme kaldırır.|  
|[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)|Metnin yazı tipini Outlook çubuğu düğmelerini ayarlar.|  
|[CMFCOutlookBar::SetMode2003](#setmode2003)|Outlook Çubuğu davranışını (açıklamalar bakın) Outlook 2003 taklit olup olmadığını belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir Outlook çubuğu örneği için bkz: [OutlookDemo örnek: MFC OutlookDemo uygulama](../../visual-cpp-samples.md).  
  
## <a name="implementing-the-outlook-bar"></a>Outlook Çubuğu uygulama  
 Kullanılacak `CMFCOutlookBar` denetiminde uygulamanızda, şu adımları izleyin:  
  
1.  Embed bir `CMFCOutlookBar` ana çerçeve pencere sınıfı nesnesine.  
  
 ```  
    class CMainFrame : public CMDIFrameWnd  
 { ...  
    CMFCOutlookBar m_wndOutlookBar;  
    CMFCOutlookBarPane m_wndOutlookPane;  
 ... };  
 ```  
2.  İşleme sırasında `WM_CREATE` ana çerçevesinde, çağrı ileti [CMFCOutlookBar::Create](#create) Outlook sekme denetimi çubuğu oluşturmak için yöntemi.  
  
 ```  
    m_wndOutlookBar.Create (_T("Shortcuts"),
    this,
    CRect (0,
    0,
    100,
    100),
    ID_VIEW_OUTLOOKBAR,
    WS_CHILD | WS_VISIBLE | CBRS_LEFT);

 ```  
3.  Arka plandaki bir işaretçi elde `CMFCOutlookBarTabCtrl` kullanarak [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow).  
  
 ```  
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();

 ```  
4.  Oluşturma bir [CMFCOutlookBarPane sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md) düğmelerini içeren her sekme nesne.  
  
 ```  
    m_wndOutlookPane.Create (&m_wndOutlookBar,
    AFX_DEFAULT_TOOLBAR_STYLE,
    ID_OUTLOOK_PANE_GENERAL,
    AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);
*// make the Outlook pane detachable (enable docking)  
    m_wndOutlookPane.EnableDocking (CBRS_ALIGN_ANY);
*// add buttons  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_MAINFRAME), "About",
    ID_APP_ABOUT);

    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON), "Open",
    ID_FILE_OPEN);

 ```  
5.  Çağrı [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) her yeni sekmede eklemek için. Ayarlama `bDetachable` parametresi `FALSE` bir sayfa çıkarılabilir olmayan yapma. Veya kullanmak [CMFCOutlookBarTabCtrl::AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) çıkarılabilir sayfaları eklemek için.  
  
 ```  
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1,
    TRUE);

 ```  
6.  Eklemek için bir `CWnd`-denetim türetilmiş (örneğin, [CMFCShellTreeCtrl sınıfı](../../mfc/reference/cmfcshelltreectrl-class.md)) bir sekme denetimi ve çağrı oluşturma [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) Outlook çubuğuna eklemek için.  
  
> [!NOTE]
>  Her biri için benzersiz Denetim kimliklerinin kullanması gereken [CMFCOutlookBarPane sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md) nesnesi ve her `CWnd`-türetilmiş bir nesne içermelidir.  
  
 Dinamik olarak ekleyin veya çalışma zamanında yeni sayfa silmek için kullanın [CMFCOutlookBar::CreateCustomPage](#createcustompage) ve [CMFCOutlookBar::RemoveCustomPage](#removecustompage).  
  
## <a name="outlook-2003-mode"></a>Outlook 2003 modu  
 Outlook 2003 modunda sekme düğmeleri Outlook Çubuğu bölmesinin en altında konumlandırılır. Düğmeleri görüntülemek için yeterli alan olmadığında bölmesinin boyunca araç benzeri alanındaki simgeler olarak görüntülenir.  
  
 Kullanım [CMFCOutlookBar::SetMode2003](#setmode2003) Outlook 2003 modunu etkinleştirmek için. Kullanım [CMFCOutlookBarTabCtrl::SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) Outlook Çubuğu altta görüntülenen simgeler içeren bit eşlem ayarlamak için. Bit eşlem simgeleri sekme dizini tarafından sıralanmalıdır.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxoutlookbar.h  
  
##  <a name="allowdestroyemptytabbedpane"></a>CMFCOutlookBar::AllowDestroyEmptyTabbedPane  
 Boş bir sekmeli bölmesinde yok edilmesi belirtir.  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`boş bir sekmeli bölmesinde yok Aksi takdirde `FALSE`. Varsayılan uygulama her zaman döndürür `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve boş bir sekmeli bölmesinde yok, bunun yerine gizler.  
  
##  <a name="canacceptpane"></a>CMFCOutlookBar::CanAcceptPane  
 Başka bir bölme Outlook Çubuğu bölmesine yerleştirilmiş olup olmadığını belirler.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 Bu bölme yerleşik başka bir bölme için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`başka bir bölme Outlook Çubuğu bölmesine; yerleşik, Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Outlook Çubuğu Outlook 2003 modundaysa, dönüş değeri olacak şekilde yerleştirme desteklenmez, `FALSE`.  
  
 Varsa `pBar` parametresi `NULL`, bu yöntem `FALSE`.  
  
 Aksi takdirde, bu yöntem temel yöntemi olarak davranır [CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane), yerleştirme etkin değilse, bir Outlook Çubuğu hala üzerine yerleştirilmiş için başka bir Outlook çubuğunu etkinleştirebilirsiniz dışında.  
  
##  <a name="cansetcaptiontexttotabname"></a>CMFCOutlookBar::CanSetCaptionTextToTabName  
 Sekmeli bölmesi için başlığı etkin sekme aynı metin görüntülenip görüntülenmeyeceğini belirler.  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Outlook penceresinin başlık çubuğu etkin sekme metni için otomatik olarak ayarlanır Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CBaseTabbedPane::EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) etkinleştirin veya bu işlevi devre dışı.  
  
 Outlook 2003 modunda, bu ayar her zaman etkindir.  
  
##  <a name="create"></a>CMFCOutlookBar::Create  
 Outlook Çubuğu denetimi oluşturur.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwControlBarStyle=AFX_CBRS_RESIZE,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszCaption`  
 Pencere resim yazısını belirtir.  
  
 [in]`pParentWnd`  
 Bir üst penceresi için bir işaretçi belirtir. NULL olmamalıdır.  
  
 [in]`rect`  
 Outlook çubuğu boyutunu ve konumunu piksel cinsinden belirtir.  
  
 [in]`nID`  
 Denetim kimliğini belirtir. Uygulamada kullanılan kimlikleri diğer denetiminden farklı olması gerekir.  
  
 [in]`dwStyle`  
 İstenen denetim çubuğu stilini belirtir. Olası değerler için bkz: [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in]`dwControlBarStyle`  
 Özel kitaplığı tanımlanan stiller belirtir.  
  
 [in]`pContext`  
 Bağlam oluşturun.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CMFCOutlookBar` iki adımda nesne. İlk Oluşturucusu arayın ve ardından arama `Create`, outlook çubuğu denetimi oluşturur ve ekler `CMFCOutlookBar` nesnesi.  
  
 Bkz: [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) tarafından belirtilen için kullanılabilir olan kitaplığı tanımlanan stiller listesi için `dwControlBarStyle`.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `Create` yöntemi `CMFCOutlookBar` sınıfı. Bu kod parçacığını parçası olan [Outlook çoklu görünümler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]  
  
##  <a name="createcustompage"></a>CMFCOutlookBar::CreateCustomPage  
 Özel bir Outlook Çubuğu sekme oluşturur.  
  
```  
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,  
    BOOL bActivatePage=TRUE,  
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,  
    BOOL bEnableTextLabels=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszPageName`  
 Sayfa etiketi.  
  
 [in]`bActivatePage`  
 Varsa `TRUE`, sayfa oluşturma sırasında etkinleşir.  
  
 [in]`dwEnabledDocking`  
 Etkin takma yanları sayfa ayrılması belirten bir birleşimi CBRS_ALIGN_ bayrakları.  
  
 [in]`bEnableTextLabels`  
 Varsa `TRUE`, metin etiketlerini sayfasında bulunan düğmeleri için etkinleştirilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan sayfa için bir işaretçi veya `NULL` oluşturma başarısız olursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcıların özel Outlook Çubuğu sayfaları oluşturmak bu yöntemi kullanın. Uygulama başına en fazla 100 sayfaları oluşturabilirsiniz. Sayfa denetimini kimlikleri 0xF000 başlatın. Özel Outlook Çubuğu sayfaların toplam sayısı 100 aşarsa oluşturma başarısız olur.  
  
 Kullanım [CMFCOutlookBar::RemoveCustomPage](#removecustompage) özel sayfaları silmek için.  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCOutlookBar::DoesAllowDynInsertBefore  
 Bir kullanıcı bir Outlook Çubuğu dış ucunun bölmesinde yerleştirme olup olmadığını belirtir.  
  
```  
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama döndürür `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework çağrıları `DoesAllowDynInsertBefore` dinamik bölmesinde yerleştirme için bir konum göründüğünde yöntemi. İşlev döndürürse `FALSE`, framework herhangi bir dinamik bölme bölmesinde dış kenarlarında yerleştirme izin vermiyor.  
  
 Genellikle, bir Outlook Çubuğu statik bir değişken olmayan denetimi oluşturun. Bu işlev bir türetilmiş sınıfta geçersiz kılabilir ve dönüş `TRUE` bu davranışı değiştirmek için.  
  
> [!NOTE]
>  Yerleştirme sırasında dinamik bölmeleri yerleşik statik bölmeleri durumunu denetlemek için statik bölmeleri sonra mümkün olduğunca dinamik bölmeleri yerleştirme.  
  
##  <a name="floattab"></a>CMFCOutlookBar::FloatTab  
 Bir bölme kayar.  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 Float bölmesine bir işaretçi.  
  
 [in]`nTabID`  
 Float sekmesine sıfır tabanlı dizini.  
  
 [in]`dockMethod`  
 Bölmesinde yüzer duruma getirmek için kullanılacak yöntemi belirtir.  Daha fazla bilgi için bkz: [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).  
  
 [in]`bHide`  
 `TRUE`Kayan önce bölmesini gizlemek için; Aksi takdirde `FALSE`. Bu yöntem temel sınıf sürümü, bu parametre bir varsayılan değeri yok.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bölmesinde kaydırılmış Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem benzer [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab) dışında bir Outlook Çubuğu denetimi float için Son kalan sekmesinde etkinleştirmez.  
  
##  <a name="getbuttonsfont"></a>CMFCOutlookBar::GetButtonsFont  
 Metnin yazı tipini sayfada Outlook çubuğu düğmesini sekmelerinde döndürür.  
  
```  
CFont* GetButtonsFont() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metni Outlook sayfa düğmesi sekmelerini görüntülemek için kullanılan yazı tipi nesnesine bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Outlook sayfa düğmesi sekmelerinde metni görüntülemek için kullanılan yazı tipi almak için bu işlevi kullanın. Üzerinde çağırarak yazı tipini ayarlayabilirsiniz [CMFCOutlookBar::SetButtonsFont](#setbuttonsfont).  
  
##  <a name="gettabarea"></a>CMFCOutlookBar::GetTabArea  
 Boyutunu ve konumunu Outlook çubuğunda sekme alanlarının belirler.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`rectTabAreaTop`  
 İşlevi döndüğünde boyutunu ve konumunu (istemci koordinatlarında) üst sekme alanı içerir.  
  
 [out]`rectTabAreaBottom`  
 İşlevi döndüğünde boyutunu ve konumunu (istemci koordinatlarında) alt sekme alanı içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework hedef bölmesine yerleştirme türünü belirlemek için bu yöntemi çağırır. Kullanıcının hedef bölmesinde sekme alanı yerleştirilmiş için bölmesinde sürüklediği framework belirlediğinde, yeni bir sekmede hedef bölmesinin ilk bölmesinde eklemeye çalışır. Aksi takdirde, uygun hedef bölmesinde tarafındaki ilk bölmesinde sabitlemek çalışır. Framework ek yerleşik bölmesinde uyum sağlayacak şekilde içeren bir kaydırıcı yeni bir kapsayıcı oluşturur.  
  
 Varsayılan uygulaması `GetTabArea` Outlook çubuğu olan statik; ise, Outlook Çubuğu tüm istemci alanını döndürür, Outlook Çubuğu float olamaz. Aksi takdirde, üst ve alt Outlook çubuğu denetiminin sayfa düğmelerini ele alan döndürür.  
  
 Türetilen sınıfındaki bu yöntemi geçersiz kılın `CMFCOutlookBar` bu davranışı değiştirmek için.  
  
##  <a name="ismode2003"></a>CMFCOutlookBar::IsMode2003  
 Outlook Çubuğu davranışını Microsoft Office Outlook 2003 taklit olup olmadığını belirtir.  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Outlook Çubuğu Microsoft Office 2003 modunda çalışıyorsa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu mod kullanarak etkinleştirebilirsiniz [CMFCOutlookBar::SetMode2003](#setmode2003).  
  
##  <a name="onafteranimation"></a>CMFCOutlookBar::OnAfterAnimation  
 Tarafından çağrılır [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) etkin sekme animasyon kullanarak ayarlandıktan sonra.  
  
```  
virtual void OnAfterAnimation(int nPage);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nPage`  
 Etkin hale sekme sayfası sıfır tabanlı dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon olup etkinleştirdiyseniz üzerinde etkin sekme ayarı visual etkisini bağlıdır. Daha fazla bilgi için bkz: [CMFCOutlookBarTabCtrl::EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation).  
  
##  <a name="onbeforeanimation"></a>CMFCOutlookBar::OnBeforeAnimation  
 Tarafından çağrılır [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) önce bir sekme sayfası animasyon kullanarak etkin sekme ayarlanır.  
  
```  
virtual BOOL OnBeforeAnimation(int nPage);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nPage`  
 Yaklaşık etkin ayarlanacak sekme sayfası sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` animasyon yeni etkin sekme ayarı kullanılıp kullanılmayacağını veya `FALSE` animasyon devre dışı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onscroll"></a>CMFCOutlookBar::OnScroll  
 Outlook çubuğu yukarı veya aşağı kaydırma varsa çerçevesi tarafından çağrılır.  
  
```  
virtual void OnScroll(BOOL bDown);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bDown`  
 `TRUE`Outlook Çubuğu aşağı kaydırma varsa veya `FALSE` yukarı kaydırma durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removecustompage"></a>CMFCOutlookBar::RemoveCustomPage  
 Özel bir Outlook Çubuğu sekme sayfası kaldırır.  
  
```  
BOOL RemoveCustomPage(
    UINT uiPage,  
    CMFCOutlookBarTabCtrl* pTargetWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiPage`  
 Sayfanın üst Outlook penceresinde sıfır tabanlı dizini.  
  
 [in]`pTargetWnd`  
 Verildiğinde üst Outlook penceresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Özel sayfa başarıyla kaldırıldı, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel sayfaları silmek için bu işlevini çağırın. Sayfa kaldırıldığında denetim Kimliğini kullanılabilir kimlikleri havuzuna döndürülür.  
  
 Bir işaretçi sağlamalısınız [CMFCOutlookBarTabCtrl sınıfı](../../mfc/reference/cmfcoutlookbartabctrl-class.md) nesne şu anda kaldırılacak sayfa bulunduğu. Bir kullanıcı çıkarılabilir sayfaları arasında farklı Outlook Çubukları taşıyabilirsiniz, ancak özel bir sayfa hakkında bilgi için çağırıldığı Outlook Çubuğu nesnesinde bulunan Not [CMFCOutlookBar::CreateCustomPage](#createcustompage).  
  
 Kullanım [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) Outlook penceresi için bir işaretçi elde edilir.  
  
##  <a name="setbuttonsfont"></a>CMFCOutlookBar::SetButtonsFont  
 Metnin yazı tipini Outlook çubuğu düğmelerini ayarlar.  
  
```  
void SetButtonsFont(
    CFont* pFont,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pFont`  
 Yeni yazı tipini belirtir.  
  
 [in]`bRedraw`  
 Varsa `TRUE`, Outlook Çubuğu çizilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Outlook sekmesinde sayfa düğmeleri görüntülenen metni için yazı tipi ayarlamak için bu yöntemi kullanın.  
  
##  <a name="setmode2003"></a>CMFCOutlookBar::SetMode2003  
 Outlook Çubuğu davranışını Outlook 2003 taklit olup olmadığını belirtir.  
  
```  
void SetMode2003(BOOL bMode2003=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bMode2003`  
 TRUE ise, Office 2003 modu etkin.  
  
### <a name="remarks"></a>Açıklamalar  
 Etkinleştirmek veya Office 2003 modu devre dışı bırakmak için bu işlevi kullanın. Bu modda, Outlook çubuğu özelleştirme düğmesini kullanarak bir ek araç vardır. Microsoft Office 2003'te Outlook Çubuğu davranışını için Outlook Çubuğu davranışını uyumludur.  
  
 Varsayılan olarak, bu mod devre dışıdır.  
  
> [!NOTE]
>  Bu işlev önce çağrılmalıdır [CMFCOutlookBar::Create](#create).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CBaseTabbedPane sınıfı](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBarTabCtrl sınıfı](../../mfc/reference/cmfcoutlookbartabctrl-class.md)   
 [CMFCOutlookBarPane sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md)
