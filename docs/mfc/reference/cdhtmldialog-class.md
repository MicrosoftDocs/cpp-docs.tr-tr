---
title: CDHtmlDialog sınıfı
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
ms.openlocfilehash: 9cc01c94357d7aac7fa6fa98127628a60746e1e8
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842890"
---
# <a name="cdhtmldialog-class"></a>CDHtmlDialog sınıfı

, Kullanıcı arabirimini uygulamak için iletişim kutusu kaynakları yerine HTML kullanan iletişim kutuları oluşturmak için kullanılır.

## <a name="syntax"></a>Syntax

```
class CDHtmlDialog : public CDialog, public CDHtmlEventSink
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDHtmlDialog:: CDHtmlDialog](#cdhtmldialog)|Bir CDHtmlDialog nesnesi oluşturur.|
|[CDHtmlDialog:: ~ CDHtmlDialog](#_dtorcdhtmldialog)|CDHtmlDialog nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDHtmlDialog:: CanAccessExternal](#canaccessexternal)|Yüklenen sayfada betik nesnelerinin denetim sitesinin dış gönderimi 'ne erişip erişemeyeceğini görmek için erişim denetimi olarak çağrılan geçersiz kılınabilir. Dağıtım için güvenli hale geldiğinden veya geçerli bölgenin betik için güvenli olmayan nesneler için izin verdiğinden emin olmak için denetler.|
|[CDHtmlDialog:: CreateControlSite](#createcontrolsite)|Geçersiz kılınabilir, iletişim kutusunda WebBrowser denetimini barındırmak üzere bir denetim sitesi örneği oluşturmak için kullanılır.|
|[CDHtmlDialog::D DX_DHtml_AxControl](#ddx_dhtml_axcontrol)|Bir üye değişkeni ve bir HTML sayfasındaki ActiveX denetiminin özellik değeri arasındaki verileri değiş tokuş eder.|
|[CDHtmlDialog::D DX_DHtml_CheckBox](#ddx_dhtml_checkbox)|Bir üye değişkeni ve bir HTML sayfasındaki onay kutusu arasındaki verileri değiş tokuş eder.|
|[CDHtmlDialog::D DX_DHtml_ElementText](#ddx_dhtml_elementtext)|Bir HTML sayfasındaki üye değişkeni ile herhangi bir HTML öğesi özelliği arasındaki verileri değiş tokuş eder.|
|[CDHtmlDialog::D DX_DHtml_Radio](#ddx_dhtml_radio)|Bir üye değişkeni ve bir HTML sayfasındaki radyo düğmesi arasındaki verileri değiş tokuş eder.|
|[CDHtmlDialog::D DX_DHtml_SelectIndex](#ddx_dhtml_selectindex)|HTML sayfasındaki liste kutusunun dizinini alır veya ayarlar.|
|[CDHtmlDialog::D DX_DHtml_SelectString](#ddx_dhtml_selectstring)|Bir HTML sayfasındaki liste kutusu girişinin (geçerli dizine göre) görüntüleme metnini alır veya ayarlar.|
|[CDHtmlDialog::D DX_DHtml_SelectValue](#ddx_dhtml_selectvalue)|Bir HTML sayfasındaki liste kutusu girişinin (geçerli dizine göre) değerini alır veya ayarlar.|
|[CDHtmlDialog::D estroyModeless](#destroymodeless)|Kalıcı olmayan iletişim kutusunu yok eder.|
|[CDHtmlDialog:: Enablemodsuz](#enablemodeless)|Kalıcı olmayan iletişim kutularını izin vermez.|
|[CDHtmlDialog:: FilterDataObject](#filterdataobject)|İletişim kutusunun barındırılan tarayıcı tarafından oluşturulan Pano veri nesnelerini filtrelemesine olanak sağlar.|
|[CDHtmlDialog:: GetControlDispatch](#getcontroldispatch)|`IDispatch`HTML belgesine katıştırılmış ActiveX denetimindeki arabirimi alır.|
|[CDHtmlDialog:: GetControlProperty](#getcontrolproperty)|Belirtilen ActiveX denetiminin istenen özelliğini alır.|
|[CDHtmlDialog:: GetCurrentUrl](#getcurrenturl)|Geçerli belgeyle ilişkili Tekdüzen Kaynak Konumlandırıcı 'Sını (URL) alır.|
|[CDHtmlDialog:: GetDHtmlDocument](#getdhtmldocument)|Şu anda yüklü olan HTML belgesinde IHTMLDocument2 arabirimini alır.|
|[CDHtmlDialog:: GetDropTarget](#getdroptarget)|İletişim kutusunun alternatif bir [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget)sağlaması için bırakma hedefi olarak kullanıldığında içerilen WebBrowser denetimi tarafından çağırılır.|
|[CDHtmlDialog:: GetElement](#getelement)|Bir HTML öğesinde bir arabirim alır.|
|[CDHtmlDialog:: GetElementHtml](#getelementhtml)|`innerHTML`BIR HTML öğesinin özelliğini alır.|
|[CDHtmlDialog:: Getelementınterface](#getelementinterface)|Bir HTML öğesinden istenen arabirim işaretçisini alır.|
|[CDHtmlDialog:: GetElementProperty](#getelementproperty)|Bir HTML öğesinin özelliğinin değerini alır.|
|[CDHtmlDialog:: GetElementText](#getelementtext)|`innerText`BIR HTML öğesinin özelliğini alır.|
|[CDHtmlDialog:: GetEvent](#getevent)|`IHTMLEventObj`Geçerli olay nesnesine olan işaretçiyi alır.|
|[CDHtmlDialog:: GetExternal](#getexternal)|Konağın `IDispatch` arabirimini alır.|
|[CDHtmlDialog:: GetHostInfo](#gethostinfo)|Konağın Kullanıcı arabirimi yeteneklerini alır.|
|[CDHtmlDialog:: GetOptionKeyPath](#getoptionkeypath)|Kullanıcı tercihlerinin depolanacağı kayıt defteri anahtarını alır.|
|[CDHtmlDialog:: HideUI](#hideui)|Konağın Kullanıcı arabirimini gizler.|
|[CDHtmlDialog:: ısexternaldispatchsafe](#isexternaldispatchsafe)|Ana bilgisayarın `IDispatch` arabiriminin komut dosyası oluşturma için güvenli olup olmadığını gösterir.|
|[CDHtmlDialog:: LoadFromResource](#loadfromresource)|Belirtilen kaynağı WebBrowser denetimine yükler.|
|[CDHtmlDialog:: gezinmek](#navigate)|Belirtilen URL 'ye gider.|
|[CDHtmlDialog:: OnBeforeNavigate](#onbeforenavigate)|Bir gezinti olayı tetiklenmadan önce Framework tarafından çağırılır.|
|[CDHtmlDialog:: Ondocumenttamamlanmıştır](#ondocumentcomplete)|Bir belge READYSTATE_COMPLETE durumuna ulaştığında bir uygulamaya bildirim almak için Framework tarafından çağırılır.|
|[CDHtmlDialog:: OnDocWindowActivate](#ondocwindowactivate)|Belge penceresi etkinleştirildiğinde veya devre dışı bırakıldığında Framework tarafından çağırılır.|
|[CDHtmlDialog:: OnFrameWindowActivate](#onframewindowactivate)|Çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında Framework tarafından çağırılır.|
|[CDHtmlDialog:: OnInitDialog](#oninitdialog)|WM_INITDIALOG iletisine yanıt olarak çağırılır.|
|[CDHtmlDialog:: Onnavigatetamamlanmıştır](#onnavigatecomplete)|Bir gezinti olayı tamamlandıktan sonra Framework tarafından çağırılır.|
|[CDHtmlDialog:: ResizeBorder](#resizeborder)|Nesnenin kenarlık alanını yeniden boyutlandırmak için ihtiyacı olan nesneyi uyarır.|
|[CDHtmlDialog:: SetControlProperty](#setcontrolproperty)|ActiveX denetiminin özelliğini yeni bir değere ayarlar.|
|[CDHtmlDialog:: SetElementHtml](#setelementhtml)|`innerHTML`BIR HTML öğesinin özelliğini ayarlar.|
|[CDHtmlDialog:: SetElementProperty](#setelementproperty)|Bir HTML öğesinin özelliğini ayarlar.|
|[CDHtmlDialog:: SetElementText](#setelementtext)|`innerText`BIR HTML öğesinin özelliğini ayarlar.|
|[CDHtmlDialog:: SetExternalDispatch](#setexternaldispatch)|Konağın `IDispatch` arabirimini ayarlar.|
|[CDHtmlDialog:: SetHostFlags](#sethostflags)|Konağın Kullanıcı arabirimi bayraklarını ayarlar.|
|[CDHtmlDialog:: ShowContextMenu](#showcontextmenu)|Bağlam menüsü görüntülenmek üzereyken çağırılır.|
|[CDHtmlDialog:: ShowUI](#showui)|Konağın Kullanıcı arabirimini gösterir.|
|[CDHtmlDialog:: TranslateAccelerator](#translateaccelerator)|Menü Hızlandırıcısı anahtar iletilerini işlemek için çağırılır.|
|[CDHtmlDialog:: TranslateUrl](#translateurl)|Yüklenecek URL 'YI değiştirmek için çağırılır.|
|[CDHtmlDialog:: UpdateUI](#updateui)|Ana bilgisayara komut durumunun değiştiğini bildirmek için çağırılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDHtmlDialog:: m_bUseHtmlTitle](#m_busehtmltitle)|HTML belgesinin başlığının iletişim kutusu başlığı olarak kullanılıp kullanılmayacağını gösterir.|
|[CDHtmlDialog:: m_nHtmlResID](#m_nhtmlresid)|Görüntülenecek HTML kaynağının kaynak KIMLIĞI.|
|[CDHtmlDialog:: m_pBrowserApp](#m_pbrowserapp)|Web tarayıcı uygulaması için bir işaretçi.|
|[CDHtmlDialog:: m_spHtmlDoc](#m_sphtmldoc)|HTML belgesi işaretçisi.|
|[CDHtmlDialog:: m_strCurrentUrl](#m_strcurrenturl)|Geçerli URL.|
|[CDHtmlDialog:: m_szHtmlResID](#m_szhtmlresid)|HTML kaynak KIMLIĞININ dize sürümü.|

## <a name="remarks"></a>Açıklamalar

`CDHtmlDialog` HTML 'den veya URL 'den görüntülenmek üzere HTML yükleyebilir.

`CDHtmlDialog` Ayrıca, HTML denetimleriyle veri alışverişi yapabilir ve düğme tıklamaları gibi HTML denetimlerinden olayları işleyebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDHtmlSinkHandlerBase2`

