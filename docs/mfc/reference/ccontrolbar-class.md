---
title: CControlBar Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CControlBar
- AFXEXT/CControlBar
- AFXEXT/CControlBar::CControlBar
- AFXEXT/CControlBar::CalcDynamicLayout
- AFXEXT/CControlBar::CalcFixedLayout
- AFXEXT/CControlBar::CalcInsideRect
- AFXEXT/CControlBar::DoPaint
- AFXEXT/CControlBar::DrawBorders
- AFXEXT/CControlBar::DrawGripper
- AFXEXT/CControlBar::EnableDocking
- AFXEXT/CControlBar::GetBarStyle
- AFXEXT/CControlBar::GetBorders
- AFXEXT/CControlBar::GetCount
- AFXEXT/CControlBar::GetDockingFrame
- AFXEXT/CControlBar::IsFloating
- AFXEXT/CControlBar::OnUpdateCmdUI
- AFXEXT/CControlBar::SetBarStyle
- AFXEXT/CControlBar::SetBorders
- AFXEXT/CControlBar::SetInPlaceOwner
- AFXEXT/CControlBar::m_bAutoDelete
- AFXEXT/CControlBar::m_pInPlaceOwner
helpviewer_keywords:
- CControlBar [MFC], CControlBar
- CControlBar [MFC], CalcDynamicLayout
- CControlBar [MFC], CalcFixedLayout
- CControlBar [MFC], CalcInsideRect
- CControlBar [MFC], DoPaint
- CControlBar [MFC], DrawBorders
- CControlBar [MFC], DrawGripper
- CControlBar [MFC], EnableDocking
- CControlBar [MFC], GetBarStyle
- CControlBar [MFC], GetBorders
- CControlBar [MFC], GetCount
- CControlBar [MFC], GetDockingFrame
- CControlBar [MFC], IsFloating
- CControlBar [MFC], OnUpdateCmdUI
- CControlBar [MFC], SetBarStyle
- CControlBar [MFC], SetBorders
- CControlBar [MFC], SetInPlaceOwner
- CControlBar [MFC], m_bAutoDelete
- CControlBar [MFC], m_pInPlaceOwner
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
ms.openlocfilehash: deb95d76e6d68ba5b9fad82bca1d88fd71c5a547
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369390"
---
# <a name="ccontrolbar-class"></a>CControlBar Sınıfı

