---
title: CPropertySheet sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 23d17aee2aacbc1484c0f3e181bc824546ab49a2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502821"
---
# <a name="cpropertysheet-class"></a>CPropertySheet sınıfı

Sekme iletişim kutusu olarak da bilinen özellik sayfalarını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CPropertySheet : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPropertySheet:: CPropertySheet](#cpropertysheet)|Bir `CPropertySheet` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPropertySheet:: AddPage](#addpage)|Özellik sayfasına bir sayfa ekler.|
|[CPropertySheet:: yapısı](#construct)|Bir `CPropertySheet` nesnesi oluşturur.|
|[CPropertySheet:: Create](#create)|Kalıcı olmayan bir özellik sayfası görüntüler.|
|[CPropertySheet::D oModal](#domodal)|Kalıcı bir özellik sayfası görüntüler.|
|[CPropertySheet:: Enablestackedtab](#enablestackedtabs)|Özellik sayfasının yığın veya kaydırma sekmeleri kullanıp kullanmadığını belirtir.|
|[CPropertySheet:: EndDialog](#enddialog)|Özellik sayfasını sonlandırır.|
|[CPropertySheet:: GetActiveIndex](#getactiveindex)|Özellik sayfasının etkin sayfasının dizinini alır.|
|[CPropertySheet:: GetActivePage](#getactivepage)|Etkin sayfa nesnesini döndürür.|
|[CPropertySheet:: GetPage](#getpage)|Belirtilen sayfaya bir işaretçi alır.|
|[CPropertySheet:: GetPageCount](#getpagecount)|Özellik sayfasındaki sayfa sayısını alır.|
|[CPropertySheet:: GetPageIndex](#getpageindex)|Özellik sayfasının belirtilen sayfasının dizinini alır.|
|[CPropertySheet:: GetTabControl](#gettabcontrol)|Sekme denetimine yönelik bir işaretçi alır.|
|[CPropertySheet:: MapDialogRect](#mapdialogrect)|Bir dikdörtgenin iletişim kutusu birimlerini ekran birimlerine dönüştürür.|
|[CPropertySheet:: OnInitDialog](#oninitdialog)|Özellik sayfası başlatmasını artırmak için geçersiz kılın.|
|[CPropertySheet::P ressButton](#pressbutton)|Bir özellik sayfasında belirtilen düğme seçimine benzetir.|
|[CPropertySheet:: RemovePage](#removepage)|Özellik sayfasından bir sayfayı kaldırır.|
|[CPropertySheet:: SetActivePage](#setactivepage)|Etkin sayfa nesnesini programlı olarak ayarlar.|
|[CPropertySheet:: Setsonlandırhtext](#setfinishtext)|Son düğmesinin metnini ayarlar.|
|[CPropertySheet:: SetTitle](#settitle)|Özellik sayfasının resim yazısını ayarlar.|
|[CPropertySheet:: SetWizardButtons](#setwizardbuttons)|Sihirbaz düğmelerini etkinleştirilir.|
|[CPropertySheet:: SetWizardMode](#setwizardmode)|Sihirbaz modunu sunar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPropertySheet:: m_psh](#m_psh)|Windows [propsheetheader](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2) yapısı. Temel özellik sayfası parametrelerine erişim sağlar.|

## <a name="remarks"></a>Açıklamalar

Bir özellik sayfası bir `CPropertySheet` nesne ve bir veya daha fazla [CPropertyPage](../../mfc/reference/cpropertypage-class.md) nesnesinden oluşur. Framework, bir özellik sayfasını bir sekme dizini kümesi ve şu anda seçili olan sayfayı içeren bir alan olan bir pencere olarak görüntüler. Kullanıcı ilgili sekmeyi kullanarak belirli bir sayfaya gider.

`CPropertySheet`Windows 98 ve Windows NT 2000 ' de tanıtılan genişletilmiş [propsheetheader](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2) yapısına yönelik destek sağlar. Yapı, "filigran" arka plan bit eşlemi kullanımını destekleyen ek bayraklar ve Üyeler içerir.

Bu yeni görüntüleri Özellik sayfası nesneniz içinde otomatik olarak göstermek için, [CPropertySheet:: yapı](#construct) veya [CPropertySheet:: CPropertySheet](#cpropertysheet)çağrısında bit eşlem ve palet görüntüleri için geçerli değerleri geçirin.

CDialog 'dan türetilmese de [](../../mfc/reference/cdialog-class.md), bir `CPropertySheet` nesneyi yönetmek, bir `CDialog` nesneyi yönetmek gibidir. `CPropertySheet` Örneğin, bir özellik sayfasının oluşturulması iki bölümden oluşan oluşturma gerektirir: oluşturucuyu çağırın ve ardından kalıcı bir özellik sayfası veya [](#domodal) kalıcı olmayan özellik sayfası için [oluşturun](#create) . `CPropertySheet`iki tür oluşturucuya sahiptir: [CPropertySheet:: yapı](#construct) ve [CPropertySheet:: CPropertySheet](#cpropertysheet).

Bir `CPropertySheet` nesne oluşturduğunuzda, bazı [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) birinci şans özel durumunun oluşmasına neden olabilir. Bu durum, sistem, sayfa oluşturulmadan önce Özellik sayfasının stilini değiştirmeye çalışırken oluşur. Bu özel durumdan kaçınmak için, aşağıdaki stilleri oluştururken `CPropertySheet`ayarladığınızdan emin olun:

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

Aşağıdaki stiller isteğe bağlıdır ve ilk şans özel durumuna neden olmaz:

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

`Window Styles` Bazıları yasaktır ve bunları etkinleştirememelisiniz.

Bir `CPropertySheet` nesne ile dış nesne arasında veri değişimi, bir `CDialog` nesne ile veri değişimi ile benzerdir. Önemli fark, bir özellik sayfası ayarlarının genellikle `CPropertyPage` `CPropertySheet` nesnenin kendisi yerine nesnelerin üye değişkenlerinin olduğu nedenleridir.

Bir cihaz ayarlama veya bülten oluşturma gibi bir işlemin adımları boyunca kullanıcıya kılavuzluk eden Özellik sayfaları dizisi olan bir özellik sayfasından oluşan, sihirbaz adlı bir sekme iletişim kutusu türü oluşturabilirsiniz. Sihirbaz-tür sekmesi iletişim kutusunda, özellik sayfalarında sekmeler yoktur ve tek seferde yalnızca bir özellik sayfası görünür. Ayrıca, **Tamam** ve **Şimdi Uygula** düğmelerine sahip olmak yerine, bir sihirbaz türü sekme iletişim kutusu **geri** düğmesi, **İleri** veya **son** düğmesi, **iptal** düğmesi ve **Yardım** düğmesi içerir.

Bir sihirbaz türü iletişim kutusu oluşturmak için, bir standart özellik sayfası oluşturmak üzere izlemeniz gereken adımların aynısını izleyin, ancak [Dokalıcı](#domodal)çağrısı yapmadan önce [SetWizardMode](#setwizardmode) ' ı çağırın. Sihirbaz düğmelerini etkinleştirmek için, bayraklarını ve görünümlerini özelleştirmek üzere bayrakları kullanarak [SetWizardButton](#setwizardbuttons)öğesini çağırın. **Son** düğmesini etkinleştirmek için, sihirbazın son sayfasında Kullanıcı eylemi gerçekleştirildikten sonra [Setbithtext](#setfinishtext) çağrısı yapın.

Nesneleri kullanma `CPropertySheet` hakkında daha fazla bilgi için [Özellik sayfaları ve özellik sayfaları](../../mfc/property-sheets-and-property-pages-in-mfc.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPropertySheet`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs. h

##  <a name="addpage"></a>CPropertySheet:: AddPage

Verilen sayfayı Özellik sayfasında en sağdaki sekmeye ekler.

```
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*pPage*<br/>
Özellik sayfasına eklenecek sayfaya işaret eder. NULL olamaz.

### <a name="remarks"></a>Açıklamalar

Özellik sayfasına, görünmesini istediğiniz soldan sağa doğru sırada sayfa ekleyin.

`AddPage`[CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage) nesnesini `CPropertySheet` nesnenin sayfa listesine ekler ancak sayfa için gerçekten pencere oluşturmaz. Çerçeve, Kullanıcı bu sayfayı seçinceye kadar sayfanın pencere oluşturulmasını erteler.

`CPropertyPage`Kullanarak `AddPage` birözelliksayfasıeklediğinizde,`CPropertySheet` öğesinin üst öğesidir. Özellik sayfasından özellik sayfasına erişim kazanmak için [CWnd:: GetParent](../../mfc/reference/cwnd-class.md#getparent)öğesini çağırın.

Çağrılacak `AddPage`Özellik sayfası penceresini oluşturmaya kadar beklemeniz gerekmez. Genellikle, [DoModal](#domodal) veya `AddPage` [Oluştur](#create)çağrısından önce çağıracaksınız.

Özellik sayfasını görüntülendikten `AddPage` sonra çağırdığınızda, sekme satırı yeni eklenen sayfayı yansıtır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#129](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]

##  <a name="construct"></a>CPropertySheet:: yapısı

Bir `CPropertySheet` nesnesi oluşturur.

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
Özellik sayfası için kullanılacak açıklamalı alt yazının KIMLIĞI.

*pParentWnd*<br/>
Özellik sayfasının üst penceresine yönelik işaretçi. NULL ise, ana pencere uygulamanın ana penceresi olur.

*ıselectpage*<br/>
Başlangıçta en üstte olacak sayfanın dizini. Varsayılan, sayfaya eklenen ilk sayfasıdır.

*pszCaption*<br/>
Özellik sayfası için kullanılacak açıklamalı alt yazı etiketini içeren bir dize işaretçisi. NULL olamaz.

*hbmWatermark*<br/>
Özellik sayfasının filigran bit eşlemini işleyin.

*Hpalfiligran*<br/>
Filigran bit eşlemi ve/veya üst bilgi bit eşlem paletini işleyin.

*hbmHeader*<br/>
Özellik sayfasının üst bilgi bit eşlemini işleyin.

### <a name="remarks"></a>Açıklamalar

Sınıf oluşturucularından biri zaten çağrılmışsa, bu üye işlevi çağırın. Örneğin, `CPropertySheet` nesne dizilerini `Construct` bildirdiğinizde veya ayırdığınızda çağırın. Diziler durumunda dizideki her üye için çağrı `Construct` yapmanız gerekir.

Özellik sayfasını göstermek için [DoModal](#domodal) veya [Oluştur](#create)' u çağırın. İlk parametrede yer alan dize, özellik sayfasının başlık çubuğuna yerleştirilir.

Yukarıda listelenen üçüncü veya `Construct`dördüncü prototipten türlerini kullanırsanız ve *hbmWatermark*, *hpalfiligran*ve/veya *hbmHeader* parametreleri için geçerli değerler geçirdiğinizde, filigranı ve/veya üst bilgi görüntülerini otomatik olarak gösterebilirsiniz.

### <a name="example"></a>Örnek

Aşağıdaki örnek, hangi koşullarda çağrılacağını `Construct`gösterir.

[!code-cpp[NVC_MFCDocView#130](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]

##  <a name="cpropertysheet"></a>CPropertySheet:: CPropertySheet

Bir `CPropertySheet` nesnesi oluşturur.

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
Özellik sayfası için kullanılacak açıklamalı alt yazının KIMLIĞI.

*pParentWnd*<br/>
Özellik sayfasının üst penceresine işaret eder. NULL ise, ana pencere uygulamanın ana penceresi olur.

*ıselectpage*<br/>
Başlangıçta en üstte olacak sayfanın dizini. Varsayılan, sayfaya eklenen ilk sayfasıdır.

*pszCaption*<br/>
Özellik sayfası için kullanılacak açıklamalı alt yazı başlığını içeren bir dizeye işaret eder. NULL olamaz.

*hbmWatermark*<br/>
Özellik sayfasının arka plan bit eşlemiyle bir tanıtıcı.

*Hpalfiligran*<br/>
Filigran bit eşlem ve/veya üst bilgi bit eşlem paleti için bir tanıtıcı.

*hbmHeader*<br/>
Özellik sayfasının üstbilgi bit eşlemiyle bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Özellik sayfasını göstermek için [DoModal](#domodal) veya [Oluştur](#create)' u çağırın. İlk parametrede yer alan dize, özellik sayfasının başlık çubuğuna yerleştirilir.

Birden çok parametreye sahipseniz (örneğin, bir dizi kullanıyorsanız), yerine `CPropertySheet` [Yapı](#construct) kullanın.

Yukarıdaki üçüncü `CPropertySheet`ve dördüncü prototiplerinizi kullanırsanız ve *hbmWatermark*, *hpalfiligran*ve/veya *hbmHeader* parametreleri için geçerli değerler geçirirseniz, filigran ve/veya üst bilgi görüntülerini otomatik olarak gösterebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#131](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]

##  <a name="create"></a>CPropertySheet:: Create

Kalıcı olmayan bir özellik sayfası görüntüler.

```
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)-1,
    DWORD dwExStyle = 0);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Ana pencereye işaret eder. NULL ise, üst düzey masaüstüdür.

*dwStyle*<br/>
Özellik sayfası için pencere stilleri. Kullanılabilir stillerin tüm listesi için bkz. [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*dwExStyle*<br/>
Özellik sayfası için genişletilmiş pencere stilleri. Kullanılabilir stillerin tüm listesi için bkz. [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfası başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çağrısı `Create` , oluşturucunun içinde olabilir veya Oluşturucu çağrıldıktan sonra bunu çağırabilirsiniz.

Varsayılan stil,-1 ' i *dwStyle*olarak geçirerek ifade edilir, aslında WS_SYSMENU&#124;WS_POPUP&#124;WS_CAPTION&#124;DS_MODALFRAME&#124;DS_CONTEXTHELP&#124;WS_VISIBLE. Varsayılan genişletilmiş pencere stili, *dwExStyle*olarak 0 geçirilerek belirtilir, aslında ws_ex_dlgmodalframe.

`Create` Üye işlevi, özellik sayfası oluşturulduktan hemen sonra geri döner. Özellik sayfasını yok etmek için [CWnd::D estroyWindow](../../mfc/reference/cwnd-class.md#destroywindow)öğesini çağırın.

Bir çağrısıyla `Create` birlikte görüntülenecek kalıcı olmayan özellik sayfaları, kalıcı Özellik sayfaları olarak Tamam, iptal, şimdi Uygula ve yardım düğmelerine sahip değildir. İstenen düğmelerin Kullanıcı tarafından oluşturulması gerekir.

Kalıcı bir özellik sayfasını göstermek için, bunun yerine [DoModal](#domodal) ' ı çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#132](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]

[!code-cpp[NVC_MFCDocView#133](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]

##  <a name="domodal"></a>CPropertySheet::D oModal

Kalıcı bir özellik sayfası görüntüler.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa ıDOK veya ıDCANCEL; Aksi takdirde 0 veya-1. Özellik sayfası sihirbaz olarak kurulduysa (bkz. [SetWizardMode](#setwizardmode)), ID_WIZFINISH veya IDCANCEL `DoModal` ' ı döndürür.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri, özellik sayfasını kapatan denetimin KIMLIĞINE karşılık gelir. Bu işlev döndüğünde, özellik sayfasına ve tüm sayfalara karşılık gelen pencereler yok edilir. Nesneler hala mevcut olacaktır. Genellikle, [CPropertyPage](../../mfc/reference/cpropertypage-class.md) nesnelerinden `DoModal` IDOK öğesini döndürdüğünü, verileri elde edersiniz.

Kalıcı olmayan bir özellik sayfasını göstermek için, bunun yerine [Create](#create) çağırın.

Kendisine karşılık gelen iletişim kutusu kaynağından bir özellik sayfası oluşturulduğunda, ilk fırsat özel durumuna neden olabilir. Bu, özellik sayfasının, iletişim kaynağı stilini, sayfa oluşturulmadan önce gerekli stile değiştirme sonucu olur. Kaynaklar genellikle salt okunurdur, bu durum bir özel duruma neden olur. Sistem özel durumu işler ve değiştirilen kaynağın bir kopyasını oluşturur. Bu nedenle, ilk şans özel durumu yok sayılır.

> [!NOTE]
>  Bu özel durum, zaman uyumsuz özel durum işleme modeliyle derlerken, işletim sistemi tarafından işlenmelidir. Özel durum işleme modelleri hakkında daha fazla bilgi için bkz. [/Eh (özel durum Işleme modeli)](../../build/reference/eh-exception-handling-model.md). Bu durumda, çağrılarını `CPropertySheet::DoModal` , catch 'in tüm özel durumları (örneğin, C++ `catch (...)`) işlediği bir try-catch bloğuyla sarmayın. Bu blok, işletim sistemi için tasarlanan özel durumu işleyebilir ve öngörülemeyen davranışlara neden olur. Bununla birlikte, belirli özel durum C++ türleriyle özel durum Işlemeyi veya erişim ihlali özel durumunun işletim sistemine geçirildiği yapılandırılmış özel durum işlemesini güvenle kullanabilirsiniz.

Bu birinci şans özel durumunun oluşturulmasını önlemek için, özellik sayfasında doğru [pencere stillerinin](../../mfc/reference/styles-used-by-mfc.md#window-styles)olduğunu el ile garanti edebilirsiniz. Bir özellik sayfası için aşağıdaki stilleri ayarlamanız gerekir:

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

Aşağıdaki isteğe bağlı stilleri, birinci şans özel durumuna neden olmadan kullanabilirsiniz:

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

Özellik sayfalarıyla uyumlu olmadıkları için diğer tüm Windows stillerini devre dışı bırakın. Bu öneri, genişletilmiş stiller için geçerlidir. Bu standart stilleri uygun şekilde ayarlamak, özellik sayfasının değiştirilmesini garantilemez ve birinci şans özel durumunu üretmemek için bir işlem yapar.

### <a name="example"></a>Örnek

[CPropertySheet:: AddPage](#addpage)örneğine bakın.

##  <a name="enablestackedtabs"></a>CPropertySheet:: Enablestackedtab

Bir özellik sayfasında sekmelerin satırlarının yığanıp ayrılmayacağını gösterir.

```
void EnableStackedTabs(BOOL bStacked);
```

### <a name="parameters"></a>Parametreler

*Byığınlanmış*<br/>
Özellik sayfasında yığılmış sekmelerin etkinleştirilip etkinleştirilmeyeceğini gösterir. *Byığınlanmış* değerini false olarak ayarlayarak, yığılmış satırları devre dışı bırakın.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir özellik sayfasında, özellik sayfasının genişliğine göre tek bir satıra sığacak kadar daha fazla sekme varsa, sekmeler birden çok satırda yığılır. Yığın sekmeleri yerine kaydırma sekmelerini kullanmak için, `EnableStackedTabs` [DoModal](#domodal) veya [Oluştur](#create)çağırılmadan önce *byığılmış* kümesi false olarak çağırın.

Kalıcı veya kalıcı `EnableStackedTabs` olmayan bir özellik sayfası oluşturduğunuzda çağırmanız gerekir. Bu stili bir `CPropertySheet`türetilmiş sınıfta birleştirmek için, WM_CREATE için bir ileti işleyicisi yazın. Geçersiz kılınan [CWnd:: OnCreate](../../mfc/reference/cwnd-class.md#oncreate)sürümünde, temel sınıf uygulamasını `EnableStackedTabs( FALSE )` çağırmadan önce çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#134](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]

##  <a name="enddialog"></a>CPropertySheet:: EndDialog

Özellik sayfasını sonlandırır.

```
void EndDialog(int nEndID);
```

### <a name="parameters"></a>Parametreler

*nEndID*<br/>
Özellik sayfasının dönüş değeri olarak kullanılacak tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, OK, Cancel veya Close düğmesine basıldığında Framework tarafından çağırılır. Özellik sayfasını kapatması gereken bir olay oluşursa, bu üye işlevi çağırın.

Bu üye işlevi yalnızca kalıcı iletişim kutusuyla birlikte kullanılır.

### <a name="example"></a>Örnek

[CPropertySheet::P ressButton](#pressbutton)örneğine bakın.

##  <a name="getactiveindex"></a>CPropertySheet:: GetActiveIndex

Özellik sayfası penceresinin etkin sayfasının dizin numarasını alır ve ardından için `GetPage`parametresi olarak döndürülen dizin numarasını kullanır.

```
int GetActiveIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkin sayfanın dizin numarası.

### <a name="example"></a>Örnek

[CPropertySheet:: GetActivePage](#getactivepage)örneğine bakın.

##  <a name="getactivepage"></a>CPropertySheet:: GetActivePage

Özellik sayfası penceresinin etkin sayfasını alır.

```
CPropertyPage* GetActivePage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkin sayfanın işaretçisi.

### <a name="remarks"></a>Açıklamalar

Etkin sayfada bazı eylemler gerçekleştirmek için bu üye işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#135](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]

##  <a name="getpage"></a>CPropertySheet:: GetPage

Bu özellik sayfasında belirtilen sayfaya bir işaretçi döndürür.

```
CPropertyPage* GetPage(int nPage) const;
```

### <a name="parameters"></a>Parametreler

*Nsayfa*<br/>
İstenen sayfanın dizini 0 ' dan başlayarak. 0 ile bir, özellik sayfasındaki (dahil) sayfa sayısından küçük olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Sayfanın, *nPage* parametresine karşılık gelen işaretçisi.

### <a name="example"></a>Örnek

[CPropertyPage:: Onwizardbitiş](../../mfc/reference/cpropertypage-class.md#onwizardfinish)örneğine bakın.

##  <a name="getpagecount"></a>CPropertySheet:: GetPageCount

Özellik sayfasındaki geçerli sayfa sayısını belirler.

```
int GetPageCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfasındaki sayfa sayısı.

### <a name="example"></a>Örnek

[CPropertyPage:: Onwizardbitiş](../../mfc/reference/cpropertypage-class.md#onwizardfinish)örneğine bakın.

##  <a name="getpageindex"></a>CPropertySheet:: GetPageIndex

Özellik sayfasında belirtilen sayfanın dizin numarasını alır.

```
int GetPageIndex(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*pPage*<br/>
Bulunan dizini içeren sayfaya işaret eder. NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Bir sayfanın dizin numarası.

### <a name="remarks"></a>Açıklamalar

Örneğin, [SetActivePage](#setactivepage) veya `GetPageIndex` [GetPage](#getpage)kullanmak için sayfa dizinini almak üzere öğesini kullanabilirsiniz.

### <a name="example"></a>Örnek

[CPropertySheet:: GetActivePage](#getactivepage)örneğine bakın.

##  <a name="gettabcontrol"></a>CPropertySheet:: GetTabControl

Sekme denetimine özgü bir şey yapmak için Sekme denetimine yönelik bir işaretçi alır (diğer bir deyişle, [CTabCtrl](../../mfc/reference/ctabctrl-class.md)'teki API 'lerden herhangi birini kullanmak için).

```
CTabCtrl* GetTabControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekme denetimine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Örneğin, başlatma sırasında sekmelerin her birine bit eşlemler eklemek istiyorsanız bu üye işlevini çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#136](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]

##  <a name="m_psh"></a>CPropertySheet:: m_psh

Üyeleri [propsheetheader](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2)özelliklerini depolayan bir yapı.

### <a name="remarks"></a>Açıklamalar

Özellik sayfasının, oluşturulduktan sonra, ancak [DoModal](#domodal) üye işleviyle görüntülenmeden önce görünümünü başlatmak için bu yapıyı kullanın. Örneğin, *dwSize* üyesini `m_psh` Özellik sayfasının sahip olmasını istediğiniz boyuta ayarlayın.

Bu yapı hakkında, üyelerinin bir listesi de dahil daha fazla bilgi için bkz. PROPSHEETHEADER Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#143](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]

##  <a name="mapdialogrect"></a>CPropertySheet:: MapDialogRect

Bir dikdörtgenin iletişim kutusu birimlerini ekran birimlerine dönüştürür.

```
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
Dönüştürülecek iletişim kutusu koordinatlarını içeren bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine işaret eder.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu birimleri, iletişim kutusu metni için kullanılan yazı tipindeki ortalama genişlik ve karakterlerin yüksekliğinden türetilmiş geçerli iletişim kutusu taban birimi açısından belirtilir. Bir yatay birim iletişim kutusu taban genişliği biriminin dörtte biridir ve bir dikey birim iletişim kutusu Taban yükseklik biriminin sekizde biridir.

[GetDialogBaseUnits](/windows/win32/api/winuser/nf-winuser-getdialogbaseunits) Windows işlevi, sistem yazı tipi için boyut bilgilerini döndürür, ancak kaynak tanımı dosyasında DS_SETFONT stilini kullanırsanız her bir özellik sayfası için farklı bir yazı tipi belirtebilirsiniz. Windows SDK açıklanan [MapDialogRect](/windows/win32/api/winuser/nf-winuser-mapdialogrect) Windows işlevi, bu iletişim kutusu için uygun yazı tipini kullanır.

Üye işlevi, *loprect* 'daki iletişim kutusu birimlerinin yerini ekran birimleri (piksel) ile değiştirir, böylece dikdörtgen bir iletişim kutusu oluşturmak veya bir kutuyu kutu içinde konumlandırmak için kullanılabilir. `MapDialogRect`

##  <a name="oninitdialog"></a>CPropertySheet:: OnInitDialog

Özellik sayfası başlatmasını artırmak için geçersiz kılar.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın, giriş odağını özellik sayfasındaki denetimlerden birine ayarlayıp ayarlamadığını belirtir. Sıfır dışında bir değer döndürürse, Windows giriş odağını özellik sayfasındaki ilk denetime ayarlar. `OnInitDialog` Uygulama, yalnızca giriş odağını özellik sayfasındaki denetimlerden birine açıkça ayarlamışsa 0 döndürebilir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, WM_INITDIALOG iletisine yanıt olarak çağırılır. Bu ileti, özellik sayfası görüntülenmeden hemen önce gerçekleşen [Create](#create) veya [DoModal](#domodal) çağrıları sırasında özellik sayfasına gönderilir.

Özellik sayfası başlatıldığında özel işlem gerçekleştirmeniz gerekiyorsa, bu üye işlevi geçersiz kılın. Geçersiz kılınan sürümde, önce temel sınıfı `OnInitDialog` çağırın, ancak dönüş değerini yok sayın. Normalde geçersiz kılınan üye işlevinizden doğru bir değer döndürülecektir.

Bu üye işlevi için bir ileti eşleme girişi gerekmez.

##  <a name="pressbutton"></a>CPropertySheet::P ressButton

Bir özellik sayfasında belirtilen düğme seçimine benzetir.

```
void PressButton(int nButton);
```

### <a name="parameters"></a>Parametreler

*Ndüğme*<br/>
Ndüğme Basılan düğmeyi tanımlar. Bu parametre aşağıdaki değerlerden biri olabilir:

- PSBTN_BACK geri düğmesini seçer.

- PSBTN_NEXT Ileri düğmesini seçer.

- PSBTN_FINISH, son düğmesini seçer.

- PSBTN_OK Tamam düğmesini seçer.

- PSBTN_APPLYNOW Şimdi Uygula düğmesini seçer.

- PSBTN_CANCEL Iptal düğmesini seçer.

- PSBTN_HELP Yardım düğmesini seçer.

### <a name="remarks"></a>Açıklamalar

PressButton iletisi Windows SDK hakkında daha fazla bilgi için bkz. [PSM_PRESSBUTTON](/windows/win32/Controls/psm-pressbutton) .

' A yapılan `PressButton` bir çağrı, bir özellik sayfasından çerçeveye [PSN_APPLY](/windows/win32/Controls/psn-apply) bildirimi göndermeyecektir. Bu bildirimi göndermek için [CPropertyPage:: OnOK](../../mfc/reference/cpropertypage-class.md#onok)çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#137](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]

##  <a name="removepage"></a>CPropertySheet:: RemovePage

Özellik sayfasından bir sayfayı kaldırır ve ilişkili pencereyi yok eder.

```
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>Parametreler

*pPage*<br/>
Özellik sayfasından kaldırılacak sayfayı işaret eder. NULL olamaz.

*Nsayfa*<br/>
Kaldırılacak sayfanın dizini. 0 ile bir, özellik sayfasındaki (dahil) sayfa sayısından küçük olmalıdır.

### <a name="remarks"></a>Açıklamalar

`CPropertySheet` Pencerenin sahibi kapatılana kadar [CPropertyPage](../../mfc/reference/cpropertypage-class.md) nesnesinin kendisi yok edilmez.

##  <a name="setactivepage"></a>CPropertySheet:: SetActivePage

Etkin sayfayı değiştirir.

```
BOOL SetActivePage(int nPage);
BOOL SetActivePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*Nsayfa*<br/>
Ayarlanacak sayfanın dizini. Bu, 0 ile bir, özellik sayfasındaki (dahil) sayfa sayısından az olmalıdır.

*pPage*<br/>
Özellik sayfasında ayarlanacak sayfaya işaret eder. NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfası başarıyla etkinleştirildiyse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Örneğin, bir kullanıcının `SetActivePage` eylemi bir sayfada başka bir sayfanın etkin sayfa haline gelmesine neden olursa kullanın.

### <a name="example"></a>Örnek

[CPropertySheet:: GetActivePage](#getactivepage)örneğine bakın.

##  <a name="setfinishtext"></a>CPropertySheet:: Setsonlandırhtext

Son komut düğmesindeki metni ayarlar.

```
void SetFinishText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
Son komut düğmesinde görüntülenecek metni işaret eder.

### <a name="remarks"></a>Açıklamalar

Komutu `SetFinishText` son komut düğmesinde göstermek için çağırın ve sihirbazın son sayfasında Kullanıcı eylemi tamamlandıktan sonra ileri ve geri düğmelerini gizleyin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

##  <a name="settitle"></a>CPropertySheet:: SetTitle

Özellik sayfasının başlığını belirtir (bir çerçeve penceresinin başlık çubuğunda görünen metin).

```
void SetTitle(
    LPCTSTR lpszText,
    UINT nStyle = 0);
```

### <a name="parameters"></a>Parametreler

*nStyle*<br/>
Özellik sayfası başlığının stilini belirtir. Stilin 0 veya PSH_PROPTITLE olarak belirtilmesi gerekir. Stil PSH_PROPTITLE olarak ayarlandıysa, "Özellikler" sözcüğü, başlık olarak belirtilen metinden sonra görüntülenir. Örneğin, (" `SetTitle`Simple", PSH_PROPTITLE) çağırmak, "basit özellikler" öğesinin bir özellik sayfası açıklamalı alt yazısının oluşmasına neden olur.

*lpszText*<br/>
Özellik sayfasının başlık çubuğunda başlık olarak kullanılacak metni gösterir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir özellik sayfası, özellik sayfası oluşturucusunda Caption parametresini kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#139](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]

##  <a name="setwizardbuttons"></a>CPropertySheet:: SetWizardButtons

Sihirbaz Özellik sayfasında geri, Ileri veya son düğmesini etkinleştirilir veya devre dışı bırakır.

```
void SetWizardButtons(DWORD dwFlags);
```

### <a name="parameters"></a>Parametreler

*dwFlags*<br/>
Sihirbaz düğmelerinin işlevini ve görünümünü özelleştiren bayraklar kümesi. Bu parametre aşağıdaki değerlerin bir birleşimi olabilir:

- PSWIZB_BACK geri düğmesi

- PSWIZB_NEXT Ileri düğmesi

- PSWIZB_FINISH son düğmesi

- PSWIZB_DISABLEDFINISH devre dışı bitiş düğmesi

### <a name="remarks"></a>Açıklamalar

Yalnızca `SetWizardButtons` iletişim kutusu açıldıktan sonra çağrı yapın; [dokalıcı](#domodal)çağrısı `SetWizardButtons` yapmadan önce çağırılamaz. Genellikle, `SetWizardButtons` [CPropertyPage:: OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive)öğesinden çağırmanız gerekir.

Kullanıcı Sihirbazı tamamladıktan sonra son düğmedeki metni değiştirmek veya Ileri ve geri düğmelerini gizlemek istiyorsanız, [Setbithtext](#setfinishtext)' i çağırın. Aynı düğmenin son ve Ileri için paylaşıldığını unutmayın. Bir kerede bir son veya bir sonraki düğme görüntüleyebilirsiniz, ancak her ikisini birden kullanamazsınız.

### <a name="example"></a>Örnek

A `CPropertySheet` , üç sihirbaz Özellik sayfasına sahiptir `CStylePage`: `CColorPage`, ve `CShapePage`.  Aşağıdaki kod parçası, sihirbaz Özellik sayfasında **geri** ve **İleri** düğmelerinin nasıl etkinleştirileceğini ve devre dışı bırakılacağını gösterir.

[!code-cpp[NVC_MFCDocView#140](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]

[!code-cpp[NVC_MFCDocView#141](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

##  <a name="setwizardmode"></a>CPropertySheet:: SetWizardMode

Sihirbaz olarak bir özellik sayfası oluşturur.

```
void SetWizardMode();
```

### <a name="remarks"></a>Açıklamalar

Sihirbaz Özellik sayfasının önemli özellikleri, kullanıcının sekmeler yerine Ileri veya son, geri ve Iptal düğmelerini kullanarak gezinmesine bağlıdır.

`SetWizardMode` [DoModal](#domodal)çağrılmadan önce çağırın. ' İ çağırdığınızda `SetWizardMode`, `DoModal` ID_WIZFINISH (Kullanıcı son düğme ile kapanırsa) veya IDCANCEL olarak döndürülür.

`SetWizardMode`PSH_WIZARD bayrağını ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#142](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
