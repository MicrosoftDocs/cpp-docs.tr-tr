---
title: CScrollBar Sınıfı
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
ms.openlocfilehash: 761d7e9db650c6d95e916c85bd7456d9b1c647c5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318529"
---
# <a name="cscrollbar-class"></a>CScrollBar Sınıfı

Windows kaydırma çubuğu denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CScrollBar : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CScrollBar::CScrollBar](#cscrollbar)|Bir `CScrollBar` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CScrollBar::Oluştur](#create)|Windows kaydırma çubuğunu oluşturur ve `CScrollBar` nesneye bağlar.|
|[CScrollBar::EnableScrollBar](#enablescrollbar)|Kaydırma çubuğunun bir veya her iki okunu etkinleştirir veya devre dışı kılabilir.|
|[CScrollBar::GetScrollBarInfo](#getscrollbarinfo)|Bir `SCROLLBARINFO` yapı kullanarak kaydırma çubuğu hakkındaki bilgileri alır.|
|[CScrollBar::GetScrollInfo](#getscrollinfo)|Kaydırma çubuğu yla ilgili bilgileri alır.|
|[CScrollBar::GetScrollLimit](#getscrolllimit)|Kaydırma çubuğunun sınırını alır|
|[CScrollBar::GetScrollPos](#getscrollpos)|Kaydırma kutusunun geçerli konumunu alır.|
|[CScrollBar::GetScrollRange](#getscrollrange)|Verilen kaydırma çubuğu için geçerli minimum ve maksimum kaydırma çubuğu konumlarını alır.|
|[CScrollBar::SetScrollInfo](#setscrollinfo)|Kaydırma çubuğu yla ilgili bilgileri ayarlar.|
|[CScrollBar::SetScrollPos](#setscrollpos)|Kaydırma kutusunun geçerli konumunu ayarlar.|
|[CScrollBar::SetScrollRange](#setscrollrange)|Verilen kaydırma çubuğu için minimum ve maksimum konum değerlerini ayarlar.|
|[CScrollBar::ShowScrollBar](#showscrollbar)|Kaydırma çubuğugösterir veya gizler.|

## <a name="remarks"></a>Açıklamalar

İki adımda kaydırma çubuğu denetimi oluşturursunuz. Önce `CScrollBar` nesneyi oluşturmak `CScrollBar` için oluşturucuyu çağırın, ardından Windows kaydırma çubuğu denetimini oluşturmak `CScrollBar` için Üye [Oluştur](#create) işlevini çağırın ve nesneye takın.

Bir iletişim `CScrollBar` kutusu içinde (iletişim kaynağı aracılığıyla) bir `CScrollBar` nesne oluşturursanız, kullanıcı iletişim kutusunu kapattığında nesne otomatik olarak yok edilir.

Bir pencere `CScrollBar` içinde bir nesne oluşturursanız, onu yok etmek de gerekebilir.

Yığının `CScrollBar` üzerinde nesne oluşturursanız, otomatik olarak yok edilir. Nesneyi `CScrollBar` **yeni** işlevi kullanarak yığında oluşturursanız, kullanıcı Windows kaydırma çubuğunu sonlandırdığında nesneyi yok etmek için nesneyi **sil'i** aramanız gerekir.

Nesnede `CScrollBar` herhangi bir bellek ayırırsanız, `CScrollBar` ayırmaları elden çıkarmak için yıkıcı geçersiz kılın.

Kullanma `CScrollBar`hakkında ilgili ilgili bilgiler için [Denetimler'e](../../mfc/controls-mfc.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CScrollBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cscrollbarcreate"></a><a name="create"></a>CScrollBar::Oluştur

Windows kaydırma çubuğunu oluşturur ve `CScrollBar` nesneye bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Kaydırma çubuğunun stilini belirtir. Kaydırma çubuğu [stillerinin](../../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles) herhangi bir birleşimini kaydırma çubuğuna uygulayın.

*Rect*<br/>
Kaydırma çubuğunun boyutunu ve konumunu belirtir. Bir `RECT` yapı veya nesne `CRect` olabilir.

*pParentWnd*<br/>
Kaydırma çubuğunun ana penceresini, genellikle `CDialog` bir nesneyi belirtir. NULL olmamalıdır.

*Nıd*<br/>
Kaydırma çubuğunun kontrol kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CScrollBar` iki adımda inşa ee. İlk olarak, nesneyi oluşturan yapıcıyı `CScrollBar` arayın; sonra, `Create`ilişkili Windows kaydırma çubuğunu oluşturur ve başharfe bağlar `CScrollBar` ve nesneye bağlar.

Aşağıdaki [pencere stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles) kaydırma çubuğuna uygulayın:

- WS_CHILD Her Zaman

- WS_VISIBLE Genellikle

- WS_DISABLED Nadiren

- WS_GROUP Denetimleri gruplandırmak için

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CScrollBar#1](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]

## <a name="cscrollbarcscrollbar"></a><a name="cscrollbar"></a>CScrollBar::CScrollBar

Bir `CScrollBar` nesne inşa eder.

```
CScrollBar();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi oluşturduktan sonra, `Create` Windows kaydırma çubuğunu oluşturmak ve başlatmak için üye işlevi arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CScrollBar#2](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]

## <a name="cscrollbarenablescrollbar"></a><a name="enablescrollbar"></a>CScrollBar::EnableScrollBar

Kaydırma çubuğunun bir veya her iki okunu etkinleştirir veya devre dışı kılabilir.

```
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```

### <a name="parameters"></a>Parametreler

*nArrowFlags*<br/>
Kaydırma oklarının etkin veya devre dışı bırakıldığını ve hangi okların etkin veya devre dışı bırakıldığını belirtir. Bu parametre aşağıdaki değerlerden biri olabilir:

- ESB_ENABLE_BOTH Kaydırma çubuğunun her iki okunu da etkinleştirilir.

- ESB_DISABLE_LTUP yatay kaydırma çubuğunun sol okunu veya dikey kaydırma çubuğunun yukarı okunu devre dışı bırakmaz.

- ESB_DISABLE_RTDN yatay kaydırma çubuğunun sağ okunu veya dikey kaydırma çubuğunun aşağı okunu devre dışı kılabilir.

- ESB_DISABLE_BOTH kaydırma çubuğunun her iki okunu da devre dışı kılabilir.

### <a name="return-value"></a>Dönüş Değeri

Oklar belirtildiği gibi etkin veya devre dışı bırakılırsa sıfıra inmez; aksi takdirde 0, hangi oklar zaten istenen durumda olduğunu veya bir hata oluştuğunu gösterir.

### <a name="example"></a>Örnek

  CScrollBar örneğine [bakın:SetScrollRange.](#setscrollrange)

## <a name="cscrollbargetscrollbarinfo"></a><a name="getscrollbarinfo"></a>CScrollBar::GetScrollBarInfo

Yapının `SCROLLBARINFO` kaydırma çubuğu hakkında koruduğu bilgileri alır.

```
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;
```

### <a name="parameters"></a>Parametreler

*pScrollInfo*<br/>
[SCROLLBARINFO](/windows/win32/api/winuser/ns-winuser-scrollbarinfo) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [SBM_SCROLLBARINFO](/windows/win32/Controls/sbm-getscrollbarinfo) iletisinin işlevselliğini taklit eder.

## <a name="cscrollbargetscrollinfo"></a><a name="getscrollinfo"></a>CScrollBar::GetScrollInfo

Yapının `SCROLLINFO` kaydırma çubuğu hakkında koruduğu bilgileri alır.

```
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    UINT nMask = SIF_ALL);
```

### <a name="parameters"></a>Parametreler

*lpScrollInfo*<br/>
[SCROLLINFO](/windows/win32/api/winuser/ns-winuser-scrollinfo) yapısına işaretçi. Bu yapı hakkında daha fazla bilgi için Windows SDK'ya bakın.

*nMask*<br/>
Alınacak kaydırma çubuğu parametrelerini belirtir. Tipik kullanım, SIF_ALL, SIF_PAGE, SIF_POS, SIF_TRACKPOS ve SIF_RANGE bir arada belirtir. nMask değerleri hakkında daha fazla bilgi için bkz. `SCROLLINFO`

### <a name="return-value"></a>Dönüş Değeri

İleti herhangi bir değer aldıysa, iade TRUE'dur. Aksi takdirde, BU YANLIŞ olduğunu.

### <a name="remarks"></a>Açıklamalar

`GetScrollInfo`uygulamaların 32 bit kaydırma konumlarını kullanmasını sağlar.

[SCROLLINFO](/windows/win32/api/winuser/ns-winuser-scrollinfo) yapısı, minimum ve maksimum kaydırma konumları, sayfa boyutu ve kaydırma kutusunun (başparmak) konumu da dahil olmak üzere bir kaydırma çubuğu hakkında bilgi içerir. Yapı `SCROLLINFO` varsayılanlarını değiştirme hakkında daha fazla bilgi için Windows SDK'daki yapı konusuna bakın.

Kaydırma çubuğu konumunu gösteren MFC Windows ileti işleyicileri, [CWnd::OnHScroll ve [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll), yalnızca 16 bit konum verisi sağlar. `GetScrollInfo`ve `SetScrollInfo` 32 bit kaydırma çubuğu konumu verileri sağlayın. Böylece, bir uygulama `GetScrollInfo` ya `CWnd::OnHScroll` işleme `CWnd::OnVScroll` sırasında arama veya 32-bit kaydırma çubuğu konumu verileri elde etmek için.

### <a name="example"></a>Örnek

  CWnd örneğine [bakın:OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

## <a name="cscrollbargetscrolllimit"></a><a name="getscrolllimit"></a>CScrollBar::GetScrollLimit

Kaydırma çubuğunun maksimum kaydırma konumunu alır.

```
int GetScrollLimit();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa kaydırma çubuğunun maksimum konumunu belirtir; aksi takdirde 0.

### <a name="example"></a>Örnek

  CWnd örneğine [bakın:OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

## <a name="cscrollbargetscrollpos"></a><a name="getscrollpos"></a>CScrollBar::GetScrollPos

Kaydırma kutusunun geçerli konumunu alır.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa kaydırma kutusunun geçerli konumunu belirtir; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Geçerli konum, geçerli kaydırma aralığına bağlı olarak göreli bir değerdir. Örneğin, kaydırma aralığı 100 ile 200 arasındaysa ve kaydırma kutusu çubuğun ortasındaysa, geçerli konum 150'dir.

### <a name="example"></a>Örnek

  CWnd örneğine [bakın:OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

## <a name="cscrollbargetscrollrange"></a><a name="getscrollrange"></a>CScrollBar::GetScrollRange

Verilen kaydırma çubuğu için geçerli minimum ve maksimum kaydırma çubuğu konumlarını *lpMinPos* ve *lpMaxPos*tarafından belirtilen konumlara kopyalar.

```
void GetScrollRange(
    LPINT lpMinPos,
    LPINT lpMaxPos) const;
```

### <a name="parameters"></a>Parametreler

*lpMinPos*<br/>
Minimum konumu almak için olan sonsayı değişkenine işaret ediyor.

*lpMaxPos*<br/>
Maksimum konumu almak için, sondaki değişkene işaret ediyor.

### <a name="remarks"></a>Açıklamalar

Kaydırma çubuğu denetimi için varsayılan aralık boştur (her iki değer de 0'dır).

### <a name="example"></a>Örnek

  CWnd örneğine [bakın:OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).

## <a name="cscrollbarsetscrollinfo"></a><a name="setscrollinfo"></a>CScrollBar::SetScrollInfo

Yapının `SCROLLINFO` kaydırma çubuğu hakkında koruduğu bilgileri ayarlar.

```
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpScrollInfo*<br/>
[SCROLLINFO](/windows/win32/api/winuser/ns-winuser-scrollinfo) yapısına işaretçi.

*bRedraw*<br/>
Kaydırma çubuğunun yeni bilgileri yansıtacak şekilde yeniden çizilip çizilmeyeceğini belirtir. *bRedraw* TRUE ise kaydırma çubuğu yeniden çizilir. YANLIŞ ise, yeniden çizilmez. Kaydırma çubuğu varsayılan olarak yeniden çizilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, dönüş DOĞRUolur. Aksi takdirde, BU YANLIŞ olduğunu.

### <a name="remarks"></a>Açıklamalar

Bayrak değerleri de dahil `SCROLLINFO` olmak üzere yapı parametrelerinin gerektirdiği değerleri sağlamanız gerekir.

Yapı, `SCROLLINFO` minimum ve maksimum kaydırma konumları, sayfa boyutu ve kaydırma kutusunun (başparmak) konumu da dahil olmak üzere bir kaydırma çubuğu hakkında bilgi içerir. Yapı varsayılanlarını değiştirme hakkında daha fazla bilgi için Windows SDK'daki [SCROLLINFO](/windows/win32/api/winuser/ns-winuser-scrollinfo) yapı konusuna bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CScrollBar#3](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]

## <a name="cscrollbarsetscrollpos"></a><a name="setscrollpos"></a>CScrollBar::SetScrollPos

Kaydırma kutusunun geçerli konumunu *nPos* tarafından belirtilen konuma ayarlar ve belirtildiği takdirde kaydırma çubuğunu yeni konumu yansıtacak şekilde yeniden çizer.

```
int SetScrollPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Kaydırma kutusu için yeni konumu belirtir. Kaydırma aralığında olmalı.

*bRedraw*<br/>
Kaydırma çubuğunun yeni konumu yansıtacak şekilde yeniden çizilip çizilmeyeceğini belirtir. *bRedraw* TRUE ise kaydırma çubuğu yeniden çizilir. YANLIŞ ise, yeniden çizilmez. Kaydırma çubuğu varsayılan olarak yeniden çizilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa kaydırma kutusunun önceki konumunu belirtir; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kaydırma çubuğunun kısa bir aralık içinde iki kez yeniden çizilmesini önlemek için sonraki bir çağrı yla kaydırma çubuğu başka bir işleve çağrı yapıldığında *bRedraw'ı* FALSE olarak ayarlayın.

### <a name="example"></a>Örnek

  CScrollBar örneğine [bakın:SetScrollRange.](#setscrollrange)

## <a name="cscrollbarsetscrollrange"></a><a name="setscrollrange"></a>CScrollBar::SetScrollRange

Verilen kaydırma çubuğu için minimum ve maksimum konum değerlerini ayarlar.

```
void SetScrollRange(
    int nMinPos,
    int nMaxPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*nMinPos*<br/>
Minimum kaydırma konumunu belirtir.

*nMaxPos*<br/>
Maksimum kaydırma konumunu belirtir.

*bRedraw*<br/>
Kaydırma çubuğunun değişikliği yansıtacak şekilde yeniden çizilip çizilmeyeceğini belirtir. *bRedraw* TRUE ise kaydırma çubuğu yeniden çizilir; FALSE ise, yeniden çizilmez. Varsayılan olarak yeniden çizilir.

### <a name="remarks"></a>Açıklamalar

Standart kaydırma çubuklarını gizlemek için *nMinPos* ve *nMaxPos'u* 0 olarak ayarlayın.

Kaydırma çubuğu bildirim iletisini işlerken kaydırma çubuğunun gizlemesi için bu işlevi aramayın.

Üye işlevine `SetScrollRange` yapılan bir çağrıyı hemen izlerse, `SetScrollPos` kaydırma çubuğunun iki kez yeniden çizilmesini önlemek için *bRedraw'ı* 0 olarak ayarlayın. `SetScrollPos`

*nMinPos* ve *nMaxPos* tarafından belirtilen değerler arasındaki fark 32.767'den büyük olmamalıdır. Kaydırma çubuğu denetimi için varsayılan aralık boştur (hem *nMinPos* hem de *nMaxPos* 0'dır).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CScrollBar#4](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]

## <a name="cscrollbarshowscrollbar"></a><a name="showscrollbar"></a>CScrollBar::ShowScrollBar

Kaydırma çubuğugösterir veya gizler.

```
void ShowScrollBar(BOOL bShow = TRUE);
```

### <a name="parameters"></a>Parametreler

*bGöster*<br/>
Kaydırma çubuğunun gösterip gösterilmediğini veya gizlenip gizlenmediğini belirtir. Bu parametre TRUE ise kaydırma çubuğu gösterilir; aksi takdirde gizlidir.

### <a name="remarks"></a>Açıklamalar

Bir uygulama kaydırma çubuğubildirim iletisini işlerken kaydırma çubuğugizlemek için bu işlevi aramamalıdır.

### <a name="example"></a>Örnek

  CScrollBar için örneğe [bakın:Oluştur](#create).

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CButton Sınıfı](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox Sınıfı](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CListBox Sınıfı](../../mfc/reference/clistbox-class.md)<br/>
[Cstatic Sınıfı](../../mfc/reference/cstatic-class.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
