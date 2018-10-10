---
title: CPropertySheet sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPropertySheet
- AFXDLGS/CPropertySheet
- AFXDLGS/CPropertySheet::CPropertySheet
- AFXDLGS/CPropertySheet::AddPage
- AFXDLGS/CPropertySheet::Construct
- AFXDLGS/CPropertySheet::Create
- AFXDLGS/CPropertySheet::DoModal
- AFXDLGS/CPropertySheet::EnableStackedTabs
- AFXDLGS/CPropertySheet::EndDialog
- AFXDLGS/CPropertySheet::GetActiveIndex
- AFXDLGS/CPropertySheet::GetActivePage
- AFXDLGS/CPropertySheet::GetPage
- AFXDLGS/CPropertySheet::GetPageCount
- AFXDLGS/CPropertySheet::GetPageIndex
- AFXDLGS/CPropertySheet::GetTabControl
- AFXDLGS/CPropertySheet::MapDialogRect
- AFXDLGS/CPropertySheet::OnInitDialog
- AFXDLGS/CPropertySheet::PressButton
- AFXDLGS/CPropertySheet::RemovePage
- AFXDLGS/CPropertySheet::SetActivePage
- AFXDLGS/CPropertySheet::SetFinishText
- AFXDLGS/CPropertySheet::SetTitle
- AFXDLGS/CPropertySheet::SetWizardButtons
- AFXDLGS/CPropertySheet::SetWizardMode
- AFXDLGS/CPropertySheet::m_psh
dev_langs:
- C++
helpviewer_keywords:
- CPropertySheet [MFC], CPropertySheet
- CPropertySheet [MFC], AddPage
- CPropertySheet [MFC], Construct
- CPropertySheet [MFC], Create
- CPropertySheet [MFC], DoModal
- CPropertySheet [MFC], EnableStackedTabs
- CPropertySheet [MFC], EndDialog
- CPropertySheet [MFC], GetActiveIndex
- CPropertySheet [MFC], GetActivePage
- CPropertySheet [MFC], GetPage
- CPropertySheet [MFC], GetPageCount
- CPropertySheet [MFC], GetPageIndex
- CPropertySheet [MFC], GetTabControl
- CPropertySheet [MFC], MapDialogRect
- CPropertySheet [MFC], OnInitDialog
- CPropertySheet [MFC], PressButton
- CPropertySheet [MFC], RemovePage
- CPropertySheet [MFC], SetActivePage
- CPropertySheet [MFC], SetFinishText
- CPropertySheet [MFC], SetTitle
- CPropertySheet [MFC], SetWizardButtons
- CPropertySheet [MFC], SetWizardMode
- CPropertySheet [MFC], m_psh
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50b1816320521f8ad20ee64fc4a051f938e902ec
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890783"
---
# <a name="cpropertysheet-class"></a>CPropertySheet sınıfı

