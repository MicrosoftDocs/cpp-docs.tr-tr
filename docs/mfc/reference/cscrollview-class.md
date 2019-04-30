---
title: CScrollView sınıfı
ms.date: 11/04/2016
f1_keywords:
- CScrollView
- AFXWIN/CScrollView
- AFXWIN/CScrollView::CScrollView
- AFXWIN/CScrollView::CheckScrollBars
- AFXWIN/CScrollView::FillOutsideRect
- AFXWIN/CScrollView::GetDeviceScrollPosition
- AFXWIN/CScrollView::GetDeviceScrollSizes
- AFXWIN/CScrollView::GetScrollPosition
- AFXWIN/CScrollView::GetTotalSize
- AFXWIN/CScrollView::ResizeParentToFit
- AFXWIN/CScrollView::ScrollToPosition
- AFXWIN/CScrollView::SetScaleToFitSize
- AFXWIN/CScrollView::SetScrollSizes
helpviewer_keywords:
- CScrollView [MFC], CScrollView
- CScrollView [MFC], CheckScrollBars
- CScrollView [MFC], FillOutsideRect
- CScrollView [MFC], GetDeviceScrollPosition
- CScrollView [MFC], GetDeviceScrollSizes
- CScrollView [MFC], GetScrollPosition
- CScrollView [MFC], GetTotalSize
- CScrollView [MFC], ResizeParentToFit
- CScrollView [MFC], ScrollToPosition
- CScrollView [MFC], SetScaleToFitSize
- CScrollView [MFC], SetScrollSizes
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
ms.openlocfilehash: d60082092bd42fbe220eee08953ad5fda0ff0a85
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339593"
---
# <a name="cscrollview-class"></a>CScrollView sınıfı

A [CView](../../mfc/reference/cview-class.md) kaydırma özelliğine sahip.

## <a name="syntax"></a>Sözdizimi

