---
title: CRectTracker Sınıfı
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
ms.openlocfilehash: 4d262ab5f88481d56de1c236effb66fcbf6a706a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368373"
---
# <a name="crecttracker-class"></a>CRectTracker Sınıfı

Bir öğenin farklı şekillerde görüntülenmesine, taşınmasına ve yeniden boyutlandırılmasına izin verir.

## <a name="syntax"></a>Sözdizimi

```
class CRectTracker
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CRectTracker::CRectTracker](#crecttracker)|Bir `CRectTracker` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRectTracker::AdjustRect](#adjustrect)|Dikdörtgen yeniden boyutlandırıldığında çağrılır.|
|[CRectTracker::Draw](#draw)|Dikdörtgeni işler.|
|[CRectTracker::DrawTrackerRect](#drawtrackerrect)|Bir `CRectTracker` nesnenin kenarlığı çizerken çağrılır.|
|[CRectTracker::GetHandleMask](#gethandlemask)|Bir `CRectTracker` öğenin yeniden boyutlandırma tutamaçlarının maskesini almak için çağrıldı.|
|[CRectTracker::GetTrueRect](#gettruerect)|Yeniden boyutlandırma tutamaçları da dahil olmak üzere dikdörtgenin genişliğini ve yüksekliğini döndürür.|
|[CRectTracker::HitTest](#hittest)|`CRectTracker` Imlecin nesneyle ilgili geçerli konumunu döndürür.|
|[CRectTracker::NormalizeHit](#normalizehit)|Bir isabet testi kodunu normalleştirir.|
|[CRectTracker::OnChangedRect](#onchangedrect)|Dikdörtgen yeniden boyutlandırıldığında veya taşındığında çağrılır.|
|[CRectTracker::SetCursor](#setcursor)|İmleci dikdörtgenin üzerindeki konumuna bağlı olarak ayarlar.|
|[CRectTracker::İzle](#track)|Kullanıcının dikdörtgeni işlemesini sağlar.|
|[CRectTracker::TrackRubberBand](#trackrubberband)|Kullanıcının seçimi "lastik bantla" bantlamasına olanak tanır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CRectTracker::m_nHandleSize](#m_nhandlesize)|Yeniden boyutlandırma tanıtıcılarının boyutunu belirler.|
|[CRectTracker::m_nStyle](#m_nstyle)|İzleyicinin geçerli stili(ler).|
|[CRectTracker::m_rect](#m_rect)|Dikdörtgenin geçerli konumu (piksel olarak).|
|[CRectTracker::m_sizeMin](#m_sizemin)|Minimum dikdörtgen genişliğini ve yüksekliğini belirler.|

## <a name="remarks"></a>Açıklamalar

`CRectTracker`taban sınıfa sahip değildir.

Sınıf, `CRectTracker` kullanıcının grafik arabirimi kullanarak OLE öğeleriyle etkileşim kurabilmesi için tasarlanmış olsa da, kullanımı OLE özellikli uygulamalarla sınırlı değildir. Böyle bir kullanıcı arabirimi gerekli olduğu her yerde kullanılabilir.

`CRectTracker`kenarlıklar düz veya noktalı çizgiler olabilir. Öğe, yumurtadan çıkmış bir kenarlık verilebilir veya maddenin farklı durumlarını belirtmek için yumurtadan çıkarılmış bir desenle kaplanabilir. Öğenin dış veya iç kenarlığı üzerinde sekiz yeniden boyutlandırma tutamacı yerleştirebilirsiniz. (Yeniden boyutlandırma tutamaçlarının açıklaması için [Bkz. GetHandleMask.)](#gethandlemask) Son olarak, bir `CRectTracker` öğenin yönünü yeniden boyutlandırma sırasında değiştirmenize olanak tanır.

Kullanmak `CRectTracker`için, `CRectTracker` bir nesne oluşturmak ve hangi ekran durumları baş harfe olduğunu belirtin. Daha sonra bu arabirimi, kullanıcıya `CRectTracker` nesneyle ilişkili OLE öğesinin geçerli durumu hakkında görsel geri bildirim vermek için kullanabilirsiniz.

Kullanma `CRectTracker`hakkında daha fazla bilgi için, makale [Trackers](../../mfc/trackers.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CRectTracker`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext.h

