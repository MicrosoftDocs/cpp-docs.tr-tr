---
title: CMiniFrameWnd sınıfı
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
ms.openlocfilehash: f16a8cd21fe724c44a1ed648f29e42cb5d00dcd1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663322"
---
# <a name="cminiframewnd-class"></a>CMiniFrameWnd sınıfı

Genelde kayan araç çubukları geçici olarak görülen bir yarım yükseklikte pencereyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CMiniFrameWnd : public CFrameWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMiniFrameWnd::CMiniFrameWnd](#cminiframewnd)|Oluşturur bir `CMiniFrameWnd` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMiniFrameWnd::Create](#create)|Oluşturur bir `CMiniFrameWnd` yapım sonra nesne.|
|[CMiniFrameWnd::CreateEx](#createex)|Oluşturur bir `CMiniFrameWnd` yapım sonra (ek seçenekler) nesne.|

## <a name="remarks"></a>Açıklamalar

Bu mini çerçeve pencereleri simge durumuna küçült/Ekranı Kapla düğmeleri olmayan veya menüler ve yalnızca tek tıklamayla bunları kapatmak için sistem menüsünden zorunda dışında normal çerçeve windows gibi davranır.

Kullanılacak bir `CMiniFrameWnd` nesne, nesne ilk tanımlayın. Ardından çağırın [Oluştur](#create) Mini çerçeve penceresini görüntülemek için üye işlevi.

Nasıl kullanılacağı hakkında daha fazla bilgi için `CMiniFrameWnd` nesneleri başlıklı makaleye bakın [Docking ve kayan araç çubukları](../../mfc/docking-and-floating-toolbars.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMiniFrameWnd`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="cminiframewnd"></a>  CMiniFrameWnd::CMiniFrameWnd

Oluşturur bir `CMiniFrameWnd` nesne, ancak pencere oluşturmaz.

```
CMiniFrameWnd();
```

### <a name="remarks"></a>Açıklamalar

Pencere oluşturmak için arama [CMiniFrameWnd::Create](#create).

##  <a name="create"></a>  CMiniFrameWnd::Create

Windows mini çerçeve penceresi oluşturur ve ona ekler `CMiniFrameWnd` nesne.

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
Windows sınıf adları null ile sonlandırılmış dizeye işaret eder. Sınıf adı genel kayıtlı herhangi bir ad olabilir [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) işlevi. Pencere sınıfı NULL ise, sizin için framework tarafından kaydedilir. MFC varsayılan sınıfı aşağıdaki stilleri ve öznitelikleri sağlar:

- Kümeleri stili CS_DBLCLKS hangi gönderimler pencere yordamını iletileri çift tıklayın, bu kullanıcı fare çift tıkladığında, bit.

- Pencere boyutu değiştiğinde çizilmesini istemci alanının içeriği doğrudan CS_HREDRAW ve CS_VREDRAW, stil BITS ayarlar.

- Sınıf imleci Windows standart IDC_ARROW ayarlar.

- Pencere arka planı silme değil şekilde sınıfı arkaplan Fırçası NULL olarak ayarlar.

- Sınıf simgesi standart, el Sallayan bayrağı Windows logo simgesini ayarlar.

- Pencere için varsayılan boyutunu ve konumunu, Windows tarafından belirtildiği gibi ayarlar.

*lpWindowName*<br/>
Pencere adının içeren null ile sonlandırılmış dizeye işaret eder.

*dwStyle*<br/>
Pencere stili özniteliklerini belirtir. Bu, standart pencere stilleri ve bir veya daha fazla özel stilleri aşağıdaki içerebilir:

- MFS_MOVEFRAME yalnızca resim yazısı Pencerenin kenarında tıklayarak taşınacak Mini çerçeve sağlar.

- MFS_4THICKFRAME devre dışı bırakır, Mini çerçeve penceresi yeniden boyutlandırılıyor.

- Mini çerçeve penceresinin üst pencereye etkinleştirme için etkinleştirme MFS_SYNCACTIVE eşitler.

- MFS_THICKFRAME sağlar, Mini çerçeve penceresinin istemci alanını içeriğini küçük boyutta olması için izin verin.

- Sistem menüsü ve denetimi menüsü, erişim MFS_BLOCKSYSMENU devre dışı bırakır ve bunlara açıklamalı alt yazı (başlık çubuğu) bir parçası için dönüştürür.

Bkz: [CWnd::Create](../../mfc/reference/cwnd-class.md#create) olası pencere stili değerleri açıklaması. Mini çerçeve pencereleri için kullanılan tipik WS_POPUP birleşimidir&#124;ws_captıon&#124;WS_SYSMENU.

*Rect*<br/>
A `RECT` yapısı pencerenin istenen boyutlarını belirleme.

*pParentWnd*<br/>
Üst pencere işaret eder. NULL değerini en üst düzey windows için kullanın.

*nID*<br/>
Mini çerçeve penceresinin alt pencere olarak oluşturulursa, alt denetimin tanımlayıcısını budur; Aksi durumda 0.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

`Create` pencere sınıfı adı ve penceresi adı başlatır ve stil ve üst varsayılan değerleri kaydeder.

##  <a name="createex"></a>  CMiniFrameWnd::CreateEx

Oluşturur bir `CMiniFrameWnd` nesne.

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
Genişletilmiş stilini belirtir `CMiniFrameWnd` oluşturuluyor. Atanamadığı [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) penceresine.

*lpClassName*<br/>
Windows sınıf adları null ile sonlandırılmış dizeye işaret (bir [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) yapısı). Sınıf adı genel kayıtlı herhangi bir ad olabilir [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) işlev veya önceden tanımlanmış denetimi-sınıf adları. NULL olmamalıdır.

*lpWindowName*<br/>
Pencere adının içeren null ile sonlandırılmış dizeye işaret eder.

*dwStyle*<br/>
Pencere stili özniteliklerini belirtir. Bkz: [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve [CWnd::Create](../../mfc/reference/cwnd-class.md#create) olası değerlerin bir açıklaması.

*Rect*<br/>
İstemci koordinatları, pencerenin konumunu ve boyutunu *pParentWnd*.

*pParentWnd*<br/>
Ana pencere nesnesi işaret eder.

*nID*<br/>
Alt pencere tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

`CreateEx` Parametreleri WNDCLASS, pencere stili ve (isteğe bağlı olarak) ilk konumunu ve pencere boyutunu belirtin. `CreateEx` Ayrıca pencerenin üst (varsa) ve kimliğini belirtir

Zaman `CreateEx` yürütür, Windows gönderir [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo), [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), ve [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) pencere iletileri.

Varsayılan ileti işleme genişletmek için öğesinden bir sınıf türetin `CMiniFrameWnd`, yeni sınıfa ileti eşlemesi ekleyin ve yukarıdaki iletileri üye işlevleri sağlar. Geçersiz kılma `OnCreate`, örneğin, gerekli başlatma için yeni bir sınıf gerçekleştirmek için.

Daha fazla geçersiz kılma `On` *ileti* ileti işleyicileri, daha fazla türetilmiş sınıfa işlevselliği eklemek için.

Ws_vısıble stili belirtilmezse, Windows penceresi penceresini görüntüleyin ve etkinleştirmek için gereken tüm iletileri gönderir. Pencere stili bir başlık çubuğu belirtiyorsa, pencere başlığı tarafından işaret edilen *lpszWindowName* parametresi, başlık çubuğunda görüntülenir.

*DwStyle* parametresi, herhangi bir birleşimi olabilir [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).

Eski stil palet araç kutusu windows artık desteklenmemektedir. Bir "X" Kapat düğmesi yoktu, eski stil bir MFC uygulaması, Windows, önceki sürümleri üzerinde çalışırken desteklenir, ancak Visual C++ .NET içinde artık desteklenmiyor. Yalnızca yeni ws_ex_toolwındow stil artık desteklenir. Bu stil açıklaması için bkz: [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

## <a name="see-also"></a>Ayrıca Bkz.

[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)
