---
title: CPrintDialogEx Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CPrintDialogEx
- AFXDLGS/CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CreatePrinterDC
- AFXDLGS/CPrintDialogEx::DoModal
- AFXDLGS/CPrintDialogEx::GetCopies
- AFXDLGS/CPrintDialogEx::GetDefaults
- AFXDLGS/CPrintDialogEx::GetDeviceName
- AFXDLGS/CPrintDialogEx::GetDevMode
- AFXDLGS/CPrintDialogEx::GetDriverName
- AFXDLGS/CPrintDialogEx::GetPortName
- AFXDLGS/CPrintDialogEx::GetPrinterDC
- AFXDLGS/CPrintDialogEx::PrintAll
- AFXDLGS/CPrintDialogEx::PrintCollate
- AFXDLGS/CPrintDialogEx::PrintCurrentPage
- AFXDLGS/CPrintDialogEx::PrintRange
- AFXDLGS/CPrintDialogEx::PrintSelection
- AFXDLGS/CPrintDialogEx::m_pdex
helpviewer_keywords:
- CPrintDialogEx [MFC], CPrintDialogEx
- CPrintDialogEx [MFC], CreatePrinterDC
- CPrintDialogEx [MFC], DoModal
- CPrintDialogEx [MFC], GetCopies
- CPrintDialogEx [MFC], GetDefaults
- CPrintDialogEx [MFC], GetDeviceName
- CPrintDialogEx [MFC], GetDevMode
- CPrintDialogEx [MFC], GetDriverName
- CPrintDialogEx [MFC], GetPortName
- CPrintDialogEx [MFC], GetPrinterDC
- CPrintDialogEx [MFC], PrintAll
- CPrintDialogEx [MFC], PrintCollate
- CPrintDialogEx [MFC], PrintCurrentPage
- CPrintDialogEx [MFC], PrintRange
- CPrintDialogEx [MFC], PrintSelection
- CPrintDialogEx [MFC], m_pdex
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
ms.openlocfilehash: 52e992cf021a592198daeddf0a4321fcea487f72
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364038"
---
# <a name="cprintdialogex-class"></a>CPrintDialogEx Sınıfı