## <a name="crecttrackeradjustrect"></a><a name="adjustrect"></a>CRectTracker::AdjustRect

İzleme dikdörtgeni yeniden boyutlandırıldığında, yeniden boyutlandırma tutamacı kullanılarak çerçeve tarafından çağrılır.

```
virtual void AdjustRect(
    int nHandle,
    LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*nHandle*<br/>
Kullanılan tutamaç dizin.

*Lprect*<br/>
Dikdörtgenin geçerli boyutunu işaretçi. (Dikdörtgenin boyutu, yüksekliği ve genişliği ile verilir.)

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan davranışı, dikdörtgenin yönünüyalnızca ters `Track` çevrildiğinde ve `TrackRubberBand` izin verilen ters çevrildiğinde değiştirmesini sağlar.

Sürükleme işlemi sırasında izleme dikdörtgeninin ayarını denetlemek için bu işlevi geçersiz kılın. Bir yöntem dönmeden önce *lpRect* tarafından belirtilen koordinatları ayarlamaktır.

Bu işlevi geçersiz kılarak, `CRectTracker`eşzamanlı veya tutma-en boy oranı gibi doğrudan tarafından desteklenmeyen özel özellikler uygulanabilir.

## <a name="crecttrackercrecttracker"></a><a name="crecttracker"></a>CRectTracker::CRectTracker

Bir `CRectTracker` nesne oluşturur ve başharfe bleştirir.

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
Nesnenin stilini `CRectTracker` belirtir. Aşağıdaki stiller desteklenir:

- `CRectTracker::solidLine`Dikdörtgen kenarlığı için düz bir çizgi kullanın.

- `CRectTracker::dottedLine`Dikdörtgen kenarlığı için noktalı bir çizgi kullanın.

- `CRectTracker::hatchedBorder`Dikdörtgen kenarlığı için kapaklı bir desen kullanın.

- `CRectTracker::resizeInside`Dikdörtgenin içinde bulunan tutamaçları yeniden boyutlandırın.

- `CRectTracker::resizeOutside`Dikdörtgenin dışında bulunan tutamaçları yeniden boyutlandırın.

- `CRectTracker::hatchInside`Yumurtadan çıkmış desen tüm dikdörtgeni kaplar.

### <a name="remarks"></a>Açıklamalar

Varsayılan oluşturucu, nesneyi `CRectTracker` *lpSrcRect'ten* gelen değerlerle başharfe çeker ve diğer boyutları sistem varsayılanlarına başlar. Nesne parametreleri olmadan `m_rect` oluşturulursa, `m_nStyle` ve veri üyeleri uninitialized.

## <a name="crecttrackerdraw"></a><a name="draw"></a>CRectTracker::Draw

Dikdörtgenin dış çizgilerini ve iç bölgesini çizmek için bu işlevi arayın.

```
void Draw(CDC* pDC) const;
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Çizecek aygıt bağlamını işaretle.

### <a name="remarks"></a>Açıklamalar

İzleyicinin stili çizimin nasıl yapılacağını belirler. Kullanılabilir stiller `CRectTracker` hakkında daha fazla bilgi için oluşturucuya bakın.

## <a name="crecttrackerdrawtrackerrect"></a><a name="drawtrackerrect"></a>CRectTracker::DrawTrackerRect

İzleyicinin konumu `Track` veya `TrackRubberBand` üye işlevin içindeyken ne zaman değişse çerçeve tarafından çağrılır.