`CDHtmlSinkHandlerBase1`

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDHtmlSinkHandler`

[CWnd](../../mfc/reference/cwnd-class.md)

`CDHtmlEventSink`

[CDialog](../../mfc/reference/cdialog-class.md)

`CDHtmlDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdhtml. h

## <a name="ddx_dhtml-helper-macros"></a><a name="ddx_dhtml_helper_macros"></a> DDX_DHtml Yardımcısı makroları

DDX_DHtml Yardımcısı makroları, HTML sayfasındaki denetimlerin yaygın olarak kullanılan özelliklerine kolayca erişim sağlar.

### <a name="data-exchange-macros"></a>Veri değişimi makroları

|Ad|Açıklama|
|-|-|
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|Seçili denetimden değer özelliğini ayarlar veya alır.|
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|Geçerli öğenin başlangıç ve bitiş etiketleri arasındaki metni ayarlar veya alır.|
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|Geçerli öğenin başlangıç ve bitiş etiketleri arasında HTML ayarlar veya alır.|
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|Hedef URL 'YI veya bağlantı noktasını ayarlar veya alır.|
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|Hedef pencereyi veya çerçeveyi ayarlar veya alır.|
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|Belgedeki bir görüntünün veya video klibinin adını ayarlar veya alır.|
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|İlişkili çerçevenin URL 'sini ayarlar veya alır.|
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|İlişkili çerçevenin URL 'sini ayarlar veya alır.|

