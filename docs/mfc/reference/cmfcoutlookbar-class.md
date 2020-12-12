---
description: 'Daha fazla bilgi edinin: CMFCOutlookBar sınıfı'
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
ms.openlocfilehash: e54e44e702aaf8d6883ada6be9c127f63ecee97d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265044"
---
# <a name="cmfcoutlookbar-class"></a>CMFCOutlookBar sınıfı

Microsoft Outlook 2000 veya Outlook 2003 ' deki **Gezinti bölmesinin** görsel görünüşünün bulunduğu sekmeli bir bölme. `CMFCOutlookBar`Nesne bir [CMFCOutlookBarTabCtrl sınıfı](../../mfc/reference/cmfcoutlookbartabctrl-class.md) nesnesi ve bir dizi sekme içerir. Sekmeler [CMFCOutlookBarPane sınıf](../../mfc/reference/cmfcoutlookbarpane-class.md) nesneleri ya da `CWnd` türetilmiş nesneler olabilir. Kullanıcıya Outlook çubuğu, bir dizi düğme ve bir görüntüleme alanı olarak görünür. Kullanıcı bir düğmeye tıkladığında, ilgili denetim veya düğme bölmesi görüntülenir.

## <a name="syntax"></a>Syntax

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
|[CMFCOutlookBar:: AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Boş bir sekmeli bölmenin yok edilip edilmeyeceğini belirtir. ( [CBaseTabbedPane:: AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|
|[CMFCOutlookBar:: CanAcceptPane](#canacceptpane)|Başka bir bölmenin Outlook çubuğu bölmesine yerleştirilip yerleştirilmeyeceğini belirler. (CDockablePane:: CanAcceptPane ' i geçersiz kılar.)|
|[CMFCOutlookBar:: CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Sekmeli bölme başlığının etkin sekme ile aynı metni görüntüleyip görüntülemediğini belirler. ( [CBaseTabbedPane:: CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname)geçersiz kılar.)|
|[CMFCOutlookBar:: Create](#create)|Outlook çubuğu denetimini oluşturur.|
|[CMFCOutlookBar:: CreateCustomPage](#createcustompage)|Özel bir Outlook Çubuğu sekmesi oluşturur.|
|`CMFCOutlookBar::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|[CMFCOutlookBar::D Oesallowdynınsertbefore](#doesallowdyninsertbefore)|Kullanıcının Outlook çubuğunun dış kenarında bir denetim çubuğunu sabitleyebilir olup olmayacağını belirler.|
|[CMFCOutlookBar:: FloatTab](#floattab)|Bir bölmeyi, ancak yalnızca bölme şu anda çıkarılabilir bir sekmede bulunuyorsa kayar. ( [CBaseTabbedPane:: FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab)geçersiz kılar.)|
|[CMFCOutlookBar:: GetButtonsFont](#getbuttonsfont)|Outlook çubuğu düğmelerindeki metnin yazı tipini döndürür.|
|[CMFCOutlookBar:: GetTabArea](#gettabarea)|Outlook çubuğundaki sekme alanlarının boyutunu ve konumunu döndürür. ( [CBaseTabbedPane:: GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea)öğesini geçersiz kılar.)|
|`CMFCOutlookBar::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCOutlookBar:: IsMode2003](#ismode2003)|Outlook çubuğu 'nun davranışının Outlook 2003 Microsoft Office (bkz. notlar) taklit edilip edilmeyeceğini belirler.|
|[CMFCOutlookBar:: OnAfterAnimation](#onafteranimation)|Etkin sekme animasyon kullanılarak ayarlandıktan sonra [CMFCOutlookBarTabCtrl:: SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) tarafından çağırılır.|
|[CMFCOutlookBar:: OnBeforeAnimation](#onbeforeanimation)|Bir sekme sayfası animasyon kullanılarak etkin sekme olarak ayarlanmadan önce [CMFCOutlookBarTabCtrl:: SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) tarafından çağırılır.|
|[CMFCOutlookBar:: OnScroll](#onscroll)|Outlook çubuğu kaydırılırken veya kapanıyorsa Framework tarafından çağırılır.|
|[CMFCOutlookBar:: RemoveCustomPage](#removecustompage)|Özel bir Outlook Çubuğu sekmesini kaldırır.|
|[CMFCOutlookBar:: SetButtonsFont](#setbuttonsfont)|Outlook çubuğu düğmelerindeki metnin yazı tipini ayarlar.|
|[CMFCOutlookBar:: SetMode2003](#setmode2003)|Outlook çubuğu davranışının Outlook 2003 (bkz. notlar) olarak taklit edilip edilmeyeceğini belirtir.|

## <a name="remarks"></a>Açıklamalar

Outlook çubuğu örneği için, bkz. [OutlookDemo örneği: MFC OutlookDemo uygulaması](../../overview/visual-cpp-samples.md).

## <a name="implementing-the-outlook-bar"></a>Outlook çubuğunu uygulama

`CMFCOutlookBar`Uygulamanızda denetimi kullanmak için şu adımları izleyin:

1. `CMFCOutlookBar`Ana çerçeve pencere sınıfına bir nesne ekleyin.

    ```cpp
    class CMainFrame : public CMDIFrameWnd
    {
        // ...
        CMFCOutlookBar m_wndOutlookBar;
        CMFCOutlookBarPane m_wndOutlookPane;
        // ...
    };
    ```

1. Ana çerçevede WM_CREATE iletisi işlenirken, Outlook çubuğu sekme denetimini oluşturmak için [CMFCOutlookBar:: Create](#create) metodunu çağırın.

    ```cpp
    m_wndOutlookBar.Create (_T("Shortcuts"),
        this,
        CRect (0, 0, 100, 100),
        ID_VIEW_OUTLOOKBAR,
        WS_CHILD | WS_VISIBLE | CBRS_LEFT);
    ```

1. `CMFCOutlookBarTabCtrl` [CBaseTabbedPane:: GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow)kullanarak temeldeki bir işaretçi elde edin.

    ```cpp
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();
    ```

1. Düğmeleri içeren her sekme için bir [CMFCOutlookBarPane sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md) nesnesi oluşturun.

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

1. Her yeni sekmeyi eklemek için [CMFCOutlookBarTabCtrl:: AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) komutunu çağırın. Sayfa çıkarılabilir olmayan *bir parametreyi hatalı* hale getirmek için yanlış olarak ayarlayın. Ya da, çıkarılabilir sayfalar eklemek için [CMFCOutlookBarTabCtrl:: AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) komutunu kullanın.

    ```cpp
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);
    ```

1. Bir `CWnd` sekme olarak türetilmiş bir denetim (örneğin, [Cmfcshelltreectclass](../../mfc/reference/cmfcshelltreectrl-class.md)) eklemek için denetim oluşturun ve [CMFCOutlookBarTabCtrl:: AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) komutunu çağırıp Outlook çubuğuna ekleyin.

> [!NOTE]
> Her [CMFCOutlookBarPane sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md) nesnesi ve her türetilmiş nesne için benzersiz Denetim kimlikleri kullanmanız gerekir `CWnd` .

Çalışma zamanında yeni sayfaları dinamik olarak eklemek veya silmek için [CMFCOutlookBar:: CreateCustomPage](#createcustompage) ve [CMFCOutlookBar:: RemoveCustomPage](#removecustompage)komutunu kullanın.

## <a name="outlook-2003-mode"></a>Outlook 2003 modu

Outlook 2003 modunda, sekme düğmeleri Outlook çubuğu bölmesinin en altında konumlandırılır. Düğmeleri göstermek için yeterli alan olmadığında, bölmenin alt tarafındaki bir araç çubuğu benzeri alanda simge olarak görüntülenir.

Outlook 2003 modunu etkinleştirmek için [CMFCOutlookBar:: SetMode2003](#setmode2003) kullanın. Outlook çubuğunun altında görüntülenen simgeleri içeren bit eşlemi ayarlamak için [CMFCOutlookBarTabCtrl:: SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) ' i kullanın. Bit eşlemdeki simgelerin sekme dizinine göre sıralanmış olması gerekir.

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

**Üstbilgi:** afxoutlookbar. h

## <a name="cmfcoutlookbarallowdestroyemptytabbedpane"></a><a name="allowdestroyemptytabbedpane"></a> CMFCOutlookBar:: AllowDestroyEmptyTabbedPane

Boş bir sekmeli bölmenin yok edilip edilmeyeceğini belirtir.

```cpp
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>Dönüş Değeri

Boş bir sekmeli bölme yok edilebiliyorsa TRUE; Aksi takdirde, FALSE. Varsayılan uygulama her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Boş bir sekmeli bölme yok edilemez, bunun yerine Framework onu gizler.

## <a name="cmfcoutlookbarcanacceptpane"></a><a name="canacceptpane"></a> CMFCOutlookBar:: CanAcceptPane

Başka bir bölmenin Outlook çubuğu bölmesine yerleştirilip yerleştirilmeyeceğini belirler.

```cpp
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
'ndaki Bu bölmeye yerleştirilmiş başka bir bölmeye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Outlook çubuğu bölmesine başka bir bölme sabitlenebilir ise doğru. Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Outlook çubuğu Outlook 2003 modundaysa, yerleştirme desteklenmez, bu nedenle dönüş değeri FALSE olur.

*PBar* parametresi null ise, bu yöntem false döndürür.

Aksi takdirde, bu yöntem, takma etkin olmasa bile bir Outlook çubuğu başka bir Outlook çubuğunun üzerine yerleştirilmeye olanak tanımak dışında, [CBasePane:: CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane)temel yöntemi olarak davranır.

## <a name="cmfcoutlookbarcansetcaptiontexttotabname"></a><a name="cansetcaptiontexttotabname"></a> CMFCOutlookBar:: CanSetCaptionTextToTabName

Sekmeli bölme başlığının etkin sekme ile aynı metni görüntüleyip görüntülemediğini belirler.

```cpp
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Outlook çubuğu pencere başlığı otomatik olarak etkin sekmenin metnine ayarlanmışsa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu işlevi etkinleştirmek veya devre dışı bırakmak için [CBaseTabbedPane:: EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) kullanın.

Outlook 2003 modunda, bu ayar her zaman etkindir.

## <a name="cmfcoutlookbarcreate"></a><a name="create"></a> CMFCOutlookBar:: Create

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
'ndaki Pencere başlığını belirtir.

*pParentWnd*<br/>
'ndaki Üst pencere için bir işaretçi belirtir. NULL olmaması gerekir.

*Rect*<br/>
'ndaki Outlook çubuğu boyutunu ve konumunu piksel cinsinden belirtir.

*NID*<br/>
'ndaki Denetim KIMLIĞINI belirtir. Uygulamada kullanılan diğer denetim kimliklerinden farklı olmalıdır.

*dwStyle*<br/>
'ndaki İstenen denetim çubuğu stilini belirtir. Olası değerler için bkz. [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*dwControlBarStyle*<br/>
'ndaki Özel kitaplık tanımlı stilleri belirtir.

*pContext*<br/>
'ndaki Bağlam oluştur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CMFCOutlookBar`İki adımda bir nesne oluşturursunuz. Önce oluşturucuyu çağırın ve sonra `Create` Outlook çubuğu denetimini oluşturan ve bunu nesnesine ekleyen çağırın `CMFCOutlookBar` .

*DwControlBarStyle* tarafından belirtiedilecek kullanılabilir kitaplık tanımlı stillerin listesi için bkz. [CBasePane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex) .

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının yönteminin nasıl kullanılacağını gösterir `Create` `CMFCOutlookBar` . Bu kod parçacığı [Outlook çok görünümleri örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_OutlookMultiViews#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]

## <a name="cmfcoutlookbarcreatecustompage"></a><a name="createcustompage"></a> CMFCOutlookBar:: CreateCustomPage

Özel bir Outlook Çubuğu sekmesi oluşturur.

```cpp
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,
    BOOL bActivatePage=TRUE,
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,
    BOOL bEnableTextLabels=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszPageName*<br/>
'ndaki Sayfa etiketi.

*bActivatePage*<br/>
'ndaki TRUE ise, sayfa oluşturma sonrasında etkin hale gelir.

*dwEnabledDocking*<br/>
'ndaki Sayfa ayrıldığında etkin sabitleme yüzlerini belirten CBRS_ALIGN_ bayraklarının birleşimi.

*bEnableTextLabels*<br/>
'ndaki TRUE ise, sayfada bulunan düğmeler için metin etiketleri etkinleştirilir.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan sayfanın işaretçisi veya oluşturma başarısız olduysa NULL.

### <a name="remarks"></a>Açıklamalar

Kullanıcıların özel Outlook çubuğu sayfaları oluşturmalarına olanak tanımak için bu yöntemi kullanın. Uygulama başına en fazla 100 sayfa oluşturabilirsiniz. Sayfa denetimi kimlikleri 0xF000 ' dan başlar. Özel Outlook çubuğu sayfalarının toplam sayısı 100 ' i aşarsa, oluşturma başarısız olur.

Özel sayfaları silmek için [CMFCOutlookBar:: RemoveCustomPage](#removecustompage) komutunu kullanın.

## <a name="cmfcoutlookbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a> CMFCOutlookBar::D Oesallowdynınsertbefore

Bir kullanıcının Outlook çubuğunun dış kenarında bölme yapıp yapamayacağını belirtir.

```
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama yanlış döndürür.

### <a name="remarks"></a>Açıklamalar

Framework, `DoesAllowDynInsertBefore` dinamik bir bölmeyi sabitlemek üzere bir konum ararken yöntemini çağırır. İşlev FALSE döndürürse, çerçeve bölmenin dış kenarlarındaki herhangi bir dinamik bölmenin yuvaya eklenmesine izin vermez.

Genellikle, statik kayan olmayan bir denetim olarak Outlook çubuğu oluşturursunuz. Bu işlevi türetilmiş bir sınıfta geçersiz kılabilir ve bu davranışı değiştirmek için TRUE değerini döndürün.

> [!NOTE]
> Dinamik bölmeler, yerleştirme sırasında yerleştirilmiş statik bölmeler durumunu denetlemediğinden, mümkün olduğunda statik bölmeleri dinamik bölmeleri sabitlemelidir.

## <a name="cmfcoutlookbarfloattab"></a><a name="floattab"></a> CMFCOutlookBar:: FloatTab

Bir bölmeyi kayın.

```cpp
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
'ndaki Kaydırma için bölmeye yönelik bir işaretçi.

*Ntabıd*<br/>
'ndaki Kayan sekmenin sıfır tabanlı dizini.

*Dockyöntemi*<br/>
'ndaki Bölmeyi yüzer hale getirmek için kullanılacak yöntemi belirtir.  Daha fazla bilgi için bkz. [CBaseTabbedPane:: FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).

*bHide*<br/>
'ndaki Kayan bölmeden gizlemek için TRUE; Aksi takdirde, FALSE. Bu yöntemin temel sınıf sürümünden farklı olarak, bu parametre varsayılan bir değere sahip değildir.

### <a name="return-value"></a>Dönüş Değeri

Bölme katalıyorsa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CBaseTabbedPane:: FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab) gibidir, ancak Outlook çubuğu denetimindeki son kalan sekmeyi float olarak etkinleştirmez.

## <a name="cmfcoutlookbargetbuttonsfont"></a><a name="getbuttonsfont"></a> CMFCOutlookBar:: GetButtonsFont

Outlook çubuğunun sayfa düğmesi sekmelerindeki metnin yazı tipini döndürür.

```cpp
CFont* GetButtonsFont() const;
```

### <a name="return-value"></a>Dönüş Değeri

Outlook çubuğu sayfası düğme sekmelerinde metin göstermek için kullanılan yazı tipi nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Outlook sayfa düğmesi sekmelerinde metni göstermek için kullanılan yazı tipini almak için bu işlevi kullanın. [CMFCOutlookBar:: SetButtonsFont](#setbuttonsfont)' de çağırarak yazı tipini ayarlayabilirsiniz.

## <a name="cmfcoutlookbargettabarea"></a><a name="gettabarea"></a> CMFCOutlookBar:: GetTabArea

Outlook çubuğu 'ndaki sekme alanlarının boyutunu ve konumunu belirler.

```cpp
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>Parametreler

*rectTabAreaTop*<br/>
dışı İşlevin döndürdüğü üst sekme alanının boyutunu ve konumunu (istemci koordinatlarındaki) içerir.

*rectTabAreaBottom*<br/>
dışı İşlev döndüğünde alt sekme alanının boyutunu ve konumunu (istemci koordinatlarındaki) içerir.

### <a name="remarks"></a>Açıklamalar

Framework, hedef bölmesine yerleştirme türünü belirlemekte bu yöntemi çağırır. Çerçeve, kullanıcının hedef bölmenin sekme alanı üzerine yerleştirilme bölmesini belirlediğinde, ilk bölmeyi hedef bölmenin yeni bir sekmesi olarak eklemeye çalışır. Aksi halde, hedef bölmenin uygun bir tarafında ilk bölmeyi yerleştirmeyi dener. Çerçeve, ek yerleşik bölmeye uyum sağlamak için kaydırıcıyla yeni bir kapsayıcı oluşturur.

Varsayılan uygulama, Outlook çubuğu `GetTabArea` statikse Outlook çubuğunun tüm istemci alanını döndürür; diğer bir deyişle, Outlook çubuğu de kayamaz. Aksi halde, sayfa düğmelerinin Outlook çubuğu denetiminin en üstünde ve altında aldığı alanı döndürür.

Bu davranışı değiştirmek için öğesinden türetilmiş sınıfta bu yöntemi geçersiz kılın `CMFCOutlookBar` .

## <a name="cmfcoutlookbarismode2003"></a><a name="ismode2003"></a> CMFCOutlookBar:: IsMode2003

Outlook çubuğu davranışının Outlook 2003 Microsoft Office taklit edilip edilmeyeceğini belirtir.

```cpp
BOOL IsMode2003() const;
```

### <a name="return-value"></a>Dönüş Değeri

Outlook Çubuğu Microsoft Office 2003 modunda çalışıyorsa sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu modu [CMFCOutlookBar:: SetMode2003](#setmode2003)kullanarak etkinleştirebilirsiniz.

## <a name="cmfcoutlookbaronafteranimation"></a><a name="onafteranimation"></a> CMFCOutlookBar:: OnAfterAnimation

Etkin sekme animasyon kullanılarak ayarlandıktan sonra [CMFCOutlookBarTabCtrl:: SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) tarafından çağırılır.

```cpp
virtual void OnAfterAnimation(int nPage);
```

### <a name="parameters"></a>Parametreler

*Nsayfa*<br/>
'ndaki Etkin hale getirilen sekme sayfasının sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Etkin sekmeyi ayarlamanın görsel etkisi, animasyonu etkinleştirdiğinize bağlıdır. Daha fazla bilgi için bkz. [CMFCOutlookBarTabCtrl:: EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation).

## <a name="cmfcoutlookbaronbeforeanimation"></a><a name="onbeforeanimation"></a> CMFCOutlookBar:: OnBeforeAnimation

Bir sekme sayfası animasyon kullanılarak etkin sekme olarak ayarlanmadan önce [CMFCOutlookBarTabCtrl:: SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) tarafından çağırılır.

```cpp
virtual BOOL OnBeforeAnimation(int nPage);
```

### <a name="parameters"></a>Parametreler

*Nsayfa*<br/>
'ndaki Etkin olarak ayarlanması gereken sekme sayfasının sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Animasyon yeni etkin sekmesini ayarlamakta kullanılacaksa TRUE, animasyonun devre dışı bırakılması gerekiyorsa FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcoutlookbaronscroll"></a><a name="onscroll"></a> CMFCOutlookBar:: OnScroll

Outlook çubuğu kaydırılırken veya kapanıyorsa Framework tarafından çağırılır.

```cpp
virtual void OnScroll(BOOL bDown);
```

### <a name="parameters"></a>Parametreler

*Aşağı doğru*<br/>
'ndaki Outlook çubuğu kaydırılırken TRUE, kaydırılırken FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcoutlookbarremovecustompage"></a><a name="removecustompage"></a> CMFCOutlookBar:: RemoveCustomPage

Özel bir Outlook çubuğu sekme sayfasını kaldırır.

```cpp
BOOL RemoveCustomPage(
    UINT uiPage,
    CMFCOutlookBarTabCtrl* pTargetWnd);
```

### <a name="parameters"></a>Parametreler

*Uıpage*<br/>
'ndaki Üst Outlook penceresinde sayfanın sıfır tabanlı dizini.

*pTargetWnd*<br/>
'ndaki Ana Outlook penceresine pointerto.

### <a name="return-value"></a>Dönüş Değeri

Özel sayfa başarıyla kaldırılmışsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Özel sayfaları silmek için bu işlevi çağırın. Sayfa kaldırıldığında denetim KIMLIĞI kullanılabilir kimlik havuzuna döndürülür.

Şu anda kaldırılacak sayfanın bulunduğu [CMFCOutlookBarTabCtrl sınıfı](../../mfc/reference/cmfcoutlookbartabctrl-class.md) nesnesine bir işaretçi sağlamanız gerekir. Kullanıcının çıkarılabilir sayfaları farklı Outlook çubukları arasında taşıyabileceğini unutmayın, ancak özel bir sayfayla ilgili bilgiler, [CMFCOutlookBar:: CreateCustomPage](#createcustompage)olarak adlandırdığı Outlook çubuğu nesnesinde yer alır.

Outlook penceresine bir işaretçi almak için [CBaseTabbedPane:: GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) kullanın.

## <a name="cmfcoutlookbarsetbuttonsfont"></a><a name="setbuttonsfont"></a> CMFCOutlookBar:: SetButtonsFont

Outlook çubuğu düğmelerindeki metnin yazı tipini ayarlar.

```cpp
void SetButtonsFont(
    CFont* pFont,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
'ndaki Yeni yazı tipini belirtir.

*bRedraw*<br/>
'ndaki TRUE ise Outlook çubuğu yeniden çizilir.

### <a name="remarks"></a>Açıklamalar

Outlook sekme sayfası düğmelerinde görüntülenecek metin için bir yazı tipi ayarlamak için bu yöntemi kullanın.

## <a name="cmfcoutlookbarsetmode2003"></a><a name="setmode2003"></a> CMFCOutlookBar:: SetMode2003

Outlook çubuğu davranışının Outlook 2003 ' un bu şekilde taklit edilip edilmeyeceğini belirtir.

```cpp
void SetMode2003(BOOL bMode2003=TRUE);
```

### <a name="parameters"></a>Parametreler

*bMode2003*<br/>
'ndaki DOĞRU ise, Office 2003 modu etkin olur.

### <a name="remarks"></a>Açıklamalar

Office 2003 modunu etkinleştirmek veya devre dışı bırakmak için bu işlevi kullanın. Bu modda, Outlook çubuğunun özelleştirme düğmesi olan ek bir araç çubuğu vardır. Outlook çubuğunun davranışı Microsoft Office 2003 ' deki Outlook çubuğunun davranışına uyar.

Bu mod varsayılan olarak devre dışıdır.

> [!NOTE]
> Bu işlevin [CMFCOutlookBar:: Create](#create)öğesinden önce çağrılması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CBaseTabbedPane sınıfı](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[CMFCOutlookBarTabCtrl sınıfı](../../mfc/reference/cmfcoutlookbartabctrl-class.md)<br/>
[CMFCOutlookBarPane sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md)
