---
description: 'Daha fazla bilgi edinin: CRectTracker sınıfı'
title: CRectTracker sınıfı
ms.date: 11/19/2018
f1_keywords:
- CRectTracker
- AFXEXT/CRectTracker
- AFXEXT/CRectTracker::CRectTracker
- AFXEXT/CRectTracker::AdjustRect
- AFXEXT/CRectTracker::Draw
- AFXEXT/CRectTracker::DrawTrackerRect
- AFXEXT/CRectTracker::GetHandleMask
- AFXEXT/CRectTracker::GetTrueRect
- AFXEXT/CRectTracker::HitTest
- AFXEXT/CRectTracker::NormalizeHit
- AFXEXT/CRectTracker::OnChangedRect
- AFXEXT/CRectTracker::SetCursor
- AFXEXT/CRectTracker::Track
- AFXEXT/CRectTracker::TrackRubberBand
- AFXEXT/CRectTracker::m_nHandleSize
- AFXEXT/CRectTracker::m_nStyle
- AFXEXT/CRectTracker::m_rect
- AFXEXT/CRectTracker::m_sizeMin
helpviewer_keywords:
- CRectTracker [MFC], CRectTracker
- CRectTracker [MFC], AdjustRect
- CRectTracker [MFC], Draw
- CRectTracker [MFC], DrawTrackerRect
- CRectTracker [MFC], GetHandleMask
- CRectTracker [MFC], GetTrueRect
- CRectTracker [MFC], HitTest
- CRectTracker [MFC], NormalizeHit
- CRectTracker [MFC], OnChangedRect
- CRectTracker [MFC], SetCursor
- CRectTracker [MFC], Track
- CRectTracker [MFC], TrackRubberBand
- CRectTracker [MFC], m_nHandleSize
- CRectTracker [MFC], m_nStyle
- CRectTracker [MFC], m_rect
- CRectTracker [MFC], m_sizeMin
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
ms.openlocfilehash: 8406b6b45a99ca2e1816cb650f243fcea2db8ddc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343026"
---
# <a name="crecttracker-class"></a>CRectTracker sınıfı

Bir öğenin farklı fashiler halinde görüntülenmesine, taşınmasına ve yeniden boyutlandırılabilmesini sağlar.

## <a name="syntax"></a>Syntax

```
class CRectTracker
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRectTracker:: CRectTracker](#crecttracker)|Bir `CRectTracker` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRectTracker:: AdjustRect](#adjustrect)|Dikdörtgen yeniden boyutlandırılırken çağırılır.|
|[CRectTracker::D RAW](#draw)|Dikdörtgeni işler.|
|[CRectTracker::D rawTrackerRect](#drawtrackerrect)|Bir nesnenin kenarlığını çizerken çağırılır `CRectTracker` .|
|[CRectTracker:: GetHandleMask](#gethandlemask)|Bir `CRectTracker` öğenin yeniden boyutlandırma tutamaçlarının maskesini almak için çağırılır.|
|[CRectTracker:: GetTrueRect](#gettruerect)|Yeniden boyutlandırma tutamaçları dahil olmak üzere dikdörtgenin genişliğini ve yüksekliğini döndürür.|
|[CRectTracker:: HitTest](#hittest)|Nesneyle ilgili imlecin geçerli konumunu döndürür `CRectTracker` .|
|[CRectTracker:: NormalizeHit](#normalizehit)|İsabet sınama kodunu normalleştirir.|
|[CRectTracker:: OnChangedRect](#onchangedrect)|Dikdörtgen yeniden boyutlandırılırken veya taşındığında çağırılır.|
|[CRectTracker:: SetCursor](#setcursor)|İmleci dikdörtgen üzerinde konumuna göre ayarlar.|
|[CRectTracker:: Track](#track)|Kullanıcının dikdörtgeni işlemesini sağlar.|
|[CRectTracker:: TrackRubberBand](#trackrubberband)|Kullanıcının seçimi "lastik" kullanmasına izin verir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CRectTracker:: m_nHandleSize](#m_nhandlesize)|Yeniden boyutlandırma tutamaçlarının boyutunu belirler.|
|[CRectTracker:: m_nStyle](#m_nstyle)|İzleyicide geçerli stil (ler) i.|
|[CRectTracker:: m_rect](#m_rect)|Dikdörtgenin geçerli konumu (piksel cinsinden).|
|[CRectTracker:: m_sizeMin](#m_sizemin)|Minimum dikdörtgen genişliğini ve yüksekliğini belirler.|

## <a name="remarks"></a>Açıklamalar

`CRectTracker` taban sınıfına sahip değildir.

Sınıfı, `CRectTracker` bir grafik arabirim kullanarak kullanıcının OLE öğeleriyle etkileşime girmesine izin vermek üzere tasarlansa da, kullanımı OLE özellikli uygulamalarla sınırlı değildir. Bu, bir kullanıcı arabirimi gereken her yerde kullanılabilir.

`CRectTracker` kenarlıklar düz veya noktalı çizgiler olabilir. Öğe, bir taranmış kenarlık veya öğenin farklı durumlarını göstermek üzere taranmış bir desenli kaplama olabilir. Öğenin dışına veya iç kenarlığına sekiz yeniden boyutlandırma tutamacı yerleştirebilirsiniz. (Yeniden boyutlandırma tutamaçlarının açıklaması için bkz. [GetHandleMask](#gethandlemask).) Son olarak, bir `CRectTracker` öğenin yeniden boyutlandırma sırasında yönünü değiştirmenize izin verir.

Kullanmak için `CRectTracker` bir nesnesi oluşturun `CRectTracker` ve hangi görüntüleme durumlarının başlatıldığını belirtin. Daha sonra bu arabirimi, nesneyle ilişkili OLE öğesinin geçerli durumu hakkında kullanıcıya görsel geri bildirim vermek için kullanabilirsiniz `CRectTracker` .

Kullanma hakkında daha fazla bilgi için `CRectTracker` bkz. [trackingseçiciler](../../mfc/trackers.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CRectTracker`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext. h