## <a name="cdhtmldialogcanaccessexternal"></a><a name="canaccessexternal"></a> CDHtmlDialog:: CanAccessExternal

Yüklenen sayfada betik nesnelerinin denetim sitesinin dış gönderimi 'ne erişip erişemeyeceğini görmek için erişim denetimi olarak çağrılan geçersiz kılınabilir. Dağıtım için güvenli hale geldiğinden veya geçerli bölgenin betik için güvenli olmayan nesneler için izin verdiğinden emin olmak için denetler.

```
virtual BOOL CanAccessExternal();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

## <a name="cdhtmldialogcdhtmldialog"></a><a name="cdhtmldialog"></a> CDHtmlDialog:: CDHtmlDialog

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
Bir iletişim kutusu şablon kaynağının adı olan null ile sonlandırılmış dize.

*Szhtmlresd*<br/>
Bir HTML kaynağının adı olan null ile sonlandırılmış dize.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip pencere nesnesine ( [CWnd](../../mfc/reference/cwnd-class.md)türü) yönelik bir işaretçi. NULL ise, iletişim kutusu nesnesinin ana penceresi ana uygulama penceresine ayarlanır.

*Nıdtemplate*<br/>
Bir iletişim kutusu şablon kaynağının KIMLIK numarasını içerir.

*Nhtmlresd*<br/>
Bir HTML kaynağının KIMLIK numarasını içerir.

### <a name="remarks"></a>Açıklamalar

Oluşturucunun ikinci formu, şablon adı aracılığıyla iletişim kaynağına erişim sağlar. Oluşturucunun üçüncü formu, kaynak şablonun KIMLIĞI üzerinden iletişim kaynağına erişim sağlar. Genellikle KIMLIK **IDD_** önekiyle başlar.

## <a name="cdhtmldialogcdhtmldialog"></a><a name="_dtorcdhtmldialog"></a> CDHtmlDialog:: ~ CDHtmlDialog

CDHtmlDialog nesnesini yok eder.

```
virtual ~CDHtmlDialog();
```

### <a name="remarks"></a>Açıklamalar

[CWnd::D estroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) üye Işlevi, [CDialog:: Create](../../mfc/reference/cdialog-class.md#create)tarafından oluşturulan kalıcı olmayan iletişim kutularını yok etmek için kullanılmalıdır.

## <a name="cdhtmldialogcreatecontrolsite"></a><a name="createcontrolsite"></a> CDHtmlDialog:: CreateControlSite

Geçersiz kılınabilir, iletişim kutusunda WebBrowser denetimini barındırmak üzere bir denetim sitesi örneği oluşturmak için kullanılır.

```
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,
    COleControlSite** ppSite,
    UINT /* nID */,
    REFCLSID /* clsid */);
```

### <a name="parameters"></a>Parametreler

*pContainer*<br/>
[Cotacontrolcontainer](../../mfc/reference/colecontrolcontainer-class.md) nesnesine yönelik bir işaretçi

*ppSite*<br/>
[Cotacontrolsite](../../mfc/reference/colecontrolsite-class.md)işaretçisinin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kendi denetim sitesi sınıfınızın bir örneğini döndürmek için bu üye işlevi geçersiz kılabilirsiniz.

## <a name="cdhtmldialogddx_dhtml_axcontrol"></a><a name="ddx_dhtml_axcontrol"></a> CDHtmlDialog::D DX_DHtml_AxControl

Bir üye değişkeni ve bir HTML sayfasındaki ActiveX denetiminin özellik değeri arasındaki verileri değiş tokuş eder.

```cpp
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

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*szID*<br/>
ActiveX denetimi için HTML kaynağındaki nesne etiketinin ID parametresinin değeri.

*Dı*<br/>
Veri alışverişi yapmak istediğiniz özelliğin dağıtım KIMLIĞI.

*szPropName*<br/>
Özelliğin adı.

*l*<br/>
ActiveX denetim özelliğiyle değiş tokuş edilen değeri tutan VARIANT, [Cotavariant](../../mfc/reference/colevariant-class.md)veya [CComVariant](../../atl/reference/ccomvariant-class.md)türünde veri üyesi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCHtmlHttp#1](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_1.cpp)]

## <a name="cdhtmldialogddx_dhtml_checkbox"></a><a name="ddx_dhtml_checkbox"></a> CDHtmlDialog::D DX_DHtml_CheckBox

Bir üye değişkeni ve bir HTML sayfasındaki onay kutusu arasındaki verileri değiş tokuş eder.

```cpp
void DDX_DHtml_CheckBox(
    CDataExchange* pDX,
    LPCTSTR szId,
    int& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*szID*<br/>
HTML denetiminin ID parametresi için belirttiğiniz değer.

*deeri*<br/>
Takas edilmekte olan değer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCHtmlHttp#2](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]

## <a name="cdhtmldialogddx_dhtml_elementtext"></a><a name="ddx_dhtml_elementtext"></a> CDHtmlDialog::D DX_DHtml_ElementText

Bir HTML sayfasındaki üye değişkeni ile herhangi bir HTML öğesi özelliği arasındaki verileri değiş tokuş eder.

```cpp
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

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*szID*<br/>
HTML denetiminin ID parametresi için belirttiğiniz değer.

*Dı*<br/>
Veri alışverişi yapmak istediğiniz HTML öğesinin dağıtım KIMLIĞI.

*deeri*<br/>
Takas edilmekte olan değer.

## <a name="cdhtmldialogddx_dhtml_radio"></a><a name="ddx_dhtml_radio"></a> CDHtmlDialog::D DX_DHtml_Radio

Bir üye değişkeni ve bir HTML sayfasındaki radyo düğmesi arasındaki verileri değiş tokuş eder.

