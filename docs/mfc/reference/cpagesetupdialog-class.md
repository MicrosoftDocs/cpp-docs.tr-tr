---
title: CPageSetupDialog Sınıfı
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
ms.openlocfilehash: 218ed24ccf56854622e20936299fcc2e8a3d0fa9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374785"
---
# <a name="cpagesetupdialog-class"></a>CPageSetupDialog Sınıfı

Windows tarafından sağlanan hizmetleri kapsüller, yazdırma kenar boşluklarını ayarlamak ve değiştirmek için ek destekle Windows ortak OLE Sayfa Kurulumu iletişim kutusu tarafından sağlanır.

## <a name="syntax"></a>Sözdizimi

```
class CPageSetupDialog : public CCommonDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)|Bir `CPageSetupDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|Yazdırma için bir aygıt bağlamı oluşturur.|
|[CPageSetupDialog::DoModal](#domodal)|İletişim kutusunu görüntüler ve kullanıcının seçim yapmasına izin verir.|
|[CPageSetupDialog::GetDeviceName](#getdevicename)|Yazıcının aygıt adını döndürür.|
|[CPageSetupDialog::GetDevMode](#getdevmode)|Yazıcının geçerli DEVMODE'unu döndürür.|
|[CPageSetupDialog::GetDriverName](#getdrivername)|Yazıcı tarafından kullanılan sürücüyü döndürür.|
|[CPageSetupDialog::GetMargins](#getmargins)|Yazıcının geçerli kenar boşluğu ayarlarını verir.|
|[CPageSetupDialog::GetPaperSize](#getpapersize)|Yazıcının kağıt boyutunu döndürür.|
|[CPageSetupDialog::GetPortName](#getportname)|Çıkış bağlantı noktası adını döndürür.|
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|Yazdırılan bir sayfanın ekran görüntüsünü işlemek için çerçeve tarafından çağrılır.|
|[CPageSetupDialog::PreDrawPage](#predrawpage)|Yazdırılan bir sayfanın ekran görüntüsünü oluşturmadan önce çerçeve tarafından çağrılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CPageSetupDialog::m_psd](#m_psd)|Nesneyi özelleştirmek için `CPageSetupDialog` kullanılan bir yapı.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, Yazdırma Kurulumu iletişim kutusunun yerini alacak şekilde tasarlanmıştır.

Bir `CPageSetupDialog` nesneyi kullanmak için önce `CPageSetupDialog` oluşturucuyu kullanarak nesneyi oluşturun. İletişim kutusu oluşturulduktan sonra, iletişim kutusunun denetimlerinin `m_psd` değerlerini açmak için veri üyesindeki tüm değerleri ayarlayabilir veya değiştirebilirsiniz. [m_psd](#m_psd) yapısı PAGESETUPDLG türüdür.

İletişim kutusu denetimlerini açtıktan sonra, iletişim kutusunu görüntülemek için `DoModal` üye işlevi arayın ve kullanıcının yazdırma seçeneklerini seçmesine izin verin. `DoModal`kullanıcıok (IDOK) veya İptal (IDCANCEL) düğmesini seçip seçmediğini döndürür.

`DoModal` IDOK'u döndürürse, kullanıcı tarafından bilgi girdisi `CPageSetupDialog`almak için birkaç 'üye işlevini kullanabilir veya veri üyesine `m_psd` erişebilirsiniz.

> [!NOTE]
> Ortak OLE Sayfa Kurulumu iletişim kutusu reddedildikten sonra, kullanıcı tarafından yapılan değişiklikler çerçeve tarafından kaydedilmez. Bu iletişim kutusundan, uygulamanın belge veya uygulama sınıfının üyesi gibi kalıcı bir konuma herhangi bir değeri kaydetmek uygulamanın kendisine bağlıdır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPageSetupDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs.h

## <a name="cpagesetupdialogcpagesetupdialog"></a><a name="cpagesetupdialog"></a>CPageSetupDialog::CPageSetupDialog

Bir `CPageSetupDialog` nesne oluşturmak için bu işlevi çağırın.

```
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*Dwflags*<br/>
İletişim kutusunun ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayrak. Değerler bitwise-OR işleci kullanılarak birleştirilebilir. Bu değerlerin şu anlamları vardır:

- PSD_DEFAULTMINMARGINS Sayfa kenar boşlukları için izin verilebilen minimum genişlikleri yazıcının minimum sahipolduğu şekilde ayarlar. PSD_MARGINS ve PSD_MINMARGINS bayrakları da belirtilirse bu bayrak yoksayılır.

- PSD_INWININIINTLMEASURE Uygulanmadı.

- PSD_MINMARGINS Sistemin `rtMinMargin` üyede belirtilen değerleri sol, üst, sağ ve alt kenar boşlukları için izin verilebilen minimum genişlikolarak kullanmasına neden olur. Sistem, kullanıcının belirtilen minimumdan daha az bir genişlik girmesini engeller. PSD_MINMARGINS belirtilmemişse, sistem yazıcı tarafından izin verilen en az izin verilen genişlikleri ayarlar.

- PSD_MARGINS Kenar boşluğu denetim alanını etkinleştirir.

- PSD_INTHOUSANDTHSOFINCHES İletişim kutusunun birimlerinin bir inçin 1/1000'inde ölçülmesini neden olur.

- PSD_INHUNDREDTHSOFMILLIMETERS İletişim kutusunun birimlerinin milimetrenin 1/100'ü cinsinden ölçülmesini neden olur.

- PSD_DISABLEMARGINS kenar boşluğu iletişim kutusu denetimlerini devre dışı bırakıyor.

- PSD_DISABLEPRINTER Yazıcı düğmesini devre dışı kılabilir.

- PSD_NOWARNING Varsayılan yazıcı olmadığında uyarı iletisinin görüntülenmesini önler.

- PSD_DISABLEORIENTATION sayfa yönlendirme iletişim denetimini devre dışı bırakmaz.

- PSD_RETURNDEFAULT `CPageSetupDialog` Bir iletişim kutusu görüntülemeden sistem varsayılan yazıcı için başlatılan [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) ve [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) yapıları dönmek için neden olur. Hem de `hDevNames` NULL `hDevMode` olduğu varsayılır; aksi takdirde, işlev bir hata döndürür. Sistem varsayılan yazıcısı eski bir yazıcı sürücüsü (Windows sürüm 3.0'dan önce) tarafından desteklenirse, yalnızca `hDevNames` döndürülür; `hDevMode` NULL'dur.

- PSD_DISABLEPAPER kağıt seçim denetimini devre dışı kılabilir.

- PSD_SHOWHELP İletişim kutusunun Yardım düğmesini göstermesine neden olur. Bu `hwndOwner` bayrak belirtilmişse üye NULL olmamalıdır.

- PSD_ENABLEPAGESETUPHOOK Belirtilen kanca işlevini `lpfnSetupHook`sağlar.

- PSD_ENABLEPAGESETUPTEMPLATE Tarafından tanımlanan iletişim şablonu kutusunu kullanarak işletim sisteminin iletişim `hInstance` kutusunu `lpSetupTemplateName`oluşturmasına neden olur.

- PSD_ENABLEPAGESETUPTEMPLATEHANDLE Önceden `hInstance` yüklenmiş iletişim kutusu şablonu içeren bir veri bloğunu tanımlayani gösterir. Bu bayrak `lpSetupTemplateName` belirtilirse sistem yoksa.

- PSD_ENABLEPAGEPAINTHOOK Belirtilen kanca işlevini `lpfnPagePaintHook`sağlar.

- PSD_DISABLEPAGEPAINTING iletişim kutusunun çizim alanını devre dışı kılabilir.

*pParentWnd*<br/>
İletişim kutusunun üst öğesine veya sahibine işaretçi.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu görüntülemek için [DoModal](../../mfc/reference/cdialog-class.md#domodal) işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]

## <a name="cpagesetupdialogcreateprinterdc"></a><a name="createprinterdc"></a>CPageSetupDialog::CreatePrinterDC

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) ve [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) yapılarından bir yazıcı aygıtı bağlamı oluşturur.

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan yazıcı aygıtı bağlamını (DC) işleyin.

## <a name="cpagesetupdialogdomodal"></a><a name="domodal"></a>CPageSetupDialog::DoModal

Windows'un ortak OLE Sayfa Kurulumu iletişim kutusunu görüntülemek ve kullanıcının yazdırma kenar boşlukları, kağıdın boyutu ve yönü ve hedef yazıcı gibi çeşitli yazdırma kurulum seçeneklerini seçmesine izin vermek için bu işlevi arayın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İDOK veya IDCANCEL. IDCANCEL döndürülürse, bir hata oluşup oluşmadığını belirlemek için Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) işlevini arayın.

IDOK ve IDCANCEL, kullanıcının Ok veya İptal düğmesini seçip seçmediğini gösteren sabitlerdir.

### <a name="remarks"></a>Açıklamalar

Ayrıca, kullanıcı ağ konumu ve seçili yazıcıya özgü özellikler gibi yazıcı kurulum seçeneklerine erişebilir.

`m_psd` Yapının üyelerini ayarlayarak çeşitli Sayfa Kurulumu iletişim seçeneklerini başlatmayı istiyorsanız, bunu `DoModal`çağırmadan önce ve iletişim nesnesi oluşturulduktan sonra yapmalısınız. Aramadan `DoModal`sonra, kullanıcı tarafından iletişim kutusuna ayar veya bilgi girişi almak için diğer üye işlevleri arayın.

Kullanıcı tarafından girilen geçerli ayarları yaymak istiyorsanız, [CWinApp'ı arayın:SelectPrinter.](../../mfc/reference/cwinapp-class.md#selectprinter) Bu `CPageSetupDialog` işlev, nesneye ait bilgileri alır ve doğru özniteliklere sahip yeni bir yazıcı DC'sini seçer.

[!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]

### <a name="example"></a>Örnek

  [CPageSetupDialog örneğine bakın:CPageSetupDialog](#cpagesetupdialog).

## <a name="cpagesetupdialoggetdevicename"></a><a name="getdevicename"></a>CPageSetupDialog::GetDeviceName

Şu anda `DoModal` seçili yazıcının adını almak için bu işlevi çağırın.

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CPageSetupDialog` Nesne tarafından kullanılan aygıt adı.

## <a name="cpagesetupdialoggetdevmode"></a><a name="getdevmode"></a>CPageSetupDialog::GetDevMode

Nesnenin yazıcı aygıtı bağlamı hakkında bilgi almak için aradıktan sonra bu işlevi arayın. `DoModal` `CPageSetupDialog`

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aygıt başlatma ve yazdırma sürücüsünün ortamı hakkında bilgi içeren [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) veri yapısı. Windows SDK'da açıklanan Windows [GlobalUnlock](/windows/win32/api/winbase/nf-winbase-globalunlock) işlevi ile bu yapı tarafından alınan bellek kilidini açmanız gerekir.

## <a name="cpagesetupdialoggetdrivername"></a><a name="getdrivername"></a>CPageSetupDialog::GetDriverName

Sistem tanımlı yazıcı aygıtı sürücüsünün adını almak için [DoModal'ı](../../mfc/reference/cprintdialog-class.md#domodal) aradıktan sonra bu işlevi arayın.

```
CString GetDriverName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sistem `CString` tanımlı sürücü adını belirten bir.

### <a name="remarks"></a>Açıklamalar

CDC'ye yapılan `CString` bir `GetDriverName` çağrıda değeri `lpszDriverName` olarak döndürülen nesneye işaretçi [kullanın::CreateDC](../../mfc/reference/cdc-class.md#createdc).

## <a name="cpagesetupdialoggetmargins"></a><a name="getmargins"></a>CPageSetupDialog::GetMargins

Yazıcı aygıtı sürücüsünün `DoModal` kenar boşluklarını almak için bir çağrıdan sonra bu işlevi arayın.

```
void GetMargins(
    LPRECT lpRectMargins,
    LPRECT lpRectMinMargins) const;
```

### <a name="parameters"></a>Parametreler

*lpRectMargins*<br/>
Şu anda seçili yazıcının yazdırma kenar boşluklarını açıklayan bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine işaretçi. Bu dikdörtgenle ilgilenmiyorsanız, bu parametre için NULL'u geçirin.

*lpRectMinMargins*<br/>
Şu anda seçili yazıcının minimum yazdırma kenar boşluklarını açıklayan bir `RECT` yapı veya `CRect` nesneye işaretçi . Bu dikdörtgenle ilgilenmiyorsanız, bu parametre için NULL'u geçirin.

## <a name="cpagesetupdialoggetpapersize"></a><a name="getpapersize"></a>CPageSetupDialog::GetPaperSize

Yazdırmaiçin seçilen kağıdın boyutunu almak için bu işlevi arayın.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırma için seçilen kağıdın boyutunu (1/1000 inç veya 1/100 mm olarak) içeren bir [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.

## <a name="cpagesetupdialoggetportname"></a><a name="getportname"></a>CPageSetupDialog::GetPortName

Şu anda `DoModal` seçili yazıcı bağlantı noktasının adını almak için aradıktan sonra bu işlevi arayın.

```
CString GetPortName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili yazıcı bağlantı noktasının adı.

## <a name="cpagesetupdialogm_psd"></a><a name="m_psd"></a>CPageSetupDialog::m_psd

Üyeleri iletişim nesnesinin özelliklerini depolayan PAGESETUPDLG türünden bir yapı.

```
PAGESETUPDLG m_psd;
```

### <a name="remarks"></a>Açıklamalar

Bir `CPageSetupDialog` nesne yaptıktan sonra, `m_psd` `DoModal` üye işlevi aramadan önce iletişim kutusunun çeşitli yönlerini ayarlamak için kullanabilirsiniz.

Veri üyesini `m_psd` doğrudan değiştirirseniz, varsayılan davranışı geçersiz kılarsınız.

[PAGESETUPDLG](/windows/win32/api/commdlg/ns-commdlg-pagesetupdlgw) yapısı hakkında daha fazla bilgi için Windows SDK'ya bakın.

[CPageSetupDialog örneğine bakın:CPageSetupDialog](#cpagesetupdialog).

## <a name="cpagesetupdialogondrawpage"></a><a name="ondrawpage"></a>CPageSetupDialog::OnDrawPage

Yazdırılan bir sayfanın ekran görüntüsünü çizmek için çerçeve tarafından çağrılır.

```
virtual UINT OnDrawPage(
    CDC* pDC,
    UINT nMessage,
    LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Yazıcı aygıtı bağlamını işaretçi.

*nMessage*<br/>
Şu anda çizilmekte olan sayfanın alanını belirten bir ileti belirtir. Aşağıdakilerden biri olabilir:

- tüm sayfa alanını WM_PSD_FULLPAGERECT.

- WM_PSD_MINMARGINRECT Geçerli minimum kenar boşlukları.

- WM_PSD_MARGINRECT Geçerli kenar boşlukları.

- WM_PSD_GREEKTEXTRECT Sayfanın Içeriği.

- WM_PSD_ENVSTAMPRECT Alan bir posta pulu gösterimi için ayrılmıştır.

- İade adresi gösterimi için WM_PSD_YAFULLPAGERECT Alanı. Bu alan, örnek sayfa alanının kenarlarına kadar uzanır.

*Lprect*<br/>
Çizim alanının koordinatlarını içeren bir [CRect](../../atl-mfc-shared/reference/crect-class.md) veya [RECT](/windows/win32/api/windef/ns-windef-rect) nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Ele alınırsa sıfır olmayan değer; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu resim daha sonra ortak OLE Sayfa Kurulumu iletişim kutusunun bir parçası olarak görüntülenir. Varsayılan uygulama, bir metin sayfasının görüntüsünü çizer.

Görüntünün belirli bir alanının veya görüntünün tamamının çizimini özelleştirmek için bu işlevi geçersiz kılın. Bunu, *nMessage'ın*değerini kontrol eden **servis talebi** ekstrelerini içeren bir **anahtar** deyimi kullanarak yapabilirsiniz. Örneğin, sayfa görüntüsünün içeriğini özelleştirmek için aşağıdaki örnek kodu kullanabilirsiniz:

[!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]

*NMessage'ın*her örneğini işlemeniz gerekmediğini unutmayın. Görüntünün bir bileşenini, görüntünün çeşitli bileşenlerini veya tüm alanı işlemeyi seçebilirsiniz.

## <a name="cpagesetupdialogpredrawpage"></a><a name="predrawpage"></a>CPageSetupDialog::PreDrawPage

Yazdırılan bir sayfanın ekran görüntüsünü çizmeden önce çerçeve tarafından çağrılır.

```
virtual UINT PreDrawPage(
    WORD wPaper,
    WORD wFlags,
    LPPAGESETUPDLG pPSD);
```

### <a name="parameters"></a>Parametreler

*wKağıt*<br/>
Kağıt boyutunu gösteren bir değer belirtir. Bu [değer, DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) yapısının açıklamasında listelenen **DMPAPER_** değerlerinden biri olabilir.

*wFlags*<br/>
Kağıdın veya zarfın yönünü ve yazıcının nokta matris mi yoksa HPPCL (Hewlett Packard Printer Control Language) aygıtı olup olmadığını gösterir. Bu parametre aşağıdaki değerlerden birine sahip olabilir:

- Yatay modda 0x001 Kağıt (nokta matrisi)

- 0x003 Yatay modda kağıt (HPPCL)

- 0x005 Dikey modda kağıt (nokta matrisi)

- 0x007 Dikey modda kağıt (HPPCL)

- Yatay modda 0x00b Zarf (HPPCL)

- Portre modunda 0x00d Zarf (nokta matrisi)

- 0x019 Yatay modda zarf (nokta matrisi)

- Portre modunda 0x01f Zarf (nokta matrisi)

*pPSD*<br/>
Bir `PAGESETUPDLG` yapıya işaretçi. [PAGESETUPDLG](/windows/win32/api/commdlg/ns-commdlg-pagesetupdlgw)hakkında daha fazla bilgi için Windows SDK sayfasına bakın.

### <a name="return-value"></a>Dönüş Değeri

Ele alınırsa sıfır olmayan değer; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Görüntünün çizimini özelleştirmek için bu işlevi geçersiz kılın. Bu işlevi geçersiz kılar ve TRUE döndürürseniz, görüntünün tamamını çizmeniz gerekir. Bu işlevi geçersiz kılar ve FALSE döndürürseniz, varsayılan görüntünün tamamı çerçeve tarafından çizilir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog Sınıfı](../../mfc/reference/ccommondialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
