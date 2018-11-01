---
title: CPrintDialogEx sınıfı
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
ms.openlocfilehash: 79d696f89ca7474220559abbf5464f32b6e684c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543331"
---
# <a name="cprintdialogex-class"></a>CPrintDialogEx sınıfı

Windows Print özellik sayfası tarafından sağlanan hizmetleri kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CPrintDialogEx : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|Oluşturur bir `CPrintDialogEx` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|Yazdır iletişim kutusu görüntülenmeden yazıcı cihaz bağlamı oluşturur.|
|[CPrintDialogEx::DoModal](#domodal)|İletişim kutusunu görüntüler ve kullanıcının seçim yapmanızı sağlar.|
|[CPrintDialogEx::GetCopies](#getcopies)|İstenen kopya sayısını alır.|
|[CPrintDialogEx::GetDefaults](#getdefaults)|Cihaz Varsayılanları iletişim kutusu görüntülenmeden alır.|
|[CPrintDialogEx::GetDeviceName](#getdevicename)|Şu anda seçili yazıcı cihazın adını alır.|
|[CPrintDialogEx::GetDevMode](#getdevmode)|Alır `DEVMODE` yapısı.|
|[CPrintDialogEx::GetDriverName](#getdrivername)|Sistem tarafından tanımlanan yazıcı aygıt sürücüsünün adını alır.|
|[CPrintDialogEx::GetPortName](#getportname)|Şu anda seçili yazıcı bağlantı noktasını adını alır.|
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|Yazıcı cihaz bağlamı için bir tanıtıcı alır.|
|[CPrintDialogEx::PrintAll](#printall)|Belgenin tüm sayfalarının yazdırılıp yazdırılmayacağını belirler.|
|[CPrintDialogEx::PrintCollate](#printcollate)|Kopya istenen Harmanlanmış olup olmadığını belirler.|
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|Belgenin geçerli sayfayı yazdır belirler.|
|[CPrintDialogEx::PrintRange](#printrange)|Sayfa için belirtilen bir aralıktaki yazdırılıp yazdırılmayacağını belirler.|
|[CPrintDialogEx::PrintSelection](#printselection)|Yalnızca şu anda seçtiğiniz öğelerin yazdırılıp yazdırılmayacağını belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPrintDialogEx::m_pdex](#m_pdex)|Özelleştirmek için kullanılan bir yapının bir `CPrintDialogEx` nesne.|

## <a name="remarks"></a>Açıklamalar

Yazdırma işlemi uygulamanız için birçok yönden işlemek için Framework güvenebilirsiniz. Yazdırma görevleri işlemek için çerçeve kullanma hakkında daha fazla bilgi için bkz [yazdırma](../../mfc/printing.md).

Uygulamanızın framework'ün katılımı olmadan yazdırmak işlemesini istiyorsanız, kullanabileceğiniz `CPrintDialogEx` sağlanan oluşturucuyla "olduğu gibi" sınıf ya da kendi iletişim sınıftan türetilip `CPrintDialogEx` ve ihtiyaçlarınıza uyacak şekilde bir oluşturucu yazma. Sınıfından türetildiği her iki durumda da, bu iletişim kutularından standart MFC iletişim kutuları gibi davranır `CCommonDialog`.

Kullanılacak bir `CPrintDialogEx` nesne, ilk nesnesini kullanarak oluşturun `CPrintDialogEx` Oluşturucusu. İletişim kutusu oluşturulmuş bir kez ayarlayabilir veya herhangi bir değer değiştirme [m_pdex](#m_pdex) Yapısı iletişim kutusunun denetimleri değerlerini başlatılamadı. `m_pdex` Yapısıdır türünü [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa). Bu yapı hakkında daha fazla bilgi için Windows SDK'sı bakın.

Kendi işleyicileri sağlamazsanız `m_pdex` için `hDevMode` ve `hDevNames` üyeleri, Windows işlevi çağırma mutlaka `GlobalFree` iletişim kutusu ile işiniz bittiğinde bu tanıtıcıları için.

İletişim kutusu denetimleri başlatılıyor sonra çağrı `DoModal` iletişim kutusunu görüntülemek ve yazdırma seçeneklerini seçmesini sağlamak için üye işlevi. Zaman `DoModal` döndürür, kullanıcı Tamam, Uygula veya iptal düğmesi seçili olup olmadığını belirleyebilirsiniz.

Kullanıcı Tamam basıldıysa kullanabileceğiniz `CPrintDialogEx`ait üye işlevleri tarafından kullanıcı giriş bilgileri alınamıyor.

`CPrintDialogEx::GetDefaults` Üye işlevi, geçerli bir yazıcı Varsayılanları iletişim kutusu görüntülenmeden almak için kullanışlıdır. Bu yöntem, kullanıcı etkileşimi gerektirir.

Windows kullanabileceğiniz `CommDlgExtendedError` işlevi bir hata iletişim kutusunun başlatma sırasında oluşup oluşmadığını belirleyin ve hata hakkında daha fazla bilgi edinin. Bu işlev hakkında daha fazla bilgi için Windows SDK'sı bakın.

Kullanma hakkında daha fazla bilgi için `CPrintDialogEx`, bkz: [ortak iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`IObjectWithSite`

`IPrintDialogCallback`

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialogEx`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdlgs.h

##  <a name="cprintdialogex"></a>  CPrintDialogEx::CPrintDialogEx

Bir Windows Print özellik sayfası oluşturur.

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*CertOpenStore*<br/>
Bit düzeyinde OR işleci kullanılarak birleştirilen iletişim kutusunun ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayraklar. Örneğin, PD_ALLPAGES bayrağı, tüm belge sayfaları varsayılan yazdırma aralığı ayarlar. Bkz: [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) yapısı içinde bu bayraklar hakkında daha fazla bilgi için Windows SDK'sı.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahip penceresine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yalnızca bir nesne oluşturur. Kullanım `DoModal` iletişim kutusunu görüntülemek için üye işlevi.

##  <a name="createprinterdc"></a>  CPrintDialogEx::CreatePrinterDC

Bir yazıcı cihaz bağlamı (DC) oluşturur [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) ve [DEVNAMES](../../mfc/reference/devnames-structure.md) yapıları.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan yazıcı cihaz bağlamına işleyin.

### <a name="remarks"></a>Açıklamalar

Döndürülen etki alanı denetleyicisi de depolanan `hDC` üyesi [m_pdex](#m_pdex).

Bu DC'nin geçerli yazıcı DC olarak kabul edilir ve daha önce edindiğiniz diğer yazıcı DC'leri silinmesi gerekir. Bu işlev çağrılabilir ve Yazdır iletişim kutusu görüntülenmeden elde edilen DC kullanılır.

##  <a name="domodal"></a>  CPrintDialogEx::DoModal

Windows yazdırma özellik sayfasını görüntüleyin ve kopyalar, sayfa aralığı sayısı gibi çeşitli yazdırma seçeneklerini seçmesini sağlamak için bu işlevi çağırın ve kopya Harmanlanmış.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

INT_PTR dönüş değeri gerçekten HRESULT:. Dönüş değerleri bölümüne bakın [PrintDlgEx](https://msdn.microsoft.com/library/windows/desktop/ms646942) Windows SDK.

### <a name="remarks"></a>Açıklamalar

Çeşitli Yazdır iletişim kutusu seçenekleri üyeleri ayarlayarak başlatmak istiyorsanız `m_pdex` yapısı, bunu çağırmadan önce yapmalısınız `DoModal`, ancak iletişim nesnesi oluşturulur.

Arama sonra `DoModal`, diğer üye işlevleri, kullanıcı giriş bilgileri ve Ayarları iletişim kutusuna alınacak çağırabilirsiniz.

Çağrılırken PD_RETURNDC bayrağı kullanılırsa `DoModal`, yazıcı DC içinde döndürülen `hDC` üyesi [m_pdex](#m_pdex). Bu DC çağrısı ile serbest bırakılmalıdır [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) çağıran tarafından `CPrintDialogEx`.

##  <a name="getcopies"></a>  CPrintDialogEx::GetCopies

Çağırdıktan sonra bu işlevi çağırın `DoModal` istenen kopya sayısı alınamıyor.

```
int GetCopies() const;
```

### <a name="return-value"></a>Dönüş Değeri

İstenen kopya sayısı.

##  <a name="getdefaults"></a>  CPrintDialogEx::GetDefaults

Varsayılan yazıcı cihaz varsayılan bir iletişim kutusu görüntülenmeden almak için bu işlevi çağırın.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı, aksi takdirde FALSE ise TRUE.

### <a name="remarks"></a>Açıklamalar

Bir yazıcı cihaz bağlamı (DC) oluşturur [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) ve [DEVNAMES](../../mfc/reference/devnames-structure.md) yapıları.

`GetDefaults` Print özellik sayfası görüntülenmez. Bunun yerine, ayarlar `hDevNames` ve `hDevMode` üyeleri [m_pdex](#m_pdex) tanıtıcıları için [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) ve [DEVNAMES](../../mfc/reference/devnames-structure.md) için başlatılan yapıları Sistem varsayılan yazıcı. Her ikisi de `hDevNames` ve `hDevMode` NULL olmalı veya `GetDefaults` başarısız olur.

PD_RETURNDC bayrağı ayarlandıysa, bu işlev değil yalnızca döndürür `hDevNames` ve `hDevMode` (bulunan `m_pdex.hDevNames` ve `m_pdex.hDevMode`) çağırana, ancak ayrıca yazıcıya DC döndürür `m_pdex.hDC`. DC yazıcı silip Windows çağrı çağıranın sorumluluğundadır [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree) işlevi ile işiniz bittiğinde tutamaçları üzerinde `CPrintDialogEx` nesne.

##  <a name="getdevicename"></a>  CPrintDialogEx::GetDeviceName

Çağırdıktan sonra bu işlevi çağırın [DoModal](#domodal) şu anda seçili yazıcının veya arama sonra adı almak için [GetDefaults](#getdefaults) varsayılan yazıcının adını almak için.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili yazıcının adı.

### <a name="remarks"></a>Açıklamalar

Bir işaretçi kullanın `CString` tarafından döndürülen nesne `GetDeviceName` değeri olarak `lpszDeviceName` çağrıda [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

##  <a name="getdevmode"></a>  CPrintDialogEx::GetDevMode

Çağırdıktan sonra bu işlevi çağırın [DoModal](#domodal) veya [GetDefaults](#getdefaults) yazdırma cihaz hakkında bilgi almak için.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

[DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) cihaz başlatma ve yazdırma sürücüsü ortamı hakkında bilgi içeren veri yapısı. Windows ile bu yapı tarafından gerçekleştirilecek bellek kilidini açmanız gerekir [GlobalUnlock](/windows/desktop/api/winbase/nf-winbase-globalunlock) Windows SDK'da açıklanan işlevi.

##  <a name="getdrivername"></a>  CPrintDialogEx::GetDriverName

Çağırdıktan sonra bu işlevi çağırın [DoModal](#domodal) veya [GetDefaults](#getdefaults) sistem tarafından tanımlanan yazıcı aygıt sürücüsünün adını alamadı.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` sistem tarafından tanımlanan sürücü adı belirtme.

### <a name="remarks"></a>Açıklamalar

Bir işaretçi kullanın `CString` tarafından döndürülen nesne `GetDriverName` değeri olarak *lpszDriverName* çağrıda [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

##  <a name="getportname"></a>  CPrintDialogEx::GetPortName

Çağırdıktan sonra bu işlevi çağırın [DoModal](#domodal) veya [GetDefaults](#getdefaults) seçili yazıcı bağlantı noktasını adını almak için.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili yazıcı bağlantı noktasını adı.

##  <a name="getprinterdc"></a>  CPrintDialogEx::GetPrinterDC

Yazıcı cihaz bağlamı için bir tanıtıcı döndürür.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazıcı cihaz bağlamı için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Windows çağırmalıdır [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) işlevi işiniz bittiğinde, cihaz bağlam silmek için onu kullanarak.

##  <a name="m_pdex"></a>  CPrintDialogEx::m_pdex

Üyeleri iletişim nesnesinin özelliklerini depolamak bir PRINTDLGEX yapısı.

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>Açıklamalar

Oluşturma sonrasında bir `CPrintDialogEx` nesne kullanabileceğiniz `m_pdex` çeşitli yönlerini çağırmadan önce iletişim kutusunda ayarlanacak [DoModal](#domodal) üye işlevi. Daha fazla bilgi için `m_pdex` yapısı için bkz: [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) Windows SDK.

Değiştirirseniz `m_pdex` veri üyesi doğrudan, hiçbir varsayılan davranışı geçersiz kılar.

##  <a name="printall"></a>  CPrintDialogEx::PrintAll

Çağırdıktan sonra bu işlevi çağırın `DoModal` belgedeki tüm sayfalarını yazdırma belirlemek için.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgedeki tüm sayfalar yazdırılır ise TRUE; Aksi durumda FALSE.

##  <a name="printcollate"></a>  CPrintDialogEx::PrintCollate

Çağırdıktan sonra bu işlevi çağırın `DoModal` yazıcı belge yazdırılan tüm kopyalarını collate olup olmadığını belirlemek için.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı iletişim kutusundaki collate onay kutusunu seçer TRUE; Aksi durumda FALSE.

##  <a name="printcurrentpage"></a>  CPrintDialogEx::PrintCurrentPage

Çağırdıktan sonra bu işlevi çağırın `DoModal` belgedeki geçerli sayfayı yazdır belirlemek için.

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE ise **geçerli sayfayı Yazdır** olduğu yazdırma iletişim kutusunda seçili; Aksi takdirde FALSE.

##  <a name="printrange"></a>  CPrintDialogEx::PrintRange

Çağırdıktan sonra bu işlevi çağırın `DoModal` yalnızca bir dizi belgedeki sayfa yazdırma belirlemek için.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir belgedeki sayfa aralığı yalnızca yazdırılması için TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Belirtilen sayfa aralıklarını gelen belirlenebilir [m_pdex](#m_pdex) (bkz `nPageRanges`, `nMaxPageRanges`, ve `lpPageRanges` içinde [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) Windows SDK'sındaki yapısı).

##  <a name="printselection"></a>  CPrintDialogEx::PrintSelection

Çağırdıktan sonra bu işlevi çağırın `DoModal` yalnızca şu anda seçtiğiniz öğelerin yazdırma belirlemek için.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili öğeleri yazdırılması, yalnızca TRUE; Aksi durumda FALSE.

## <a name="see-also"></a>Ayrıca Bkz.

[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo Yapısı](../../mfc/reference/cprintinfo-structure.md)