```cpp
void DDX_DHtml_Radio(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*szID*<br/>
HTML denetiminin ID parametresi için belirttiğiniz değer.

*deeri*<br/>
Takas edilmekte olan değer.

## <a name="cdhtmldialogddx_dhtml_selectindex"></a><a name="ddx_dhtml_selectindex"></a> CDHtmlDialog::D DX_DHtml_SelectIndex

HTML sayfasındaki liste kutusunun dizinini alır veya ayarlar.

```cpp
void DDX_DHtml_SelectIndex(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*szID*<br/>
HTML denetiminin parametresi için belirttiğiniz değer `id` .

*deeri*<br/>
Takas edilmekte olan değer.

## <a name="cdhtmldialogddx_dhtml_selectstring"></a><a name="ddx_dhtml_selectstring"></a> CDHtmlDialog::D DX_DHtml_SelectString

Bir HTML sayfasındaki liste kutusu girişinin (geçerli dizine göre) görüntüleme metnini alır veya ayarlar.

```cpp
void DDX_DHtml_SelectString(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*szID*<br/>
HTML denetiminin ID parametresi için belirttiğiniz değer.

*deeri*<br/>
Takas edilmekte olan değer.

## <a name="cdhtmldialogddx_dhtml_selectvalue"></a><a name="ddx_dhtml_selectvalue"></a> CDHtmlDialog::D DX_DHtml_SelectValue

Bir HTML sayfasındaki liste kutusu girişinin (geçerli dizine göre) değerini alır veya ayarlar.

```cpp
void DDX_DHtml_SelectValue(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>Parametreler

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesine yönelik bir işaretçi.

*szID*<br/>
HTML denetiminin ID parametresi için belirttiğiniz değer.

*deeri*<br/>
Takas edilmekte olan değer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCHtmlHttp#3](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]

## <a name="cdhtmldialogdestroymodeless"></a><a name="destroymodeless"></a> CDHtmlDialog::D estroyModeless

Nesneden kalıcı olmayan iletişim kutusu ayırır `CDHtmlDialog` ve nesneyi yok eder.

```cpp
void DestroyModeless();
```

## <a name="cdhtmldialogenablemodeless"></a><a name="enablemodeless"></a> CDHtmlDialog:: Enablemodsuz

Kalıcı olmayan iletişim kutularını izin vermez.

```
STDMETHOD(EnableModeless)(BOOL fEnable);
```

### <a name="parameters"></a>Parametreler

*fEnable*<br/>
Windows SDK, [ıdochostuihandler:: Enablemodin](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\)) Içinde *fEnable* bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, CDHtmlDialog 'ın [ıdochostuihandler:: Enablemodary](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))uygulamasıdır.

## <a name="cdhtmldialogfilterdataobject"></a><a name="filterdataobject"></a> CDHtmlDialog:: FilterDataObject

İletişim kutusunun barındırılan tarayıcı tarafından oluşturulan Pano veri nesnelerini filtrelemesine olanak sağlar.

```
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,
    IDataObject** ppDORet);
```

### <a name="parameters"></a>Parametreler

*Kaldırıldığında*<br/>
Windows SDK için bkz. [ıdochostuihandler:: FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\)) içindeki *pDO* .

*ppDORet*<br/>
Windows SDK içindeki *Ppdoret* bölümüne bakın `IDocHostUIHandler::FilterDataObject` .

### <a name="return-value"></a>Dönüş Değeri

S_FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, CDHtmlDialog 'ın [ıdochostuihandler:: FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))uygulamasıdır.

## <a name="cdhtmldialoggetcontroldispatch"></a><a name="getcontroldispatch"></a> CDHtmlDialog:: GetControlDispatch

`IDispatch` [Getdhtmldocument](#getdhtmldocument)tarafından döndürülen HTML belgesinde gömülü bir ActiveX denetimindeki arabirimi alır.

```
HRESULT GetControlDispatch(
    LPCTSTR szId,
    IDispatch** ppdisp);
```

### <a name="parameters"></a>Parametreler

*szID*<br/>
ActiveX denetiminin HTML KIMLIĞI.

*ppDisp*<br/>
`IDispatch`Web sayfasında bulunursa denetimin arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="cdhtmldialoggetcontrolproperty"></a><a name="getcontrolproperty"></a> CDHtmlDialog:: GetControlProperty

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

*szID*<br/>
ActiveX denetiminin HTML KIMLIĞI.

*szPropName*<br/>
Geçerli kullanıcının varsayılan yerel ayarında bir özelliğin adı.

*pdispControl*<br/>
`IDispatch`Bir ActiveX denetimi işaretçisi.

*Dı*<br/>
Bir özelliğin dağıtım KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Denetim veya özellik bulunamazsa, istenen özelliği veya boş bir değişkeni içeren bir değişken.

### <a name="remarks"></a>Açıklamalar

Aşırı yüklemeler en üstte en çok etkin olarak listelenir.

## <a name="cdhtmldialoggetcurrenturl"></a><a name="getcurrenturl"></a> CDHtmlDialog:: GetCurrentUrl

Geçerli belgeyle ilişkili Tekdüzen Kaynak Konumlandırıcı 'Sını (URL) alır.

```cpp
void GetCurrentUrl(CString& szUrl);
```

### <a name="parameters"></a>Parametreler

*szUrl*<br/>
Alınacak URL 'YI içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

## <a name="cdhtmldialoggetdhtmldocument"></a><a name="getdhtmldocument"></a> CDHtmlDialog:: GetDHtmlDocument

Şu anda yüklü olan HTML belgesinde [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) arabirimini alır.

```
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```

### <a name="parameters"></a>Parametreler

bir HTML belgesi işaretçisine yönelik bir işaretçi olan * \* \* pphtmldoc* .

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT. Başarılı olursa S_OK döndürür.

## <a name="cdhtmldialoggetdroptarget"></a><a name="getdroptarget"></a> CDHtmlDialog:: GetDropTarget

İletişim kutusunun alternatif bir [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget)sağlaması için bırakma hedefi olarak kullanıldığında içerilen WebBrowser denetimi tarafından çağırılır.

```
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,
    IDropTarget** ppDropTarget);
```

### <a name="parameters"></a>Parametreler

*pDropTarget*<br/>
Windows SDK [ıdochostuihandler:: GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\)) Içindeki *pdroptarget* bölümüne bakın.