```
class CScrollView : public CView
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CScrollView::CScrollView](#cscrollview)|Oluşturur bir `CScrollView` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CScrollView::CheckScrollBars](#checkscrollbars)|Kaydırma görünümü yatay ve dikey kaydırma çubuğu olup olmadığını gösterir.|
|[CScrollView::FillOutsideRect](#filloutsiderect)|Kaydırma alanının dışına görünüm alanı doldurur.|
|[CScrollView::GetDeviceScrollPosition](#getdevicescrollposition)|Cihaz birimi geçerli kaydırma konumunu alır.|
|[CScrollView::GetDeviceScrollSizes](#getdevicescrollsizes)|Geçerli eşleme modu, toplam boyutu ve kaydırılabilir görünümü satır ve sayfa boyutunu alır. Cihaz birimlerinde boyutlarıdır.|
|[CScrollView::GetScrollPosition](#getscrollposition)|Mantıksal birimler cinsinden geçerli kaydırma konumunu alır.|
|[CScrollView::GetTotalSize](#gettotalsize)|Mantıksal birimler cinsinden kaydırma görünümün toplam boyutunu alır.|
|[CScrollView::ResizeParentToFit](#resizeparenttofit)|Çerçevesini boyutunu söylemesi görünümün boyutunu neden olur.|
|[CScrollView::ScrollToPosition](#scrolltoposition)|Mantıksal birimler cinsinden belirtilen belirli bir noktaya görünümüne kaydırır.|
|[CScrollView::SetScaleToFitSize](#setscaletofitsize)|Kaydırma görünümü, Ölçek uygun moduna geçirir.|
|[CScrollView::SetScrollSizes](#setscrollsizes)|Kaydırma görünümün eşleme modu, toplam boyutu ve yatay ve dikey kaydırma miktarları ayarlar.|

## <a name="remarks"></a>Açıklamalar

Standart kendiniz türetilen herhangi bir sınıf kaydırma işleyebilir `CView` ileti eşlemeli kılarak [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) ve [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) üye işlevleri. Ancak `CScrollView` için aşağıdaki özellikleri ekler, `CView` özellikleri:

- Bu pencere ve Görünüm penceresi boyutları ve eşleme modları yönetir.

- Otomatik kaydırma çubuğu iletilere yanıt olarak kaydırır.

- Klavye, fare kaydırma olmayan ya da IntelliMouse tekerleğini yanıt iletilerine otomatik olarak kayar.

Klavye yanıt iletilerine otomatik olarak kaydırmak için WM_KEYDOWN iletisi ekleyin ve test VK_DOWN, VK_PREV ve çağrı [SetScrollPos](/windows/desktop/api/winuser/nf-winuser-setscrollpos).

Fare tekerleği kendiniz ileti eşlemeli geçersiz kılarak kaydırma işleyebilir [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) ve [OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel) üye işlevleri. İçin oldukları gibi `CScrollView`, bu üye işlevleri desteklemek için önerilen davranışı [WM_MOUSEWHEEL](/windows/desktop/inputdev/wm-mousewheel), tekerlek döndürme ileti.

Otomatik kaydırma avantajından yararlanmak için görünümü sınıfından türetilen `CScrollView` yerine gelen `CView`. Görünüm ilk oluşturulduğunda, belge, çağrı boyutuna göre kaydırılabilir görünümü boyutunu hesaplamak isterseniz `SetScrollSizes` kılacağınızı ya da üye işlev [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) veya [ CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate). (Belgenin boyutunu sorgulamak için kendi kodunuzu yazmanız gerekir. Bir örnek için bkz. [Scribble örneğinin](../../overview/visual-cpp-samples.md).)

Çağrı `SetScrollSizes` üye işlevi, görünümün eşleme modu, kaydırma görünümü ve yatay ve dikey kaydırma tutarlarının toplam boyutunu ayarlar. Tüm boyutlarda mantıksal birimler cinsinden. Bu görünüm mantıksal boyutu genellikle belge içinde depolanan verilerden hesaplanır, ancak bazı durumlarda bir sabit boyut belirtmek isteyebilirsiniz. Her iki yaklaşım örnekleri için bkz: [CScrollView::SetScrollSizes](#setscrollsizes).

Mantıksal birimler cinsinden yatay ve dikey kaydırma tutarlarının belirtirsiniz. Varsayılan olarak kullanıcının kaydırma kutusunun dışında bir kaydırma çubuğu mil tıklarsa `CScrollView` kayan bir "sayfası." Kullanıcı her iki ucunda bir kaydırma çubuğunun kaydırma oku tıklarsa `CScrollView` kayan "satırı." Varsayılan olarak, bir sayfa 1/10 görünümün toplam boyutunu olur; Sayfa boyutu 1/10 satırıdır. Özel boyutlarında geçirerek bu varsayılan değerleri geçersiz kılmak `SetScrollSizes` üye işlevi. Örneğin, yatay boyutunu toplam boyutu ve bir satırın yüksekliğini dikey boyutuna genişliğinin süreliğine için geçerli yazı tipini ayarlayabilirsiniz.

Dikey kaydırma yerine `CScrollView` pencere boyutunu geçerli görünüme otomatik olarak ölçeklendirebilirsiniz. Bu modda, kaydırma çubukları görünümü vardır ve mantıksal görünümü esnetildiğini veya pencerenin istemci alanını tam olarak sığması için küçültülebilir. Bu ölçek uygun özellikten yararlanabilmek için çağrı [CScrollView::SetScaleToFitSize](#setscaletofitsize). (Çağırın ya da `SetScaleToFitSize` veya `SetScrollSizes`, ikisini birden belirtmeyin.)

Önce `OnDraw` türetilmiş görünüm sınıfının üye işlevi çağrıldığında `CScrollView` otomatik olarak görünüm penceresinin başlangıç noktasını ayarlar `CPaintDC` geçirir, cihaz bağlamındaki nesne `OnDraw`.

Kayan pencere, Görünüm penceresi başlangıcı ayarlamak için `CScrollView` geçersiz kılmalar [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc). Bu düzeltme için otomatik `CPaintDC` cihaz bağlamı, `CScrollView` geçirir `OnDraw`, ancak çağırmalısınız `CScrollView::OnPrepareDC` kendiniz herhangi bir cihaz bağlamları, gibi kullandığınız bir `CClientDC`. Geçersiz kılabilirsiniz `CScrollView::OnPrepareDC` Kalem, arka plan rengi ve diğer çizim öznitelikleri ayarlanmasına, ancak ölçeklendirme yapmak için temel sınıfı çağırın.

Kaydırma çubukları aşağıdaki durumlarda gösterildiği gibi bir görünüm göre üç yerde görünebilir:

- WS_HSCROLL ve WS_VSCROLL kullanarak görünüm için standart pencere stili kaydırma çubukları ayarlanabilir[Windows stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).

- Kaydırma çubuğu denetimleri de görünümü içeren çerçevenin eklenebilir, bu durumda framework WM_HSCROLL ve WM_VSCROLL iletileri: çerçeve penceresinde şu anda etkin görünüme iletir.

- Framework ayrıca iletir kaydırma gelen iletileri bir `CSplitterWnd` Bölümlendirici denetimi şu anda etkin Bölümlendirici bölmesine (Görünüm). Konumlandırıldığında bir [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) paylaşılan kaydırma çubuklu bir `CScrollView` nesne kendi oluşturmak yerine paylaşılan olanları kullanır.

Kullanma hakkında daha fazla bilgi için `CScrollView`, bkz: [belge/görünüm mimarisi](../../mfc/document-view-architecture.md) ve [türetilmiş görünüm sınıfları kullanılabilir MFC'de](../../mfc/derived-view-classes-available-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CScrollView`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="checkscrollbars"></a>  CScrollView::CheckScrollBars

