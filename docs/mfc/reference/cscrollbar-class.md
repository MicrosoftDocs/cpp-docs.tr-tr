---
title: CScrollBar sınıfı
ms.date: 11/04/2016
f1_keywords:
- CScrollBar
- AFXWIN/CScrollBar
- AFXWIN/CScrollBar::CScrollBar
- AFXWIN/CScrollBar::Create
- AFXWIN/CScrollBar::EnableScrollBar
- AFXWIN/CScrollBar::GetScrollBarInfo
- AFXWIN/CScrollBar::GetScrollInfo
- AFXWIN/CScrollBar::GetScrollLimit
- AFXWIN/CScrollBar::GetScrollPos
- AFXWIN/CScrollBar::GetScrollRange
- AFXWIN/CScrollBar::SetScrollInfo
- AFXWIN/CScrollBar::SetScrollPos
- AFXWIN/CScrollBar::SetScrollRange
- AFXWIN/CScrollBar::ShowScrollBar
helpviewer_keywords:
- CScrollBar [MFC], CScrollBar
- CScrollBar [MFC], Create
- CScrollBar [MFC], EnableScrollBar
- CScrollBar [MFC], GetScrollBarInfo
- CScrollBar [MFC], GetScrollInfo
- CScrollBar [MFC], GetScrollLimit
- CScrollBar [MFC], GetScrollPos
- CScrollBar [MFC], GetScrollRange
- CScrollBar [MFC], SetScrollInfo
- CScrollBar [MFC], SetScrollPos
- CScrollBar [MFC], SetScrollRange
- CScrollBar [MFC], ShowScrollBar
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
ms.openlocfilehash: 1ab25ad26357abe9091d273637f3ae9f77457342
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230486"
---
# <a name="cscrollbar-class"></a>CScrollBar sınıfı