```
virtual void DrawTrackerRect(
    LPCRECT lpRect,
    CWnd* pWndClipTo,
    CDC* pDC,
    CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Lprect*<br/>
Çizmek için `RECT` dikdörtgen içeren işaretçi.

*pWndClipTo*<br/>
Dikdörtgenkırpma de kullanmak için pencereişaretçisi.

*Pdc*<br/>
Çizecek aygıt bağlamını işaretle.

*Pwnd*<br/>
Çizimin gerçekleşeceği pencereyi işaretle.

### <a name="remarks"></a>Açıklamalar

Varsayılan `CDC::DrawFocusRect`uygulama, noktalı dikdörtgen çizen bir çağrı yapar.

İzleme işlemi sırasında farklı geri bildirim sağlamak için bu işlevi geçersiz kılın.

## <a name="crecttrackergethandlemask"></a><a name="gethandlemask"></a>CRectTracker::GetHandleMask

Çerçeve, bir dikdörtgenin yeniden boyutlandırma tutamaçları için maskeyi almak için bu üye işlevi çağırır.

```
virtual UINT GetHandleMask() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CRectTracker` öğenin yeniden boyutlandırma tutamacının maskesi.

### <a name="remarks"></a>Açıklamalar

Yeniden boyutlandırma tutamaçları dikdörtgenin yanlarında ve köşelerinde görünür ve kullanıcının dikdörtgenin şeklini ve boyutunu denetlemesine olanak sağlar.

Bir dikdörtgen0-7 numaralı 8 yeniden boyutlandırma tutamacı vardır. Her yeniden boyutlandırma tutamacı maskede biraz ile temsil edilir; bu bitin değeri 2^ *n*' dir, *n* yeniden boyutlandırma tutamacı numarasıdır. 0-3 bitleri, sol üstkısımdan başlayarak saat yönünde hareket eden köşe yeniden boyutlandırma kollarına karşılık gelir. Bit 4-7, saat yönünde hareket eden üstten başlayarak yan yeniden boyutlandırma kollarına karşılık gelir. Aşağıdaki resimde, bir dikdörtgenin yeniden boyutlandırma tutamaçları ve bunların karşılık gelen yeniden boyutlandırma tutamacı numaraları ve değerleri gösterilmektedir:

![Tutamacı numaralarını yeniden boyutlandırma](../../mfc/reference/media/vc35dp1.gif "Tutamacı numaralarını yeniden boyutlandırma")

Varsayılan uygulama, `GetHandleMask` yeniden boyutlandırma tanıtıcılarının görünmesi için bitlerin maskesini döndürür. Tek bit açıktıysa, karşılık gelen yeniden boyutlandırma tutamacı çizilir.

Belirtilen yeniden boyutlandırma tanıtıcılarını gizlemek veya göstermek için bu üye işlevi geçersiz kılın.

## <a name="crecttrackergettruerect"></a><a name="gettruerect"></a>CRectTracker::GetTrueRect

Dikdörtgenin koordinatlarını almak için bu işlevi arayın.

```
void GetTrueRect(LPRECT lpTrueRect) const;
```

### <a name="parameters"></a>Parametreler

*lpTrueRect*<br/>
Nesnenin `RECT` aygıt koordinatlarını içeren yapıyı `CRectTracker` işaretçi.

### <a name="remarks"></a>Açıklamalar

Dikdörtgenin boyutları, dış kenarlıkta bulunan yeniden boyutlandırma tutamaçlarının yükseklik ve genişliğini içerir. Döndükten *sonra, lpTrueRect* cihaz koordinatlarında her zaman normalleştirilmiş bir dikdörtgendir.

## <a name="crecttrackerhittest"></a><a name="hittest"></a>CRectTracker::HitTest

Kullanıcının yeniden boyutlandırma tutamacını yakalayıp yakalamadığını öğrenmek için bu işlevi arayın.

```
int HitTest(CPoint point) const;
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
Nokta, cihaz koordinatlarında, test etmek için.

### <a name="return-value"></a>Dönüş Değeri

Döndürülen değer numaralandırılmış türü `CRectTracker::TrackerHit` temel alınr ve aşağıdaki değerlerden birine sahip olabilir:

- `CRectTracker::hitNothing`-1

