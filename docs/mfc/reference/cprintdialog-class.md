---
title: CPrintDialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- CPrintDialog
- AFXDLGS/CPrintDialog
- AFXDLGS/CPrintDialog::CPrintDialog
- AFXDLGS/CPrintDialog::CreatePrinterDC
- AFXDLGS/CPrintDialog::DoModal
- AFXDLGS/CPrintDialog::GetCopies
- AFXDLGS/CPrintDialog::GetDefaults
- AFXDLGS/CPrintDialog::GetDeviceName
- AFXDLGS/CPrintDialog::GetDevMode
- AFXDLGS/CPrintDialog::GetDriverName
- AFXDLGS/CPrintDialog::GetFromPage
- AFXDLGS/CPrintDialog::GetPortName
- AFXDLGS/CPrintDialog::GetPrinterDC
- AFXDLGS/CPrintDialog::GetToPage
- AFXDLGS/CPrintDialog::PrintAll
- AFXDLGS/CPrintDialog::PrintCollate
- AFXDLGS/CPrintDialog::PrintRange
- AFXDLGS/CPrintDialog::PrintSelection
- AFXDLGS/CPrintDialog::m_pd
helpviewer_keywords:
- CPrintDialog [MFC], CPrintDialog
- CPrintDialog [MFC], CreatePrinterDC
- CPrintDialog [MFC], DoModal
- CPrintDialog [MFC], GetCopies
- CPrintDialog [MFC], GetDefaults
- CPrintDialog [MFC], GetDeviceName
- CPrintDialog [MFC], GetDevMode
- CPrintDialog [MFC], GetDriverName
- CPrintDialog [MFC], GetFromPage
- CPrintDialog [MFC], GetPortName
- CPrintDialog [MFC], GetPrinterDC
- CPrintDialog [MFC], GetToPage
- CPrintDialog [MFC], PrintAll
- CPrintDialog [MFC], PrintCollate
- CPrintDialog [MFC], PrintRange
- CPrintDialog [MFC], PrintSelection
- CPrintDialog [MFC], m_pd
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
ms.openlocfilehash: d6d76ecb9042f299ce0c5e573870ee79954751c5
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178773"
---
# <a name="cprintdialog-class"></a>CPrintDialog sınıfı

