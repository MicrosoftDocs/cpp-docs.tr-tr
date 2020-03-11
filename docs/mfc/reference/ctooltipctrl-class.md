---
title: CToolTipCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CToolTipCtrl
- AFXCMN/CToolTipCtrl
- AFXCMN/CToolTipCtrl::CToolTipCtrl
- AFXCMN/CToolTipCtrl::Activate
- AFXCMN/CToolTipCtrl::AddTool
- AFXCMN/CToolTipCtrl::AdjustRect
- AFXCMN/CToolTipCtrl::Create
- AFXCMN/CToolTipCtrl::CreateEx
- AFXCMN/CToolTipCtrl::DelTool
- AFXCMN/CToolTipCtrl::GetBubbleSize
- AFXCMN/CToolTipCtrl::GetCurrentTool
- AFXCMN/CToolTipCtrl::GetDelayTime
- AFXCMN/CToolTipCtrl::GetMargin
- AFXCMN/CToolTipCtrl::GetMaxTipWidth
- AFXCMN/CToolTipCtrl::GetText
- AFXCMN/CToolTipCtrl::GetTipBkColor
- AFXCMN/CToolTipCtrl::GetTipTextColor
- AFXCMN/CToolTipCtrl::GetTitle
- AFXCMN/CToolTipCtrl::GetToolCount
- AFXCMN/CToolTipCtrl::GetToolInfo
- AFXCMN/CToolTipCtrl::HitTest
- AFXCMN/CToolTipCtrl::Pop
- AFXCMN/CToolTipCtrl::Popup
- AFXCMN/CToolTipCtrl::RelayEvent
- AFXCMN/CToolTipCtrl::SetDelayTime
- AFXCMN/CToolTipCtrl::SetMargin
- AFXCMN/CToolTipCtrl::SetMaxTipWidth
- AFXCMN/CToolTipCtrl::SetTipBkColor
- AFXCMN/CToolTipCtrl::SetTipTextColor
- AFXCMN/CToolTipCtrl::SetTitle
- AFXCMN/CToolTipCtrl::SetToolInfo
- AFXCMN/CToolTipCtrl::SetToolRect
- AFXCMN/CToolTipCtrl::SetWindowTheme
- AFXCMN/CToolTipCtrl::Update
- AFXCMN/CToolTipCtrl::UpdateTipText
helpviewer_keywords:
- CToolTipCtrl [MFC], CToolTipCtrl
- CToolTipCtrl [MFC], Activate
- CToolTipCtrl [MFC], AddTool
- CToolTipCtrl [MFC], AdjustRect
- CToolTipCtrl [MFC], Create
- CToolTipCtrl [MFC], CreateEx
- CToolTipCtrl [MFC], DelTool
- CToolTipCtrl [MFC], GetBubbleSize
- CToolTipCtrl [MFC], GetCurrentTool
- CToolTipCtrl [MFC], GetDelayTime
- CToolTipCtrl [MFC], GetMargin
- CToolTipCtrl [MFC], GetMaxTipWidth
- CToolTipCtrl [MFC], GetText
- CToolTipCtrl [MFC], GetTipBkColor
- CToolTipCtrl [MFC], GetTipTextColor
- CToolTipCtrl [MFC], GetTitle
- CToolTipCtrl [MFC], GetToolCount
- CToolTipCtrl [MFC], GetToolInfo
- CToolTipCtrl [MFC], HitTest
- CToolTipCtrl [MFC], Pop
- CToolTipCtrl [MFC], Popup
- CToolTipCtrl [MFC], RelayEvent
- CToolTipCtrl [MFC], SetDelayTime
- CToolTipCtrl [MFC], SetMargin
- CToolTipCtrl [MFC], SetMaxTipWidth
- CToolTipCtrl [MFC], SetTipBkColor
- CToolTipCtrl [MFC], SetTipTextColor
- CToolTipCtrl [MFC], SetTitle
- CToolTipCtrl [MFC], SetToolInfo
- CToolTipCtrl [MFC], SetToolRect
- CToolTipCtrl [MFC], SetWindowTheme
- CToolTipCtrl [MFC], Update
- CToolTipCtrl [MFC], UpdateTipText
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
ms.openlocfilehash: bf32671eb3535de1bf072e24bc642145e87c84ee
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865462"
---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl sınıfı