Özellik sayfaları iletişim kutusu olarak da bilinen temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CPropertySheet : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPropertySheet::CPropertySheet](#cpropertysheet)|Oluşturur bir `CPropertySheet` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPropertySheet::AddPage](#addpage)|Bir sayfa için özellik sayfası ekler.|
|[CPropertySheet::Construct](#construct)|Oluşturur bir `CPropertySheet` nesne.|
|[CPropertySheet::Create](#create)|Kalıcı olmayan özellik sayfası görüntüler.|
|[CPropertySheet::DoModal](#domodal)|Bir kalıcı özellik sayfasını görüntüler.|
|[CPropertySheet::EnableStackedTabs](#enablestackedtabs)|Özellik sayfası Yığılmış veya kayan sekme kullanıp kullanmadığını belirtir.|
|[CPropertySheet::EndDialog](#enddialog)|Özellik sayfası sonlandırır.|
|[CPropertySheet::GetActiveIndex](#getactiveindex)|Etkin sayfa özellik sayfasının dizinini alır.|
|[CPropertySheet::GetActivePage](#getactivepage)|Etkin sayfa nesnesini döndürür.|
|[CPropertySheet::GetPage](#getpage)|Belirtilen sayfa için bir işaretçi alır.|
|[CPropertySheet::GetPageCount](#getpagecount)|Özellik sayfasında sayfa sayısını alır.|
|[CPropertySheet::GetPageIndex](#getpageindex)|Belirtilen sayfaya özellik sayfasının dizinini alır.|
|[CPropertySheet::GetTabControl](#gettabcontrol)|Sekme denetimi için bir işaretçi alır.|
|[CPropertySheet::MapDialogRect](#mapdialogrect)|İletişim kutusu birimleri bir dikdörtgen ekran birimlerine dönüştürür.|
|[CPropertySheet::OnInitDialog](#oninitdialog)|Özellik sayfası başlatıcısını büyütmek için geçersiz kılın.|
|[CPropertySheet::PressButton](#pressbutton)|Bir özellik sayfasında belirtilen düğmesi seçimi benzetimini yapar.|
|[CPropertySheet::RemovePage](#removepage)|Bir özellik sayfası'ndan kaldırır.|
|[CPropertySheet::SetActivePage](#setactivepage)|Programlı olarak etkin olan sayfa nesnesine ayarlar.|
|[CPropertySheet::SetFinishText](#setfinishtext)|Son düğmesini metnini ayarlar.|
|[CPropertySheet::SetTitle](#settitle)|Özellik sayfası başlığını ayarlar.|
|[CPropertySheet::SetWizardButtons](#setwizardbuttons)|Sihirbaz düğmeleri sağlar.|
|[CPropertySheet::SetWizardMode](#setwizardmode)|Sihirbaz modu sağlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPropertySheet::m_psh](#m_psh)|Windows [PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2) yapısı. Temel özellik sayfası parametreleri erişim sağlar.|

## <a name="remarks"></a>Açıklamalar

Bir özellik sayfası oluşan bir `CPropertySheet` nesnesi ve bir veya daha fazla [CPropertyPage](../../mfc/reference/cpropertypage-class.md) nesneleri. Framework bir özellik sayfası bir dizi sekme dizinlerini ve şu anda seçili sayfasını içeren bir alan içeren bir pencere olarak görüntülenir. Kullanıcı uygun sekmesini kullanarak belirli bir sayfaya götürür.

`CPropertySheet` Genişletilmiş için destek sağlayan [PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2) Windows 98 ve Windows NT 2000'de kullanıma sunulan yapısı. Yapısı, ek bayrakları ve "Filigran" arka plan bit eşlem kullanma desteği üyeleri içerir.

Bu yeni görüntüleri otomatik olarak, özellik sayfası nesnesi içinde görüntülemek için yapılan çağrıda bit eşlem ve palet görüntüleri için geçerli değerler geçirmek [CPropertySheet::Construct](#construct) veya [CPropertySheet::CPropertySheet](#cpropertysheet).

Olsa da `CPropertySheet` türünden türetilmediğinden [CDialog](../../mfc/reference/cdialog-class.md), yöneten bir `CPropertySheet` nesnedir yönetme gibi bir `CDialog` nesne. Örneğin, iki aşamalı yapımı bir özellik sayfası oluşturulmasını gerektirir: oluşturucusunu çağırın ve ardından arama [DoModal](#domodal) bir kalıcı özellik sayfası için veya [Oluştur](#create) modelsiz bir özellik sayfası için. `CPropertySheet` Oluşturucular iki tür vardır: [CPropertySheet::Construct](#construct) ve [CPropertySheet::CPropertySheet](#cpropertysheet).

Oluşturduğunuzda bir `CPropertySheet` bazı nesne [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) bir ilk fırsat özel durum oluşmasına neden olabilir. Bu sayfa oluşturulmadan önce özellik sayfasının stilini değiştirme çalışılırken sistemden sonuçlanır. Bu özel durumdan kaçınmak için oluşturduğunuzda aşağıdaki stilleri ayarladığınızdan emin olun, `CPropertySheet`:

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

Aşağıdaki stilleri isteğe bağlıdır ve ilk fırsat özel durum neden olmaz:

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

Diğer `Window Styles` yasaklanmış olduğuna ve bunları etkinleştirmemelisiniz.

Arasında veri değişimi bir `CPropertySheet` nesnesi ve bir dış nesnesi ile veri değişimi için benzer bir `CDialog` nesne. Önemli fark bir özellik sayfası ayarlarını üye değişkenleri genellikle olduğunu `CPropertyPage` nesneler yerine, `CPropertySheet` nesnenin kendisi.

Sekme iletişim kutusu, kullanıcı cihazı kurarken ya da bir bülten oluşturma gibi bir işlemin adımlarında rehberlik özellik sayfaları dizisi ile bir özellik sayfasından oluşan bir sihirbaz adlı bir türünü oluşturabilirsiniz. Sihirbaz türü sekme iletişim kutusu, özellik sayfaları sekmeleri yoktur ve aynı anda yalnızca bir özellik sayfası görünür. Yerine ayrıca **Tamam** ve **şimdi Uygula** sihirbaz türü sekme iletişim kutusu düğmeleri, sahip bir **geri** düğmesi, bir **sonraki** veya  **Son** düğmesi, bir **iptal** düğme ve bir **yardımcı** düğmesi.

Bir sihirbaz türü iletişim kutusu oluşturmak için çağrı ancak standart bir özellik sayfası oluşturmak için izlemeniz gerekir adımlarının aynısını izleyin [SetWizardMode](#setwizardmode) çağırmadan önce [DoModal](#domodal). Sihirbaz düğmeleri etkinleştirmek için çağrı [SetWizardButtons](#setwizardbuttons), kendi işlev ve görünümünü özelleştirmek için bayrakları kullanılarak. Etkinleştirmek için **son** düğmesi, çağrı [SetFinishText](#setfinishtext) kullanıcı sihirbazın son sayfasında eylem gerçekleştirildikten sonra.

Nasıl kullanılacağı hakkında daha fazla bilgi için `CPropertySheet` nesneleri başlıklı makaleye bakın [özellik bölümleri ve özellik sayfaları](../../mfc/property-sheets-and-property-pages-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPropertySheet`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdlgs.h

##  <a name="addpage"></a>  CPropertySheet::AddPage

Özellik sayfasında sağlanan sayfasında en sağdaki sekmesi ekler.

```
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*fsayfa*<br/>
Özellik sayfasına eklenecek sayfayı işaret eder. NULL olamaz.

### <a name="remarks"></a>Açıklamalar

Özellik sayfası görünmesini istediğiniz sırayla soldan sağa sayfaları ekleyin.

`AddPage` ekler [CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage) nesnesini `CPropertySheet` nesne liste sayfalarının kullanıcının ancak aslında sayfa için pencere oluşturmaz. Bu sayfa kullanıcı seçene kadar framework sayfa için pencere oluşturulmasını erteler.

Bir özellik sayfasını kullanarak eklediğinizde `AddPage`, `CPropertySheet` üst `CPropertyPage`. Özellik sayfasından özellik sayfasına erişmek için çağrı [CWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent).

Çağırmak için özellik sayfası pencerenin oluşturulmasını kadar beklenecek gerekli değil `AddPage`. Genellikle, çağıracak `AddPage` çağırmadan önce [DoModal](#domodal) veya [Oluştur](#create).

Eğer `AddPage` özellik sayfasını görüntüleme sonra yeni eklenen sayfa sekmesi satır yansıtır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#129](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]

##  <a name="construct"></a>  CPropertySheet::Construct

Oluşturur bir `CPropertySheet` nesne.

```
void Construct(
    UINT nIDCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);


void Construct(
    LPCTSTR pszCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);


void Construct(
    UINT nIDCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);


void Construct(
    LPCTSTR pszCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);
```

### <a name="parameters"></a>Parametreler

*nIDCaption*<br/>
Özellik sayfası için kullanılacak resim yazısı kimliği.

*pParentWnd*<br/>
Özellik sayfasının üst pencere işaretçisi. NULL ise, ana pencereyi uygulamanın ana pencere olacaktır.

*iSelectPage*<br/>
Başlangıçta en üstte olacak sayfasının dizini. Varsayılan sayfasına eklenen ilk sayfa verilmiştir.

*pszCaption*<br/>
Özellik sayfası için kullanılacak resim yazısını içeren bir dize işaretçisi. NULL olamaz.

*hbmWatermark*<br/>
Özellik sayfasının Filigran bit eşlem işleyin.

*hpalWatermark*<br/>
Filigran bit eşlem ve/veya üst bilgi bit eşlem paleti işleyin.

*hbmHeader*<br/>
Özellik sayfasının başlığı bit eşlem işleyin.

### <a name="remarks"></a>Açıklamalar

Bir sınıf oluşturucuları olmayan zaten çağırmışsa, bu üye işlevini çağırın. Örneğin, çağrı `Construct` ne zaman bildirmek veya dizi ayırmak `CPropertySheet` nesneleri. Diziler söz konusu olduğunda, çağırmalısınız `Construct` dizideki her üyesi için.

Özellik sayfasını görüntülemek için çağrı [DoModal](#domodal) veya [Oluştur](#create). Özellik sayfası için başlık çubuğunda yer alan ilk parametre dize yer alır.

Üçüncü veya dördüncü prototiplerini kullanırsanız, filigran ve/veya üst bilgi görüntüleri otomatik olarak görüntüleyebilirsiniz `Construct`, yukarıda listelenen ve geçerli değerlerini geçirirsiniz *hbmWatermark*, *hpalWatermark* , ve/veya *hbmHeader* parametreleri.

### <a name="example"></a>Örnek

Aşağıdaki örnek, altında gösterir, koşulda çağıracak `Construct`.

[!code-cpp[NVC_MFCDocView#130](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]

##  <a name="cpropertysheet"></a>  CPropertySheet::CPropertySheet

Oluşturur bir `CPropertySheet` nesne.

```
CPropertySheet();


explicit CPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);


explicit CPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);


CPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);


CPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);
```

### <a name="parameters"></a>Parametreler

*nIDCaption*<br/>
Özellik sayfası için kullanılacak resim yazısı kimliği.

*pParentWnd*<br/>
Özellik sayfasının üst pencere işaret. NULL ise, ana pencereyi uygulamanın ana pencere olacaktır.

*iSelectPage*<br/>
Başlangıçta en üstte olacak sayfasının dizini. Varsayılan sayfasına eklenen ilk sayfa verilmiştir.

*pszCaption*<br/>
Özellik sayfası için kullanılacak resim yazısını içeren bir dize işaret eder. NULL olamaz.

*hbmWatermark*<br/>
Arka plan bit eşlem özellik sayfası için bir tanıtıcı.

*hpalWatermark*<br/>
Filigran bit eşlem ve/veya üst bilgi bit eşlem paletini işleyici.

*hbmHeader*<br/>
Özellik sayfasının başlığı bit eşlem işleyici.

### <a name="remarks"></a>Açıklamalar

Özellik sayfasını görüntülemek için çağrı [DoModal](#domodal) veya [Oluştur](#create). Özellik sayfası için başlık çubuğunda yer alan ilk parametre dize yer alır.

Birden çok parametre (örneğin, bir dizi kullanıyorsa) varsa, [oluşturmak](#construct) yerine `CPropertySheet`.

Üçüncü veya dördüncü prototiplerini kullanırsanız, filigran ve/veya üst bilgi görüntüleri otomatik olarak görüntüleyebilirsiniz `CPropertySheet`, yukarıdaki ve geçerli değerlerini geçirirsiniz *hbmWatermark*, *hpalWatermark*, ve / veya *hbmHeader* parametreleri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#131](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]

##  <a name="create"></a>  CPropertySheet::Create

Kalıcı olmayan özellik sayfası görüntüler.

```
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)-1,
    DWORD dwExStyle = 0);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Üst penceresine işaret eder. NULL ise, Masaüstü üst öğesidir.

*dwStyle*<br/>
Özellik sayfası için pencere stilleri. Kullanılabilir stiller tam bir listesi için bkz. [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*dwExStyle*<br/>
Özellik sayfası için genişletilmiş pencere stilleri. Kullanılabilir stiller tam bir listesi için bkz. [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfası başarıyla oluşturulursa, sıfır olmayan; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağrı `Create` oluşturucusu içinde olabilir veya Oluşturucu çağrıldıktan sonra çağırabilirsiniz.

-1 olarak geçirerek ifade varsayılan stili *dwStyle*, aslında WS_SYSMENU olduğu&#124;WS_POPUP&#124;ws_captıon&#124;DS_MODALFRAME&#124;DS_CONTEXTHELP&#124;ws_vısıble. Varsayılan pencere stili ifade 0 olarak geçirerek, Genişletilmiş *dwExStyle*, aslında WS_EX_DLGMODALFRAME olduğu.

`Create` Üye işlevinin döndürdüğü özellik sayfası oluşturduktan hemen sonra. Özellik sayfası yok etmek için çağrı [CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow).

Kalıcı olmayan özellik sayfaları çağrısı ile görüntülenen `Create` kalıcı özellik sayfaları gibi Tamam, iptal, şimdi Uygula ve Yardım düğmeleri izniniz yok. İstenen düğmelerinin kullanıcı tarafından oluşturulması gerekir.

Bir kalıcı özellik sayfasını görüntülemek için çağrı [DoModal](#domodal) yerine.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#132](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]

[!code-cpp[NVC_MFCDocView#133](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]

##  <a name="domodal"></a>  CPropertySheet::DoModal

Bir kalıcı özellik sayfasını görüntüler.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

IDOK veya işlev başarılı olursa IDCANCEL; Aksi durumda 0 veya -1. Sihirbaz özellik sayfası kurmuştur, (bkz [SetWizardMode](#setwizardmode)), `DoModal` ID_WIZFINISH ya da IDCANCEL döndürür.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri, özellik sayfası kapalı denetim Kimliğine karşılık gelir. Bu işlev döndürdükten sonra özellik sayfası ve tüm sayfaları için karşılık gelen windows yok edildikten sonra. Nesnelerinin kendileri varolmaya devam eder. Genellikle, verileri alır [CPropertyPage](../../mfc/reference/cpropertypage-class.md) sonra nesneleri `DoModal` IDOK döndürür.

Kalıcı olmayan özellik sayfası görüntülemek için çağrı [Oluştur](#create) yerine.

Özellik sayfasında karşılık gelen iletişim kaynaktan oluşturulduğunda, ilk şans özel durum neden olabilir. Bu sayfa oluşturulmadan önce gerekli stil iletişim kutusu kaynağı stilini değiştirme özellik sayfasından sonuçlanır. Kaynaklar genellikle salt okunur olduğundan, bu özel durum neden olur. Sistem özel durumu işleyen ve değiştirilen kaynağı bir kopyasını oluşturur. İlk fırsat özel durum, bu nedenle yoksayılabilir.

> [!NOTE]
>  Zaman uyumsuz özel durum işleme modeliyle derleme yapıyorsanız bu özel işletim sistemi tarafından işlenmesi gerekir. Özel durum işleme modelleri hakkında daha fazla bilgi için bkz: [/EH (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md). Bu durumda, çağrıları kaydırılacak `CPropertySheet::DoModal` C++ try-catch bloğu ile yakalama işleme tüm özel durumlar, örneğin, `catch (...)`. Bu blok işletim sistemi ve öngörülemeyen davranışlara neden için amaçlanan özel durum işlemesi. Ancak, erişim ihlali özel durum ile işletim sistemine geçirildiği işleme belirli özel durum türleri veya yapılandırılmış özel durum işleme ile C++ özel durumu güvenli bir şekilde kullanabilirsiniz.

Bu ilk fırsat özel durum oluşturmaktan kaçınmak için el ile özellik sayfası doğru olduğunu garanti edebilir [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles). Bir özellik sayfası için aşağıdaki stilleri ayarlamanız gerekir:

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

Aşağıdaki isteğe bağlı stilleri ilk fırsat özel durum neden olmadan kullanabilirsiniz:

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

Özellik sayfaları ile uyumlu olmadığı için diğer tüm Windows stillerini devre dışı bırakın. Bu öneri genişletilmiş stilleri için geçerli değildir. Bu standart stilleri uygun şekilde ayarlamaktan özellik sayfası değiştirilmesi gerekmez ve ilk fırsat özel durum oluşturma kaçınır garanti eder.

### <a name="example"></a>Örnek

Örneğin bakın [CPropertySheet::AddPage](#addpage).

##  <a name="enablestackedtabs"></a>  CPropertySheet::EnableStackedTabs

Bir özellik sayfası sekmeleri satırlarını yığın görüntülenip görüntülenmeyeceğini gösterir.

```
void EnableStackedTabs(BOOL bStacked);
```

### <a name="parameters"></a>Parametreler

*bStacked*<br/>
Yığılmış sekmeleri ve özellik sayfasında etkin olup olmadığını gösterir. Yığılmış satır etiket ayarlayarak devre dışı bırakmanız *bStacked* false.

### <a name="remarks"></a>Açıklamalar

Özellik sayfası genişliği tek bir satır içinde sığmayacak kadar çok daha fazla sekme bir özellik sayfası varsa, varsayılan olarak, sekmeleri birden çok satır yığın. Kayan sekme yığın sekme yerine kullanılacak arama `EnableStackedTabs` ile *bStacked* çağırmadan önce FALSE olarak ayarlanmış [DoModal](#domodal) veya [Oluştur](#create).

Çağırmalısınız `EnableStackedTabs` oluştururken bir kalıcı veya kalıcı olmayan özellik sayfası. Bu stil birleştirmek için bir `CPropertySheet`-türetilmiş sınıf, bir ileti işleyicisi için WM_CREATE yazma. Geçersiz kılınan sürümünde [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate), çağrı `EnableStackedTabs( FALSE )` temel sınıf uygulamasına çağırmadan önce.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#134](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]

##  <a name="enddialog"></a>  CPropertySheet::EndDialog

Özellik sayfası sonlandırır.

```
void EndDialog(int nEndID);
```

### <a name="parameters"></a>Parametreler

*nEndID*<br/>
Özellik sayfası dönüş değeri olarak kullanılacak tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Tamam, iptal ya da Kapat düğmesine basıldığında bu üye işlevi framework tarafından çağırılır. Çağrısı, bir olay oluşursa, bu üye işlevi özellik sayfasını kapatmalısınız.

Bu üye işlevi yalnızca bir kalıcı iletişim kutusu ile kullanılır.

### <a name="example"></a>Örnek

Örneğin bakın [CPropertySheet::PressButton](#pressbutton).

##  <a name="getactiveindex"></a>  CPropertySheet::GetActiveIndex

Özellik sayfası pencerenin etkin sayfa dizini sayısını alır ve ardından parametre olarak döndürülen dizin numarasını kullanır `GetPage`.

```
int GetActiveIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizin etkin sayfa sayısı.

### <a name="example"></a>Örnek

Örneğin bakın [CPropertySheet::GetActivePage](#getactivepage).

##  <a name="getactivepage"></a>  CPropertySheet::GetActivePage

Özellik sayfası pencerenin etkin sayfa alır.

```
CPropertyPage* GetActivePage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkin sayfa işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, etkin sayfada bazı eylemleri gerçekleştirmek için kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#135](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]

##  <a name="getpage"></a>  CPropertySheet::GetPage

Bu özellik sayfasında belirtilen sayfa için bir işaretçi döndürür.

```
CPropertyPage* GetPage(int nPage) const;
```

### <a name="parameters"></a>Parametreler

*nPage*<br/>
İstenen sayfanın dizini 0'dan başlayan. 0 ile bir özellik sayfasını, kapsamlı sayfalarında sayısından küçük olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Sayfa karşılık gelen için işaretçiyi *nPage* parametresi.

### <a name="example"></a>Örnek

Örneğin bakın [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).

##  <a name="getpagecount"></a>  CPropertySheet::GetPageCount

Şu anda özellik sayfasında sayfa sayısını belirler.

```
int GetPageCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfası sayfa sayısı.

### <a name="example"></a>Örnek

Örneğin bakın [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).

##  <a name="getpageindex"></a>  CPropertySheet::GetPageIndex

Özellik sayfasında belirtilen sayfa dizini sayısını alır.

```
int GetPageIndex(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*fsayfa*<br/>
Dizini bulunacak sayfasıyla işaret eder. NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Bir sayfa dizin numarası.

### <a name="remarks"></a>Açıklamalar

Örneğin, kullanacağınız `GetPageIndex` kullanmak için sayfa dizini almak için [SetActivePage](#setactivepage) veya [GetPage](#getpage).

### <a name="example"></a>Örnek

Örneğin bakın [CPropertySheet::GetActivePage](#getactivepage).

##  <a name="gettabcontrol"></a>  CPropertySheet::GetTabControl

Sekme denetimi için belirli bir şey için sekmesinde denetlemek için bir işaretçi alır (yani, API'leri birini kullanmak için [CTabCtrl](../../mfc/reference/ctabctrl-class.md)).

```
CTabCtrl* GetTabControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekme denetimine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Örneğin, bit eşlemler sekmelerin her birinde için başlatma sırasında eklemek isterseniz, bu üye işlevini çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#136](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]

##  <a name="m_psh"></a>  CPropertySheet::m_psh

Bir yapının üyeleri özelliklerini depolamak [PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2).

### <a name="remarks"></a>Açıklamalar

Sonra oluşturduğu, ancak ile görüntülenmeden önce özellik sayfasının görünümünü başlatmak için bu yapı kullanmak [DoModal](#domodal) üye işlevi. Örneğin, *dwSize* üyesi `m_psh` özellik sayfası için istediğiniz boyutu.

Bu grubun üyeleri listesi dahil olmak üzere, bu yapı hakkında daha fazla bilgi için Windows SDK'sındaki PROPSHEETHEADER bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#143](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]

##  <a name="mapdialogrect"></a>  CPropertySheet::MapDialogRect

İletişim kutusu birimleri bir dikdörtgen ekran birimlerine dönüştürür.

```
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
İşaret eden bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) iletişim kutusu içeren nesne koordinatları dönüştürülecek.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu birimleri cinsinden ortalama genişlik ve yükseklik yazı tipi iletişim kutusu metni için kullanılan karakter türetilen geçerli iletişim kutusu temel birim belirtilmiştir. Tek bir yatay birim dörtte biri iletişim kutusu genişliği temel birim, ve dikey bir birimi bir sekizinci iletişim kutusu temel yükseklik birimi.

[GetDialogBaseUnits](/windows/desktop/api/winuser/nf-winuser-getdialogbaseunits) Windows işlevi sistem yazı tipi boyutu bilgilerini döndürür, ancak kaynak tanımı dosyasında DS_SETFONT stili kullanıyorsanız her bir özellik sayfası için farklı bir yazı tipi belirtebilirsiniz. [MapDialogRect](/windows/desktop/api/winuser/nf-winuser-mapdialogrect) açıklanan Windows SDK'da Windows işlevi, bu iletişim kutusu için uygun yazı tipini kullanır.

`MapDialogRect` Üye işlevini değiştiren iletişim kutusu birimlerinde *lpRect* ile dikdörtgen Oluştur iletişim kutusu veya bir kutu içinde bir denetim konumlandırmak için kullanılabilir, böylece ekran birimleri (piksel cinsinden).

##  <a name="oninitdialog"></a>  CPropertySheet::OnInitDialog

Özellik sayfası başlatıcısını büyütmek için geçersiz kılar.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama giriş odağını özellik sayfası denetimlerinde birine olup olmadığını belirtir. Varsa `OnInitDialog` sıfır döndürür, Windows ayarlar giriş odağını özellik sayfası ilk denetim. Uygulama, yalnızca onu açıkça giriş odağı bir özellik sayfası denetimleri ayarlanırsa 0 geri dönebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi WM_INITDIALOG iletiye yanıt olarak adlandırılır. Bu ileti sırasında özellik sayfasına gönderilir [Oluştur](#create) veya [DoModal](#domodal) hemen özellik sayfasını görüntülemeden önce oluşan çağırır.

Özellik sayfası başlatılırken özel işlem yapmanız gerekiyorsa bu üye işlevini geçersiz kılar. Geçersiz kılınan sürümünde temel sınıfı çağırın `OnInitDialog` ancak dönüş değerini dikkate. Normalde, geçersiz kılınan üye işlev TRUE döndürür.

Bu üye işlevi için bir ileti eşleme girişi gerekmez.

##  <a name="pressbutton"></a>  CPropertySheet::PressButton

Bir özellik sayfasında belirtilen düğmesi seçimi benzetimini yapar.

```
void PressButton(int nButton);
```

### <a name="parameters"></a>Parametreler

*Ndüğme*<br/>
Ndüğme: düğmesine basıldığında tanımlar. Bu parametre aşağıdaki değerlerden biri olabilir:

- PSBTN_BACK geri düğmesini seçer.

- PSBTN_NEXT İleri düğmesini seçer.

- PSBTN_FINISH Son düğmesini seçer.

- PSBTN_OK Tamam düğmesini seçer.

- Şimdi Uygula düğmesine PSBTN_APPLYNOW seçer.

- PSBTN_CANCEL İptal düğmesini seçer.

- PSBTN_HELP Yardım düğmesini seçer.

### <a name="remarks"></a>Açıklamalar

Bkz: [PSM_PRESSBUTTON](/windows/desktop/Controls/psm-pressbutton) Windows SDK'sı Pressbutton ileti hakkında daha fazla bilgi.

Bir çağrı `PressButton` değil gönderir [PSN_APPLY](/windows/desktop/Controls/psn-apply) bildirim bir özellik sayfasından çerçevesi. Bu bildirim göndermek için arama [CPropertyPage::OnOK](../../mfc/reference/cpropertypage-class.md#onok).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#137](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]

##  <a name="removepage"></a>  CPropertySheet::RemovePage

Bir özellik sayfasından kaldırır ve ilişkili penceresini yok eder.

```
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>Parametreler

*fsayfa*<br/>
Özellik sayfasından kaldırılması için sayfayı işaret eder. NULL olamaz.

*nPage*<br/>
Kaldırılacak sayfanın dizini. 0 ile bir özellik sayfasını, kapsamlı sayfalarında sayısından küçük olmalıdır.

### <a name="remarks"></a>Açıklamalar

[CPropertyPage](../../mfc/reference/cpropertypage-class.md) nesnenin kendisi kadar sahibi yok edilmez `CPropertySheet` penceresi kapatılır.

##  <a name="setactivepage"></a>  CPropertySheet::SetActivePage

Etkin sayfa değiştirir.

```
BOOL SetActivePage(int nPage);
BOOL SetActivePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*nPage*<br/>
Ayarlanacak sayfasının dizini. 0 ile bir özellik sayfasını, kapsamlı sayfalarında sayısından daha az arasında olmalıdır.

*fsayfa*<br/>
Özellik sayfasında ayarlamak için sayfayı işaret eder. NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfası başarıyla etkinleştirildi olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Örneğin, `SetActivePage` , bir kullanıcının eylemi tek bir sayfada başka bir sayfa etkin sayfa vermemesine neden olmamalıdır.

### <a name="example"></a>Örnek

Örneğin bakın [CPropertySheet::GetActivePage](#getactivepage).

##  <a name="setfinishtext"></a>  CPropertySheet::SetFinishText

Metin son komut düğmesini ayarlar.

```
void SetFinishText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
Son komut düğmesini görüntülenecek metni işaret eder.

### <a name="remarks"></a>Açıklamalar

Çağrı `SetFinishText` son komut düğmesini metni görüntüler ve kullanıcının sihirbazın son sayfasında eylemi tamamlandıktan sonra İleri ve geri düğmeleri gizlemek için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

##  <a name="settitle"></a>  CPropertySheet::SetTitle

Özellik Sayfası'nın başlık (bir çerçeve penceresinin başlık çubuğunda görüntülenen metni) belirtir.

```
void SetTitle(
    LPCTSTR lpszText,
    UINT nStyle = 0);
```

### <a name="parameters"></a>Parametreler

*nStyle*<br/>
Özellik sayfası başlığı stilini belirtir. Stil, 0 veya PSH_PROPTITLE olarak belirtilmelidir. Stil PSH_PROPTITLE ayarlanırsa, resim yazısı olarak belirtilen metin sonra "Özellikler" sözcüğü görünür. Örneğin, çağırma `SetTitle`("Basit", PSH_PROPTITLE) "Basit özellikler." bir özellik sayfası başlığı neden olur

*lpszText*<br/>
Başlık çubuğunda özellik sayfasının başlığı olarak kullanılacak metin işaret eder.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir özellik sayfası özellik sayfası oluşturucuda açıklamalı alt yazı parametresini kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#139](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]

##  <a name="setwizardbuttons"></a>  CPropertySheet::SetWizardButtons

Etkinleştirir veya sihirbaz özellik sayfası geri, sonraki veya Son'a düğmesini devre dışı bırakır.

```
void SetWizardButtons(DWORD dwFlags);
```

### <a name="parameters"></a>Parametreler

*CertOpenStore*<br/>
Sihirbazı düğmelerin görünümünü ve işlevini Özelleştir bayrak kümesi. Bu parametre aşağıdaki değerleri birleşimi olabilir:

- PSWIZB_BACK geri düğmesi

- PSWIZB_NEXT İleri düğmesi

- PSWIZB_FINISH son düğmesi

- PSWIZB_DISABLEDFINISH devre dışı son düğmesi

### <a name="remarks"></a>Açıklamalar

Çağrı `SetWizardButtons` yalnızca iletişim; açıldıktan sonra çağıramazsınız `SetWizardButtons` çağırmadan önce [DoModal](#domodal). Genellikle, çağırmalıdır `SetWizardButtons` gelen [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).

Bitiş düğmenin üzerindeki metni değiştirmek veya sonraki gizlemek istiyorsanız ve geri düğmeleri kez kullanıcı çağrı Sihirbazı Tamamlandı [SetFinishText](#setfinishtext). Aynı düğmeye bitiş ve sonraki için paylaşılan unutmayın. Bir son veya aynı anda İleri düğmesi, ancak ikisini de görüntüleyebilirsiniz.

### <a name="example"></a>Örnek

A `CPropertySheet` üç sihirbaz özellik sayfası vardır: `CStylePage`, `CColorPage`, ve `CShapePage`.  Aşağıdaki kod parçası, etkinleştirme ve devre dışı bırakma gösterilmektedir **geri** ve **sonraki** sihirbaz özellik sayfasında düğme.

[!code-cpp[NVC_MFCDocView#140](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]

[!code-cpp[NVC_MFCDocView#141](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

##  <a name="setwizardmode"></a>  CPropertySheet::SetWizardMode

Sihirbaz özellik sayfası oluşturur.

```
void SetWizardMode();
```

### <a name="remarks"></a>Açıklamalar

Bir anahtar Özellik Sayfası Sihirbazı kullanıcı kullanarak ileri gider veya son yedekleme ve İptal düğmeleri sekmelerin yerine, özelliğidir.

Çağrı `SetWizardMode` çağırmadan önce [DoModal](#domodal). Çağırdıktan sonra `SetWizardMode`, `DoModal` (kullanıcı Son'u kapatırsa) ID_WIZFINISH ya da IDCANCEL döndürür.

`SetWizardMode` PSH_WIZARD bayrağını ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#142](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek CMNCTRL1](../../visual-cpp-samples.md)<br/>
[MFC örnek CMNCTRL2](../../visual-cpp-samples.md)<br/>
[MFC örnek PROPDLG](../../visual-cpp-samples.md)<br/>
[MFC örnek SNAPVW](../../visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
