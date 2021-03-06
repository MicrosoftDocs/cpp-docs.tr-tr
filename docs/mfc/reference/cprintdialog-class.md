---
description: 'Daha fazla bilgi edinin: CPrintDialog sınıfı'
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
ms.openlocfilehash: f662f3d2a522dc3a53ea887bb1031e9431df2e3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343407"
---
# <a name="cprintdialog-class"></a>CPrintDialog sınıfı

Yazdırma için Windows ortak iletişim kutusu tarafından sunulan hizmetleri kapsüller.

## <a name="syntax"></a>Syntax

```
class CPrintDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPrintDialog:: CPrintDialog](#cprintdialog)|Bir `CPrintDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPrintDialog:: CreatePrinterDC](#createprinterdc)|Yazdır iletişim kutusunu görüntülemeden bir yazıcı cihaz bağlamı oluşturur.|
|[CPrintDialog::D oModal](#domodal)|İletişim kutusunu görüntüler ve kullanıcının seçim yapmasına izin verir.|
|[CPrintDialog:: Getkopyaların](#getcopies)|İstenen kopya sayısını alır.|
|[CPrintDialog:: GetDefaults](#getdefaults)|Bir iletişim kutusu görüntülemeden cihaz varsayılanlarını alır.|
|[CPrintDialog:: Getaygıtadı](#getdevicename)|Şu anda seçili olan yazıcı cihazının adını alır.|
|[CPrintDialog:: GetDevMode](#getdevmode)|Yapıyı alır `DEVMODE` .|
|[CPrintDialog:: Getsürücüadı](#getdrivername)|Şu anda seçili olan yazıcı sürücüsünün adını alır.|
|[CPrintDialog:: GetFromPage](#getfrompage)|Yazdırma aralığının başlangıç sayfasını alır.|
|[CPrintDialog:: GetPortName](#getportname)|Şu anda seçili olan yazıcı bağlantı noktasının adını alır.|
|[CPrintDialog:: GetPrinterDC](#getprinterdc)|Yazıcı cihaz bağlamına bir tanıtıcı alır.|
|[CPrintDialog:: GetToPage](#gettopage)|Yazdırma aralığının bitiş sayfasını alır.|
|[CPrintDialog::P Rinyüksekliğinde](#printall)|Belgenin tüm sayfalarının yazdırılması gerekip gerekmediğini belirler.|
|[CPrintDialog::P rintCollate](#printcollate)|Harmanlanmış kopyaların istenip istenmediğini belirler.|
|[CPrintDialog::P rintRange](#printrange)|Yalnızca belirli bir sayfa aralığının mi yazdırılacağını belirler.|
|[CPrintDialog::P rintSelection](#printselection)|Yalnızca şu anda seçili olan öğelerin yazdırılması gerekip gerekmediğini belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPrintDialog:: m_pd](#m_pd)|Bir nesneyi özelleştirmek için kullanılan bir yapı `CPrintDialog` .|

## <a name="remarks"></a>Açıklamalar

Ortak yazdırma iletişim kutuları, yazdırma ve yazdırma kurulum iletişim kutularını Windows standartlarıyla tutarlı bir şekilde uygulamak için kolay bir yol sağlar.

> [!NOTE]
> `CPrintDialogEx`Sınıfı, Windows yazdırma özelliği sayfası tarafından sunulan hizmetleri kapsüller. Daha fazla bilgi için bkz. [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) Overview.

`CPrintDialog`uygulamasının işlevselliği, hem yazdırma Kurulumu hem de sayfa kurulumu için ortak bir iletişim kutusu sağlamak üzere tasarlanan [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)'ın yerini almıştır.

Uygulamanız için yazdırma sürecinin birçok yönlerini işlemek üzere çerçevesini kullanabilirsiniz. Bu durumda, çerçeve, yazdırma için Windows ortak iletişim kutusunu otomatik olarak görüntüler. Ayrıca, uygulama için çerçeve işleyicisini yazdırma, ancak kendi Yazdır iletişim kutusuyla ortak Yazdır iletişim kutusunu geçersiz kılabilirsiniz. Yazdırma görevlerini işlemek için Framework 'ü kullanma hakkında daha fazla bilgi için [yazdırma](../../mfc/printing.md)makalesine bakın.

Uygulamanızın, Framework 'ün katılımı olmadan yazdırmayı işlemesini istiyorsanız, `CPrintDialog` "olduğu gibi" sınıfını, sağlanmış Oluşturucu ile kullanabilir veya kendi iletişim sınıfınızı kendi iletişim sınıfınızı türetebilir `CPrintDialog` ve gereksinimlerinize uyacak şekilde bir Oluşturucu yazabilirsiniz. Her iki durumda da, bu iletişim kutuları sınıfından türetildiklerinden standart MFC iletişim kutuları gibi davranır `CCommonDialog` .

Bir nesnesi kullanmak için `CPrintDialog` , önce oluşturucuyu kullanarak nesnesini oluşturun `CPrintDialog` . İletişim kutusu oluşturulduktan sonra, iletişim kutusu denetimlerinin değerlerini başlatmak için [m_pd](#m_pd) yapısındaki herhangi bir değeri ayarlayabilir veya değiştirebilirsiniz. `m_pd`Yapı [PrintDlg](/windows/win32/api/commdlg/ns-commdlg-printdlga)türündedir. Bu yapı hakkında daha fazla bilgi için Windows SDK bakın.

Ve üyeleri için kendi tanıtıcılarınızı sağlamadıysanız `m_pd` `hDevMode` `hDevNames` , `GlobalFree` iletişim kutusuyla işiniz bittiğinde bu tutamaçlar için Windows işlevini çağırdığınızdan emin olun. Çerçevesinin tarafından sunulan yazdırma Kurulumu uygulamasını kullanırken `CWinApp::OnFilePrintSetup` , bu tutamaçları serbest bırakmak zorunda değilsiniz. İşleyiciler tarafından korunur `CWinApp` ve `CWinApp` yıkıcısında serbest bırakılır. Yalnızca tek başına kullanılırken bu tutamaçları serbest bırakmak gereklidir `CPrintDialog` .

İletişim kutusu denetimlerini başlattıktan sonra, `DoModal` iletişim kutusunu göstermek ve kullanıcının yazdırma seçeneklerini seçmesine izin vermek için üye işlevini çağırın. `DoModal` kullanıcının Tamam (IDOK) veya Cancel (ıDCANCEL) düğmesini seçmediğini döndürür.

`DoModal`IDOK döndürürse, `CPrintDialog` Kullanıcı tarafından bilgi girişi almak için üye işlevlerinden birini kullanabilirsiniz.

`CPrintDialog::GetDefaults`Üye işlevi, geçerli yazıcı varsayılanlarını bir iletişim kutusu görüntülemeden almak için yararlıdır. Bu üye işlevi için Kullanıcı etkileşimi gerekmez.

`CommDlgExtendedError`İletişim kutusunun başlatılması sırasında hata oluşup oluşmadığını ve hata hakkında daha fazla bilgi Için Windows işlevini kullanabilirsiniz. Bu işlev hakkında daha fazla bilgi için Windows SDK bakın.

`CPrintDialog` , 3,1 ve üzeri Windows sürümleriyle birlikte gelen COMMDLG.DLL dosyasını kullanır.

İletişim kutusunu özelleştirmek için, öğesinden bir sınıf türetebilir `CPrintDialog` , özel bir iletişim kutusu şablonu sağlayın ve genişletilmiş denetimlerden gelen bildirim iletilerini işlemek için bir ileti eşlemesi ekleyin. İşlenmemiş tüm iletiler taban sınıfına geçirilmelidir. Kanca işlevinin özelleştirilmesi gerekli değildir.

İletişim kutusunun yazdırma veya yazdırma ayarları olmasına bağlı olarak aynı iletiyi farklı şekilde işlemek için her iletişim kutusu için bir sınıf türetmeniz gerekir. Ayrıca `AttachOnSetup` , Yazdır iletişim kutusu Içinde yazdırma ayarı düğmesi seçildiğinde yeni bir iletişim kutusu oluşturmayı Işleyen Windows işlevini de geçersiz kılmanız gerekir.

Kullanma hakkında daha fazla bilgi için `CPrintDialog` bkz. [ortak Iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[Ccommoniletişim kutusu](../../mfc/reference/ccommondialog-class.md)

`CPrintDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs. h

## <a name="cprintdialogcprintdialog"></a><a name="cprintdialog"></a> CPrintDialog:: CPrintDialog

Bir Windows yazdırma veya yazdırma kurulum iletişim kutusu nesnesi oluşturur.

```
CPrintDialog(
    BOOL bPrintSetupOnly,
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*yalnızca bprintsetup*<br/>
Standart Windows yazdırma iletişim kutusu veya yazdırma ayarı iletişim kutusunun görüntülenip görüntülenmeyeceğini belirtir. Standart Windows yazdırma Kurulumu iletişim kutusunu göstermek için bu parametreyi TRUE olarak ayarlayın. Windows Yazdır iletişim kutusunu göstermek için bu değeri FALSE olarak ayarlayın. *BPrintSetupOnly* false Ise, Yazdır iletişim kutusunda bir yazdırma ayarı seçeneği düğmesi hala görüntülenir.

*dwFlags*<br/>
Bit düzeyinde OR işleci kullanılarak birleştirilen iletişim kutusunun ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayrak. Örneğin, PD_ALLPAGES bayrağı varsayılan yazdırma aralığını belgenin tüm sayfalarına ayarlar. Bu bayraklar hakkında daha fazla bilgi için Windows SDK [PrintDlg](/windows/win32/api/commdlg/ns-commdlg-printdlga) yapısına bakın.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahip penceresine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yalnızca nesnesini oluşturur. `DoModal`İletişim kutusunu göstermek için üye işlevini kullanın.

Oluşturucuyu *bPrintSetupOnly* false olarak ayarlarsanız, pd_returndc bayrağının otomatik olarak kullanıldığını unutmayın. , Veya çağrıldıktan sonra ' `DoModal` `GetDefaults` `GetPrinterDC` de bir yazıcı DC 'si döndürülür `m_pd.hDC` . Bu DC, çağıran tarafından bir [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) çağrısıyla serbest bırakılmalıdır `CPrintDialog` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]

## <a name="cprintdialogcreateprinterdc"></a><a name="createprinterdc"></a> CPrintDialog:: CreatePrinterDC

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) ve [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) yapılarından bir yazıcı cihaz bağlamı (DC) oluşturur.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan yazıcı cihaz bağlamına yönelik tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu DC 'nin geçerli yazıcı DC olduğu varsayılır ve daha önce edinilen diğer yazıcı DC 'leri Kullanıcı tarafından silinmelidir. Bu işlev çağrılabilir ve yazdırma iletişim kutusu görüntülenmeden, sonuçta elde edilen DC kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]

## <a name="cprintdialogdomodal"></a><a name="domodal"></a> CPrintDialog::D oModal

Windows ortak Yazdır iletişim kutusunu görüntüler ve kullanıcının kopya sayısı, sayfa aralığı ve kopyaların harmanlanmasının yapılıp yapılmayacağını belirlemek gibi çeşitli yazdırma seçeneklerini seçmesine olanak sağlar.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

IDOK veya ıDCANCEL. IDCANCEL döndürülürse, bir hatanın oluşup oluşmadığını öğrenmek için Windows [Commıdextendebir](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini çağırın.

IDOK ve ıDCANCEL, kullanıcının Tamam veya Iptal düğmesini seçip seçmediğini belirten sabitlerdir.

### <a name="remarks"></a>Açıklamalar

Yapının üyelerini ayarlayarak çeşitli yazdırma iletişim kutusu seçeneklerini başlatmak isterseniz, bunu `m_pd` çağırmadan önce `DoModal` , ancak iletişim kutusu nesnesi oluşturulduktan sonra yapmanız gerekir.

Öğesini çağırdıktan sonra `DoModal` , Kullanıcı tarafından iletişim kutusuna ayarları veya bilgi girişini almak için diğer üye işlevlerini çağırabilirsiniz.

Oluşturucuyu *bPrintSetupOnly* false olarak ayarlarsanız, pd_returndc bayrağının otomatik olarak kullanıldığını unutmayın. , Veya çağrıldıktan sonra ' `DoModal` `GetDefaults` `GetPrinterDC` de bir yazıcı DC 'si döndürülür `m_pd.hDC` . Bu DC, çağıran tarafından bir [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) çağrısıyla serbest bırakılmalıdır `CPrintDialog` .

### <a name="example"></a>Örnek

  [CPrintDialog:: CreatePrinterDC](#createprinterdc)örneğine bakın.

## <a name="cprintdialoggetcopies"></a><a name="getcopies"></a> CPrintDialog:: Getkopyaların

İstenen kopya sayısını alır.

```
int GetCopies() const;
```

### <a name="return-value"></a>Dönüş Değeri

İstenen kopya sayısı.

### <a name="remarks"></a>Açıklamalar

`DoModal`İstenen kopya sayısını almak için çağrıldıktan sonra bu işlevi çağırın.

### <a name="example"></a>Örnek

  [CPrintDialog::P rintCollate](#printcollate)örneğine bakın.

## <a name="cprintdialoggetdefaults"></a><a name="getdefaults"></a> CPrintDialog:: GetDefaults

Varsayılan yazıcının cihaz varsayılan ayarlarını bir iletişim kutusu görüntülemeden alır.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Alınan değerler `m_pd` yapıya yerleştirilir.

Bazı durumlarda, bu işleve yapılan bir çağrı [](#cprintdialog) `CPrintDialog` *BPRINTSETUPONLY* değeri false olarak ayarlanan oluşturucuyu çağıracaktır. Bu durumlarda, bir yazıcı DC ve `hDevNames` ve `hDevMode` (veri üyesinde bulunan iki tanıtıcı `m_pd` ) otomatik olarak ayrılır.

İçin oluşturucusunun `CPrintDialog` adı *bPrintSetupOnly* false olarak ayarlandıysa, bu işlev yalnızca arayana döndürmez ve ' de yer alır `hDevNames` `hDevMode` `m_pd.hDevNames` `m_pd.hDevMode` , ancak aynı zamanda ' de bir yazıcı DC 'si döndürür `m_pd.hDC` . Bu, çağıranın yazıcı DC 'sini silme ve nesne ile işiniz bittiğinde Tanıtıcılarda Windows [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree) işlevini çağırma sorumluluğundadır `CPrintDialog` .

### <a name="example"></a>Örnek

Bu kod parçası, varsayılan yazıcının cihaz bağlamını ve raporlarını kullanıcıya, inç başına nokta olarak bir yazıcı çözünürlüğü olarak alır. (Yazıcı yeteneklerinin bu özniteliği genellikle DPı olarak adlandırılır.)

[!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]

## <a name="cprintdialoggetdevicename"></a><a name="getdevicename"></a> CPrintDialog:: Getaygıtadı

Şu anda seçili olan yazıcı cihazının adını alır.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili olan yazıcının adı.

### <a name="remarks"></a>Açıklamalar

Şu anda seçili olan yazıcının adını almak için [DoModal](#domodal) çağrıldıktan sonra veya varsayılan yazıcının geçerli cihaz varsayılanlarını almak Için [GetDefaults](#getdefaults) çağrıldıktan sonra bu işlevi çağırın. `CString` `GetDeviceName` `lpszDeviceName` [CDC:: CreateDC](../../mfc/reference/cdc-class.md#createdc)çağrısında değeri olarak döndürülen nesneye yönelik bir işaretçi kullanın.

### <a name="example"></a>Örnek

Bu kod parçası, kullanıcının varsayılan yazıcı adını ve bağlı olduğu bağlantı noktasını, yazıcının kullandığı biriktirici adı ile birlikte gösterir. Kod, "varsayılan yazıcınız, \\ winspool kullanarak \server\share ÜZERINDE HP LaserJet iiıp." ifadesini gösteren bir ileti kutusu gösterebilir.

[!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]

## <a name="cprintdialoggetdevmode"></a><a name="getdevmode"></a> CPrintDialog:: GetDevMode

Yapıyı alır `DEVMODE` .

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Cihaz başlatma ve yazdırma sürücüsünün ortamı hakkında bilgi içeren [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) veri yapısı. Windows SDK açıklanan Windows [GlobalUnlock](/windows/win32/api/winbase/nf-winbase-globalunlock) işleviyle bu yapı tarafından alınan belleğin kilidini açmanız gerekir.

### <a name="remarks"></a>Açıklamalar

Yazdırma aygıtı hakkında bilgi almak için [DoModal](#domodal) veya [GetDefaults](#getdefaults) çağrıldıktan sonra bu işlevi çağırın.

### <a name="example"></a>Örnek

  [CPrintDialog::P rintCollate](#printcollate)örneğine bakın.

## <a name="cprintdialoggetdrivername"></a><a name="getdrivername"></a> CPrintDialog:: Getsürücüadı

Şu anda seçili olan yazıcı sürücüsünün adını alır.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CString`Sistem tarafından tanımlanan sürücü adını belirtme.

### <a name="remarks"></a>Açıklamalar

Sistem tanımlı yazıcı cihazı sürücüsünün adını almak için [DoModal](#domodal) veya [GetDefaults](#getdefaults) çağrıldıktan sonra bu işlevi çağırın. `CString` `GetDriverName` `lpszDriverName` [CDC:: CreateDC](../../mfc/reference/cdc-class.md#createdc)çağrısında değeri olarak döndürülen nesneye yönelik bir işaretçi kullanın.

### <a name="example"></a>Örnek

  [CPrintDialog:: Getaygıtadı](#getdevicename)için örneğe bakın.

## <a name="cprintdialoggetfrompage"></a><a name="getfrompage"></a> CPrintDialog:: GetFromPage

Yazdırma aralığının başlangıç sayfasını alır.

```
int GetFromPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırılacak sayfa aralığındaki Başlangıç sayfası numarası.

### <a name="remarks"></a>Açıklamalar

`DoModal`Yazdırılacak sayfa aralığındaki Başlangıç sayfası numarasını almak için çağrıldıktan sonra bu işlevi çağırın.

### <a name="example"></a>Örnek

  [CPrintDialog:: m_pd](#m_pd)örneğine bakın.

## <a name="cprintdialoggetportname"></a><a name="getportname"></a> CPrintDialog:: GetPortName

Şu anda seçili olan yazıcı bağlantı noktasının adını alır.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili olan yazıcı bağlantı noktasının adı.

### <a name="remarks"></a>Açıklamalar

Şu anda seçili olan yazıcı bağlantı noktasının adını almak için [DoModal](#domodal) veya [GetDefaults](#getdefaults) çağrıldıktan sonra bu işlevi çağırın.

### <a name="example"></a>Örnek

  [CPrintDialog:: Getaygıtadı](#getdevicename)için örneğe bakın.

## <a name="cprintdialoggetprinterdc"></a><a name="getprinterdc"></a> CPrintDialog:: GetPrinterDC

Yazıcı cihaz bağlamına bir tanıtıcı alır.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa yazıcı cihaz bağlamına yönelik bir tanıtıcı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Oluşturucunun *bPrintSetupOnly* parametresi `CPrintDialog` yanlışsa (Yazdır iletişim kutusunun görüntülendiğini belirten), `GetPrinterDC` Yazıcı cihaz bağlamına bir tanıtıcı döndürür. Kullanmayı bitirdiğinizde cihaz bağlamını silmek için Windows [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) işlevini çağırmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]

## <a name="cprintdialoggettopage"></a><a name="gettopage"></a> CPrintDialog:: GetToPage

Yazdırma aralığının bitiş sayfasını alır.

```
int GetToPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırılacak sayfa aralığındaki bitiş sayfa numarası.

### <a name="remarks"></a>Açıklamalar

`DoModal`Yazdırılacak sayfa aralığındaki bitiş sayfası numarasını almak için çağrıldıktan sonra bu işlevi çağırın.

### <a name="example"></a>Örnek

  [CPrintDialog:: m_pd](#m_pd)örneğine bakın.

## <a name="cprintdialogm_pd"></a><a name="m_pd"></a> CPrintDialog:: m_pd

Üyeleri iletişim kutusu nesnesinin özelliklerini depolayan bir yapı.

```
PRINTDLG& m_pd;
```

### <a name="remarks"></a>Açıklamalar

Bir nesne oluşturduktan sonra `CPrintDialog` , `m_pd` [DoModal](#domodal) üye işlevini çağırmadan önce iletişim kutusunun çeşitli yönlerini ayarlamak için kullanabilirsiniz. Yapı hakkında daha fazla bilgi için `m_pd` Windows SDK [PrintDlg](/windows/win32/api/commdlg/ns-commdlg-printdlga) bölümüne bakın.

`m_pd`Veri üyesini doğrudan değiştirirseniz, varsayılan davranışı geçersiz kılarsınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]

## <a name="cprintdialogprintall"></a><a name="printall"></a> CPrintDialog::P Rinyüksekliğinde

Belgenin tüm sayfalarının yazdırılması gerekip gerekmediğini belirler.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgedeki tüm sayfalar yazdırıldıysa sıfır dışı. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`DoModal`Belgedeki tüm sayfaların yazdırılması gerekip gerekmediğini anlamak için çağrıldıktan sonra bu işlevi çağırın.

### <a name="example"></a>Örnek

  [CPrintDialog:: m_pd](#m_pd)örneğine bakın.

## <a name="cprintdialogprintcollate"></a><a name="printcollate"></a> CPrintDialog::P rintCollate

Harmanlanmış kopyaların istenip istenmediğini belirler.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı iletişim kutusunda Harmanla onay kutusunu seçerse sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`DoModal`Yazıcının belgenin tüm yazdırılan kopyalarını harmanlamaları gerekip gerekmediğini belirleme ' yı çağırdıktan sonra bu işlevi çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]

## <a name="cprintdialogprintrange"></a><a name="printrange"></a> CPrintDialog::P rintRange

Yalnızca belirli bir sayfa aralığının mi yazdırılacağını belirler.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yalnızca belgedeki bir sayfa aralığının yazdırılması halinde sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`DoModal`Belgedeki yalnızca bir sayfa aralığını yazdırıp yazdırmayacağını anlamak için çağrıldıktan sonra bu işlevi çağırın.

### <a name="example"></a>Örnek

  [CPrintDialog:: m_pd](#m_pd)örneğine bakın.

## <a name="cprintdialogprintselection"></a><a name="printselection"></a> CPrintDialog::P rintSelection

Yalnızca şu anda seçili olan öğelerin yazdırılması gerekip gerekmediğini belirler.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yalnızca seçili öğelerin yazdırılması halinde sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`DoModal`Yalnızca şu anda seçili olan öğelerin yazdırılması gerekip gerekmediğini anlamak için çağrıldıktan sonra bu işlevi çağırın.

### <a name="example"></a>Örnek

  [CPrintDialog:: m_pd](#m_pd)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo yapısı](../../mfc/reference/cprintinfo-structure.md)