- `CRectTracker::hitTopLeft`0

- `CRectTracker::hitTopRight`1

- `CRectTracker::hitBottomRight`2

- `CRectTracker::hitBottomLeft`3

- `CRectTracker::hitTop`4

- `CRectTracker::hitRight`5

- `CRectTracker::hitBottom`6

- `CRectTracker::hitLeft`7

- `CRectTracker::hitMiddle`8

## <a name="crecttrackerm_nhandlesize"></a><a name="m_nhandlesize"></a>CRectTracker::m_nHandleSize

Boyutlandırma tutamaçlarının `CRectTracker` piksel boyutu.

```
int m_nHandleSize;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan sistem değeri ile baş harfe getirilmektedir.

## <a name="crecttrackerm_rect"></a><a name="m_rect"></a>CRectTracker::m_rect

İstemci koordinatlarında (piksel) dikdörtgenin geçerli konumu.

```
CRect m_rect;
```

## <a name="crecttrackerm_sizemin"></a><a name="m_sizemin"></a>CRectTracker::m_sizeMin

Dikdörtgenin minimum boyutu.

```
CSize m_sizeMin;
```

### <a name="remarks"></a>Açıklamalar

Her iki `cx` varsayılan `cy`değer ve , kenarlık genişliği için varsayılan sistem değerinden hesaplanır. Bu veri üyesi yalnızca `AdjustRect` üye işlev tarafından kullanılır.

## <a name="crecttrackerm_nstyle"></a><a name="m_nstyle"></a>CRectTracker::m_nStyle

Dikdörtgenin geçerli stili.

```
UINT m_nStyle;
```

### <a name="remarks"></a>Açıklamalar

Olası stillerin listesi için [CRectTracker::CRectTracker'a](#crecttracker) bakın.

## <a name="crecttrackernormalizehit"></a><a name="normalizehit"></a>CRectTracker::NormalizeHit

Potansiyel olarak ters çevrilmiş bir tutamacı dönüştürmek için bu işlevi arayın.

```
int NormalizeHit(int nHandle) const;
```

### <a name="parameters"></a>Parametreler

*nHandle*<br/>
Kullanıcı tarafından seçilen tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Normalleştirilmiş tutamacın dizini.

### <a name="remarks"></a>Açıklamalar

İzin verilen ters çevirme yle çağrıldığında, `CRectTracker::Track` dikdörtgenin x ekseni, y ekseni veya her ikisinde ters çevrilmesi mümkündür. `CRectTracker::TrackRubberBand` Bu durumda, `HitTest` dikdörtgen ile ilgili olarak da ters olan tutamaçları döndürür. Geri bildirim, değiştirilecek dikdörtgen veri yapısının bölümüne değil, dikdörtgenin ekran konumuna bağlı olduğundan imleç geri bildirimi çizmek için uygun değildir.

## <a name="crecttrackeronchangedrect"></a><a name="onchangedrect"></a>CRectTracker::OnChangedRect

Bir çağrı sırasında izci dikdörtgeni değiştiğinde çerçeve `Track`tarafından çağrılır.

```
virtual void OnChangedRect(const CRect& rectOld);
```

### <a name="parameters"></a>Parametreler

*rektEski*<br/>
`CRectTracker` Nesnenin eski aygıt koordinatlarını içerir.

### <a name="remarks"></a>Açıklamalar

Bu işlev çağrıldığında, çekilen `DrawTrackerRect` tüm geri bildirim kaldırıldı. Bu işlevin varsayılan uygulaması hiçbir şey yapmaz.

Dikdörtgen yeniden boyutlandıktan sonra herhangi bir eylemi gerçekleştirmek istediğinizde bu işlevi geçersiz kılın.

## <a name="crecttrackersetcursor"></a><a name="setcursor"></a>CRectTracker::SetCursor

`CRectTracker` Nesnenin bölgesi üzerindeyken imleç şeklini değiştirmek için bu işlevi çağırın.

```
BOOL SetCursor(
    CWnd* pWnd,
    UINT nHitTest) const;
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Şu anda imleci içeren pencereyi işaret eder.

