---
description: 'Daha fazla bilgi edinin: CMiniFrameWnd sınıfı'
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
ms.openlocfilehash: f4cb4b04897a2410d7fb81933e0611dde99e9f8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331609"
---
# <a name="cminiframewnd-class"></a>CMiniFrameWnd sınıfı

Genellikle kayan araç çubukları etrafında görülen yarı yükseklikli bir çerçeve penceresini temsil eder.

## <a name="syntax"></a>Syntax

```
class CMiniFrameWnd : public CFrameWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMiniFrameWnd:: CMiniFrameWnd](#cminiframewnd)|Bir `CMiniFrameWnd` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMiniFrameWnd:: Create](#create)|`CMiniFrameWnd`Oluşturma sonrasında bir nesne oluşturur.|
|[CMiniFrameWnd:: CreateEx](#createex)|`CMiniFrameWnd`Oluşturma işleminden sonra bir nesne (ek seçeneklerle birlikte) oluşturur.|

## <a name="remarks"></a>Açıklamalar

Bu mini çerçeve pencereleri, küçük pencere pencereleri gibi davranır, ancak en aza indirmeler/ekranı kaplamaları ve Menüleri kapatmak için yalnızca sistem menüsüne tek tıklamanın olması gerekir.

Bir nesnesi kullanmak için `CMiniFrameWnd` önce nesneyi tanımlayın. Sonra da mini çerçeve penceresini göstermek için üye [Oluştur](#create) işlevini çağırın.

Nesneleri kullanma hakkında daha fazla bilgi için `CMiniFrameWnd` , bkz. [yerleştirme ve kayan araç çubukları](../../mfc/docking-and-floating-toolbars.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMiniFrameWnd`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cminiframewndcminiframewnd"></a><a name="cminiframewnd"></a> CMiniFrameWnd:: CMiniFrameWnd

Bir `CMiniFrameWnd` nesne oluşturur, ancak pencereyi oluşturmaz.

```
CMiniFrameWnd();
```

### <a name="remarks"></a>Açıklamalar