Kaydırma görünümü yatay ve dikey çubuklar olup olmadığını belirlemek için bu üye işlevini çağırın.

```
void CheckScrollBars(
    BOOL& bHasHorzBar,
    BOOL& bHasVertBar) const;
```

### <a name="parameters"></a>Parametreler

*bHasHorzBar*<br/>
Uygulama bir yatay kaydırma çubuğu olduğunu gösterir.

*bHasVertBar*<br/>
Uygulama dikey kaydırma çubuğu olduğunu gösterir.

##  <a name="cscrollview"></a>  CScrollView::CScrollView

Oluşturur bir `CScrollView` nesne.

```
CScrollView();
```

### <a name="remarks"></a>Açıklamalar

Ya da çağırmalıdır `SetScrollSizes` veya `SetScaleToFitSize` önce kaydırma görünümü kullanılamaz.

##  <a name="filloutsiderect"></a>  CScrollView::FillOutsideRect

Çağrı `FillOutsideRect` kaydırma alanının dışında görünen görünümün alanı dolduracak şekilde.

```
void FillOutsideRect(
    CDC* pDC,
    CBrush* pBrush);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Doldurma yapılacak olan cihaz bağlamı.

*pBrush*<br/>
Fırça ile doldurulacak bir alandır.

### <a name="remarks"></a>Açıklamalar

Kullanım `FillOutsideRect` kaydırma görünümünüzün içinde `OnEraseBkgnd` aşırı arka plan yeniden çizerken önlemek için işleyici işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]

##  <a name="getdevicescrollposition"></a>  CScrollView::GetDeviceScrollPosition

Çağrı `GetDeviceScrollPosition` geçerli yatay ve dikey konumlarını Kaydırma kutusu içinde kaydırma çubukları gerektiğinde.

```
CPoint GetDeviceScrollPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yatay ve dikey konumda (cihaz birimleri) Kaydırma kutusu bir `CPoint` nesne.

### <a name="remarks"></a>Açıklamalar

Bu koordinat çifti görünümünün sol üst köşesinde kaydırılan belge içindeki konumuna karşılık gelir. Fare aygıtı konumları kaydırma görünümü cihaz konumlara mahsup için kullanışlıdır.

`GetDeviceScrollPosition` cihaz birimlerinde değerlerini döndürür. Mantıksal birimler istiyorsanız kullanın `GetScrollPosition` yerine.

##  <a name="getdevicescrollsizes"></a>  CScrollView::GetDeviceScrollSizes

`GetDeviceScrollSizes` Geçerli eşleme modu, toplam boyutu ve kaydırılabilir görünümü satır ve sayfa boyutunu alır.

```
void GetDeviceScrollSizes(
    int& nMapMode,
    SIZE& sizeTotal,
    SIZE& sizePage,
    SIZE& sizeLine) const;
```

### <a name="parameters"></a>Parametreler

*nMapMode*<br/>
Bu görünüm için geçerli eşleme modunu döndürür. Olası değerler listesi için bkz. `SetScrollSizes`.

*sizeTotal*<br/>
Kaydırma görünümü, şu anki toplam boyutu, cihaz birimleri cinsinden döndürür.

*sizePage*<br/>
Bir kaydırma çubuğu mil her bir yönde yanıt olarak bir fare kaydırma geçerli yatay ve dikey miktarları tıklayın döndürür. `cx` Üyeyi içeren yatay tutar. `cy` Üyeyi içeren dikey tutar.

*sizeLine*<br/>
Yanıt olarak bir fare her yönde kaydırmak için geçerli yatay ve dikey miktarları kaydırma okunu döndürür. `cx` Üyeyi içeren yatay tutar. `cy` Üyeyi içeren dikey tutar.

### <a name="remarks"></a>Açıklamalar

Cihaz birimlerinde boyutlarıdır. Bu üye işlev nadiren çağrılır.

##  <a name="getscrollposition"></a>  CScrollView::GetScrollPosition