*ppDropTarget*<br/>
Windows SDK içindeki *Ppdroptarget* bölümüne bakın `IDocHostUIHandler::GetDropTarget` .

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, CDHtmlDialog 'ın [ıdochostuihandler:: GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))uygulamasıdır.

## <a name="cdhtmldialoggetelement"></a><a name="getelement"></a> CDHtmlDialog:: GetElement

*SzElementId*tarafından belirtilen HTML öğesinde bir arabirim döndürür.

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
Bir HTML öğesinin KIMLIĞI.

*ppDisp*<br/>
`IDispatch`İstenen öğe veya öğe koleksiyonu için bir işaretçi.

*pbCollection*<br/>
*PpDisp* tarafından temsil edilen nesnenin tek bir öğe mi yoksa bir öğe koleksiyonu mu olduğunu gösteren bir bool.

*pphtmlElement*<br/>
`IHTMLElement`İstenen öğeye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Belirtilen KIMLIĞE sahip birden fazla öğe olabileceği koşulları işlemeniz gerekiyorsa, ilk tekrar yüklemeyi kullanın. Döndürülen arabirim işaretçisinin bir koleksiyona mi yoksa tek bir öğe mi olduğunu öğrenmek için son parametresini kullanabilirsiniz. Arabirim işaretçisi bir koleksiyon üzerinde ise, ' i sorgulayabilir `IHTMLElementCollection` ve `item` özelliğini kullanarak öğeleri sıralı konuma göre başvurabilirsiniz.

Sayfada aynı KIMLIĞE sahip birden fazla öğe varsa ikinci aşırı yükleme başarısız olur.

## <a name="cdhtmldialoggetelementhtml"></a><a name="getelementhtml"></a> CDHtmlDialog:: GetElementHtml

`innerHTML` *SzElementId*tarafından tanımlanan html öğesinin özelliğini alır.

```
BSTR GetElementHtml(LPCTSTR szElementId);
```

### <a name="parameters"></a>Parametreler

*szElementId*<br/>
Bir HTML öğesinin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

`innerHTML`Öğe bulunamazsa *szElementId* tarafından tanımlanan html ÖĞESININ özelliği veya null.

## <a name="cdhtmldialoggetelementinterface"></a><a name="getelementinterface"></a> CDHtmlDialog:: Getelementınterface

*SzElementId*tarafından tanımlanan html öğesinden istenen arabirim işaretçisini alır.

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
Bir HTML öğesinin KIMLIĞI.

*ppvObj*<br/>
Öğe bulunursa ve sorgu başarılı olursa istenen arabirim işaretçiyle doldurulacak bir işaretçinin adresi.

*yeniden fııd*<br/>
İstenen arabirimin arabirim KIMLIĞI (IID).

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCHtmlHttp#4](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]

## <a name="cdhtmldialoggetelementproperty"></a><a name="getelementproperty"></a> CDHtmlDialog:: GetElementProperty

*SzElementId*tarafından tanımlanan html öğesinden *DISPID* tarafından tanımlanan özelliğin değerini alır.

```
VARIANT GetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId);
```

### <a name="parameters"></a>Parametreler

*szElementId*<br/>
Bir HTML öğesinin KIMLIĞI.

*Dı*<br/>
Bir özelliğin dağıtım KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Özellik veya öğe bulunamazsa, özelliğin veya boş bir varyantın değeri.

## <a name="cdhtmldialoggetelementtext"></a><a name="getelementtext"></a> CDHtmlDialog:: GetElementText

`innerText` *SzElementId*tarafından tanımlanan html öğesinin özelliğini alır.

```
BSTR GetElementText(LPCTSTR szElementId);
```

### <a name="parameters"></a>Parametreler

*szElementId*<br/>
Bir HTML öğesinin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

`innerText`Property veya element bulunamazsa *szElementId* tarafından tanımlanan html ÖĞESININ özelliği veya null.

## <a name="cdhtmldialoggetevent"></a><a name="getevent"></a> CDHtmlDialog:: GetEvent

`IHTMLEventObj`Geçerli olay nesnesine olan işaretçiyi döndürür.

```
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```

### <a name="parameters"></a>Parametreler

*ppEventObj*<br/>
`IHTMLEventObj`Arabirim işaretçiyle doldurulacak işaretçinin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca bir DHTML olay işleyicisi içinden çağrılmalıdır.

## <a name="cdhtmldialoggetexternal"></a><a name="getexternal"></a> CDHtmlDialog:: GetExternal

Konağın `IDispatch` arabirimini alır.

```
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```

### <a name="parameters"></a>Parametreler

*ppDispatch*<br/>
Windows SDK [ıdochostuihandler:: GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\)) Içindeki *ppdispatch* öğesine bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya E_NOTIMPL hata durumunda S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, CDHtmlDialog 'ın [ıdochostuihandler:: GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))uygulamasıdır.

## <a name="cdhtmldialoggethostinfo"></a><a name="gethostinfo"></a> CDHtmlDialog:: GetHostInfo

Konağın Kullanıcı arabirimi yeteneklerini alır.

```
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```

### <a name="parameters"></a>Parametreler

*pInfo*<br/>
Windows SDK, [ıdochostuihandler:: GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\)) Içindeki *pInfo* bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, CDHtmlDialog 'ın [ıdochostuihandler:: GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))uygulamasıdır.

## <a name="cdhtmldialoggetoptionkeypath"></a><a name="getoptionkeypath"></a> CDHtmlDialog:: GetOptionKeyPath

Kullanıcı tercihlerinin depolanacağı kayıt defteri anahtarını alır.

```
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,
    DWORD dw);
```

### <a name="parameters"></a>Parametreler

*pchKey*<br/>
Windows SDK [ıdochostuihandler:: GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\)) Içindeki *pchkey* öğesine bakın.

*DW*<br/>
Windows SDK içinde *DW* 'de bakın `IDocHostUIHandler::GetOptionKeyPath` .

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, CDHtmlDialog 'ın [ıdochostuihandler:: GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))'in uygulamasıdır.