Yazdırma için Windows ortak iletişim kutusu tarafından sağlanan hizmetleri kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CPrintDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPrintDialog::CPrintDialog](#cprintdialog)|Oluşturur bir `CPrintDialog` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|Yazdır iletişim kutusu görüntülenmeden yazıcı cihaz bağlamı oluşturur.|
|[CPrintDialog::DoModal](#domodal)|İletişim kutusunu görüntüler ve kullanıcının seçim yapmanıza izin verir.|
|[CPrintDialog::GetCopies](#getcopies)|İstenen kopya sayısını alır.|
|[CPrintDialog::GetDefaults](#getdefaults)|Cihaz Varsayılanları iletişim kutusu görüntülenmeden alır.|
|[CPrintDialog::GetDeviceName](#getdevicename)|Şu anda seçili yazıcı cihazın adını alır.|
|[CPrintDialog::GetDevMode](#getdevmode)|Alır `DEVMODE` yapısı.|
|[CPrintDialog::GetDriverName](#getdrivername)|Şu anda seçili yazıcı sürücüsü adını alır.|
|[CPrintDialog::GetFromPage](#getfrompage)|Yazdırma aralığı başlangıç sayfası alır.|
|[CPrintDialog::GetPortName](#getportname)|Şu anda seçili yazıcı bağlantı noktasını adını alır.|
|[CPrintDialog::GetPrinterDC](#getprinterdc)|Yazıcı cihaz bağlamı için bir tanıtıcı alır.|
|[CPrintDialog::GetToPage](#gettopage)|Yazdırma aralığı bitiş sayfasının alır.|
|[CPrintDialog::PrintAll](#printall)|Belgenin tüm sayfalarının yazdırılıp yazdırılmayacağını belirler.|
|[CPrintDialog::PrintCollate](#printcollate)|Kopya istenen Harmanlanmış olup olmadığını belirler.|
|[CPrintDialog::PrintRange](#printrange)|Sayfa için belirtilen bir aralıktaki yazdırılıp yazdırılmayacağını belirler.|
|[CPrintDialog::PrintSelection](#printselection)|Yalnızca şu anda seçtiğiniz öğelerin yazdırılıp yazdırılmayacağını belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPrintDialog::m_pd](#m_pd)|Özelleştirmek için kullanılan bir yapının bir `CPrintDialog` nesne.|

## <a name="remarks"></a>Açıklamalar

Ortak yazdırma iletişim kutuları, yazdırma ve yazdırma Kurulum iletişim kutusu Windows standartları ile tutarlı bir şekilde uygulamak için kolay bir yol sağlar.

> [!NOTE]
>  `CPrintDialogEx` Sınıfı Windows Print özellik sayfası tarafından sağlanan hizmetleri kapsüller. Daha fazla bilgi için [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) genel bakış.

`CPrintDialog`ın işlevi,'ın yerini [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md), hem Yazdırma Kurulumu ve sayfa düzeni için ortak bir iletişim kutusu ile sağlamak için tasarlanmıştır.

Yazdırma işlemi uygulamanız için birçok yönden işlemek için Framework güvenebilirsiniz. Bu durumda, çerçeve otomatik olarak yazdırma için Windows ortak iletişim kutusu görüntüler. Ayrıca, uygulamanız için yazdırma framework çağırıp ancak kendi yazdırma iletişim kutusu ile ortak Yazdır iletişim kutusunu geçersiz. Yazdırma görevleri işlemek için çerçeve kullanma hakkında daha fazla bilgi için bkz [yazdırma](../../mfc/printing.md).

Uygulamanızın framework'ün katılımı olmadan yazdırmak işlemesini istiyorsanız, kullanabileceğiniz `CPrintDialog` sağlanan oluşturucuyla "olduğu gibi" sınıf ya da kendi iletişim sınıftan türetilip `CPrintDialog` ve ihtiyaçlarınıza uyacak şekilde bir oluşturucu yazma. Sınıfından türetildiği her iki durumda da, bu iletişim kutularından standart MFC iletişim kutuları gibi davranır `CCommonDialog`.

Kullanılacak bir `CPrintDialog` nesne, ilk nesnesini kullanarak oluşturun `CPrintDialog` Oluşturucusu. İletişim kutusu oluşturulmuş bir kez ayarlayabilir veya herhangi bir değer değiştirme [m_pd](#m_pd) Yapısı iletişim kutusunun denetimleri değerlerini başlatılamadı. `m_pd` Yapısıdır türünü [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda). Bu yapı hakkında daha fazla bilgi için Windows SDK'sı bakın.

Kendi işleyicileri sağlamazsanız `m_pd` için `hDevMode` ve `hDevNames` üyeleri, Windows işlevi çağırma mutlaka `GlobalFree` iletişim kutusu ile işiniz bittiğinde bu tanıtıcıları için. Framework'ün yazıcı ayarları uygulama tarafından sağlanan kullanırken `CWinApp::OnFilePrintSetup`, bu tanıtıcıları ücretsiz gerekmez. İşler tarafından korunur `CWinApp` ve serbest bırakılan `CWinApp`'s yıkıcı. Yalnızca bu tanıtıcıları kullanırken boşaltmak gerekli olan `CPrintDialog` tek başına.

İletişim kutusu denetimleri başlatılıyor sonra çağrı `DoModal` iletişim kutusunu görüntülemek ve yazdırma seçeneklerini seçmesini sağlamak için üye işlevi. `DoModal` Kullanıcı Tamam (IDOK) veya iptal edin (IDCANCEL) düğmesi seçili olup olmadığını döndürür.

Varsa `DoModal` IDOK, döndürür birini kullanabilirsiniz `CPrintDialog`ait üye işlevleri tarafından kullanıcı giriş bilgileri alınamıyor.

`CPrintDialog::GetDefaults` Üye işlevi, geçerli bir yazıcı Varsayılanları iletişim kutusu görüntülenmeden almak için kullanışlıdır. Bu üye işlevi, kullanıcı etkileşimi gerektirir.

Windows kullanabileceğiniz `CommDlgExtendedError` işlevi bir hata iletişim kutusunun başlatma sırasında oluşup oluşmadığını belirleyin ve hata hakkında daha fazla bilgi edinin. Bu işlev hakkında daha fazla bilgi için Windows SDK'sı bakın.

`CPrintDialog` üzerinde COMMDLG kullanır. Windows 3.1 ve sonraki sürümleri ile birlikte gelen DLL dosyası.

Özelleştir iletişim kutusu için öğesinden bir sınıf türetin `CPrintDialog`, bir özel iletişim şablonu sağlar ve genişletilmiş denetimlerden bildirim iletilerini işlemek için ileti eşlemesi ekleyin. İşlenmemiş tüm iletiler için temel sınıf geçirilmelidir. Kanca işlevini özelleştirme gerekli değildir.

Farklı iletişim kutusunda yazdırma ve yazdırma Kurulum olup olmamasına bağlı olarak aynı iletiyi işlemek için bir sınıf her iletişim kutusu için türetilmesi gerekir. Windows geçersiz kılmalısınız `AttachOnSetup` Yazdır iletişim kutusu içinde Yazdırma Kurulumu düğme seçildiğinde yeni iletişim kutusu oluşturulmasını yürüten işlev.

Kullanma hakkında daha fazla bilgi için `CPrintDialog`, bkz: [ortak iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdlgs.h

##  <a name="cprintdialog"></a>  CPrintDialog::CPrintDialog

Bir Windows yazdırma veya Sayfa Yapısı iletişim nesnesi oluşturur.

```
CPrintDialog(
    BOOL bPrintSetupOnly,
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*bPrintSetupOnly*<br/>
Standart Windows yazdırma iletişim kutusu veya yazıcı ayarları iletişim kutusunda görüntülenip görüntülenmeyeceğini belirtir. Bu parametre için standart Windows Sayfa Yapısı iletişim kutusu görüntülemek true olarak ayarlayın. Windows Yazdır iletişim kutusunu görüntülemek için FALSE olarak ayarlayın. Varsa *bPrintSetupOnly* yanlış, bir yazdırma Kurulumu yazdırma iletişim kutusunda seçenek düğmesini gösterilmeye devam eder.

*CertOpenStore*<br/>
Bit düzeyinde OR işleci kullanılarak birleştirilen iletişim kutusunun ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayraklar. Örneğin, PD_ALLPAGES bayrağı, tüm belge sayfaları varsayılan yazdırma aralığı ayarlar. Bkz: [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) yapısı içinde bu bayraklar hakkında daha fazla bilgi için Windows SDK'sı.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahip penceresine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yalnızca bir nesne oluşturur. Kullanım `DoModal` iletişim kutusunu görüntülemek için üye işlevi.

Oluşturucuyla çağırdığınızda unutmayın *bPrintSetupOnly* FALSE olarak ayarlanırsa PD_RETURNDC bayrağı otomatik olarak kullanılır. Arama sonra `DoModal`, `GetDefaults`, veya `GetPrinterDC`, yazıcı DC içinde döndürülen `m_pd.hDC`. Bu DC çağrısı ile serbest bırakılmalıdır [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) çağıran tarafından `CPrintDialog`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]

##  <a name="createprinterdc"></a>  CPrintDialog::CreatePrinterDC

Bir yazıcı cihaz bağlamı (DC) oluşturur [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) ve [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) yapıları.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan yazıcı cihaz bağlamına işleyin.

### <a name="remarks"></a>Açıklamalar

Bu DC'nin geçerli yazıcı DC olarak kabul edilir ve daha önce edindiğiniz diğer yazıcı DC'leri kullanıcı tarafından silinmesi gerekir. Bu işlev çağrılabilir ve Yazdır iletişim kutusu görüntülenmeden elde edilen DC kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]

##  <a name="domodal"></a>  CPrintDialog::DoModal

Windows ortak Yazdır iletişim kutusunu görüntüler ve kullanıcının kopyalar, sayfa aralığı sayısı gibi çeşitli yazdırma seçeneklerini seçmesini sağlar ve kopya Harmanlanmış.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

IDOK veya IDCANCEL. IDCANCEL döndürülürse, Windows Arama [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) hata oluşup oluşmadığını belirlemek için işlevi.

IDOK ve IDCANCEL kullanıcı Tamam'ı veya iptal düğmesi seçili olup olmadığını gösteren sabittir.

### <a name="remarks"></a>Açıklamalar

Çeşitli Yazdır iletişim kutusu seçenekleri üyeleri ayarlayarak başlatmak istiyorsanız `m_pd` yapısı, bunu çağırmadan önce yapmalısınız `DoModal`, ancak iletişim nesnesi oluşturulur.

Arama sonra `DoModal`, diğer üye işlevleri, kullanıcı giriş bilgileri ve Ayarları iletişim kutusuna alınacak çağırabilirsiniz.

Oluşturucuyla çağırdığınızda unutmayın *bPrintSetupOnly* FALSE olarak ayarlanırsa PD_RETURNDC bayrağı otomatik olarak kullanılır. Arama sonra `DoModal`, `GetDefaults`, veya `GetPrinterDC`, yazıcı DC içinde döndürülen `m_pd.hDC`. Bu DC çağrısı ile serbest bırakılmalıdır [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) çağıran tarafından `CPrintDialog`.

### <a name="example"></a>Örnek

  Örneğin bakın [CPrintDialog::CreatePrinterDC](#createprinterdc).

##  <a name="getcopies"></a>  CPrintDialog::GetCopies

İstenen kopya sayısını alır.

```
int GetCopies() const;
```

### <a name="return-value"></a>Dönüş Değeri

İstenen kopya sayısı.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra bu işlevi çağırın `DoModal` istenen kopya sayısı alınamıyor.

### <a name="example"></a>Örnek

  Örneğin bakın [CPrintDialog::PrintCollate](#printcollate).

##  <a name="getdefaults"></a>  CPrintDialog::GetDefaults

Varsayılan yazıcı cihaz varsayılan bir iletişim kutusu görüntülenmeden alır.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Alınan değerleri yerleştirilir `m_pd` yapısı.

Bazı durumlarda, bu işlev çağrısı çağıracak [Oluşturucusu](#cprintdialog) için `CPrintDialog` ile *bPrintSetupOnly* FALSE olarak ayarlayın. Bu gibi durumlarda, bir yazıcı DC ve `hDevNames` ve `hDevMode` (iki tanıtıcıları bulunan `m_pd` veri üyesi) otomatik olarak ayrılır.

IF için oluşturucu `CPrintDialog` ile çağrıldı *bPrintSetupOnly* FALSE olarak ayarlanırsa, bu işlev değil yalnızca döndürür `hDevNames` ve `hDevMode` bulunan `m_pd.hDevNames` ve `m_pd.hDevMode`), çağırana ancak Ayrıca, bir yazıcı DC döndürür `m_pd.hDC`. DC yazıcı silip Windows çağrı çağıranın sorumluluğundadır [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree) işlevi ile işiniz bittiğinde tutamaçları üzerinde `CPrintDialog` nesne.

### <a name="example"></a>Örnek

Bu kod parçası varsayılan yazıcının cihaz bağlamını alır ve yazıcı inç başına nokta çözünürlüğünü kullanıcıya bildirir. (Bu öznitelik yazıcının özellikler genellikle DPI adlandırılır.)

[!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]

##  <a name="getdevicename"></a>  CPrintDialog::GetDeviceName

Şu anda seçili yazıcı cihazın adını alır.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazıcının adı.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra bu işlevi çağırın [DoModal](#domodal) şu anda seçili yazıcının veya arama sonra adı almak için [GetDefaults](#getdefaults) varsayılan yazıcı geçerli cihaz Varsayılanları alınamadı. Bir işaretçi kullanın `CString` tarafından döndürülen nesne `GetDeviceName` değeri olarak `lpszDeviceName` çağrıda [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

### <a name="example"></a>Örnek

Bu kod parçası, kullanıcının varsayılan yazıcı adını ve bağlantı noktasını, yazıcı kullanır biriktirici adının yanı sıra bağlı olduğu gösterilmektedir. Kod yazan bir ileti kutusu gösterebilir "HP LaserJet IIIP açıksa varsayılan yazıcıyı \\\server\share kullanarak winspool.", örneğin.

[!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]

##  <a name="getdevmode"></a>  CPrintDialog::GetDevMode

Alır `DEVMODE` yapısı.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

[DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) cihaz başlatma ve yazdırma sürücüsü ortamı hakkında bilgi içeren veri yapısı. Windows ile bu yapı tarafından gerçekleştirilecek bellek kilidini açmanız gerekir [GlobalUnlock](/windows/desktop/api/winbase/nf-winbase-globalunlock) Windows SDK'da açıklanan işlevi.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra bu işlevi çağırın [DoModal](#domodal) veya [GetDefaults](#getdefaults) yazdırma cihaz hakkında bilgi almak için.

### <a name="example"></a>Örnek

  Örneğin bakın [CPrintDialog::PrintCollate](#printcollate).

##  <a name="getdrivername"></a>  CPrintDialog::GetDriverName

Şu anda seçili yazıcı sürücüsü adını alır.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` sistem tarafından tanımlanan sürücü adı belirtme.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra bu işlevi çağırın [DoModal](#domodal) veya [GetDefaults](#getdefaults) sistem tarafından tanımlanan yazıcı aygıt sürücüsünün adını alamadı. Bir işaretçi kullanın `CString` tarafından döndürülen nesne `GetDriverName` değeri olarak `lpszDriverName` çağrıda [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

### <a name="example"></a>Örnek

  Örneğin bakın [CPrintDialog::GetDeviceName](#getdevicename).

##  <a name="getfrompage"></a>  CPrintDialog::GetFromPage

Yazdırma aralığı başlangıç sayfası alır.

```
int GetFromPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başlangıç sayfası aralığında yazdırılacak sayfa sayısı.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra bu işlevi çağırın `DoModal` aralıktaki başlangıç sayfa numarası yazdırılacak sayfaların alınacak.

### <a name="example"></a>Örnek

  Örneğin bakın [CPrintDialog::m_pd](#m_pd).

##  <a name="getportname"></a>  CPrintDialog::GetPortName

Şu anda seçili yazıcı bağlantı noktasını adını alır.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili yazıcı bağlantı noktasını adı.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra bu işlevi çağırın [DoModal](#domodal) veya [GetDefaults](#getdefaults) seçili yazıcı bağlantı noktasını adını almak için.

### <a name="example"></a>Örnek

  Örneğin bakın [CPrintDialog::GetDeviceName](#getdevicename).

##  <a name="getprinterdc"></a>  CPrintDialog::GetPrinterDC

Yazıcı cihaz bağlamı için bir tanıtıcı alır.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa yazıcı cihaz bağlamı için bir tanıtıcı; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Varsa *bPrintSetupOnly* parametresinin `CPrintDialog` Oluşturucusu olan FALSE (Yazdır iletişim kutusunun görüntülendiğini gösterir), ardından `GetPrinterDC` yazıcı cihaz bağlamı için bir tanıtıcı döndürür. Windows çağırmalıdır [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) işlevi işiniz bittiğinde, cihaz bağlam silmek için onu kullanarak.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]

##  <a name="gettopage"></a>  CPrintDialog::GetToPage

Yazdırma aralığı bitiş sayfasının alır.

```
int GetToPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bitiş sayfa aralığında yazdırılacak sayfa sayısı.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra bu işlevi çağırın `DoModal` aralığın bitiş sayfa numarası yazdırılacak sayfaların alınacak.

### <a name="example"></a>Örnek

  Örneğin bakın [CPrintDialog::m_pd](#m_pd).

##  <a name="m_pd"></a>  CPrintDialog::m_pd

Üyeleri iletişim nesnesinin özelliklerini depolamak için bir yapı.

```
PRINTDLG& m_pd;
```

### <a name="remarks"></a>Açıklamalar

Oluşturma sonrasında bir `CPrintDialog` nesne kullanabileceğiniz `m_pd` çeşitli yönlerini çağırmadan önce iletişim kutusunda ayarlanacak [DoModal](#domodal) üye işlevi. Daha fazla bilgi için `m_pd` yapısı için bkz: [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) Windows SDK.

Değiştirirseniz `m_pd` veri üyesi doğrudan, hiçbir varsayılan davranışı geçersiz kılar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]

##  <a name="printall"></a>  CPrintDialog::PrintAll

Belgenin tüm sayfalarının yazdırılıp yazdırılmayacağını belirler.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgedeki tüm sayfalar yazdırılır yoksa sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra bu işlevi çağırın `DoModal` belgedeki tüm sayfalarını yazdırma belirlemek için.

### <a name="example"></a>Örnek

  Örneğin bakın [CPrintDialog::m_pd](#m_pd).

##  <a name="printcollate"></a>  CPrintDialog::PrintCollate

Kopya istenen Harmanlanmış olup olmadığını belirler.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı iletişim kutusundaki collate onay kutusunu seçer olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra bu işlevi çağırın `DoModal` yazıcı belge yazdırılan tüm kopyalarını collate olup olmadığını belirlemek için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]

##  <a name="printrange"></a>  CPrintDialog::PrintRange

Sayfa için belirtilen bir aralıktaki yazdırılıp yazdırılmayacağını belirler.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir belgedeki sayfa aralığı yalnızca yazdırılması sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra bu işlevi çağırın `DoModal` yalnızca bir dizi belgedeki sayfa yazdırma belirlemek için.

### <a name="example"></a>Örnek

  Örneğin bakın [CPrintDialog::m_pd](#m_pd).

##  <a name="printselection"></a>  CPrintDialog::PrintSelection

Yalnızca şu anda seçtiğiniz öğelerin yazdırılıp yazdırılmayacağını belirler.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili öğeleri yazdırılması, yalnızca sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra bu işlevi çağırın `DoModal` yalnızca şu anda seçtiğiniz öğelerin yazdırma belirlemek için.

### <a name="example"></a>Örnek

  Örneğin bakın [CPrintDialog::m_pd](#m_pd).

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek DIBLOOK](../../visual-cpp-samples.md)<br/>
[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo Yapısı](../../mfc/reference/cprintinfo-structure.md)
