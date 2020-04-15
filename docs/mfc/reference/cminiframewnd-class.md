---
title: CMiniFrameWnd Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMiniFrameWnd
- AFXWIN/CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::Create
- AFXWIN/CMiniFrameWnd::CreateEx
helpviewer_keywords:
- CMiniFrameWnd [MFC], CMiniFrameWnd
- CMiniFrameWnd [MFC], Create
- CMiniFrameWnd [MFC], CreateEx
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
ms.openlocfilehash: e9b91161f4207f4d2215d8777beade93617ddfac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319812"
---
# <a name="cminiframewnd-class"></a>CMiniFrameWnd Sınıfı

Genellikle kayan araç çubuklarının çevresinde görülen yarım yüksekliktebir çerçeve pencereyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CMiniFrameWnd : public CFrameWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMiniFrameWnd::CMiniFrameWnd](#cminiframewnd)|Bir `CMiniFrameWnd` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMiniFrameWnd::Oluştur](#create)|Yapı dan `CMiniFrameWnd` sonra bir nesne oluşturur.|
|[CMiniFrameWnd::CreateEx](#createex)|Yapı dan `CMiniFrameWnd` sonra bir nesne (ek seçeneklerle) oluşturur.|

## <a name="remarks"></a>Açıklamalar

Bu mini çerçeveli pencereler normal çerçeve pencereleri gibi, en aza indirmek / maksimize düğmeleri veya menüler yok ve sadece bunları kapatmak için sistem menüsüne tek tıklamanız dışında.

Bir `CMiniFrameWnd` nesneyi kullanmak için önce nesneyi tanımlayın. Ardından, mini çerçeve penceresini görüntülemek için [Üye Oluştur](#create) işlevini arayın.

Nesnelerin nasıl kullanılacağı `CMiniFrameWnd` hakkında daha fazla bilgi için, [docking ve Kayan Araç Çubukları](../../mfc/docking-and-floating-toolbars.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMiniFrameWnd`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cminiframewndcminiframewnd"></a><a name="cminiframewnd"></a>CMiniFrameWnd::CMiniFrameWnd

Bir `CMiniFrameWnd` nesne oluşturur, ancak pencereoluşturmaz.

```
CMiniFrameWnd();
```

### <a name="remarks"></a>Açıklamalar

Pencereyi oluşturmak için [CMiniFrameWnd'i arayın::Oluştur.](#create)

## <a name="cminiframewndcreate"></a><a name="create"></a>CMiniFrameWnd::Oluştur

Windows mini çerçeve penceresini oluşturur ve `CMiniFrameWnd` nesneye bağlar.

```
virtual BOOL Create(
    LPCTSTR lpClassName,
    LPCTSTR lpWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd = NULL,
    UINT nID = 0);
```

### <a name="parameters"></a>Parametreler

*lpClassName*<br/>
Windows sınıfını isimleyen geçersiz sonlandırılmış karakter dizesini işaret edin. Sınıf adı, global [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) işlevine kayıtlı herhangi bir ad olabilir. NULL durumunda, pencere sınıfı çerçeve tarafından sizin için kaydedilir. MFC varsayılan sınıfa aşağıdaki stilleri ve öznitelikleri verir:

- Kullanıcı fareyi çift tıklattığında pencere yordamına çift tıklatma iletileri gönderen stil biti CS_DBLCLKS ayarlar.

- Stil bitlerini CS_HREDRAW ve CS_VREDRAW ayarlar ve pencere boyutu değiştiğinde istemci alanının içeriğini yeniden çizilecek şekilde yönlendirir.

- Sınıf imlecini Windows standart IDC_ARROW ayarlar.

- Sınıf arka plan fırçasını NULL olarak ayarlar, böylece pencere arka planını silmez.

- Sınıf simgesini standart, sallanan Windows logosu simgesine ayarlar.

- Pencereyi Windows tarafından belirtildiği gibi varsayılan boyuta ve konuma ayarlar.

*lpWindowName*<br/>
Pencere adını içeren null-sonlandırılan karakter dizesini işaret ediyor.

*Dwstyle*<br/>
Pencere stili özniteliklerini belirtir. Bunlar, standart pencere stillerini ve aşağıdaki özel stillerden birini veya birkaçını içerebilir:

- MFS_MOVEFRAME Mini çerçeve penceresinin yalnızca altyazıyı değil, pencerenin herhangi bir kenarına tıklayarak taşınmasına izin verir.

- MFS_4THICKFRAME mini çerçeve penceresinin yeniden boyutlandırılmasını devre dışı kılabilir.

- MFS_SYNCACTIVE Mini çerçeve penceresinin etkinleştirmesini üst penceresinin etkinleştirmesine eşitler.

- MFS_THICKFRAME Mini çerçeve penceresinin istemci alanının içeriğinin izin verdiği kadar küçük boyutlandırılmasına izin verir.

- MFS_BLOCKSYSMENU sistem menüsüne ve denetim menüsüne erişimi devre dışı bırakıp altyazının (başlık çubuğu) bir bölümüne dönüştürür.

[Bkz. CWnd::Olası](../../mfc/reference/cwnd-class.md#create) pencere stili değerlerinin açıklaması için oluştur. Mini çerçeveli pencereler için kullanılan tipik kombinasyon, WS_SYSMENU&#124;WS_CAPTION WS_CAPTION WS_POPUP&#124;.

*Rect*<br/>
Pencerenin istenilen boyutlarını belirten bir `RECT` yapı.

*pParentWnd*<br/>
Üst pencereyi işaret ediyor. Üst düzey pencereler için NULL'u kullanın.

*Nıd*<br/>
Mini çerçeve penceresi alt pencere olarak oluşturulursa, bu alt denetimin tanımlayıcısır; aksi takdirde 0.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`Create`pencerenin sınıf adını ve pencere adını aparat eder ve stili ve üst öğesi için varsayılan değerleri kaydeder.

## <a name="cminiframewndcreateex"></a><a name="createex"></a>CMiniFrameWnd::CreateEx

Bir `CMiniFrameWnd` nesnesi oluşturur.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    LPCTSTR lpClassName,
    LPCTSTR lpWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd = NULL,
    UINT nID = 0);
```

### <a name="parameters"></a>Parametreler

*dwExStyle*<br/>
Oluşturulan `CMiniFrameWnd` genişletilmiş stili belirtir. Genişletilmiş pencere [stillerinden](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) herhangi birini pencereye uygulayın.

*lpClassName*<br/>
Windows sınıfını [(WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) yapısı) isimleyen null-sonlandırılan karakter dizesini işaret eder. Sınıf adı, global [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) işlevine veya önceden tanımlanmış denetim sınıfı adlarından herhangi biriyle kayıtlı herhangi bir ad olabilir. NULL olmamalıdır.

*lpWindowName*<br/>
Pencere adını içeren null-sonlandırılan karakter dizesini işaret ediyor.

*Dwstyle*<br/>
Pencere stili özniteliklerini belirtir. [Bkz. Pencere Stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve [CWnd::Olası](../../mfc/reference/cwnd-class.md#create) değerlerin açıklaması için oluştur.

*Rect*<br/>
Pencerenin boyutu ve konumu, *pParentWnd*istemci koordinatlarında.

*pParentWnd*<br/>
Üst pencere nesnesine işaret ediyor.

*Nıd*<br/>
Çocuk penceresinin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Parametreler, `CreateEx` WNDCLASS'ı, pencere stilini ve (isteğe bağlı olarak) pencerenin başlangıç konumunu ve boyutunu belirtir. `CreateEx`ayrıca pencerenin üst öğesini (varsa) ve kimliğini belirtir.

Yürütüldüğünde, `CreateEx` Windows [WM_GETMINMAXINFO,](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) [WM_NCCREATE,](../../mfc/reference/cwnd-class.md#onnccreate) [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)ve [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) iletileri pencereye gönderir.

Varsayılan ileti işlemeyi genişletmek `CMiniFrameWnd`için, yeni sınıfa bir ileti eşlemi ekleyin ve yukarıdaki iletiler için üye işlevler sağlayın. Geçersiz `OnCreate`kılma , örneğin, yeni bir sınıf için gerekli başlatma gerçekleştirmek için.

Türemiş `On`sınıfınıza daha fazla işlevsellik eklemek için daha fazla *İleti* iletisi işleyicisini geçersiz kılın.

WS_VISIBLE stili verilirse, Windows pencereyi etkinleştirmek ve pencereyi göstermek için gereken tüm iletileri gönderir. Pencere stilinde bir başlık çubuğu belirtilirse, *lpszWindowName* parametresinin işaret ettiği pencere başlığı başlık çubuğunda görüntülenir.

*dwStyle* parametresi [pencere stillerinin](../../mfc/reference/styles-used-by-mfc.md#window-styles)herhangi bir birleşimi olabilir.

Eski stil Palette araç kutusu pencereleri artık desteklenmez. "X" Yakın düğmesi olmayan eski stil, Windows'un önceki sürümlerinde bir MFC uygulaması çalıştırılırken desteklendi, ancak artık Visual C++.NET'te desteklenmiyor. Artık yalnızca yeni WS_EX_TOOLWINDOW tarzı desteklenir; bu stilin açıklaması için [Genişletilmiş Pencere Stilleri'ne](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)
