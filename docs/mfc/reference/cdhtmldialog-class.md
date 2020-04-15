---
title: CDHtmlDialog Sınıfı
ms.date: 03/27/2019
f1_keywords:
- CDHtmlDialog
- AFXDHTML/CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CanAccessExternal
- AFXDHTML/CDHtmlDialog::CreateControlSite
- AFXDHTML/CDHtmlDialog::DDX_DHtml_AxControl
- AFXDHTML/CDHtmlDialog::DDX_DHtml_CheckBox
- AFXDHTML/CDHtmlDialog::DDX_DHtml_ElementText
- AFXDHTML/CDHtmlDialog::DDX_DHtml_Radio
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectIndex
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectString
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectValue
- AFXDHTML/CDHtmlDialog::DestroyModeless
- AFXDHTML/CDHtmlDialog::EnableModeless
- AFXDHTML/CDHtmlDialog::FilterDataObject
- AFXDHTML/CDHtmlDialog::GetControlDispatch
- AFXDHTML/CDHtmlDialog::GetControlProperty
- AFXDHTML/CDHtmlDialog::GetCurrentUrl
- AFXDHTML/CDHtmlDialog::GetDHtmlDocument
- AFXDHTML/CDHtmlDialog::GetDropTarget
- AFXDHTML/CDHtmlDialog::GetElement
- AFXDHTML/CDHtmlDialog::GetElementHtml
- AFXDHTML/CDHtmlDialog::GetElementInterface
- AFXDHTML/CDHtmlDialog::GetElementProperty
- AFXDHTML/CDHtmlDialog::GetElementText
- AFXDHTML/CDHtmlDialog::GetEvent
- AFXDHTML/CDHtmlDialog::GetExternal
- AFXDHTML/CDHtmlDialog::GetHostInfo
- AFXDHTML/CDHtmlDialog::GetOptionKeyPath
- AFXDHTML/CDHtmlDialog::HideUI
- AFXDHTML/CDHtmlDialog::IsExternalDispatchSafe
- AFXDHTML/CDHtmlDialog::LoadFromResource
- AFXDHTML/CDHtmlDialog::Navigate
- AFXDHTML/CDHtmlDialog::OnBeforeNavigate
- AFXDHTML/CDHtmlDialog::OnDocumentComplete
- AFXDHTML/CDHtmlDialog::OnDocWindowActivate
- AFXDHTML/CDHtmlDialog::OnFrameWindowActivate
- AFXDHTML/CDHtmlDialog::OnInitDialog
- AFXDHTML/CDHtmlDialog::OnNavigateComplete
- AFXDHTML/CDHtmlDialog::ResizeBorder
- AFXDHTML/CDHtmlDialog::SetControlProperty
- AFXDHTML/CDHtmlDialog::SetElementHtml
- AFXDHTML/CDHtmlDialog::SetElementProperty
- AFXDHTML/CDHtmlDialog::SetElementText
- AFXDHTML/CDHtmlDialog::SetExternalDispatch
- AFXDHTML/CDHtmlDialog::SetHostFlags
- AFXDHTML/CDHtmlDialog::ShowContextMenu
- AFXDHTML/CDHtmlDialog::ShowUI
- AFXDHTML/CDHtmlDialog::TranslateAccelerator
- AFXDHTML/CDHtmlDialog::TranslateUrl
- AFXDHTML/CDHtmlDialog::UpdateUI
- AFXDHTML/CDHtmlDialog::m_bUseHtmlTitle
- AFXDHTML/CDHtmlDialog::m_nHtmlResID
- AFXDHTML/CDHtmlDialog::m_pBrowserApp
- AFXDHTML/CDHtmlDialog::m_spHtmlDoc
- AFXDHTML/CDHtmlDialog::m_strCurrentUrl
- AFXDHTML/CDHtmlDialog::m_szHtmlResID
helpviewer_keywords:
- CDHtmlDialog [MFC], CDHtmlDialog
- CDHtmlDialog [MFC], CanAccessExternal
- CDHtmlDialog [MFC], CreateControlSite
- CDHtmlDialog [MFC], DDX_DHtml_AxControl
- CDHtmlDialog [MFC], DDX_DHtml_CheckBox
- CDHtmlDialog [MFC], DDX_DHtml_ElementText
- CDHtmlDialog [MFC], DDX_DHtml_Radio
- CDHtmlDialog [MFC], DDX_DHtml_SelectIndex
- CDHtmlDialog [MFC], DDX_DHtml_SelectString
- CDHtmlDialog [MFC], DDX_DHtml_SelectValue
- CDHtmlDialog [MFC], DestroyModeless
- CDHtmlDialog [MFC], EnableModeless
- CDHtmlDialog [MFC], FilterDataObject
- CDHtmlDialog [MFC], GetControlDispatch
- CDHtmlDialog [MFC], GetControlProperty
- CDHtmlDialog [MFC], GetCurrentUrl
- CDHtmlDialog [MFC], GetDHtmlDocument
- CDHtmlDialog [MFC], GetDropTarget
- CDHtmlDialog [MFC], GetElement
- CDHtmlDialog [MFC], GetElementHtml
- CDHtmlDialog [MFC], GetElementInterface
- CDHtmlDialog [MFC], GetElementProperty
- CDHtmlDialog [MFC], GetElementText
- CDHtmlDialog [MFC], GetEvent
- CDHtmlDialog [MFC], GetExternal
- CDHtmlDialog [MFC], GetHostInfo
- CDHtmlDialog [MFC], GetOptionKeyPath
- CDHtmlDialog [MFC], HideUI
- CDHtmlDialog [MFC], IsExternalDispatchSafe
- CDHtmlDialog [MFC], LoadFromResource
- CDHtmlDialog [MFC], Navigate
- CDHtmlDialog [MFC], OnBeforeNavigate
- CDHtmlDialog [MFC], OnDocumentComplete
- CDHtmlDialog [MFC], OnDocWindowActivate
- CDHtmlDialog [MFC], OnFrameWindowActivate
- CDHtmlDialog [MFC], OnInitDialog
- CDHtmlDialog [MFC], OnNavigateComplete
- CDHtmlDialog [MFC], ResizeBorder
- CDHtmlDialog [MFC], SetControlProperty
- CDHtmlDialog [MFC], SetElementHtml
- CDHtmlDialog [MFC], SetElementProperty
- CDHtmlDialog [MFC], SetElementText
- CDHtmlDialog [MFC], SetExternalDispatch
- CDHtmlDialog [MFC], SetHostFlags
- CDHtmlDialog [MFC], ShowContextMenu
- CDHtmlDialog [MFC], ShowUI
- CDHtmlDialog [MFC], TranslateAccelerator
- CDHtmlDialog [MFC], TranslateUrl
- CDHtmlDialog [MFC], UpdateUI
- CDHtmlDialog [MFC], m_bUseHtmlTitle
- CDHtmlDialog [MFC], m_nHtmlResID
- CDHtmlDialog [MFC], m_pBrowserApp
- CDHtmlDialog [MFC], m_spHtmlDoc
- CDHtmlDialog [MFC], m_strCurrentUrl
- CDHtmlDialog [MFC], m_szHtmlResID
ms.assetid: 3f941c85-87e1-4f0f-9cc5-ffee8498b312
ms.openlocfilehash: 57ea8f3a1dbbce4fcfa350bd99e4ee628e9675c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375681"
---
# <a name="cdhtmldialog-class"></a>CDHtmlDialog Sınıfı

