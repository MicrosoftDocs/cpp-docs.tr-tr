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
ms.openlocfilehash: 01a320fbcd9760bab484f3c75553613852ca9aed
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778097"
---
# <a name="cpagesetupdialog-class"></a>CPageSetupDialog sınıfı

Ayar ve yazdırma kenar boşluklarını değiştirmek için ek destek içeren Windows ortak OLE sayfa düzeni iletişim kutusu tarafından sağlanan hizmetleri kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CPageSetupDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)|Oluşturur bir `CPageSetupDialog` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|Yazdırma için bir cihaz bağlamı oluşturur.|
|[CPageSetupDialog::DoModal](#domodal)|İletişim kutusunda görüntülenir ve kullanıcı oluşturma seçimi sağlar.|
|[CPageSetupDialog::GetDeviceName](#getdevicename)|Yazıcı cihaz adını döndürür.|
|[CPageSetupDialog::GetDevMode](#getdevmode)|Geçerli DEVMODE yazıcının döndürür.|
|[CPageSetupDialog::GetDriverName](#getdrivername)|Yazıcı tarafından kullanılan sürücü döndürür.|
|[CPageSetupDialog::GetMargins](#getmargins)|Yazıcı geçerli kenar boşluğu ayarlarını döndürür.|
|[CPageSetupDialog::GetPaperSize](#getpapersize)|Yazıcı kağıdı boyutunu döndürür.|
|[CPageSetupDialog::GetPortName](#getportname)|Çıkış bağlantı noktası adını döndürür.|
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|Yazdırılan sayfaya bir ekran görüntüsünü işlemek için framework tarafından çağırılır.|
|[CPageSetupDialog::PreDrawPage](#predrawpage)|Yazdırılan sayfanın ekran görüntüsünü işlemeden önce framework tarafından çağırılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPageSetupDialog::m_psd](#m_psd)|Özelleştirmek için kullanılan bir yapının bir `CPageSetupDialog` nesne.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, Sayfa Yapısı iletişim kutusunun gerçekleşmesi için tasarlanmıştır.

Kullanılacak bir `CPageSetupDialog` nesne, ilk nesnesini kullanarak oluşturun `CPageSetupDialog` Oluşturucusu. İletişim kutusu oluşturulmuş bir kez ayarlayabilir veya herhangi bir değer değiştirme `m_psd` iletişim kutusunun denetimleri değerlerini başlatmak için veri üyesi. [M_psd](#m_psd) türü PAGESETUPDLG yapısıdır.

İletişim kutusu denetimleri başlatılıyor sonra çağrı `DoModal` iletişim kutusunu görüntülemek ve yazdırma seçeneklerini seçmesini sağlamak için üye işlevi. `DoModal` Kullanıcı Tamam (IDOK) veya iptal edin (IDCANCEL) düğmesi seçili olup olmadığını döndürür.

Varsa `DoModal` IDOK, döndürür birkaç kullanabileceğiniz `CPageSetupDialog`ait üye işlevleri veya erişim `m_psd` veri üyesi, kullanıcı giriş bilgileri almak için.

> [!NOTE]
>  Ortak OLE Sayfa Yapısı iletişim kutusu kapatıldıktan sonra framework tarafından kullanıcı tarafından yapılan değişiklikler kaydedilmeyecek. Bu iletişim kutusundaki tüm değerleri uygulamanın belge veya uygulama sınıfı üyesi gibi kalıcı bir konuma kaydetmek için uygulamanın kendisi kadar olan.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPageSetupDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdlgs.h

##  <a name="cpagesetupdialog"></a>  CPageSetupDialog::CPageSetupDialog

Oluşturmak için bu işlevi çağırın bir `CPageSetupDialog` nesne.

```
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*CertOpenStore*<br/>
İletişim kutusunun ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayraklar. Değerleri, bit düzeyinde OR işleci kullanılarak birleştirilebilir. Bu değerler, aşağıdaki anlamlara sahip:

- Yazıcının alt sınır aynı olacak şekilde kenar izin verilen en düşük genişlik PSD_DEFAULTMINMARGINS ayarlar. Bu bayrak PSD_MARGINS ve PSD_MINMARGINS bayrakları ayrıca belirtilmişse göz ardı edilir.

- Uygulanan PSD_INWININIINTLMEASURE değil.

- PSD_MINMARGINS neden olur, belirtilen değerler kullanılacak sistem `rtMinMargin` üyesi olarak sol, üst, sağ ve alt kenar boşlukları izin verilen en düşük genişlik. Sistem, kullanıcının belirtilen en düşük'dan küçük bir genişliğe girmesini engeller. PSD_MINMARGINS belirtilmezse bu yazıcı tarafından izin verilen minimum izin verilen genişlikleri ayarlar.

- Kenar boşluğu denetim alanı PSD_MARGINS etkinleştirir.

- PSD_INTHOUSANDTHSOFINCHES inç 1/1000 ile Karşılaştırılacak iletişim kutusu birimleri neden olur.

- PSD_INHUNDREDTHSOFMILLIMETERS 1/100 biri ölçülecek iletişim kutusu birimleri neden olur.

- PSD_DISABLEMARGINS kenar boşluğu iletişim kutusu denetimleri devre dışı bırakır.

- PSD_DISABLEPRINTER yazıcı düğmesini devre dışı bırakır.

- PSD_NOWARNING uyarı iletisi hiçbir varsayılan yazıcı olduğunda görüntülenmesini engeller.

- PSD_DISABLEORIENTATION sayfa yönünü iletişim denetimini devre dışı bırakır.

- PSD_RETURNDEFAULT neden `CPageSetupDialog` döndürülecek [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) ve [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) yapıları sistem varsayılan yazıcı için bir iletişim kutusu görüntülenmeden başlatılır. Her iki varsayılır `hDevNames` ve `hDevMode` NULL; Aksi halde, işlev hata döndürür. Bir eski yazıcı sürücüsü tarafından (öncesindeki Windows sürüm 3.0), sistem varsayılan yazıcı destekleniyorsa yalnızca `hDevNames` döndürülür; `hDevMode` null.

- PSD_DISABLEPAPER kağıt seçim denetimi devre dışı bırakır.

- PSD_SHOWHELP Yardım düğmesini göstermek iletişim kutusu neden olur. `hwndOwner` Bu bayrak belirtilmezse üyesi NULL olmamalıdır.

- Kanca işlevini belirtilen PSD_ENABLEPAGESETUPHOOK sağlayan `lpfnSetupHook`.

- PSD_ENABLEPAGESETUPTEMPLATE Oluştur iletişim kutusu tarafından tanımlanan iletişim şablonu kutusunu kullanarak işletim sisteminin neden `hInstance` ve `lpSetupTemplateName`.

- PSD_ENABLEPAGESETUPTEMPLATEHANDLE gösterir `hInstance` önceden yüklenmiş iletişim kutusunda şablon içeren veri bloğu tanımlar. Yoksayar `lpSetupTemplateName` Bu bayrak belirtilmezse.

- Kanca işlevini belirtilen PSD_ENABLEPAGEPAINTHOOK sağlayan `lpfnPagePaintHook`.

- Çizim alanı iletişim kutusunun PSD_DISABLEPAGEPAINTING devre dışı bırakır.

*pParentWnd*<br/>
İletişim kutusunun üst veya sahibi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Kullanım [DoModal](../../mfc/reference/cdialog-class.md#domodal) iletişim kutusunu görüntülemek için işlev.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]

##  <a name="createprinterdc"></a>  CPageSetupDialog::CreatePrinterDC

Bir yazıcı cihaz bağlamında oluşturur [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) ve [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) yapıları.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan yazıcı cihaz bağlamına (DC) işler.

##  <a name="domodal"></a>  CPageSetupDialog::DoModal

Windows ortak OLE sayfa düzeni iletişim kutusunu görüntülemek ve yazdırma kenar boşluklarını, boyutunu ve yönünü kağıt ve hedef yazıcı gibi çeşitli yazdırma Kur seçeneklerini seçmek kullanıcı izin vermek için bu işlevi çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

IDOK veya IDCANCEL. IDCANCEL döndürülürse, Windows Arama [CommDlgExtendedError](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) hata oluşup oluşmadığını belirlemek için işlevi.

IDOK ve IDCANCEL kullanıcı Tamam'ı veya iptal düğmesi seçili olup olmadığını gösteren sabittir.

### <a name="remarks"></a>Açıklamalar

Ayrıca, kullanıcı yazıcı ayarları ağ konumu ve seçili yazıcıya özgü özellikleri gibi erişebilirsiniz.

Çeşitli Sayfa Yapısı iletişim kutusu seçenekleri üyeleri ayarlayarak başlatmak istiyorsanız `m_psd` yapısını çağırmadan önce yapmalısınız `DoModal`, ve sonra iletişim nesnesi oluşturulur. Arama sonra `DoModal`, diğer üye işlevlerini kullanıcı giriş bilgileri ve Ayarları iletişim kutusuna alınacak çağırın.

Kullanıcı tarafından girilen geçerli ayarları yayılması istiyorsanız, çağrı yapmak [CWinApp::SelectPrinter](../../mfc/reference/cwinapp-class.md#selectprinter). Bu işlev bilgileri alır `CPageSetupDialog` nesnesini başlatır ve uygun özniteliklerle yeni bir yazıcı DC seçer.

[!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]

### <a name="example"></a>Örnek

  Örneğin bakın [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).

##  <a name="getdevicename"></a>  CPageSetupDialog::GetDeviceName

Sonra bu işlevi çağırın `DoModal` Seçili yazıcının adını almak için.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından kullanılan cihaz adı `CPageSetupDialog` nesne.

##  <a name="getdevmode"></a>  CPageSetupDialog::GetDevMode

Çağırdıktan sonra bu işlevi çağırın `DoModal` yazıcı cihaz bağlamı hakkında bilgi almak için `CPageSetupDialog` nesne.

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

[DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) cihaz başlatma ve yazdırma sürücüsü ortamı hakkında bilgi içeren veri yapısı. Windows ile bu yapı tarafından gerçekleştirilecek bellek kilidini açmanız gerekir [GlobalUnlock](/windows/desktop/api/winbase/nf-winbase-globalunlock) Windows SDK'da açıklanan işlevi.

##  <a name="getdrivername"></a>  CPageSetupDialog::GetDriverName

Çağırdıktan sonra bu işlevi çağırın [DoModal](../../mfc/reference/cprintdialog-class.md#domodal) sistem tarafından tanımlanan yazıcı aygıt sürücüsünün adını alamadı.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` sistem tarafından tanımlanan sürücü adı belirtme.

### <a name="remarks"></a>Açıklamalar

Bir işaretçi kullanın `CString` tarafından döndürülen nesne `GetDriverName` değeri olarak `lpszDriverName` çağrıda [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).

##  <a name="getmargins"></a>  CPageSetupDialog::GetMargins

Çağrısı yapıldıktan sonra bu işlevi çağırın `DoModal` yazıcı cihaz sürücüsü kenar boşlukları alınacak.

```
void GetMargins(
    LPRECT lpRectMargins,
    LPRECT lpRectMinMargins) const;
```

### <a name="parameters"></a>Parametreler

*lpRectMargins*<br/>
İşaretçi bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) (1/1000 inç veya 1/100 mm) şu anda seçili yazıcıya yazdırma kenar boşluklarını tanımlayan nesne. Bu dikdörtgenin içindeki ilgilenmiyorsanız Bu parametre için NULL geçirin.

*lpRectMinMargins*<br/>
İşaretçi bir `RECT` yapısı veya `CRect` (1/1000 inç veya 1/100 mm) şu anda seçili yazıcı minimum yazdırma kenar boşluklarını tanımlayan nesne. Bu dikdörtgenin içindeki ilgilenmiyorsanız Bu parametre için NULL geçirin.

##  <a name="getpapersize"></a>  CPageSetupDialog::GetPaperSize

Yazdırma için seçili boyutunu almak için bu işlevi çağırın.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

A [CSize](../../atl-mfc-shared/reference/csize-class.md) yazdırma için seçili kağıt (1/1000 inç veya 1/100 mm) boyutunu içeren nesne.

##  <a name="getportname"></a>  CPageSetupDialog::GetPortName

Çağırdıktan sonra bu işlevi çağırın `DoModal` seçili yazıcı bağlantı noktasını adını almak için.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili yazıcı bağlantı noktasını adı.

##  <a name="m_psd"></a>  CPageSetupDialog::m_psd

Yapı üyeleri iletişim nesnesinin özelliklerini depolamak PAGESETUPDLG, türünü.

```
PAGESETUPDLG m_psd;
```

### <a name="remarks"></a>Açıklamalar

Oluşturma sonrasında bir `CPageSetupDialog` nesne kullanabileceğiniz `m_psd` çeşitli yönlerini çağırmadan önce iletişim kutusunda ayarlanacak `DoModal` üye işlevi.

Değiştirirseniz `m_psd` veri üyesi doğrudan, hiçbir varsayılan davranışı geçersiz kılar.

Daha fazla bilgi için [PAGESETUPDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpsda) yapısı, Windows SDK'sı bakın.

Örneğin bakın [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).

##  <a name="ondrawpage"></a>  CPageSetupDialog::OnDrawPage

Yazdırılan sayfanın ekran görüntüsünü çizmek için framework tarafından çağırılır.

```
virtual UINT OnDrawPage(
    CDC* pDC,
    UINT nMessage,
    LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Yazıcı cihaz bağlamı işaretçisi.

*nİleti*<br/>
Şu anda çizilen sayfa alanı belirten bir ileti belirtir. Aşağıdakilerden biri olabilir:

- WM_PSD_FULLPAGERECT sayfanın tamamını alan.

- WM_PSD_MINMARGINRECT geçerli en düşük kenar boşlukları.

- Kenar boşlukları WM_PSD_MARGINRECT geçerli.

- Sayfa içeriğini WM_PSD_GREEKTEXTRECT.

- WM_PSD_ENVSTAMPRECT pulu gösterimi için ayrılmış alan.

- WM_PSD_YAFULLPAGERECT alanı için bir dönüş adresi gösterimi. Bu alan örnek sayfası alanın kenarlarına genişletir.

*lpRect*<br/>
İşaretçi bir [CRect](../../atl-mfc-shared/reference/crect-class.md) veya [RECT](/windows/desktop/api/windef/ns-windef-tagrect) çizim alanının koordinatları içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlenen belirtilmişse sıfır dışı değer; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu görüntü daha sonra ortak OLE sayfa düzeni iletişim kutusunun bir parçası olarak görüntülenir. Varsayılan uygulama görüntüyü bir sayfanın metin çizer.

Bu işlev, belirli bir görüntünün veya görüntü alanının çiziminin özelleştirmek için geçersiz kılın. Kullanarak bunu yapabilirsiniz bir **geçiş** deyimiyle **çalışması** değerini kontrol deyimleri *nİleti*. Örneğin, sayfa görüntüsü içeriğini işlenmesi özelleştirmek için aşağıdaki kod örneği kullanabilirsiniz:

[!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]

Unutmayın, her bir durumu işlemek gerekmez *nİleti*. Görüntünün görüntü ya da tüm alanı çeşitli bileşenlerinin bir bileşen işlemek seçebilirsiniz.

##  <a name="predrawpage"></a>  CPageSetupDialog::PreDrawPage

Yazdırılan sayfanın ekran görüntüsünü çizmeden önce framework tarafından çağırılır.

```
virtual UINT PreDrawPage(
    WORD wPaper,
    WORD wFlags,
    LPPAGESETUPDLG pPSD);
```

### <a name="parameters"></a>Parametreler

*wPaper*<br/>
Sayfa boyutunu belirten bir değer belirtir. Bu değer şunlardan biri olabilir **DMPAPER_** değerleri açıklamasında listelenen [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) yapısı.

*wFlags*<br/>
Kağıt veya Zarf yönünü belirtir ve yazıcı iğneli veya HPPCL (Hewlett Packard Yazıcı Denetim Dili) cihazı olup olmadığı. Bu parametre aşağıdaki değerlerden biri olabilir:

- 0x001 (nokta vuruşlu) yatay modda kağıt

- 0x003 (HPPCL) yatay modda kağıt

- 0x005 (nokta vuruşlu) dikey modda kağıt

- 0x007 (HPPCL) dikey modda kağıt

- 0x00b (HPPCL) yatay modda zarfa koy

- 0x00d (nokta vuruşlu) dikey modda zarfa koy

- 0x019 (nokta vuruşlu) yatay modda zarfa koy

- 0x01f (nokta vuruşlu) dikey modda zarfa koy

*pPSD*<br/>
İşaretçi bir `PAGESETUPDLG` yapısı. Daha fazla bilgi için [PAGESETUPDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpsda), Windows SDK'sı bakın.

### <a name="return-value"></a>Dönüş Değeri

İşlenen belirtilmişse sıfır dışı değer; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Resmin çizim özelleştirmek için bu işlevi geçersiz kılar. Bu işlev geçersiz kılma ve TRUE döndürün, görüntünün çizin gerekir. Bu işlev geçersiz kılma ve false değerini döndürür, tüm varsayılan görüntü framework tarafından çekilir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
