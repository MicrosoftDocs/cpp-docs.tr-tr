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
ms.openlocfilehash: ebef892e174525c0b907818c02b7d34b1b41f850
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916890"
---
# <a name="cprintdialogex-class"></a>CPrintDialogEx sınıfı

Windows yazdırma özelliği sayfası tarafından sunulan hizmetleri kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CPrintDialogEx : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|Bir `CPrintDialogEx` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPrintDialogEx:: CreatePrinterDC](#createprinterdc)|Yazdır iletişim kutusunu görüntülemeden bir yazıcı cihaz bağlamı oluşturur.|
|[CPrintDialogEx::DoModal](#domodal)|İletişim kutusunu görüntüler ve kullanıcının seçim yapmasına izin verir.|
|[CPrintDialogEx:: Getkopyaların](#getcopies)|İstenen kopya sayısını alır.|
|[CPrintDialogEx:: GetDefaults](#getdefaults)|Bir iletişim kutusu görüntülemeden cihaz varsayılanlarını alır.|
|[CPrintDialogEx:: Getaygıtadı](#getdevicename)|Şu anda seçili olan yazıcı cihazının adını alır.|
|[CPrintDialogEx:: GetDevMode](#getdevmode)|`DEVMODE` Yapıyı alır.|
|[CPrintDialogEx:: Getsürücüadı](#getdrivername)|Sistem tanımlı yazıcı aygıtı sürücüsünün adını alır.|
|[CPrintDialogEx:: GetPortName](#getportname)|Şu anda seçili olan yazıcı bağlantı noktasının adını alır.|
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|Yazıcı cihaz bağlamına bir tanıtıcı alır.|
|[CPrintDialogEx::P Rinyüksekliğinde](#printall)|Belgenin tüm sayfalarının yazdırılması gerekip gerekmediğini belirler.|
|[CPrintDialogEx::P rintCollate](#printcollate)|Harmanlanmış kopyaların istenip istenmediğini belirler.|
|[CPrintDialogEx::P rintCurrentPage](#printcurrentpage)|Belgenin geçerli sayfasının yazdırılması gerekip gerekmediğini belirler.|
|[CPrintDialogEx::P rintRange](#printrange)|Yalnızca belirli bir sayfa aralığının mi yazdırılacağını belirler.|
|[CPrintDialogEx::P rintSelection](#printselection)|Yalnızca şu anda seçili olan öğelerin yazdırılması gerekip gerekmediğini belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPrintDialogEx::m_pdex](#m_pdex)|Bir `CPrintDialogEx` nesneyi özelleştirmek için kullanılan bir yapı.|

## <a name="remarks"></a>Açıklamalar

Uygulamanız için yazdırma sürecinin birçok yönlerini işlemek üzere çerçevesini kullanabilirsiniz. Yazdırma görevlerini işlemek için Framework 'ü kullanma hakkında daha fazla bilgi için [yazdırma](../../mfc/printing.md)makalesine bakın.

Uygulamanızın, Framework 'ün katılımı olmadan yazdırmayı işlemesini istiyorsanız, "olduğu gibi" `CPrintDialogEx` sınıfını, sağlanmış Oluşturucu ile kullanabilir veya kendi iletişim `CPrintDialogEx` sınıfınızı kendi iletişim sınıfınızı türetebilir ve gereksinimlerinize uyacak şekilde bir Oluşturucu yazabilirsiniz. Her iki durumda da, bu iletişim kutuları sınıfından `CCommonDialog`TÜRETILDIKLERINDEN standart MFC iletişim kutuları gibi davranır.

Bir `CPrintDialogEx` nesnesi kullanmak için, önce `CPrintDialogEx` oluşturucuyu kullanarak nesnesini oluşturun. İletişim kutusu oluşturulduktan sonra, iletişim kutusu denetimlerinin değerlerini başlatmak için [m_pdex](#m_pdex) yapısındaki herhangi bir değeri ayarlayabilir veya değiştirebilirsiniz. Yapı PRINTDLGEX türündedir. [](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) `m_pdex` Bu yapı hakkında daha fazla bilgi için Windows SDK bakın.

`m_pdex` `GlobalFree` Ve üyeleri`hDevNames` için kendi tanıtıcılarınızı sağlamadıysanız, iletişim kutusuyla işiniz bittiğinde bu tutamaçlar için Windows işlevini çağırdığınızdan `hDevMode` emin olun.

İletişim kutusu denetimlerini başlattıktan sonra, iletişim kutusunu göstermek `DoModal` ve kullanıcının yazdırma seçeneklerini seçmesine izin vermek için üye işlevini çağırın. ' `DoModal` İ döndüğünde, kullanıcının Tamam, Uygula veya iptal düğmesini seçmiş olup olmadığını belirleyebilirsiniz.

Kullanıcı Tamam 'a basıldığında, Kullanıcı tarafından bilgi girişi `CPrintDialogEx`almak için üye işlevlerini kullanabilirsiniz.

`CPrintDialogEx::GetDefaults` Üye işlevi, geçerli yazıcı varsayılanlarını bir iletişim kutusu görüntülemeden almak için yararlıdır. Bu yöntem için Kullanıcı etkileşimi gerekmez.

İletişim kutusunun başlatılması sırasında hata `CommDlgExtendedError` oluşup oluşmadığını ve hata hakkında daha fazla bilgi için Windows işlevini kullanabilirsiniz. Bu işlev hakkında daha fazla bilgi için Windows SDK bakın.

Kullanma `CPrintDialogEx`hakkında daha fazla bilgi için bkz. [ortak iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md).

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

**Üstbilgi:** afxdlgs. h

##  <a name="cprintdialogex"></a>CPrintDialogEx::CPrintDialogEx

Windows yazdırma özellik sayfası oluşturur.

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*dwFlags*<br/>
Bit düzeyinde OR işleci kullanılarak birleştirilen iletişim kutusunun ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayrak. Örneğin, PD_ALLPAGES bayrağı varsayılan yazdırma aralığını belgenin tüm sayfalarına ayarlar. Bu bayraklar hakkında daha fazla bilgi için Windows SDK [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) yapısına bakın.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahip penceresine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yalnızca nesnesini oluşturur. İletişim kutusunu göstermek için üyeişlevinikullanın.`DoModal`

##  <a name="createprinterdc"></a>CPrintDialogEx:: CreatePrinterDC

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) ve [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) yapılarından bir yazıcı cihaz bağlamı (DC) oluşturur.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan yazıcı cihaz bağlamına yönelik tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Döndürülen DC, `hDC` [m_pdex](#m_pdex)üyesinde de depolanır.

Bu DC 'nin geçerli yazıcı DC olduğu varsayılır ve daha önce edinilen diğer yazıcı DC 'leri silinmelidir. Bu işlev çağrılabilir ve yazdırma iletişim kutusu görüntülenmeden, sonuçta elde edilen DC kullanılır.

##  <a name="domodal"></a>CPrintDialogEx::D oModal

Windows yazdırma özelliği sayfasını göstermek ve kullanıcının kopya sayısı, sayfa aralığı ve kopyaların harmanlanmasının gerekip gerekmediğini belirlemek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

INT_PTR dönüş değeri aslında HRESULT olur. Windows SDK içindeki [PrintDlgEx](/previous-versions/windows/desktop/legacy/ms646942\(v=vs.85\)) Içindeki dönüş değerleri bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

`m_pdex` Yapının üyelerini ayarlayarak çeşitli yazdırma iletişim kutusu seçeneklerini başlatmak isterseniz, bunu çağırmadan `DoModal`önce, ancak iletişim kutusu nesnesi oluşturulduktan sonra yapmanız gerekir.

Öğesini çağırdıktan `DoModal`sonra, Kullanıcı tarafından iletişim kutusuna ayarları veya bilgi girişini almak için diğer üye işlevlerini çağırabilirsiniz.

Çağrılırken `DoModal`pd_returndc bayrağı kullanılırsa, `hDC` [m_pdex](#m_pdex)üyesine bir yazıcı DC 'si döndürülür. Bu DC, çağıran `CPrintDialogEx`tarafından bir [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) çağrısıyla serbest bırakılmalıdır.

##  <a name="getcopies"></a>CPrintDialogEx:: Getkopyaların

İstenen kopya sayısını almak için `DoModal` çağrıldıktan sonra bu işlevi çağırın.

```
int GetCopies() const;
```

### <a name="return-value"></a>Dönüş Değeri

İstenen kopya sayısı.

##  <a name="getdefaults"></a>CPrintDialogEx:: GetDefaults

Bir iletişim kutusu görüntülemeden varsayılan yazıcının cihaz varsayılanlarını almak için bu işlevi çağırın.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE, aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) ve [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) yapılarından bir yazıcı cihaz bağlamı (DC) oluşturur.

`GetDefaults`Yazdırma özelliği sayfasını görüntülemez. Bunun `hDevNames` yerine, [](#m_pdex) m_pdex `hDevMode` üyelerini, sistem varsayılan yazıcısı için başlatılan [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) ve [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) yapılarına işleyecek şekilde ayarlar. Her ikisi de `hDevNames` null veya `GetDefaults` başarısız olmalıdır.`hDevMode`

Pd_returndc bayrağı ayarlandıysa, bu işlev yalnızca `hDevNames` çağırana geri dönmez ve `hDevMode` (ve `m_pdex.hDevMode`içinde `m_pdex.hDevNames` bulunur), Ayrıca, içinde `m_pdex.hDC`bir yazıcı DC 'si döndürür. Bu, çağıranın yazıcı DC 'sini silme ve `CPrintDialogEx` nesne ile işiniz bittiğinde Tanıtıcılarda Windows [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree) işlevini çağırma sorumluluğundadır.

##  <a name="getdevicename"></a>CPrintDialogEx:: Getaygıtadı

Şu anda seçili olan yazıcının adını almak için [DoModal](#domodal) çağrıldıktan sonra veya varsayılan yazıcının adını almak Için [GetDefaults](#getdefaults) çağrıldıktan sonra bu işlevi çağırın.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili olan yazıcının adı.

### <a name="remarks"></a>Açıklamalar

`CString` [CDC:: CreateDC](../../mfc/reference/cdc-class.md#createdc)çağrısında değeri `GetDeviceName` `lpszDeviceName` olarak döndürülen nesneye yönelik bir işaretçi kullanın.

##  <a name="getdevmode"></a>CPrintDialogEx:: GetDevMode

Yazdırma aygıtı hakkında bilgi almak için [DoModal](#domodal) veya [GetDefaults](#getdefaults) çağrıldıktan sonra bu işlevi çağırın.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Cihaz başlatma ve yazdırma sürücüsünün ortamı hakkında bilgi içeren [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) veri yapısı. Windows SDK açıklanan Windows [GlobalUnlock](/windows/desktop/api/winbase/nf-winbase-globalunlock) işleviyle bu yapı tarafından alınan belleğin kilidini açmanız gerekir.

##  <a name="getdrivername"></a>CPrintDialogEx:: Getsürücüadı

Sistem tanımlı yazıcı cihazı sürücüsünün adını almak için [DoModal](#domodal) veya [GetDefaults](#getdefaults) çağrıldıktan sonra bu işlevi çağırın.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sistem tarafından tanımlanan sürücü adını belirtme.`CString`

### <a name="remarks"></a>Açıklamalar

`CString` [CDC:: CreateDC](../../mfc/reference/cdc-class.md#createdc)çağrısında *lpszDriverName* değeri `GetDriverName` olarak döndürülen nesneye yönelik bir işaretçi kullanın.

##  <a name="getportname"></a>CPrintDialogEx:: GetPortName

Şu anda seçili olan yazıcı bağlantı noktasının adını almak için [DoModal](#domodal) veya [GetDefaults](#getdefaults) çağrıldıktan sonra bu işlevi çağırın.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili olan yazıcı bağlantı noktasının adı.

##  <a name="getprinterdc"></a>CPrintDialogEx:: GetPrinterDC

Yazıcı cihaz bağlamına bir tanıtıcı döndürür.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazıcı cihaz bağlamı için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Kullanmayı bitirdiğinizde cihaz bağlamını silmek için Windows [DeleteDC](/windows/desktop/api/wingdi/nf-wingdi-deletedc) işlevini çağırmanız gerekir.

##  <a name="m_pdex"></a>CPrintDialogEx::m_pdex

Üyeleri iletişim kutusu nesnesinin özelliklerini depolayan bir PRINTDLGEX yapısı.

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>Açıklamalar

Bir `CPrintDialogEx` nesne oluşturduktan sonra, [DoModal](#domodal) üye `m_pdex` işlevini çağırmadan önce iletişim kutusunun çeşitli yönlerini ayarlamak için kullanabilirsiniz. `m_pdex` Yapı hakkında daha fazla bilgi için Windows SDK [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) bakın.

`m_pdex` Veri üyesini doğrudan değiştirirseniz, varsayılan davranışı geçersiz kılarsınız.

##  <a name="printall"></a>CPrintDialogEx::P Rinyüksekliğinde

Belgedeki tüm sayfaların yazdırılması gerekip `DoModal` gerekmediğini anlamak için çağrıldıktan sonra bu işlevi çağırın.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgedeki tüm sayfalar yazdırıldıysa TRUE; Aksi halde yanlış.

##  <a name="printcollate"></a>CPrintDialogEx::P rintCollate

Yazıcının belgenin tüm yazdırılan kopyalarını `DoModal` harmanlamaları gerekip gerekmediğini belirleme ' yı çağırdıktan sonra bu işlevi çağırın.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı iletişim kutusunda Harmanla onay kutusunu seçerse TRUE; Aksi halde yanlış.

##  <a name="printcurrentpage"></a>CPrintDialogEx::P rintCurrentPage

Geçerli sayfanın belgede yazdırılması gerekip `DoModal` gerekmediğini anlamak için bu işlevi çağırın.

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdır iletişim kutusunda **geçerli sayfayı yazdır** seçiliyse true; Aksi halde yanlış.

##  <a name="printrange"></a>CPrintDialogEx::P rintRange

Belgedeki yalnızca bir sayfa aralığını `DoModal` yazdırıp yazdırmayacağını anlamak için çağrıldıktan sonra bu işlevi çağırın.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yalnızca belgedeki bir sayfa aralığının yazdırılması gerekiyorsa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Belirtilen sayfa aralıkları [m_pdex](#m_pdex) ' dan `nPageRanges`belirlenebilir (Windows SDK, `nMaxPageRanges`, ve `lpPageRanges` [PRINTDLGEX](/windows/desktop/api/commdlg/ns-commdlg-tagpdexa) yapısında bkz.).

##  <a name="printselection"></a>CPrintDialogEx::P rintSelection

Yalnızca şu anda seçili olan `DoModal` öğelerin yazdırılması gerekip gerekmediğini anlamak için çağrıldıktan sonra bu işlevi çağırın.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yalnızca seçilen öğeler yazdırılabiliyorsa TRUE; Aksi halde yanlış.

## <a name="see-also"></a>Ayrıca bkz.

[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo Yapısı](../../mfc/reference/cprintinfo-structure.md)