## <a name="cdhtmldialoghideui"></a><a name="hideui"></a> CDHtmlDialog:: HideUI

Konağın Kullanıcı arabirimini gizler.

```
STDMETHOD(HideUI)(void);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, CDHtmlDialog 'ın [ıdochostuihandler:: HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))uygulamasıdır.

## <a name="cdhtmldialogisexternaldispatchsafe"></a><a name="isexternaldispatchsafe"></a> CDHtmlDialog:: ısexternaldispatchsafe

Ana bilgisayarın `IDispatch` arabiriminin komut dosyası oluşturma için güvenli olup olmadığını gösterir.

```
virtual BOOL IsExternalDispatchSafe();
```

### <a name="return-value"></a>Dönüş Değeri

FALSE döndürür.

## <a name="cdhtmldialogloadfromresource"></a><a name="loadfromresource"></a> CDHtmlDialog:: LoadFromResource

Belirtilen kaynağı DHTML iletişim kutusunda WebBrowser denetimine yükler.

```
BOOL LoadFromResource(LPCTSTR lpszResource);
BOOL LoadFromResource(UINT nRes);
```

### <a name="parameters"></a>Parametreler

*lpszResource*<br/>
Yüklenecek kaynağın adını içeren bir dize işaretçisi.

*nRes*<br/>
Yüklenecek kaynağın KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

## <a name="cdhtmldialogm_busehtmltitle"></a><a name="m_busehtmltitle"></a> CDHtmlDialog:: m_bUseHtmlTitle

HTML belgesinin başlığının iletişim kutusu başlığı olarak kullanılıp kullanılmayacağını gösterir.

```
BOOL m_bUseHtmlTitle;
```

### <a name="remarks"></a>Açıklamalar

**E**_ **busehtmltitle** değeri true ise, iletişim kutusu başlığı html belgesinin başlığına eşit olarak ayarlanır; Aksi takdirde, iletişim kutusu kaynağındaki başlık kullanılır.

## <a name="cdhtmldialogm_nhtmlresid"></a><a name="m_nhtmlresid"></a> CDHtmlDialog:: m_nHtmlResID

Görüntülenecek HTML kaynağının kaynak KIMLIĞI.

```
UINT m_nHtmlResID;
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCHtmlHttp#5](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_5.cpp)]

## <a name="cdhtmldialogm_pbrowserapp"></a><a name="m_pbrowserapp"></a> CDHtmlDialog:: m_pBrowserApp

Web tarayıcı uygulaması için bir işaretçi.

```
CComPtr <IWebBrowser2> m_pBrowserApp;
```

## <a name="cdhtmldialogm_sphtmldoc"></a><a name="m_sphtmldoc"></a> CDHtmlDialog:: m_spHtmlDoc

HTML belgesi işaretçisi.

```
CComPtr<IHTMLDocument2> m_spHtmlDoc;
```

## <a name="cdhtmldialogm_strcurrenturl"></a><a name="m_strcurrenturl"></a> CDHtmlDialog:: m_strCurrentUrl

Geçerli URL.

```
CString m_strCurrentUrl;
```

## <a name="cdhtmldialogm_szhtmlresid"></a><a name="m_szhtmlresid"></a> CDHtmlDialog:: m_szHtmlResID

HTML kaynak KIMLIĞININ dize sürümü.

```
LPTSTR m_szHtmlResID;
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCHtmlHttp#6](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]

## <a name="cdhtmldialognavigate"></a><a name="navigate"></a> CDHtmlDialog:: gezinmek

*LpszURL*tarafından belirtilen URL tarafından tanımlanan kaynağa gider.

```cpp
void Navigate(
    LPCTSTR lpszURL,
    DWORD dwFlags = 0,
    LPCTSTR lpszTargetFrameName = NULL,
    LPCTSTR lpszHeaders = NULL,
    LPVOID lpvPostData = NULL,
    DWORD dwPostDataLen = 0);
```

### <a name="parameters"></a>Parametreler

*lpszURL*<br/>
Hedeflenecek URL 'YI içeren bir dize işaretçisi.

*dwFlags*<br/>
Kaynağın geçmiş listesine eklenip eklenmeyeceğini, önbelleğe okunup okunmayacağını veya önbellekten yazılacağını ve kaynağın yeni bir pencerede görüntülenip görüntülenmeyeceğini belirten bir değişkenin bayrakları. Değişken, [Browsernavsabitleri](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768360\(v=vs.85\)) numaralandırması tarafından tanımlanan değerlerin bir birleşimi olabilir.

*lpszTargetFrameName*<br/>
Kaynağın görüntüleneceği çerçevenin adını içeren bir dize işaretçisi.

*lpszHeaders*<br/>
Sunucuya göndermek için HTTP üstbilgilerini belirten bir değere yönelik işaretçi. Bu üstbilgiler varsayılan Internet Explorer üst bilgilerine eklenir. Üst bilgiler, sunucuda gereken eylem, sunucuya geçirilen verilerin türü veya bir durum kodu gibi bilgileri belirtebilir. URL bir HTTP URL 'SI değilse bu parametre yoksayılır.

*lpvPostData*<br/>
HTTP POST hareketiyle gönderilecek verilerin bir işaretçisi. Örneğin, POST işlemi bir HTML formu tarafından toplanan verileri göndermek için kullanılır. Bu parametre hiçbir gönderi verisi belirtmezse, `Navigate` BIR http get işlemi yayınlar. URL bir HTTP URL 'SI değilse bu parametre yoksayılır.

*dwPostDataLen*<br/>
HTTP POST hareketiyle gönderilecek veriler. Örneğin, POST işlemi bir HTML formu tarafından toplanan verileri göndermek için kullanılır. Bu parametre hiçbir gönderi verisi belirtmezse, `Navigate` BIR http get işlemi yayınlar. URL bir HTTP URL 'SI değilse bu parametre yoksayılır.

## <a name="cdhtmldialogonbeforenavigate"></a><a name="onbeforenavigate"></a> CDHtmlDialog:: OnBeforeNavigate

Bir gezinti gerçekleşmeden önce bir olayın tetiklenmesine neden olmak için Framework tarafından çağırılır.

```
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
Bir `IDispatch` nesne işaretçisi.

