---
title: CControlBar sınıfı
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
ms.openlocfilehash: 41e40b3da7b4a294fe396a9d93f7c6a93593ff95
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866453"
---
# <a name="ccontrolbar-class"></a>CControlBar sınıfı

Denetim çubuğu sınıfları [CStatusBar](../../mfc/reference/cstatusbar-class.md), [CToolBar](../../mfc/reference/ctoolbar-class.md), [CDialogBar](../../mfc/reference/cdialogbar-class.md), [CReBar](../../mfc/reference/crebar-class.md)ve [COleResizeBar](../../mfc/reference/coleresizebar-class.md)için temel sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CControlBar : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CControlBar:: CControlBar](#ccontrolbar)|`CControlBar` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CControlBar:: CalcDynamicLayout](#calcdynamiclayout)|Dinamik denetim çubuğunun boyutunu [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi olarak döndürür.|
|[CControlBar:: CalcFixedLayout](#calcfixedlayout)|Denetim çubuğunun boyutunu [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi olarak döndürür.|
|[CControlBar:: CalcInsideRect](#calcinsiderect)|Denetim çubuğu alanının geçerli boyutlarını döndürür; kenarlıkları dahil edin.|
|[CControlBar::D oPaint](#dopaint)|Denetim çubuğunun kenarlıklarını ve kavrayıcıyı işler.|
|[CControlBar::D Rawkenarlýklar](#drawborders)|Denetim çubuğunun kenarlıklarını işler.|
|[CControlBar::D Rawkavrayıcı](#drawgripper)|Denetim çubuğunun kavrayıcıyı işler.|
|[CControlBar:: EnableDocking](#enabledocking)|Denetim çubuğunun yerleştirilmiş veya kayan olmasına izin verir.|
|[CControlBar:: GetBarStyle](#getbarstyle)|Denetim çubuğu stili ayarlarını alır.|
|[CControlBar:: Getkenarlýklar](#getborders)|Denetim çubuğunun kenarlık değerlerini alır.|
|[CControlBar:: GetCount](#getcount)|Denetim çubuğundaki HWND olmayan öğe sayısını döndürür.|
|[CControlBar:: GetDockingFrame](#getdockingframe)|Bir denetim çubuğunun yerleştirildiği çerçeveye bir işaretçi döndürür.|
|[CControlBar:: ıskayan](#isfloating)|Söz konusu denetim çubuğu bir kayan denetim çubuğu ise, sıfır dışında bir değer döndürür.|
|[CControlBar:: OnUpdateCmdUI](#onupdatecmdui)|Komut UI işleyicilerini çağırır.|
|[CControlBar:: SetBarStyle](#setbarstyle)|Denetim çubuğu stili ayarlarını değiştirir.|
|[CControlBar:: Setkenarlýklar](#setborders)|Denetim çubuğunun kenarlık değerlerini ayarlar.|
|[CControlBar:: Setınplaceowner](#setinplaceowner)|Denetim çubuğunun yerinde sahibini değiştirir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CControlBar:: m_bAutoDelete](#m_bautodelete)|Sıfır değilse, Windows Denetim çubuğu yok edildiğinde `CControlBar` nesnesi silinir.|
|[CControlBar:: m_pInPlaceOwner](#m_pinplaceowner)|Denetim çubuğunun yerinde sahibi.|

## <a name="remarks"></a>Açıklamalar

Denetim çubuğu, genellikle bir çerçeve penceresinin soluna veya sağına hizalanmış bir penceredir. Windows iletileri oluşturan ve yanıt veren Windows olan ve Windows olmayan ve uygulama kodu veya Framework kodu tarafından yönetilen ve HWND tabanlı olmayan öğeler olan HWND tabanlı denetimler olan alt öğeler içerebilir. Liste kutuları ve düzenleme denetimleri HWND tabanlı denetimlerin örnekleridir; durum çubuğu bölmeleri ve bit eşlem düğmeleri HWND tabanlı olmayan denetimlere örnektir.

Denetim çubuğu pencereleri genellikle üst çerçeve penceresinin alt pencereleri olur ve genellikle çerçeve penceresinin istemci görünümü veya MDI istemcisiyle eş lardır. Bir `CControlBar` nesnesi, kendisini konumlandırmak için üst pencerenin istemci dikdörtgeniyle ilgili bilgileri kullanır. Daha sonra ana pencerenin istemci alanında ayrılmamış alanın ne kadar alana ayrıldığına ilişkin olarak ana pencereye bildirir.

`CControlBar`hakkında daha fazla bilgi için bkz.

- [Denetim Çubukları](../../mfc/control-bars.md)

- [Teknik notta 31: denetim çubukları](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CControlBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext. h

##  <a name="calcdynamiclayout"></a>CControlBar:: CalcDynamicLayout

Framework, dinamik bir araç çubuğunun boyutlarını hesaplamak için bu üye işlevini çağırır.

```
virtual CSize CalcDynamicLayout(
    int nLength,
    DWORD nMode);
```

### <a name="parameters"></a>Parametreler

*nLength*<br/>
*DwMode*'a bağlı olarak, yatay veya dikey olan denetim çubuğunun istenen boyutu.

*nMode*<br/>
Aşağıdaki önceden tanımlanmış bayraklar, dinamik denetim çubuğunun yüksekliğini ve genişliğini belirlemede kullanılır. Bayrakları birleştirmek için bit düzeyinde OR&#124;() işlecini kullanın.

|Düzen modu bayrakları|Anlamı|
|-----------------------|-------------------|
|LM_STRETCH|Denetim çubuğunun çerçeve boyutuna esnetilip esnetilmeyeceğini gösterir. Çubuk bir yerleştirme çubuğu değilse (yerleştirme için kullanılamaz) ayarlayın. Çubuk yerleştirildiğinde veya kayan olduğunda (yerleştirme için kullanılabilir) ayarlı değildir. Ayarlanırsa, LM_STRETCH *nLength* yok sayılır ve LM_HORZ durumuna göre boyutları döndürür. LM_STRETCH, [CalcFixedLayout](#calcfixedlayout)Içinde kullanılan *beskme* parametresine benzer şekilde çalışır. uzatma ve yönlendirme arasındaki ilişki hakkında daha fazla bilgi için bkz. üye işlevi.|
|LM_HORZ|Çubuğun yatay veya dikey olarak yönlendirildiğini gösterir. Çubuk yatay olarak yönlendirilliyse ve dikey olarak yönlendirilliyse ayarlanır. LM_HORZ, [CalcFixedLayout](#calcfixedlayout)Içinde kullanılan *bHorz* parametresine benzer şekilde çalışır. uzatma ve yönlendirme arasındaki ilişki hakkında daha fazla bilgi için bkz. üye işlevi.|
|LM_MRUWIDTH|En son kullanılan dinamik Genişlik. *NLength* parametresini yoksayar ve anımsanan en son kullanılan genişliği kullanır.|
|LM_HORZDOCK|Yatay yerleştirilmiş boyutlar. *NLength* parametresini yoksayar ve en büyük genişliğe sahip dinamik boyutu döndürür.|
|LM_VERTDOCK|Dikey yerleştirilmiş boyutlar. *NLength* parametresini yoksayar ve en büyük yüksekliğe sahip dinamik boyutu döndürür.|
|LM_LENGTHY|*NLength* genişlik yerine yüksekliği (Y yönü) gösteriyorsa ayarlanır.|
|LM_COMMIT|LM_MRUWIDTH kayan denetim çubuğunun geçerli genişliğine sıfırlar.|

### <a name="return-value"></a>Dönüş Değeri

[CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesinin piksel cinsinden denetim çubuğu boyutu.

### <a name="remarks"></a>Açıklamalar

`CControlBar`türettiğiniz sınıflarda kendi dinamik düzeninizi sağlamak için bu üye işlevi geçersiz kılın. [CToolBar](../../mfc/reference/ctoolbar-class.md)gibi `CControlBar`türetilen MFC sınıfları, bu üye işlevini geçersiz kılar ve kendi uygulamasını sağlar.

##  <a name="calcfixedlayout"></a>CControlBar:: CalcFixedLayout

Bir denetim çubuğunun yatay boyutunu hesaplamak için bu üye işlevini çağırın.

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

*Besnetme*<br/>
Çubuğun çerçevenin boyutuna esnetilip uzatılmayacağını gösterir. Çubuk bir yerleştirme çubuğu olmadığında (yerleştirme için kullanılamaz) ve yerleştirildiğinde veya kayan olduğunda (yerleştirme için kullanılabilir) 0 olduğunda *Besnetme* parametresi sıfır dışı olur.

*bHorz*<br/>
Çubuğun yatay veya dikey olarak yönlendirildiğini gösterir. Çubuk yatay olarak yönlendirilse *bHorz* parametresi sıfır değildir ve dikey olarak yönlendirilse 0 ' dır.

### <a name="return-value"></a>Dönüş Değeri

`CSize` nesnesinin piksel cinsinden denetim çubuğu boyutu.

### <a name="remarks"></a>Açıklamalar

Araç çubukları gibi denetim çubukları, Denetim çubuğunda bulunan düğmelere uyum sağlamak için yatay veya dikey olarak uzatılabilirler.

*Besnetme* doğruysa, boyutu *bHorz*tarafından belirtilen yönle birlikte uzatın. Diğer bir deyişle, *bHorz* yanlış ise, denetim çubuğu dikey olarak uzatılır. *Besnetme* yanlışsa, bir Esnetme gerçekleşmez. Aşağıdaki tabloda, *Besnetme* ve *bHorz*gibi olası permütasyon ve ortaya çıkan denetim çubuğu stilleri gösterilmektedir.

|Besnetme|bHorz|Uzatı|Hizalama|Yerleştirme/yerleştirme yok|
|--------------|-----------|----------------|-----------------|--------------------------|
|TRUE|TRUE|Yatay uzatma|Yatay yönelimli|Yerleştirme yok|
|TRUE|Yanlış|Dikey Uzatma|Dikey yönelimli|Yerleştirme yok|
|Yanlış|TRUE|Hiçbir uzatma yok|Yatay yönelimli|Tanımlaya|
|Yanlış|Yanlış|Hiçbir uzatma yok|Dikey yönelimli|Tanımlaya|

##  <a name="calcinsiderect"></a>CControlBar:: CalcInsideRect

Framework, denetim çubuğunun istemci alanını hesaplamak için bu işlevi çağırır.

```
virtual void CalcInsideRect(
    CRect& rect,
    BOOL bHorz) const;
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Denetim çubuğunun geçerli boyutlarını içerir; kenarlıkları dahil edin.

*bHorz*<br/>
Çubuğun yatay veya dikey olarak yönlendirildiğini gösterir. Çubuk yatay olarak yönlendirilse *bHorz* parametresi sıfır değildir ve dikey olarak yönlendirilse 0 ' dır.

### <a name="remarks"></a>Açıklamalar

Bu işlev, denetim çubuğu boyanmadan önce çağrılır.

Denetim çubuğunun kenarlıkların ve kavrayıcı çubuğunun işlenmesini özelleştirmek için bu işlevi geçersiz kılın.

##  <a name="ccontrolbar"></a>CControlBar:: CControlBar

`CControlBar` nesnesi oluşturur.

```
CControlBar();
```

##  <a name="dopaint"></a>CControlBar::D oPaint

Denetim çubuğunun kenarlıklarını ve kavrayıcı çubuğunu işlemek için Framework tarafından çağırılır.

```
virtual void DoPaint(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Denetim çubuğunun kenarlıklarını ve kavrayıcıyı işlemek için kullanılacak cihaz bağlamını işaret eder.

### <a name="remarks"></a>Açıklamalar

Denetim çubuğunun çizim davranışını özelleştirmek için bu işlevi geçersiz kılın.

Başka bir özelleştirme yöntemi, `DrawBorders` ve `DrawGripper` işlevlerini geçersiz kılmak ve Kenarlıklar ve kavrayıcı için özel çizim kodu eklemektir. Bu yöntemler varsayılan `DoPaint` yöntemi tarafından çağrıldığı için `DoPaint` bir geçersiz kılma gerekli değildir.

##  <a name="drawborders"></a>CControlBar::D Rawkenarlýklar

Denetim çubuğunun kenarlıklarını işlemek için Framework tarafından çağırılır.

```
virtual void DrawBorders(
    CDC* pDC,
    CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Denetim çubuğunun kenarlıklarını işlemek için kullanılacak cihaz bağlamını işaret eder.

*Rect*<br/>
Denetim çubuğunun boyutlarını içeren `CRect` nesnesi.

### <a name="remarks"></a>Açıklamalar

Denetim çubuğu kenarlıklarının görünümünü özelleştirmek için bu işlevi geçersiz kılın.

##  <a name="drawgripper"></a>CControlBar::D Rawkavrayıcı

Denetim çubuğunun kavrayıcıyı işlemek için Framework tarafından çağırılır.

```
virtual void DrawGripper(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Denetim çubuğu kavrayıcıyı işlemek için kullanılacak cihaz bağlamına işaret eder.

*Rect*<br/>
Denetim çubuğu kavrayıcı boyutlarını içeren `CRect` nesnesi.

### <a name="remarks"></a>Açıklamalar

Denetim çubuğu kavrayıcı görünümünü özelleştirmek için bu işlevi geçersiz kılın.

##  <a name="enabledocking"></a>CControlBar:: EnableDocking

Bir denetim çubuğunun yerleştirilme özelliğini etkinleştirmek için bu işlevi çağırın.

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Parametreler

*dwDockStyle*<br/>
Denetim çubuğunun yerleştirmeyi ve üst penceresinin, varsa denetim çubuğunun sabitlenebilir olduğunu ve bunların yanlarını destekleyip desteklemediğini belirtir. Aşağıdakilerden biri veya daha fazlası olabilir:

- CBRS_ALIGN_TOP, istemci alanının en üstünde yerleştirme yapılmasına Izin verir.

- CBRS_ALIGN_BOTTOM, istemci alanının en altında yerleştirmeyi sağlar.

- CBRS_ALIGN_LEFT istemci alanının sol tarafında yerleştirme yapılmasına Izin verir.

- CBRS_ALIGN_RIGHT istemci alanının sağ tarafında yerleştirme yapılmasına Izin verir.

- CBRS_ALIGN_ANY istemci alanının herhangi bir tarafında yerleştirme yapılmasına Izin verir.

- CBRS_FLOAT_MULTI, tek bir mini çerçeve penceresinde birden fazla denetim çubuğunun ayrılmasını sağlar.

0 ise (yani, bayrak yoksa) denetim çubuğu çalışmaz.

### <a name="remarks"></a>Açıklamalar

Belirtilen kenarlar, hedef çerçeve penceresinde yerleştirme için etkinleştirilen taraflardan biriyle eşleşmelidir veya denetim çubuğu bu çerçeve penceresine yerleştirilmemelidir.

##  <a name="getbarstyle"></a>CControlBar:: GetBarStyle

Denetim çubuğu için hangi **cbrs_** (denetim çubuğu stilleri) ayarlarının ayarlandığını öğrenmek için bu işlevi çağırın.

```
DWORD GetBarStyle();
```

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğu için geçerli **cbrs_** (denetim çubuğu stilleri) ayarları. Kullanılabilir stillerin tüm listesi için bkz. [CControlBar:: SetBarStyle](#setbarstyle) .

### <a name="remarks"></a>Açıklamalar

**WS_** (pencere stili) stillerini işlemez.

##  <a name="getborders"></a>CControlBar:: Getkenarlýklar

Denetim çubuğu için geçerli sınır değerlerini döndürür.

```
CRect GetBorders() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğu nesnesinin her bir tarafındaki geçerli genişliği (piksel cinsinden) içeren `CRect` nesne. Örneğin, [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesinin *sol* üyesinin değeri, sol kenarlığın genişliğidir.

##  <a name="getcount"></a>CControlBar:: GetCount

`CControlBar` nesnesindeki HWND olmayan öğe sayısını döndürür.

```
int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CControlBar` nesnesindeki HWND olmayan öğe sayısı. Bu işlev bir [CDialogBar](../../mfc/reference/cdialogbar-class.md) nesnesi için 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Öğenin türü türetilmiş nesneye bağlıdır: [CStatusBar](../../mfc/reference/cstatusbar-class.md) nesneleri için bölmeler, [CToolBar](../../mfc/reference/ctoolbar-class.md) nesneleri için düğmeler ve ayırıcılar.

##  <a name="getdockingframe"></a>CControlBar:: GetDockingFrame

Denetim çubuğunuzun yerleştirildiği geçerli çerçeve penceresine bir işaretçi almak için bu üye işlevini çağırın.

```
CFrameWnd* GetDockingFrame() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa çerçeve penceresine yönelik bir işaretçi; Aksi takdirde NULL.

Denetim çubuğu bir çerçeve penceresine yerleştirilmemişse (yani, denetim çubuğu kayan ise), bu işlev üst [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)için bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Yerleştirilebilir denetim çubukları hakkında daha fazla bilgi için bkz. [CControlBar:: EnableDocking](#enabledocking) ve [CFrameWnd::D ockcontrolbar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).

##  <a name="isfloating"></a>CControlBar:: ıskayan

Denetim çubuğunun kayan mı yoksa yerleştirilmiş mi olduğunu anlamak için bu üye işlevi çağırın.

```
BOOL IsFloating() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğu yüzer ise sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir denetim çubuğunun durumunu, sabitlenmiş iken kayan olarak değiştirmek için [CFrameWnd:: FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar)öğesini çağırın.

##  <a name="m_bautodelete"></a>CControlBar:: m_bAutoDelete

Sıfır değilse, Windows Denetim çubuğu yok edildiğinde `CControlBar` nesnesi silinir.

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>Açıklamalar

*M_BAUTODELETE* bool türünde genel bir değişkendir.

Bir denetim çubuğu nesnesi genellikle çerçeve pencere nesnesine katıştırılır. Bu durumda, çerçeve penceresi yok edildiğinde katıştırılmış denetim çubuğu nesnesi yok edileceği için, *m_bAutoDelete* 0 ' dır.

Yığında bir `CControlBar` nesnesi ayırırsanız ve **silmeyi**çağırmayı planlamıyorsanız, bu değişkeni sıfır olmayan bir değere ayarlayın.

##  <a name="m_pinplaceowner"></a>CControlBar:: m_pInPlaceOwner

Denetim çubuğunun yerinde sahibi.

```
CWnd* m_pInPlaceOwner;
```

##  <a name="onupdatecmdui"></a>CControlBar:: OnUpdateCmdUI

Bu üye işlevi, araç çubuğunun ya da durum çubuğunun durumunu güncelleştirmek için Framework tarafından çağırılır.

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler) = 0;
```

### <a name="parameters"></a>Parametreler

*pTarget*<br/>
Uygulamanın ana çerçeve penceresine işaret eder. Bu işaretçi, güncelleştirme iletilerini yönlendirme için kullanılır.

*bDisableIfNoHndler*<br/>
Güncelleştirme işleyicisi olmayan bir denetimin otomatik olarak devre dışı olarak görüntülenip görüntülenmeyeceğini belirten bayrak.

### <a name="remarks"></a>Açıklamalar

Tek bir düğmeyi veya bölmeyi güncelleştirmek için ileti haritadaki ON_UPDATE_COMMAND_UI makrosunu kullanarak bir güncelleştirme işleyicisini uygun şekilde ayarlayın. Bu makroyu kullanma hakkında daha fazla bilgi için bkz. [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) .

`OnUpdateCmdUI`, uygulama boştayken Framework tarafından çağırılır. Görüntülenecek çerçeve penceresinin, görünür bir çerçeve penceresinin en azından dolaylı olarak bir alt pencere olması gerekir. `OnUpdateCmdUI` gelişmiş bir geçersiz kılınabilir.

##  <a name="setbarstyle"></a>CControlBar:: SetBarStyle

Denetim çubuğu için istenen **cbrs_** stillerini ayarlamak için bu işlevi çağırın.

```
void SetBarStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Denetim çubuğu için istenen stiller. Aşağıdakilerden biri veya daha fazlası olabilir:

- CBRS_ALIGN_TOP, denetim çubuğunun bir çerçeve penceresinin istemci alanının üstüne yerleştirilme olanağı sağlar.

- CBRS_ALIGN_BOTTOM, denetim çubuğunun bir çerçeve penceresinin istemci alanının altına yerleştirilme olanağı sağlar.

- CBRS_ALIGN_LEFT, denetim çubuğunun bir çerçeve penceresinin istemci alanının sol tarafına yerleştirilme olanağı sağlar.

- CBRS_ALIGN_RIGHT, denetim çubuğunun bir çerçeve penceresinin istemci alanının sağ tarafına yerleştirilme olanağı sağlar.

- CBRS_ALIGN_ANY, denetim çubuğunun bir çerçeve penceresinin istemci alanının herhangi bir tarafına yerleştirilme olanağı sağlar.

- CBRS_BORDER_TOP, görünür hale geldiğinde denetim çubuğunun üst kenarına bir kenarlık çizilmesini neden olur.

- CBRS_BORDER_BOTTOM, görünür hale geldiğinde denetim çubuğunun alt kenarına bir kenarlığın çizilmesini sağlar.

- CBRS_BORDER_LEFT, görünür hale geldiğinde denetim çubuğunun sol kenarında bir kenarlığın çizilmesini sağlar.

- CBRS_BORDER_RIGHT, görünür hale geldiğinde denetim çubuğunun sağ kenarında bir kenarlığın çizilmesini sağlar.

- CBRS_FLOAT_MULTI, tek bir mini çerçeve penceresinde birden fazla denetim çubuğunun ayrılmasını sağlar.

- CBRS_TOOLTIPS, denetim çubuğu için araç ipuçlarının görüntülenmesine neden olur.

- CBRS_FLYBY ileti metninin araç ipuçlarıyla aynı zamanda güncelleştirilmesini sağlar.

- CBRS_GRIPPER, bir `CReBar` nesnesindeki bantların `CControlBar`türetilmiş herhangi bir sınıf için çizilmesine benzer bir kavrayıcı neden olur.

### <a name="remarks"></a>Açıklamalar

**WS_** (pencere stili) ayarlarını etkilemez.

##  <a name="setborders"></a>CControlBar:: Setkenarlýklar

Denetim çubuğu kenarlıklarının boyutunu ayarlamak için bu işlevi çağırın.

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
Denetim çubuğunun sol kenarlığının genişliği (piksel cinsinden).

*cyTop*<br/>
Denetim çubuğunun üst kenarlığının yüksekliği (piksel cinsinden).

*cxRight*<br/>
Denetim çubuğunun sağ kenarlığının genişliği (piksel cinsinden).

*cyBottom*<br/>
Denetim çubuğunun alt kenarlığının yüksekliği (piksel cinsinden).

*lpRect*<br/>
Denetim çubuğu nesnesinin her kenarlığının geçerli genişliğini (piksel cinsinden) içeren bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine yönelik işaretçi.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, denetim çubuğunun üst ve alt kenarlıklarını 5 piksel ve sol ve sağ kenarlıklarını 2 piksel olarak ayarlar:

[!code-cpp[NVC_MFCControlLadenDialog#61](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]

##  <a name="setinplaceowner"></a>CControlBar:: Setınplaceowner

Denetim çubuğunun yerinde sahibini değiştirir.

```
void SetInPlaceOwner(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
`CWnd` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CToolBar Sınıfı](../../mfc/reference/ctoolbar-class.md)<br/>
[CDialogBar Sınıfı](../../mfc/reference/cdialogbar-class.md)<br/>
[CStatusBar Sınıfı](../../mfc/reference/cstatusbar-class.md)<br/>
[CReBar Sınıfı](../../mfc/reference/crebar-class.md)
