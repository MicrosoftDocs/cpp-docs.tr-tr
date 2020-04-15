---
title: CMFCOutlookBar Sınıfı
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
ms.openlocfilehash: fe328cb0d857ff9154624d218b1b56362890ce81
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369649"
---
# <a name="cmfcoutlookbar-class"></a>CMFCOutlookBar Sınıfı

Microsoft Outlook 2000 veya Outlook 2003'teki **Gezinti Bölmesi'nin** görsel görünümünü içeren sekmeli bölme. Nesne `CMFCOutlookBar` bir [CMFCOutlookBarTabCtrl Sınıf](../../mfc/reference/cmfcoutlookbartabctrl-class.md) nesnesi ve bir dizi sekme içerir. Sekmeler [CMFCOutlookBarPane Sınıf](../../mfc/reference/cmfcoutlookbarpane-class.md) nesneleri veya `CWnd`türetilmiş nesneler olabilir. Kullanıcı için Outlook çubuğu bir dizi düğme ve görüntü alanı olarak görünür. Kullanıcı bir düğmeyi tıklattığında, karşılık gelen denetim veya düğme bölmesi görüntülenir.

## <a name="syntax"></a>Sözdizimi

```cpp
class CMFCOutlookBar : public CBaseTabbedPane
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMFCOutlookBar::CMFCOutlookBar`|Varsayılan oluşturucu.|
|`CMFCOutlookBar::~CMFCOutlookBar`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Boş sekmeli bölmenin yok edilip edilmeyeceğini belirtir. (Geçersiz kılar [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|
|[CMFCOutlookBar::CanAcceptPane](#canacceptpane)|Başka bir bölmenin Outlook çubuğubölmesine sabitlenip yapıştırılamayacağını belirler. (CDockablePane geçersiz kılar::CanAcceptPane.)|
|[CMFCOutlookBar::CanSetCaptionTexttotabname](#cansetcaptiontexttotabname)|Sekmeli bölmenin alt yazısının etkin sekmeyle aynı metni gösterip görüntülemediğini belirler. (Geçersiz kılar [CBaseTabbedPane::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname).)|
|[CMFCOutlookBar::Oluştur](#create)|Outlook çubuğu denetimini oluşturur.|
|[CMFCOutlookBar::CreateCustomPage](#createcustompage)|Özel bir Outlook çubuğu sekmesi oluşturur.|
|`CMFCOutlookBar::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|[CMFCOutlookBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Kullanıcının Outlook çubuğunun dış kenarına bir denetim çubuğu nu sabitleyip yerleştirmeyebileceğini belirler.|
|[CMFCOutlookBar::FloatTab](#floattab)|Bölmeyi yüzdürür, ancak bölme şu anda çıkarılabilir bir sekmede bulunursa. (Geçersiz Kılar [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|
|[CMFCOutlookBar::GetButtonsFont](#getbuttonsfont)|Outlook çubuğunun düğmelerinde metnin yazı tipini döndürür.|
|[CMFCOutlookBar::GetTabArea](#gettabarea)|Outlook çubuğundaki sekme alanlarının boyutunu ve konumunu döndürür. (Geçersiz kılar [CBaseTabbedPane::GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea).)|
|`CMFCOutlookBar::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCOutlookBar::IsMode2003](#ismode2003)|Outlook çubuğunun davranışının Microsoft Office Outlook 2003'ün davranışını taklit edip etmediğini belirler (bkz. Açıklamalar).|
|[CMFCOutlookBar::OnafterAnimation](#onafteranimation)|[CMFCOutlookBarTabCtrl tarafından çağrılan::Etkin](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) sekme animasyon kullanılarak ayarlandıktan sonra SetActiveTab.|
|[CMFCOutlookBar::OnBeforeAnimasyon](#onbeforeanimation)|[CMFCOutlookBarTabCtrl tarafından çağrılan::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) önce bir sekme sayfası animasyon kullanarak etkin sekme olarak ayarlanır.|
|[CMFCOutlookBar::OnScroll](#onscroll)|Outlook çubuğu yukarı veya aşağı kaydırılıyorsa çerçeve tarafından çağrılır.|
|[CMFCOutlookBar::RemoveCustomPage](#removecustompage)|Özel Outlook çubuğu sekmesini kaldırır.|
|[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)|Outlook çubuğunun düğmelerinde metnin yazı tipini ayarlar.|
|[CMFCOutlookBar::SetMode2003](#setmode2003)|Outlook çubuğunun davranışının Outlook 2003'tekileri taklit edip etmediğini belirtir (Bkz. Açıklamalar).|

## <a name="remarks"></a>Açıklamalar

Outlook çubuğu örneği için [OutlookDemo Örneği' ne bakın: MFC OutlookDemo Uygulaması.](../../overview/visual-cpp-samples.md)

## <a name="implementing-the-outlook-bar"></a>Outlook Çubuğu'nu uygulama

Uygulamanızdaki `CMFCOutlookBar` denetimi kullanmak için aşağıdaki adımları izleyin:

1. Ana çerçeve `CMFCOutlookBar` penceresi sınıfına bir nesne gömün.

    ```cpp
    class CMainFrame : public CMDIFrameWnd
    {
        // ...
        CMFCOutlookBar m_wndOutlookBar;
        CMFCOutlookBarPane m_wndOutlookPane;
        // ...
    };
    ```

1. Ana çerçevede WM_CREATE iletiyi işlerken [CMFCOutlookBar'ı arayın::Outlook](#create) çubuğu sekmesi denetimini oluşturmak için yöntem oluşturun.

    ```cpp
    m_wndOutlookBar.Create (_T("Shortcuts"),
        this,
        CRect (0, 0, 100, 100),
        ID_VIEW_OUTLOOKBAR,
        WS_CHILD | WS_VISIBLE | CBRS_LEFT);
    ```

1. CBaseTabbedPane `CMFCOutlookBarTabCtrl` kullanarak altta yatan bir işaretçi [edinin::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow).

    ```cpp
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();
    ```

1. Düğmeleri içeren her sekme için bir [CMFCOutlookBarPane Sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md) nesnesi oluşturun.

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

1. Her yeni sekmeyi eklemek için [CMFCOutlookBarTabCtrl::AddTab'ı](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) arayın. *bDetachable* Veya, çıkarılabilir sayfalar eklemek için [CMFCOutlookBarTabCtrl::AddControl'i](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) kullanın.

    ```cpp
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);
    ```

1. Sekme `CWnd`olarak türetilmiş bir denetim (örneğin [CMFCShellTreeCtrl Sınıfı)](../../mfc/reference/cmfcshelltreectrl-class.md)eklemek için denetimi oluşturun ve [CMFCOutlookBarTabCtrl'ı arayın::Outlook](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) çubuğuna eklemek için AddTab'ı ekleyin.

> [!NOTE]
> Her [CMFCOutlookBarPane Sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md) nesnesi ve türetilmiş `CWnd`her nesne için benzersiz denetim titreleri kullanmalısınız.

Çalışma zamanında dinamik olarak yeni sayfalar eklemek veya silmek için [CMFCOutlookBar'ı kullanın::CreateCustomPage](#createcustompage) ve [CMFCOutlookBar::RemoveCustomPage](#removecustompage).

## <a name="outlook-2003-mode"></a>Outlook 2003 Modu

Outlook 2003 modunda, sekme düğmeleri Outlook çubuğu bölmesinin alt kısmında konumlandırılır. Düğmeleri görüntülemek için yeterli alan olmadığında, bölmenin alt kısmında araç çubuğu nabenzer bir alanda simge olarak görüntülenirler.

Outlook 2003 modunu etkinleştirmek için [CMFCOutlookBar::SetMode2003'u](#setmode2003) kullanın. Outlook çubuğunun alt kısmında görüntülenen simgeleri içeren bit eşlemeyi ayarlamak için [CMFCOutlookBarTabCtrl::SetToolbarImageList'i](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) kullanın. Bit eşlemindeki simgeler sekme dizini tarafından sıralanmalıdır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[Cpane](../../mfc/reference/cpane-class.md)

[Cdockablepane](../../mfc/reference/cdockablepane-class.md)

[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)

[Cmfcoutlookbar](../../mfc/reference/cmfcoutlookbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxoutlookbar.h

## <a name="cmfcoutlookbarallowdestroyemptytabbedpane"></a><a name="allowdestroyemptytabbedpane"></a>CMFCOutlookBar::AllowDestroyEmptyTabbedPane

Boş sekmeli bölmenin yok edilip edilmeyeceğini belirtir.

```cpp
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>Dönüş Değeri

Boş sekmeli bölme yok edilebiliyorsa DOĞRU; aksi takdirde, YANLIŞ. Varsayılan uygulama her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Boş sekmeli bölme yok edilemiyorsa, çerçeve bunun yerine gizler.

## <a name="cmfcoutlookbarcanacceptpane"></a><a name="canacceptpane"></a>CMFCOutlookBar::CanAcceptPane

Başka bir bölmenin Outlook çubuğubölmesine sabitlenip yapıştırılamayacağını belirler.

```cpp
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[içinde] Bu bölmeye kenetlenen başka bir bölmeye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başka bir bölme Outlook çubuğu bölmesine sabitlenebilirse DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Outlook çubuğu Outlook 2003 modundaysa, yerleştirme desteklenmez, bu nedenle iade değeri FALSE'dur.

*pBar* parametresi NULL ise, bu yöntem FALSE döndürür.

Aksi takdirde, bu yöntem temel yöntem [CBasePane gibi olur::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane), docking etkin olmasa bile, bir Outlook çubuğu hala üzerinde docked başka bir Outlook çubuğu etkinleştirebilirsiniz dışında.

## <a name="cmfcoutlookbarcansetcaptiontexttotabname"></a><a name="cansetcaptiontexttotabname"></a>CMFCOutlookBar::CanSetCaptionTexttotabname

Sekmeli bölmenin alt yazısının etkin sekmeyle aynı metni gösterip görüntülemediğini belirler.

```cpp
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Outlook çubuğu pencere başlığı etkin sekmenin metnine otomatik olarak ayarlanırsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu işlevselliği etkinleştirmek veya devre dışı katmak için [CBaseTabbedPane::EnableSetCaptionTextToTabName'yi](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) kullanın.

Outlook 2003 modunda, bu ayar her zaman etkinleştirilir.

## <a name="cmfcoutlookbarcreate"></a><a name="create"></a>CMFCOutlookBar::Oluştur

Outlook çubuğu denetimini oluşturur.

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
[içinde] Pencere başlığını belirtir.

*pParentWnd*<br/>
[içinde] Bir üst pencereiçin işaretçi belirtir. NULL olmamalıdır.

*Rect*<br/>
[içinde] Outlook çubuğuboyutunu ve konumunu piksellerde belirtir.

*Nıd*<br/>
[içinde] Denetim kimliğini belirtir. Uygulamada kullanılan diğer denetim lid'lerinden farklı olmalıdır.

*Dwstyle*<br/>
[içinde] İstenilen kontrol çubuğu stilini belirtir. Olası değerler için [Bkz. Pencere Stilleri.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

*dwControlBarStyle*<br/>
[içinde] Özel kitaplık tanımlı stilleri belirtir.

*Pcontext*<br/>
[içinde] Bağlam oluşturun.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CMFCOutlookBar` iki adımda inşa ee. Önce oluşturucuyu çağırın, `Create`sonra outlook çubuğu denetimini oluşturan ve `CMFCOutlookBar` nesneye iliştiren , çağırın.

Bkz. [CBasePane::DwControlBarStyle](../../mfc/reference/cbasepane-class.md#createex) tarafından belirtilecek kullanılabilir kitaplık tanımlı stillerin listesi için CreateEx. *dwControlBarStyle*

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın yönteminin `Create` nasıl `CMFCOutlookBar` kullanılacağını göstermektedir. Bu kod parçacığı Outlook Çok [Görünümler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_OutlookMultiViews#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]

## <a name="cmfcoutlookbarcreatecustompage"></a><a name="createcustompage"></a>CMFCOutlookBar::CreateCustomPage

Özel bir Outlook çubuğu sekmesi oluşturur.

```cpp
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,
    BOOL bActivatePage=TRUE,
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,
    BOOL bEnableTextLabels=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszPageName*<br/>
[içinde] Sayfa etiketi.

*bActivatePage*<br/>
[içinde] TRUE ise, sayfa oluşturma üzerine etkin hale gelir.

*dwEnabledYerleştirme*<br/>
[içinde] Sayfa ayrıldığında etkin kenetlenme taraflarını belirten CBRS_ALIGN_ bayraklarının birleşimi.

*bEnableTextLabels*<br/>
[içinde] TRUE ise, sayfada yer alan düğmeler için metin etiketleri etkinleştirilir.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan sayfaya işaretçi veya oluşturma başarısız olduysa NULL.

### <a name="remarks"></a>Açıklamalar

Kullanıcıların özel Outlook çubuğu sayfaları oluşturmasını sağlamak için bu yöntemi kullanın. Uygulama başına en fazla 100 sayfa oluşturabilirsiniz. Sayfa denetimi tüna'ları 0xF000'den başlar. Özel Outlook çubuğu sayfalarının toplam sayısı 100'ü aşarsa oluşturma başarısız olur.

Özel sayfaları silmek için [CMFCOutlookBar::RemoveCustomPage'i](#removecustompage) kullanın.

## <a name="cmfcoutlookbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CMFCOutlookBar::DoesAllowDynInsertBefore

Bir kullanıcının outlook çubuğunun dış kenarına bir bölme yiyep yapıştıramayacağını belirtir.

```
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Çerçeve, dinamik `DoesAllowDynInsertBefore` bir bölmeyi yapıştıracak bir konum aradığında yöntemi çağırır. İşlev FALSE döndürürse, çerçeve bölmenin dış kenarlarında herhangi bir dinamik bölmenin yerleştirmesine izin vermez.

Genellikle, sabit kayan olmayan denetim olarak bir Outlook çubuğu oluşturursunuz. Türetilmiş bir sınıfta bu işlevi geçersiz kılmak ve bu davranışı değiştirmek için TRUE döndürebilirsiniz.

> [!NOTE]
> Dinamik bölmeler kenetlenme yaparken sabitlenmiş statik bölmelerin durumunu denetlediğinden, mümkün olduğunca statik bölmelerden sonra dinamik bölmeleri yerleştirmeniz gerekir.

## <a name="cmfcoutlookbarfloattab"></a><a name="floattab"></a>CMFCOutlookBar::FloatTab

Bir bölmeyüzer.

```cpp
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[içinde] Kaydırmak için bölmeye bir işaretçi.

*nTabID*<br/>
[içinde] Float için sekme sıfır tabanlı dizin.

*dockMethod*<br/>
[içinde] Bölmeyi float yapmak için kullanılacak yöntemi belirtir.  Daha fazla bilgi için [Bkz. CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).

*bHide*<br/>
[içinde] Doğru yüzen önce bölmeyi gizlemek için; aksi takdirde, YANLIŞ. Bu yöntemin taban sınıf sürümünün aksine, bu parametrenin varsayılan bir değeri yoktur.

### <a name="return-value"></a>Dönüş Değeri

Bölme yüzdürse DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CBaseTabbedPane gibi::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab) dışında bir Outlook çubuğu denetiminde kalan son sekmeyi float için etkinleştirmez.

## <a name="cmfcoutlookbargetbuttonsfont"></a><a name="getbuttonsfont"></a>CMFCOutlookBar::GetButtonsFont

Outlook çubuğunun sayfa düğmesi sekmelerinde metnin yazı tipini döndürür.

```cpp
CFont* GetButtonsFont() const;
```

### <a name="return-value"></a>Dönüş Değeri

Outlook çubuğu sayfa düğme sekmelerinde metni görüntülemek için kullanılan yazı tipi nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Outlook sayfa düğmesi sekmelerinde metni görüntülemek için kullanılan yazı tipini almak için bu işlevi kullanın. CMFCOutlookBar'ı arayarak yazı tipini [ayarlayabilirsiniz::SetButtonsFont](#setbuttonsfont).

## <a name="cmfcoutlookbargettabarea"></a><a name="gettabarea"></a>CMFCOutlookBar::GetTabArea

Outlook çubuğundaki sekme alanlarının boyutunu ve konumunu belirler.

```cpp
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>Parametreler

*rectTabAreaTop*<br/>
[çıkış] İşlev döndüğünde üst sekme alanının boyutunu ve konumunu (istemci koordinatlarında) içerir.

*rectTabAreaBottom*<br/>
[çıkış] İşlev döndüğünde alt sekme alanının boyutunu ve konumunu (istemci koordinatlarında) içerir.

### <a name="remarks"></a>Açıklamalar

Çerçeve, hedef bölmeye yerleştirme türünü belirlemek için bu yöntemi çağırır. Çerçeve, kullanıcının hedef bölmenin sekme alanı üzerinde sabitlenecek bölmeyi sürüklediğini belirlediğinde, hedef bölmenin yeni bir sekmesi olarak ilk bölmeyi eklemeye çalışır. Aksi takdirde, ilk bölmeyi hedef bölmenin uygun bir tarafına yerleştirmeye çalışır. Çerçeve, ek kenetlenmiş bölmeyi yerleştirmek için kaydırıcılı yeni bir kapsayıcı oluşturur.

Outlook çubuğu `GetTabArea` statikse Outlook çubuğunun tüm istemci alanını döndürür; diğer bir de, Outlook çubuğu yüzdüremiyorsa. Aksi takdirde, sayfa düğmelerinin Outlook çubuğu denetiminin üst ve alt kısmından ayırdığı alanı döndürür.

Bu davranışı değiştirmek `CMFCOutlookBar` için türetilen sınıfta bu yöntemi geçersiz kılmak.

## <a name="cmfcoutlookbarismode2003"></a><a name="ismode2003"></a>CMFCOutlookBar::IsMode2003

Outlook çubuğunun davranışının Microsoft Office Outlook 2003'ün davranışını taklit edip etmediğini belirtir.

```cpp
BOOL IsMode2003() const;
```

### <a name="return-value"></a>Dönüş Değeri

Outlook çubuğu Microsoft Office 2003 modunda çalışıyorsa sıfır aveya değildir; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[CmFCOutlookBar::SetMode2003'ün](#setmode2003)isini kullanarak bu modu etkinleştirebilirsiniz.

## <a name="cmfcoutlookbaronafteranimation"></a><a name="onafteranimation"></a>CMFCOutlookBar::OnafterAnimation

[CMFCOutlookBarTabCtrl tarafından çağrılan::Etkin](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) sekme animasyon kullanılarak ayarlandıktan sonra SetActiveTab.

```cpp
virtual void OnAfterAnimation(int nPage);
```

### <a name="parameters"></a>Parametreler

*nPage*<br/>
[içinde] Etkin hale getirilmiş sekme sayfasının sıfır tabanlı dizin.

### <a name="remarks"></a>Açıklamalar

Etkin sekmeyi ayarlamanın görsel etkisi animasyonu etkinleştirip etkinleştirmediğinize bağlıdır. Daha fazla bilgi için [cmfcOutlookBarTabCtrl::EnableAnimation'a](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation)bakın.

## <a name="cmfcoutlookbaronbeforeanimation"></a><a name="onbeforeanimation"></a>CMFCOutlookBar::OnBeforeAnimasyon

[CMFCOutlookBarTabCtrl tarafından çağrılan::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) önce bir sekme sayfası animasyon kullanarak etkin sekme olarak ayarlanır.

```cpp
virtual BOOL OnBeforeAnimation(int nPage);
```

### <a name="parameters"></a>Parametreler

*nPage*<br/>
[içinde] Etkin olarak ayarlanacak sekme sayfasının sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Yeni etkin sekmeyi ayarlarken animasyon kullanılıyorsa TRUE'yu döndürür veya animasyon devre dışı bırakılırsa FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcoutlookbaronscroll"></a><a name="onscroll"></a>CMFCOutlookBar::OnScroll

Outlook çubuğu yukarı veya aşağı kaydırılıyorsa çerçeve tarafından çağrılır.

```cpp
virtual void OnScroll(BOOL bDown);
```

### <a name="parameters"></a>Parametreler

*bDown*<br/>
[içinde] Outlook çubuğu aşağı kaydırıyorsa DOĞRU veya yukarı doğru kaydırıyorsa FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcoutlookbarremovecustompage"></a><a name="removecustompage"></a>CMFCOutlookBar::RemoveCustomPage

Özel Outlook çubuğu sekmesi sayfasını kaldırır.

```cpp
BOOL RemoveCustomPage(
    UINT uiPage,
    CMFCOutlookBarTabCtrl* pTargetWnd);
```

### <a name="parameters"></a>Parametreler

*uiPage*<br/>
[içinde] Üst Outlook penceresindesayfanın sıfır tabanlı dizin.

*pTargetWnd*<br/>
[içinde] Üst Outlook penceresini işareteder.

### <a name="return-value"></a>Dönüş Değeri

Özel sayfa başarıyla kaldırıldıysa sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Özel sayfaları silmek için bu işlevi arayın. Sayfa kaldırıldığında denetim kimliği kullanılabilir kimlikhavuzuna döndürülür.

Kaldırılacak sayfanın şu anda bulunduğu [CMFCOutlookBTabCtrl Sınıf](../../mfc/reference/cmfcoutlookbartabctrl-class.md) nesnesine bir işaretçi sağlamanız gerekir. Bir kullanıcının farklı Outlook çubukları arasında ayrılabilir sayfaları taşıyabileceğini, ancak özel bir sayfayla ilgili bilgilerin CMFCOutlookBar adını vermiş olduğunuz Outlook çubuğu nesnesinde bulunduğunu [unutmayın::CreateCustomPage](#createcustompage).

Outlook penceresine bir işaretçi almak için [CBaseTabbedPane::GetUnderlyingWindow'u](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) kullanın.

## <a name="cmfcoutlookbarsetbuttonsfont"></a><a name="setbuttonsfont"></a>CMFCOutlookBar::SetButtonsFont

Outlook çubuğunun düğmelerinde metnin yazı tipini ayarlar.

```cpp
void SetButtonsFont(
    CFont* pFont,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
[içinde] Yeni yazı tipini belirtir.

*bRedraw*<br/>
[içinde] TRUE ise, Outlook çubuğu yeniden çizilir.

### <a name="remarks"></a>Açıklamalar

Outlook sekmesi sayfa düğmelerinde görüntülenen metin için yazı tipi ayarlamak için bu yöntemi kullanın.

## <a name="cmfcoutlookbarsetmode2003"></a><a name="setmode2003"></a>CMFCOutlookBar::SetMode2003

Outlook çubuğunun davranışının Outlook 2003'ün davranışını taklit edip etmediğini belirtir.

```cpp
void SetMode2003(BOOL bMode2003=TRUE);
```

### <a name="parameters"></a>Parametreler

*bMode2003*<br/>
[içinde] TRUE ise, Office 2003 modu etkinleştirilir.

### <a name="remarks"></a>Açıklamalar

Office 2003 modunu etkinleştirmek veya devre dışı kalmak için bu işlevi kullanın. Bu modda, Outlook çubuğunda özelleştirme düğmesi içeren ek bir araç çubuğu vardır. Outlook çubuğunun davranışı, Microsoft Office 2003'teki Outlook çubuğunun davranışına uygundur.

Varsayılan olarak, bu mod devre dışı bırakılır.

> [!NOTE]
> Bu işlev [CMFCOutlookBar](#create)önce çağrılmalıdır::Oluştur .

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CBaseTabbedPane Sınıfı](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[CMFCOutlookBarTabCtrl Sınıfı](../../mfc/reference/cmfcoutlookbartabctrl-class.md)<br/>
[CMFCOutlookBarPane Sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md)