## <a name="crecttrackeradjustrect"></a><a name="adjustrect"></a> CRectTracker:: AdjustRect

İzleme dikdörtgeni bir yeniden boyutlandırma tutamacı kullanılarak yeniden boyutlandırılırken Framework tarafından çağırılır.

```
virtual void AdjustRect(
    int nHandle,
    LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*Ntanıtıcı*<br/>
Kullanılan tanıtıcının dizini.

*lpRect*<br/>
Dikdörtgenin geçerli boyutuna yönelik işaretçi. (Bir dikdörtgenin boyutu yükseklik ve genişlik ile verilir.)

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan davranışı, dikdörtgenin yönünün yalnızca `Track` ve `TrackRubberBand` ters çevirme ile çağrıldığında değiştirilmesine izin verir.

Sürükleme işlemi sırasında izleme dikdörtgeninin ayarlanmasını denetlemek için bu işlevi geçersiz kılın. Bir yöntem, döndürülmeden önce *lpRect* tarafından belirtilen koordinatları ayarlamadır.

`CRectTracker`Kılavuza uydur veya en boy oranı gibi, tarafından doğrudan desteklenmeyen özel özellikler, bu işlev geçersiz kılınarak uygulanabilir.

## <a name="crecttrackercrecttracker"></a><a name="crecttracker"></a> CRectTracker:: CRectTracker

Bir nesne oluşturur ve başlatır `CRectTracker` .

```
CRectTracker();

