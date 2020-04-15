---
title: CPropertySheet Sınıfı
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
ms.openlocfilehash: 167c99f734e4538ff2704e032a6ca98fb1d82004
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363944"
---
# <a name="cpropertysheet-class"></a>CPropertySheet Sınıfı

Sekme iletişim kutuları olarak da bilinen özellik sayfalarını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CPropertySheet : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CpropertySheet::cpropertysheet](#cpropertysheet)|Bir `CPropertySheet` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPropertySheet::AddPage](#addpage)|Özellik sayfasına bir sayfa ekler.|
|[CPropertySheet::Yapı](#construct)|Bir `CPropertySheet` nesne inşa eder.|
|[CPropertySheet::Oluştur](#create)|Modeless özellik sayfası görüntüler.|
|[CPropertySheet::DoModal](#domodal)|Modal özellik sayfası görüntüler.|
|[CPropertySheet::EnableStackedTabs](#enablestackedtabs)|Özellik sayfasının yığılmış veya kaydırma sekmelerini kullanıp kullanmadığını gösterir.|
|[CPropertySheet::EndDialog](#enddialog)|Özellik sayfasını sonlandırır.|
|[CpropertySheet::GetActiveIndex](#getactiveindex)|Özellik sayfasının etkin sayfasının dizini alır.|
|[CpropertySheet::GetActivePage](#getactivepage)|Etkin sayfa nesnesini döndürür.|
|[CPropertySheet::GetPage](#getpage)|Belirtilen sayfaya bir işaretçi alır.|
|[CpropertySheet::GetPageCount](#getpagecount)|Özellik sayfasındaki sayfa sayısını alır.|
|[CpropertySheet::GetPageIndex](#getpageindex)|Özellik sayfasının belirtilen sayfasının dizinini alır.|
|[CpropertySheet::gettabcontrol](#gettabcontrol)|Bir sekme denetimi için işaretçi alır.|
|[CPropertySheet::MapDialogRect](#mapdialogrect)|Dikdörtgenin iletişim kutusu birimlerini ekran birimlerine dönüştürür.|
|[CPropertySheet::OnInitDialog](#oninitdialog)|Özellik sayfası başlatmayı artırmak için geçersiz kılın.|
|[CPropertySheet::PressButton](#pressbutton)|Bir özellik sayfasında belirtilen düğmenin seçimini simüle eder.|
|[CÖzellik Sayfası::RemovePage](#removepage)|Bir sayfayı özellik sayfasından kaldırır.|
|[CpropertySheet::SetActivePage](#setactivepage)|Etkin sayfa nesnesini programlı olarak ayarlar.|
|[CpropertySheet::SetFinishText](#setfinishtext)|Bitiş düğmesi için metni ayarlar.|
|[CPropertySheet::SetTitle](#settitle)|Özellik sayfasının alt yazısını ayarlar.|
|[CPropertySheet::SetWizardButtons](#setwizardbuttons)|Sihirbaz düğmelerini etkinleştiri.|
|[CpropertySheet::SetWizardMode](#setwizardmode)|Sihirbaz modunu etkinleştiri.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CPropertySheet::m_psh](#m_psh)|Windows [PROPSHEETHEADER](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2) yapısı. Temel özellik sayfası parametrelerine erişim sağlar.|

## <a name="remarks"></a>Açıklamalar

Özellik sayfası bir `CPropertySheet` nesne ve bir veya daha fazla [CPropertyPage](../../mfc/reference/cpropertypage-class.md) nesnesi oluşur. Çerçeve, bir özellik sayfasını sekme endeksleri kümesi ve şu anda seçili sayfayı içeren bir alan içeren bir pencere olarak görüntüler. Kullanıcı, uygun sekmeyi kullanarak belirli bir sayfaya yönlendirin.

`CPropertySheet`Windows 98 ve Windows NT 2000'de tanıtılan genişletilmiş [PROPSHEETHEADER](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2) yapısı için destek sağlar. Yapı, "filigran" arka plan bit eşlemi kullanarak destekleyen ek bayraklar ve üyeler içerir.

Bu yeni görüntüleri özellik sayfası nesnenizde otomatik olarak görüntülemek için, [CPropertySheet'e](#construct) yapılan çağrıdabitmap ve palet görüntüleri için geçerli değerleri geçirin::Construct veya [CPropertySheet::CPropertySheet](#cpropertysheet).

[CDialog'dan](../../mfc/reference/cdialog-class.md)türetilmiş olmasa `CPropertySheet` da, `CPropertySheet` bir `CDialog` nesneyi yönetmek nesneyi yönetmek gibidir. Örneğin, bir özellik sayfasının oluşturulması iki parçalı yapı gerektirir: oluşturucuyu arayın ve ardından modal özellik sayfası için [DoModal'ı](#domodal) arayın veya modeless bir özellik sayfası için [oluştur.](#create) `CPropertySheet`iki tür oluşturucu vardır: [CPropertySheet::Construct](#construct) and [CPropertySheet::CPropertySheet](#cpropertysheet).

Bir `CPropertySheet` nesne oluştururken, bazı [Pencere Stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) ilk şans özel durum oluşmasına neden olabilir. Bu, sayfa oluşturulmadan önce özellik sayfasının stilini değiştirmeye çalışan sistemden kaynaklanır. Bu özel durum önlemek için, aşağıdaki stilleri oluşturduğunuzda `CPropertySheet`ayarladığınızdan emin olun:

- DS_3DLOOK

- DS_CONTROL

- Ws_chıld

- WS_TABSTOP

Aşağıdaki stiller isteğe bağlıdır ve ilk şans özel durumu neden olmaz:

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

Başka `Window Styles` herhangi bir yasaktır ve bunları izin vermemelisiniz.

Bir `CPropertySheet` nesne ve harici bir nesne arasında veri alışverişi, bir `CDialog` nesne yle veri alışverişine benzer. Önemli fark, bir özellik sayfasının ayarlarının genellikle `CPropertyPage` `CPropertySheet` nesnenin kendisi yerine nesnelerin üye değişkenleri olmasıdır.

Sihirbaz adı verilen ve kullanıcıya aygıt ayarlama veya bülten oluşturma gibi işlem adımlarından rehberlik eden özellik sayfaları dizisiiçeren bir özellik sayfası içeren bir sekme iletişim kutusu türü oluşturabilirsiniz. Sihirbaz türü sekmesi iletişim kutusunda, özellik sayfalarında sekmeler yoktur ve aynı anda yalnızca bir özellik sayfası görünür. Ayrıca, **Tamam** ve **Şimdi Uygula** düğmelerine sahip olmak yerine, sihirbaz türü sekmesi iletişim kutusunda **Geri Düğmesi,** **İleri** veya **Bitiş** düğmesi, **İptal** düğmesi ve **Yardım düğmesi** bulunur.

Sihirbaz türünde bir iletişim kutusu oluşturmak için, standart bir özellik sayfası oluşturmak için izleyeceğiniz adımları izleyin, ancak [DoModal'ı](#domodal)aramadan önce [SetWizardMode'u](#setwizardmode) arayın. Sihirbaz düğmelerini etkinleştirmek için, işlevlerini ve görünümlerini özelleştirmek için bayrakları kullanarak [SetWizardButtons'ı](#setwizardbuttons)arayın. **Bitiş** düğmesini etkinleştirmek için, kullanıcı sihirbazın son sayfasında işlem yaptıktan sonra [SetFinishText'i](#setfinishtext) arayın.

Nesnelerin nasıl kullanılacağı `CPropertySheet` hakkında daha fazla bilgi [için, Makale Özellik Sayfaları ve Özellik Sayfaları'na](../../mfc/property-sheets-and-property-pages-in-mfc.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CPropertySheet`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs.h

## <a name="cpropertysheetaddpage"></a><a name="addpage"></a>CPropertySheet::AddPage

Verilen sayfayı özellik sayfasına en doğru sekmeyle ekler.

```
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*pPage*<br/>
Özellik sayfasına eklenecek sayfayı işaret edin. NULL olamaz.

### <a name="remarks"></a>Açıklamalar

Görünmesini istediğiniz soldan sağa sırayla özellik sayfasına sayfalar ekleyin.

`AddPage`[CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage) nesnesini nesnenin sayfa listesine `CPropertySheet` ekler, ancak sayfa için pencereyi gerçekte oluşturmaz. Çerçeve, kullanıcı bu sayfayı seçene kadar sayfa için pencere oluşturmayı erteler.

Bir özellik sayfası `AddPage`kullandığınızda, `CPropertySheet` 'nin üst `CPropertyPage`öğesidir. Özellik sayfasından özellik sayfasına erişmek için [CWnd'yi arayın::GetParent](../../mfc/reference/cwnd-class.md#getparent).

Aramak `AddPage`için özellik sayfası penceresinin oluşturulmasına kadar beklemek gerekli değildir. Genellikle, `AddPage` [DoModal](#domodal) veya [Create'i](#create)aramadan önce ararsınız.

Özellik sayfasını `AddPage` görüntüledikten sonra ararsanız, sekme satırı yeni eklenen sayfayı yansıtır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#129](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]

## <a name="cpropertysheetconstruct"></a><a name="construct"></a>CPropertySheet::Yapı

Bir `CPropertySheet` nesne inşa eder.

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
Özellik sayfası için kullanılacak resim yazısının kimliği.

*pParentWnd*<br/>
Özellik sayfasının üst penceresine işaretçi. NULL ise, üst pencere uygulamanın ana penceresi olacaktır.

*iSelectPage*<br/>
Başlangıçta üstte olacak sayfanın dizin. Varsayılan, sayfaya eklenen ilk sayfadır.

*pszCaption*<br/>
Özellik sayfası için kullanılacak resim yazısını içeren bir dize işaretçi. NULL olamaz.

*hbmFili*<br/>
Özellik sayfasının filigran bit haritasını işleyin.

*hpalWatermark*<br/>
Filigran bit eşlemi ve/veya üstbilgi bit eşlemi paletine işleyin.

*hbmHeader*<br/>
Özellik sayfasının üstbilgi bit haritasına işleyin.

### <a name="remarks"></a>Açıklamalar

Sınıf oluşturucularından biri zaten çağrılmadıysa bu üye işlevi çağırın. Örneğin, `CPropertySheet` nesne `Construct` dizilerini beyan ettiğinizde veya ayırdığınızda arayın. Diziler söz konusu olduğunda, `Construct` dizideki her üyeyi aramanız gerekir.

Özellik sayfasını görüntülemek için [DoModal](#domodal) veya [Create'i](#create)arayın. İlk parametrede yer alan dize, özellik sayfasının resim yazısı çubuğuna yerleştirilir.

Yukarıda listelenen üçüncü veya dördüncü `Construct`prototipleri kullanırsanız filigran ve/veya üstbilgi görüntülerini otomatik olarak görüntüleyebilir ve *hbmWatermark*, *hpalWatermark*ve/veya *hbmHeader* parametreleri için geçerli değerleri geçirebilirsiniz.

### <a name="example"></a>Örnek

Aşağıdaki örnek, hangi koşullar altında `Construct`çağıracağınızı gösterir.

[!code-cpp[NVC_MFCDocView#130](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]

## <a name="cpropertysheetcpropertysheet"></a><a name="cpropertysheet"></a>CpropertySheet::cpropertysheet

Bir `CPropertySheet` nesne inşa eder.

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
Özellik sayfası için kullanılacak resim yazısının kimliği.

*pParentWnd*<br/>
Özellik sayfasının üst penceresine işaret ediyor. NULL ise, üst pencere uygulamanın ana penceresi olacaktır.

*iSelectPage*<br/>
Başlangıçta üstte olacak sayfanın dizin. Varsayılan, sayfaya eklenen ilk sayfadır.

*pszCaption*<br/>
Özellik sayfası için kullanılacak resim yazısını içeren bir dize yi işaret eder. NULL olamaz.

*hbmFili*<br/>
Özellik sayfasının arka plan bit haritasına bir tutamaç.

*hpalWatermark*<br/>
Filigran bit eşlemi ve/veya üstbilgi bit eşlemi paletine bir tutamaç.

*hbmHeader*<br/>
Özellik sayfasının üstbilgi bit haritasına bir tutamak.

### <a name="remarks"></a>Açıklamalar

Özellik sayfasını görüntülemek için [DoModal](#domodal) veya [Create'i](#create)arayın. İlk parametrede yer alan dize, özellik sayfasının resim yazısı çubuğuna yerleştirilir.

Birden çok parametreniz varsa (örneğin, bir dizi kullanıyorsanız), '' yerine `CPropertySheet` [Oluştur'u](#construct) kullanın.

Yukarıdaki üçüncü veya dördüncü prototipleri kullanırsanız ve `CPropertySheet` *hbmWatermark*, *hpalWatermark*ve/veya *hbmHeader* parametreleri için geçerli değerleri geçerseniz filigran ve/veya üstbilgi görüntülerini otomatik olarak görüntüleyebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#131](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]

## <a name="cpropertysheetcreate"></a><a name="create"></a>CPropertySheet::Oluştur

Modeless özellik sayfası görüntüler.

```
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)-1,
    DWORD dwExStyle = 0);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Üst pencereye işaret ediyor. NULL ise, üst masaüstüdür.

*Dwstyle*<br/>
Özellik sayfası için pencere stilleri. Kullanılabilir stillerin tam listesi için [Bkz. Pencere Stilleri.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

*dwExStyle*<br/>
Özellik sayfası için genişletilmiş pencere stilleri. Kullanılabilir stillerin tam listesi için [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) bölümüne bakın

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfası başarıyla oluşturulursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çağrı yapıcının içinde `Create` olabilir veya oluşturucu çağrıldıktan sonra arayabilirsiniz.

*-1'i dwStyle*olarak geçirerek ifade edilen varsayılan stil, WS_SYSMENU aslında&#124;&#124;&#124;&#124;WS_CAPTION&#124;DS_CONTEXTHELP&#124;DS_CONTEXTHELP WS_VISIBLE&#124;&#124;DS_MODALFRAME&#124;WS_POPUP&#124;. Varsayılan genişletilmiş pencere stili, *dwExStyle*olarak 0 geçerek ifade, aslında WS_EX_DLGMODALFRAME.

`Create` Üye işlev özellik sayfasını oluşturduktan hemen sonra geri döner. Mülkiyet sayfası yok etmek için, [CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow)arayın.

Modsuz özellik sayfaları, modal özellik sayfaları gibi Tamam, İptal, Şimdi Uygula ve Yardım düğmeleri yok bir `Create` çağrı ile görüntülenir. İstenilen düğmeler kullanıcı tarafından oluşturulmalıdır.

Modal özellik sayfası görüntülemek için bunun yerine [DoModal'ı](#domodal) arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#132](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]

[!code-cpp[NVC_MFCDocView#133](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]

## <a name="cpropertysheetdomodal"></a><a name="domodal"></a>CPropertySheet::DoModal

Modal özellik sayfası görüntüler.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa İDOK veya IDCANCEL; aksi takdirde 0 veya -1. Özellik sayfası sihirbaz olarak kurulmuşsa [(bkz. SetWizardMode),](#setwizardmode) `DoModal` ID_WIZFINISH veya IDCANCEL döndürür.

### <a name="remarks"></a>Açıklamalar

İade değeri, özellik sayfasını kapatan denetimin kimliğine karşılık gelir. Bu işlev döndükten sonra, özellik sayfasına karşılık gelen pencereler ve tüm sayfalar yok edilmiş olur. Nesnelerin kendileri hala var olacaktır. Genellikle, IDOK döndükten sonra `DoModal` [CPropertyPage](../../mfc/reference/cpropertypage-class.md) nesnelerinden veri alırsınız.

Modeless özellik sayfasını görüntülemek için bunun yerine [Oluştur'u](#create) arayın.

Bir özellik sayfası ilgili iletişim kaynağından oluşturulduğunda, ilk şans özel duruma neden olabilir. Bu, sayfa oluşturulmadan önce iletişim kaynağının stilini gerekli stilde değiştiren özellik sayfasından kaynaklanır. Kaynaklar genellikle salt okunur olduğundan, bu bir özel durum neden olur. Sistem özel durumu işler ve değiştirilen kaynağın bir kopyasını yapar. Bu nedenle ilk şans özel durumu yoksayılabilir.

> [!NOTE]
> Bu özel durum, eşzamanlı özel durum işleme modeliyle derleniyorsanız, işletim sistemi tarafından ele alınmalıdır. Özel durum işleme modelleri hakkında daha fazla bilgi için bkz: [/EH (Özel Durum Taşıma Modeli).](../../build/reference/eh-exception-handling-model.md) Bu durumda, aramayı, örneğin, tüm özel durumları işlediği bir C++ try-catch `CPropertySheet::DoModal` bloğuyla `catch (...)`sarmayın. Bu blok, işletim sistemi için amaçlanan özel durumu işler ve öngörülemeyen davranışlara neden olur. Ancak, Access İhlali özel durum işletim sistemine geçirilir belirli özel durum türleri veya yapılandırılmış özel durum işleme ile C++ özel durum işleme güvenle kullanabilirsiniz.

Bu ilk şans özel durum oluşturmayı önlemek için, özellik sayfasının doğru [Pencere Stillerine](../../mfc/reference/styles-used-by-mfc.md#window-styles)sahip olduğunu el ile garanti edebilirsiniz. Bir özellik sayfası için aşağıdaki stilleri ayarlamanız gerekir:

- DS_3DLOOK

- DS_CONTROL

- Ws_chıld

- WS_TABSTOP

İlk şans özel durum larını neden olmadan aşağıdaki isteğe bağlı stilleri kullanabilirsiniz:

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

Özellik sayfalarıyla uyumlu olmadığından diğer tüm Windows stillerini devre dışı kılabilir. Bu tavsiye genişletilmiş stiller için geçerli değildir. Bu standart stilleri uygun şekilde ayarlamak, özellik sayfasının değiştirilmesi gerekmediğini garanti eder ve ilk şans özel durumu oluşturmayı önler.

### <a name="example"></a>Örnek

CPropertySheet için örneğe [bakın:AddPage](#addpage).

## <a name="cpropertysheetenablestackedtabs"></a><a name="enablestackedtabs"></a>CPropertySheet::EnableStackedTabs

Bir özellik sayfasına sekme satırları nın yığılıp yığılmayacağını gösterir.

```
void EnableStackedTabs(BOOL bStacked);
```

### <a name="parameters"></a>Parametreler

*bYığılmış*<br/>
Yığılmış sekmelerin özellik sayfasında etkin olup olmadığını gösterir. *bStacked'ı* FALSE'a ayarlayarak yığılmış etiket satırlarını devre dışı bırak.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir özellik sayfasının özellik sayfasının genişliğinde tek bir satıra sığmayacak kadar sekmeleri varsa, sekmeler birden çok satırda istifler. Sekmeleri istiflemek yerine kaydırma sekmelerini `EnableStackedTabs` kullanmak için, [DoModal](#domodal) veya [Create'i](#create)aramadan önce FALSE'a ayarlanmış *bStacked* ile arayın.

Bir modal veya modeless özellik sayfası oluştururken aramanız `EnableStackedTabs` gerekir. Bu stili türetilmiş `CPropertySheet`bir sınıfa dahil etmek için WM_CREATE için bir ileti işleyicisi yazın. CWnd geçersiz sürümünde::OnCreate , temel `EnableStackedTabs( FALSE )` sınıf uygulamasını aramadan önce arayın. [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#134](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]

## <a name="cpropertysheetenddialog"></a><a name="enddialog"></a>CPropertySheet::EndDialog

Özellik sayfasını sonlandırır.

```
void EndDialog(int nEndID);
```

### <a name="parameters"></a>Parametreler

*nEndID*<br/>
Özellik sayfasının iade değeri olarak kullanılacak tanımlayıcı.

### <a name="remarks"></a>Açıklamalar

Tamam, İptal veya Kapat düğmesine basıldığında bu üye işlev çerçeve tarafından çağrılır. Özellik sayfasını kapatması gereken bir olay oluşursa bu üye işlevi arayın.

Bu üye işlev yalnızca bir modal iletişim kutusu ile kullanılır.

### <a name="example"></a>Örnek

[CPropertySheet::PressButton](#pressbutton)için örneğe bakın.

## <a name="cpropertysheetgetactiveindex"></a><a name="getactiveindex"></a>CpropertySheet::GetActiveIndex

Özellik sayfası penceresinin etkin sayfasının dizin numarasını alır ve döndürülen dizin numarasını `GetPage`parametre olarak kullanır.

```
int GetActiveIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkin sayfanın dizin numarası.

### <a name="example"></a>Örnek

CPropertySheet örneğine [bakın:GetActivePage](#getactivepage).

## <a name="cpropertysheetgetactivepage"></a><a name="getactivepage"></a>CpropertySheet::GetActivePage

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

## <a name="cpropertysheetgetpage"></a><a name="getpage"></a>CPropertySheet::GetPage

Bu özellik sayfasında belirtilen sayfaya bir işaretçi döndürür.

```
CPropertyPage* GetPage(int nPage) const;
```

### <a name="parameters"></a>Parametreler

*nPage*<br/>
0'dan başlayan istenilen sayfanın dizini. Dahil olmak üzere, özellik sayfasındaki sayfa sayısından 0 ile bir arasında olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

sayfanın işaretçisi *nPage* parametresine karşılık geliyor.

### <a name="example"></a>Örnek

CPropertyPage örneğine [bakın::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).

## <a name="cpropertysheetgetpagecount"></a><a name="getpagecount"></a>CpropertySheet::GetPageCount

Özellik sayfasında şu anda bulunan sayfa sayısını belirler.

```
int GetPageCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfasındaki sayfa sayısı.

### <a name="example"></a>Örnek

CPropertyPage örneğine [bakın::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).

## <a name="cpropertysheetgetpageindex"></a><a name="getpageindex"></a>CpropertySheet::GetPageIndex

Özellik sayfasında belirtilen sayfanın dizin numarasını alır.

```
int GetPageIndex(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*pPage*<br/>
Bulunacak dizinle sayfaya işaret edin. NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Bir sayfanın dizin numarası.

### <a name="remarks"></a>Açıklamalar

Örneğin, SetActivePage `GetPageIndex` veya [GetPage'i](#setactivepage) kullanmak için sayfa [GetPage](#getpage)dizini almak için kullanılır.

### <a name="example"></a>Örnek

CPropertySheet örneğine [bakın:GetActivePage](#getactivepage).

## <a name="cpropertysheetgettabcontrol"></a><a name="gettabcontrol"></a>CpropertySheet::gettabcontrol

Sekme denetimine özgü bir şey yapmak için sekme denetimine işaretçi salar (diğer bir [deyişle, CTabCtrl'daki](../../mfc/reference/ctabctrl-class.md)API'lerden herhangi birini kullanmak için).

```
CTabCtrl* GetTabControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekme denetimi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Örneğin, başlatma sırasında sekmelerin her birine bit eşlemleri eklemek istiyorsanız bu üye işlevi arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#136](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]

## <a name="cpropertysheetm_psh"></a><a name="m_psh"></a>CPropertySheet::m_psh

Üyeleri [PROPSHEETHEADER](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2)özelliklerini depolayan bir yapı.

### <a name="remarks"></a>Açıklamalar

Bu yapıyı, özellik sayfasının oluşturulduktan sonra ancak [DoModal](#domodal) üye işlevi ile görüntülenmeden önce görünümünü ortaya çıkarmak için kullanın. Örneğin, *dwSize* üyesini `m_psh` özellik sayfasının sahip olmasını istediğiniz boyuta ayarlayın.

Üyelerinin listesi de dahil olmak üzere bu yapı hakkında daha fazla bilgi için Windows SDK'daki PROPSHEETHEADER sayfasına bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#143](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]

## <a name="cpropertysheetmapdialogrect"></a><a name="mapdialogrect"></a>CPropertySheet::MapDialogRect

Dikdörtgenin iletişim kutusu birimlerini ekran birimlerine dönüştürür.

```
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*Lprect*<br/>
Dönüştürülecek iletişim kutusu koordinatlarını içeren bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine işaret eder.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu birimleri, iletişim kutusu metni için kullanılan yazı tipindeki karakterlerin ortalama genişliği ve yüksekliğinden türetilen geçerli iletişim kutusu temel birimi açısından belirtilir. Yatay birim, iletişim kutusu taban genişliği biriminin dörtte biridir ve bir dikey birim iletişim kutusu taban yüksekliği biriminin sekizde biridir.

[GetDialogBaseUnits](/windows/win32/api/winuser/nf-winuser-getdialogbaseunits) Windows işlevi sistem yazı tipi için boyut bilgilerini döndürür, ancak kaynak tanım dosyasındaki DS_SETFONT stilini kullanırsanız her özellik sayfası için farklı bir yazı tipi belirtebilirsiniz. Windows SDK'da açıklanan [MapDialogRect](/windows/win32/api/winuser/nf-winuser-mapdialogrect) Windows işlevi, bu iletişim kutusu için uygun yazı tipini kullanır.

Üye `MapDialogRect` işlev, kartbirimi oluşturmak veya bir kutu içinde bir denetim konumlandırmak için dikdörtgenin kullanılabilmesi için *lpRect'teki* iletişim kutusu birimlerini ekran birimleriyle (pikseller) değiştirir.

## <a name="cpropertysheetoninitdialog"></a><a name="oninitdialog"></a>CPropertySheet::OnInitDialog

Özellik sayfası başlatmayı artırmak için geçersiz kılar.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın giriş odağının özellik sayfasındaki denetimlerden birine ayarlayıp ayarlamadığını belirtir. Sıfırsız `OnInitDialog` dönerse, Windows giriş odağı özellik sayfasındaki ilk denetime ayarlar. Uygulama, yalnızca giriş odağının özellik sayfasındaki denetimlerden birine açıkça ayarlamısa 0 döndürebilir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, WM_INITDIALOG iletisine yanıt olarak çağrılır. Bu ileti, özellik sayfası görüntülenmeden hemen önce gerçekleşen [Create](#create) veya [DoModal](#domodal) aramaları sırasında özellik sayfasına gönderilir.

Özellik sayfası başharfe atıldığında özel işleme gerçekleştirmeniz gerekiyorsa bu üye işlevi geçersiz kılın. Geçersiz kılınan sürümde, önce taban `OnInitDialog` sınıfı arayın, ancak geri dönüş değerini göz ardı edin. Normalde geçersiz kılınan üye işlevinizden TRUE'ya geri dönersiniz.

Bu üye işlev için ileti eşlemi girişine gerek yoktur.

## <a name="cpropertysheetpressbutton"></a><a name="pressbutton"></a>CPropertySheet::PressButton

Bir özellik sayfasında belirtilen düğmenin seçimini simüle eder.

```
void PressButton(int nButton);
```

### <a name="parameters"></a>Parametreler

*nDüğme*<br/>
nButton : Basılacak düğmeyi tanımlar. Bu parametre aşağıdaki değerlerden biri olabilir:

- PSBTN_BACK Geri düğmesini seçer.

- PSBTN_NEXT Sonraki düğmesini seçer.

- PSBTN_FINISH Bitiş düğmesini seçer.

- PSBTN_OK Tamam düğmesini seçer.

- PSBTN_APPLYNOW Şimdi Uygula düğmesini seçer.

- PSBTN_CANCEL İptal düğmesini seçer.

- PSBTN_HELP Yardım düğmesini seçer.

### <a name="remarks"></a>Açıklamalar

Windows SDK Pressbutton iletisi hakkında daha fazla bilgi için [PSM_PRESSBUTTON](/windows/win32/Controls/psm-pressbutton) bakın.

Çağrı, `PressButton` [PSN_APPLY](/windows/win32/Controls/psn-apply) bildirimini bir özellik sayfasından çerçeveye göndermez. Bu bildirimi göndermek için [CPropertyPage'i arayın::OnOK.](../../mfc/reference/cpropertypage-class.md#onok)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#137](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]

## <a name="cpropertysheetremovepage"></a><a name="removepage"></a>CÖzellik Sayfası::RemovePage

Bir sayfayı özellik sayfasından kaldırır ve ilişkili pencereyi yok eder.

```
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>Parametreler

*pPage*<br/>
Özellik sayfasından kaldırılacak sayfaya işaret edin. NULL olamaz.

*nPage*<br/>
Kaldırılacak sayfanın dizin. Dahil olmak üzere, özellik sayfasındaki sayfa sayısından 0 ile bir arasında olmalıdır.

### <a name="remarks"></a>Açıklamalar

[CPropertyPage](../../mfc/reference/cpropertypage-class.md) nesnesinin kendisi, pencerenin sahibi `CPropertySheet` kapatılana kadar yok edilmez.

## <a name="cpropertysheetsetactivepage"></a><a name="setactivepage"></a>CpropertySheet::SetActivePage

Etkin sayfayı değiştirir.

```
BOOL SetActivePage(int nPage);
BOOL SetActivePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parametreler

*nPage*<br/>
Ayarlanan sayfanın dizin. Bu, özellik sayfasındaki sayfa sayısından 0 ile bir arasında olmalıdır.

*pPage*<br/>
Özellik sayfasında ayarlanan sayfaya işaret edin. NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfası başarıyla etkinleştirilirse sıfıra inmez; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Örneğin, bir `SetActivePage` kullanıcının bir sayfadaki eylemi başka bir sayfanın etkin sayfa olmasına neden olacaksa kullanın.

### <a name="example"></a>Örnek

CPropertySheet örneğine [bakın:GetActivePage](#getactivepage).

## <a name="cpropertysheetsetfinishtext"></a><a name="setfinishtext"></a>CpropertySheet::SetFinishText

Bitiş komutu düğmesindeki metni ayarlar.

```
void SetFinishText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*lpszMetin*<br/>
Bitiş komutu düğmesinde görüntülenecek metni işaret edin.

### <a name="remarks"></a>Açıklamalar

Bitiş `SetFinishText` komutu düğmesindeki metni görüntülemek için arayın ve kullanıcı sihirbazın son sayfasındaki eylemi tamamladıktan sonra Sonraki ve Geri düğmelerini gizleyin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

## <a name="cpropertysheetsettitle"></a><a name="settitle"></a>CPropertySheet::SetTitle

Özellik sayfasının başlığını (çerçeve penceresinin başlık çubuğunda görüntülenen metin) belirtir.

```
void SetTitle(
    LPCTSTR lpszText,
    UINT nStyle = 0);
```

### <a name="parameters"></a>Parametreler

*nStyle*<br/>
Özellik sayfası başlığının stilini belirtir. Stil 0 veya PSH_PROPTITLE olarak belirtilmelidir. Stil PSH_PROPTITLE olarak ayarlanırsa, başlık olarak belirtilen metinden sonra "Özellikler" sözcüğü görüntülenir. Örneğin, arama `SetTitle`("Basit", PSH_PROPTITLE) "Basit Özellikler" özelliği sayfası başlığıyla sonuçlanır.

*lpszMetin*<br/>
Özellik sayfasının başlık çubuğunda başlık olarak kullanılacak metne işaret edin.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir özellik sayfası özellik sayfası oluşturucudaki resim yazısı parametresini kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#139](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]

## <a name="cpropertysheetsetwizardbuttons"></a><a name="setwizardbuttons"></a>CPropertySheet::SetWizardButtons

Sihirbaz özellik sayfasında Geri, İleri veya Bitiş düğmesini etkinleştirir veya devre dışı kılabilir.

```
void SetWizardButtons(DWORD dwFlags);
```

### <a name="parameters"></a>Parametreler

*Dwflags*<br/>
Sihirbaz düğmelerinin işlevini ve görünümünü özelleştiren bir bayrak kümesi. Bu parametre aşağıdaki değerlerin bir birleşimi olabilir:

- PSWIZB_BACK Geri düğmesi

- PSWIZB_NEXT Sonraki düğme

- PSWIZB_FINISH Bitiş düğmesi

- PSWIZB_DISABLEDFINISH Devre Dışı Bitiş düğmesi

### <a name="remarks"></a>Açıklamalar

Yalnızca `SetWizardButtons` iletişim kutusu açıldıktan sonra arayın; `SetWizardButtons` [DoModal'ı](#domodal)aramadan önce arayama. Genellikle, CPropertyPage `SetWizardButtons` aramanız [gerekir::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).

Kullanıcı sihirbazı tamamladıktan sonra Bitiş düğmesindeki metni değiştirmek veya Sonraki ve Geri düğmelerini gizlemek istiyorsanız [SetFinishText'i](#setfinishtext)arayın. Bitiş ve Sonraki için aynı düğmenin paylaşıldığına dikkat edin. Aynı anda Bir Bitiş veya İleri düğmesini görüntüleyebilirsiniz, ancak her ikisini birden görüntülemezsiniz.

### <a name="example"></a>Örnek

`CPropertySheet` A'nın üç sihirbaz `CStylePage` `CColorPage`özelliği `CShapePage`vardır: , , ve .  Aşağıdaki kod parçası, sihirbaz özelliği sayfasındaki **Geri** ve **Sonraki** düğmelerini nasıl etkinleştirip devre dışı kkarşılayacak olduğunu gösterir.

[!code-cpp[NVC_MFCDocView#140](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]

[!code-cpp[NVC_MFCDocView#141](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

## <a name="cpropertysheetsetwizardmode"></a><a name="setwizardmode"></a>CpropertySheet::SetWizardMode

Sihirbaz olarak bir özellik sayfası kurar.

```
void SetWizardMode();
```

### <a name="remarks"></a>Açıklamalar

Sihirbaz özelliği sayfasının önemli bir özelliği, kullanıcının sekmeler yerine İleri veya Bitiş, Geri ve İptal düğmelerini kullanarak gezinmesidir.

`SetWizardMode` [DoModal'ı](#domodal)aramadan önce arayın. Aradıktan `SetWizardMode`sonra, `DoModal` ID_WIZFINISH (kullanıcı Finish düğmesiyle kapanırsa) veya IDCANCEL'ı iade edecektir.

`SetWizardMode`PSH_WIZARD bayrağını ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#142](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Numune CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[MFC Numune CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
