---
description: 'Daha fazla bilgi edinin: CPrintDialogEx Class'
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
ms.openlocfilehash: 2f0d124422efa641c3ace833a5970b364a5cbc48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301470"
---
# <a name="cprintdialogex-class"></a>CPrintDialogEx sınıfı

Windows yazdırma özelliği sayfası tarafından sunulan hizmetleri kapsüller.

## <a name="syntax"></a>Syntax

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
|[CPrintDialogEx::D oModal](#domodal)|İletişim kutusunu görüntüler ve kullanıcının seçim yapmasına izin verir.|
|[CPrintDialogEx:: Getkopyaların](#getcopies)|İstenen kopya sayısını alır.|
|[CPrintDialogEx:: GetDefaults](#getdefaults)|Bir iletişim kutusu görüntülemeden cihaz varsayılanlarını alır.|
|[CPrintDialogEx:: Getaygıtadı](#getdevicename)|Şu anda seçili olan yazıcı cihazının adını alır.|
|[CPrintDialogEx:: GetDevMode](#getdevmode)|Yapıyı alır `DEVMODE` .|
|[CPrintDialogEx:: Getsürücüadı](#getdrivername)|Sistem tanımlı yazıcı aygıtı sürücüsünün adını alır.|
|[CPrintDialogEx:: GetPortName](#getportname)|Şu anda seçili olan yazıcı bağlantı noktasının adını alır.|
|[CPrintDialogEx:: GetPrinterDC](#getprinterdc)|Yazıcı cihaz bağlamına bir tanıtıcı alır.|
|[CPrintDialogEx::P Rinyüksekliğinde](#printall)|Belgenin tüm sayfalarının yazdırılması gerekip gerekmediğini belirler.|
|[CPrintDialogEx::P rintCollate](#printcollate)|Harmanlanmış kopyaların istenip istenmediğini belirler.|
|[CPrintDialogEx::P rintCurrentPage](#printcurrentpage)|Belgenin geçerli sayfasının yazdırılması gerekip gerekmediğini belirler.|
|[CPrintDialogEx::P rintRange](#printrange)|Yalnızca belirli bir sayfa aralığının mi yazdırılacağını belirler.|
|[CPrintDialogEx::P rintSelection](#printselection)|Yalnızca şu anda seçili olan öğelerin yazdırılması gerekip gerekmediğini belirler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPrintDialogEx:: m_pdex](#m_pdex)|Bir nesneyi özelleştirmek için kullanılan bir yapı `CPrintDialogEx` .|

## <a name="remarks"></a>Açıklamalar

Uygulamanız için yazdırma sürecinin birçok yönlerini işlemek üzere çerçevesini kullanabilirsiniz. Yazdırma görevlerini işlemek için Framework 'ü kullanma hakkında daha fazla bilgi için [yazdırma](../../mfc/printing.md)makalesine bakın.

Uygulamanızın, Framework 'ün katılımı olmadan yazdırmayı işlemesini istiyorsanız, `CPrintDialogEx` "olduğu gibi" sınıfını, sağlanmış Oluşturucu ile kullanabilir veya kendi iletişim sınıfınızı kendi iletişim sınıfınızı türetebilir `CPrintDialogEx` ve gereksinimlerinize uyacak şekilde bir Oluşturucu yazabilirsiniz. Her iki durumda da, bu iletişim kutuları sınıfından türetildiklerinden standart MFC iletişim kutuları gibi davranır `CCommonDialog` .

Bir nesnesi kullanmak için `CPrintDialogEx` , önce oluşturucuyu kullanarak nesnesini oluşturun `CPrintDialogEx` . İletişim kutusu oluşturulduktan sonra, iletişim kutusu denetimlerinin değerlerini başlatmak için [m_pdex](#m_pdex) yapısındaki herhangi bir değeri ayarlayabilir veya değiştirebilirsiniz. `m_pdex`Yapı [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw)türündedir. Bu yapı hakkında daha fazla bilgi için Windows SDK bakın.

Ve üyeleri için kendi tanıtıcılarınızı sağlamadıysanız `m_pdex` `hDevMode` `hDevNames` , `GlobalFree` iletişim kutusuyla işiniz bittiğinde bu tutamaçlar için Windows işlevini çağırdığınızdan emin olun.

İletişim kutusu denetimlerini başlattıktan sonra, `DoModal` iletişim kutusunu göstermek ve kullanıcının yazdırma seçeneklerini seçmesine izin vermek için üye işlevini çağırın. `DoModal`' İ döndüğünde, kullanıcının Tamam, Uygula veya iptal düğmesini seçmiş olup olmadığını belirleyebilirsiniz.

Kullanıcı Tamam 'a basıldığında, `CPrintDialogEx` Kullanıcı tarafından bilgi girişi almak için üye işlevlerini kullanabilirsiniz.

`CPrintDialogEx::GetDefaults`Üye işlevi, geçerli yazıcı varsayılanlarını bir iletişim kutusu görüntülemeden almak için yararlıdır. Bu yöntem için Kullanıcı etkileşimi gerekmez.

`CommDlgExtendedError`İletişim kutusunun başlatılması sırasında hata oluşup oluşmadığını ve hata hakkında daha fazla bilgi Için Windows işlevini kullanabilirsiniz. Bu işlev hakkında daha fazla bilgi için Windows SDK bakın.

Kullanma hakkında daha fazla bilgi için `CPrintDialogEx` bkz. [ortak Iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`IObjectWithSite`

`IPrintDialogCallback`

[Ccommoniletişim kutusu](../../mfc/reference/ccommondialog-class.md)

`CPrintDialogEx`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs. h

## <a name="cprintdialogexcprintdialogex"></a><a name="cprintdialogex"></a> CPrintDialogEx::CPrintDialogEx

Windows yazdırma özellik sayfası oluşturur.

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*dwFlags*<br/>
Bit düzeyinde OR işleci kullanılarak birleştirilen iletişim kutusunun ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayrak. Örneğin, PD_ALLPAGES bayrağı varsayılan yazdırma aralığını belgenin tüm sayfalarına ayarlar. Bu bayraklar hakkında daha fazla bilgi için Windows SDK [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) yapısına bakın.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahip penceresine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yalnızca nesnesini oluşturur. `DoModal`İletişim kutusunu göstermek için üye işlevini kullanın.

## <a name="cprintdialogexcreateprinterdc"></a><a name="createprinterdc"></a> CPrintDialogEx:: CreatePrinterDC

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) ve [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) yapılarından bir yazıcı cihaz bağlamı (DC) oluşturur.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan yazıcı cihaz bağlamına yönelik tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Döndürülen DC, `hDC` [m_pdex](#m_pdex)üyesinde de depolanır.

Bu DC 'nin geçerli yazıcı DC olduğu varsayılır ve daha önce edinilen diğer yazıcı DC 'leri silinmelidir. Bu işlev çağrılabilir ve yazdırma iletişim kutusu görüntülenmeden, sonuçta elde edilen DC kullanılır.

## <a name="cprintdialogexdomodal"></a><a name="domodal"></a> CPrintDialogEx::D oModal

Windows yazdırma özelliği sayfasını göstermek ve kullanıcının kopya sayısı, sayfa aralığı ve kopyaların harmanlanmasının gerekip gerekmediğini belirlemek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

INT_PTR dönüş değeri aslında HRESULT 'dir. Windows SDK içindeki [PrintDlgEx](/previous-versions/windows/desktop/legacy/ms646942\(v=vs.85\)) Içindeki dönüş değerleri bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Yapının üyelerini ayarlayarak çeşitli yazdırma iletişim kutusu seçeneklerini başlatmak isterseniz, bunu `m_pdex` çağırmadan önce `DoModal` , ancak iletişim kutusu nesnesi oluşturulduktan sonra yapmanız gerekir.

Öğesini çağırdıktan sonra `DoModal` , Kullanıcı tarafından iletişim kutusuna ayarları veya bilgi girişini almak için diğer üye işlevlerini çağırabilirsiniz.

' I çağırırken PD_RETURNDC bayrağı kullanılırsa `DoModal` , bir yazıcı DC 'si, `hDC` [m_pdex](#m_pdex)üyesine döndürülür. Bu DC, çağıran tarafından bir [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) çağrısıyla serbest bırakılmalıdır `CPrintDialogEx` .

## <a name="cprintdialogexgetcopies"></a><a name="getcopies"></a> CPrintDialogEx:: Getkopyaların

`DoModal`İstenen kopya sayısını almak için çağrıldıktan sonra bu işlevi çağırın.

```
int GetCopies() const;
```

### <a name="return-value"></a>Dönüş Değeri

İstenen kopya sayısı.

## <a name="cprintdialogexgetdefaults"></a><a name="getdefaults"></a> CPrintDialogEx:: GetDefaults

Bir iletişim kutusu görüntülemeden varsayılan yazıcının cihaz varsayılanlarını almak için bu işlevi çağırın.

```
BOOL GetDefaults();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE, aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) ve [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) yapılarından bir yazıcı cihaz bağlamı (DC) oluşturur.

`GetDefaults` Yazdırma özelliği sayfasını görüntülemez. Bunun yerine, `hDevNames` ve `hDevMode` [m_pdex](#m_pdex) üyelerini, sistem varsayılan yazıcısı Için başlatılan [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) ve [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) yapılarına işleyecek şekilde ayarlar. Her ikisi de `hDevNames` `hDevMode` null veya başarısız olmalıdır `GetDefaults` .

PD_RETURNDC bayrağı ayarlandıysa, bu işlev yalnızca `hDevNames` `hDevMode` çağırana döndürmez ve (ve içinde yer alır `m_pdex.hDevNames` `m_pdex.hDevMode` ), Ayrıca, içinde bir yazıcı DC 'si döndürür `m_pdex.hDC` . Bu, çağıranın yazıcı DC 'sini silme ve nesne ile işiniz bittiğinde Tanıtıcılarda Windows [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree) işlevini çağırma sorumluluğundadır `CPrintDialogEx` .

## <a name="cprintdialogexgetdevicename"></a><a name="getdevicename"></a> CPrintDialogEx:: Getaygıtadı

Şu anda seçili olan yazıcının adını almak için [DoModal](#domodal) çağrıldıktan sonra veya varsayılan yazıcının adını almak Için [GetDefaults](#getdefaults) çağrıldıktan sonra bu işlevi çağırın.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili olan yazıcının adı.

### <a name="remarks"></a>Açıklamalar

`CString` `GetDeviceName` `lpszDeviceName` [CDC:: CreateDC](../../mfc/reference/cdc-class.md#createdc)çağrısında değeri olarak döndürülen nesneye yönelik bir işaretçi kullanın.

## <a name="cprintdialogexgetdevmode"></a><a name="getdevmode"></a> CPrintDialogEx:: GetDevMode

Yazdırma aygıtı hakkında bilgi almak için [DoModal](#domodal) veya [GetDefaults](#getdefaults) çağrıldıktan sonra bu işlevi çağırın.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Cihaz başlatma ve yazdırma sürücüsünün ortamı hakkında bilgi içeren [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) veri yapısı. Windows SDK açıklanan Windows [GlobalUnlock](/windows/win32/api/winbase/nf-winbase-globalunlock) işleviyle bu yapı tarafından alınan belleğin kilidini açmanız gerekir.

## <a name="cprintdialogexgetdrivername"></a><a name="getdrivername"></a> CPrintDialogEx:: Getsürücüadı

Sistem tanımlı yazıcı cihazı sürücüsünün adını almak için [DoModal](#domodal) veya [GetDefaults](#getdefaults) çağrıldıktan sonra bu işlevi çağırın.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CString`Sistem tarafından tanımlanan sürücü adını belirtme.

### <a name="remarks"></a>Açıklamalar

`CString` `GetDriverName` [CDC:: CreateDC](../../mfc/reference/cdc-class.md#createdc)çağrısında *lpszDriverName* değeri olarak döndürülen nesneye yönelik bir işaretçi kullanın.

## <a name="cprintdialogexgetportname"></a><a name="getportname"></a> CPrintDialogEx:: GetPortName

Şu anda seçili olan yazıcı bağlantı noktasının adını almak için [DoModal](#domodal) veya [GetDefaults](#getdefaults) çağrıldıktan sonra bu işlevi çağırın.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili olan yazıcı bağlantı noktasının adı.

## <a name="cprintdialogexgetprinterdc"></a><a name="getprinterdc"></a> CPrintDialogEx:: GetPrinterDC

Yazıcı cihaz bağlamına bir tanıtıcı döndürür.

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazıcı cihaz bağlamı için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Kullanmayı bitirdiğinizde cihaz bağlamını silmek için Windows [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) işlevini çağırmanız gerekir.

## <a name="cprintdialogexm_pdex"></a><a name="m_pdex"></a> CPrintDialogEx:: m_pdex

Üyeleri iletişim kutusu nesnesinin özelliklerini depolayan bir PRINTDLGEX yapısı.

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>Açıklamalar

Bir nesne oluşturduktan sonra `CPrintDialogEx` , `m_pdex` [DoModal](#domodal) üye işlevini çağırmadan önce iletişim kutusunun çeşitli yönlerini ayarlamak için kullanabilirsiniz. Yapı hakkında daha fazla bilgi için `m_pdex` Windows SDK [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) bakın.

`m_pdex`Veri üyesini doğrudan değiştirirseniz, varsayılan davranışı geçersiz kılarsınız.

## <a name="cprintdialogexprintall"></a><a name="printall"></a> CPrintDialogEx::P Rinyüksekliğinde

`DoModal`Belgedeki tüm sayfaların yazdırılması gerekip gerekmediğini anlamak için çağrıldıktan sonra bu işlevi çağırın.

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgedeki tüm sayfalar yazdırıldıysa TRUE; Aksi halde yanlış.

## <a name="cprintdialogexprintcollate"></a><a name="printcollate"></a> CPrintDialogEx::P rintCollate

`DoModal`Yazıcının belgenin tüm yazdırılan kopyalarını harmanlamaları gerekip gerekmediğini belirleme ' yı çağırdıktan sonra bu işlevi çağırın.

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı iletişim kutusunda Harmanla onay kutusunu seçerse TRUE; Aksi halde yanlış.

## <a name="cprintdialogexprintcurrentpage"></a><a name="printcurrentpage"></a> CPrintDialogEx::P rintCurrentPage

`DoModal`Geçerli sayfanın belgede yazdırılması gerekip gerekmediğini anlamak için bu işlevi çağırın.

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdır iletişim kutusunda **geçerli sayfayı yazdır** seçiliyse true; Aksi halde yanlış.

## <a name="cprintdialogexprintrange"></a><a name="printrange"></a> CPrintDialogEx::P rintRange

`DoModal`Belgedeki yalnızca bir sayfa aralığını yazdırıp yazdırmayacağını anlamak için çağrıldıktan sonra bu işlevi çağırın.

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yalnızca belgedeki bir sayfa aralığının yazdırılması gerekiyorsa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Belirtilen sayfa aralıkları [m_pdex](#m_pdex) belirlenebilir (bkz `nPageRanges` `nMaxPageRanges` ., ve `lpPageRanges` Windows SDK yapısındaki [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) yapısı).

## <a name="cprintdialogexprintselection"></a><a name="printselection"></a> CPrintDialogEx::P rintSelection

`DoModal`Yalnızca şu anda seçili olan öğelerin yazdırılması gerekip gerekmediğini anlamak için çağrıldıktan sonra bu işlevi çağırın.

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yalnızca seçilen öğeler yazdırılabiliyorsa TRUE; Aksi halde yanlış.

## <a name="see-also"></a>Ayrıca bkz.

[CCommonDialog sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo yapısı](../../mfc/reference/cprintinfo-structure.md)