Kullanıcı arabirimini uygulamak için iletişim kaynakları yerine HTML kullanan iletişim kutuları oluşturmak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class CDHtmlDialog : public CDialog, public CDHtmlEventSink
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDHtmlDialog::CDHtmlDialog](#cdhtmldialog)|BIR CDHtmlDialog nesnesi oluşturuyor.|
|[CDHtmlDialog::~CDHtmlDialog](#_dtorcdhtmldialog)|BIR CDHtmlDialog nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDHtmlDialog::CanAccessExternal](#canaccessexternal)|Yüklenen sayfadaki komut dosyası nesnelerinin denetim sitesinin dış gönderime erişip erişemeyeceğini görmek için erişim denetimi olarak adlandırılan geçersiz kılınabilir. Göndermenin komut dosyası oluşturma için güvenli olduğundan veya geçerli bölgenin komut dosyası oluşturma için güvenli olmayan nesnelere izin verdiğinden emin olmak için denetler.|
|[CDHtmlDialog::CreateControlSite](#createcontrolsite)|İletişim kutusunda WebBrowser denetimini barındırmak için bir denetim sitesi örneği oluşturmak için kullanılan overridable.|
|[CDHtmlDialog::DDX_DHtml_AxControl](#ddx_dhtml_axcontrol)|Bir üye değişkeni ile HTML sayfasındaki ActiveX denetiminin özellik değeri arasında veri alışverişi.|
|[CDHtmlDialog::DDX_DHtml_CheckBox](#ddx_dhtml_checkbox)|Html sayfasındaki bir üye değişkeni ile onay kutusu arasında veri alışverişi.|
|[CDHtmlDialog::DDX_DHtml_ElementText](#ddx_dhtml_elementtext)|Bir ÜYE değişkeni ile HTML sayfasındaki herhangi bir HTML öğesi arasında veri alışverişi.|
|[CDHtmlDialog::DDX_DHtml_Radio](#ddx_dhtml_radio)|Html sayfasındaki bir üye değişkeni ile radyo düğmesi arasında veri alışverişi.|
|[CDHtmlDialog::DDX_DHtml_SelectIndex](#ddx_dhtml_selectindex)|HTML sayfasındaki liste kutusunun dizinini alır veya ayarlar.|
|[CDHtmlDialog::DDX_DHtml_SelectString](#ddx_dhtml_selectstring)|Bir HTML sayfasındabir liste kutusu girişinin ekran metnini alır veya ayarlar (geçerli dizine göre).|
|[CDHtmlDialog::DDX_DHtml_SelectValue](#ddx_dhtml_selectvalue)|Bir HTML sayfasındaki liste kutusu girişinin (geçerli dizine göre) değerini alır veya ayarlar.|
|[CDHtmlDialog::DestroyModeless](#destroymodeless)|Modeless iletişim kutusunu yok eder.|
|[CDHtmlDialog::EnableModeless](#enablemodeless)|Modeless iletişim kutularını etkinleştirin.|
|[CDHtmlDialog::FilterDataObject](#filterdataobject)|İletişim kutusunun barındırılan tarayıcı tarafından oluşturulan veri nesnelerine filtre filtresi yapmasına izin verir.|
|[CDHtmlDialog::GetControlDispatch](#getcontroldispatch)|HTML belgesine `IDispatch` katıştırılmış bir ActiveX denetimindeki arabirimi alır.|
|[CDHtmlDialog::GetControlProperty](#getcontrolproperty)|Belirtilen ActiveX denetiminin istenen özelliğini alır.|
|[CDHtmlDialog::GetCurrentUrl](#getcurrenturl)|Geçerli belgeyle ilişkili Tek düzen Kaynak Bulucu'yu (URL) alır.|
|[CDHtmlDialog::GetDHtmlDocument](#getdhtmldocument)|Şu anda yüklenen HTML belgesindeki IHTMLDocument2 arabirimini alır.|
|[CDHtmlDialog::GetDropTarget](#getdroptarget)|Bu iletişim alternatif bir [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget)sağlamak için izin vermek için bir bırakma hedefi olarak kullanıldığında içerdiği WebBrowser denetimi tarafından çağrılır.|
|[CDHtmlDialog::GetElement](#getelement)|BIR HTML öğesi üzerinde bir arabirim alır.|
|[CDHtmlDialog::GetElementHtml](#getelementhtml)|Bir HTML `innerHTML` öğesinin özelliğini alır.|
|[CDHtmlDialog::GetElementInterface](#getelementinterface)|İstenen arabirim işaretçisini bir HTML öğesinden alır.|
|[CDHtmlDialog::GetElementProperty](#getelementproperty)|BIR HTML öğesinin özelliğinin değerini alır.|
|[CDHtmlDialog::GetElementText](#getelementtext)|Bir HTML `innerText` öğesinin özelliğini alır.|
|[CDHtmlDialog::GetEvent](#getevent)|İşaretçiyi `IHTMLEventObj` geçerli olay nesnesine alır.|
|[CDHtmlDialog::GetExternal](#getexternal)|Ev sahibinin `IDispatch` arabirimini alır.|
|[CDHtmlDialog::GetHostInfo](#gethostinfo)|Ana bilgisayardaki web cisme yeteneklerini alır.|
|[CDHtmlDialog::GetOptionKeyPath](#getoptionkeypath)|Kullanıcı tercihlerinin depolandığı kayıt defteri anahtarını alır.|
|[CDHtmlDialog::HideUI](#hideui)|Ev sahibinin ui'sini gizler.|
|[CDHtmlDialog::IsExternalDispatchSafe](#isexternaldispatchsafe)|Ana bilgisayar `IDispatch` arabiriminin komut dosyası için güvenli olup olmadığını gösterir.|
|[CDHtmlDialog::LoadFromResource](#loadfromresource)|Belirtilen kaynağı WebBrowser denetimine yükler.|
|[CDHtmlDialog::Gezinme](#navigate)|Belirtilen URL'ye yönlendirilir.|
|[CDHtmlDialog::OnBeforeGezinme](#onbeforenavigate)|Bir navigasyon olayı ateşedilmeden önce çerçeve tarafından çağrılır.|
|[CDHtmlDialog::OnDocumentComplete](#ondocumentcomplete)|Bir belge READYSTATE_COMPLETE durumuna ulaştığında bir uygulamayı bildirmek için çerçeve tarafından çağrılır.|
|[CDHtmlDialog::OnDocWindowEtkinleştir](#ondocwindowactivate)|Belge penceresi etkinleştirildiğinde veya devre dışı bırakıldığında çerçeve tarafından çağrılır.|
|[CDHtmlDialog::OnFrameWindowEtkinleştir](#onframewindowactivate)|Çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında çerçeve tarafından çağrılır.|
|[CDHtmlDialog::OnInitDialog](#oninitdialog)|WM_INITDIALOG iletisine yanıt olarak çağrıldı.|
|[CDHtmlDialog::OnNavigateComplete](#onnavigatecomplete)|Bir gezinti olayı tamamlandıktan sonra çerçeve tarafından çağrılır.|
|[CDHtmlDialog::ResizeBorder](#resizeborder)|Kenarlık alanını yeniden boyutlandırmak için gereken nesneyi uyarır.|
|[CDHtmlDialog::SetControlProperty](#setcontrolproperty)|ActiveX denetiminin özelliğini yeni bir değere ayarlar.|
|[CDHtmlDialog::SetElementHtml](#setelementhtml)|BIR `innerHTML` HTML öğesinin özelliğini ayarlar.|
|[CDHtmlDialog::SetElementÖzellik](#setelementproperty)|BIR HTML öğesinin özelliğini ayarlar.|
|[CDHtmlDialog::SetElementText](#setelementtext)|BIR `innerText` HTML öğesinin özelliğini ayarlar.|
|[CDHtmlDialog::SetExternalDispatch](#setexternaldispatch)|Ana bilgisayar `IDispatch` arabirimini ayarlar.|
|[CDHtmlDialog::SetHostFlags](#sethostflags)|Ev sahibinin Web Telefonu bayraklarını ayarlar.|
|[CDHtmlDialog::ShowContextMenu](#showcontextmenu)|Bağlam menüsü görüntülenmek üzereyken çağrılır.|
|[CDHtmlDialog::ShowUI](#showui)|Ev sahibinin u-u-larını gösterir.|
|[CDHtmlDialog::TranslateAccelerator](#translateaccelerator)|Menü hızlandırıcı anahtar lı iletileri işlemek için çağrıldı.|
|[CDHtmlDialog::ÇeviriUrl](#translateurl)|Yüklenecek URL'yi değiştirmek için çağrıldı.|
|[CDHtmlDialog::UpdateUI](#updateui)|Komut durumunun değiştiğini ana bilgisayara bildirmek için çağrıldı.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDHtmlDialog::m_bUseHtmlTitle](#m_busehtmltitle)|HTML belgesinin başlığının iletişim başlığı olarak kullanılıp kullanılmayacağını gösterir.|
|[CDHtmlDialog::m_nHtmlResID](#m_nhtmlresid)|HTML kaynağının kaynak kimliği görüntülenecektir.|
|[CDHtmlDialog::m_pBrowserApp](#m_pbrowserapp)|Web tarayıcısı uygulamasıiçin bir işaretçi.|
|[CDHtmlDialog::m_spHtmlDoc](#m_sphtmldoc)|HTML belgesiiçin bir işaretçi.|
|[CDHtmlDialog::m_strCurrentUrl](#m_strcurrenturl)|Geçerli URL.|
|[CDHtmlDialog::m_szHtmlResID](#m_szhtmlresid)|HTML kaynak kimliğinin string sürümü.|

## <a name="remarks"></a>Açıklamalar

`CDHtmlDialog`HTML kaynağını veya URL'sini görüntülenecek şekilde yükleyebilir.

`CDHtmlDialog`html denetimleri ile veri alışverişi yapabilir ve düğme tıklamaları gibi HTML denetimlerinden olayları işleyebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CDHtmlSinkHandlerBase2`

`CDHtmlSinkHandlerBase1`

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

`CDHtmlSinkHandler`

[Cwnd](../../mfc/reference/cwnd-class.md)

`CDHtmlEventSink`

[Cdialog](../../mfc/reference/cdialog-class.md)

`CDHtmlDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdhtml.h

## <a name="ddx_dhtml-helper-macros"></a><a name="ddx_dhtml_helper_macros"></a>DDX_DHtml Yardımcı Makrolar

Yardımcı makroların DDX_DHtml, html sayfasında denetimlerin yaygın olarak kullanılan özelliklerine kolay erişim sağlar.

### <a name="data-exchange-macros"></a>Veri Değişim Makroları

|||
|-|-|
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|Seçili denetimden Değer özelliğini ayarlar veya alır.|
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|Geçerli öğenin başlangıç ve bitiş etiketleri arasındaki metni ayarlar veya alır.|
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|Geçerli öğenin başlangıç ve bitiş etiketleri arasındaki HTML'yi ayarlar veya alır.|
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|Hedef URL'yi veya bağlantı noktasını ayarlar veya alır.|
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|Hedef pencereyi veya çerçeveyi ayarlar veya alır.|
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|Belgedeki görüntünün veya video klibin adını ayarlar veya alır.|
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|İlişkili çerçevenin URL'sini ayarlar veya alır.|
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|İlişkili çerçevenin URL'sini ayarlar veya alır.|

## <a name="cdhtmldialogcanaccessexternal"></a><a name="canaccessexternal"></a>CDHtmlDialog::CanAccessExternal

Yüklenen sayfadaki komut dosyası nesnelerinin denetim sitesinin dış gönderime erişip erişemeyeceğini görmek için erişim denetimi olarak adlandırılan geçersiz kılınabilir. Göndermenin komut dosyası oluşturma için güvenli olduğundan veya geçerli bölgenin komut dosyası oluşturma için güvenli olmayan nesnelere izin verdiğinden emin olmak için denetler.

```
virtual BOOL CanAccessExternal();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

## <a name="cdhtmldialogcdhtmldialog"></a><a name="cdhtmldialog"></a>CDHtmlDialog::CDHtmlDialog

Kaynak tabanlı dinamik HTML iletişim kutusu oluşturur.

```
CDHtmlDialog();

CDHtmlDialog(
    LPCTSTR lpszTemplateName,
    LPCTSTR szHtmlResID,
    CWnd *pParentWnd = NULL);

CDHtmlDialog(
    UINT nIDTemplate,
    UINT nHtmlResID = 0,
    CWnd *pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszTemplateName*<br/>
İletişim kutusu şablon kaynağının adı olan null-sonlandırılan dize.

*szHtmlResID*<br/>
HTML kaynağının adı olan null-sonlandırılan dize.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip penceresi nesnesine [(CWnd](../../mfc/reference/cwnd-class.md)türünden) işaretçi. NULL ise, iletişim nesnesinin üst penceresi ana uygulama penceresine ayarlanır.

*nIDTemplate*<br/>
İletişim kutusu şablonkaynağının kimlik numarasını içerir.

*nHtmlResID*<br/>
BIR HTML kaynağının kimlik numarasını içerir.

### <a name="remarks"></a>Açıklamalar

Oluşturucunun ikinci biçimi, şablon adı üzerinden iletişim kaynağına erişim sağlar. Oluşturucunun üçüncü biçimi, kaynak şablonunun kimliği aracılığıyla iletişim kaynağına erişim sağlar. Genellikle, kimlik **IDD_** öneki ile başlar.

## <a name="cdhtmldialogcdhtmldialog"></a><a name="_dtorcdhtmldialog"></a>CDHtmlDialog::~CDHtmlDialog

BIR CDHtmlDialog nesnesini yok eder.

```
virtual ~CDHtmlDialog();
```

### <a name="remarks"></a>Açıklamalar

[CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) üye işlevi CDialog tarafından oluşturulan modsuz iletişim kutularını yok etmek için [kullanılmalıdır::Oluştur](../../mfc/reference/cdialog-class.md#create).

## <a name="cdhtmldialogcreatecontrolsite"></a><a name="createcontrolsite"></a>CDHtmlDialog::CreateControlSite

İletişim kutusunda WebBrowser denetimini barındırmak için bir denetim sitesi örneği oluşturmak için kullanılan overridable.

```
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,
    COleControlSite** ppSite,
    UINT /* nID */,
    REFCLSID /* clsid */);
```

### <a name="parameters"></a>Parametreler

*pKonteyner*<br/>
[COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md) nesnesine bir işaretçi

*ppSite*<br/>
[COleControlSite](../../mfc/reference/colecontrolsite-class.md)için bir işaretçi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kendi denetim sitesi sınıfınızın bir örneğini döndürmek için bu üye işlevini geçersiz kılabilirsiniz.

## <a name="cdhtmldialogddx_dhtml_axcontrol"></a><a name="ddx_dhtml_axcontrol"></a>CDHtmlDialog::DDX_DHtml_AxControl

Bir üye değişkeni ile HTML sayfasındaki ActiveX denetiminin özellik değeri arasında veri alışverişi.

```
void DDX_DHtml_AxControl(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    VARIANT& var);

void DDX_DHtml_AxControl(
    CDataExchange* pDX,
    LPCTSTR szId,
    LPCTSTR szPropName,
    VARIANT& var);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*szId*<br/>
ActiveX denetimi için HTML kaynağındaki nesne etiketinin kimlik parametresinin değeri.

*Dıspıd*<br/>
Veri alışverişi yapmak istediğiniz özelliğin sevk kimliği.

*szPropName*<br/>
Özelliğin adı.

*var*<br/>
ActiveX denetim özelliği ile değiştirilen değeri tutan tür VARIANT, [COleVariant](../../mfc/reference/colevariant-class.md)veya [CComVariant](../../atl/reference/ccomvariant-class.md)veri üyesi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCHtmlHttp#1](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_1.cpp)]

## <a name="cdhtmldialogddx_dhtml_checkbox"></a><a name="ddx_dhtml_checkbox"></a>CDHtmlDialog::DDX_DHtml_CheckBox

Html sayfasındaki bir üye değişkeni ile onay kutusu arasında veri alışverişi.

```
void DDX_DHtml_CheckBox(
    CDataExchange* pDX,
    LPCTSTR szId,
    int& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*szId*<br/>
HTML denetiminin kimlik parametresi için belirttiğiniz değer.

*Değer*<br/>
Değiştirilen değer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCHtmlHttp#2](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]

## <a name="cdhtmldialogddx_dhtml_elementtext"></a><a name="ddx_dhtml_elementtext"></a>CDHtmlDialog::DDX_DHtml_ElementText

Bir ÜYE değişkeni ile HTML sayfasındaki herhangi bir HTML öğesi arasında veri alışverişi.

```
void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    CString& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    short& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    int& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    long& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    DWORD& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    float& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    double& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*szId*<br/>
HTML denetiminin kimlik parametresi için belirttiğiniz değer.

*Dıspıd*<br/>
Veri alışverişi yapmak istediğiniz HTML öğesinin sevk kimliği.

*Değer*<br/>
Değiştirilen değer.

## <a name="cdhtmldialogddx_dhtml_radio"></a><a name="ddx_dhtml_radio"></a>CDHtmlDialog::DDX_DHtml_Radio

Html sayfasındaki bir üye değişkeni ile radyo düğmesi arasında veri alışverişi.

```
void DDX_DHtml_Radio(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*szId*<br/>
HTML denetiminin kimlik parametresi için belirttiğiniz değer.

*Değer*<br/>
Değiştirilen değer.

## <a name="cdhtmldialogddx_dhtml_selectindex"></a><a name="ddx_dhtml_selectindex"></a>CDHtmlDialog::DDX_DHtml_SelectIndex

HTML sayfasındaki liste kutusunun dizinini alır veya ayarlar.

```
void DDX_DHtml_SelectIndex(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*szId*<br/>
HTML denetiminin `id` parametresi için belirttiğiniz değer.

*Değer*<br/>
Değiştirilen değer.

## <a name="cdhtmldialogddx_dhtml_selectstring"></a><a name="ddx_dhtml_selectstring"></a>CDHtmlDialog::DDX_DHtml_SelectString

Bir HTML sayfasındabir liste kutusu girişinin ekran metnini alır veya ayarlar (geçerli dizine göre).

```
void DDX_DHtml_SelectString(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*szId*<br/>
HTML denetiminin kimlik parametresi için belirttiğiniz değer.

*Değer*<br/>
Değiştirilen değer.

## <a name="cdhtmldialogddx_dhtml_selectvalue"></a><a name="ddx_dhtml_selectvalue"></a>CDHtmlDialog::DDX_DHtml_SelectValue

Bir HTML sayfasındaki liste kutusu girişinin (geçerli dizine göre) değerini alır veya ayarlar.

```
void DDX_DHtml_SelectValue(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*Pdx*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine işaretçi.

*szId*<br/>
HTML denetiminin kimlik parametresi için belirttiğiniz değer.

*Değer*<br/>
Değiştirilen değer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCHtmlHttp#3](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]

## <a name="cdhtmldialogdestroymodeless"></a><a name="destroymodeless"></a>CDHtmlDialog::DestroyModeless

Modsuz bir iletişim kutusunu `CDHtmlDialog` nesneden ayırır ve nesneyi yok eder.

```
void DestroyModeless();
```

## <a name="cdhtmldialogenablemodeless"></a><a name="enablemodeless"></a>CDHtmlDialog::EnableModeless

Modeless iletişim kutularını etkinleştirin.

```
STDMETHOD(EnableModeless)(BOOL fEnable);
```

### <a name="parameters"></a>Parametreler

*fEtkinleştir*<br/>
Bkz. *fEnable* in [IDocHostUIHandler::EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\)) in Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, CDHtmlDialog'un [IDocHostUIHandler uygulamasıdır::EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\)), Windows SDK'da açıklandığı gibi.

## <a name="cdhtmldialogfilterdataobject"></a><a name="filterdataobject"></a>CDHtmlDialog::FilterDataObject

İletişim kutusunun barındırılan tarayıcı tarafından oluşturulan veri nesnelerine filtre filtresi yapmasına izin verir.

```
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,
    IDataObject** ppDORet);
```

### <a name="parameters"></a>Parametreler

*Pdo*<br/>
[Bkz. iDocHostUIHandler::FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\)) windows SDK içinde. *pDO*

*ppDORet*<br/>
Windows SDK'da `IDocHostUIHandler::FilterDataObject` *ppDORet'e* bakın.

### <a name="return-value"></a>Dönüş Değeri

S_FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, CDHtmlDialog'un Windows SDK'da açıklandığı gibi [IDocHostUIHandler::FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))uygulamasıdır.

## <a name="cdhtmldialoggetcontroldispatch"></a><a name="getcontroldispatch"></a>CDHtmlDialog::GetControlDispatch

`IDispatch` [GetDHtmlDocument](#getdhtmldocument)tarafından döndürülen HTML belgesine katıştırılmış activex denetimindeki arabirimi alır.

```
HRESULT GetControlDispatch(
    LPCTSTR szId,
    IDispatch** ppdisp);
```

### <a name="parameters"></a>Parametreler

*szId*<br/>
ActiveX denetiminin HTML kimliği.

*ppdisp*<br/>
Web `IDispatch` sayfasında bulunursa denetimin arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="cdhtmldialoggetcontrolproperty"></a><a name="getcontrolproperty"></a>CDHtmlDialog::GetControlProperty

Belirtilen ActiveX denetiminin istenen özelliğini alır.

```
VARIANT GetControlProperty(
    LPCTSTR szId,
    LPCTSTR szPropName);

VARIANT GetControlProperty(
    LPCTSTR szId,
    DISPID dispId);

VARIANT GetControlProperty(
    IDispatch* pdispControl,
    DISPID dispId);
```

### <a name="parameters"></a>Parametreler

*szId*<br/>
ActiveX denetiminin HTML kimliği.

*szPropName*<br/>
Geçerli kullanıcının varsayılan yerel alanında bir özelliğin adı.

*pdispKontrol*<br/>
ActiveX denetiminin `IDispatch` işaretçisi.

*Dıspıd*<br/>
Bir mülkün sevk kimliği.

### <a name="return-value"></a>Dönüş Değeri

Denetim veya özellik bulunamadıysa, istenen özelliği veya boş bir varyantı içeren bir varyant.

### <a name="remarks"></a>Açıklamalar

Aşırı yükler en az verimli en üstten en alttabakada en verimliye doğru listelenir.

## <a name="cdhtmldialoggetcurrenturl"></a><a name="getcurrenturl"></a>CDHtmlDialog::GetCurrentUrl

Geçerli belgeyle ilişkili Tek düzen Kaynak Bulucu'yu (URL) alır.

```
void GetCurrentUrl(CString& szUrl);
```

### <a name="parameters"></a>Parametreler

*szUrl*<br/>
Alınacak URL'yi içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

## <a name="cdhtmldialoggetdhtmldocument"></a><a name="getdhtmldocument"></a>CDHtmlDialog::GetDHtmlDocument

Şu anda yüklenen HTML belgesindeki [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) arabirimini alır.

```
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```

### <a name="parameters"></a>Parametreler

* \* \** HTML belgesi için işaretçi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT. Başarılı olursa S_OK döndürür.

## <a name="cdhtmldialoggetdroptarget"></a><a name="getdroptarget"></a>CDHtmlDialog::GetDropTarget

Bu iletişim alternatif bir [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget)sağlamak için izin vermek için bir bırakma hedefi olarak kullanıldığında içerdiği WebBrowser denetimi tarafından çağrılır.

```
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,
    IDropTarget** ppDropTarget);
```

### <a name="parameters"></a>Parametreler

*pDropTarget*<br/>
Bkz. *pDropTarget* in [IDocHostUIHandler::GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\)) in Windows SDK.

*ppDropTarget*<br/>
Windows SDK'da *ppDropTarget'e* `IDocHostUIHandler::GetDropTarget` bakın.

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, CDHtmlDialog'un [IDocHostUIHandler uygulamasıdır::GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\)), Windows SDK'da açıklandığı gibi.

## <a name="cdhtmldialoggetelement"></a><a name="getelement"></a>CDHtmlDialog::GetElement

*szElementId*tarafından belirtilen HTML öğesi üzerinde bir arabirim döndürür.

```
HRESULT GetElement(
    LPCTSTR szElementId,
    IDispatch** ppdisp,
    BOOL* pbCollection = NULL);

HRESULT GetElement(
    LPCTSTR szElementId,
    IHTMLElement** pphtmlElement);
```

### <a name="parameters"></a>Parametreler

*szElementId*<br/>
Bir HTML öğesinin kimliği.

*ppdisp*<br/>
İstenen öğe veya öğe koleksiyonu için `IDispatch` bir işaretçi.

*pbKoleksiyon*<br/>
*Ppdisp* tarafından temsil edilen nesnenin tek bir öğe mi yoksa eleman lar topluluğu mu olduğunu gösteren bir BOOL.

*pphtmlElement*<br/>
İstenen öğeiçin bir `IHTMLElement` işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Belirtilen kimlikle birden fazla öğe nin olabileceği koşulları işlemeniz gerekiyorsa, ilk aşırı yüklemeyi kullanın. Döndürülen arabirim işaretçisinin bir koleksiyona mı yoksa tek bir öğeye mi olduğunu öğrenmek için son parametreyi kullanabilirsiniz. Arabirim işaretçisi bir koleksiyondaysa, `IHTMLElementCollection` sözcük `item` konumuna göre öğelere başvurmak için öğeyi sorgulayabilir ve özelliğini kullanabilirsiniz.

Sayfada aynı kimliği olan birden fazla öğe varsa ikinci aşırı yükleme başarısız olur.

## <a name="cdhtmldialoggetelementhtml"></a><a name="getelementhtml"></a>CDHtmlDialog::GetElementHtml

`innerHTML` *szElementId*tarafından tanımlanan HTML öğesinin özelliğini alır.

```
BSTR GetElementHtml(LPCTSTR szElementId);
```

### <a name="parameters"></a>Parametreler

*szElementId*<br/>
Bir HTML öğesinin kimliği.

### <a name="return-value"></a>Dönüş Değeri

Öğe `innerHTML` *bulunamadıysa, szElementId* veya NULL tarafından tanımlanan HTML öğesinin özelliği.

## <a name="cdhtmldialoggetelementinterface"></a><a name="getelementinterface"></a>CDHtmlDialog::GetElementInterface

*SzElementId*tarafından tanımlanan HTML öğesinden istenen arabirim işaretçisini alır.

```
template <class Q> HRESULT GetElementInterface(
    LPCTSTR szElementId,
    Q** ppvObj);

HRESULT GetElementInterface(
    LPCTSTR szElementId,
    REFIID refiid,
    void** ppvObj);
```

### <a name="parameters"></a>Parametreler

*szElementId*<br/>
Bir HTML öğesinin kimliği.

*ppvObj*<br/>
Öğe bulunursa ve sorgu başarılı olursa, istenen arabirim işaretçisiyle doldurulacak bir işaretçinin adresi.

*refiid*<br/>
İstenen arabirimin arabirim kimliği (IID).

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCHtmlHttp#4](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]

## <a name="cdhtmldialoggetelementproperty"></a><a name="getelementproperty"></a>CDHtmlDialog::GetElementProperty

*SzElementId*tarafından tanımlanan HTML öğesinden *dispId* tarafından tanımlanan özelliğin değerini alır.

```
VARIANT GetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId);
```

### <a name="parameters"></a>Parametreler

*szElementId*<br/>
Bir HTML öğesinin kimliği.

*Dıspıd*<br/>
Bir mülkün sevk kimliği.

### <a name="return-value"></a>Dönüş Değeri

Özellik veya öğe bulunamazsa özelliğin veya boş bir varyantın değeri.

## <a name="cdhtmldialoggetelementtext"></a><a name="getelementtext"></a>CDHtmlDialog::GetElementText

`innerText` *szElementId*tarafından tanımlanan HTML öğesinin özelliğini alır.

```
BSTR GetElementText(LPCTSTR szElementId);
```

### <a name="parameters"></a>Parametreler

*szElementId*<br/>
Bir HTML öğesinin kimliği.

### <a name="return-value"></a>Dönüş Değeri

Özellik `innerText` veya öğe bulunamazsa, *szElementId* veya NULL tarafından tanımlanan HTML öğesinin özelliği.

## <a name="cdhtmldialoggetevent"></a><a name="getevent"></a>CDHtmlDialog::GetEvent

İşaretçiyi `IHTMLEventObj` geçerli olay nesnesine döndürür.

```
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```

### <a name="parameters"></a>Parametreler

*ppEventObj*<br/>
Arabirim işaretçisiyle doldurulacak `IHTMLEventObj` bir işaretçinin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca bir DHTML olay işleyicisi içinden çağrılmalıdır.

## <a name="cdhtmldialoggetexternal"></a><a name="getexternal"></a>CDHtmlDialog::GetExternal

Ev sahibinin `IDispatch` arabirimini alır.

```
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```

### <a name="parameters"></a>Parametreler

*ppDispatch*<br/>
Bkz. *ppDispatch* in [IDocHostUIHandler::Windows](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\)) SDK'da GetExternal.

### <a name="return-value"></a>Dönüş Değeri

Başarı veya başarısızlık E_NOTIMPL S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, CDHtmlDialog'un [IDocHostUIHandler uygulamasıdır::GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\)), Windows SDK'da açıklandığı gibi.

## <a name="cdhtmldialoggethostinfo"></a><a name="gethostinfo"></a>CDHtmlDialog::GetHostInfo

Ana bilgisayardaki web cisme yeteneklerini alır.

```
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```

### <a name="parameters"></a>Parametreler

*Pınfo*<br/>
[Bkz. iDocHostUIHandler::GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\)) in Windows SDK. *pInfo*

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, CDHtmlDialog'un [IDocHostUIHandler uygulamasıdır::GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\)), Windows SDK'da açıklandığı gibi.

## <a name="cdhtmldialoggetoptionkeypath"></a><a name="getoptionkeypath"></a>CDHtmlDialog::GetOptionKeyPath

Kullanıcı tercihlerinin depolandığı kayıt defteri anahtarını alır.

```
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,
    DWORD dw);
```

### <a name="parameters"></a>Parametreler

*pchKey*<br/>
Bkz. *pchKey* in [IDocHostUIHandler::GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\)) in The Windows SDK.

*Dw*<br/>
Windows SDK'da `IDocHostUIHandler::GetOptionKeyPath` *dw'ye* bakın.

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, CDHtmlDialog'un Windows SDK'da açıklandığı gibi [IDocHostUIHandler::GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))uygulamasıdır.

## <a name="cdhtmldialoghideui"></a><a name="hideui"></a>CDHtmlDialog::HideUI

Ev sahibinin ui'sini gizler.

```
STDMETHOD(HideUI)(void);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, CDHtmlDialog'un Windows SDK'da açıklandığı gibi [IDocHostUIHandler::HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))uygulamasıdır.

## <a name="cdhtmldialogisexternaldispatchsafe"></a><a name="isexternaldispatchsafe"></a>CDHtmlDialog::IsExternalDispatchSafe

Ana bilgisayar `IDispatch` arabiriminin komut dosyası için güvenli olup olmadığını gösterir.

```
virtual BOOL IsExternalDispatchSafe();
```

### <a name="return-value"></a>Dönüş Değeri

FALSE döndürür.

## <a name="cdhtmldialogloadfromresource"></a><a name="loadfromresource"></a>CDHtmlDialog::LoadFromResource

DHTML iletişim kutusunda belirtilen kaynağı WebBrowser denetimine yükler.

```
BOOL LoadFromResource(LPCTSTR lpszResource);
BOOL LoadFromResource(UINT nRes);
```

### <a name="parameters"></a>Parametreler

*lpszKaynak*<br/>
Yüklenmesi gereken kaynağın adını içeren bir dize işaretçisi.

*nRes*<br/>
Yüklenmesi gereken kaynağın kimliği.

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; aksi takdirde YANLIŞ.

## <a name="cdhtmldialogm_busehtmltitle"></a><a name="m_busehtmltitle"></a>CDHtmlDialog::m_bUseHtmlTitle

HTML belgesinin başlığının iletişim başlığı olarak kullanılıp kullanılmayacağını gösterir.

```
BOOL m_bUseHtmlTitle;
```

### <a name="remarks"></a>Açıklamalar

**m**_ **bUseHtmlTitle** DOĞRU ise, iletişim başlığı HTML belgesinin başlığına eşit olarak ayarlanır; aksi takdirde, iletişim kaynağındaki alt yazı kullanılır.

## <a name="cdhtmldialogm_nhtmlresid"></a><a name="m_nhtmlresid"></a>CDHtmlDialog::m_nHtmlResID

HTML kaynağının kaynak kimliği görüntülenecektir.

```
UINT m_nHtmlResID;
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCHtmlHttp#5](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_5.cpp)]

## <a name="cdhtmldialogm_pbrowserapp"></a><a name="m_pbrowserapp"></a>CDHtmlDialog::m_pBrowserApp

Web tarayıcısı uygulamasıiçin bir işaretçi.

```
CComPtr <IWebBrowser2> m_pBrowserApp;
```

## <a name="cdhtmldialogm_sphtmldoc"></a><a name="m_sphtmldoc"></a>CDHtmlDialog::m_spHtmlDoc

HTML belgesiiçin bir işaretçi.

```
CComPtr<IHTMLDocument2> m_spHtmlDoc;
```

## <a name="cdhtmldialogm_strcurrenturl"></a><a name="m_strcurrenturl"></a>CDHtmlDialog::m_strCurrentUrl

Geçerli URL.

```
CString m_strCurrentUrl;
```

## <a name="cdhtmldialogm_szhtmlresid"></a><a name="m_szhtmlresid"></a>CDHtmlDialog::m_szHtmlResID

HTML kaynak kimliğinin string sürümü.

```
LPTSTR m_szHtmlResID;
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCHtmlHttp#6](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]

## <a name="cdhtmldialognavigate"></a><a name="navigate"></a>CDHtmlDialog::Gezinme

*LPSZURL*tarafından belirtilen URL tarafından tanımlanan kaynağa yönlendirilir.

```
void Navigate(
    LPCTSTR lpszURL,
    DWORD dwFlags = 0,
    LPCTSTR lpszTargetFrameName = NULL,
    LPCTSTR lpszHeaders = NULL,
    LPVOID lpvPostData = NULL,
    DWORD dwPostDataLen = 0);
```

### <a name="parameters"></a>Parametreler

*Lpszurl*<br/>
Hedeflenecek URL'yi içeren bir dize için işaretçi.

*Dwflags*<br/>
Kaynağın geçmiş listesine eklenip eklenmeyeceğini, önbelleğe okunup okunmayacağını veya önbellekten yazıp yazılmayacağını ve kaynağın yeni bir pencerede görüntülenip görüntülenip görüntülenmeyeceğini belirten bir değişkenin bayrakları. Değişken [BrowserNavConstants](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768360\(v=vs.85\)) numaralandırma tarafından tanımlanan değerlerin bir leşimi olabilir.

*lpszTargetFrameName*<br/>
Kaynağı görüntülemek için çerçevenin adını içeren bir dize işaretçisi.

*lpszHeaders*<br/>
Sunucuya göndermek için HTTP üstbilgilerini belirten bir değer için bir işaretçi. Bu üstbilgi varsayılan Internet Explorer üstbilgilerine eklenir. Üstbilgiler, sunucunun gerektirdiği eylem, sunucuya geçirilen veri türü veya durum kodu gibi bilgileri belirtebilir. URL bir HTTP URL'si değilse, bu parametre yoksayılır.

*lpvPostData*<br/>
HTTP POST hareketi ile gönderilecek verilere işaretçi. Örneğin, POST hareketi bir HTML formu tarafından toplanan verileri göndermek için kullanılır. Bu parametre herhangi bir posta `Navigate` verisi belirtmezse, bir HTTP GET hareketi yayınlar. URL bir HTTP URL'si değilse, bu parametre yoksayılır.

*dwPostDataLen*<br/>
HTTP POST işlemi ile gönderilecek veriler. Örneğin, POST hareketi bir HTML formu tarafından toplanan verileri göndermek için kullanılır. Bu parametre herhangi bir posta `Navigate` verisi belirtmezse, bir HTTP GET hareketi yayınlar. URL bir HTTP URL'si değilse, bu parametre yoksayılır.

## <a name="cdhtmldialogonbeforenavigate"></a><a name="onbeforenavigate"></a>CDHtmlDialog::OnBeforeGezinme

Bir gezinti meydana gelmeden önce bir olayın alev alsın.

```
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
Bir `IDispatch` nesneye işaretçi.

*szUrl*<br/>
Gezinecek URL'yi içeren bir dize işaretçisi.

## <a name="cdhtmldialogondocumentcomplete"></a><a name="ondocumentcomplete"></a>CDHtmlDialog::OnDocumentComplete

Bir belge READYSTATE_COMPLETE durumu elde ettiğinde bir uygulamayı bildirmek için çerçeve tarafından çağrılır.

```
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
Bir `IDispatch` nesneye işaretçi.

*szUrl*<br/>
Gezinilen URL'yi içeren bir dize işaretçisi.

## <a name="cdhtmldialogondocwindowactivate"></a><a name="ondocwindowactivate"></a>CDHtmlDialog::OnDocWindowEtkinleştir

Belge penceresi etkinleştirildiğinde veya devre dışı bırakıldığında çerçeve tarafından çağrılır.

```
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>Parametreler

*fEtkinleştir*<br/>
Bkz. [fIDocHostUIHandler::OnDocWindowWindows](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\)) SDK'da etkinleştirin. *fActivate*

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, CDHtmlDialog'un [IDocHostUIHandler uygulamasıdır::OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\)), Windows SDK'da açıklandığı gibi.

## <a name="cdhtmldialogonframewindowactivate"></a><a name="onframewindowactivate"></a>CDHtmlDialog::OnFrameWindowEtkinleştir

Çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında çerçeve tarafından çağrılır.

```
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>Parametreler

*fEtkinleştir*<br/>
Bkz. [fIDocHostUIHandler::OnFrameWindowWindows](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\)) SDK'da etkinleştirin. *fActivate*

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, CDHtmlDialog'un [IDocHostUIHandler uygulamasıdır::OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\)), Windows SDK'da açıklandığı gibi.

## <a name="cdhtmldialogoninitdialog"></a><a name="oninitdialog"></a>CDHtmlDialog::OnInitDialog

WM_INITDIALOG iletisine yanıt olarak çağrıldı.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu ileti, iletişim kutusu görüntülenmeden `CreateIndirect`hemen `DoModal` önce oluşan `Create`, , veya aramalar sırasında iletişim kutusuna gönderilir.

İletişim kutusu başharfe geçtiğinde özel işlem gerçekleştirmeniz gerekiyorsa bu üye işlevi geçersiz kılın. Geçersiz kılınan sürümde, önce taban `OnInitDialog` sınıfı arayın, ancak geri dönüş değerini göz ardı edin. Normalde geçersiz kılınan üye işlevinizden TRUE'ya geri dönersiniz.

`OnInitDialog` Windows, ileti haritanız yerine tüm Microsoft Hazırlık Sınıfı Kitaplığı iletişim kutularında yaygın olan standart genel iletişim kutusu yordamı aracılığıyla işlevi çağırır, bu nedenle bu üye işlev için ileti eşlemi girişine ihtiyacınız yoktur.

## <a name="cdhtmldialogonnavigatecomplete"></a><a name="onnavigatecomplete"></a>CDHtmlDialog::OnNavigateComplete

Belirtilen URL'ye gezinme tamamlandıktan sonra çerçeve tarafından çağrılır.

```
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
Bir `IDispatch` nesneye işaretçi.

*szUrl*<br/>
Gezinilen URL'yi içeren bir dize işaretçisi.

## <a name="cdhtmldialogresizeborder"></a><a name="resizeborder"></a>CDHtmlDialog::ResizeBorder

Kenarlık alanını yeniden boyutlandırmak için gereken nesneyi uyarır.

```
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fRameWindow);
```

### <a name="parameters"></a>Parametreler

*prcBorder*<br/>
Bkz. [iDocHostUIHandler](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\)) içinde *prcBorder::Windows* SDK'da Yeniden Kenarlık.

*pUIWindow*<br/>
Windows SDK'daki `IDocHostUIHandler::ResizeBorder` *pUIWindow'a* bakın.

*fFrameWindow*<br/>
Windows SDK'daki `IDocHostUIHandler::ResizeBorder` *fFrameWindow'a* bakın.

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

## <a name="cdhtmldialogsetcontrolproperty"></a><a name="setcontrolproperty"></a>CDHtmlDialog::SetControlProperty

ActiveX denetiminin özelliğini yeni bir değere ayarlar.

```
void SetControlProperty(
    LPCTSTR szElementId,
    DISPID dispId,
    VARIANT* pVar);

void SetControlProperty(
    IDispatch* pdispControl,
    DISPID dispId,
    VARIANT* pVar);

void SetControlProperty(
    LPCTSTR szElementId,
    LPCTSTR szPropName,
    VARIANT* pVar);
```

### <a name="parameters"></a>Parametreler

*szElementId*<br/>
ActiveX denetiminin HTML kimliği.

*Dıspıd*<br/>
Ayarlanan özelliğin sevk kimliği.

*pVar*<br/>
Yeni özellik değerini içeren bir VARYANT işaretçisi.

*pdispKontrol*<br/>
ActiveX denetiminin `IDispatch` arabirimini işaretçi.

*szPropName*<br/>
Ayarlanan özelliğin adını içeren dize.

## <a name="cdhtmldialogsetelementhtml"></a><a name="setelementhtml"></a>CDHtmlDialog::SetElementHtml

BIR `innerHTML` HTML öğesinin özelliğini ayarlar.

```
void SetElementHtml(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementHtml(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>Parametreler

*szElementId*<br/>
Bir HTML öğesinin kimliği.

*bstrText*<br/>
Özelliğin `innerHTML` yeni değeri.

*punkElem*<br/>
Bir `IUnknown` HTML öğesinin işaretçisi.

## <a name="cdhtmldialogsetelementproperty"></a><a name="setelementproperty"></a>CDHtmlDialog::SetElementÖzellik

BIR HTML öğesinin özelliğini ayarlar.

```
void SetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId,
    VARIANT* pVar);
```

### <a name="parameters"></a>Parametreler

*szElementId*<br/>
Bir HTML öğesinin kimliği.

*Dıspıd*<br/>
Ayarlanan özelliğin sevk kimliği.

*pVar*<br/>
Özelliğin yeni değeri.

## <a name="cdhtmldialogsetelementtext"></a><a name="setelementtext"></a>CDHtmlDialog::SetElementText

BIR `innerText` HTML öğesinin özelliğini ayarlar.

```
void SetElementText(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementText(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>Parametreler

*szElementId*<br/>
Bir HTML öğesinin kimliği.

*bstrText*<br/>
Özelliğin `innerText` yeni değeri.

*punkElem*<br/>
Bir `IUnknown` HTML öğesinin işaretçisi.

## <a name="cdhtmldialogsetexternaldispatch"></a><a name="setexternaldispatch"></a>CDHtmlDialog::SetExternalDispatch

Ana bilgisayar `IDispatch` arabirimini ayarlar.

```
void SetExternalDispatch(IDispatch* pdispExternal);
```

### <a name="parameters"></a>Parametreler

*pdispExternal*<br/>
Yeni `IDispatch` arayüz.

## <a name="cdhtmldialogsethostflags"></a><a name="sethostflags"></a>CDHtmlDialog::SetHostFlags

Ana bilgisayar ui bayraklarını ayarlar.

```
void SetHostFlags(DWORD dwFlags);
```

### <a name="parameters"></a>Parametreler

*Dwflags*<br/>
Olası değerler için Windows SDK'daki [DOCHOSTUIFLAG'a](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753277\(v=vs.85\)) bakın.

## <a name="cdhtmldialogshowcontextmenu"></a><a name="showcontextmenu"></a>CDHtmlDialog::ShowContextMenu

Bağlam menüsü görüntülenmek üzereyken çağrılır.

```
STDMETHOD(ShowContextMenu)(
    DWORD dwID,
    POINT* ppt,
    IUnknown* pcmdtReserved,
    IDispatch* pdispReserved);
```

### <a name="parameters"></a>Parametreler

*dwID*<br/>
Bkz. *dwID* [in IDocHostUIHandler::Windows](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\)) SDK'da ShowContextMenu.

*Ppt*<br/>
Windows SDK'da `IDocHostUIHandler::ShowContextMenu` *ppt'ye* bakın.

*pcmdtAyrılmış*<br/>
Bkz. Windows SDK'da `IDocHostUIHandler::ShowContextMenu` *pcmdtReserved.*

*pdispReserved*<br/>
Bkz. windows SDK'da `IDocHostUIHandler::ShowContextMenu` ayrılmış *pdispReserved.*

### <a name="return-value"></a>Dönüş Değeri

S_FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, CDHtmlDialog'un [IDocHostUIHandler uygulamasıdır::ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\)), Windows SDK'da açıklandığı gibi.

## <a name="cdhtmldialogshowui"></a><a name="showui"></a>CDHtmlDialog::ShowUI

Ev sahibinin u-u-larını gösterir.

```
STDMETHOD(ShowUI)(
    DWORD dwID,
    IOleInPlaceActiveObject* pActiveObject,
    IOleCommandTarget* pCommandTarget,
    IOleInPlaceFrame* pFrame,
    IOleInPlaceUIWindow* pDoc);
```

### <a name="parameters"></a>Parametreler

*dwID*<br/>
Bkz. *dwID* [in IDocHostUIHandler::ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\)) in the Windows SDK.

*pActiveObject*<br/>
Windows SDK'daki `IDocHostUIHandler::ShowUI` *d pActiveObject'e* bakın.

*pCommandTarget*<br/>
Windows SDK'da *pCommandTarget'e* `IDocHostUIHandler::ShowUI` bakın.

*pFrame*<br/>
Windows SDK'daki `IDocHostUIHandler::ShowUI` *pFrame'e* bakın.

*pDoc*<br/>
Windows SDK'da *pDoc'a* `IDocHostUIHandler::ShowUI` bakın.

### <a name="return-value"></a>Dönüş Değeri

S_FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, CDHtmlDialog'un [IDocHostUIHandler uygulamasıdır::ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\)), Windows SDK'da açıklandığı gibi.

## <a name="cdhtmldialogtranslateaccelerator"></a><a name="translateaccelerator"></a>CDHtmlDialog::TranslateAccelerator

Menü hızlandırıcı anahtar lı iletileri işlemek için çağrıldı.

```
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,
    const GUID* pguidCmdGroup,
    DWORD nCmdID);
```

### <a name="parameters"></a>Parametreler

*lpMsg*<br/>
[Bkz. iDocHostUIHandler](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\)) içinde *lpMsg::Windows* SDK'da TranslateAccelerator.

*pguidCmdGroup*<br/>
Windows SDK'daki `IDocHostUIHandler::TranslateAccelerator` *pguidCmdGroup'a* bakın.

*nCmdID*<br/>
Windows SDK'da `IDocHostUIHandler::TranslateAccelerator` *nCmdID'ye* bakın.

### <a name="return-value"></a>Dönüş Değeri

S_FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, CDHtmlDialog'un [IDocHostUIHandler uygulamasıdır::TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\)), Windows SDK'da açıklandığı gibi.

## <a name="cdhtmldialogtranslateurl"></a><a name="translateurl"></a>CDHtmlDialog::ÇeviriUrl

Yüklenecek URL'yi değiştirmek için çağrıldı.

```
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,
    OLECHAR* pchURLIn,
    OLECHAR** ppchURLOut);
```

### <a name="parameters"></a>Parametreler

*dwÇeviri*<br/>
Bkz. *dwTranslate* in [IDocHostUIHandler::Windows](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\)) SDK'da Url'yi çevirin.

*pchURLIn*<br/>
Windows SDK'da `IDocHostUIHandler::TranslateUrl` *pchURLIn'e* bakın.

*ppchURLOut*<br/>
Windows SDK'da `IDocHostUIHandler::TranslateUrl` *ppchURLOut'a* bakın.

### <a name="return-value"></a>Dönüş Değeri

S_FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, CDHtmlDialog'un [IDocHostUIHandler uygulamasıdır::ÇeviriUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\)), Windows SDK'da açıklandığı gibi.

## <a name="cdhtmldialogupdateui"></a><a name="updateui"></a>CDHtmlDialog::UpdateUI

Komut durumunun değiştiğini ana bilgisayara bildirmek için çağrıldı.

```
STDMETHOD(UpdateUI)(void);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, CDHtmlDialog'un [IDocHostUIHandler uygulamasıdır::UpdateUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\)), Windows SDK'da açıklandığı gibi.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek DHtmlExplore](../../overview/visual-cpp-samples.md)<br/>
[DDX_DHtml Yardımcı Makrolar](#ddx_dhtml_helper_macros)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