Windows Print özellik sayfası tarafından sağlanan hizmetleri kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CPrintDialogEx : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|Bir `CPrintDialogEx` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|Yazdır iletişim kutusunu görüntülemeden bir yazıcı aygıtı bağlamı oluşturur.|
|[CPrintDialogEx::DoModal](#domodal)|İletişim kutusunu görüntüler ve kullanıcının seçim yapmasına izin verir.|
|[CPrintDialogEx::Kopya ları](#getcopies)|İstenilen kopya sayısını alır.|
|[CPrintDialogEx::GetDefaults](#getdefaults)|İletişim kutusu görüntülemeden aygıt varsayılanlarını alır.|
|[CPrintDialogEx::GetDeviceName](#getdevicename)|Seçili yazıcı aygıtının adını alır.|
|[CPrintDialogEx::GetDevMode](#getdevmode)|Yapıyı `DEVMODE` alır.|
|[CPrintDialogEx::GetDriverName](#getdrivername)|Sistem tanımlı yazıcı aygıtı sürücüsünün adını alır.|
|[CPrintDialogEx::GetPortName](#getportname)|Şu anda seçili yazıcı bağlantı noktasının adını alır.|
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|Yazıcı aygıtı bağlamına bir tanıtıcı alır.|
|[CPrintDialogEx::PrintAll](#printall)|Belgenin tüm sayfalarını yazdırıp yazdırmayacağını belirler.|
|[CPrintDialogEx::PrintCollate](#printcollate)|Harmanlanmış kopyaların istenip istenmediğini belirler.|
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|Belgenin geçerli sayfasının yazdırılıp yazdırılmayacağını belirler.|
|[CPrintDialogEx::PrintRange](#printrange)|Yalnızca belirli bir sayfa aralığının yazdırılıp yazdırılmayacağını belirler.|
|[CPrintDialogEx::PrintSelection](#printselection)|Yalnızca seçili öğeleri yazdırıp yazdırmayacağını belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CPrintDialogEx::m_pdex](#m_pdex)|Nesneyi özelleştirmek için `CPrintDialogEx` kullanılan bir yapı.|

## <a name="remarks"></a>Açıklamalar

Uygulamanız için yazdırma işleminin birçok yönünü işlemek için çerçeveye güvenebilirsiniz. Yazdırma görevlerini işlemek için çerçeveyi kullanma hakkında daha fazla bilgi için [Yazdırma](../../mfc/printing.md)makalesine bakın.

Uygulamanızın çerçevenin katılımı olmadan yazdırmayı işlemesini istiyorsanız, `CPrintDialogEx` sağlanan oluşturucuyla "olduğu gibi" sınıfı kullanabilir veya kendi iletişim `CPrintDialogEx` sınıfınızı türetebilir ve ihtiyaçlarınıza uygun bir oluşturucu yazabilirsiniz. Her iki durumda da, bu iletişim kutuları standart MFC iletişim kutuları `CCommonDialog`gibi, çünkü sınıftan türetilmiştir.

Bir `CPrintDialogEx` nesneyi kullanmak için önce `CPrintDialogEx` oluşturucuyu kullanarak nesneyi oluşturun. İletişim kutusu oluşturulduktan sonra, iletişim kutusunun denetimlerinin değerlerini açmak için [m_pdex](#m_pdex) yapısındaki tüm değerleri ayarlayabilir veya değiştirebilirsiniz. Yapısı `m_pdex` [printdlgex](/windows/win32/api/commdlg/ns-commdlg-printdlgexw)türündendir. Bu yapı hakkında daha fazla bilgi için Windows SDK'ya bakın.

`m_pdex` Üyeler `hDevMode` ve `hDevNames` üyeler için kendi tutamaçlarınızı sağlamazsanız, iletişim kutusuyla işiniz bittiğinde bu tutamaçların Windows işlevini `GlobalFree` aradığınızdan emin olun.

İletişim kutusu denetimlerini açtıktan sonra, iletişim kutusunu görüntülemek için `DoModal` üye işlevi arayın ve kullanıcının yazdırma seçeneklerini seçmesine izin verin. Döndüklerinde, `DoModal` kullanıcının Tamam, Uygula veya İptal düğmesini seçip seçmediğini belirleyebilirsiniz.

Kullanıcı Tamam tuşuna basıldığında, kullanıcı tarafından bilgi girişi almak için 'üye işlevlerini kullanabilirsiniz. `CPrintDialogEx`

Üye `CPrintDialogEx::GetDefaults` işlev, bir iletişim kutusu görüntülemeden geçerli yazıcı varsayılanlarını almak için yararlıdır. Bu yöntem kullanıcı etkileşimi gerektirmez.

İletişim kutusunun `CommDlgExtendedError` başlatılması sırasında bir hata oluşup oluşmadığını belirlemek ve hata hakkında daha fazla bilgi edinmek için Windows işlevini kullanabilirsiniz. Bu işlev hakkında daha fazla bilgi için Windows SDK'ya bakın.

Kullanma `CPrintDialogEx`hakkında daha fazla bilgi için [Ortak İletişim Sınıfları'na](../../mfc/common-dialog-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

`IObjectWithSite`

`IPrintDialogCallback`

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialogEx`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs.h

## <a name="cprintdialogexcprintdialogex"></a><a name="cprintdialogex"></a>CPrintDialogEx::CPrintDialogEx

Windows Print özellik sayfası oluşturuyor.

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*Dwflags*<br/>
Bitwise OR işleci kullanarak birlikte iletişim kutusunun ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayrak. Örneğin, PD_ALLPAGES bayrağı varsayılan yazdırma aralığını belgenin tüm sayfalarına ayarlar. Bu bayraklar hakkında daha fazla bilgi için Windows SDK'daki [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) yapısına bakın.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahip penceresiiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev yalnızca nesneyi oluşturuyor. İletişim `DoModal` kutusunu görüntülemek için üye işlevini kullanın.

## <a name="cprintdialogexcreateprinterdc"></a><a name="createprinterdc"></a>CPrintDialogEx::CreatePrinterDC

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) ve [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) yapılarından bir yazıcı aygıtı bağlamı (DC) oluşturur.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan yazıcı aygıtı bağlamını ele alın.

### <a name="remarks"></a>Açıklamalar

Döndürülen DC de [m_pdex](#m_pdex) `hDC` üyesi saklanır.

Bu DC geçerli yazıcı DC olarak kabul edilir ve daha önce elde edilen diğer yazıcı DC'leri silinmelidir. Bu işlev çağrılabilir ve ortaya çıkan DC, Yazdır iletişim kutusunu hiç görüntülemeden kullanılır.

## <a name="cprintdialogexdomodal"></a><a name="domodal"></a>CPrintDialogEx::DoModal

Windows Print özellik sayfasını görüntülemek ve kullanıcının kopya sayısı, sayfa aralığı ve kopyaların harmanlanıp harmanlanmaması gibi çeşitli yazdırma seçeneklerini seçmesine izin vermek için bu işlevi arayın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

INT_PTR iade değeri aslında bir HRESULT'dir. Windows SDK'daki [PrintDlgEx'teki](/previous-versions/windows/desktop/legacy/ms646942\(v=vs.85\)) İade Değerleri bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Yapının üyelerini ayarlayarak çeşitli yazdırma iletişim seçeneklerinin `m_pdex` başlatılmasını istiyorsanız, bunu `DoModal`çağırmadan önce, ancak iletişim nesnesi oluşturulduktan sonra yapmalısınız.

Aradıktan `DoModal`sonra, kullanıcı tarafından iletişim kutusuna ayarları veya bilgi girişini almak için diğer üye işlevleri arayabilirsiniz.

Arama `DoModal`yaparken PD_RETURNDC bayrağı kullanılırsa, `hDC` [m_pdex](#m_pdex)üyesi bir yazıcı DC döndürülür. Bu DC arayan tarafından [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) bir çağrı `CPrintDialogEx`ile serbest bırakılmalıdır.

## <a name="cprintdialogexgetcopies"></a><a name="getcopies"></a>CPrintDialogEx::Kopya ları

İstenilen `DoModal` kopya sayısını almak için aradıktan sonra bu işlevi arayın.

```
int GetCopies() const;
```

### <a name="return-value"></a>Dönüş Değeri

İstenen kopya sayısı.

## <a name="cprintdialogexgetdefaults"></a><a name="getdefaults"></a>CPrintDialogEx::GetDefaults

Bir iletişim kutusu görüntülemeden varsayılan yazıcının varsayılan aygıt varsayılanlarını almak için bu işlevi arayın.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Dönüş Değeri

DOĞRU eğer başarılı, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) ve [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) yapılarından bir yazıcı aygıtı bağlamı (DC) oluşturur.

`GetDefaults`Yazdır özellik sayfasını görüntülemez. Bunun yerine, `hDevNames` sistem `hDevMode` varsayılan yazıcıiçin başlatılan [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) ve [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) yapılarına işlemek için [m_pdex](#m_pdex) ve üyelerini ayarlar. Her `hDevNames` `hDevMode` ikisi de ve `GetDefaults` NULL olmalıdır, ya da başarısız.

PD_RETURNDC bayrağı ayarlanırsa, bu işlev `hDevNames` yalnızca `hDevMode` ve `m_pdex.hDevNames` (bulunan `m_pdex.hDevMode`ve) arayana geri dönmekle kalmıyor, aynı zamanda bir yazıcı DC'sini de döndürecek. `m_pdex.hDC` Yazıcı DC'yi silmek ve `CPrintDialogEx` nesneyle işi bittiğinde tutamaçtaki Windows [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree) işlevini aramak arayanın sorumluluğundadır.

## <a name="cprintdialogexgetdevicename"></a><a name="getdevicename"></a>CPrintDialogEx::GetDeviceName

Şu anda seçili yazıcının adını almak için [DoModal'ı](#domodal) aradıktan sonra veya varsayılan yazıcının adını almak için [GetDefaults'ı](#getdefaults) aradıktan sonra bu işlevi arayın.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili yazıcının adı.

### <a name="remarks"></a>Açıklamalar

CDC'ye yapılan `CString` bir `GetDeviceName` çağrıda değeri `lpszDeviceName` olarak döndürülen nesneye işaretçi [kullanın::CreateDC](../../mfc/reference/cdc-class.md#createdc).

## <a name="cprintdialogexgetdevmode"></a><a name="getdevmode"></a>CPrintDialogEx::GetDevMode

Yazdırma aygıtı hakkında bilgi almak için [DoModal](#domodal) veya [GetDefaults'ı](#getdefaults) aradıktan sonra bu işlevi arayın.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aygıt başlatma ve yazdırma sürücüsünün ortamı hakkında bilgi içeren [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) veri yapısı. Windows SDK'da açıklanan Windows [GlobalUnlock](/windows/win32/api/winbase/nf-winbase-globalunlock) işlevi ile bu yapı tarafından alınan bellek kilidini açmanız gerekir.

## <a name="cprintdialogexgetdrivername"></a><a name="getdrivername"></a>CPrintDialogEx::GetDriverName

Sistem tanımlı yazıcı aygıtı sürücüsünün adını almak için [DoModal](#domodal) veya [GetDefaults'ı](#getdefaults) aradıktan sonra bu işlevi arayın.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sistem `CString` tanımlı sürücü adını belirten bir.

### <a name="remarks"></a>Açıklamalar

CDC'ye `CString` yapılan bir `GetDriverName` çağrıda *lpszDriverName* değeri olarak döndürülen nesneye işaretçi [kullanın:CreateDC](../../mfc/reference/cdc-class.md#createdc).

## <a name="cprintdialogexgetportname"></a><a name="getportname"></a>CPrintDialogEx::GetPortName

Şu anda seçili yazıcı bağlantı noktasının adını almak için [DoModal](#domodal) veya [GetDefaults'ı](#getdefaults) aradıktan sonra bu işlevi arayın.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili yazıcı bağlantı noktasının adı.

## <a name="cprintdialogexgetprinterdc"></a><a name="getprinterdc"></a>CPrintDialogEx::GetPrinterDC

Bir tanıtıcıyı yazıcı aygıtı bağlamına döndürür.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazıcı aygıtı bağlamına bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Aygıtı kullanmayı bitirdiğinizde aygıt bağlamını silmek için Windows [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) işlevini aramalısınız.

## <a name="cprintdialogexm_pdex"></a><a name="m_pdex"></a>CPrintDialogEx::m_pdex

Üyeleri iletişim nesnesinin özelliklerini depolayan bir PRINTDLGEX yapısı.

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>Açıklamalar

Bir `CPrintDialogEx` nesne yaptıktan sonra, `m_pdex` [DoModal](#domodal) üye işlevini aramadan önce iletişim kutusunun çeşitli yönlerini ayarlamak için kullanabilirsiniz. `m_pdex` Yapı hakkında daha fazla bilgi için Windows SDK'daki [PRINTDLGEX'e](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) bakın.

Veri üyesini `m_pdex` doğrudan değiştirirseniz, varsayılan davranışı geçersiz kılarsınız.

## <a name="cprintdialogexprintall"></a><a name="printall"></a>CPrintDialogEx::PrintAll

Belgedeki tüm `DoModal` sayfaların yazdırılıp yazdırılmayacağını belirlemek için aradıktan sonra bu işlevi arayın.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgedeki tüm sayfaların yazdırılması gerekiyorsa DOĞRU; aksi takdirde YANLIŞ.

## <a name="cprintdialogexprintcollate"></a><a name="printcollate"></a>CPrintDialogEx::PrintCollate

Yazıcının belgenin `DoModal` yazdırılan tüm kopyalarını harmanlaması gerekip gerekmediğini belirlemek için aradıktan sonra bu işlevi arayın.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı iletişim kutusundaki harmanlama onay kutusunu seçerse TRUE; aksi takdirde YANLIŞ.

## <a name="cprintdialogexprintcurrentpage"></a><a name="printcurrentpage"></a>CPrintDialogEx::PrintCurrentPage

Belgedeki geçerli `DoModal` sayfayı yazdırıp yazdırmayacağını belirlemek için aradıktan sonra bu işlevi arayın.

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırma iletişim kutusunda **Yazdırma Geçerli Sayfası** seçilirse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cprintdialogexprintrange"></a><a name="printrange"></a>CPrintDialogEx::PrintRange

Belgede yalnızca bir `DoModal` sayfa aralığıyazdırılıp yazdırılmayacağını belirlemek için aradıktan sonra bu işlevi arayın.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgedeki yalnızca bir sayfa aralığı yazdırılacaksa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Belirtilen sayfa aralıkları [m_pdex](#m_pdex) `nPageRanges` `nMaxPageRanges`'den ve `lpPageRanges` Windows SDK'daki [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) yapısından) belirlenebilir.

## <a name="cprintdialogexprintselection"></a><a name="printselection"></a>CPrintDialogEx::PrintSelection

Yalnızca seçili `DoModal` öğeleri yazdırıp yazdırmayacağımı belirlemek için çağrıda bulunduktan sonra bu işlevi arayın.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yalnızca seçili öğeler yazdırılacaksa TRUE; aksi takdirde YANLIŞ.

## <a name="see-also"></a>Ayrıca bkz.

[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CprintInfo Yapısı](../../mfc/reference/cprintinfo-structure.md)