*nHitTest*<br/>
Önceki isabet testinin sonuçları, WM_SETCURSOR iletisinden.

### <a name="return-value"></a>Dönüş Değeri

Önceki isabet izci dikdörtgen üzerinde ise Nonzero; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi, WM_SETCURSOR iletiyi işleyen pencerenizin işlevinin `OnSetCursor`içinden (genellikle) çağırın.

## <a name="crecttrackertrack"></a><a name="track"></a>CRectTracker::İzle

Dikdörtgeni yeniden boyutlandırmak için kullanıcı arabirimini görüntülemek için bu işlevi arayın.

```
BOOL Track(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = FALSE,
    CWnd* pWndClipTo = NULL);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Dikdörtgeni içeren pencere nesnesi.

*Nokta*<br/>
İstemci alanına göre geçerli fare konumunun aygıt koordinatları.

*bAllowInvert*<br/>
TRUE ise, dikdörtgen x ekseni veya y ekseni boyunca ters çevrilebilir; aksi takdirde YANLIŞ.

*pWndClipTo*<br/>
Çizim işlemlerinin kırpılacak penceresi. NULL ise, *pWnd* kırpma dikdörtgeni olarak kullanılır.

### <a name="return-value"></a>Dönüş Değeri

ESC tuşuna basıldığında izleme işlemi durdurulur, izcide depolanan dikdörtgen değiştirilmez ve 0 döndürülür. Değişiklik yapılırsa, fareyi hareket ettirerek ve sol fare düğmesini bırakarak, yeni konum ve/veya boyut izleyicinin dikdörtgenine kaydedilir ve sıfırsız döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu genellikle `WM_LBUTTONDOWN` iletiyi işleyen uygulamanızın işlevi içinden çağrılır `OnLButtonDown`(genellikle).

Bu işlev, kullanıcı sol fare düğmesini serbest bırakana, ESC tuşuna basana veya sağ fare düğmesine basana kadar fareyi yakalar. Kullanıcı fare imlecini hareket ettikçe, geri bildirim `DrawTrackerRect` `OnChangedRect`arayarak güncelleştirilir ve .

*bAllowInvert* TRUE ise, izleme dikdörtgeni x ekseni veya y ekseni üzerinde ters çevrilebilir.

## <a name="crecttrackertrackrubberband"></a><a name="trackrubberband"></a>CRectTracker::TrackRubberBand

Kauçuk bant seçimi yapmak için bu işlevi arayın.

```
BOOL TrackRubberBand(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = TRUE);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Dikdörtgeni içeren pencere nesnesi.

*Nokta*<br/>
İstemci alanına göre geçerli fare konumunun aygıt koordinatları.

*bAllowInvert*<br/>
TRUE ise, dikdörtgen x ekseni veya y ekseni boyunca ters çevrilebilir; aksi takdirde YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

Fare hareket ettiyse ve dikdörtgen boş değilse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Genellikle WM_LBUTTONDOWN iletisini işleyen uygulamanızın işlevi içinden çağrılır `OnLButtonDown`(genellikle).

Bu işlev, kullanıcı sol fare düğmesini serbest bırakana, ESC tuşuna basana veya sağ fare düğmesine basana kadar fareyi yakalar. Kullanıcı fare imlecini hareket ettikçe, geri bildirim `DrawTrackerRect` `OnChangedRect`arayarak güncelleştirilir ve .

İzleme, sağ alt tutamaktan lastik bant tipi bir seçimle gerçekleştirilir. Ters çevirmeye izin verilirse, dikdörtgen yukarı ve sola veya aşağıya ve sağa sürükleyerek boyutlandırılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek TRACKER](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek ÇEKMECE](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleResizeBar Sınıfı](../../mfc/reference/coleresizebar-class.md)<br/>
[CRect Sınıfı](../../atl-mfc-shared/reference/crect-class.md)