Pencereyi oluşturmak için [CMiniFrameWnd:: Create](#create)öğesini çağırın.

## <a name="cminiframewndcreate"></a><a name="create"></a> CMiniFrameWnd:: Create

Windows mini çerçeve penceresini oluşturur ve `CMiniFrameWnd` nesneye ekler.

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
Windows sınıfına ad veren null ile sonlandırılmış bir karakter dizesini işaret eder. Sınıf adı, genel [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) işlevine kayıtlı herhangi bir ad olabilir. NULL ise, pencere sınıfı sizin için çerçeve tarafından kaydedilir. MFC varsayılan sınıfa aşağıdaki stilleri ve öznitelikleri verir:

- Kullanıcı fareyle çift tıkladığında pencere yordamına çift tıklama iletileri gönderen stil bit CS_DBLCLKS belirler.

- Pencere boyutunu değiştirdiğinde, istemci alanının içeriğinin yeniden çizilmesini sağlayan stil bitleri CS_HREDRAW ve CS_VREDRAW ayarlar.

- Sınıf imlecini Windows standart IDC_ARROW olarak ayarlar.

- Sınıf arkaplan fırçasını NULL olarak ayarlar, bu nedenle pencere arka planını silmez.

- Sınıf simgesini standart, geri döndürme bayrağı Windows logosu simgesine ayarlar.

- Pencereyi, Windows tarafından belirtildiği gibi varsayılan boyut ve konuma ayarlar.

*lpWindowName*<br/>
Pencere adını içeren, null ile sonlandırılmış bir karakter dizesini işaret eder.

*dwStyle*<br/>
Pencere stili özniteliklerini belirtir. Bunlar, standart pencere stillerini ve aşağıdaki özel stillerden bir veya daha fazlasını içerebilir:

- MFS_MOVEFRAME, Mini kare pencerenin yalnızca başlık değil, pencerenin herhangi bir kenarına tıklanarak taşınmasını sağlar.

- MFS_4THICKFRAME, mini çerçeve penceresinin yeniden boyutlandırılmasını devre dışı bırakır.

- MFS_SYNCACTIVE, mini çerçeve penceresinin etkinleştirmesini, ana penceresinin etkinleştirilmesini eşitler.

- MFS_THICKFRAME, mini çerçeve penceresinin, istemci alanının içerikleri izin verdiğinden küçük olarak boyutlandırılması için izin verir.

- MFS_BLOCKSYSMENU, sistem menüsüne ve denetim menüsüne erişimi devre dışı bırakır ve bunları başlığın (başlık çubuğu) bir bölümüne dönüştürür.

Olası pencere stili değerlerinin açıklaması için bkz. [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) . Küçük çerçeve pencereleri için kullanılan tipik birleşim,&#124;WS_SYSMENU WS_CAPTION&#124;WS_POPUP.

*Rect*<br/>
`RECT`Pencerenin istenen boyutlarını belirten bir yapı.

*pParentWnd*<br/>
Üst pencereyi işaret eder. Üst düzey pencereler için NULL kullanın.

*NID*<br/>
Mini çerçeve penceresi bir alt pencere olarak oluşturulduysa, bu, alt denetimin tanımlayıcısıdır; Aksi takdirde 0.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`Create` pencerenin sınıf adını ve pencere adını başlatır ve stili ve üst öğesi için varsayılan değerleri kaydeder.

## <a name="cminiframewndcreateex"></a><a name="createex"></a> CMiniFrameWnd:: CreateEx

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
Oluşturulmakta olan genişletilmiş stilini belirtir `CMiniFrameWnd` . Penceredeki [genişletilmiş pencere stillerinden](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) birini uygulayın.

*lpClassName*<br/>
Windows sınıfına ( [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) yapısı) ad veren null ile sonlandırılmış bir karakter dizesini işaret eder. Sınıf adı, genel [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) işlevine veya önceden tanımlanmış denetim sınıfı adlarından herhangi birine kayıtlı herhangi bir ad olabilir. NULL olmaması gerekir.

*lpWindowName*<br/>
Pencere adını içeren, null ile sonlandırılmış bir karakter dizesini işaret eder.

*dwStyle*<br/>
Pencere stili özniteliklerini belirtir. Olası değerlerin açıklaması için bkz. [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) .

*Rect*<br/>
Pencerenin, *pParentWnd* istemci koordinatlarındaki boyutu ve konumu.

*pParentWnd*<br/>
Üst pencere nesnesine işaret eder.

*NID*<br/>
Alt pencerenin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`CreateEx`Parametreler WNDCLASS, pencere stili ve (isteğe bağlı olarak) pencerenin başlangıç konumunu ve boyutunu belirtir. `CreateEx` Ayrıca pencerenin üst öğesini (varsa) ve KIMLIĞINI belirtir.

`CreateEx`Yürütüldüğünde, Windows [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo), [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)ve [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) iletilerini pencereye gönderir.

Varsayılan ileti işlemeyi genişletmek için, öğesinden bir sınıf türetebilir `CMiniFrameWnd` , yeni sınıfa bir ileti haritası ekleyin ve yukarıdaki iletiler için üye işlevleri sağlayın. `OnCreate`Yeni bir sınıf için gerekli başlatmayı gerçekleştirmek üzere, örneğin, öğesini geçersiz kılın.

`On`Türetilmiş sınıfınıza daha fazla işlevsellik eklemek için diğer *ileti* ileti işleyicilerini geçersiz kılın.

WS_VISIBLE stil verilirse Windows, pencereyi etkinleştirmek ve göstermek için gereken tüm iletileri gönderir. Pencere stili bir başlık çubuğu belirtiyorsa, *lpszWindowName* parametresi tarafından işaret edilen pencere başlığı başlık çubuğunda görüntülenir.

*DwStyle* parametresi [pencere stillerinin](../../mfc/reference/styles-used-by-mfc.md#window-styles)herhangi bir birleşimi olabilir.

Eski stil paleti araç kutusu pencereleri artık desteklenmiyor. Bir "X" Close düğmesine sahip olmayan eski stil, Windows 'un önceki sürümlerinde bir MFC uygulaması çalıştırılırken desteklenir, ancak artık Visual C++ .NET sürümünde desteklenmiyordur. Yalnızca yeni WS_EX_TOOLWINDOW stili artık desteklenmektedir; Bu stilin açıklaması için bkz. [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

## <a name="see-also"></a>Ayrıca bkz.

[CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)
