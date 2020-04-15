---
title: CToolTipCtrl Sınıfı
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
ms.openlocfilehash: fdf91549fd1b911de3af82bb940b92fe5e220b92
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365098"
---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl Sınıfı

Bir uygulamadaki bir aracın amacını açıklayan tek bir metin satırı görüntüleyen küçük bir açılır pencere olan "araç uç denetimi"nin işlevselliğini kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CToolTipCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CToolTipCtrl::CToolTipCtrl](#ctooltipctrl)|Bir `CToolTipCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CToolTipCtrl::Etkinleştir](#activate)|Araç ipucu denetimini etkinleştirir ve devre dışı bırakır.|
|[CToolTipCtrl::AddTool](#addtool)|Bir aracı takım ucu denetimine kaydeder.|
|[CToolTipCtrl::AdjustRect](#adjustrect)|Bir araç uç denetiminin metin görüntüleme dikdörtgeni ile pencere dikdörtgeni arasında dönüşüm sağlar.|
|[CToolTipCtrl::Oluştur](#create)|Bir araç ucu denetimi oluşturur ve `CToolTipCtrl` bir nesneye bağlar.|
|[CToolTipCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri ile bir araç ipucu denetimi oluşturur `CToolTipCtrl` ve bir nesneye bağlar.|
|[CToolTipCtrl::DelTool](#deltool)|Bir aracı takım ucu denetiminden kaldırır.|
|[CToolTipCtrl::GetBubbleSize](#getbubblesize)|Takım ucunun boyutunu alır.|
|[CToolTipCtrl::GetCurrentTool](#getcurrenttool)|Geçerli araç ipucu denetiminin görüntülenebilen araç ipucu penceresinin boyutu, konumu ve metni gibi bilgileri alır.|
|[CToolTipCtrl::GetDelayTime](#getdelaytime)|Şu anda bir araç ipucu denetimi için ayarlanan ilk, açılır pencere ve yeniden gösteri sürelerini alır.|
|[CToolTipCtrl::GetMargin](#getmargin)|Araç ipucu penceresi için ayarlanan üst, sol, alt ve sağ kenar boşluklarını alır.|
|[CToolTipCtrl::GetMaxTipWidth](#getmaxtipwidth)|Araç ucu penceresi için maksimum genişliği alır.|
|[CToolTipCtrl::GetText](#gettext)|Bir araç ipucu denetiminin bir araç için koruduğu metni alır.|
|[CToolTipCtrl::GetTipBkColor](#gettipbkcolor)|Araç ipucu penceresindearka plan rengini alır.|
|[CToolTipCtrl::GetTipTextColor](#gettiptextcolor)|Araç ipucu penceresindeki metin rengini alır.|
|[CToolTipCtrl::GetTitle](#gettitle)|Geçerli araç ipucu denetiminin başlığını alır.|
|[CToolTipCtrl::GetToolCount](#gettoolcount)|Bir araç ucu denetimi tarafından tutulan araçların sayısını alır.|
|[CToolTipCtrl::GetToolInfo](#gettoolinfo)|Bir araç ipucu denetiminin bir araç hakkında koruduğu bilgileri alır.|
|[CToolTipCtrl::HitTest](#hittest)|Verilen aracın sınırlayıcı dikdörtgeniçinde olup olmadığını belirlemek için bir noktayı sınar. Bu ysa, araç hakkında bilgi alır.|
|[CToolTipCtrl::Pop](#pop)|Görüntülenen araç ipucu pencereyi görünümden kaldırır.|
|[CToolTipCtrl::Popup](#popup)|Geçerli Araç İpucu denetiminin son fare iletisinin koordinatlarında görüntülenmesine neden olur.|
|[CToolTipCtrl::RelayEvent](#relayevent)|Fare iletisini işleme için bir araç ipucu denetimine geçirir.|
|[CToolTipCtrl::SetDelayTime](#setdelaytime)|Bir araç ipucu denetimi için ilk, açılır pencere ve yeniden gösterme sürelerini ayarlar.|
|[CToolTipCtrl::SetMargin](#setmargin)|Araç ucu penceresi için üst, sol, alt ve sağ kenar boşluklarını ayarlar.|
|[CToolTipCtrl::SetMaxTipWidth](#setmaxtipwidth)|Araç ucu penceresi için maksimum genişliği ayarlar.|
|[CToolTipCtrl::SetTipBkColor](#settipbkcolor)|Arka plan rengini bir araç ipucu penceresinde ayarlar.|
|[CToolTipCtrl::SetTipTextColor](#settiptextcolor)|Araç ipucu penceresinde metin rengini ayarlar.|
|[CToolTipCtrl::SetTitle](#settitle)|Araç ucuna standart bir simge ve başlık dizesi ekler.|
|[CToolTipCtrl::SetToolInfo](#settoolinfo)|Bir araç ipucunun bir araç için koruduğu bilgileri ayarlar.|
|[CToolTipCtrl::SetToolRect](#settoolrect)|Bir araç için yeni bir sınırlayıcı dikdörtgen ayarlar.|
|[CToolTipCtrl::SetWindowTheme](#setwindowtheme)|Araç ucu penceresinin görsel stilini ayarlar.|
|[CToolTipCtrl::Güncelleme](#update)|Geçerli aracı yeniden çizilmeye zorlar.|
|[CToolTipCtrl::UpdateTipText](#updatetiptext)|Araç ipucu metnini bir araç için ayarlar.|

## <a name="remarks"></a>Açıklamalar

"Araç", alt pencere veya denetim gibi bir pencere veya pencerenin istemci alanı içindeki uygulama tanımlı dikdörtgen alandır. Bir araç ipucu çoğu zaman gizlenir, yalnızca kullanıcı imleci bir araca taktığında ve yaklaşık bir buçuk saniye boyunca orada bıraktığında görünür. Araç ipucu imlecin yanında görünür ve kullanıcı bir fare düğmesini tıklattığında veya imleci araçtan uzaklaştırdığında kaybolur.

`CToolTipCtrl`araç ucunun başlangıç saatini ve süresini, araç ucu metnini çevreleyen kenar boşluğu genişliklerini, araç ipucu penceresinin genişliğini ve araç ucunun arka planını ve metin rengini denetleme işlevini sağlar. Tek bir araç ipucu denetimi birden fazla araç için bilgi sağlayabilir.

Sınıf, `CToolTipCtrl` Windows ortak araç ipucu denetiminin işlevselliğini sağlar. Bu denetim (ve `CToolTipCtrl` bu nedenle sınıf) yalnızca Windows 95/98 ve Windows NT sürümleri 3.51 ve sonraki sürümler altında çalışan programlar için kullanılabilir.

Araç ipuçlarını etkinleştirme hakkında daha fazla bilgi için [CFrameWnd'den türetilmiş olmayan Windows'daki Araç İpuçları'na](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)bakın.

Kullanma `CToolTipCtrl`hakkında daha fazla bilgi [Using CToolTipCtrl](../../mfc/using-ctooltipctrl.md)için, [bkz.](../../mfc/controls-mfc.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CToolTipCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="ctooltipctrlactivate"></a><a name="activate"></a>CToolTipCtrl::Etkinleştir

Bir araç ipucu denetimini etkinleştirmek veya devre dışı bırakmak için bu işlevi arayın.

```
void Activate(BOOL bActivate);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
Araç uç denetiminin etkinleştirilip etkinleştirilmeyeceğini veya devre dışı bırakılıp atılmayacağını belirtir.

### <a name="remarks"></a>Açıklamalar

*bActivate* TRUE ise, denetim etkinleştirilir; FALSE ise devre dışı bırakılır.

Bir araç ipucu denetimi etkin olduğunda, imleç denetime kayıtlı bir araç tadığında araç ipucu bilgileri görüntülenir; etkin olmadığında, imleç bir araç üzerinde yken bile araç ipucu bilgileri görünmez.

### <a name="example"></a>Örnek

  CPropertySheet için örneğe [bakın:GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrladdtool"></a><a name="addtool"></a>CToolTipCtrl::AddTool

Bir aracı takım ucu denetimine kaydeder.

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

*Pwnd*<br/>
Aracı içeren pencereyi işaretçi.

*nIDText*<br/>
Aracın metnini içeren dize kaynağının kimliği.

*lpRectTool*<br/>
Aracın sınırlayıcı dikdörtgeninin koordinatlarını içeren bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına işaretçi. *Koordinatlar, pWnd*ile tanımlanan pencerenin istemci alanının sol üst köşesine göredir.

*nIDTool*<br/>
Aracın kimliği.

*lpszMetin*<br/>
Araç için metne işaretçi. Bu parametre LPSTR_TEXTCALLBACK değeri içeriyorsa, TTN_NEEDTEXT bildirim iletileri *pWnd* işaret pencerenin üst gidin.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*LpRectTool* ve *nIDTool* parametreleri her ikisi de geçerli olmalıdır, ya da *lpRectTool* NULL ise, *nIDTool* 0 olmalıdır.

Bir araç ipucu denetimi birden fazla araçla ilişkilendirilebilir. İmleç araç üzerindeyken araç uç ucunda depolanan bilgilerin görüntülenmesi için bir aracı araç uç denetimine kaydetmek için bu işlevi arayın.

> [!NOTE]
> Bir araç ipucunu statik denetime `AddTool`.'yi kullanarak ayarlayamazsınız.

### <a name="example"></a>Örnek

  CPropertySheet için örneğe [bakın:GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrladjustrect"></a><a name="adjustrect"></a>CToolTipCtrl::AdjustRect

Araç ucu denetiminin metin görüntüleme dikdörtgeni ile pencere dikdörtgeni arasında dönüşüm sağlar.

```
BOOL AdjustRect(
    LPRECT lprc,
    BOOL bLarger = TRUE);
```

### <a name="parameters"></a>Parametreler

*lprc*<br/>
Bir araç ucu pencere dikdörtgeni veya metin ekran dikdörtgentutan bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısı için işaretçi.

*bBüyük*<br/>
TRUE ise, *lprc* bir metin ekran dikdörtgen belirtmek için kullanılır ve ilgili pencere dikdörtgenalır. FALSE ise, *lprc* bir pencere dikdörtgeni belirtmek için kullanılır ve ilgili metin ekran dikdörtgenalır.

### <a name="return-value"></a>Dönüş Değeri

Dikdörtgen başarıyla ayarlanırsa sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, bir araç ipucu denetiminin pencere dikdörtgeninden metin görüntüleme dikdörtgenini veya belirli bir metin görüntüleme dikdörtgenini görüntülemek için gereken araç ucu pencere dikdörtgenini hesaplar.

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [TTM_ADJUSTRECT](/windows/win32/Controls/ttm-adjustrect)davranışını uygular.

## <a name="ctooltipctrlcreate"></a><a name="create"></a>CToolTipCtrl::Oluştur

Bir araç ucu denetimi oluşturur ve `CToolTipCtrl` bir nesneye bağlar.

```
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Araç ucu denetiminin ana penceresini belirtir, `CDialog`genellikle . NULL olmamalıdır.

*Dwstyle*<br/>
Takım ucu denetiminin stilini belirtir. Daha fazla bilgi için **Açıklamalar** bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla `CToolTipCtrl` oluşturulursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki adımda bir `CToolTipCtrl` yapı inşa e. Önce `CToolTipCtrl` nesneyi oluşturmak için oluşturucuyu çağırın, ardından araç ucu denetimini oluşturmak ve `Create` `CToolTipCtrl` nesneye iliştirmek için çağırın.

*dwStyle* parametresi [Pencere Stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles)herhangi bir kombinasyonu olabilir. Buna ek olarak, bir araç ipucu denetimi iki sınıfa özgü stilleri vardır: TTS_ALWAYSTIP ve TTS_NOPREFIX.

|Stil|Anlamı|
|-----------|-------------|
|TTS_ALWAYSTIP|İmleç bir araç üzerindeyken, takım ipucu denetiminin sahibipenceresietkin veya etkin olmayan olup olmadığına bakılmaksızın, takım ucunun görüntülemeyeceğini belirtir. Bu stil olmadan, aracın sahibi penceresi etkin olduğunda araç ipucu denetimi görüntülenir, ancak etkin olmadığında görünmez.|
|TTS_NOPREFIX|Bu stil, sistemin ampersand (&) karakterini bir dizeden sıyırmasını önler. Bir araç ipucu denetimiTTS_NOPREFIX stiline sahip değilse, sistem ampersand karakterleri otomatik olarak şeritler ve bir uygulamanın hem menü öğesi hem de araç ipucu denetiminde metin olarak aynı dizeyi kullanmasına olanak sağlar.|

Bir araç ipucu denetimi, denetimi oluştururken belirtip belirtmediğinize bakılmaksızın, WS_POPUP ve WS_EX_TOOLWINDOW pencere stillerine sahiptir.

Genişletilmiş windows stilleriile bir araç ipucu denetimi oluşturmak için [CToolTipCtrl::CreateEx](#createex) yerine `Create`.

### <a name="example"></a>Örnek

  CPropertySheet için örneğe [bakın:GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrlcreateex"></a><a name="createex"></a>CToolTipCtrl::CreateEx

Denetim (alt pencere) oluşturur ve nesneyle `CToolTipCtrl` ilişkilendirin.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwStyle = 0,
    DWORD dwStyleEx = 0);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Denetimin üst öğesi olan pencereye işaretçi.

*Dwstyle*<br/>
Takım ucu denetiminin stilini belirtir. Daha fazla bilgi için [Oluştur'un](#create) **Açıklamalar** bölümüne bakın.

*dwStyleEx*<br/>
Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerilistesi için Windows SDK'daki [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) için *dwExStyle* parametreye bakın.

### <a name="return-value"></a>Dönüş Değeri

Nonzero aksi takdirde başarılı 0.

### <a name="remarks"></a>Açıklamalar

Windows `CreateEx` genişletilmiş `Create` stil önsöz **WS_EX_** tarafından belirtilen genişletilmiş Windows stilleri uygulamak yerine kullanın.

## <a name="ctooltipctrlctooltipctrl"></a><a name="ctooltipctrl"></a>CToolTipCtrl::CToolTipCtrl

Bir `CToolTipCtrl` nesne inşa eder.

```
CToolTipCtrl();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi `Create` yaptıktan sonra aramalısınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]

## <a name="ctooltipctrldeltool"></a><a name="deltool"></a>CToolTipCtrl::DelTool

*PWnd* ve *nIDTool* tarafından belirtilen aracı bir araç ucu denetimi tarafından desteklenen araçların koleksiyonundan kaldırır.

```
void DelTool(
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Aracı içeren pencereyi işaretçi.

*nIDTool*<br/>
Aracın kimliği.

## <a name="ctooltipctrlgetbubblesize"></a><a name="getbubblesize"></a>CToolTipCtrl::GetBubbleSize

Takım ucunun boyutunu alır.

```
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Parametreler

*lpToolInfo*<br/>
Araç ucunun [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Takım ucunun boyutu.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/ttm-getbubblesize)iletisinin TTM_GETBUBBLESIZE davranışını uygular.

## <a name="ctooltipctrlgetcurrenttool"></a><a name="getcurrenttool"></a>CToolTipCtrl::GetCurrentTool

Geçerli araç ipucu denetimi tarafından görüntülenen araç ipucu penceresinin boyutu, konumu ve metni gibi bilgileri alır.

```
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*lpToolInfo*|[çıkış] Geçerli araç ipucu penceresi hakkında bilgi alan bir [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) yapısıiçin işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Bilgiler başarıyla alınırsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [TTM_GETCURRENTTOOL](/windows/win32/Controls/ttm-getcurrenttool) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, geçerli araç ipucu penceresi hakkında bilgi alır.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]

## <a name="ctooltipctrlgetdelaytime"></a><a name="getdelaytime"></a>CToolTipCtrl::GetDelayTime

Bir araç ipucu denetimi için şu anda ayarlanan ilk, açılır pencere ve yeniden gösteri sürelerini alır.

```
int GetDelayTime(DWORD dwDuration) const;
```

### <a name="parameters"></a>Parametreler

*dwSüre süresi*<br/>
Hangi süre değerinin alınacağını belirten bayrak. Bu parametre aşağıdaki değerlerden biri olabilir:

- TTDT_AUTOPOP İşaretçi bir aracın sınırlayan dikdörtgeninde sabitse, takım ipucu penceresinin görünür kaldığı süreyi alın.

- TTDT_INITIAL Takım ipucu penceresi görünmeden önce işaretçinin bir aracın sınırlayıcı dikdörtgeninde sabit kalması gereken süreyi alın.

- TTDT_RESHOW İşaretçi bir araçtan diğerine taşınırken sonraki araç ucu pencerelerinin görünmesi için gereken süreyi alın.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen gecikme süresi, milisaniye cinsinden

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [TTM_GETDELAYTIME](/windows/win32/Controls/ttm-getdelaytime)davranışını uygular.

## <a name="ctooltipctrlgetmargin"></a><a name="getmargin"></a>CToolTipCtrl::GetMargin

Araç ucu penceresi için ayarlanan üst, sol, alt ve sağ kenar boşluklarını alır.

```
void GetMargin(LPRECT lprc) const;
```

### <a name="parameters"></a>Parametreler

*lprc*<br/>
Kenar boşluğu `RECT` bilgilerini alacak bir yapının adresi. [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısının üyeleri sınırlayıcı bir dikdörtgen tanımlamaz. Bu iletinin amacı için yapı üyeleri aşağıdaki gibi yorumlanır:

|Üye|Gösterimi|
|------------|--------------------|
|`top`|Üst kenarlık ile araç ucu metninin üst kısmı arasındaki pikseller arasındaki mesafe.|
|`left`|Sol kenarlık ile uç metninin sol ucu arasındaki mesafe, piksel olarak.|
|`bottom`|Piksellerde alt kenarlık ile uç metninin alt kısmı arasındaki mesafe.|
|`right`|Piksellerde sağ kenarlık ile uç metninin sağ ucu arasındaki mesafe.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [TTM_GETMARGIN](/windows/win32/Controls/ttm-getmargin)davranışını uygular.

## <a name="ctooltipctrlgetmaxtipwidth"></a><a name="getmaxtipwidth"></a>CToolTipCtrl::GetMaxTipWidth

Araç ucu penceresi için maksimum genişliği alır.

```
int GetMaxTipWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

Araç ucu penceresi için maksimum genişlik.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [TTM_GETMAXTIPWIDTH](/windows/win32/Controls/ttm-getmaxtipwidth)davranışını uygular.

## <a name="ctooltipctrlgettext"></a><a name="gettext"></a>CToolTipCtrl::GetText

Bir araç ipucu denetiminin bir araç için koruduğu metni alır.

```
void GetText(
    CString& str,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Aracın metnini alan bir `CString` nesneye başvuru.

*Pwnd*<br/>
Aracı içeren pencereyi işaretçi.

*nIDTool*<br/>
Aracın kimliği.

### <a name="remarks"></a>Açıklamalar

*pWnd* ve *nIDTool* parametreleri aracı tanımlar. Bu araç daha önce bir önceki arama ile araç `CToolTipCtrl::AddTool`ucu denetimine kaydedilmişse, *str* parametresi tarafından başvurulan nesneye aracın metni atanır.

## <a name="ctooltipctrlgettipbkcolor"></a><a name="gettipbkcolor"></a>CToolTipCtrl::GetTipBkColor

Araç ipucu penceresindearka plan rengini alır.

```
COLORREF GetTipBkColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arka plan rengini temsil eden bir [COLORREF](/windows/win32/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [TTM_GETTIPBKCOLOR](/windows/win32/Controls/ttm-gettipbkcolor)davranışını uygular.

## <a name="ctooltipctrlgettiptextcolor"></a><a name="gettiptextcolor"></a>CToolTipCtrl::GetTipTextColor

Araç ipucu penceresindeki metin rengini alır.

```
COLORREF GetTipTextColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Metin rengini temsil eden bir [COLORREF](/windows/win32/gdi/colorref) değeri.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/ttm-gettiptextcolor)iletisi TTM_GETTIPTEXTCOLOR davranışını uygular.

## <a name="ctooltipctrlgettitle"></a><a name="gettitle"></a>CToolTipCtrl::GetTitle

Geçerli araç ipucu denetiminin başlığını alır.

```
void GetTitle(PTTGETTITLE pttgt) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pttgt*|[çıkış] ToolTip denetimi hakkında bilgi içeren bir [TTGETTITLE](/windows/win32/api/commctrl/ns-commctrl-ttgettitle) yapısıiçin işaretçi. Bu yöntem döndürdüğünde, [TTGETTITLE](/windows/win32/api/commctrl/ns-commctrl-ttgettitle) yapısının *pszTitle* üyesi başlığın metnini işaret edir.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [TTM_GETTITLE](/windows/win32/Controls/ttm-gettitle) iletisini gönderir.

## <a name="ctooltipctrlgettoolcount"></a><a name="gettoolcount"></a>CToolTipCtrl::GetToolCount

Araç ipucu denetimine kayıtlı araçların sayısını alır.

```
int GetToolCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Araç uç denetimine kayıtlı araç sayısı.

## <a name="ctooltipctrlgettoolinfo"></a><a name="gettoolinfo"></a>CToolTipCtrl::GetToolInfo

Bir araç ipucu denetiminin bir araç hakkında koruduğu bilgileri alır.

```
BOOL GetToolInfo(
    CToolInfo& ToolInfo,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>Parametreler

*Toolınfo*<br/>
Aracın metnini alan bir `TOOLINFO` nesneye başvuru.

*Pwnd*<br/>
Aracı içeren pencereyi işaretçi.

*nIDTool*<br/>
Aracın kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`hwnd` *CToolInfo* tarafından başvurulan [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) yapısının üyeleri `uId` aracı tanımlar. Bu araç önceki bir arama ile araç ucu `AddTool`denetimine `TOOLINFO` kaydedilmişse, yapı araç hakkında bilgilerle doldurulur.

## <a name="ctooltipctrlhittest"></a><a name="hittest"></a>CToolTipCtrl::HitTest

Verilen aracın sınırlayıcı dikdörtgeniçinde olup olmadığını belirlemek ve varsa araç hakkında bilgi almak için bir noktayı sınar.

```
BOOL HitTest(
    CWnd* pWnd,
    CPoint pt,
    LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Aracı içeren pencereyi işaretçi.

*Pt*<br/>
Test edilecek `CPoint` noktanın koordinatlarını içeren bir nesneye işaretçi.

*lpToolInfo*<br/>
Araç hakkında bilgi içeren [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Isabet testi bilgilerinin belirttiği nokta aracın sınırlayıcı dikdörtgenindeyse sıfıra inmez; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev sıfır olmayan bir değer döndürürse, *lpToolInfo* tarafından işaret edilen yapı, dikdörtgeni noktası nın bulunduğu araçla doldurulur.

Yapı `TTHITTESTINFO` aşağıdaki gibi tanımlanır:

```cpp
typedef struct _TT_HITTESTINFO { // tthti
    HWND hwnd;   // handle of tool or window with tool
    POINT pt;    // client coordinates of point to test
    TOOLINFO ti; // receives information about the tool
} TTHITTESTINFO, FAR * LPHITTESTINFO;
```

- `hwnd`

   Aracın tutamacını belirtir.

- `pt`

   Nokta aracın sınırlayıcı dikdörtgenindeyse bir noktanın koordinatlarını belirtir.

- `ti`

   Araç hakkında bilgi. `TOOLINFO` Yapı hakkında daha fazla bilgi için [Bkz. CToolTipCtrl::GetToolInfo](#gettoolinfo).

## <a name="ctooltipctrlpop"></a><a name="pop"></a>CToolTipCtrl::Pop

Görüntülenen araç ipucu penceresini görünümden kaldırır.

```
void Pop();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/ttm-pop)iletisinin TTM_POP davranışını uygular.

## <a name="ctooltipctrlpopup"></a><a name="popup"></a>CToolTipCtrl::Popup

Geçerli araç ipucu denetiminin son fare iletisinin koordinatlarında görüntülenmesine neden olur.

```
void Popup();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [TTM_POPUP](/windows/win32/Controls/ttm-popup) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği bir araç ipucu penceresi görüntüler.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]

## <a name="ctooltipctrlrelayevent"></a><a name="relayevent"></a>CToolTipCtrl::RelayEvent

Fare iletisini işleme için bir araç ipucu denetimine geçirir.

```
void RelayEvent(LPMSG lpMsg);
```

### <a name="parameters"></a>Parametreler

*lpMsg*<br/>
İletiyi içeren bir [MSG](/windows/win32/api/winuser/ns-winuser-msg) yapısına işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir araç ipucu denetimi yalnızca aşağıdaki iletileri `RelayEvent`işler:

|WM_LBUTTONDOWN|Wm_mousemove|
|---------------------|-------------------|
|WM_LBUTTONUP|WM_RBUTTONDOWN|
|WM_MBUTTONDOWN|WM_RBUTTONUP|
|WM_MBUTTONUP||

### <a name="example"></a>Örnek

  CPropertySheet için örneğe [bakın:GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrlsetdelaytime"></a><a name="setdelaytime"></a>CToolTipCtrl::SetDelayTime

Bir araç ipucu denetimi için gecikme süresini ayarlar.

```
void SetDelayTime(UINT nDelay);

void SetDelayTime(
    DWORD dwDuration,
    int iTime);
```

### <a name="parameters"></a>Parametreler

*nGecikme*<br/>
Yeni gecikme süresini milisaniye cinsinden belirtir.

*dwSüre süresi*<br/>
Hangi süre değerinin alınacağını belirten bayrak. Geçerli değerlerin açıklaması için [CToolTipCtrl::GetDelayTime'a](#getdelaytime) bakın.

*iTime*<br/>
Belirtilen gecikme süresi, milisaniye cinsinden.

### <a name="remarks"></a>Açıklamalar

Gecikme süresi, imlecin araç ipucu penceresi görünmeden önce bir araçta kalması gereken süredir. Varsayılan gecikme süresi 500 milisaniyedir.

## <a name="ctooltipctrlsetmargin"></a><a name="setmargin"></a>CToolTipCtrl::SetMargin

Araç ucu penceresi için üst, sol, alt ve sağ kenar boşluklarını ayarlar.

```
void SetMargin(LPRECT lprc);
```

### <a name="parameters"></a>Parametreler

*lprc*<br/>
Ayarlanacak `RECT` kenar boşluğu bilgilerini içeren bir yapının adresi. Yapının `RECT` üyeleri sınırlayıcı bir dikdörtgen tanımlamaz. Bkz. [CToolTipCtrl::Marj](#getmargin) bilgilerinin açıklaması için Margin alın.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [TTM_SETMARGIN](/windows/win32/Controls/ttm-setmargin)davranışını uygular.

## <a name="ctooltipctrlsetmaxtipwidth"></a><a name="setmaxtipwidth"></a>CToolTipCtrl::SetMaxTipWidth

Araç ucu penceresi için maksimum genişliği ayarlar.

```
int SetMaxTipWidth(int iWidth);
```

### <a name="parameters"></a>Parametreler

*iGenişlik*<br/>
Ayarlanacak maksimum araç ucu pencere genişliği.

### <a name="return-value"></a>Dönüş Değeri

Önceki maksimum uç genişliği.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [TTM_SETMAXTIPWIDTH](/windows/win32/Controls/ttm-setmaxtipwidth)davranışını uygular.

## <a name="ctooltipctrlsettipbkcolor"></a><a name="settipbkcolor"></a>CToolTipCtrl::SetTipBkColor

Arka plan rengini bir araç ipucu penceresinde ayarlar.

```
void SetTipBkColor(COLORREF clr);
```

### <a name="parameters"></a>Parametreler

*Clr*<br/>
Yeni arka plan rengi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/ttm-settipbkcolor)iletisinin TTM_SETTIPBKCOLOR davranışını uygular.

## <a name="ctooltipctrlsettiptextcolor"></a><a name="settiptextcolor"></a>CToolTipCtrl::SetTipTextColor

Araç ipucu penceresinde metin rengini ayarlar.

```
void SetTipTextColor(COLORREF clr);
```

### <a name="parameters"></a>Parametreler

*Clr*<br/>
Yeni metin rengi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [TTM_SETTIPTEXTCOLOR](/windows/win32/Controls/ttm-settiptextcolor)davranışını uygular.

## <a name="ctooltipctrlsettitle"></a><a name="settitle"></a>CToolTipCtrl::SetTitle

Araç ucuna standart bir simge ve başlık dizesi ekler.

```
BOOL SetTitle(
    UINT uIcon,
    LPCTSTR lpstrTitle);
```

### <a name="parameters"></a>Parametreler

*uIcon*<br/>
Windows SDK'daki [TTM_SETTITLE](/windows/win32/Controls/ttm-settitle) *simgesine* bakın.

*lpstrTitle*<br/>
Başlık dizesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [TTM_SETTITLE](/windows/win32/Controls/ttm-settitle)davranışını uygular.

## <a name="ctooltipctrlsettoolinfo"></a><a name="settoolinfo"></a>CToolTipCtrl::SetToolInfo

Bir araç ipucunun bir araç için koruduğu bilgileri ayarlar.

```
void SetToolInfo(LPTOOLINFO lpToolInfo);
```

### <a name="parameters"></a>Parametreler

*lpToolInfo*<br/>
Ayarlayabilmek için bilgileri belirten bir [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) yapısına işaretçi.

## <a name="ctooltipctrlsettoolrect"></a><a name="settoolrect"></a>CToolTipCtrl::SetToolRect

Bir araç için yeni bir sınırlayıcı dikdörtgen ayarlar.

```
void SetToolRect(
    CWnd* pWnd,
    UINT_PTR nIDTool,
    LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Aracı içeren pencereyi işaretçi.

*nIDTool*<br/>
Aracın kimliği.

*Lprect*<br/>
Yeni sınırlayıcı dikdörtgeni belirten bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısıişaretçisi.

## <a name="ctooltipctrlsetwindowtheme"></a><a name="setwindowtheme"></a>CToolTipCtrl::SetWindowTheme

Araç ucu penceresinin görsel stilini ayarlar.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Parametreler

*pszSubAppName*<br/>
Ayarlanan görsel stili içeren Unicode dizesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İade değeri kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [TTM_SETWINDOWTHEME](/windows/win32/Controls/ttm-setwindowtheme) iletisinin işlevselliğini taklit eder.

## <a name="ctooltipctrlupdate"></a><a name="update"></a>CToolTipCtrl::Güncelleme

Geçerli aracı yeniden çizilmeye zorlar.

```
void Update();
```

## <a name="ctooltipctrlupdatetiptext"></a><a name="updatetiptext"></a>CToolTipCtrl::UpdateTipText

Bu denetimaraçları için araç ipucu metnini güncelleştirir.

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

*lpszMetin*<br/>
Araç için metne işaretçi.

*Pwnd*<br/>
Aracı içeren pencereyi işaretçi.

*nIDTool*<br/>
Aracın kimliği.

*nIDText*<br/>
Aracın metnini içeren dize kaynağının kimliği.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Ctoolbar Sınıfı](../../mfc/reference/ctoolbar-class.md)