Windows kaydırma çubuğu denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CScrollBar : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CScrollBar:: CScrollBar](#cscrollbar)|Bir `CScrollBar` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CScrollBar:: Create](#create)|Windows kaydırma çubuğunu oluşturur ve `CScrollBar` nesneye ekler.|
|[CScrollBar:: EnableScrollBar](#enablescrollbar)|Bir kaydırma çubuğunun bir ya da her iki okinin bir veya her iki oklarının|
|[CScrollBar:: GetScrollBarInfo](#getscrollbarinfo)|Bir yapıyı kullanarak kaydırma çubuğu hakkındaki bilgileri alır `SCROLLBARINFO` .|
|[CScrollBar:: Getscrollinınfo](#getscrollinfo)|Kaydırma çubuğu hakkındaki bilgileri alır.|
|[CScrollBar:: GetScrollLimit](#getscrolllimit)|Kaydırma çubuğunun sınırını alır|
|[CScrollBar:: GetScrollPos](#getscrollpos)|Bir kaydırma kutusunun geçerli konumunu alır.|
|[CScrollBar:: GetScrollRange](#getscrollrange)|Verilen kaydırma çubuğu için geçerli en düşük ve en fazla kaydırma çubuğu konumunu alır.|
|[CScrollBar:: Setscrollinınfo](#setscrollinfo)|Kaydırma çubuğu hakkındaki bilgileri ayarlar.|
|[CScrollBar:: SetScrollPos](#setscrollpos)|Bir kaydırma kutusunun geçerli konumunu ayarlar.|
|[CScrollBar:: SetScrollRange](#setscrollrange)|Verilen kaydırma çubuğu için en düşük ve en yüksek konum değerlerini ayarlar.|
|[CScrollBar:: ShowScrollBar](#showscrollbar)|Bir kaydırma çubuğunu gösterir veya gizler.|

## <a name="remarks"></a>Açıklamalar

İki adımda bir kaydırma çubuğu denetimi oluşturursunuz. İlk olarak, nesneyi oluşturmak `CScrollBar` için oluşturucuyu çağırın `CScrollBar` , sonra Windows kaydırma çubuğu denetimini oluşturmak ve nesneye iliştirmek Için üye [Oluştur](#create) işlevini çağırın `CScrollBar` .

İletişim `CScrollBar` kutusu içinde (bir iletişim kaynağı aracılığıyla) bir nesne oluşturursanız, `CScrollBar` Kullanıcı iletişim kutusunu kapattığında otomatik olarak yok edilir.

Bir `CScrollBar` pencere içinde bir nesne oluşturursanız, bunu yok etmeniz de gerekebilir.

`CScrollBar`Nesneyi yığında oluşturursanız, otomatik olarak yok edilir. `CScrollBar`Nesnesini, işlevini kullanarak yığında oluşturursanız **`new`** , **`delete`** Kullanıcı Windows kaydırma çubuğunu sonlandırdığında nesneyi yok etmek için nesnesini çağırmanız gerekir.

Nesnede herhangi bir bellek ayırırsanız `CScrollBar` , `CScrollBar` ayırmaların atılacağı yıkıcıyı geçersiz kılın.

Kullanmayla ilgili bilgiler için `CScrollBar` bkz. [denetimler](../../mfc/controls-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CScrollBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cscrollbarcreate"></a><a name="create"></a>CScrollBar:: Create

Windows kaydırma çubuğunu oluşturur ve `CScrollBar` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Kaydırma çubuğunun stilini belirtir. Kaydırma çubuğuna [kaydırma çubuğu stillerinin](../../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles) herhangi bir birleşimini uygulayın.

*Rect*<br/>
Kaydırma çubuğunun boyutunu ve konumunu belirtir. Ya bir `RECT` Yapı ya da bir `CRect` nesne olabilir.

*pParentWnd*<br/>
Kaydırma çubuğunun üst penceresini, genellikle bir `CDialog` nesneyi belirtir. NULL olmaması gerekir.

*NID*<br/>
Kaydırma çubuğunun denetim KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CScrollBar`İki adımda bir nesne oluşturursunuz. İlk olarak, nesneyi oluşturan oluşturucuyu çağırın `CScrollBar` ; ardından `Create` , ilişkili Windows kaydırma çubuğunu oluşturup başlatan ve bunu nesnesine ekleyen çağırın `CScrollBar` .

Bir kaydırma çubuğuna aşağıdaki [pencere stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles) uygulayın:

- WS_CHILD her zaman

- Genellikle WS_VISIBLE

- WS_DISABLED nadiren

- Denetimleri gruplamak Için WS_GROUP

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CScrollBar#1](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]

## <a name="cscrollbarcscrollbar"></a><a name="cscrollbar"></a>CScrollBar:: CScrollBar

Bir `CScrollBar` nesnesi oluşturur.

```
CScrollBar();
```

### <a name="remarks"></a>Açıklamalar

Nesnesi oluşturulduktan sonra, `Create` Windows kaydırma çubuğunu oluşturmak ve başlatmak için üye işlevini çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CScrollBar#2](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]

## <a name="cscrollbarenablescrollbar"></a><a name="enablescrollbar"></a>CScrollBar:: EnableScrollBar

Bir kaydırma çubuğunun bir ya da her iki okinin bir veya her iki oklarının

```
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```

### <a name="parameters"></a>Parametreler

*Dar bayraklar*<br/>
Kaydırma oklarının etkin mi yoksa devre dışı mı olduğunu ve hangi okların etkinleştirildiğini veya devre dışı bırakılacağını belirtir. Bu parametre aşağıdaki değerlerden biri olabilir:

- ESB_ENABLE_BOTH, kaydırma çubuğunun her iki oklarının de yapılmasını mümkün.

- ESB_DISABLE_LTUP bir yatay kaydırma çubuğunun sol okuna veya dikey bir kaydırma çubuğunun yukarı okuna devre dışı bırakır.

- ESB_DISABLE_RTDN bir yatay kaydırma çubuğunun sağ okuna veya dikey bir kaydırma çubuğunun aşağı okuna devre dışı bırakır.

- ESB_DISABLE_BOTH, kaydırma çubuğunun her iki oku devre dışı bırakır.

### <a name="return-value"></a>Dönüş Değeri

Oklar etkinse veya belirtilen şekilde devre dışı bırakılmışsa sıfır dışında; Aksi halde, okların istenen durumda olduğunu veya bir hatanın oluştuğunu gösteren 0.

### <a name="example"></a>Örnek

  [CScrollBar:: SetScrollRange](#setscrollrange)örneğine bakın.

## <a name="cscrollbargetscrollbarinfo"></a><a name="getscrollbarinfo"></a>CScrollBar:: GetScrollBarInfo

`SCROLLBARINFO`Yapının bir kaydırma çubuğu hakkında koruduğu bilgileri alır.

```
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;
```

### <a name="parameters"></a>Parametreler

*pScrollInfo*<br/>
[SCROLLBARINFO](/windows/win32/api/winuser/ns-winuser-scrollbarinfo) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi [SBM_SCROLLBARINFO](/windows/win32/Controls/sbm-getscrollbarinfo) iletisinin işlevselliğine öykünür.

## <a name="cscrollbargetscrollinfo"></a><a name="getscrollinfo"></a>CScrollBar:: Getscrollinınfo

`SCROLLINFO`Yapının bir kaydırma çubuğu hakkında koruduğu bilgileri alır.

```
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    UINT nMask = SIF_ALL);
```

### <a name="parameters"></a>Parametreler

*lpScrollInfo*<br/>
Bir [Scrollinfo](/windows/win32/api/winuser/ns-winuser-scrollinfo) yapısına yönelik işaretçi. Bu yapı hakkında daha fazla bilgi için Windows SDK bakın.

*nMask*<br/>
Alınacak kaydırma çubuğu parametrelerini belirtir. Tipik kullanım, SIF_ALL, SIF_PAGE, SIF_POS, SIF_TRACKPOS ve SIF_RANGE birleşimini belirtir. `SCROLLINFO`NMask değerleri hakkında daha fazla bilgi için bkz..

### <a name="return-value"></a>Dönüş Değeri

İleti herhangi bir değer elde alıyorsa, dönüş doğru olur. Aksi halde, yanlış olur.

### <a name="remarks"></a>Açıklamalar

`GetScrollInfo`uygulamaların 32 bitlik kaydırma konumlarını kullanmasına olanak sağlar.

[Scrollinfo](/windows/win32/api/winuser/ns-winuser-scrollinfo) yapısı, en düşük ve en yüksek kaydırma konumları, sayfa boyutu ve kaydırma kutusunun konumu (Thumb) dahil olmak üzere bir kaydırma çubuğu hakkındaki bilgileri içerir. `SCROLLINFO`Yapı varsayılanlarını değiştirme hakkında daha fazla bilgi için Windows SDK yapı konusuna bakın.

Kaydırma çubuğu konumunu, [CWnd:: OnHScroll ve [CWnd:: OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll)DEĞERINI belirten mfc Windows ileti işleyicileri yalnızca 16 bit konum verisi sağlar. `GetScrollInfo`ve `SetScrollInfo` 32 bit kaydırma çubuğu konumu verisi sağlar. Bu nedenle, bir uygulama `GetScrollInfo` işlem sırasında ya da `CWnd::OnHScroll` `CWnd::OnVScroll` 32 bitlik kaydırma çubuğu konumu verileri elde etmek için çağrı yapabilir.

### <a name="example"></a>Örnek

  [CWnd:: OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)örneğine bakın.

## <a name="cscrollbargetscrolllimit"></a><a name="getscrolllimit"></a>CScrollBar:: GetScrollLimit

Kaydırma çubuğunun en büyük kaydırma konumunu alır.

```
int GetScrollLimit();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa kaydırma çubuğunun maksimum konumunu belirtir; Aksi takdirde 0.

### <a name="example"></a>Örnek

  [CWnd:: OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)örneğine bakın.

## <a name="cscrollbargetscrollpos"></a><a name="getscrollpos"></a>CScrollBar:: GetScrollPos

Bir kaydırma kutusunun geçerli konumunu alır.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa kaydırma kutusunun geçerli konumunu belirtir; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Geçerli konum, geçerli kaydırma aralığına bağlı olan göreli bir değerdir. Örneğin, kaydırma aralığı 100 ile 200 ise ve kaydırma kutusu çubuğun ortasında ise, geçerli konum 150 ' dir.

### <a name="example"></a>Örnek

  [CWnd:: OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)örneğine bakın.

## <a name="cscrollbargetscrollrange"></a><a name="getscrollrange"></a>CScrollBar:: GetScrollRange

Verilen kaydırma çubuğu için geçerli en düşük ve en büyük kaydırma çubuğu konumlarını, *lpMinPos* ve *lpMaxPos*tarafından belirtilen konumlara kopyalar.

```cpp
void GetScrollRange(
    LPINT lpMinPos,
    LPINT lpMaxPos) const;
```

### <a name="parameters"></a>Parametreler

*lpMinPos*<br/>
En küçük konumu alacak tamsayı değişkenine işaret eder.

*lpMaxPos*<br/>
En yüksek konumu alacak tamsayı değişkenine işaret eder.

### <a name="remarks"></a>Açıklamalar

Bir kaydırma çubuğu denetimi için varsayılan Aralık boştur (her iki değer de 0 ' dır).

### <a name="example"></a>Örnek

  [CWnd:: OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)örneğine bakın.

## <a name="cscrollbarsetscrollinfo"></a><a name="setscrollinfo"></a>CScrollBar:: Setscrollinınfo

`SCROLLINFO`Yapının bir kaydırma çubuğu hakkında koruduğu bilgileri ayarlar.

```
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpScrollInfo*<br/>
Bir [Scrollinfo](/windows/win32/api/winuser/ns-winuser-scrollinfo) yapısına yönelik işaretçi.

*bRedraw*<br/>
Kaydırma çubuğunun yeni bilgileri yansıtacak şekilde yeniden çizilip çizmeyeceğini belirtir. *BRedraw* true ise, kaydırma çubuğu yeniden çizilir. YANLıŞ ise yeniden çizilmez. Kaydırma çubuğu varsayılan olarak yeniden çizilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, dönüş doğru olur. Aksi halde, yanlış olur.

### <a name="remarks"></a>Açıklamalar

`SCROLLINFO`Bayrak değerleri de dahil olmak üzere yapı parametreleri için gereken değerleri sağlamanız gerekir.

`SCROLLINFO`Yapı, en düşük ve en yüksek kaydırma konumları, sayfa boyutu ve kaydırma kutusunun konumu (Thumb) dahil olmak üzere bir kaydırma çubuğu hakkındaki bilgileri içerir. Yapı varsayılanlarını değiştirme hakkında daha fazla bilgi için Windows SDK ' daki [Scrollinfo](/windows/win32/api/winuser/ns-winuser-scrollinfo) yapısı konusuna bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CScrollBar#3](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]

## <a name="cscrollbarsetscrollpos"></a><a name="setscrollpos"></a>CScrollBar:: SetScrollPos

Bir kaydırma kutusunun geçerli konumunu *nPos* tarafından belirtilen şekilde ayarlar ve belirtilmişse, kaydırma çubuğunu yeni konumu yansıtacak şekilde yeniden çizer.

```
int SetScrollPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Kaydırma kutusunun yeni konumunu belirtir. Kaydırma aralığı içinde olmalıdır.

*bRedraw*<br/>
Kaydırma çubuğunun yeni konumu yansıtacak şekilde yeniden çizilip çizmeyeceğini belirtir. *BRedraw* true ise, kaydırma çubuğu yeniden çizilir. YANLıŞ ise yeniden çizilmez. Kaydırma çubuğu varsayılan olarak yeniden çizilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa kaydırma kutusunun önceki konumunu belirtir; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kaydırma çubuğunun kısa bir aralıkta iki kez yeniden çizilmesini önlemek için, kaydırma çubuğu başka bir işleve sonraki bir çağrı tarafından yeniden çizildiğinde, *bRedraw* değerini false olarak ayarlayın.

### <a name="example"></a>Örnek

  [CScrollBar:: SetScrollRange](#setscrollrange)örneğine bakın.

## <a name="cscrollbarsetscrollrange"></a><a name="setscrollrange"></a>CScrollBar:: SetScrollRange

Verilen kaydırma çubuğu için en düşük ve en yüksek konum değerlerini ayarlar.

```cpp
void SetScrollRange(
    int nMinPos,
    int nMaxPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*nMinPos*<br/>
En düşük kaydırma konumunu belirtir.

*nMaxPos*<br/>
En fazla kaydırma konumunu belirtir.

*bRedraw*<br/>
Kaydırma çubuğunun değişikliği yansıtacak şekilde yeniden çizilip çizmeyeceğini belirtir. *BRedraw* true ise, kaydırma çubuğu yeniden çizilir; YANLıŞSA, yeniden çizilmez. Varsayılan olarak yeniden çizilir.

### <a name="remarks"></a>Açıklamalar

Standart kaydırma çubuklarını gizlemek için *nMinPos* ve *nMaxPos* 'u 0 olarak ayarlayın.

Bir kaydırma çubuğu bildirim iletisini işlerken kaydırma çubuğunu gizlemek için bu işlevi çağırmayın.

Üye işlevine yapılan bir `SetScrollRange` çağrıyı hemen takip eden bir çağrı varsa `SetScrollPos` , kaydırma çubuğunun iki kez yeniden çizilmesini engellemek Için *bRedraw* ' ı `SetScrollPos` 0 olarak ayarlayın.

*NMinPos* ve *nMaxPos* tarafından belirtilen değerler arasındaki fark 32.767 değerinden büyük olmamalıdır. Bir kaydırma çubuğu denetimi için varsayılan Aralık boştur ( *nMinPos* ve *nMaxPos* 0 ' dır).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CScrollBar#4](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]

## <a name="cscrollbarshowscrollbar"></a><a name="showscrollbar"></a>CScrollBar:: ShowScrollBar

Bir kaydırma çubuğunu gösterir veya gizler.

```cpp
void ShowScrollBar(BOOL bShow = TRUE);
```

### <a name="parameters"></a>Parametreler

*bShow*<br/>
Kaydırma çubuğunun gösterilip gösterilmeyeceğini veya gizlenmeyeceğini belirtir. Bu parametre TRUE ise, kaydırma çubuğu gösterilir; Aksi halde gizli olur.

### <a name="remarks"></a>Açıklamalar

Bir uygulama, bir kaydırma çubuğu bildirim iletisini işlerken bir kaydırma çubuğunu gizlemek için bu işlevi çağırmamalıdır.

### <a name="example"></a>Örnek

  [CScrollBar:: Create](#create)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CButton sınıfı](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox sınıfı](../../mfc/reference/ccombobox-class.md)<br/>
[Cedıt sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CListBox sınıfı](../../mfc/reference/clistbox-class.md)<br/>
[CStatic sınıfı](../../mfc/reference/cstatic-class.md)<br/>
[CDialog sınıfı](../../mfc/reference/cdialog-class.md)