Denetim çubuğu sınıfları [CStatusBar,](../../mfc/reference/cstatusbar-class.md) [CToolBar,](../../mfc/reference/ctoolbar-class.md) [CDialogBar,](../../mfc/reference/cdialogbar-class.md) [CReBar](../../mfc/reference/crebar-class.md)ve [COleResizeBar](../../mfc/reference/coleresizebar-class.md)için taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CControlBar : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CControlBar::CControlBar](#ccontrolbar)|Bir `CControlBar` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CControlBar::CalcDynamicLayout](#calcdynamiclayout)|[CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi olarak dinamik bir denetim çubuğunun boyutunu döndürür.|
|[CControlBar::CalcFixedLayout](#calcfixedlayout)|Denetim çubuğunun boyutunu [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi olarak döndürür.|
|[CControlBar::CalcInsideRect](#calcinsiderect)|Denetim çubuğu alanının geçerli boyutlarını verir; sınırları da dahil olmak üzere.|
|[CControlBar::DoPaint](#dopaint)|Denetim çubuğunun kenarlıklarını ve kavrayan ını işler.|
|[CControlBar::DrawBorders](#drawborders)|Denetim çubuğunun kenarlıklarını işler.|
|[CControlBar::DrawGripper](#drawgripper)|Kontrol çubuğunun kavrayan ını işler.|
|[CControlBar::Etkinleştirdocking](#enabledocking)|Bir denetim çubuğunun kenetlenmesini veya yüzdürmesine izin verir.|
|[CControlBar::GetBarStyle](#getbarstyle)|Denetim çubuğu stili ayarlarını alır.|
|[CControlBar::GetBorders](#getborders)|Denetim çubuğunun kenarlık değerlerini alır.|
|[CControlBar::GetCount](#getcount)|Denetim çubuğundaki HWND olmayan öğelerin sayısını verir.|
|[CControlBar::GetDockingFrame](#getdockingframe)|Bir işaretçiyi denetim çubuğunun kenetlendiği çerçeveye döndürür.|
|[CControlBar::IsFloating](#isfloating)|Söz konusu denetim çubuğu kayan bir denetim çubuğuysa sıfır olmayan bir değer verir.|
|[CControlBar::OnUpdateCmdUI](#onupdatecmdui)|Komut UI işleyicilerini çağırır.|
|[CControlBar::SetBarStyle](#setbarstyle)|Denetim çubuğu stili ayarlarını değiştirir.|
|[CControlBar::SetBorders](#setborders)|Denetim çubuğunun kenarlık değerlerini ayarlar.|
|[CControlBar::SetinplaceOwner](#setinplaceowner)|Denetim çubuğunun yerine sahibini değiştirir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CControlBar::m_bAutoDelete](#m_bautodelete)|Sıfır değilse, `CControlBar` Windows denetim çubuğu yok edildiğinde nesne silinir.|
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|Kontrol çubuğunun yerinde sahibi.|

## <a name="remarks"></a>Açıklamalar

Denetim çubuğu genellikle çerçeve penceresinin soluna veya sağına hizalanmış bir penceredir. Windows iletileri oluşturan ve yanıtlayan pencereler veya windows olmayan ve uygulama kodu veya çerçeve kodu tarafından yönetilen HWND tabanlı olmayan öğeler olan, HWND tabanlı denetimler olan alt öğeler içerebilir. Liste kutuları ve denetimleri HWND tabanlı denetimlere örnektir; durum çubuğu bölmeleri ve bitmap düğmeleri HWND tabanlı olmayan denetimlere örnektir.

Denetim çubuğu pencereleri genellikle bir üst çerçeve penceresinin alt pencereleridir ve genellikle çerçeve penceresinin istemci görünümü veya MDI istemcisi için kardeştir. Nesne, `CControlBar` kendisini konumlandırmak için üst pencerenin istemci dikdörtgeni hakkındaki bilgileri kullanır. Daha sonra üst pencerenin istemci alanında ne kadar boşluk kaldığı konusunda üst pencereyi bildirir.

Daha fazla `CControlBar`bilgi için bkz:

- [Denetim Çubukları](../../mfc/control-bars.md)

- [Teknik Not 31: Kontrol Çubukları](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CControlBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext.h

## <a name="ccontrolbarcalcdynamiclayout"></a><a name="calcdynamiclayout"></a>CControlBar::CalcDynamicLayout

Çerçeve, dinamik bir araç çubuğunun boyutlarını hesaplamak için bu üye işlevi çağırır.

```
virtual CSize CalcDynamicLayout(
    int nLength,
    DWORD nMode);
```

### <a name="parameters"></a>Parametreler

*nUzunluk*<br/>
*DwMode'a*bağlı olarak kontrol çubuğunun istenen boyutu yatay veya dikeydir.

*nMode*<br/>
Dinamik denetim çubuğunun yüksekliğini ve genişliğini belirlemek için aşağıdaki önceden tanımlanmış bayraklar kullanılır. Bayrakları birleştirmek için bitwise-OR (&#124;) işlecikullanın.

|Düzen modu bayrakları|Anlamı|
|-----------------------|-------------------|
|LM_STRETCH|Denetim çubuğunun çerçevenin boyutuna kadar uzatılıp genişletilmeyeceğini gösterir. Çubuk bir yerleştirme çubuğu değilse ayarlayın (yerleştirme için kullanılamaz). Çubuk kenetlendiğinde veya kayan olduğunda ayarlanmaz (yerleştirme için kullanılabilir). Ayarlanırsa, LM_STRETCH *nLength* yoklar ve LM_HORZ durumuna göre boyutları döndürür. LM_STRETCH [CalcFixedLayout](#calcfixedlayout)kullanılan *bStretch* parametre benzer çalışır; germe ve yönlendirme arasındaki ilişki hakkında daha fazla bilgi için üye işlevi ne bakın.|
|LM_HORZ|Çubuğun yatay veya dikey olarak yönlendirilmiş olduğunu gösterir. Çubuk yatay olarak yönlendirilmişse ve dikey olarak yönlendirilmişse ayarlanmaz. LM_HORZ [CalcFixedLayout](#calcfixedlayout)kullanılan *bHorz* parametre benzer çalışır; germe ve yönlendirme arasındaki ilişki hakkında daha fazla bilgi için üye işlevi ne bakın.|
|LM_MRUWIDTH|En son kullanılan dinamik genişlik. *nLength* parametresini yok sayar ve hatırlanan en son kullanılan genişliği kullanır.|
|LM_HORZDOCK|Yatay Kenetlenmiş Boyutlar. *nLength* parametresini yoksa ve en büyük genişliğe sahip dinamik boyutu döndürür.|
|LM_VERTDOCK|Dikey Kenetlenmiş Boyutlar. *nLength* parametresini yoksa ve en yüksek liğe sahip dinamik boyutu döndürür.|
|LM_LENGTHY|*nLength* genişlik yerine yükseklik (Y yönü) gösteriyorsa ayarlayın.|
|LM_COMMIT|Kayan denetim çubuğunun geçerli genişliğine LM_MRUWIDTH sıfırlar.|

### <a name="return-value"></a>Dönüş Değeri

[Bir CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesinin piksel olarak denetim çubuğu boyutu.

### <a name="remarks"></a>Açıklamalar

Türetilmiş sınıflarda kendi dinamik düzeninizi sağlamak için `CControlBar`bu üye işlevini geçersiz kılın. `CControlBar` [CToolbar](../../mfc/reference/ctoolbar-class.md)gibi, türetilen MFC sınıfları bu üye işlevi geçersiz kılar ve kendi uygulamalarını sağlar.

## <a name="ccontrolbarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CControlBar::CalcFixedLayout

Denetim çubuğunun yatay boyutunu hesaplamak için bu üye işlevi arayın.

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

*bStretch*<br/>
Çubuğun çerçevenin boyutuna kadar uzatılıp uzatılması gerektiğini gösterir. çubuk bir yerleştirme çubuğu olmadığında (yerleştirme için kullanılamaz) *bStretch* parametresi sıfır değildir ve kenetlendiğinde veya kayan olduğunda (yerleştirme için kullanılabilir) 0'dır.

*bHorz*<br/>
Çubuğun yatay veya dikey olarak yönlendirilmiş olduğunu gösterir. çubuk yatay olarak yönlendirilmişse *bHorz* parametresi sıfır değildir ve dikey olarak yönlendirilmişse 0'dır.

### <a name="return-value"></a>Dönüş Değeri

Bir `CSize` nesnenin piksel olarak denetim çubuğu boyutu.

### <a name="remarks"></a>Açıklamalar

Araç çubukları gibi denetim çubukları, denetim çubuğunda bulunan düğmeleri yerleştirmek için yatay veya dikey olarak esneebilir.

*bStretch* TRUE ise, *bHorz*tarafından sağlanan yönlendirme boyunca boyutu gerin. Başka bir deyişle, *bHorz* FALSE ise, denetim çubuğu dikey olarak gerilir. *bStretch* FALSE ise, hiçbir esneme oluşur. Aşağıdaki tabloda *bStretch* ve *bHorz*olası permütasyon ve ortaya çıkan kontrol çubuğu stilleri gösterir.

|bStretch|bHorz|Germe|Yön|Yerleştirme/yerleştirme|
|--------------|-----------|----------------|-----------------|--------------------------|
|TRUE|TRUE|Yatay germe|Yatay odaklı|Kenetlenme|
|TRUE|FALSE|Dikey germe|Dikey odaklı|Kenetlenme|
|FALSE|TRUE|Esneme yok|Yatay odaklı|Takma|
|FALSE|FALSE|Esneme yok|Dikey odaklı|Takma|

## <a name="ccontrolbarcalcinsiderect"></a><a name="calcinsiderect"></a>CControlBar::CalcInsideRect

Çerçeve, denetim çubuğunun istemci alanını hesaplamak için bu işlevi çağırır.

```
virtual void CalcInsideRect(
    CRect& rect,
    BOOL bHorz) const;
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Denetim çubuğunun geçerli boyutlarını içerir; sınırları da dahil olmak üzere.

*bHorz*<br/>
Çubuğun yatay veya dikey olarak yönlendirilmiş olduğunu gösterir. çubuk yatay olarak yönlendirilmişse *bHorz* parametresi sıfır değildir ve dikey olarak yönlendirilmişse 0'dır.

### <a name="remarks"></a>Açıklamalar

Bu işlev, denetim çubuğu boyanmadan önce çağrılır.

Kenarlıkların ve denetim çubuğunun kavrayıcı çubuğunun görüntülemeyi özelleştirmek için bu işlevi geçersiz kılın.

## <a name="ccontrolbarccontrolbar"></a><a name="ccontrolbar"></a>CControlBar::CControlBar

Bir `CControlBar` nesne inşa eder.

```
CControlBar();
```

## <a name="ccontrolbardopaint"></a><a name="dopaint"></a>CControlBar::DoPaint

Denetim çubuğunun kenarlıklarını ve kavrayan çubuğunu işlemek için çerçeve tarafından çağrılır.

```
virtual void DoPaint(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Denetim çubuğunun kenarlıklarını ve kavrayıcısını işlemek için kullanılacak aygıt bağlamını işaret ediyor.

### <a name="remarks"></a>Açıklamalar

Denetim çubuğunun çizim davranışını özelleştirmek için bu işlevi geçersiz kılın.

Başka bir özelleştirme yöntemi `DrawBorders` ve `DrawGripper` işlevleri geçersiz kılmak ve kenarlıklar ve kavrayan için özel çizim kodu eklemektir. Bu yöntemler varsayılan `DoPaint` yöntem tarafından çağrıldığı için `DoPaint` geçersiz kılma gerekmez.

## <a name="ccontrolbardrawborders"></a><a name="drawborders"></a>CControlBar::DrawBorders

Denetim çubuğunun kenarlıklarını işlemek için çerçeve tarafından çağrıldı.

```
virtual void DrawBorders(
    CDC* pDC,
    CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Denetim çubuğunun kenarlıklarını işlemek için kullanılacak aygıt bağlamını işaret ediyor.

*Rect*<br/>
Denetim `CRect` çubuğunun boyutlarını içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Denetim çubuğu kenarlıklarının görünümünü özelleştirmek için bu işlevi geçersiz kılın.

## <a name="ccontrolbardrawgripper"></a><a name="drawgripper"></a>CControlBar::DrawGripper

Kontrol çubuğunun kavrayan işlemek için çerçeve tarafından çağrıldı.

```
virtual void DrawGripper(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Kontrol çubuğu kavrayıcısını işlemek için kullanılacak aygıt bağlamını işaret ediyor.

*Rect*<br/>
Kontrol `CRect` çubuğu tutucunun boyutlarını içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Kontrol çubuğu kavrayan görünümünü özelleştirmek için bu işlevi geçersiz kılın.

## <a name="ccontrolbarenabledocking"></a><a name="enabledocking"></a>CControlBar::Etkinleştirdocking

Bir denetim çubuğunun kenetlenmesini sağlamak için bu işlevi arayın.

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Parametreler

*dwDockStyle*<br/>
Denetim çubuğunun kenetlenmeyi destekleyip desteklemediğini ve desteklenirse denetim çubuğunun kenetlenebileceği ana penceresinin yanlarını belirtir. Aşağıdakilerden biri veya birkaçı olabilir:

- CBRS_ALIGN_TOP İstemci alanının üst kısmında kenetlenme sağlar.

- CBRS_ALIGN_BOTTOM İstemci alanının altına kenetlenmeyi sağlar.

- CBRS_ALIGN_LEFT İstemci alanının sol tarafına kenetlenmeyi sağlar.

- CBRS_ALIGN_RIGHT İstemci alanının sağ tarafına kenetlenmeyi sağlar.

- CBRS_ALIGN_ANY İstemci alanının herhangi bir tarafına kenetlenmeyi sağlar.

- CBRS_FLOAT_MULTI Birden çok denetim çubuklarının tek bir mini çerçeve penceresinde yüzdürilmesine izin verir.

0 (yani bayrak olmadığını gösterirse), denetim çubuğu yanaşmayacak.

### <a name="remarks"></a>Açıklamalar

Belirtilen taraflar, hedef çerçeve penceresine yerleştirme için etkinleştirilen taraflardan biriyle eşleşmelidir veya denetim çubuğu bu çerçeve penceresine sabitlenemez.

## <a name="ccontrolbargetbarstyle"></a><a name="getbarstyle"></a>CControlBar::GetBarStyle

Denetim çubuğu için şu anda hangi **CBRS_** (denetim çubuğu stilleri) ayarlarının ayarlanabilmek için bu işlevi arayın.

```
DWORD GetBarStyle();
```

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğunun geçerli **CBRS_** (denetim çubuğu stilleri) ayarları. Kullanılabilir stillerin tam listesi için [CControlBar::SetBarStyle'a](#setbarstyle) bakın.

### <a name="remarks"></a>Açıklamalar

**WS_** (pencere stili) stilini işlemez.

## <a name="ccontrolbargetborders"></a><a name="getborders"></a>CControlBar::GetBorders

Denetim çubuğu için geçerli kenarlık değerlerini döndürür.

```
CRect GetBorders() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim `CRect` çubuğu nesnesinin her iki tarafının geçerli genişliğini (piksel olarak) içeren bir nesne. Örneğin, [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesinin *sol* üyesinin değeri sol el kenarlığı genişliğidir.

## <a name="ccontrolbargetcount"></a><a name="getcount"></a>CControlBar::GetCount

`CControlBar` Nesnedeki HWND olmayan öğelerin sayısını verir.

```
int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki HWND olmayan öğelerin `CControlBar` sayısı. Bu işlev, [cdialogbar](../../mfc/reference/cdialogbar-class.md) nesnesi için 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Öğenin türü türemiş nesneye bağlıdır: [CStatusBar](../../mfc/reference/cstatusbar-class.md) nesneleri için bölmeler ve [CToolBar](../../mfc/reference/ctoolbar-class.md) nesneleri için düğmeler ve ayırıcılar.

## <a name="ccontrolbargetdockingframe"></a><a name="getdockingframe"></a>CControlBar::GetDockingFrame

Denetim çubuğunuzun sabitlendiği geçerli çerçeve penceresine işaretçi almak için bu üye işlevi arayın.

```
CFrameWnd* GetDockingFrame() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa çerçeve penceresine işaretçi; aksi takdirde NULL.

Denetim çubuğu bir çerçeve penceresine sabitlenmezse (diğer bir süre, denetim çubuğu kayansa), bu işlev bir işaretçiyi ana [CMiniFrameWnd'e](../../mfc/reference/cminiframewnd-class.md)döndürür.

### <a name="remarks"></a>Açıklamalar

Takılabilir denetim çubukları hakkında daha fazla bilgi için [Bkz. CControlBar::EnableDocking](#enabledocking) ve [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).

## <a name="ccontrolbarisfloating"></a><a name="isfloating"></a>CControlBar::IsFloating

Denetim çubuğunun kayan veya kenetlenip kenetlenmediğini belirlemek için bu üye işlevini arayın.

```
BOOL IsFloating() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğu kayarsa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir denetim çubuğunun durumunu docked'dan kayana değiştirmek için [CFrameWnd'i arayın:FloatControlBar.](../../mfc/reference/cframewnd-class.md#floatcontrolbar)

## <a name="ccontrolbarm_bautodelete"></a><a name="m_bautodelete"></a>CControlBar::m_bAutoDelete

Sıfır değilse, `CControlBar` Windows denetim çubuğu yok edildiğinde nesne silinir.

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>Açıklamalar

*m_bAutoDelete* bool tipi nin ortak bir değişkenidir.

Denetim çubuğu nesnesi genellikle bir çerçeve penceresi nesnesine katıştırılır. Bu durumda, çerçeve penceresi yok edildiğinde katıştırılmış denetim çubuğu nesnesi yok edildiğinden *m_bAutoDelete* 0'dır.

Yığına bir `CControlBar` nesne ayırırsanız ve **sil'i**aramayı planlamazsanız, bu değişkeni sıfır olmayan bir değere ayarlayın.

## <a name="ccontrolbarm_pinplaceowner"></a><a name="m_pinplaceowner"></a>CControlBar::m_pInPlaceOwner

Kontrol çubuğunun yerinde sahibi.

```
CWnd* m_pInPlaceOwner;
```

## <a name="ccontrolbaronupdatecmdui"></a><a name="onupdatecmdui"></a>CControlBar::OnUpdateCmdUI

Bu üye işlev, araç çubuğunun veya durum çubuğunun durumunu güncelleştirmek için çerçeve tarafından çağrılır.

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler) = 0;
```

### <a name="parameters"></a>Parametreler

*pTarget*<br/>
Uygulamanın ana çerçeve penceresine işaret ediyor. Bu işaretçi, güncelleştirme iletilerini yönlendirmek için kullanılır.

*bDisableIfNoHndler*<br/>
Güncelleştirme işleyicisi olmayan bir denetimin devre dışı bırakılmış olarak otomatik olarak görüntülenip görüntülenmemesi gerektiğini belirten bayrak.

### <a name="remarks"></a>Açıklamalar

Tek bir düğmeyi veya bölmeyi güncelleştirmek için, bir güncelleştirme işleyicisini uygun şekilde ayarlamak için ileti haritanızdaki ON_UPDATE_COMMAND_UI makroyu kullanın. Bu makroyu kullanma hakkında daha fazla bilgi için [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) bakın.

`OnUpdateCmdUI`uygulama boşta olduğunda çerçeve tarafından çağrılır. Güncellenecek çerçeve penceresi, en azından dolaylı olarak görünür bir çerçeve penceresinin alt penceresi olmalıdır. `OnUpdateCmdUI`gelişmiş bir geçersizdir.

## <a name="ccontrolbarsetbarstyle"></a><a name="setbarstyle"></a>CControlBar::SetBarStyle

Denetim çubuğu için istenen **CBRS_** stilleri ayarlamak için bu işlevi arayın.

```
void SetBarStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Denetim çubuğu için istenen stiller. Aşağıdakilerden biri veya birkaçı olabilir:

- CBRS_ALIGN_TOP Denetim çubuğunun çerçeve penceresinin istemci alanının üst bölümüne sabitlemesine izin verir.

- CBRS_ALIGN_BOTTOM Denetim çubuğunun çerçeve penceresinin istemci alanının altına sabitlemesine izin verir.

- CBRS_ALIGN_LEFT Denetim çubuğunun çerçeve penceresinin istemci alanının sol tarafına sabitlemesine izin verir.

- CBRS_ALIGN_RIGHT Denetim çubuğunun çerçeve penceresinin istemci alanının sağ tarafına sabitlemesine izin verir.

- CBRS_ALIGN_ANY Denetim çubuğunun çerçeve penceresinin istemci alanının herhangi bir tarafına sabitlemesine izin verir.

- CBRS_BORDER_TOP Görünür olduğunda denetim çubuğunun üst kenarına bir kenarlık çizilmesine neden olur.

- CBRS_BORDER_BOTTOM Görünür olduğunda denetim çubuğunun alt kenarına bir kenarlık çizilmesine neden olur.

- CBRS_BORDER_LEFT Görünür olduğunda denetim çubuğunun sol kenarına bir kenar çizilmesine neden olur.

- CBRS_BORDER_RIGHT Görünür olduğunda denetim çubuğunun sağ kenarına bir kenar çizilmesine neden olur.

- CBRS_FLOAT_MULTI Birden çok denetim çubuklarının tek bir mini çerçeve penceresinde yüzdürilmesine izin verir.

- CBRS_TOOLTIPS Denetim çubuğu için araç ipuçlarının görüntülenmesine neden olur.

- CBRS_FLYBY İleti metninin araç ipuçlarıyla aynı anda güncelleştirilmesine neden olur.

- CBRS_GRIPPER Herhangi bir türetilmiş sınıf için `CReBar` `CControlBar`çizilecek bir nesnedeki bantlarda kullanılana benzer bir kavrayanın çizilmesine neden olur.

### <a name="remarks"></a>Açıklamalar

**WS_** (pencere stili) ayarlarını etkilemez.

## <a name="ccontrolbarsetborders"></a><a name="setborders"></a>CControlBar::SetBorders

Denetim çubuğunun kenarlıklarının boyutunu ayarlamak için bu işlevi arayın.

```
void SetBorders(
    int cxLeft = 0,
    int cyTop = 0,
    int cxRight = 0,
    int cyBottom = 0);

void SetBorders(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*cxLeft*<br/>
Denetim çubuğunun sol kenarlığı genişliği (piksel olarak).

*cyTop*<br/>
Denetim çubuğunun üst sınırının yüksekliği (piksel olarak).

*cxSağ*<br/>
Denetim çubuğunun sağ kenarlığı genişliği (piksel olarak).

*cyBottom*<br/>
Denetim çubuğunun alt kenarlığınyüksekliği (piksel olarak).

*Lprect*<br/>
Denetim çubuğu nesnesinin her kenarlığı için geçerli genişliğini (piksel olarak) içeren bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine işaretçi.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, denetim çubuğunun üst ve alt kenarlıklarını 5 piksel, sol ve sağ kenarlıkları ise 2 pikselolarak ayarlar:

[!code-cpp[NVC_MFCControlLadenDialog#61](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]

## <a name="ccontrolbarsetinplaceowner"></a><a name="setinplaceowner"></a>CControlBar::SetinplaceOwner

Denetim çubuğunun yerine sahibini değiştirir.

```
void SetInPlaceOwner(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Bir `CWnd` nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Ctoolbar Sınıfı](../../mfc/reference/ctoolbar-class.md)<br/>
[CDialogBar Sınıfı](../../mfc/reference/cdialogbar-class.md)<br/>
[CStatusBar Sınıfı](../../mfc/reference/cstatusbar-class.md)<br/>
[CReBar Sınıfı](../../mfc/reference/crebar-class.md)
