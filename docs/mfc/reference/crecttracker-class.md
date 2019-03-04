---
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
ms.openlocfilehash: 1834c378246835314002cdf05fe9a294b609c4e4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259587"
---
# <a name="crecttracker-class"></a>CRectTracker sınıfı

Görüntülenen, taşınan ve farklı boyutlandırmak için bir öğe sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CRectTracker
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRectTracker::CRectTracker](#crecttracker)|Oluşturur bir `CRectTracker` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRectTracker::AdjustRect](#adjustrect)|Dikdörtgen yeniden boyutlandırıldığında çağırılır.|
|[CRectTracker::Draw](#draw)|Dikdörtgen çizer.|
|[CRectTracker::DrawTrackerRect](#drawtrackerrect)|Kenarlığı çizerken adlı bir `CRectTracker` nesne.|
|[CRectTracker::GetHandleMask](#gethandlemask)|Maskesi almak için çağrılan bir `CRectTracker` öğenin yeniden boyutlandırma tutamaçları.|
|[CRectTracker::GetTrueRect](#gettruerect)|Genişlik ve yeniden boyutlandırma tutamaçları dahil olmak üzere dikdörtgenin yüksekliğini döndürür.|
|[CRectTracker::HitTest](#hittest)|İlişkili imleci geçerli konumunu döndürür `CRectTracker` nesne.|
|[CRectTracker::NormalizeHit](#normalizehit)|İsabet testi kodu normalleştirir.|
|[CRectTracker::OnChangedRect](#onchangedrect)|Dikdörtgen yeniden boyutlandırılabilir veya çağrılır.|
|[CRectTracker::SetCursor](#setcursor)|İmleç konumuna dikdörtgen üzerinden bağlı olarak ayarlar.|
|[CRectTracker::Track](#track)|Dikdörtgen işleme izin verir.|
|[CRectTracker::TrackRubberBand](#trackrubberband)|"Lastik bant" kullanıcının seçim izin verir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CRectTracker::m_nHandleSize](#m_nhandlesize)|Yeniden boyutlandırma tutamaçları boyutunu belirler.|
|[CRectTracker::m_nStyle](#m_nstyle)|İzleyici'nin geçerli style(s).|
|[CRectTracker::m_rect](#m_rect)|Dikdörtgeni (piksel cinsinden) geçerli konumu.|
|[CRectTracker::m_sizeMin](#m_sizemin)|En düşük dikdörtgenin genişliğini ve yüksekliğini belirler.|

## <a name="remarks"></a>Açıklamalar

`CRectTracker` bir temel sınıfa sahip değil.

Ancak `CRectTracker` sınıfı grafik bir arabirim kullanarak OLE öğeleri ile etkileşim kurmak izin vermek için tasarlanmıştır, kullanımını OLE özellikli uygulamalar için sınırlı değildir. Kullanılabilir herhangi bir yere bu tür bir kullanıcı arabirimi gerekli değildir.

`CRectTracker` Kenarlıklar dolu olabilir ya da noktalı çizgiler. Öğe verilen taranmış bir kenarlık veya öğenin farklı durumlarını belirtmek için taranmış bir desenle yayılan. Dış veya iç sekiz yeniden boyutlandırma tutamaçları yerleştirebilirsiniz kenarlık öğesi. (Yeniden boyutlandırma tutamaçları açıklaması için bkz: [GetHandleMask](#gethandlemask).) Son olarak, bir `CRectTracker` yeniden boyutlandırma sırasında bir öğe yönünü değiştirmenize izin verir.

Kullanılacak `CRectTracker`, oluşturun bir `CRectTracker` nesne ve hangi görüntü durumları başlatılır belirtin. İle ilişkili OLE öğesinin geçerli durumu hakkında kullanıcıya görsel geribildirim vermek için bu arabirimi ardından kullanabilirsiniz `CRectTracker` nesne.

Kullanma hakkında daha fazla bilgi için `CRectTracker`, makaleye göz atın [izleyicileri](../../mfc/trackers.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CRectTracker`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxext.h

##  <a name="adjustrect"></a>  CRectTracker::AdjustRect

İzleme dikdörtgen bir yeniden boyutlandırma tutamaçlarıyla yeniden boyutlandırıldığında framework tarafından çağırılır.

```
virtual void AdjustRect(
    int nHandle,
    LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*nHandle*<br/>
Kullanılan işleyici dizini.

*lpRect*<br/>
Dikdörtgenin geçerli boyutu işaretçi. (Bir dikdörtgen boyutunun yüksekliğini ve genişliğini tarafından verilir.)

### <a name="remarks"></a>Açıklamalar

Dikdörtgenin yönü yalnızca değiştirmek bu işlev varsayılan davranışını sağlar `Track` ve `TrackRubberBand` izin ters çevirme ile adlandırılır.

Bir sürükleme işlemi sırasında izleme dikdörtgenin ayarlamayı denetlemek için bu işlevi geçersiz kılar. Bir metottur tarafından belirtilen koordinatların ayarlamak için *lpRect* döndürmeden önce.

Tarafından doğrudan desteklenmeyen özelliklere `CRectTracker`, bu işlev geçersiz kılarak gibi kılavuza veya keep-en boy-oranı, uygulanabilir.

##  <a name="crecttracker"></a>  CRectTracker::CRectTracker

Oluşturur ve başlatır bir `CRectTracker` nesne.

```
CRectTracker();

CRectTracker(
    LPCRECT lpSrcRect,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*lpSrcRect*<br/>
Dikdörtgen nesnenin koordinatları.

*nStyle*<br/>
Stilini belirtir `CRectTracker` nesne. Aşağıdaki stilleri desteklenir:

- `CRectTracker::solidLine` Düz çizgi Dikdörtgen kenarlık için kullanın.

- `CRectTracker::dottedLine` Bir noktalı çizgi Dikdörtgen kenarlık için kullanın.

- `CRectTracker::hatchedBorder` Taranmış bir desen Dikdörtgen kenarlık için kullanın.

- `CRectTracker::resizeInside` Yeniden boyutlandırma tutamaçları dikdörtgende bulunan'nı tıklatın.

- `CRectTracker::resizeOutside` Dikdörtgenin dışında bulunan tutamaçları yeniden boyutlandırın.

- `CRectTracker::hatchInside` Desen kapsar tüm Dikdörtgen Çizgili.

### <a name="remarks"></a>Açıklamalar

Varsayılan oluşturucuyu başlatır `CRectTracker` nesne değerlerle *lpSrcRect* ve diğer sistem varsayılanlarını boyutlarına başlatır. Nesne hiçbir parametre olmadan oluşturulduysa `m_rect` ve `m_nStyle` veri üyeleri başlatılmamış.

##  <a name="draw"></a>  CRectTracker::Draw

Dikdörtgenin dış çizgiler ve iç bölgesi çizmek için bu işlevi çağırın.

```
void Draw(CDC* pDC) const;
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Cihaz bağlamı, çizmek işaretçi.

### <a name="remarks"></a>Açıklamalar

Çizimin nasıl yapıldığını İzleyici stilini belirler. Görmek için oluşturucu `CRectTracker` kullanılabilir stiller hakkında daha fazla bilgi için.

##  <a name="drawtrackerrect"></a>  CRectTracker::DrawTrackerRect

Framework tarafından İzleyici konumu değiştirildiğinde çağrılır while içinde `Track` veya `TrackRubberBand` üye işlevi.

```
virtual void DrawTrackerRect(
    LPCRECT lpRect,
    CWnd* pWndClipTo,
    CDC* pDC,
    CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
İşaretçi `RECT` dikdörtgen çizmek için içerir.

*pWndClipTo*<br/>
Kırpma dikdörtgenini içinde kullanmak için pencere işaretçisi.

*pDC*<br/>
Cihaz bağlamı, çizmek işaretçi.

*pWnd*<br/>
İşaretçi penceresine çizim meydana gelir.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama çağrıda `CDC::DrawFocusRect`, noktalı bir dikdörtgen çizer.

İzleme işlemi sırasında farklı geri bildirim sağlamak için bu işlevi geçersiz kılar.

##  <a name="gethandlemask"></a>  CRectTracker::GetHandleMask

Çerçeve, dikdörtgen yeniden boyutlandırma tutamaçları için maske almak için bu üye işlevi çağırır.

```
virtual UINT GetHandleMask() const;
```

### <a name="return-value"></a>Dönüş Değeri

Maskesi için bir `CRectTracker` öğenin yeniden boyutlandırma tutamaçları.

### <a name="remarks"></a>Açıklamalar

Yeniden boyutlandırma tutamaçları yüz ve dikdörtgenin köşelerini görünür ve dikdörtgenin boyutu ve şekli denetlemek izin verin.

Bir dikdörtgen numaralı 0-7, 8 yeniden boyutlandırma tutamaçları sahiptir. Her yeniden boyutlandırma tutamacı bir bit maskesi temsil edilir; 2 söz konusu bit değeri ^ *n*burada *n* yeniden boyutlandırma tutamacı sayısıdır. BITS 0-3 saat yönünde taşıma sol üst kısmında başlangıç köşe yeniden boyutlandırma tutamaçları karşılık gelir. BITS 4-7 kenara yeniden boyutlandırma tutamaçları saat yönünde taşıma üstten başlayarak. Aşağıdaki resimde, bir dikdörtgenin boyutlandırma işler ve bunlara karşılık gelen yeniden tutamacı numaraları ve değerlerini boyutlandırmak gösterilmektedir:

![Yeniden boyutlandırma tutamacı numaraları](../../mfc/reference/media/vc35dp1.gif "yeniden boyutlandırma tutamacı numaraları")

Varsayılan uygulaması `GetHandleMask` yeniden boyutlandırma tutamaçları görünür bir bit maskesi döndürür. Tek bit açıksa, karşılık gelen yeniden boyutlandırma tutamacı çizilir.

Belirtilen yeniden boyutlandırma tutamaçları göstermek veya gizlemek için bu üye işlevini geçersiz kılar.

##  <a name="gettruerect"></a>  CRectTracker::GetTrueRect

Dikdörtgen koordinatlarını almak için bu işlevi çağırın.

```
void GetTrueRect(LPRECT lpTrueRect) const;
```

### <a name="parameters"></a>Parametreler

*lpTrueRect*<br/>
İşaretçi `RECT` cihaz içerecek yapı koordinatları `CRectTracker` nesne.

### <a name="remarks"></a>Açıklamalar

Boyutları dikdörtgenin yüksekliğini ve genişliğini dış kenarlığı üzerinde bulunan herhangi bir yeniden boyutlandırma tutamaçları içerir. Döndürmek, bağlı *lpTrueRect* normalleştirilmiş cihaz koordinatlarında dikdörtgen her zaman'dır.

##  <a name="hittest"></a>  CRectTracker::HitTest

Olup kullanıcı yeniden boyutlandırma tutamacı yakaladı çıkış bulmak için bu işlevi çağırın.

```
int HitTest(CPoint point) const;
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
Test etmek için cihaz koordinatları noktası.

### <a name="return-value"></a>Dönüş Değeri

Döndürülen değer numaralandırılmış tür üzerinde temel `CRectTracker::TrackerHit` ve aşağıdaki değerlerden biri olabilir:

- `CRectTracker::hitNothing` -1

- `CRectTracker::hitTopLeft` 0

- `CRectTracker::hitTopRight` 1

- `CRectTracker::hitBottomRight` 2

- `CRectTracker::hitBottomLeft` 3

- `CRectTracker::hitTop` 4

- `CRectTracker::hitRight` 5

- `CRectTracker::hitBottom` 6

- `CRectTracker::hitLeft` 7

- `CRectTracker::hitMiddle` 8

##  <a name="m_nhandlesize"></a>  CRectTracker::m_nHandleSize

Piksel cinsinden boyutu, `CRectTracker` yeniden boyutlandırma tutamaçları.

```
int m_nHandleSize;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan sistem değerle başlatılır.

##  <a name="m_rect"></a>  CRectTracker::m_rect

Geçerli konumda dikdörtgenin istemci koordinatları (piksel cinsinden).

```
CRect m_rect;
```

##  <a name="m_sizemin"></a>  CRectTracker::m_sizeMin

Dikdörtgenin en küçük boyutu.

```
CSize m_sizeMin;
```

### <a name="remarks"></a>Açıklamalar

Her iki varsayılan değerleri `cx` ve `cy`, kenarlık genişliği için varsayılan sistem değerinden hesaplanır. Bu veri üyesi yalnızca kullanılan `AdjustRect` üye işlevi.

##  <a name="m_nstyle"></a>  CRectTracker::m_nStyle

Dikdörtgenin geçerli stili.

```
UINT m_nStyle;
```

### <a name="remarks"></a>Açıklamalar

Bkz: [CRectTracker::CRectTracker](#crecttracker) olası stilleri listesi.

##  <a name="normalizehit"></a>  CRectTracker::NormalizeHit

Potansiyel olarak tersine çevrilmiş bir tanıtıcı dönüştürmek için bu işlevi çağırın.

```
int NormalizeHit(int nHandle) const;
```

### <a name="parameters"></a>Parametreler

*nHandle*<br/>
Kullanıcı tarafından seçilen işleyici.

### <a name="return-value"></a>Dönüş Değeri

Normalleştirilmiş tanıtıcı dizini.

### <a name="remarks"></a>Açıklamalar

Zaman `CRectTracker::Track` veya `CRectTracker::TrackRubberBand` çağrılır izin ters çevirme ile dikdörtgenin x eksenini, y veya her ikisi de ters mümkündür. Bu durumda, `HitTest` dikdörtgenin göre de tersine tanıtıcıları döndürür. Geri bildirim değiştirilecek dikdörtgen veri yapısı bölümü dikdörtgen ekran konumuna bağlı olduğundan, bu çizim imleç geri bildirim için uygun değil.

##  <a name="onchangedrect"></a>  CRectTracker::OnChangedRect

İzleyici dikdörtgen bir çağrı sırasında değiştirildiğinde framework tarafından çağırılır `Track`.

```
virtual void OnChangedRect(const CRect& rectOld);
```

### <a name="parameters"></a>Parametreler

*rectOld*<br/>
Eski cihaz koordinatları içeren `CRectTracker` nesne.

### <a name="remarks"></a>Açıklamalar

Zaman bu işlev, tüm geri bildirim ile çizilen çağrılır `DrawTrackerRect` kaldırıldı. Bu işlevin varsayılan uygulama, hiçbir şey yapmaz.

Dikdörtgen yeniden boyutlandırıldı sonra herhangi bir eylem gerçekleştirmek istediğinizde, bu işlev geçersiz kılar.

##  <a name="setcursor"></a>  CRectTracker::SetCursor

Üzerinden ederken imleci şeklini değiştirmek için bu işlevi çağırın `CRectTracker` nesnenin bölge.

```
BOOL SetCursor(
    CWnd* pWnd,
    UINT nHitTest) const;
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Şu anda imleç içeren bir pencere işaret eder.

*nHitTest*<br/>
WM_SETCURSOR iletiden önceki isabet test sonuçları.

### <a name="return-value"></a>Dönüş Değeri

Önceki İsabet üzerine İzleyicisi dikdörtgen ise sıfır olmayan; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Pencerenizin WM_SETCURSOR iletiyi işleyen işlev içinde bu işlevden çağırma (genellikle `OnSetCursor`).

##  <a name="track"></a>  CRectTracker::Track

Dikdörtgen yeniden boyutlandırma için kullanıcı arabirimini görüntülemek için bu işlevi çağırın.

```
BOOL Track(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = FALSE,
    CWnd* pWndClipTo = NULL);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Dikdörtgen içeren pencere nesnesi.

*Noktası*<br/>
Cihaz koordinat istemci alanına göre geçerli fare konumu.

*bAllowInvert*<br/>
TRUE ise dikdörtgen x veya y ekseni ters; Aksi durumda FALSE.

*pWndClipTo*<br/>
İçin işlem çizimi kırpılır penceresi. NULL ise, *pWnd* dikdörtgen kırpımını kullanılır.

### <a name="return-value"></a>Dönüş Değeri

ESC tuşuna basıldığında, izleme işlemi durdurulur, İzleyici'depolanan dikdörtgen değiştirilmemesi ve 0 döndürdü. Değişiklik tamamlanırsa, fareyi hareket ettirmek ve sol fare düğmesini bırakmadan yeni konumunu ve/veya boyutunu kayıtlı İzleyici 's dikdörtgende ve sıfır döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu genellikle, uygulamanızın işleyen işlev içinde çağrılır `WM_LBUTTONDOWN` iletisi (genellikle `OnLButtonDown`).

Bu işlev, kullanıcının sol fare düğmesini bıraktığında, ESC tuşuna bastığında veya sağ fare düğmesine bastığında kadar fare yakalama. Kullanıcı fareyi hareket gibi geri bildirim çağırarak güncelleştirilir `DrawTrackerRect` ve `OnChangedRect`.

Varsa *bAllowInvert* doğru ise, izleme dikdörtgenin x veya y ekseni üzerinde ters.

##  <a name="trackrubberband"></a>  CRectTracker::TrackRubberBand

Lastik bant seçimi yapmak için bu işlevi çağırın.

```
BOOL TrackRubberBand(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = TRUE);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Dikdörtgen içeren pencere nesnesi.

*Noktası*<br/>
Cihaz koordinat istemci alanına göre geçerli fare konumu.

*bAllowInvert*<br/>
TRUE ise dikdörtgen x veya y ekseni ters; Aksi durumda FALSE.

### <a name="return-value"></a>Dönüş Değeri

Fare taşınmıştır ve dikdörtgen boş değil olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu genellikle, uygulamanızın WM_LBUTTONDOWN ileti işleme işlevinin içinde çağrılır (genellikle `OnLButtonDown`).

Bu işlev, kullanıcının sol fare düğmesini bıraktığında, ESC tuşuna bastığında veya sağ fare düğmesine bastığında kadar fare yakalama. Kullanıcı fareyi hareket gibi geri bildirim çağırarak güncelleştirilir `DrawTrackerRect` ve `OnChangedRect`.

İzleme sağ tutamacını bir Lastik bant türü seçim ile gerçekleştirilir. Ters çevirme izin verilirse, dikdörtgen ya da yukarı ve sola ya da aşağı ve sağa doğru sürükleyerek boyutlandırılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek İZLEYİCİSİ](../../visual-cpp-samples.md)<br/>
[MFC örnek DRAWCLI](../../visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleResizeBar Sınıfı](../../mfc/reference/coleresizebar-class.md)<br/>
[CRect Sınıfı](../../atl-mfc-shared/reference/crect-class.md)