Çağrı `GetScrollPosition` geçerli yatay ve dikey konumlarını Kaydırma kutusu içinde kaydırma çubukları gerektiğinde.

```
CPoint GetScrollPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yatay ve dikey konumda (mantıksal birimler cinsinden) Kaydırma kutusu bir `CPoint` nesne.

### <a name="remarks"></a>Açıklamalar

Bu koordinat çifti görünümünün sol üst köşesinde kaydırılan belge içindeki konumuna karşılık gelir.

`GetScrollPosition` değerleri, mantıksal birimler cinsinden döndürür. Cihaz birimleri istiyorsanız kullanın `GetDeviceScrollPosition` yerine.

##  <a name="gettotalsize"></a>  CScrollView::GetTotalSize

Çağrı `GetTotalSize` kaydırma görünümü geçerli yatay ve dikey boyutları alınamadı.

```
CSize GetTotalSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırma görünümü mantıksal birimler cinsinden toplam boyutu. Yatay boyutu `cx` üyesi `CSize` değeri döndürür. Dikey boyutu `cy` üyesi.

##  <a name="resizeparenttofit"></a>  CScrollView::ResizeParentToFit

Çağrı `ResizeParentToFit` görünümünüzü boyutunu, çerçeve penceresinin boyutunu dikte izin vermek için.

```
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```

### <a name="parameters"></a>Parametreler

*bShrinkOnly*<br/>
Yeniden boyutlandırma gerçekleştirmek için türü. Varsayılan değer TRUE, çerçeve penceresi uygunsa küçültür. Kaydırma çubukları, büyük görünümleri ya da küçük çerçeve pencereleri için yine de görünür. FALSE değeri her zaman tam olarak çerçeve penceresi yeniden boyutlandırmak görünüm neden olur. Çerçeve penceresi içinde birden çok belge arabirimi (MDI) çerçeve penceresi veya ekran sığmayacak kadar büyük alma olduğundan bu biraz tehlikeli olabilir.

### <a name="remarks"></a>Açıklamalar