*szUrl*<br/>
Gidilecek URL 'YI içeren bir dize işaretçisi.

## <a name="cdhtmldialogondocumentcomplete"></a><a name="ondocumentcomplete"></a> CDHtmlDialog:: Ondocumenttamamlanmıştır

Bir belge READYSTATE_COMPLETE durumuna geldiğinde bir uygulamaya bildirimde bulunan Framework tarafından çağırılır.

```
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
Bir `IDispatch` nesne işaretçisi.

*szUrl*<br/>
Gezindiği URL 'YI içeren bir dize işaretçisi.

## <a name="cdhtmldialogondocwindowactivate"></a><a name="ondocwindowactivate"></a> CDHtmlDialog:: OnDocWindowActivate

Belge penceresi etkinleştirildiğinde veya devre dışı bırakıldığında Framework tarafından çağırılır.

```
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>Parametreler

*fActivate*<br/>
Windows SDK, [ıdochostuihandler:: OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\)) Içindeki *factivate* öğesine bakın.

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, CDHtmlDialog 'ın [ıdochostuihandler:: OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))uygulamasıdır.

## <a name="cdhtmldialogonframewindowactivate"></a><a name="onframewindowactivate"></a> CDHtmlDialog:: OnFrameWindowActivate

Çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında Framework tarafından çağırılır.

```
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>Parametreler

*fActivate*<br/>
Windows SDK, [ıdochostuihandler:: OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\)) Içindeki *factivate* bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, CDHtmlDialog 'ın [ıdochostuihandler:: OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))uygulamasıdır.

## <a name="cdhtmldialogoninitdialog"></a><a name="oninitdialog"></a> CDHtmlDialog:: OnInitDialog

WM_INITDIALOG iletisine yanıt olarak çağırılır.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu ileti,, veya çağrıları sırasında iletişim kutusu görüntülenmeden `Create` `CreateIndirect` `DoModal` hemen önce gerçekleşen iletişim kutusuna gönderilir.

İletişim kutusu başlatıldığında özel işlem gerçekleştirmeniz gerekiyorsa, bu üye işlevi geçersiz kılın. Geçersiz kılınan sürümde, önce temel sınıfı çağırın, `OnInitDialog` ancak dönüş değerini yok sayın. Normalde geçersiz kılınan üye işlevinizden doğru bir değer döndürülecektir.

Windows, `OnInitDialog` işlevi ileti haritanız yerine tüm Microsoft Foundation Class Kitaplığı iletişim kutularında ortak olan standart genel iletişim kutusu yordamı aracılığıyla çağırır. bu nedenle, bu üye işlevi için bir ileti eşleme girişi gerekmez.

## <a name="cdhtmldialogonnavigatecomplete"></a><a name="onnavigatecomplete"></a> CDHtmlDialog:: Onnavigatetamamlanmıştır

Belirtilen URL 'nin gezintisi tamamlandıktan sonra Framework tarafından çağırılır.

```
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
Bir `IDispatch` nesne işaretçisi.

*szUrl*<br/>
Gezindiği URL 'YI içeren bir dize işaretçisi.

## <a name="cdhtmldialogresizeborder"></a><a name="resizeborder"></a> CDHtmlDialog:: ResizeBorder

Nesnenin kenarlık alanını yeniden boyutlandırmak için ihtiyacı olan nesneyi uyarır.

```
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fRameWindow);
```

### <a name="parameters"></a>Parametreler

*prcBorder*<br/>
Windows SDK [ıdochostuihandler:: ResizeBorder](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\)) Içindeki *prcborder* bölümüne bakın.

*pUIWindow*<br/>
Windows SDK içindeki *Puıwindow* ' a bakın `IDocHostUIHandler::ResizeBorder` .

*fFrameWindow*<br/>
Windows SDK içindeki *Fframewindow* öğesine bakın `IDocHostUIHandler::ResizeBorder` .

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

## <a name="cdhtmldialogsetcontrolproperty"></a><a name="setcontrolproperty"></a> CDHtmlDialog:: SetControlProperty

ActiveX denetiminin özelliğini yeni bir değere ayarlar.