Bir uygulamada aracın amacını açıklayan tek satırlık bir metin görüntüleyen küçük bir açılan pencere olan "araç ipucu denetimi" işlevselliğini Kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CToolTipCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CToolTipCtrl:: CToolTipCtrl](#ctooltipctrl)|`CToolTipCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CToolTipCtrl:: Activate](#activate)|Araç ipucu denetimini etkinleştirir ve devre dışı bırakır.|
|[CToolTipCtrl:: AddTool](#addtool)|Araç ipucu denetimiyle bir araç kaydeder.|
|[CToolTipCtrl:: AdjustRect](#adjustrect)|Araç ipucu denetiminin metin görüntüleme dikdörtgeni ve Pencere dikdörtgeni arasında dönüştürür.|
|[CToolTipCtrl:: Create](#create)|Bir araç ipucu denetimi oluşturur ve bunu bir `CToolTipCtrl` nesnesine iliştirir.|
|[CToolTipCtrl:: CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir araç ipucu denetimi oluşturur ve bunu bir `CToolTipCtrl` nesnesine ekler.|
|[CToolTipCtrl::D elTool](#deltool)|Araç ipucu denetiminden bir araç kaldırır.|
|[CToolTipCtrl:: GetBubbleSize](#getbubblesize)|Araç ipucunun boyutunu alır.|
|[CToolTipCtrl:: GetCurrentTool](#getcurrenttool)|Geçerli araç ipucu denetiminin görüntülediği araç ipucu penceresinin boyut, konum ve metin gibi bilgileri alır.|
|[CToolTipCtrl:: GetDelayTime](#getdelaytime)|Şu anda bir araç ipucu denetimi için ayarlanmış olan başlangıç, açılır ve yeniden başlatma sürelerini alır.|
|[CToolTipCtrl:: GetMargin](#getmargin)|Bir araç ipucu penceresi için ayarlanan üst, sol, alt ve sağ kenar boşluklarını alır.|
|[CToolTipCtrl:: GetMaxTipWidth](#getmaxtipwidth)|Bir araç ipucu penceresi için en büyük genişliği alır.|
|[CToolTipCtrl:: GetText](#gettext)|Araç ipucu denetiminin bir araç için sakladığı metni alır.|
|[CToolTipCtrl:: GetTipBkColor](#gettipbkcolor)|Araç İpucu penceresinde arka plan rengini alır.|
|[CToolTipCtrl:: GetTipTextColor](#gettiptextcolor)|Araç İpucu penceresinde metin rengini alır.|
|[CToolTipCtrl:: GetTitle](#gettitle)|Geçerli araç ipucu denetiminin başlığını alır.|
|[CToolTipCtrl:: GetToolCount](#gettoolcount)|Araç ipucu denetimi tarafından tutulan araçların sayısını alır.|
|[CToolTipCtrl:: GetToolInfo](#gettoolinfo)|Araç ipucu denetiminin bir araç hakkında koruduğu bilgileri alır.|
|[CToolTipCtrl:: HitTest](#hittest)|Belirlenen aracın sınırlayıcı dikdörtgeni içinde olup olmadığını anlamak için bir noktayı sınar. Varsa, araçla ilgili bilgileri alır.|
|[CToolTipCtrl::P op](#pop)|Görüntülenmiş bir araç ipucu penceresini görünümden kaldırır.|
|[CToolTipCtrl::P opup](#popup)|Geçerli araç Ipucu denetiminin son fare iletisinin koordinatlarına göre görüntülenmesine neden olur.|
|[CToolTipCtrl:: RelayEvent](#relayevent)|İşleme için bir fare iletisini bir araç ipucu denetimine geçirir.|
|[CToolTipCtrl:: SetDelayTime](#setdelaytime)|Araç ipucu denetimi için başlangıç, açılır ve yeniden süreleri ayarlar.|
|[CToolTipCtrl:: SetMargin](#setmargin)|Araç ipucu penceresi için üst, sol, alt ve sağ kenar boşluklarını ayarlar.|
|[CToolTipCtrl:: SetMaxTipWidth](#setmaxtipwidth)|Bir araç ipucu penceresi için en büyük genişliği ayarlar.|
|[CToolTipCtrl:: SetTipBkColor](#settipbkcolor)|Araç İpucu penceresinde arka plan rengini ayarlar.|
|[CToolTipCtrl:: SetTipTextColor](#settiptextcolor)|Bir araç ipucu penceresinde metin rengini ayarlar.|
|[CToolTipCtrl:: SetTitle](#settitle)|Araç ipucuna standart bir simge ve başlık dizesi ekler.|
|[CToolTipCtrl:: SetToolInfo](#settoolinfo)|Bir araç ipucunun bir araç için sakladığı bilgileri ayarlar.|
|[CToolTipCtrl:: SetToolRect](#settoolrect)|Araç için yeni bir sınırlayıcı dikdörtgen ayarlar.|
|[CToolTipCtrl:: SetWindowTheme](#setwindowtheme)|Araç ipucu penceresinin görsel stilini ayarlar.|
|[CToolTipCtrl:: Update](#update)|Geçerli aracın yeniden çizilmesini zorlar.|
|[CToolTipCtrl:: UpdateTipText](#updatetiptext)|Araç için araç ipucu metnini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir "araç", bir pencerenin istemci alanındaki bir pencere veya denetim ya da uygulama tanımlı dikdörtgen alanı gibi bir pencere olur. Bir araç ipucu, yalnızca Kullanıcı imleci bir araç üzerine yerleştirdiği ve yaklaşık bir yarı yarım saniye boyunca ayrıldığında görüntülenen zaman gizli bir araç. Araç ipucu imlecin yakınında görünür ve Kullanıcı fare düğmesine tıkladığında veya imleci aracın dışına taşırken kaybolur.

`CToolTipCtrl`, araç ipucunun başlangıç saatini ve süresini, araç ipucu metnini çevreleyen kenar boşluğu genişliklerini, araç ipucu penceresinin genişliğini ve araç ipucunun arka plan ve metin rengini denetlemek için işlevsellik sağlar. Tek bir araç ipucu denetimi, birden fazla araç için bilgi sağlayabilir.

`CToolTipCtrl` sınıfı, Windows ortak araç ipucu denetiminin işlevlerini sağlar. Bu denetim (ve bu nedenle `CToolTipCtrl` sınıfı) yalnızca Windows 95/98 ve Windows NT sürümleri 3,51 ve üzeri sürümlerde çalışan programlar için kullanılabilir.

Araç ipuçlarını etkinleştirme hakkında daha fazla bilgi için bkz. [Windows 'Daki araç Ipuçları CFrameWnd 'Den türetilmemiş](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).

`CToolTipCtrl`kullanma hakkında daha fazla bilgi için bkz. [. ve](../../mfc/controls-mfc.md) [CToolTipCtrl kullanma](../../mfc/using-ctooltipctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CToolTipCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

##  <a name="activate"></a>CToolTipCtrl:: Activate

Araç ipucu denetimini etkinleştirmek veya devre dışı bırakmak için bu işlevi çağırın.

```
void Activate(BOOL bActivate);
```

### <a name="parameters"></a>Parametreler

*Bacetkinleştir*<br/>
Araç ipucu denetiminin etkinleştirileceğini veya devre dışı bırakılıp başlatılmayacağını belirtir.

### <a name="remarks"></a>Açıklamalar

*Bacaktive* doğru ise, denetim etkinleştirilir; YANLıŞSA, devre dışı bırakılır.

Bir araç ipucu denetimi etkin olduğunda, imleç denetimle kaydedilen bir araç üzerindeyken araç ipucu bilgileri görüntülenir; etkin olmadığında, imleç bir araç üzerindeyken bile araç ipucu bilgileri görünmez.

### <a name="example"></a>Örnek

  [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)örneğine bakın.

##  <a name="addtool"></a>CToolTipCtrl:: AddTool

Araç ipucu denetimiyle bir araç kaydeder.

```
BOOL AddTool(
    CWnd* pWnd,
    UINT nIDText,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);

BOOL AddTool(
    CWnd* pWnd,
    LPCTSTR lpszText = LPSTR_TEXTCALLBACK,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Aracı içeren pencerenin işaretçisi.

*Nıdtext*<br/>
Aracın metnini içeren dize kaynağının KIMLIĞI.

*lpRectTool*<br/>
Aracın sınırlayıcı dikdörtgeninin koordinatlarını içeren bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına yönelik işaretçi. Koordinatlar, *pWnd*tarafından tanımlanan pencerenin istemci alanının sol üst köşesine göre belirlenir.

*nIDTool*<br/>
Aracın KIMLIĞI.

*lpszText*<br/>
Araç için metin işaretçisi. Bu parametre LPSTR_TEXTCALLBACK değerini içeriyorsa, TTN_NEEDTEXT bildirim iletileri, ' *ın gösterdiği pencerenin* üst öğesine gider.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*LpRectTool* ve *nIDTool* parametrelerinin her ikisi de geçerli olmalıdır veya *lpRectTool* null ise *nIDTool* 0 olmalıdır.

Bir araç ipucu denetimi, birden fazla araçla ilişkilendirilebilir. Araç ipucu denetimi ile bir araç kaydettirmek için bu işlevi çağırın, böylece araç ipucunda depolanan bilgiler imleç araç üzerindeyken görüntülenir.

> [!NOTE]
>  `AddTool`kullanarak bir araç ipucunu statik denetime ayarlayamazsınız.

### <a name="example"></a>Örnek

  [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)örneğine bakın.

##  <a name="adjustrect"></a>CToolTipCtrl:: AdjustRect

Araç ipucu denetiminin metin görüntüleme dikdörtgeni ve Pencere dikdörtgeni arasında dönüştürür.

```
BOOL AdjustRect(
    LPRECT lprc,
    BOOL bLarger = TRUE);
```

### <a name="parameters"></a>Parametreler

*LPRC*<br/>
Bir araç ipucu penceresi dikdörtgeni ya da metin görüntüleme dikdörtgeni tutan bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına yönelik işaretçi.

*bDaha büyük*<br/>
TRUE ise, bir metin görüntüleme dikdörtgeni belirtmek için *lprc* kullanılır ve ilgili pencere dikdörtgenini alır. YANLıŞSA, bir pencere dikdörtgeni belirtmek için *lprc* kullanılır ve ilgili metin görüntüleme dikdörtgenini alır.

### <a name="return-value"></a>Dönüş Değeri

Dikdörtgen başarıyla ayarlandıktan sonra sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, bir araç ipucu denetiminin metin görüntüleme dikdörtgenini pencere dikdörtgenden veya belirli bir metin görüntüleme dikdörtgeni görüntülemesi gereken araç ipucu penceresi dikdörtgeninin bir görüntüsünü hesaplar.

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TTM_ADJUSTRECT](/windows/win32/Controls/ttm-adjustrect)davranışını uygular.

##  <a name="create"></a>CToolTipCtrl:: Create

Bir araç ipucu denetimi oluşturur ve bunu bir `CToolTipCtrl` nesnesine iliştirir.

```
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Araç ipucu denetiminin üst penceresini, genellikle bir `CDialog`belirtir. NULL olmaması gerekir.

*dwStyle*<br/>
Araç ipucu denetiminin stilini belirtir. Daha fazla bilgi için **açıklamalar** bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

`CToolTipCtrl` nesnesi başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CToolTipCtrl` iki adımda oluşturursunuz. İlk olarak, `CToolTipCtrl` nesnesini oluşturmak için oluşturucuyu çağırın ve sonra araç ipucu denetimini oluşturmak ve `CToolTipCtrl` nesnesine eklemek için `Create` çağırın.

*DwStyle* parametresi [pencere stillerinin](../../mfc/reference/styles-used-by-mfc.md#window-styles)herhangi bir birleşimi olabilir. Ayrıca, bir araç ipucu denetiminde sınıfa özgü iki stil vardır: TTS_ALWAYSTIP ve TTS_NOPREFIX.

|Stil|Anlamı|
|-----------|-------------|
|TTS_ALWAYSTIP|Araç ipucu denetiminin sahip penceresinin etkin veya devre dışı olmasına bakılmaksızın, imleç bir araç üzerindeyken araç ipucunun görüneceğini belirtir. Bu stil olmadan araç ipucu denetimi, aracın sahip penceresi etkin olduğunda, ancak etkin olmadığında görünmez.|
|TTS_NOPREFIX|Bu stil, sistemin bir dizeden ampersan (&) karakterini almasını engeller. Bir araç ipucu denetiminin TTS_NOPREFIX stili yoksa, sistem ve bir uygulamanın aynı dizeyi bir menü öğesi ile aynı dizeyi ve araç ipucu denetiminde metin olarak kullanmasına izin vererek, sistem, ve karakterlerini otomatik olarak kaldırır.|

Araç ipucu denetimi, denetimi oluştururken belirttiğinize bakılmaksızın WS_POPUP ve WS_EX_TOOLWINDOW pencere stillerine sahiptir.

Genişletilmiş Windows stilleriyle bir araç ipucu denetimi oluşturmak için `Create`yerine [CToolTipCtrl:: CreateEx](#createex) çağırın.

### <a name="example"></a>Örnek

  [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)örneğine bakın.

##  <a name="createex"></a>CToolTipCtrl:: CreateEx

Bir denetim (alt pencere) oluşturur ve `CToolTipCtrl` nesnesiyle ilişkilendirir.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwStyle = 0,
    DWORD dwStyleEx = 0);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Denetimin üst öğesi olan pencerenin işaretçisi.

*dwStyle*<br/>
Araç ipucu denetiminin stilini belirtir. Daha fazla bilgi için bkz. [oluşturma](#create) konusunun **açıklamalar** bölümü.

*dwStyleEx*<br/>
Oluşturulmakta olan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerinin listesi için, Windows SDK için bkz. [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) Için *dwExStyle* parametresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır değilse 0.

### <a name="remarks"></a>Açıklamalar

Windows genişletilmiş stil ön yüzü **ws_ex_** tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için `Create` yerine `CreateEx` kullanın.

##  <a name="ctooltipctrl"></a>CToolTipCtrl:: CToolTipCtrl

`CToolTipCtrl` nesnesi oluşturur.

```
CToolTipCtrl();
```

### <a name="remarks"></a>Açıklamalar

Nesnesini oluşturduktan sonra `Create` çağırmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]

##  <a name="deltool"></a>CToolTipCtrl::D elTool

Bir araç ipucu denetimi tarafından desteklenen araçlar koleksiyonundan *pWnd* ve *nIDTool* tarafından belirtilen aracı kaldırır.

```
void DelTool(
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Aracı içeren pencerenin işaretçisi.

*nIDTool*<br/>
Aracın KIMLIĞI.

##  <a name="getbubblesize"></a>CToolTipCtrl:: GetBubbleSize

Araç ipucunun boyutunu alır.

```
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Parametreler

*lpToolInfo*<br/>
Araç ipucunun [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Araç ipucunun boyutu.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TTM_GETBUBBLESIZE](/windows/win32/Controls/ttm-getbubblesize)davranışını uygular.

##  <a name="getcurrenttool"></a>CToolTipCtrl:: GetCurrentTool

Geçerli araç ipucu denetimi tarafından gösterilen araç ipucu penceresinin boyut, konum ve metin gibi bilgileri alır.

```
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*lpToolInfo*|dışı Geçerli araç ipucu penceresi hakkında bilgi alan [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) yapısına yönelik işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Bilgiler başarıyla alınırsa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [TTM_GETCURRENTTOOL](/windows/win32/Controls/ttm-getcurrenttool) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli araç ipucu penceresi hakkındaki bilgileri alır.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]

##  <a name="getdelaytime"></a>CToolTipCtrl:: GetDelayTime

Bir araç ipucu denetimi için ilk, açılan ve daha sonra belirlenen süreleri alır.

```
int GetDelayTime(DWORD dwDuration) const;
```

### <a name="parameters"></a>Parametreler

*dwDuration*<br/>
Hangi süre değerinin alınacağını belirten bayrak. Bu parametre aşağıdaki değerlerden biri olabilir:

- TTDT_AUTOPOP, işaretçinin bir aracın sınırlayıcı dikdörtgeni içinde sabit olması durumunda araç ipucu penceresinin görünür kalacağı sürenin uzunluğunu alma.

- Araç ipucu penceresi görüntülenmeden önce bir aracın sınırlayıcı dikdörtgeni içinde işaretçinin sabit kalması gereken sürenin uzunluğunu almak TTDT_INITIAL.

- TTDT_RESHOW, işaretçi bir araçtan diğerine taşındığı sırada sonraki araç ipucu pencerelerinin görünmesi için gereken sürenin uzunluğunu alır.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen gecikme süresi (milisaniye)

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TTM_GETDELAYTIME](/windows/win32/Controls/ttm-getdelaytime)davranışını uygular.

##  <a name="getmargin"></a>CToolTipCtrl:: GetMargin

Araç ipucu penceresi için üst, sol, alt ve sağ kenar boşluğu kümesini alır.

```
void GetMargin(LPRECT lprc) const;
```

### <a name="parameters"></a>Parametreler

*LPRC*<br/>
Kenar boşluğu bilgilerini alacak `RECT` yapısının adresi. [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısının üyeleri bir sınırlayıcı dikdörtgen tanımlamaz. Bu iletinin amacı için yapı üyeleri aşağıdaki gibi yorumlanır:

|Üye|İmle|
|------------|--------------------|
|`top`|En üst sınır ve araç ipucu metninin üst ve piksel cinsinden uzaklığı.|
|`left`|Sol kenarlık ve ipucu metninin sol ucu arasındaki uzaklık (piksel cinsinden).|
|`bottom`|Alt kenarlık ve ipucu metninin alt kenar arasındaki mesafe (piksel cinsinden).|
|`right`|Sağ kenarlık ve ipucu metninin sağ ucu arasındaki uzaklık (piksel cinsinden).|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TTM_GETMARGIN](/windows/win32/Controls/ttm-getmargin)davranışını uygular.

##  <a name="getmaxtipwidth"></a>CToolTipCtrl:: GetMaxTipWidth

Bir araç ipucu penceresi için en büyük genişliği alır.

```
int GetMaxTipWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir araç ipucu penceresi için maksimum genişlik.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TTM_GETMAXTIPWIDTH](/windows/win32/Controls/ttm-getmaxtipwidth)davranışını uygular.

##  <a name="gettext"></a>CToolTipCtrl:: GetText

Araç ipucu denetiminin bir araç için sakladığı metni alır.

```
void GetText(
    CString& str,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
Aracın metnini alan `CString` nesnesine başvuru.

*pWnd*<br/>
Aracı içeren pencerenin işaretçisi.

*nIDTool*<br/>
Aracın KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

*PWnd* ve *nIDTool* parametreleri, aracı belirler. Bu araç daha önce `CToolTipCtrl::AddTool`önceki bir çağrısıyla araç ipucu denetimiyle kaydedilmişse, *Str* parametresi tarafından başvurulan nesne araç metnine atanır.

##  <a name="gettipbkcolor"></a>CToolTipCtrl:: GetTipBkColor

Araç İpucu penceresinde arka plan rengini alır.

```
COLORREF GetTipBkColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arka plan rengini temsil eden [colorref](/windows/win32/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TTM_GETTIPBKCOLOR](/windows/win32/Controls/ttm-gettipbkcolor)davranışını uygular.

##  <a name="gettiptextcolor"></a>CToolTipCtrl:: GetTipTextColor

Araç İpucu penceresinde metin rengini alır.

```
COLORREF GetTipTextColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Metin rengini temsil eden bir [colorref](/windows/win32/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TTM_GETTIPTEXTCOLOR](/windows/win32/Controls/ttm-gettiptextcolor)davranışını uygular.

##  <a name="gettitle"></a>CToolTipCtrl:: GetTitle

Geçerli araç ipucu denetiminin başlığını alır.

```
void GetTitle(PTTGETTITLE pttgt) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pttgt*|dışı Araç Ipucu denetimiyle ilgili bilgileri içeren bir [Ttgettitle](/windows/win32/api/commctrl/ns-commctrl-ttgettitle) yapısına yönelik işaretçi. Bu yöntem döndüğünde, [Ttgettitle](/windows/win32/api/commctrl/ns-commctrl-ttgettitle) yapısının *pszTitle* üyesi, başlığın metnini işaret eder.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [TTM_GETTITLE](/windows/win32/Controls/ttm-gettitle) iletisini gönderir.

##  <a name="gettoolcount"></a>CToolTipCtrl:: GetToolCount

Araç ipucu denetimiyle kaydedilen araçların sayısını alır.

```
int GetToolCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Araç ipucu denetimine kayıtlı bir araç sayısı.

##  <a name="gettoolinfo"></a>CToolTipCtrl:: GetToolInfo

Araç ipucu denetiminin bir araç hakkında koruduğu bilgileri alır.

```
BOOL GetToolInfo(
    CToolInfo& ToolInfo,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>Parametreler

*TOOLINFO*<br/>
Aracın metnini alan `TOOLINFO` nesnesine başvuru.

*pWnd*<br/>
Aracı içeren pencerenin işaretçisi.

*nIDTool*<br/>
Aracın KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) yapısının `hwnd` ve `uId` üyeleri, *CToolInfo* tarafından başvurulan, aracı belirler. Bu araç, önceki bir `AddTool`çağrısıyla araç ipucu denetimiyle kaydedilmişse, `TOOLINFO` yapısı araçla ilgili bilgilerle doldurulur.

##  <a name="hittest"></a>CToolTipCtrl:: HitTest

Bir noktayı, belirtilen aracın sınırlayıcı dikdörtgeni içinde olup olmadığını ve bu durumda araç hakkında bilgi almayı anlamak için sınar.

```
BOOL HitTest(
    CWnd* pWnd,
    CPoint pt,
    LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Aracı içeren pencerenin işaretçisi.

*yönergelerinin*<br/>
Sınanacak noktanın koordinatlarını içeren `CPoint` nesnesine yönelik işaretçi.

*lpToolInfo*<br/>
Araç hakkında bilgi içeren [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İsabet-test bilgileri tarafından belirtilen nokta aracın sınırlayıcı dikdörtgeni içindeyse sıfır dışı olur; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, sıfır dışında bir değer döndürürse, *lpToolInfo* tarafından işaret edilen yapı, dikdörtgeni işaret eden dikdörtgenin içindeki bilgilerle doldurulur.

`TTHITTESTINFO` yapısı aşağıdaki gibi tanımlanır:

```cpp
typedef struct _TT_HITTESTINFO { // tthti
    HWND hwnd;   // handle of tool or window with tool
    POINT pt;    // client coordinates of point to test
    TOOLINFO ti; // receives information about the tool
} TTHITTESTINFO, FAR * LPHITTESTINFO;
```

- `hwnd`

   Aracın tanıtıcısını belirtir.

- `pt`

   Nokta aracın sınırlayıcı dikdörtgeninde ise bir noktanın koordinatlarını belirtir.

- `ti`

   Araçla ilgili bilgiler. `TOOLINFO` yapısı hakkında daha fazla bilgi için bkz. [CToolTipCtrl:: GetToolInfo](#gettoolinfo).

##  <a name="pop"></a>CToolTipCtrl::P op

Görüntülenmiş bir araç ipucu penceresini görünümden kaldırır.

```
void Pop();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TTM_POP](/windows/win32/Controls/ttm-pop)davranışını uygular.

##  <a name="popup"></a>CToolTipCtrl::P opup

Geçerli araç ipucu denetiminin son fare iletisinin koordinatlarına göre görüntülenmesine neden olur.

```
void Popup();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [TTM_POPUP](/windows/win32/Controls/ttm-popup) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği bir araç ipucu penceresi görüntüler.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]

##  <a name="relayevent"></a>CToolTipCtrl:: RelayEvent

İşleme için bir fare iletisini bir araç ipucu denetimine geçirir.

```
void RelayEvent(LPMSG lpMsg);
```

### <a name="parameters"></a>Parametreler

*lpMsg*<br/>
Geçiş yapılacak iletiyi içeren bir [msg](/windows/win32/api/winuser/ns-winuser-msg) yapısına yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Araç ipucu denetimi yalnızca `RelayEvent`tarafından kendisine gönderilen aşağıdaki iletileri işler:

|WM_LBUTTONDOWN|WM_MOUSEMOVE|
|---------------------|-------------------|
|WM_LBUTTONUP|WM_RBUTTONDOWN|
|WM_MBUTTONDOWN|WM_RBUTTONUP|
|WM_MBUTTONUP||

### <a name="example"></a>Örnek

  [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)örneğine bakın.

##  <a name="setdelaytime"></a>CToolTipCtrl:: SetDelayTime

Araç ipucu denetiminin gecikme süresini ayarlar.

```
void SetDelayTime(UINT nDelay);

void SetDelayTime(
    DWORD dwDuration,
    int iTime);
```

### <a name="parameters"></a>Parametreler

*nDelay*<br/>
Yeni gecikme süresini milisaniye olarak belirtir.

*dwDuration*<br/>
Hangi süre değerinin alınacağını belirten bayrak. Geçerli değerlerin açıklaması için bkz. [CToolTipCtrl:: GetDelayTime](#getdelaytime) .

*ıtime*<br/>
Belirtilen gecikme süresi (milisaniye cinsinden).

### <a name="remarks"></a>Açıklamalar

Gecikme süresi, araç ipucu penceresi görüntülenmeden önce imlecin bir araç üzerinde kalması gereken süredir. Varsayılan gecikme süresi 500 milisaniyedir.

##  <a name="setmargin"></a>CToolTipCtrl:: SetMargin

Araç ipucu penceresi için üst, sol, alt ve sağ kenar boşluklarını ayarlar.

```
void SetMargin(LPRECT lprc);
```

### <a name="parameters"></a>Parametreler

*LPRC*<br/>
Ayarlanacak kenar boşluğu bilgilerini içeren `RECT` yapısının adresi. `RECT` yapısının üyeleri bir sınırlayıcı dikdörtgen tanımlamaz. Kenar boşluğu bilgilerinin açıklaması için bkz. [CToolTipCtrl:: GetMargin](#getmargin) .

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TTM_SETMARGIN](/windows/win32/Controls/ttm-setmargin)davranışını uygular.

##  <a name="setmaxtipwidth"></a>CToolTipCtrl:: SetMaxTipWidth

Bir araç ipucu penceresi için en büyük genişliği ayarlar.

```
int SetMaxTipWidth(int iWidth);
```

### <a name="parameters"></a>Parametreler

*ıwidth*<br/>
Ayarlanacak en büyük araç ipucu pencere genişliği.

### <a name="return-value"></a>Dönüş Değeri

Önceki en yüksek ipucu genişliği.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TTM_SETMAXTIPWIDTH](/windows/win32/Controls/ttm-setmaxtipwidth)davranışını uygular.

##  <a name="settipbkcolor"></a>CToolTipCtrl:: SetTipBkColor

Araç İpucu penceresinde arka plan rengini ayarlar.

```
void SetTipBkColor(COLORREF clr);
```

### <a name="parameters"></a>Parametreler

*clr*<br/>
Yeni arka plan rengi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TTM_SETTIPBKCOLOR](/windows/win32/Controls/ttm-settipbkcolor)davranışını uygular.

##  <a name="settiptextcolor"></a>CToolTipCtrl:: SetTipTextColor

Bir araç ipucu penceresinde metin rengini ayarlar.

```
void SetTipTextColor(COLORREF clr);
```

### <a name="parameters"></a>Parametreler

*clr*<br/>
Yeni metin rengi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TTM_SETTIPTEXTCOLOR](/windows/win32/Controls/ttm-settiptextcolor)davranışını uygular.

##  <a name="settitle"></a>CToolTipCtrl:: SetTitle

Araç ipucuna standart bir simge ve başlık dizesi ekler.

```
BOOL SetTitle(
    UINT uIcon,
    LPCTSTR lpstrTitle);
```

### <a name="parameters"></a>Parametreler

*UCON*<br/>
Windows SDK [TTM_SETTITLE](/windows/win32/Controls/ttm-settitle) *simgeye* bakın.

*lpstrTitle*<br/>
Başlık dizesinin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [TTM_SETTITLE](/windows/win32/Controls/ttm-settitle)davranışını uygular.

##  <a name="settoolinfo"></a>CToolTipCtrl:: SetToolInfo

Bir araç ipucunun bir araç için sakladığı bilgileri ayarlar.

```
void SetToolInfo(LPTOOLINFO lpToolInfo);
```

### <a name="parameters"></a>Parametreler

*lpToolInfo*<br/>
Ayarlanacak bilgileri belirten [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) yapısına yönelik bir işaretçi.

##  <a name="settoolrect"></a>CToolTipCtrl:: SetToolRect

Araç için yeni bir sınırlayıcı dikdörtgen ayarlar.

```
void SetToolRect(
    CWnd* pWnd,
    UINT_PTR nIDTool,
    LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Aracı içeren pencerenin işaretçisi.

*nIDTool*<br/>
Aracın KIMLIĞI.

*lpRect*<br/>
Yeni sınırlayıcı dikdörtgeni belirten bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına yönelik işaretçi.

##  <a name="setwindowtheme"></a>CToolTipCtrl:: SetWindowTheme

Araç ipucu penceresinin görsel stilini ayarlar.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Parametreler

*Pszalt Ppname*<br/>
Ayarlanacak görsel stili içeren bir Unicode dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi [TTM_SETWINDOWTHEME](/windows/win32/Controls/ttm-setwindowtheme) iletisinin işlevselliğine öykünür.

##  <a name="update"></a>CToolTipCtrl:: Update

Geçerli aracın yeniden çizilmesini zorlar.

```
void Update();
```

##  <a name="updatetiptext"></a>CToolTipCtrl:: UpdateTipText

Bu denetimin araçları için araç ipucu metnini güncelleştirir.

```
void UpdateTipText(
    LPCTSTR lpszText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);

void UpdateTipText(
    UINT nIDText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
Araç için metin işaretçisi.

*pWnd*<br/>
Aracı içeren pencerenin işaretçisi.

*nIDTool*<br/>
Aracın KIMLIĞI.

*Nıdtext*<br/>
Aracın metnini içeren dize kaynağının KIMLIĞI.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CToolBar Sınıfı](../../mfc/reference/ctoolbar-class.md)
