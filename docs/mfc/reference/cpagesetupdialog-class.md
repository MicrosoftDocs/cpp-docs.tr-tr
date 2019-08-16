---
title: CPageSetupDialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- CPageSetupDialog
- AFXDLGS/CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CreatePrinterDC
- AFXDLGS/CPageSetupDialog::DoModal
- AFXDLGS/CPageSetupDialog::GetDeviceName
- AFXDLGS/CPageSetupDialog::GetDevMode
- AFXDLGS/CPageSetupDialog::GetDriverName
- AFXDLGS/CPageSetupDialog::GetMargins
- AFXDLGS/CPageSetupDialog::GetPaperSize
- AFXDLGS/CPageSetupDialog::GetPortName
- AFXDLGS/CPageSetupDialog::OnDrawPage
- AFXDLGS/CPageSetupDialog::PreDrawPage
- AFXDLGS/CPageSetupDialog::m_psd
helpviewer_keywords:
- CPageSetupDialog [MFC], CPageSetupDialog
- CPageSetupDialog [MFC], CreatePrinterDC
- CPageSetupDialog [MFC], DoModal
- CPageSetupDialog [MFC], GetDeviceName
- CPageSetupDialog [MFC], GetDevMode
- CPageSetupDialog [MFC], GetDriverName
- CPageSetupDialog [MFC], GetMargins
- CPageSetupDialog [MFC], GetPaperSize
- CPageSetupDialog [MFC], GetPortName
- CPageSetupDialog [MFC], OnDrawPage
- CPageSetupDialog [MFC], PreDrawPage
- CPageSetupDialog [MFC], m_psd
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
ms.openlocfilehash: 18b17d0f40aaab6ba2a018a568950549eda23016
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503008"
---
# <a name="cpagesetupdialog-class"></a>CPageSetupDialog sınıfı