Bu, yalnızca MDI alt çerçeve pencereleri görünümlerde için önerilir. Kullanım `ResizeParentToFit` içinde `OnInitialUpdate` işleyici işlevi türetilmiş `CScrollView` sınıfı. Bu üye işlevi bir örnek için bkz [CScrollView::SetScrollSizes](#setscrollsizes).

`ResizeParentToFit` Görünüm penceresinin boyutunu ayarlayın varsayar. Görünüm penceresi boyutu ne zaman ayarlanmamış ise `ResizeParentToFit` olan adlı bir onay alırsınız. Bu gerçekleşmez için aşağıdaki çağrıyı çağırmadan önce olun `ResizeParentToFit`:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

##  <a name="scrolltoposition"></a>  CScrollView::ScrollToPosition

Çağrı `ScrollToPosition` görünümünde belirli bir noktaya kaydırın.

```
void ScrollToPosition(POINT pt);
```

### <a name="parameters"></a>Parametreler

*PT*<br/>
Gidin, mantıksal birimler cinsinden noktası. `x` Üye pozitif bir değer (en az 0 olarak görünümün toplam boyutu kadar) olması gerekir. Aynı true `y` eşleme modu MM_TEXT olduğunda üyesi. `y` Üyesidir negatif eşleme modda MM_TEXT dışında.

### <a name="remarks"></a>Açıklamalar

Böylece bu noktası penceresinin sol üst köşesindeki görünümü kaydırılan. Görünüm sığacak şekilde ölçeklendirilir, bu üye işlevi çağrılmaması gerekir.

##  <a name="setscaletofitsize"></a>  CScrollView::SetScaleToFitSize

Çağrı `SetScaleToFitSize` geçerli pencere boyutuna Görünüm penceresi boyutu otomatik olarak ölçeklendirme istediğinizde.

```
void SetScaleToFitSize(SIZE sizeTotal);
```

### <a name="parameters"></a>Parametreler

*sizeTotal*<br/>
Görünüm ölçeklendirilmesi olduğu yatay ve dikey boyutları. Kaydırma görünümün boyutu, mantıksal birimler cinsinden ölçülür. Yatay boyutunu bulunan `cx` üyesi. Dikey boyutu bulunan `cy` üyesi. Her ikisi de `cx` ve `cy` değerinden büyük veya 0'a eşit olmalıdır.

### <a name="remarks"></a>Açıklamalar

Kaydırma çubukları ile mantıksal görünümü sadece bir kısmı herhangi bir zamanda görünür olabilir. Ancak ölçek Sığdır özelliğine sahip hiçbir kaydırma çubukları görünümü vardır ve mantıksal görünümü esnetildiğini veya pencerenin istemci alanını tam olarak sığması için küçültülebilir. Görünüm penceresi yeniden boyutlandırıldığında verilerini pencere boyutuna bağlı olarak yeni bir ölçekte çizer.

Genellikle çağrısı ekleyeceğiniz `SetScaleToFitSize` kılacağınızı görünümün içinde `OnInitialUpdate` üye işlevi. Otomatik ölçeklendirme istemiyorsanız çağrı `SetScrollSizes` üye işlevini yerine.

`SetScaleToFitSize` bir "Yakınlaştırmak için uygun" işlemini uygulamak için kullanılabilir. Kullanım `SetScrollSizes` kaydırma yeniden başlatmak için.

`SetScaleToFitSize` Görünüm penceresinin boyutunu ayarlayın varsayar. Görünüm penceresi boyutu ne zaman ayarlanmamış ise `SetScaleToFitSize` olan adlı bir onay alırsınız. Bu gerçekleşmez için aşağıdaki çağrıyı çağırmadan önce olun `SetScaleToFitSize`:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

##  <a name="setscrollsizes"></a>  CScrollView::SetScrollSizes

Çağrı `SetScrollSizes` görünümü olduğunda hakkında güncelleştirilecek.

```
void SetScrollSizes(
    int nMapMode,
    SIZE sizeTotal,
    const SIZE& sizePage = sizeDefault,
    const SIZE& sizeLine = sizeDefault);
```

### <a name="parameters"></a>Parametreler

*nMapMode*<br/>
Bu görünüm için ayarlanacak eşleme modu. Olası değerler şunlardır:

|Eşleme modu|Mantıksal birim|Pozitif y ekseni Extends...|
|------------------|------------------|---------------------------------|
|MM_TEXT|1 piksel|Aşağı|
|MM_HIMETRIC|0,01 mm|Upward|
|MM_TWIPS|1/1440|Upward|
|MM_HIENGLISH|0,001 giriş|Upward|
|MM_LOMETRIC|0,1 mm|Upward|
|MM_LOENGLISH|0,01 giriş|Upward|

Tüm bu modlardan Windows tarafından tanımlanır. İki standart eşleme modu, MM_ISOTROPIC ve MM_ANISOTROPIC, için kullanılmaz `CScrollView`. Sınıf kitaplığı sağlar `SetScaleToFitSize` görünümüne pencere boyutunu ölçeklendirmeye yönelik üye işlevi. Yukarıdaki tablosunda üç sütun koordinat yönünü açıklar.

*sizeTotal*<br/>
Kaydırma görünümü toplam boyutu. `cx` Üye yatay ölçüde içerir. `cy` Üye dikey ölçüde içerir. Mantıksal birimler cinsinden boyutlarıdır. Her ikisi de `cx` ve `cy` değerinden büyük veya 0'a eşit olmalıdır.

*sizePage*<br/>
Bir kaydırma çubuğu mil her bir yönde yanıt olarak bir fare kaydırma yatay ve dikey tutarlarının tıklayın. `cx` Üyeyi içeren yatay tutar. `cy` Üyeyi içeren dikey tutar.

*sizeLine*<br/>
Her bir yönde yanıt olarak bir fare kaydırma yatay ve dikey tutarlarının bir kaydırma oka tıklayın. `cx` Üyeyi içeren yatay tutar. `cy` Üyeyi içeren dikey tutar.

### <a name="remarks"></a>Açıklamalar

Geçersiz kılmada çağrı `OnUpdate` gibi belge görüntülendiğinde, veya boyutu değiştiğinde kaydırma özelliklerini ayarlamak için üye işlevi.

Belki de adlı bir belge üye işlevini çağırarak boyutu bilgileri görünümün ilişkili belge genellikle alacaktır `GetMyDocSize`, belge türetilmiş sınıfınızın sağladığınız. Aşağıdaki kod, bu yaklaşım gösterilmektedir:

[!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]

Alternatif olarak, bazı durumlarda, aşağıdaki kodda gösterildiği gibi bir sabit boyutlu ayarlamanız gerekebilir:

[!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]

MM_ISOTROPIC veya MM_ANISOTROPIC dışında Windows eşleme modun herhangi birinde için eşleme modunu ayarlamanız gerekir. Sınırlandırılmamış eşleme modunu kullanmak istiyorsanız, çağrı `SetScaleToFitSize` üye işlevi yerine `SetScrollSizes`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CSplitterWnd Sınıfı](../../mfc/reference/csplitterwnd-class.md)
