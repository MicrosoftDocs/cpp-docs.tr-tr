---
title: CPrintDialog Sınıfı
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
ms.openlocfilehash: 6490e5488c5ab3b808a02e3608b75541e4063d8f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364061"
---
# <a name="cprintdialog-class"></a>CPrintDialog Sınıfı

Yazdırmak için Windows ortak iletişim kutusu tarafından sağlanan hizmetleri kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CPrintDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CPrintDialog::CPrintDialog](#cprintdialog)|Bir `CPrintDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|Yazdır iletişim kutusunu görüntülemeden bir yazıcı aygıtı bağlamı oluşturur.|
|[CPrintDialog::DoModal](#domodal)|İletişim kutusunu görüntüler ve kullanıcının seçim yapmasına izin verir.|
|[CPrintDialog::Kopya ları](#getcopies)|İstenilen kopya sayısını alır.|
|[CPrintDialog::GetDefaults](#getdefaults)|İletişim kutusu görüntülemeden aygıt varsayılanlarını alır.|
|[CPrintDialog::GetDeviceName](#getdevicename)|Seçili yazıcı aygıtının adını alır.|
|[CPrintDialog::GetDevMode](#getdevmode)|Yapıyı `DEVMODE` alır.|
|[CPrintDialog::GetDriverName](#getdrivername)|Seçili yazıcı sürücüsünün adını alır.|
|[CPrintDialog::GetFromPage](#getfrompage)|Yazdırma aralığının başlangıç sayfasını alır.|
|[CPrintDialog::GetPortName](#getportname)|Şu anda seçili yazıcı bağlantı noktasının adını alır.|
|[CPrintDialog::GetPrinterDC](#getprinterdc)|Yazıcı aygıtı bağlamına bir tanıtıcı alır.|
|[CPrintDialog::GetToPage](#gettopage)|Yazdırma aralığının bitiş sayfasını alır.|
|[CPrintDialog::PrintAll](#printall)|Belgenin tüm sayfalarını yazdırıp yazdırmayacağını belirler.|
|[CPrintDialog::PrintCollate](#printcollate)|Harmanlanmış kopyaların istenip istenmediğini belirler.|
|[CPrintDialog::PrintRange](#printrange)|Yalnızca belirli bir sayfa aralığının yazdırılıp yazdırılmayacağını belirler.|
|[CPrintDialog::PrintSelection](#printselection)|Yalnızca seçili öğeleri yazdırıp yazdırmayacağını belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CPrintDialog::m_pd](#m_pd)|Nesneyi özelleştirmek için `CPrintDialog` kullanılan bir yapı.|

## <a name="remarks"></a>Açıklamalar

Yaygın yazdırma iletişim kutuları, Yazdırma ve Yazdırma Kurulum iletişim kutularını Windows standartlarına uygun bir şekilde uygulamanın kolay bir yolunu sağlar.

> [!NOTE]
> Sınıf, `CPrintDialogEx` Windows Print özellik sayfası tarafından sağlanan hizmetleri kapsüller. Daha fazla bilgi için [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) genel bakış bakın.

`CPrintDialog`''nin işlevselliği, hem yazdırma kurulumu hem de sayfa kurulumu için ortak bir iletişim kutusu sağlamak üzere tasarlanmış olan [CPageSetupDialog'un](../../mfc/reference/cpagesetupdialog-class.md)yerini alabilen bir işlevdir.

Uygulamanız için yazdırma işleminin birçok yönünü işlemek için çerçeveye güvenebilirsiniz. Bu durumda, çerçeve yazdırmak için Windows ortak iletişim kutusunu otomatik olarak görüntüler. Ayrıca, uygulamanız için çerçeve tutamacı yazdırmayı da sağlayabilir, ancak ortak Yazdırma iletişim kutusunu kendi yazdırma iletişim kutunuzla geçersiz kılabilirsiniz. Yazdırma görevlerini işlemek için çerçeveyi kullanma hakkında daha fazla bilgi için [Yazdırma](../../mfc/printing.md)makalesine bakın.

Uygulamanızın çerçevenin katılımı olmadan yazdırmayı işlemesini istiyorsanız, `CPrintDialog` sağlanan oluşturucuyla "olduğu gibi" sınıfı kullanabilir veya kendi iletişim `CPrintDialog` sınıfınızı türetebilir ve ihtiyaçlarınıza uygun bir oluşturucu yazabilirsiniz. Her iki durumda da, bu iletişim kutuları standart MFC iletişim kutuları `CCommonDialog`gibi, çünkü sınıftan türetilmiştir.

Bir `CPrintDialog` nesneyi kullanmak için önce `CPrintDialog` oluşturucuyu kullanarak nesneyi oluşturun. İletişim kutusu oluşturulduktan sonra, iletişim kutusunun denetimlerinin değerlerini açmak için [m_pd](#m_pd) yapısındaki tüm değerleri ayarlayabilir veya değiştirebilirsiniz. Yapısı `m_pd` [printdlg](/windows/win32/api/commdlg/ns-commdlg-printdlga)türündedir. Bu yapı hakkında daha fazla bilgi için Windows SDK'ya bakın.

`m_pd` Üyeler `hDevMode` ve `hDevNames` üyeler için kendi tutamaçlarınızı sağlamazsanız, iletişim kutusuyla işiniz bittiğinde bu tutamaçların Windows işlevini `GlobalFree` aradığınızdan emin olun. Çerçevenin Sağladığı Yazdırma Kurulumu uygulamasını `CWinApp::OnFilePrintSetup`kullanırken, bu tutamaçları serbest yapmanız gerekmez. Tutamaçları tarafından korunur `CWinApp` ve `CWinApp`'yıkıcı serbest bırakılır. Bu tutamaçları tek başına kullanırken `CPrintDialog` serbest bırakmak gerekir.

İletişim kutusu denetimlerini açtıktan sonra, iletişim kutusunu görüntülemek için `DoModal` üye işlevi arayın ve kullanıcının yazdırma seçeneklerini seçmesine izin verin. `DoModal`kullanıcıok (IDOK) veya İptal (IDCANCEL) düğmesini seçip seçmediğini döndürür.

`DoModal` IDOK'u döndürürse, kullanıcı tarafından bilgi girdisini almak için `CPrintDialog`'üye işlevlerden birini kullanabilirsiniz.

Üye `CPrintDialog::GetDefaults` işlev, bir iletişim kutusu görüntülemeden geçerli yazıcı varsayılanlarını almak için yararlıdır. Bu üye işlev kullanıcı etkileşimi gerektirmez.

İletişim kutusunun `CommDlgExtendedError` başlatılması sırasında bir hata oluşup oluşmadığını belirlemek ve hata hakkında daha fazla bilgi edinmek için Windows işlevini kullanabilirsiniz. Bu işlev hakkında daha fazla bilgi için Windows SDK'ya bakın.

`CPrintDialog`COMMDLG'ye dayanır. DLL dosyası, Windows sürümleri 3.1 ve sonraki sürümlerle birlikte iletin.

İletişim kutusunu özelleştirmek için, bir sınıf `CPrintDialog`türetin, özel bir iletişim şablonu sağlayın ve genişletilmiş denetimlerden gelen bildirim iletilerini işlemek için bir ileti eşlemi ekleyin. İşlenmemiş iletiler taban sınıfa aktarılmalıdır. Kanca işlevini özelleştirmek gerekli değildir.

İletişim kutusunun Yazdır veya Yazdırma Kurulumu olup olmadığına bağlı olarak aynı iletiyi farklı şekilde işlemek için, her iletişim kutusu için bir sınıf türetmeniz gerekir. Yazdırma Kurulumu düğmesi bir `AttachOnSetup` Yazdır iletişim kutusu içinde seçildiğinde yeni bir iletişim kutusu oluşturulmasını işleyen Windows işlevini de geçersiz kılmanız gerekir.

Kullanma `CPrintDialog`hakkında daha fazla bilgi için [Ortak İletişim Sınıfları'na](../../mfc/common-dialog-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs.h

## <a name="cprintdialogcprintdialog"></a><a name="cprintdialog"></a>CPrintDialog::CPrintDialog

Windows Print veya Print Setup iletişim nesnesi oluşturuyor.

```
CPrintDialog(
    BOOL bPrintSetupOnly,
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*bPrintSetupOnly*<br/>
Standart Windows Print iletişim kutusunun veya Yazdırma Kurulumu iletişim kutusunun görüntülenip görüntülenmediğini belirtir. Standart Windows Yazdırma Kurulumu iletişim kutusunu görüntülemek için bu parametreyi TRUE olarak ayarlayın. Windows Print iletişim kutusunu görüntülemek için FALSE olarak ayarlayın. *bPrintSetupOnly* FALSE ise, Yazdır Kurulumu seçeneği düğmesi yazdırma iletişim kutusunda yine de görüntülenir.

*Dwflags*<br/>
Bitwise OR işleci kullanarak birlikte iletişim kutusunun ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayrak. Örneğin, PD_ALLPAGES bayrağı varsayılan yazdırma aralığını belgenin tüm sayfalarına ayarlar. Bu bayraklar hakkında daha fazla bilgi için Windows SDK'daki [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga) yapısına bakın.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahip penceresiiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev yalnızca nesneyi oluşturuyor. İletişim `DoModal` kutusunu görüntülemek için üye işlevini kullanın.

*BPrintSetupOnly* ile oluşturucuyu FALSE olarak ayarladığınızda, PD_RETURNDC bayrağının otomatik olarak kullanıldığını unutmayın. Aradıktan `DoModal` `GetDefaults`sonra `GetPrinterDC`, veya , bir `m_pd.hDC`yazıcı DC döndürülür. Bu DC arayan tarafından [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) bir çağrı `CPrintDialog`ile serbest bırakılmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]

## <a name="cprintdialogcreateprinterdc"></a><a name="createprinterdc"></a>CPrintDialog::CreatePrinterDC

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) ve [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) yapılarından bir yazıcı aygıtı bağlamı (DC) oluşturur.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan yazıcı aygıtı bağlamını ele alın.

### <a name="remarks"></a>Açıklamalar

Bu DC geçerli yazıcı DC olarak kabul edilir ve daha önce elde edilen diğer yazıcı DC'leri kullanıcı tarafından silinmelidir. Bu işlev çağrılabilir ve ortaya çıkan DC, Yazdır iletişim kutusunu hiç görüntülemeden kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]

## <a name="cprintdialogdomodal"></a><a name="domodal"></a>CPrintDialog::DoModal

Windows ortak yazdırma iletişim kutusunu görüntüler ve kullanıcının kopya sayısı, sayfa aralığı ve kopyaların harmanlanıp harmanlanmaması gibi çeşitli yazdırma seçeneklerini seçmesine olanak tanır.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İDOK veya IDCANCEL. IDCANCEL döndürülürse, bir hata oluşup oluşmadığını belirlemek için Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini arayın.

IDOK ve IDCANCEL, kullanıcının Ok veya İptal düğmesini seçip seçmediğini gösteren sabitlerdir.

### <a name="remarks"></a>Açıklamalar

Yapının üyelerini ayarlayarak çeşitli yazdırma iletişim seçeneklerinin `m_pd` başlatılmasını istiyorsanız, bunu `DoModal`çağırmadan önce, ancak iletişim nesnesi oluşturulduktan sonra yapmalısınız.

Aradıktan `DoModal`sonra, kullanıcı tarafından iletişim kutusuna ayarları veya bilgi girişini almak için diğer üye işlevleri arayabilirsiniz.

*BPrintSetupOnly* ile oluşturucuyu FALSE olarak ayarladığınızda, PD_RETURNDC bayrağının otomatik olarak kullanıldığını unutmayın. Aradıktan `DoModal` `GetDefaults`sonra `GetPrinterDC`, veya , bir `m_pd.hDC`yazıcı DC döndürülür. Bu DC arayan tarafından [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) bir çağrı `CPrintDialog`ile serbest bırakılmalıdır.

### <a name="example"></a>Örnek

  [CPrintDialog örneğine bakın:CreatePrinterDC](#createprinterdc).

## <a name="cprintdialoggetcopies"></a><a name="getcopies"></a>CPrintDialog::Kopya ları

İstenilen kopya sayısını alır.

```
int GetCopies() const;
```

### <a name="return-value"></a>Dönüş Değeri

İstenen kopya sayısı.

### <a name="remarks"></a>Açıklamalar

İstenilen `DoModal` kopya sayısını almak için aradıktan sonra bu işlevi arayın.

### <a name="example"></a>Örnek

  CPrintDialog için örneğe [bakın::PrintCollate](#printcollate).

## <a name="cprintdialoggetdefaults"></a><a name="getdefaults"></a>CPrintDialog::GetDefaults

İletişim kutusu görüntülemeden varsayılan yazıcının aygıt varsayılanlarını alır.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Alınan değerler yapıya `m_pd` yerleştirilir.

Bazı durumlarda, bu işleviçin bir çağrı *bPrintSetupOnly* FALSE olarak ayarlanmış `CPrintDialog` ile [oluşturucu](#cprintdialog) çağırır. Bu gibi durumlarda, bir `hDevNames` `hDevMode` yazıcı DC ve `m_pd` (veri üyesi bulunan iki tutamaçları) otomatik olarak ayrılır.

Için oluşturucu `CPrintDialog` *bPrintSetupOnly* FALSE olarak ayarlanmış olarak çağrıldıysa, `hDevNames` bu `hDevMode` işlev `m_pd.hDevNames` sadece `m_pd.hDevMode`geri dönmek ve bulunan ve ) `m_pd.hDC`arayan, ama aynı zamanda bir yazıcı DC döndürecek . Yazıcı DC'yi silmek ve `CPrintDialog` nesneyle işi bittiğinde tutamaçtaki Windows [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree) işlevini aramak arayanın sorumluluğundadır.

### <a name="example"></a>Örnek

Bu kod parçası varsayılan yazıcının aygıt bağlamını alır ve yazıcının çözünürlüğünü inç başına nokta olarak kullanıcıya bildirir. (Yazıcının yeteneklerinin bu özelliği genellikle DPI olarak adlandırılır.)

[!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]

## <a name="cprintdialoggetdevicename"></a><a name="getdevicename"></a>CPrintDialog::GetDeviceName

Seçili yazıcı aygıtının adını alır.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili yazıcının adı.

### <a name="remarks"></a>Açıklamalar

Şu anda seçili yazıcının adını almak için [DoModal'ı](#domodal) aradıktan sonra veya varsayılan yazıcının geçerli aygıt varsayılanlarını almak için [GetDefaults'ı](#getdefaults) aradıktan sonra bu işlevi arayın. CDC'ye yapılan `CString` bir `GetDeviceName` çağrıda değeri `lpszDeviceName` olarak döndürülen nesneye işaretçi [kullanın::CreateDC](../../mfc/reference/cdc-class.md#createdc).

### <a name="example"></a>Örnek

Bu kod parçası, kullanıcının varsayılan yazıcı adını ve bağlı olduğu bağlantı noktasını, yazıcının kullandığı makane adı ile birlikte gösterir. Kod, "Varsayılan yazıcınız \server\share kullanarak WINS HAVUZU'nda \\HP LaserJet IIIP'dir" yazan bir ileti kutusu gösterebilir, örneğin.

[!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]

## <a name="cprintdialoggetdevmode"></a><a name="getdevmode"></a>CPrintDialog::GetDevMode

Yapıyı `DEVMODE` alır.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aygıt başlatma ve yazdırma sürücüsünün ortamı hakkında bilgi içeren [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) veri yapısı. Windows SDK'da açıklanan Windows [GlobalUnlock](/windows/win32/api/winbase/nf-winbase-globalunlock) işlevi ile bu yapı tarafından alınan bellek kilidini açmanız gerekir.

### <a name="remarks"></a>Açıklamalar

Yazdırma aygıtı hakkında bilgi almak için [DoModal](#domodal) veya [GetDefaults'ı](#getdefaults) aradıktan sonra bu işlevi arayın.

### <a name="example"></a>Örnek

  CPrintDialog için örneğe [bakın::PrintCollate](#printcollate).

## <a name="cprintdialoggetdrivername"></a><a name="getdrivername"></a>CPrintDialog::GetDriverName

Seçili yazıcı sürücüsünün adını alır.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sistem `CString` tanımlı sürücü adını belirten bir.

### <a name="remarks"></a>Açıklamalar

Sistem tanımlı yazıcı aygıtı sürücüsünün adını almak için [DoModal](#domodal) veya [GetDefaults'ı](#getdefaults) aradıktan sonra bu işlevi arayın. CDC'ye yapılan `CString` bir `GetDriverName` çağrıda değeri `lpszDriverName` olarak döndürülen nesneye işaretçi [kullanın::CreateDC](../../mfc/reference/cdc-class.md#createdc).

### <a name="example"></a>Örnek

  [CPrintDialog örneğine bakın:GetDeviceName](#getdevicename).

## <a name="cprintdialoggetfrompage"></a><a name="getfrompage"></a>CPrintDialog::GetFromPage

Yazdırma aralığının başlangıç sayfasını alır.

```
int GetFromPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırılacak sayfa aralığındaki başlangıç sayfa numarası.

### <a name="remarks"></a>Açıklamalar

Yazdırılacak sayfa `DoModal` aralığındaki başlangıç sayfa numarasını almak için aradıktan sonra bu işlevi arayın.

### <a name="example"></a>Örnek

  [CPrintDialog örneğine bakın:m_pd.](#m_pd)

## <a name="cprintdialoggetportname"></a><a name="getportname"></a>CPrintDialog::GetPortName

Şu anda seçili yazıcı bağlantı noktasının adını alır.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili yazıcı bağlantı noktasının adı.

### <a name="remarks"></a>Açıklamalar

Şu anda seçili yazıcı bağlantı noktasının adını almak için [DoModal](#domodal) veya [GetDefaults'ı](#getdefaults) aradıktan sonra bu işlevi arayın.

### <a name="example"></a>Örnek

  [CPrintDialog örneğine bakın:GetDeviceName](#getdevicename).

## <a name="cprintdialoggetprinterdc"></a><a name="getprinterdc"></a>CPrintDialog::GetPrinterDC

Yazıcı aygıtı bağlamına bir tanıtıcı alır.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa yazıcı aygıtı bağlamına bir tanıtıcı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Oluşturucunun *bPrintSetupOnly* parametresi FALSE ise (Yazdırma iletişim kutusunun görüntülendiğini `GetPrinterDC` gösterir), ardından yazıcı aygıtı bağlamına bir tutamacı döndürür. `CPrintDialog` Aygıtı kullanmayı bitirdiğinizde aygıt bağlamını silmek için Windows [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) işlevini aramalısınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]

## <a name="cprintdialoggettopage"></a><a name="gettopage"></a>CPrintDialog::GetToPage

Yazdırma aralığının bitiş sayfasını alır.

```
int GetToPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırılacak sayfa aralığındaki bitiş sayfa numarası.

### <a name="remarks"></a>Açıklamalar

Yazdırılacak sayfa `DoModal` aralığındaki bitiş sayfa numarasını almak için aradıktan sonra bu işlevi arayın.

### <a name="example"></a>Örnek

  [CPrintDialog örneğine bakın:m_pd.](#m_pd)

## <a name="cprintdialogm_pd"></a><a name="m_pd"></a>CPrintDialog::m_pd

Üyeleri iletişim nesnesinin özelliklerini depolayan bir yapı.

```
PRINTDLG& m_pd;
```

### <a name="remarks"></a>Açıklamalar

Bir `CPrintDialog` nesne yaptıktan sonra, `m_pd` [DoModal](#domodal) üye işlevini aramadan önce iletişim kutusunun çeşitli yönlerini ayarlamak için kullanabilirsiniz. `m_pd` Yapı hakkında daha fazla bilgi için Windows [SDK'daki PRINTDLG'ye](/windows/win32/api/commdlg/ns-commdlg-printdlga) bakın.

Veri üyesini `m_pd` doğrudan değiştirirseniz, varsayılan davranışı geçersiz kılarsınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]

## <a name="cprintdialogprintall"></a><a name="printall"></a>CPrintDialog::PrintAll

Belgenin tüm sayfalarını yazdırıp yazdırmayacağını belirler.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgedeki tüm sayfaların yazdırılması gerekiyorsa sıfıra değil; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belgedeki tüm `DoModal` sayfaların yazdırılıp yazdırılmayacağını belirlemek için aradıktan sonra bu işlevi arayın.

### <a name="example"></a>Örnek

  [CPrintDialog örneğine bakın:m_pd.](#m_pd)

## <a name="cprintdialogprintcollate"></a><a name="printcollate"></a>CPrintDialog::PrintCollate

Harmanlanmış kopyaların istenip istenmediğini belirler.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı iletişim kutusundaki harmanlama onay kutusunu seçerse sıfıra doğru değil; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yazıcının belgenin `DoModal` yazdırılan tüm kopyalarını harmanlaması gerekip gerekmediğini belirlemek için aradıktan sonra bu işlevi arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]

## <a name="cprintdialogprintrange"></a><a name="printrange"></a>CPrintDialog::PrintRange

Yalnızca belirli bir sayfa aralığının yazdırılıp yazdırılmayacağını belirler.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgedeki yalnızca bir sayfa aralığı yazdırılacaksa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belgede yalnızca bir `DoModal` sayfa aralığıyazdırılıp yazdırılmayacağını belirlemek için aradıktan sonra bu işlevi arayın.

### <a name="example"></a>Örnek

  [CPrintDialog örneğine bakın:m_pd.](#m_pd)

## <a name="cprintdialogprintselection"></a><a name="printselection"></a>CPrintDialog::PrintSelection

Yalnızca seçili öğeleri yazdırıp yazdırmayacağını belirler.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yalnızca seçili öğeler yazdırılacaksa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yalnızca seçili `DoModal` öğeleri yazdırıp yazdırmayacağımı belirlemek için çağrıda bulunduktan sonra bu işlevi arayın.

### <a name="example"></a>Örnek

  [CPrintDialog örneğine bakın:m_pd.](#m_pd)

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CprintInfo Yapısı](../../mfc/reference/cprintinfo-structure.md)
