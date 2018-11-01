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
ms.openlocfilehash: 3b8e7dc78ddfa22097c97fb4e97fff92f0984c07
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571268"
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
|[CScrollBar::CScrollBar](#cscrollbar)|Oluşturur bir `CScrollBar` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CScrollBar::Create](#create)|Windows kaydırma çubuğu oluşturur ve ona ekler `CScrollBar` nesne.|
|[CScrollBar::EnableScrollBar](#enablescrollbar)|Etkinleştirir veya bir kaydırma çubuğunun biri veya ikisi de okları devre dışı bırakır.|
|[CScrollBar::GetScrollBarInfo](#getscrollbarinfo)|Kaydırma çubuğunu kullanarak hakkındaki bilgileri alır bir `SCROLLBARINFO` yapısı.|
|[CScrollBar::GetScrollInfo](#getscrollinfo)|Kaydırma çubuğu hakkında bilgi alır.|
|[CScrollBar::GetScrollLimit](#getscrolllimit)|Kaydırma çubuğu sınırını alır.|
|[CScrollBar::GetScrollPos](#getscrollpos)|Bir kaydırma kutusuna geçerli konumunu alır.|
|[CScrollBar::GetScrollRange](#getscrollrange)|Belirtilen kaydırma çubuğu için geçerli minimum ve maksimum kaydırma çubuğu konumları alır.|
|[CScrollBar::SetScrollInfo](#setscrollinfo)|Kaydırma çubuğu hakkında bilgi ayarlar.|
|[CScrollBar::SetScrollPos](#setscrollpos)|Bir kaydırma kutusuna geçerli konumunu ayarlar.|
|[CScrollBar::SetScrollRange](#setscrollrange)|Belirtilen kaydırma çubuğu için minimum ve maksimum konum değerleri ayarlar.|
|[CScrollBar::ShowScrollBar](#showscrollbar)|Bir kaydırma çubuğu gizler veya gösterir.|

## <a name="remarks"></a>Açıklamalar

Bir kaydırma çubuğu denetim iki adımda oluşturmanız. İlk olarak, oluşturucusunu `CScrollBar` oluşturmak için `CScrollBar` nesnesi ve ardından arama [Oluştur](#create) Windows kaydırma çubuğu denetimi oluşturun ve buna eklemek için üye işlevini `CScrollBar` nesne.

Oluşturursanız, bir `CScrollBar` nesnesi içinde bir iletişim kutusu (iletişim kaynak) aracılığıyla `CScrollBar` kullanıcı iletişim kutusu kapandığında otomatik olarak yok.

Oluşturursanız, bir `CScrollBar` nesnesi bir pencere içinde de gerekebilir, yok.

Oluşturursanız `CScrollBar` yığında nesne otomatik olarak bozulur. Oluşturursanız `CScrollBar` kullanarak yığında nesne **yeni** işlevini çağırmalıdır **Sil** kullanıcı Windows kaydırma çubuğu sonlandırıldığında yok etmek için nesne üzerinde.

Herhangi bir bellek ayırdığınızda `CScrollBar` nesne, geçersiz kılma `CScrollBar` ayrılmasını atmayı yıkıcı.

Kullanma hakkında ilgili bilgi `CScrollBar`, bkz: [denetimleri](../../mfc/controls-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CScrollBar`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="create"></a>  CScrollBar::Create

Windows kaydırma çubuğu oluşturur ve ona ekler `CScrollBar` nesne.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Belirtir kaydırma çubuğu stili. Herhangi bir birleşimini uygulamak [kaydırma çubuğu stilleri](../../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles) kaydırma çubuğu.

*Rect*<br/>
Kaydırma çubuğunun boyutunu ve konumunu belirtir. Olabilir bir `RECT` yapısı veya `CRect` nesne.

*pParentWnd*<br/>
Belirtir kaydırma çubuğunun üst penceresine, genellikle bir `CDialog` nesne. NULL olmamalıdır.

*nID*<br/>
Kaydırma çubuğu denetiminin kimliği.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CScrollBar` iki adımda nesne. İlk olarak, oluşturan oluşturucu çağrısı `CScrollBar` nesne; ardından çağırarak `Create`, oluşturan ve ilişkili Windows kaydırma çubuğu başlatır ve ekler `CScrollBar` nesne.

Aşağıdaki uygulama [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) kaydırma çubuğu için:

- WS_CHILD her zaman

- Ws_vısıble genellikle

- Ws_dısabled nadiren

- WS_GROUP grup denetimleri için

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CScrollBar#1](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]

##  <a name="cscrollbar"></a>  CScrollBar::CScrollBar

Oluşturur bir `CScrollBar` nesne.

```
CScrollBar();
```

### <a name="remarks"></a>Açıklamalar

Nesne oluşturduktan sonra çağrı `Create` oluşturmak ve Windows kaydırma çubuğu başlatmak için üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CScrollBar#2](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]

##  <a name="enablescrollbar"></a>  CScrollBar::EnableScrollBar

Etkinleştirir veya bir kaydırma çubuğunun biri veya ikisi de okları devre dışı bırakır.

```
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```

### <a name="parameters"></a>Parametreler

*nArrowFlags*<br/>
Kaydırma okları etkin veya devre dışı bırakılan ve hangi okları etkin veya devre dışı belirtir. Bu parametre aşağıdaki değerlerden biri olabilir:

- Her iki ok bir kaydırma çubuğunun ESB_ENABLE_BOTH sağlar.

- Yatay kaydırma çubuğunun sol ok ya da dikey kaydırma çubuğunun yukarı ok ESB_DISABLE_LTUP devre dışı bırakır.

- Yatay kaydırma çubuğunun sağ ok ya da dikey kaydırma çubuğu aşağı okunu ESB_DISABLE_RTDN devre dışı bırakır.

- Her iki ok bir kaydırma çubuğunun ESB_DISABLE_BOTH devre dışı bırakır.

### <a name="return-value"></a>Dönüş Değeri

Oklar etkin veya devre dışı olarak belirtilen olursa sıfır dışı; Aksi durumda 0, oklar istenen durumda olduğunu veya bir hata oluştuğunu gösterir.

### <a name="example"></a>Örnek

  Örneğin bakın [CScrollBar::SetScrollRange](#setscrollrange).

##  <a name="getscrollbarinfo"></a>  CScrollBar::GetScrollBarInfo

Bu bilgileri alır, `SCROLLBARINFO` yapısı bir kaydırma çubuğu hakkında tutar.

```
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;
```

### <a name="parameters"></a>Parametreler

*pScrollInfo*<br/>
Bir işaretçi [SCROLLBARINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollbarinfo) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi işlevselliğine öykünür [SBM_SCROLLBARINFO](/windows/desktop/Controls/sbm-getscrollbarinfo) Windows SDK içinde açıklandığı gibi ileti.

##  <a name="getscrollinfo"></a>  CScrollBar::GetScrollInfo

Bu bilgileri alır, `SCROLLINFO` yapısı bir kaydırma çubuğu hakkında tutar.

```
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    UINT nMask = SIF_ALL);
```

### <a name="parameters"></a>Parametreler

*lpScrollInfo*<br/>
Bir işaretçi bir [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) yapısı. Bu yapı hakkında daha fazla bilgi için Windows SDK'sı bakın.

*nMask*<br/>
Alınacak kaydırma çubuğu parametreleri belirtir. Tipik kullanım, SIF_ALL, SIF_PAGE, SIF_POS SIF_TRACKPOS ve SIF_RANGE bir birleşimini belirtir. Bkz: `SCROLLINFO` nMask değerler hakkında daha fazla bilgi için.

### <a name="return-value"></a>Dönüş Değeri

İleti alınan herhangi bir değeri, dönüş değeri true'dur. Aksi takdirde yanlış olur.

### <a name="remarks"></a>Açıklamalar

`GetScrollInfo` uygulamaların 32-bit kaydırma konumları kullanmasını sağlar.

[SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) yapısı bir kaydırma çubuğu, minimum ve maksimum konumları, sayfa boyutu ve konumu (Flash) kaydırma kutusunun kaydırma da dahil olmak üzere ilgili bilgiler içerir. Bkz: `SCROLLINFO` yapı varsayılanları değiştirme hakkında daha fazla bilgi için Windows SDK yapısı konuda.

MFC Windows ileti işleyicileri kaydırma çubuğu konumunu belirten [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) ve [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll), yalnızca 16 bitlik konum verileri sağlar. `GetScrollInfo` ve `SetScrollInfo` 32 bit kaydırma çubuğu konum verileri sağlar. Bu nedenle, bir uygulama çağırabilirsiniz `GetScrollInfo` ya da işlenirken `CWnd::OnHScroll` veya `CWnd::OnVScroll` 32-bit kaydırma çubuğu konum verileri elde edilir.

### <a name="example"></a>Örnek

  Örneğin bakın [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

##  <a name="getscrolllimit"></a>  CScrollBar::GetScrollLimit

Konum kaydırma çubuğunun kaydırma maksimum alır.

```
int GetScrollLimit();
```

### <a name="return-value"></a>Dönüş Değeri

Bir kaydırma çubuğunun başarılı olursa maksimum konumunu belirler; Aksi durumda 0.

### <a name="example"></a>Örnek

  Örneğin bakın [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

##  <a name="getscrollpos"></a>  CScrollBar::GetScrollPos

Bir kaydırma kutusuna geçerli konumunu alır.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırma kutusunun başarılı olursa geçerli konumunu belirtir. Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Geçerli konumun geçerli kaydırma aralığı bağlı göreli bir değerdir. Örneğin, 100 ila 200 kaydırma aralığı ve kaydırma kutusunun çubuğu ortasında ise, geçerli 150 konumdur.

### <a name="example"></a>Örnek

  Örneğin bakın [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

##  <a name="getscrollrange"></a>  CScrollBar::GetScrollRange

Belirtilen kaydırma çubuğu için geçerli minimum ve maksimum kaydırma çubuğu konumları tarafından belirtilen konuma kopyalar *lpMinPos* ve *lpMaxPos*.

```
void GetScrollRange(
    LPINT lpMinPos,
    LPINT lpMaxPos) const;
```

### <a name="parameters"></a>Parametreler

*lpMinPos*<br/>
En düşük konumu almak için tamsayı değişkenine işaret eder.

*lpMaxPos*<br/>
En fazla konumu almak için tamsayı değişkenine işaret eder.

### <a name="remarks"></a>Açıklamalar

Bir kaydırma çubuğu denetimi için varsayılan aralığı boş (her iki değeri 0 olan).

### <a name="example"></a>Örnek

  Örneğin bakın [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

##  <a name="setscrollinfo"></a>  CScrollBar::SetScrollInfo

Bilgi ayarlayan `SCROLLINFO` yapısı bir kaydırma çubuğu hakkında tutar.

```
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpScrollInfo*<br/>
Bir işaretçi bir [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) yapısı.

*bRedraw*<br/>
Kaydırma çubuğunu yeni bilgileri yansıtacak şekilde yeniden olup olmadığını belirtir. Varsa *bRedraw* doğru ise, kaydırma çubuğu yeniden çizilir. FALSE ise, çizilmez. Kaydırma çubuğu varsayılan olarak çizilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, dönüş değeri true'dur. Aksi takdirde yanlış olur.

### <a name="remarks"></a>Açıklamalar

Gerekli değerler sağlamanız gereken `SCROLLINFO` parametreleri bayrak değerleri dahil olmak üzere, yapı.

`SCROLLINFO` Yapısı bir kaydırma çubuğu, minimum ve maksimum konumları, sayfa boyutu ve konumu (Flash) kaydırma kutusunun kaydırma da dahil olmak üzere ilgili bilgiler içerir. Bkz: [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) yapı varsayılanları değiştirme hakkında daha fazla bilgi için Windows SDK yapısı konuda.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CScrollBar#3](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]

##  <a name="setscrollpos"></a>  CScrollBar::SetScrollPos

Tarafından belirtilen kaydırma kutusunun konumunu ayarlar *nPos* ve belirtilmişse kaydırma çubuğundaki yeni konumunu gösterecek şekilde yeniden çizer.

```
int SetScrollPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Kaydırma kutusu için yeni konumunu belirtir. Kaydırma aralığında olmalıdır.

*bRedraw*<br/>
Kaydırma çubuğunu yeni konumunu gösterecek şekilde yeniden olup olmadığını belirtir. Varsa *bRedraw* doğru ise, kaydırma çubuğu yeniden çizilir. FALSE ise, çizilmez. Kaydırma çubuğu varsayılan olarak çizilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa kaydırma kutusunun önceki konumu belirtir. Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Ayarlama *bRedraw* FALSE olduğunda kaydırma çubuğu çizilmesini iki kez kısa bir süre içinde yeniden kaydırma çubuğu önlemek için başka bir işleve sonraki çağrı tarafından.

### <a name="example"></a>Örnek

  Örneğin bakın [CScrollBar::SetScrollRange](#setscrollrange).

##  <a name="setscrollrange"></a>  CScrollBar::SetScrollRange

Belirtilen kaydırma çubuğu için minimum ve maksimum konum değerleri ayarlar.

```
void SetScrollRange(
    int nMinPos,
    int nMaxPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*nMinPos*<br/>
En düşük konumu kaydırma belirtir.

*nMaxPos*<br/>
En büyük kaydırma konumunu belirtir.

*bRedraw*<br/>
Kaydırma çubuğu değişikliği yansıtacak şekilde yeniden olup olmadığını belirtir. Varsa *bRedraw* doğru ise, kaydırma çubuğu çizilir; FALSE ise değil çizilir. Bu, varsayılan olarak çizilir.

### <a name="remarks"></a>Açıklamalar

Ayarlama *nMinPos* ve *nMaxPos* standart kaydırma çubukları gizlemek için 0.

Bir kaydırma çubuğu bildirim iletisi işlenirken bir kaydırma çubuğunu gizlemek için bu işlevi çağırmanız gerekmez.

Bir çağrı, `SetScrollRange` hemen takip `SetScrollPos` üye işlevini ayarlama *bRedraw* içinde `SetScrollPos` kaydırma çubuğundaki iki kez yeniden engellemek için 0.

Tarafından belirtilen değeri arasındaki farkı *nMinPos* ve *nMaxPos* 32.767 büyük olmamalıdır. Bir kaydırma çubuğu denetimi için varsayılan aralığı boş (her ikisi de *nMinPos* ve *nMaxPos* 0).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CScrollBar#4](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]

##  <a name="showscrollbar"></a>  CScrollBar::ShowScrollBar

Bir kaydırma çubuğu gizler veya gösterir.

```
void ShowScrollBar(BOOL bShow = TRUE);
```

### <a name="parameters"></a>Parametreler

*bBilgi Göster*<br/>
Kaydırma çubuğu gösterilen veya gizli olup olmadığını belirtir. Bu parametre TRUE ise, kaydırma çubuğu gösterilir; Aksi takdirde gizlenir.

### <a name="remarks"></a>Açıklamalar

Bir uygulama bir kaydırma çubuğu bildirim iletisi işlenirken bir kaydırma çubuğunu gizlemek için bu işlevi çağırmamanız gerekir.

### <a name="example"></a>Örnek

  Örneğin bakın [CScrollBar::Create](#create).

## <a name="see-also"></a>Ayrıca Bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CButton Sınıfı](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox Sınıfı](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CListBox Sınıfı](../../mfc/reference/clistbox-class.md)<br/>
[CStatic Sınıfı](../../mfc/reference/cstatic-class.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