CRectTracker(
    LPCRECT lpSrcRect,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*lpSrcRect*<br/>
Dikdörtgen nesnesinin koordinatları.

*nStyle*<br/>
Nesnenin stilini belirtir `CRectTracker` . Aşağıdaki stiller desteklenir:

- `CRectTracker::solidLine` Dikdörtgen kenarlığı için düz bir çizgi kullanın.

- `CRectTracker::dottedLine` Dikdörtgen kenarlığı için noktalı çizgi kullanın.

- `CRectTracker::hatchedBorder` Dikdörtgen kenarlığı için bir hadallanmış model kullanın.

- `CRectTracker::resizeInside` Dikdörtgenin içinde bulunan tutamaçları yeniden boyutlandırın.

- `CRectTracker::resizeOutside` Dikdörtgenin dışında bulunan tutamaçları yeniden boyutlandırın.

- `CRectTracker::hatchInside` Hadallanmış desenler tüm dikdörtgeni kapsıyor.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu, `CRectTracker` nesneyi *lpSrcRect* değerleri ile başlatır ve diğer boyutları sistem varsayılanlarına başlatır. Nesne parametresiz oluşturulduysa, `m_rect` ve `m_nStyle` veri üyeleri başlatılmamış olur.

## <a name="crecttrackerdraw"></a><a name="draw"></a> CRectTracker::D RAW

Dikdörtgenin dış hatlarını ve iç bölgesini çizmek için bu işlevi çağırın.

```cpp
void Draw(CDC* pDC) const;
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Üzerinde çizilecek cihaz bağlamına yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

İzleyici stili, çizimin nasıl yapıldığını belirler. `CRectTracker`Kullanılabilir stiller hakkında daha fazla bilgi için oluşturucusuna bakın.

## <a name="crecttrackerdrawtrackerrect"></a><a name="drawtrackerrect"></a> CRectTracker::D rawTrackerRect

`Track`Veya üye işlevi içindeyken izleyici konumu her değiştiğinde Framework tarafından çağırılır `TrackRubberBand` .

```
virtual void DrawTrackerRect(
    LPCRECT lpRect,
    CWnd* pWndClipTo,
    CDC* pDC,
    CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
`RECT`Çizilecek dikdörtgeni içeren öğesine yönelik işaretçi.

*pWndClipTo*<br/>
Dikdörtgenin kırpılması sırasında kullanılacak pencerenin işaretçisi.

*Kökündeki*<br/>
Üzerinde çizilecek cihaz bağlamına yönelik işaretçi.

*pWnd*<br/>
Çizimin gerçekleşeceği pencerenin işaretçisi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, noktalı bir dikdörtgen çizen öğesine bir çağrısı yapar `CDC::DrawFocusRect` .

İzleme işlemi sırasında farklı geri bildirim sağlamak için bu işlevi geçersiz kılın.

## <a name="crecttrackergethandlemask"></a><a name="gethandlemask"></a> CRectTracker:: GetHandleMask

Çerçeve, bir dikdörtgenin yeniden boyutlandırma tutamaçlarının maskesini almak için bu üye işlevini çağırır.

```
virtual UINT GetHandleMask() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CRectTracker` öğenin yeniden boyutlandırma tutamaçlarının maskesi.

### <a name="remarks"></a>Açıklamalar

Yeniden boyutlandırma tutamaçları dikdörtgenin kenarlarında ve köşelerinde görünür ve kullanıcının dikdörtgenin şeklini ve boyutunu denetlemesine izin verir.

Dikdörtgen, 8 yeniden boyutlandırma tanıtıcı 0-7 ' dir. Her yeniden boyutlandırma tutamacı maskenin içindeki bir bit ile temsil edilir; Bu bitin değeri 2 ^ *n*, burada *n* , yeniden boyutlandırma tanıtıcı numarasıdır. BITS 0-3, sol üst saat yönünde hareket eden köşe yeniden boyutlandırma işleyicilerine karşılık gelir. BITS 4-7, saatin saat yönünde hareket ettirilerek başlayan yan yeniden boyutlandırma işleyicilerine karşılık gelir. Aşağıdaki çizim, bir dikdörtgenin yeniden boyutlandırma tutamaçlarını ve karşılık gelen yeniden boyutlandırma tanıtıcı numaralarını ve değerlerini göstermektedir:

![Tanıtıcı numaralarını yeniden boyutlandır](../../mfc/reference/media/vc35dp1.gif "Tanıtıcı numaralarını yeniden boyutlandır")

Varsayılan uygulama, `GetHandleMask` yeniden boyutlandırma tutamaçlarının görünmesi için bitlerin maskesini döndürür. Tek bit açık ise, karşılık gelen yeniden boyutlandırma tutamacı çizilecektir.

Belirtilen yeniden boyutlandırma tutamaçlarını gizlemek veya göstermek için bu üye işlevini geçersiz kılın.

## <a name="crecttrackergettruerect"></a><a name="gettruerect"></a> CRectTracker:: GetTrueRect

Dikdörtgenin koordinatlarını almak için bu işlevi çağırın.

```cpp
void GetTrueRect(LPRECT lpTrueRect) const;
```

### <a name="parameters"></a>Parametreler

*lpTrueRect*<br/>
`RECT`Nesnenin aygıt koordinatlarını içerecek yapıya yönelik işaretçi `CRectTracker` .

### <a name="remarks"></a>Açıklamalar

Dikdörtgenin boyutları, dış kenarlıkta bulunan herhangi bir yeniden boyutlandırma tutamaçlarının yüksekliğini ve genişliğini içerir. Geri dönerek, *lpTrueRect* her zaman cihaz koordinatlarındaki normalleştirilmiş bir dikdörtgendir.

## <a name="crecttrackerhittest"></a><a name="hittest"></a> CRectTracker:: HitTest

Kullanıcının bir yeniden boyutlandırma tutamacı içerip içermediğini öğrenmek için bu işlevi çağırın.

```
int HitTest(CPoint point) const;
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Test etmek için cihaz koordinatlarındaki noktası.

### <a name="return-value"></a>Dönüş Değeri

Döndürülen değer, numaralandırılmış türü temel alır `CRectTracker::TrackerHit` ve aşağıdaki değerlerden birine sahip olabilir:

- `CRectTracker::hitNothing` -1

- `CRectTracker::hitTopLeft` 0

- `CRectTracker::hitTopRight` 1

- `CRectTracker::hitBottomRight` iki

- `CRectTracker::hitBottomLeft` 03

- `CRectTracker::hitTop` 4

- `CRectTracker::hitRight` e

- `CRectTracker::hitBottom` inç

- `CRectTracker::hitLeft` 7@@

- `CRectTracker::hitMiddle` 240

## <a name="crecttrackerm_nhandlesize"></a><a name="m_nhandlesize"></a> CRectTracker:: m_nHandleSize

`CRectTracker`Yeniden boyutlandırma tutamaçlarının piksel cinsinden boyutu.

```
int m_nHandleSize;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan sistem değeri ile başlatılır.

## <a name="crecttrackerm_rect"></a><a name="m_rect"></a> CRectTracker:: m_rect

Dikdörtgenin istemci koordinatlarındaki geçerli konumu (piksel).

```
CRect m_rect;
```

## <a name="crecttrackerm_sizemin"></a><a name="m_sizemin"></a> CRectTracker:: m_sizeMin

Dikdörtgenin en küçük boyutu.

```
CSize m_sizeMin;
```

### <a name="remarks"></a>Açıklamalar

Hem varsayılan değerler hem de, `cx` `cy` Kenarlık genişliği için varsayılan sistem değerinden hesaplanır. Bu veri üyesi yalnızca üye işlevi tarafından kullanılır `AdjustRect` .

## <a name="crecttrackerm_nstyle"></a><a name="m_nstyle"></a> CRectTracker:: m_nStyle

Dikdörtgenin geçerli stili.

```
UINT m_nStyle;
```

### <a name="remarks"></a>Açıklamalar

Olası stillerin listesi için bkz. [CRectTracker:: CRectTracker](#crecttracker) .

## <a name="crecttrackernormalizehit"></a><a name="normalizehit"></a> CRectTracker:: NormalizeHit

Muhtemelen ters çevrilen bir tutamacı dönüştürmek için bu işlevi çağırın.

```
int NormalizeHit(int nHandle) const;
```

### <a name="parameters"></a>Parametreler

*Ntanıtıcı*<br/>
Kullanıcı tarafından seçilen tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Normalleştirilmiş tanıtıcının dizini.

### <a name="remarks"></a>Açıklamalar

`CRectTracker::Track`Veya `CRectTracker::TrackRubberBand` ters çevirme ile çağrıldığında, dikdörtgenin x ekseni, y ekseni veya her ikisinde de ters çevrilme olasılığı vardır. Bu durumda, `HitTest` dikdörtgenle ilgili olarak da ters çevrilen tutamaçları döndürür. Bu, geri bildirim, dikdörtgenin ekran konumuna bağlı olduğundan, değiştirilecek dikdörtgen veri yapısının bölümünü değil, imlecin geri bildirimini çizmek için uygun değildir.

## <a name="crecttrackeronchangedrect"></a><a name="onchangedrect"></a> CRectTracker:: OnChangedRect

Bir çağrısı sırasında izleyici dikdörtgeni her değiştiğinde Framework tarafından çağırılır `Track` .

```
virtual void OnChangedRect(const CRect& rectOld);
```

### <a name="parameters"></a>Parametreler

*Recbildirilir*<br/>
Nesnenin eski cihaz koordinatlarını içerir `CRectTracker` .

### <a name="remarks"></a>Açıklamalar

Bu işlevin çağrıldığı zamanda, ile çizilen tüm geri bildirimler `DrawTrackerRect` kaldırılmıştır. Bu işlevin varsayılan uygulanması hiçbir şey yapmaz.

Dikdörtgen yeniden boyutlandırdıktan sonra herhangi bir eylem gerçekleştirmek istediğinizde bu işlevi geçersiz kılın.

## <a name="crecttrackersetcursor"></a><a name="setcursor"></a> CRectTracker:: SetCursor

İmleç şeklini nesne bölgesinin üzerindeyken değiştirmek için bu işlevi çağırın `CRectTracker` .

```
BOOL SetCursor(
    CWnd* pWnd,
    UINT nHitTest) const;
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Şu anda imlecin bulunduğu pencereyi işaret eder.

*nHitTest*<br/>
WM_SETCURSOR iletisinden önceki isabet testinin sonuçları.

### <a name="return-value"></a>Dönüş Değeri

Önceki isabet izleyici dikdörtgeninin üzerindeyken sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi, WM_SETCURSOR iletisini işleyen pencerenizin işlevinin içinden çağırın (genellikle `OnSetCursor` ).

## <a name="crecttrackertrack"></a><a name="track"></a> CRectTracker:: Track

Dikdörtgeni yeniden boyutlandırmak için Kullanıcı arabirimini göstermek üzere bu işlevi çağırın.

```
BOOL Track(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = FALSE,
    CWnd* pWndClipTo = NULL);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Dikdörtgeni içeren pencere nesnesi.

*seçeneğinin*<br/>
İstemci alanına göre geçerli fare konumunun cihaz koordinatları.

*bAllowInvert*<br/>
Değer TRUE ise, dikdörtgen x ekseni veya y ekseni üzerinde ters çevrilenebilir; Aksi halde yanlış.

*pWndClipTo*<br/>
Çizim işlemleri için kırpılacak pencere. NULL ise, *pWnd* kırpma dikdörtgeni olarak kullanılır.

### <a name="return-value"></a>Dönüş Değeri

ESC tuşuna basıldığında, izleme işlemi durdurulur, izleyici 'de depolanan dikdörtgen değiştirilmez ve 0 döndürülür. Değişiklik kaydedilmişse, fareyi taşıyarak ve sol fare düğmesini bırakarak yeni konum ve/veya boyut izleyici dikdörtgenine kaydedilir ve sıfır sıfır döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu, genellikle iletiyi işleyen uygulamanızın işlevinin içinden çağrılır `WM_LBUTTONDOWN` (genellikle `OnLButtonDown` ).

Bu işlev, Kullanıcı sol fare düğmesini bıraktığında, ESC tuşuna bastığında veya sağ fare düğmesine bastığında fareyi yakalar. Kullanıcı fare imlecini taşırken, ve çağırarak geri bildirim güncelleştirilir `DrawTrackerRect` `OnChangedRect` .

*BALLOWINVERT* true ise, izleme dikdörtgeni x ekseninde ya da y ekseninde ters çevrilebiliyor.

## <a name="crecttrackertrackrubberband"></a><a name="trackrubberband"></a> CRectTracker:: TrackRubberBand

Lastik bant seçimini yapmak için bu işlevi çağırın.

```
BOOL TrackRubberBand(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = TRUE);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Dikdörtgeni içeren pencere nesnesi.

*seçeneğinin*<br/>
İstemci alanına göre geçerli fare konumunun cihaz koordinatları.

*bAllowInvert*<br/>
Değer TRUE ise, dikdörtgen x ekseni veya y ekseni üzerinde ters çevrilenebilir; Aksi halde yanlış.

### <a name="return-value"></a>Dönüş Değeri

Fare taşınmışsa ve dikdörtgen boş değilse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Genellikle, WM_LBUTTONDOWN iletisini işleyen uygulamanızın işlevinin içinden çağrılır (genellikle `OnLButtonDown` ).

Bu işlev, Kullanıcı sol fare düğmesini bıraktığında, ESC tuşuna bastığında veya sağ fare düğmesine bastığında fareyi yakalar. Kullanıcı fare imlecini taşırken, ve çağırarak geri bildirim güncelleştirilir `DrawTrackerRect` `OnChangedRect` .

İzleme, sağ alt tanıtıcıdan bir lastik bant türü seçimiyle gerçekleştirilir. Ters çevirme izin veriliyorsa, dikdörtgen yukarı ve aşağı ve sağa sürükleyerek boyutlandırılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek IZLEYICISI](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek DRAWCLı](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleResizeBar sınıfı](../../mfc/reference/coleresizebar-class.md)<br/>
[CRect sınıfı](../../atl-mfc-shared/reference/crect-class.md)