```cpp
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
ActiveX denetiminin HTML KIMLIĞI.

*Dı*<br/>
Ayarlanacak özelliğin dağıtım KIMLIĞI.

*pVar*<br/>
Yeni özellik değerini içeren bir DEĞIŞKEN işaretçisi.

*pdispControl*<br/>
ActiveX denetiminin arabirimine yönelik işaretçi `IDispatch` .

*szPropName*<br/>
Ayarlanacak özelliğin adını içeren dize.

## <a name="cdhtmldialogsetelementhtml"></a><a name="setelementhtml"></a> CDHtmlDialog:: SetElementHtml

`innerHTML`BIR HTML öğesinin özelliğini ayarlar.

```cpp
void SetElementHtml(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementHtml(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>Parametreler

*szElementId*<br/>
Bir HTML öğesinin KIMLIĞI.

*bstrText*<br/>
Özelliğin yeni değeri `innerHTML` .

*punkElem*<br/>
`IUnknown`HTML öğesinin işaretçisi.

## <a name="cdhtmldialogsetelementproperty"></a><a name="setelementproperty"></a> CDHtmlDialog:: SetElementProperty

Bir HTML öğesinin özelliğini ayarlar.

```cpp
void SetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId,
    VARIANT* pVar);
```

### <a name="parameters"></a>Parametreler

*szElementId*<br/>
Bir HTML öğesinin KIMLIĞI.

*Dı*<br/>
Ayarlanacak özelliğin dağıtım KIMLIĞI.

*pVar*<br/>
Özelliğin yeni değeri.

## <a name="cdhtmldialogsetelementtext"></a><a name="setelementtext"></a> CDHtmlDialog:: SetElementText

`innerText`BIR HTML öğesinin özelliğini ayarlar.

```cpp
void SetElementText(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementText(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>Parametreler

*szElementId*<br/>
Bir HTML öğesinin KIMLIĞI.

*bstrText*<br/>
Özelliğin yeni değeri `innerText` .

*punkElem*<br/>
`IUnknown`HTML öğesinin işaretçisi.

## <a name="cdhtmldialogsetexternaldispatch"></a><a name="setexternaldispatch"></a> CDHtmlDialog:: SetExternalDispatch

Konağın `IDispatch` arabirimini ayarlar.

```cpp
void SetExternalDispatch(IDispatch* pdispExternal);
```

### <a name="parameters"></a>Parametreler

*pdispExternal*<br/>
Yeni `IDispatch` arabirim.

## <a name="cdhtmldialogsethostflags"></a><a name="sethostflags"></a> CDHtmlDialog:: SetHostFlags

Konak Kullanıcı arabirimi bayraklarını ayarlar.

```cpp
void SetHostFlags(DWORD dwFlags);
```

### <a name="parameters"></a>Parametreler

*dwFlags*<br/>
Olası değerler için Windows SDK [Dochostuiflag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753277\(v=vs.85\)) bölümüne bakın.

## <a name="cdhtmldialogshowcontextmenu"></a><a name="showcontextmenu"></a> CDHtmlDialog:: ShowContextMenu

Bağlam menüsü görüntülenmek üzereyken çağırılır.

```
STDMETHOD(ShowContextMenu)(
    DWORD dwID,
    POINT* ppt,
    IUnknown* pcmdtReserved,
    IDispatch* pdispReserved);
```

### <a name="parameters"></a>Parametreler

*Dwıd*<br/>
Windows SDK [ıdochostuihandler:: ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\)) Içindeki *dwıd* öğesine bakın.

*PPT*<br/>
Windows SDK içindeki *PPT* 'yi inceleyin `IDocHostUIHandler::ShowContextMenu` .

*pcmdtReserved*<br/>
Windows SDK içindeki *pcmdtReserved* bakın `IDocHostUIHandler::ShowContextMenu` .

*Pdiskorundu*<br/>
Windows SDK içindeki *Pdiskoruna* bakın `IDocHostUIHandler::ShowContextMenu` .

### <a name="return-value"></a>Dönüş Değeri

S_FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, CDHtmlDialog 'ın [ıdochostuihandler:: ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))uygulamasıdır.

## <a name="cdhtmldialogshowui"></a><a name="showui"></a> CDHtmlDialog:: ShowUI

Konağın Kullanıcı arabirimini gösterir.

```
STDMETHOD(ShowUI)(
    DWORD dwID,
    IOleInPlaceActiveObject* pActiveObject,
    IOleCommandTarget* pCommandTarget,
    IOleInPlaceFrame* pFrame,
    IOleInPlaceUIWindow* pDoc);
```

### <a name="parameters"></a>Parametreler

*Dwıd*<br/>
Windows SDK, [ıdochostuihandler:: ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\)) öğesinde *dwıd* öğesine bakın.

*pActiveObject*<br/>
Windows SDK içindeki *d pActiveObject* öğesine bakın `IDocHostUIHandler::ShowUI` .

*pCommandTarget*<br/>
Windows SDK içindeki *pCommandTarget* bakın `IDocHostUIHandler::ShowUI` .

*pFrame*<br/>
Windows SDK içindeki *Pframe* bölümüne bakın `IDocHostUIHandler::ShowUI` .

*pDoc*<br/>
Windows SDK içindeki *pDoc* bölümüne bakın `IDocHostUIHandler::ShowUI` .

### <a name="return-value"></a>Dönüş Değeri

S_FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, CDHtmlDialog 'ın [ıdochostuihandler:: ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))uygulamasıdır.

## <a name="cdhtmldialogtranslateaccelerator"></a><a name="translateaccelerator"></a> CDHtmlDialog:: TranslateAccelerator

Menü Hızlandırıcısı anahtar iletilerini işlemek için çağırılır.

```
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,
    const GUID* pguidCmdGroup,
    DWORD nCmdID);
```

### <a name="parameters"></a>Parametreler

*lpMsg*<br/>
Windows SDK için bkz. [ıdochostuihandler:: TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\)) öğesinde *lpMsg* .

*pguidCmdGroup*<br/>
Windows SDK içindeki *pguidCmdGroup* öğesine bakın `IDocHostUIHandler::TranslateAccelerator` .

*nCmdID*<br/>
Windows SDK *nCmdID* bölümüne bakın `IDocHostUIHandler::TranslateAccelerator` .

### <a name="return-value"></a>Dönüş Değeri

S_FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, CDHtmlDialog 'ın [ıdochostuihandler:: TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))' in uygulamasıdır.

## <a name="cdhtmldialogtranslateurl"></a><a name="translateurl"></a> CDHtmlDialog:: TranslateUrl

Yüklenecek URL 'YI değiştirmek için çağırılır.

```
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,
    OLECHAR* pchURLIn,
    OLECHAR** ppchURLOut);
```

### <a name="parameters"></a>Parametreler

*dwTranslate*<br/>
Windows SDK [ıdochostuihandler:: TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\)) Içinde *dwtranslate* öğesine bakın.

*pchURLIn*<br/>
Windows SDK 'de *Pchurlin* bölümüne bakın `IDocHostUIHandler::TranslateUrl` .

*ppchURLOut*<br/>
Windows SDK içindeki *Ppchurlout* bölümüne bakın `IDocHostUIHandler::TranslateUrl` .

### <a name="return-value"></a>Dönüş Değeri

S_FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, CDHtmlDialog 'ın [ıdochostuihandler:: TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))'nin uygulamasıdır.

## <a name="cdhtmldialogupdateui"></a><a name="updateui"></a> CDHtmlDialog:: UpdateUI

Ana bilgisayara komut durumunun değiştiğini bildirmek için çağırılır.

```
STDMETHOD(UpdateUI)(void);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi, CDHtmlDialog 'ın [ıdochostuihandler:: UpdateUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))uygulamasıdır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek DHtmlExplore](../../overview/visual-cpp-samples.md)<br/>
[DDX_DHtml Yardımcısı makroları](#ddx_dhtml_helper_macros)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
