---
title: CMFCOutlookBar sınıfı
ms.date: 06/25/2018
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
ms.openlocfilehash: fc1281db0271393ec0538e26c2a2d2af09c99f7a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58775263"
---
# <a name="cmfcoutlookbar-class"></a>CMFCOutlookBar sınıfı

Öğesinin görsel görünümüne sahip sekmeli bölme **Gezinti bölmesinde** Microsoft Outlook 2000 veya Outlook 2003'te. `CMFCOutlookBar` Nesne içeren bir [CMFCOutlookBarTabCtrl sınıfı](../../mfc/reference/cmfcoutlookbartabctrl-class.md) nesnesi ve bir dizi sekme. Sekmeleri olabilir [CMFCOutlookBarPane sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md) nesneleri veya `CWnd`-türetilmiş nesneler. Kullanıcıya Outlook Çubuğu bir dizi düğme ve görüntüleme alanı görünür. Kullanıcı bir düğmeyi tıkladığında karşılık gelen denetim veya düğme bölmesi görüntülenir.

## <a name="syntax"></a>Sözdizimi

```cpp
class CMFCOutlookBar : public CBaseTabbedPane
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMFCOutlookBar::CMFCOutlookBar`|Varsayılan Oluşturucu.|
|`CMFCOutlookBar::~CMFCOutlookBar`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Boş bir sekmeli bölme yok edilebilir olup olmadığını belirtir. (Geçersiz kılmaları [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|
|[CMFCOutlookBar::CanAcceptPane](#canacceptpane)|Outlook Çubuğu bölmesi için başka bir bölme yerleştirilmiş olup olmadığını belirler. (CDockablePane::CanAcceptPane geçersiz kılar.)|
|[CMFCOutlookBar::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Sekmeli bölmesi için açıklama yazısını aynı metni etkin sekme görüntülenip görüntülenmeyeceğini belirler. (Geçersiz kılmaları [CBaseTabbedPane::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname).)|
|[CMFCOutlookBar::Create](#create)|Outlook Çubuğu denetimi oluşturur.|
|[CMFCOutlookBar::CreateCustomPage](#createcustompage)|Özel bir Outlook Çubuğu sekme oluşturur.|
|`CMFCOutlookBar::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|
|[CMFCOutlookBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Bir kullanıcı bir Outlook Çubuğu dış ucunun denetim çubuğu yerleştirme olup olmadığını belirler.|
|[CMFCOutlookBar::FloatTab](#floattab)|Bölmeyi şu anda çıkarılabilir bir sekmede yer alıyorsa ancak yalnızca bir bölme kaydırır. (Geçersiz kılmaları [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|
|[CMFCOutlookBar::GetButtonsFont](#getbuttonsfont)|Outlook çubuğu düğmelerini metnin yazı tipini döndürür.|
|[CMFCOutlookBar::GetTabArea](#gettabarea)|Outlook Çubuğu için sekmesinde bölümlerden konumunu ve boyutunu döndürür. (Geçersiz kılmaları [CBaseTabbedPane::GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea).)|
|`CMFCOutlookBar::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|
|[CMFCOutlookBar::IsMode2003](#ismode2003)|Outlook Çubuğu davranışını (bkz. Notlar) Microsoft Office Outlook 2003 taklit olup olmadığını belirler.|
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|Çağıran [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) animasyon kullanarak etkin sekmede ayarlandıktan sonra.|
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|Çağıran [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) önce bir sekme sayfası animasyon kullanarak etkin sekme ayarlanır.|
|[CMFCOutlookBar::OnScroll](#onscroll)|Outlook çubuğu yukarı veya aşağı kaydırma, framework tarafından çağırılır.|
|[CMFCOutlookBar::RemoveCustomPage](#removecustompage)|Özel bir Outlook Çubuğu sekme kaldırır.|
|[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)|Outlook çubuğu düğmelerini metnin yazı tipini ayarlar.|
|[CMFCOutlookBar::SetMode2003](#setmode2003)|Outlook Çubuğu davranışını (bkz. Notlar) Outlook 2003 taklit olup olmadığını belirtir.|

## <a name="remarks"></a>Açıklamalar

Bir Outlook Çubuğu bir örnek için bkz [OutlookDemo örnek: MFC OutlookDemo uygulama](../../overview/visual-cpp-samples.md).

## <a name="implementing-the-outlook-bar"></a>Outlook Çubuğu uygulama

Kullanılacak `CMFCOutlookBar` denetim uygulamanızda, aşağıdaki adımları izleyin:

1. Ekleme bir `CMFCOutlookBar` ana çerçeve penceresi sınıfında nesnesine.

    ```cpp
    class CMainFrame : public CMDIFrameWnd
    {
        // ...
        CMFCOutlookBar m_wndOutlookBar;
        CMFCOutlookBarPane m_wndOutlookPane;
        // ...
    };
    ```

1. Ana çerçeve WM_CREATE iletiyi işlerken çağırmak [CMFCOutlookBar::Create](#create) Outlook Çubuğu sekme denetimi oluşturmak için yöntemi.

    ```cpp
    m_wndOutlookBar.Create (_T("Shortcuts"),
        this,
        CRect (0, 0, 100, 100),
        ID_VIEW_OUTLOOKBAR,
        WS_CHILD | WS_VISIBLE | CBRS_LEFT);
    ```

1. Bağlantılı bir işaretçi alma `CMFCOutlookBarTabCtrl` kullanarak [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow).

    ```cpp
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();
    ```

1. Oluşturma bir [CMFCOutlookBarPane sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md) düğmeleri içeren her sekme için nesne.

    ```cpp
    m_wndOutlookPane.Create(&m_wndOutlookBar,
        AFX_DEFAULT_TOOLBAR_STYLE,
        ID_OUTLOOK_PANE_GENERAL,
        AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);

    // make the Outlook pane detachable (enable docking)
    m_wndOutlookPane.EnableDocking(CBRS_ALIGN_ANY);

    // add buttons
    m_wndOutlookPane.AddButton(theApp.LoadIcon (IDR_MAINFRAME),
        "About",
        ID_APP_ABOUT);

    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON),
        "Open",
        ID_FILE_OPEN);
    ```

1. Çağrı [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) her yeni bir sekme eklemek için. Ayarlama *bDetachable* parametresi bir sayfayı çıkarılabilir olmayan yapmak için false. Ya da kullanmak [CMFCOutlookBarTabCtrl::AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) çıkarılabilir sayfalar eklemek için.

    ```cpp
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);
    ```

1. Eklemek için bir `CWnd`-denetim türetilmiş (örneğin, [CMFCShellTreeCtrl sınıfı](../../mfc/reference/cmfcshelltreectrl-class.md)) bir sekme denetim ve çağrı oluşturma [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) Outlook çubuğuna eklenecek.

> [!NOTE]
>  Her biri için benzersiz Denetim kimliklerinin kullanması gereken [CMFCOutlookBarPane sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md) nesnesi ve her `CWnd`-türetilmiş bir nesneye.

Dinamik olarak ekleyin veya yeni sayfalar çalışma zamanında silmek için kullanın [CMFCOutlookBar::CreateCustomPage](#createcustompage) ve [CMFCOutlookBar::RemoveCustomPage](#removecustompage).

## <a name="outlook-2003-mode"></a>Outlook 2003 modu

Outlook 2003 modunda sekme düğmelerinin Outlook Çubuğu bölmesinin en altında yerleştirilir. Düğmeleri görüntülemek için yeterli alan olmadığında bölmesinin alt kısmında bulunan bir araç çubuğu benzeri alanındaki simgeler olarak görüntülenir.

Kullanım [CMFCOutlookBar::SetMode2003](#setmode2003) Outlook 2003 modunu etkinleştirmek için. Kullanım [CMFCOutlookBarTabCtrl::SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) Outlook çubuğu en altında görüntülenen simge bit eşlemi ayarlamak için. Bit eşlem simgeleri sekmesini dizine göre sıralanmış olmaları gerekmektedir.

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

##  <a name="allowdestroyemptytabbedpane"></a>  CMFCOutlookBar::AllowDestroyEmptyTabbedPane

Boş bir sekmeli bölme yok edilebilir olup olmadığını belirtir.

```cpp
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>Dönüş Değeri

Boş bir sekmeli bölme yok edilebilir TRUE; Aksi takdirde FALSE. Varsayılan uygulama her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Framework boş bir sekmeli bölme yok, bunun yerine gizler.

##  <a name="canacceptpane"></a>  CMFCOutlookBar::CanAcceptPane

Outlook Çubuğu bölmesi için başka bir bölme yerleştirilmiş olup olmadığını belirler.

```cpp
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[in] Bu bölme için yerleştirilmiş başka bir bölme için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başka bir bölme Outlook Çubuğu bölmesi için yerleştirilmiş olması gerekiyorsa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu nedenle Outlook Çubuğu yerleştirme Outlook 2003 modundaysa desteklenmiyorsa, dönüş değeri FALSE olur.

Varsa *pBar* parametre NULL ise, bu yöntem FALSE döndürür.

Aksi takdirde, bu yöntem temel yöntemi olarak davranır [CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane)dışında bir Outlook Çubuğu yerleştirme etkin değilse, yine de başka bir Outlook çubuğu üzerine yerleştirilemediğinde etkinleştirebilirsiniz.

##  <a name="cansetcaptiontexttotabname"></a>  CMFCOutlookBar::CanSetCaptionTextToTabName

Sekmeli bölmesi için açıklama yazısını aynı metni etkin sekme görüntülenip görüntülenmeyeceğini belirler.

```cpp
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Outlook çubuğu pencere başlığı etkin sekmede metni için otomatik olarak ayarlanmışsa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Kullanım [CBaseTabbedPane::EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) etkinleştirme veya bu işlevi devre dışı.

Outlook 2003 modunda, bu ayar her zaman etkindir.

##  <a name="create"></a>  CMFCOutlookBar::Create

Outlook Çubuğu denetimi oluşturur.

```cpp
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

*lpszCaption*<br/>
[in] Pencere resim yazısını belirtir.

*pParentWnd*<br/>
[in] Bir üst penceresine bir işaretçi belirtir. NULL olmamalıdır.

*Rect*<br/>
[in] Outlook çubuğu boyutunu ve konumunu piksel cinsinden belirtir.

*nID*<br/>
[in] Denetim kimliğini belirtir. Diğer denetimi uygulamada kullanılan kimlikleri farklı olmalıdır.

*dwStyle*<br/>
[in] İstenen denetim çubuğu stilini belirtir. Olası değerler için bkz. [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*dwControlBarStyle*<br/>
[in] Kitaplığı tarafından tanımlanan özel stilleri belirtir.

*pContext*<br/>
[in] Bağlam oluşturur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CMFCOutlookBar` iki adımda nesne. İlk oluşturucusunu çağırın ve ardından arama `Create`, outlook çubuğu denetimi oluşturur ve ona ekler `CMFCOutlookBar` nesne.

Bkz: [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) tarafından belirtilen için kullanılabilir olan kitaplığı tarafından tanımlanan stiller listesi için *dwControlBarStyle*.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `Create` yöntemi `CMFCOutlookBar` sınıfı. Bu kod parçacığı parçasıdır [Outlook çoklu görünümleri örnek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_OutlookMultiViews#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]

##  <a name="createcustompage"></a>  CMFCOutlookBar::CreateCustomPage

Özel bir Outlook Çubuğu sekme oluşturur.

```cpp
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,
    BOOL bActivatePage=TRUE,
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,
    BOOL bEnableTextLabels=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszPageName*<br/>
[in] Sayfa etiketi.

*bActivatePage*<br/>
[in] TRUE ise, sayfa oluşturulduktan sonra etkinleşir.

*dwEnabledDocking*<br/>
[in] Etkin yerleştirme kenarı sayfanın ayrıldığında belirten CBRS_ALIGN_ bayrakların birleşimi.

*bEnableTextLabels*<br/>
[in] TRUE ise, sayfada bulunan düğmelerinin metin etiketlerini etkinleştirilir.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan bir sayfa ya da oluşturma başarısız olursa NULL bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Özel Outlook Çubuğu sayfaları oluşturmak için kullanıcıları etkinleştirmek için bu yöntemi kullanın. Uygulama başına en fazla 100 sayfaları oluşturabilirsiniz. Sayfa denetimi kimlikleri 0xF000 ' başlatın. Özel Outlook Çubuğu sayfaların toplam sayısı 100 aşarsa oluşturma başarısız olur.

Kullanım [CMFCOutlookBar::RemoveCustomPage](#removecustompage) özel sayfalar silinemedi.

##  <a name="doesallowdyninsertbefore"></a>  CMFCOutlookBar::DoesAllowDynInsertBefore

Bir kullanıcı bir Outlook Çubuğu dış ucunun bölmesine sabitleyebilirsiniz olup olmadığını belirtir.

```
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Framework çağrıları `DoesAllowDynInsertBefore` dinamik bölmesinde sabitlemek için bir konum göründüğünde yöntemi. İşlev FALSE döndürürse, framework bölmesinde dış kenarları tüm dinamik bölmesinde yerleştirme izin vermez.

Genellikle, bir Outlook Çubuğu bir statik değişken olmayan denetimi olarak oluşturun. Bu işlev türetilen bir sınıfta geçersiz kılın ve bu davranışı değiştirmek için true değerini döndürür.

> [!NOTE]
>  Yerleştirme sırasında dinamik bölmeleri yerleştirilmiş statik bölmeleri durumunu denetlemek için dinamik bölmeleri statik bölmeleri sonra mümkün olduğunca dock.

##  <a name="floattab"></a>  CMFCOutlookBar::FloatTab

Bir bölme kayar.

```cpp
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[in] Kayan nokta bölmesi için bir işaretçi.

*nTabID*<br/>
[in] Kayan nokta için sekmesinde sıfır tabanlı dizini.

*dockMethod*<br/>
[in] Bölmesinde float yapmak için kullanılacak yöntemi belirtir.  Daha fazla bilgi için [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).

*bHide*<br/>
[in] Kayan önce bölmesinde gizlemek için TRUE; Aksi takdirde FALSE. Bu yöntemin temel sınıftaki sürümün, bu parametre bir varsayılan değer yok.

### <a name="return-value"></a>Dönüş Değeri

Bölmesinde kaydırıldı TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem benzer [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab) dışında kayan nokta bir Outlook çubuğu denetimini son kalan sekmesinde etkinleştirmez.

##  <a name="getbuttonsfont"></a>  CMFCOutlookBar::GetButtonsFont

Metnin yazı tipini sayfada Outlook çubuğu düğme sekmeleri döndürür.

```cpp
CFont* GetButtonsFont() const;
```

### <a name="return-value"></a>Dönüş Değeri

Metin Outlook sayfası düğmesi sekmeleri görüntülemek için kullanılan yazı nesnesine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Outlook sayfa düğmesi sekmelerinde metni görüntülemek için kullanılan yazı tipi almak için bu işlevi kullanın. Yazı tipi üzerinde çağırarak ayarlayabileceğiniz [CMFCOutlookBar::SetButtonsFont](#setbuttonsfont).

##  <a name="gettabarea"></a>  CMFCOutlookBar::GetTabArea

Boyutunu ve konumunu Outlook Çubuğu sekmesi alanlarının belirler.

```cpp
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>Parametreler

*rectTabAreaTop*<br/>
[out] İşlevi döndüğünde, boyutunu ve konumunu (istemci koordinatlarında) üst sekme alanının içerir.

*rectTabAreaBottom*<br/>
[out] İşlevi döndüğünde, boyutunu ve konumunu (istemci koordinatlarında) alt sekme alanının içerir.

### <a name="remarks"></a>Açıklamalar

Çerçeve hedef bölmesine yerleştirme türünü belirlemek için bu yöntemi çağırır. Kullanıcı'nin hedef bölmesinin sekme alanı yerleştirilemediğinde bölmesi simge durumuna küçültülmüş framework belirlediğinde, ilk bölmesinde hedef bölmesinde yeni bir sekme eklemeyi dener. Aksi takdirde, uygun bir hedef bölmesinde tarafındaki ilk bölmesinde sabitlemek çalışır. Framework ek yerleştirilmiş bölmenin uyum sağlamak için bir kaydırıcı ile yeni bir kapsayıcı oluşturur.

Varsayılan uygulaması `GetTabArea` Outlook çubuğu olan statik; Outlook Çubuğu tüm istemci alanını döndürür, Outlook Çubuğu float olamaz. Aksi takdirde, sayfa düğmelerini Outlook çubuğu denetiminin altındaki ve üstündeki ele alan döndürür.

Öğesinden türetilen sınıfta bu yöntemin `CMFCOutlookBar` bu davranışı değiştirmek için.

##  <a name="ismode2003"></a>  CMFCOutlookBar::IsMode2003

Outlook Çubuğu davranışını Microsoft Office Outlook 2003 taklit olup olmadığını belirtir.

```cpp
BOOL IsMode2003() const;
```

### <a name="return-value"></a>Dönüş Değeri

Outlook Çubuğu Microsoft Office 2003 modunda çalışıyorsa sıfır olmayan; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kullanarak bu modu etkinleştirebilirsiniz [CMFCOutlookBar::SetMode2003](#setmode2003).

##  <a name="onafteranimation"></a>  CMFCOutlookBar::OnAfterAnimation

Çağıran [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) animasyon kullanarak etkin sekmede ayarlandıktan sonra.

```cpp
virtual void OnAfterAnimation(int nPage);
```

### <a name="parameters"></a>Parametreler

*nPage*<br/>
[in] Etkin hale sekme sayfası sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Etkin sekmede ayarlamanın görsel efekt animasyonu olup etkinleştirdiyseniz üzerinde bağlıdır. Daha fazla bilgi için [CMFCOutlookBarTabCtrl::EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation).

##  <a name="onbeforeanimation"></a>  CMFCOutlookBar::OnBeforeAnimation

Çağıran [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) önce bir sekme sayfası animasyon kullanarak etkin sekme ayarlanır.

```cpp
virtual BOOL OnBeforeAnimation(int nPage);
```

### <a name="parameters"></a>Parametreler

*nPage*<br/>
[in] Yaklaşık etkin olarak ayarlanması için sekmesinde sayfasının sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Animasyon yeni etkin sekmede ayarı kullanılması gerekiyorsa TRUE veya FALSE animasyon devre dışı bırakılmalıdır döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="onscroll"></a>  CMFCOutlookBar::OnScroll

Outlook çubuğu yukarı veya aşağı kaydırma, framework tarafından çağırılır.

```cpp
virtual void OnScroll(BOOL bDown);
```

### <a name="parameters"></a>Parametreler

*bDown*<br/>
[in] Outlook Çubuğu aşağı kaydırarak veya yukarı kaydırma, FALSE ise TRUE.

### <a name="remarks"></a>Açıklamalar

##  <a name="removecustompage"></a>  CMFCOutlookBar::RemoveCustomPage

Özel bir Outlook Çubuğu sekme sayfası kaldırır.

```cpp
BOOL RemoveCustomPage(
    UINT uiPage,
    CMFCOutlookBarTabCtrl* pTargetWnd);
```

### <a name="parameters"></a>Parametreler

*Uıpage*<br/>
[in] Sayfanın üst Outlook penceresindeki sıfır tabanlı dizini.

*pTargetWnd*<br/>
[in] Verildiğinde Outlook üst pencere.

### <a name="return-value"></a>Dönüş Değeri

Özel sayfa başarıyla kaldırıldı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Özel sayfalar silmek için bu işlevi çağırın. Sayfa kaldırıldığında denetim Kimliğini kullanılabilir kimlikleri havuzuna döndürülür.

Bir işaretçi sağlamalısınız [CMFCOutlookBarTabCtrl sınıfı](../../mfc/reference/cmfcoutlookbartabctrl-class.md) nesnesi şu anda kaldırılması için sayfayı bulunduğu. Kullanıcının çıkarılabilir sayfaları farklı Outlook çubuğu arasında taşıyabilirsiniz, ancak özel bir sayfa hakkında bilgiler için adlı Outlook Çubuğu nesnesini bulunduğu Not [CMFCOutlookBar::CreateCustomPage](#createcustompage).

Kullanım [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) Outlook penceresine bir işaretçi elde edilir.

##  <a name="setbuttonsfont"></a>  CMFCOutlookBar::SetButtonsFont

Outlook çubuğu düğmelerini metnin yazı tipini ayarlar.

```cpp
void SetButtonsFont(
    CFont* pFont,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
[in] Yeni yazı tipini belirtir.

*bRedraw*<br/>
[in] TRUE ise Outlook Çubuğu çizilir.

### <a name="remarks"></a>Açıklamalar

Bir outlook sekmesinde sayfa düğmelerini görüntülenen metnin yazı tipi ayarlamak için bu yöntemi kullanın.

##  <a name="setmode2003"></a>  CMFCOutlookBar::SetMode2003

Outlook Çubuğu davranışını Outlook 2003 taklit olup olmadığını belirtir.

```cpp
void SetMode2003(BOOL bMode2003=TRUE);
```

### <a name="parameters"></a>Parametreler

*bMode2003*<br/>
[in] TRUE ise, Office 2003 modu etkin.

### <a name="remarks"></a>Açıklamalar

Office 2003 modunu devre dışı bırakmak veya etkinleştirmek için bu işlevi kullanın. Bu modda, Outlook Çubuğu bir ek araç çubuğu özelleştirme düğmesi vardır. Microsoft Office 2003'te Outlook Çubuğu davranışını Outlook Çubuğu davranışını uyar.

Varsayılan olarak, bu modu devre dışıdır.

> [!NOTE]
>  Bu işlev, önce çağrılmalıdır [CMFCOutlookBar::Create](#create).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CBaseTabbedPane Sınıfı](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[CMFCOutlookBarTabCtrl Sınıfı](../../mfc/reference/cmfcoutlookbartabctrl-class.md)<br/>
[CMFCOutlookBarPane Sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md)