Windows ortak OLE sayfa kurulumu iletişim kutusu tarafından sunulan hizmetleri, yazdırma kenar boşluklarını ayarlama ve değiştirme için ek destek ile kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CPageSetupDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPageSetupDialog:: CPageSetupDialog](#cpagesetupdialog)|Bir `CPageSetupDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|Yazdırma için bir cihaz bağlamı oluşturur.|
|[CPageSetupDialog::DoModal](#domodal)|İletişim kutusunu görüntüler ve kullanıcının seçim yapmasına izin verir.|
|[CPageSetupDialog::GetDeviceName](#getdevicename)|Yazıcının cihaz adını döndürür.|
|[CPageSetupDialog::GetDevMode](#getdevmode)|Yazıcının geçerli DEVMODE değerini döndürür.|
|[CPageSetupDialog::GetDriverName](#getdrivername)|Yazıcı tarafından kullanılan sürücüyü döndürür.|
|[CPageSetupDialog::GetMargins](#getmargins)|Yazıcının geçerli kenar boşluğu ayarlarını döndürür.|
|[CPageSetupDialog::GetPaperSize](#getpapersize)|Yazıcının kağıt boyutunu döndürür.|
|[CPageSetupDialog::GetPortName](#getportname)|Çıkış bağlantı noktası adını döndürür.|
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|Yazdırılmış bir sayfanın ekran görüntüsünü işlemek için Framework tarafından çağırılır.|
|[CPageSetupDialog::PreDrawPage](#predrawpage)|Yazdırılmış bir sayfanın ekran görüntüsünü işlemeden önce Framework tarafından çağırılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPageSetupDialog::m_psd](#m_psd)|Bir `CPageSetupDialog` nesneyi özelleştirmek için kullanılan bir yapı.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, yazdırma Kurulumu iletişim kutusunun yerini alacak şekilde tasarlanmıştır.

Bir `CPageSetupDialog` nesnesi kullanmak için, önce `CPageSetupDialog` oluşturucuyu kullanarak nesnesini oluşturun. İletişim kutusu oluşturulduktan sonra, iletişim kutusu denetimlerinin değerlerini başlatmak için `m_psd` veri üyesinde herhangi bir değer ayarlayabilir veya değiştirebilirsiniz. [M_psd](#m_psd) yapısı PAGESETUPDLG türündedir.

İletişim kutusu denetimlerini başlattıktan sonra, iletişim kutusunu göstermek `DoModal` ve kullanıcının yazdırma seçeneklerini seçmesine izin vermek için üye işlevini çağırın. `DoModal`kullanıcının Tamam (IDOK) veya Cancel (ıDCANCEL) düğmesini seçmediğini döndürür.

IDOK `CPageSetupDialog`döndürürse,Kullanıcı tarafından bilgi girişi almak için çeşitli üye `m_psd` işlevlerini kullanabilir veya veri üyesine erişebilirsiniz. `DoModal`

> [!NOTE]
>  Ortak OLE sayfa kurulumu iletişim kutusu kapatıldıktan sonra, Kullanıcı tarafından yapılan tüm değişiklikler Framework tarafından kaydedilmez. Bu iletişim kutusundan herhangi bir değeri, uygulamanın belge veya uygulama sınıfının üyesi gibi kalıcı bir konuma kaydetmek, uygulamanın kendisine ait olur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPageSetupDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs. h

##  <a name="cpagesetupdialog"></a>CPageSetupDialog:: CPageSetupDialog

Bir `CPageSetupDialog` nesne oluşturmak için bu işlevi çağırın.

```
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*dwFlags*<br/>
İletişim kutusunun ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayrak. Değerler bit düzeyinde OR işleci kullanılarak birleştirilebilir. Bu değerler aşağıdaki anlamlara sahiptir:

- PSD_DEFAULTMINMARGINS sayfa kenar boşlukları için izin verilen en düşük genişlikler, yazıcı alt limitleriyle aynı olacak şekilde ayarlar. PSD_MARGINS ve PSD_MINMARGINS bayrakları da belirtilmişse bu bayrak yoksayılır.

- PSD_INWININIINTLMEASURE uygulanmadı.

- PSD_MINMARGINS, sistemin `rtMinMargin` üyede belirtilen değerleri sol, üst, sağ ve alt kenar boşlukları için izin verilen en düşük genişlikler olarak kullanmasına neden olur. Sistem, kullanıcının belirtilen en düşük boyuttan daha küçük bir genişlik girmesini engeller. PSD_MINMARGINS belirtilmemişse, sistem izin verilen en düşük genişliği yazıcı tarafından izin verilen genişlik olarak ayarlar.

- PSD_MARGINS, kenar boşluğu denetim alanını etkinleştirir.

- PSD_INTHOUSANDTHSOFINCHES, iletişim kutusu birimlerinin bir inç 1/1000 ' de ölçülmesine neden olur.

- PSD_INHUNDREDTHSOFMILLIMETERS, iletişim kutusu birimlerinin bir milimetrenin 1/100 ' de ölçülmesine neden olur.

- PSD_DISABLEMARGINS, kenar boşluğu iletişim kutusu denetimlerini devre dışı bırakır.

- PSD_DISABLEPRINTER, yazıcı düğmesini devre dışı bırakır.

- PSD_NOWARNING, varsayılan bir yazıcı olmadığında uyarı iletisinin görüntülenmesini önler.

- PSD_DISABLEORIENTATION, sayfa yönlendirme iletişim kutusu denetimini devre dışı bırakır.

- PSD_RETURNDEFAULT, `CPageSetupDialog` bir iletişim kutusu görüntülemeden sistem varsayılan yazıcısı için başlatılan [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) ve [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) yapılarını döndürmesine neden olur. Her ikisi de `hDevNames` `hDevMode` null olduğu varsayılır; Aksi takdirde, işlev bir hata döndürür. Sistem varsayılan yazıcısı eski bir yazıcı sürücüsü (Windows sürüm 3,0 ' den önceki sürümler) tarafından destekleniyorsa, yalnızca `hDevNames` döndürülür; `hDevMode` null.

- PSD_DISABLEPAPER, kağıt seçim denetimini devre dışı bırakır.

- PSD_SHOWHELP, iletişim kutusunun Yardım düğmesini göstermesini sağlar. Bu bayrak belirtilmişse üyenin null olmaması gerekir. `hwndOwner`

- PSD_ENABLEPAGESETUPHOOK, içinde `lpfnSetupHook`belirtilen kanca işlevinin kullanılmasına izin vermez.

- PSD_ENABLEPAGESETUPTEMPLATE, ve `hInstance` `lpSetupTemplateName`tarafından tanımlanan iletişim kutusu şablonu kutusunu kullanarak, işletim sisteminin iletişim kutusunu oluşturmasına neden olur.

- PSD_ENABLEPAGESETUPTEMPLATEHANDLE, `hInstance` önceden yüklenmiş bir iletişim kutusu şablonu içeren bir veri bloğunu tanımlayan anlamına gelir. Bu bayrak belirtilmişse `lpSetupTemplateName` sistem yok sayılır.

- PSD_ENABLEPAGEPAINTHOOK, içinde `lpfnPagePaintHook`belirtilen kanca işlevinin kullanılmasına izin vermez.

- PSD_DISABLEPAGEPAINTING iletişim kutusunun çizim alanını devre dışı bırakır.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahibine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu göstermek için [DoModal](../../mfc/reference/cdialog-class.md#domodal) işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]

##  <a name="createprinterdc"></a>  CPageSetupDialog::CreatePrinterDC

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) ve [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) yapılarından bir yazıcı cihaz bağlamı oluşturur.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan yazıcı cihaz bağlamına (DC) işleyin.

##  <a name="domodal"></a>CPageSetupDialog::D oModal

Windows ortak OLE sayfası Kurulumu iletişim kutusunu göstermek ve kullanıcının yazdırma kenar boşlukları, kağıdın boyutu ve yönü ile hedef yazıcı gibi çeşitli yazdırma kurulum seçeneklerini seçmesine izin vermek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

IDOK veya ıDCANCEL. IDCANCEL döndürülürse, bir hatanın oluşup oluşmadığını öğrenmek için Windows [Commıdextendebir](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini çağırın.

IDOK ve ıDCANCEL, kullanıcının Tamam veya Iptal düğmesini seçip seçmediğini belirten sabitlerdir.

### <a name="remarks"></a>Açıklamalar

Ayrıca, Kullanıcı, seçilen yazıcıya özgü ağ konumu ve özellikler gibi yazıcı kurulum seçeneklerine de erişebilir.

`m_psd` Yapının üyelerini ayarlayarak çeşitli sayfa Kurulum iletişim seçeneklerini başlatmak istiyorsanız, ' yi çağırmadan `DoModal`önce ve iletişim kutusu nesnesi oluşturulduktan sonra yapmanız gerekir. Çağrıldıktan `DoModal`sonra, Kullanıcı tarafından iletişim kutusuna ayarları veya bilgileri almak için diğer üye işlevlerini çağırın.

Kullanıcı tarafından girilen geçerli ayarları yaymak istiyorsanız, [CWinApp:: SelectPrinter](../../mfc/reference/cwinapp-class.md#selectprinter)çağrısı yapın. Bu işlev `CPageSetupDialog` nesnesinden bilgileri alır ve başlatılır ve uygun özniteliklere sahip yeni bir yazıcı DC 'si seçer.

[!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]

### <a name="example"></a>Örnek

  [CPageSetupDialog:: CPageSetupDialog](#cpagesetupdialog)örneğine bakın.

##  <a name="getdevicename"></a>  CPageSetupDialog::GetDeviceName

Şu anda seçili olan `DoModal` yazıcının adını almak için bu işlevi çağırın.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CPageSetupDialog` Nesne tarafından kullanılan cihaz adı.

##  <a name="getdevmode"></a>  CPageSetupDialog::GetDevMode

`CPageSetupDialog` Nesnenin yazıcı cihaz bağlamı hakkında `DoModal` bilgi almak için çağrısından sonra bu işlevi çağırın.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Cihaz başlatma ve yazdırma sürücüsünün ortamı hakkında bilgi içeren [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) veri yapısı. Windows SDK açıklanan Windows [GlobalUnlock](/windows/win32/api/winbase/nf-winbase-globalunlock) işleviyle bu yapı tarafından alınan belleğin kilidini açmanız gerekir.

##  <a name="getdrivername"></a>  CPageSetupDialog::GetDriverName

Sistem tanımlı yazıcı aygıt sürücüsünün adını almak için [DoModal](../../mfc/reference/cprintdialog-class.md#domodal) çağrıldıktan sonra bu işlevi çağırın.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sistem tarafından tanımlanan sürücü adını belirtme.`CString`

### <a name="remarks"></a>Açıklamalar

`CString` [CDC:: CreateDC](../../mfc/reference/cdc-class.md#createdc)çağrısında değeri `GetDriverName` `lpszDriverName` olarak döndürülen nesneye yönelik bir işaretçi kullanın.

##  <a name="getmargins"></a>  CPageSetupDialog::GetMargins

Yazıcı aygıt sürücüsünün kenar boşluklarını almak `DoModal` için çağrısından sonra bu işlevi çağırın.

```
void GetMargins(
    LPRECT lpRectMargins,
    LPRECT lpRectMinMargins) const;
```

### <a name="parameters"></a>Parametreler

*lpRectMargins*<br/>
Şu anda seçili olan yazıcının yazdırma kenar boşluklarını 1/100 1/1000 açıklayan bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine yönelik işaretçi. Bu dikdörtgenle ilgilenmiyorsanız, bu parametre için NULL değeri geçirin.

*Lprectminkenar boşlukları*<br/>
Şu anda seçili `RECT` olan yazıcı `CRect` için en düşük yazdırma kenar boşluklarını (1/1000 inç veya 1/100 mm 'de) açıklayan bir yapı veya nesne işaretçisi. Bu dikdörtgenle ilgilenmiyorsanız, bu parametre için NULL değeri geçirin.

##  <a name="getpapersize"></a>  CPageSetupDialog::GetPaperSize

Yazdırma için seçilen kağıdın boyutunu almak için bu işlevi çağırın.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırma için seçilen kağıdın boyutunu (1/1000 inç veya 1/100 mm) içeren bir [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.

##  <a name="getportname"></a>  CPageSetupDialog::GetPortName

Şu anda seçili olan yazıcı `DoModal` bağlantı noktasının adını almak için çağrıldıktan sonra bu işlevi çağırın.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili olan yazıcı bağlantı noktasının adı.

##  <a name="m_psd"></a>CPageSetupDialog:: m_psd

Üyeleri iletişim kutusu nesnesinin özelliklerini depolayan PAGESETUPDLG türünde bir yapı.

```
PAGESETUPDLG m_psd;
```

### <a name="remarks"></a>Açıklamalar

Bir `CPageSetupDialog` nesne oluşturduktan sonra, `DoModal` üye işlevini çağırmadan `m_psd` önce iletişim kutusunun çeşitli yönlerini ayarlamak için kullanabilirsiniz.

`m_psd` Veri üyesini doğrudan değiştirirseniz, varsayılan davranışı geçersiz kılarsınız.

[Pagesetupdlg](/windows/win32/api/commdlg/ns-commdlg-psdw) yapısı hakkında daha fazla bilgi için Windows SDK bakın.

[CPageSetupDialog:: CPageSetupDialog](#cpagesetupdialog)örneğine bakın.

##  <a name="ondrawpage"></a>CPageSetupDialog:: OnDrawPage

Yazdırılmış bir sayfanın ekran görüntüsünü çizmek için Framework tarafından çağırılır.

```
virtual UINT OnDrawPage(
    CDC* pDC,
    UINT nMessage,
    LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Yazıcı cihaz bağlamına yönelik işaretçi.

*nİleti*<br/>
Sayfanın Şu anda çizildiği alanı belirten bir ileti belirtir. Aşağıdakilerden biri olabilir:

- Tüm sayfa alanını WM_PSD_FULLPAGERECT.

- WM_PSD_MINMARGINRECT geçerli en düşük kenar boşlukları.

- WM_PSD_MARGINRECT geçerli kenar boşlukları.

- Sayfanın WM_PSD_GREEKTEXTRECT Içeriği.

- Bir pul damgası gösterimi için ayrılmış WM_PSD_ENVSTAMPRECT alanı.

- Dönüş adres gösterimi için WM_PSD_YAFULLPAGERECT alanı. Bu alan, örnek sayfa alanının kenarlarını genişletir.

*lpRect*<br/>
Çizim alanının koordinatlarını içeren bir [CRect](../../atl-mfc-shared/reference/crect-class.md) veya [Rect](/windows/win32/api/windef/ns-windef-rect) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlenirse sıfır olmayan değer; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu görüntü daha sonra ortak OLE sayfası Kurulumu iletişim kutusunun bir parçası olarak görüntülenir. Varsayılan uygulama bir metin sayfasının görüntüsünü çizer.

Görüntünün belirli bir alanının veya tüm görüntünün çizimini özelleştirmek için bu işlevi geçersiz kılın. Bunu bir **Switch** deyimi kullanarak, **örnek durum** deyimleriyle *nMessage*değerini denetleyerek yapabilirsiniz. Örneğin, sayfa görüntüsünün içeriğinin işlenmesini özelleştirmek için aşağıdaki örnek kodu kullanabilirsiniz:

[!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]

*NMessage*her durumda, her durum için işleme gerekmediğini unutmayın. Görüntünün bir bileşenini, görüntünün çeşitli bileşenlerini veya tüm alanı işleme seçeneğini belirleyebilirsiniz.

##  <a name="predrawpage"></a>CPageSetupDialog::P reDrawPage

Yazdırılmış bir sayfanın ekran görüntüsünü çizmadan önce Framework tarafından çağırılır.

```
virtual UINT PreDrawPage(
    WORD wPaper,
    WORD wFlags,
    LPPAGESETUPDLG pPSD);
```

### <a name="parameters"></a>Parametreler

*wPaper*<br/>
Kağıt boyutunu gösteren bir değer belirtir. Bu değer, [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) yapısının açıklamasında listelenen **DMPAPER_** değerlerinden biri olabilir.

*wFlags*<br/>
Kağıdın veya zarfın yönünü ve yazıcının bir nokta vuruşlu veya HPPCL (Hewlett Packard Printer Control Language) cihazı olup olmadığını gösterir. Bu parametre aşağıdaki değerlerden birine sahip olabilir:

- bir yatay modda 0x001 kağıt (nokta matrisi)

- 0x003 kağıt yatay modda (HPPCL)

- dikey modda 0x005 kağıdı (nokta matrisi)

- dikey modda 0x007 kağıdı (HPPCL)

- 0x00b zarfı yatay modda (HPPCL)

- dikey modda 0x00d zarfı (nokta matrisi)

- 0x019 yatay modda zarf (nokta matris)

- dikey modda 0x01f zarfı (nokta matris)

*pPSD*<br/>
`PAGESETUPDLG` Yapı işaretçisi. [Pagesetupdlg](/windows/win32/api/commdlg/ns-commdlg-psdw)hakkında daha fazla bilgi için Windows SDK bakın.

### <a name="return-value"></a>Dönüş Değeri

İşlenirse sıfır olmayan değer; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Görüntünün çizimini özelleştirmek için bu işlevi geçersiz kılın. Bu işlevi geçersiz kılarsınız ve TRUE değerini döndürdüğünüzde görüntünün tamamını çizmeniz gerekir. Bu işlevi geçersiz kılarsınız ve FALSE değerini döndürdüğünüzde varsayılan görüntünün tamamı Framework tarafından çizilir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
