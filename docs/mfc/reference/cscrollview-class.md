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
ms.openlocfilehash: b89daaae4bb578d328e1468cc29470825e19c670
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502599"
---
# <a name="cscrollview-class"></a>CScrollView sınıfı

Kaydırma özelliklerine sahip bir [CView](../../mfc/reference/cview-class.md) .

## <a name="syntax"></a>Sözdizimi

```
class CScrollView : public CView
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CScrollView:: CScrollView](#cscrollview)|Bir `CScrollView` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CScrollView:: CheckScrollBars](#checkscrollbars)|Kaydırma görünümünün yatay ve dikey kaydırma çubuklarına sahip olup olmadığını gösterir.|
|[CScrollView:: FillOutsideRect](#filloutsiderect)|Bir görünümün alanını kaydırma alanı dışında doldurur.|
|[CScrollView:: GetDeviceScrollPosition](#getdevicescrollposition)|Cihaz birimlerindeki geçerli kaydırma konumunu alır.|
|[CScrollView:: GetDeviceScrollSizes](#getdevicescrollsizes)|Geçerli eşleme modunu, toplam boyutunu ve kaydırılabilir görünümün çizgi ve sayfa boyutlarını alır. Boyutlar, cihaz birimleridir.|
|[CScrollView:: GetScrollPosition](#getscrollposition)|Mantıksal birimlerde geçerli kaydırma konumunu alır.|
|[CScrollView:: GetTotalSize](#gettotalsize)|Mantıksal birimlerde kaydırma görünümünün toplam boyutunu alır.|
|[CScrollView:: ResizeParentToFit](#resizeparenttofit)|Görünümün boyutunun Çerçevenin boyutunu dikte etmesine neden olur.|
|[CScrollView:: ScrollToPosition](#scrolltoposition)|Görünümü mantıksal birimlerde belirtilen belirli bir noktaya kaydırır.|
|[CScrollView:: SetScaleToFitSize](#setscaletofitsize)|Kaydırma görünümünü ölçeklendirme moduna geçirir.|
|[CScrollView:: Setscrollboyutlar](#setscrollsizes)|Kaydırma görünümünün eşleme modunu, toplam boyutunu, yatay ve dikey kaydırma tutarlarını ayarlar.|

## <a name="remarks"></a>Açıklamalar

İleti eşlemeli [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) ve [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) üye işlevlerini `CView` geçersiz kılarak, kendi içinden türetilmiş herhangi bir sınıfta standart kaydırmayı işleyebilirsiniz. Ancak `CScrollView` `CView` özelliklerine aşağıdaki özellikleri ekler:

- Pencere ve Görünüm penceresi boyutlarını ve eşleme modlarını yönetir.

- Kaydırma çubuğu iletilerine yanıt olarak otomatik olarak kayar.

- Klavyeden, kaydırılmayan bir fare veya IntelliMouse tekerindeki iletilere yanıt olarak otomatik olarak kayar.

Klavyeden gelen iletilere yanıt olarak otomatik olarak kaydırmak için, bir WM_KEYDOWN iletisi ekleyin ve VK_DOWN, VK_PREV için test edin ve [SetScrollPos](/windows/win32/api/winuser/nf-winuser-setscrollpos)'u çağırın.

İleti eşlemeli [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) ve [OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel) member işlevlerini geçersiz kılarak fare tekerleğini kaydırmayı kendiniz de işleyebilirsiniz. İçin `CScrollView`, bu üye işlevleri, tekerlek döndürme iletisi olan [wm_mousewheel](/windows/win32/inputdev/wm-mousewheel)için önerilen davranışı destekler.

Otomatik kaydırmanın avantajlarından yararlanmak için, from `CScrollView` `CView`yerine ' den görünüm sınıfınızı türetebilirsiniz. Görünüm ilk oluşturulduğunda, belge boyutuna bağlı olarak kaydırılabilir görünümün boyutunu hesaplamak istiyorsanız, `SetScrollSizes` [CView:: OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) veya [CView:: OnUpdate](../../mfc/reference/cview-class.md#onupdate)' in geçersiz kılınınızdan üye işlevini çağırın. (Belgenin boyutunu sorgulamak için kendi kodunuzu yazmanız gerekir. Bir örnek için bkz. [karalama örneği](../../overview/visual-cpp-samples.md).)

`SetScrollSizes` Üye işlevine yapılan çağrı görünümün eşleme modunu, kaydırma görünümünün toplam boyutlarını ve yatay ve dikey olarak kaydırmak için miktarları ayarlar. Tüm boyutlar mantıksal birimlerde bulunur. Görünümün mantıksal boyutu genellikle belgede depolanan verilerden hesaplanır, ancak bazı durumlarda sabit bir boyut belirtmek isteyebilirsiniz. Her iki yaklaşımın örnekleri için bkz. [CScrollView:: Setscrollboyutlar](#setscrollsizes).

Mantıksal birimlerde yatay ve dikey olarak kaydırmak için miktarları belirtirsiniz. Varsayılan olarak, Kullanıcı kaydırma kutusunun dışında bir kaydırma çubuğu Shaft tıkladığında, `CScrollView` bir "sayfa" kaydırır. Kullanıcı, kaydırma çubuğunun iki ucundaki bir kaydırma okuna tıkladığında, `CScrollView` bir "Line" kaydırır. Varsayılan olarak, bir sayfa, görünümün toplam boyutunun 1/10 ' dir; sayfa boyutunun 1/10 bir satırı vardır. Bu varsayılan değerleri, `SetScrollSizes` üye işlevindeki özel boyutları geçirerek geçersiz kılın. Örneğin, yatay boyutunu toplam boyut genişliğinin bir kesirine ve dikey boyutun geçerli yazı tipindeki bir satırın yüksekliğine kadar olan boyutunu ayarlayabilirsiniz.

Kaydırma yerine, `CScrollView` görünümü otomatik olarak geçerli pencere boyutuna ölçeklendirebilir. Bu modda, görünümün bir kaydırma çubuğu yoktur ve mantıksal görünüm, pencerenin istemci alanına tam olarak sığacak şekilde uzatılır veya daraltıladır. Bu ölçeğe uyacak özelliği kullanmak için [CScrollView:: SetScaleToFitSize](#setscaletofitsize)çağırın. (Ya `SetScaleToFitSize` `SetScrollSizes`da ' i çağırın, ancak ikisini birden değil.)

Türetilmiş Görünüm sınıfınızın `CScrollView` `CPaintDC` `OnDraw`üye işlevine çağrılmadan önce, geçiş yaptığı cihaz bağlamı nesnesinin Görünüm penceresini otomatik olarak ayarlar. `OnDraw`

Kayan pencerenin `CScrollView` görünüm penceresinin kaynağını ayarlamak için [CView:: onhazırlık EDC](../../mfc/reference/cview-class.md#onpreparedc)geçersiz kılar. `CPaintDC` Bu ayarlama `OnDraw`, ' a `CScrollView::OnPrepareDC` `CScrollView` geçişyapancihazbağlamıiçinotomatiktir,ancaksizingibikullandığınızdiğercihazbağlamlarıiçinkendikendinizeçağrıyapmanızgerekir.`CClientDC` Kalemi, arka `CScrollView::OnPrepareDC` plan rengini ve diğer çizim özniteliklerini ayarlamak için geçersiz kılabilirsiniz, ancak ölçeklendirilmesi için temel sınıfı çağırabilirsiniz.

Aşağıdaki durumlarda gösterildiği gibi, kaydırma çubukları bir görünüme göre üç yerde görünebilir:

- WS_HSCROLL ve WS_VSCROLL[Windows stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles)kullanarak görünüm için standart pencere stili kaydırma çubukları ayarlanabilir.

- Kaydırma çubuğu denetimleri, görünümü içeren çerçeveye da eklenebilir, bu durumda Framework çerçeve penceresinden WM_HSCROLL ve WM_VSCROLL iletilerini Şu anda etkin görünüme iletir.

- Çerçeve ayrıca, bir `CSplitterWnd` Splitter denetimindeki kaydırma iletilerini Şu anda etkin olan Bölümlendirici bölmesine (bir görünüm) iletir. Paylaşılan kaydırma çubuklarıyla bir [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) 'e yerleştirildiğinde, bir `CScrollView` nesne kendi kendine oluşturulması yerine paylaşılan olanları kullanacaktır.

Kullanma `CScrollView`hakkında daha fazla bilgi için bkz. MFC 'de kullanılabilen [belge/görünüm mimarisi](../../mfc/document-view-architecture.md) ve [türetilmiş Görünüm sınıfları](../../mfc/derived-view-classes-available-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CScrollView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="checkscrollbars"></a>CScrollView:: CheckScrollBars

Kaydırma görünümünün yatay ve dikey çubuklara sahip olup olmadığını anlamak için bu üye işlevini çağırın.

```
void CheckScrollBars(
    BOOL& bHasHorzBar,
    BOOL& bHasVertBar) const;
```

### <a name="parameters"></a>Parametreler

*Bhakısalzbar*<br/>
Uygulamanın yatay kaydırma çubuğu olduğunu gösterir.

*bHasVertBar*<br/>
Uygulamanın dikey bir kaydırma çubuğu olduğunu gösterir.

##  <a name="cscrollview"></a>CScrollView:: CScrollView

Bir `CScrollView` nesnesi oluşturur.

```
CScrollView();
```

### <a name="remarks"></a>Açıklamalar

Kaydırma görünümü kullanılabilir olmadan `SetScrollSizes` önce `SetScaleToFitSize` ya da ' i çağırmanız gerekir.

##  <a name="filloutsiderect"></a>CScrollView:: FillOutsideRect

Görünümün `FillOutsideRect` , kaydırma alanının dışında görünen alanını doldurmasını sağlayan çağrı.

```
void FillOutsideRect(
    CDC* pDC,
    CBrush* pBrush);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Doldurmanın yapılacağı cihaz bağlamı.

*pBrush*<br/>
Alanın doldurulması gereken fırça.

### <a name="remarks"></a>Açıklamalar

Aşırı `FillOutsideRect` arka plan arkalenmesini engellemek `OnEraseBkgnd` için kaydırma görünümlerinizin işleyici işlevinde kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]

##  <a name="getdevicescrollposition"></a>CScrollView:: GetDeviceScrollPosition

Kaydırma `GetDeviceScrollPosition` çubuklarındaki kaydırma kutularının geçerli yatay ve dikey konumlarına ihtiyacınız olduğunda çağrı yapın.

```
CPoint GetDeviceScrollPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırma kutularının bir `CPoint` nesne olarak yatay ve dikey konumları (cihaz birimlerinde).

### <a name="remarks"></a>Açıklamalar

Bu koordinat çifti, görünümün sol üst köşesinin kaydırılabildiği belgedeki konuma karşılık gelir. Bu, cihaz konumlarını kaydırmak için fare aygıtı konumlarının gezmek için yararlıdır.

`GetDeviceScrollPosition`cihaz birimlerindeki değerleri döndürür. Mantıksal birimleri istiyorsanız bunun yerine kullanın `GetScrollPosition` .

##  <a name="getdevicescrollsizes"></a>CScrollView:: GetDeviceScrollSizes

`GetDeviceScrollSizes`Geçerli eşleme modunu, toplam boyutunu ve kaydırılabilir görünümün çizgi ve sayfa boyutlarını alır.

```
void GetDeviceScrollSizes(
    int& nMapMode,
    SIZE& sizeTotal,
    SIZE& sizePage,
    SIZE& sizeLine) const;
```

### <a name="parameters"></a>Parametreler

*nMapMode*<br/>
Bu görünüm için geçerli eşleme modunu döndürür. Olası değerler listesi için bkz `SetScrollSizes`.

*Toplam Boyut*<br/>
Cihaz birimlerindeki kaydırma görünümünün geçerli toplam boyutunu döndürür.

*sizePage*<br/>
Bir kaydırma çubuğu biçimlendirbir çubukta fare tıklamasını yanıtlamak üzere her yönde kaydırmak için geçerli yatay ve dikey miktarları döndürür. `cx` Üye yatay miktarı içerir. `cy` Üye dikey miktarı içerir.

*sizeLine*<br/>
Bir kaydırma okuna fare tıklaması karşılığında her bir yönde kaydırmak için geçerli yatay ve dikey miktarları döndürür. `cx` Üye yatay miktarı içerir. `cy` Üye dikey miktarı içerir.

### <a name="remarks"></a>Açıklamalar

Boyutlar, cihaz birimleridir. Bu üye işlevi nadiren çağırılır.

##  <a name="getscrollposition"></a>CScrollView:: GetScrollPosition

Kaydırma `GetScrollPosition` çubuklarındaki kaydırma kutularının geçerli yatay ve dikey konumlarına ihtiyacınız olduğunda çağrı yapın.

```
CPoint GetScrollPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırma kutularının bir `CPoint` nesne olarak yatay ve dikey konumları (mantıksal birimler cinsinden).

### <a name="remarks"></a>Açıklamalar

Bu koordinat çifti, görünümün sol üst köşesinin kaydırılabildiği belgedeki konuma karşılık gelir.

`GetScrollPosition`mantıksal birimlerdeki değerleri döndürür. Cihaz birimleri istiyorsanız bunun yerine kullanın `GetDeviceScrollPosition` .

##  <a name="gettotalsize"></a>CScrollView:: GetTotalSize

Kaydırma `GetTotalSize` görünümünün geçerli yatay ve dikey boyutlarını almak için çağırın.

```
CSize GetTotalSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mantıksal birimlerde kaydırma görünümünün toplam boyutu. Yatay boyut `cx` , `CSize` dönüş değerinin üyesidir. Dikey boyut `cy` üye içinde.

##  <a name="resizeparenttofit"></a>CScrollView:: ResizeParentToFit

Görünümlerinizin boyutunun çerçeve penceresinin boyutunu görüntülemesini sağlamak için çağrısı `ResizeParentToFit` yapın.

```
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```

### <a name="parameters"></a>Parametreler

*Bshrınkonly*<br/>
Gerçekleştirilecek yeniden boyutlandırma türü. Varsayılan değer TRUE, uygunsa çerçeve penceresini küçültür. Büyük görünümler veya küçük çerçeve pencereleri için kaydırma çubukları görünmeye devam eder. FALSE değeri, görünümün çerçeve penceresini her zaman yeniden boyutlandırmasına neden olur. Çerçeve penceresi birden çok belge arabirimi (MDI) çerçeve penceresi veya ekranı içine sığmayacak kadar büyük olduğundan, bu biraz tehlikeli olabilir.

### <a name="remarks"></a>Açıklamalar

Bu yalnızca MDI alt çerçeve pencerelerinin görünümleri için önerilir. Türetilmiş `ResizeParentToFit` sınıfınızın`CScrollView` işleyici `OnInitialUpdate` işlevinde kullanın. Bu üye işlevine bir örnek için bkz. [CScrollView:: Setscrollboyutlar](#setscrollsizes).

`ResizeParentToFit`Görünüm penceresinin boyutunun ayarlandığını varsayar. Çağrıldığında Görünüm penceresi boyutu ayarlanmamışsa `ResizeParentToFit` bir onaylama işlemi alırsınız. Bunun gerçekleşmediğinden emin olmak için çağrılmadan `ResizeParentToFit`önce aşağıdaki çağrıyı yapın:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

##  <a name="scrolltoposition"></a>CScrollView:: ScrollToPosition

Görünümdeki `ScrollToPosition` belirli bir noktaya kaydırmak için çağırın.

```
void ScrollToPosition(POINT pt);
```

### <a name="parameters"></a>Parametreler

*yönergelerinin*<br/>
Mantıksal birimlerde kaydırma noktası. `x` Üyenin pozitif bir değer olması gerekir (en fazla, görünümün toplam boyutuna kadar, 0 ' dan büyük veya buna eşit). Eşleme modu MM_TEXT olduğunda aynı `y` üye için de geçerlidir. Üye `y` , MM_TEXT dışındaki eşleme modlarında negatiftir.

### <a name="remarks"></a>Açıklamalar

Bu noktanın pencerenin sol üst köşesinde olması için görünüm kaydırılacaktır. Görünüm sığacak şekilde ölçeklendirildiyse, bu üye işlevin çağrılmaması gerekir.

##  <a name="setscaletofitsize"></a>CScrollView:: SetScaleToFitSize

Görünüm `SetScaleToFitSize` penceresinin boyutunu otomatik olarak geçerli pencere boyutuna ölçeklendirmek istediğinizde çağırın.

```
void SetScaleToFitSize(SIZE sizeTotal);
```

### <a name="parameters"></a>Parametreler

*Toplam Boyut*<br/>
Görünümün ölçeklendirileceği yatay ve dikey boyutlar. Kaydırma görünümünün boyutu mantıksal birimlerde ölçülür. Yatay boyut `cx` üye içinde yer alır. Dikey boyut `cy` üye içinde yer alır. Her `cx` ikisi `cy` de 0 ' dan büyük veya buna eşit olmalıdır.

### <a name="remarks"></a>Açıklamalar

Kaydırma çubukları ile, yalnızca mantıksal görünümün bir kısmı herhangi bir zamanda görünür olabilir. Ancak ölçeklendirme özelliği sayesinde, görünümün bir kaydırma çubuğu yoktur ve mantıksal görünüm, pencerenin istemci alanına tam olarak sığacak şekilde uzatılır veya daraltıladır. Pencere yeniden boyutlandırılırken, görünüm verileri pencerenin boyutuna bağlı olarak yeni bir ölçekte çizer.

Bu çağrıyı genellikle `OnInitialUpdate` görünümün üye işlevindeki geçersiz `SetScaleToFitSize` kılmada olacak şekilde yerleştirebilirsiniz. Otomatik ölçeklendirmeyi istemiyorsanız, bunun yerine `SetScrollSizes` üye işlevini çağırın.

`SetScaleToFitSize`"sığacak kadar yaklaştır" işlemi uygulamak için kullanılabilir. Kaydırmayı `SetScrollSizes` yeniden başlatmak için kullanın.

`SetScaleToFitSize`Görünüm penceresinin boyutunun ayarlandığını varsayar. Çağrıldığında Görünüm penceresi boyutu ayarlanmamışsa `SetScaleToFitSize` bir onaylama işlemi alırsınız. Bunun gerçekleşmediğinden emin olmak için çağrılmadan `SetScaleToFitSize`önce aşağıdaki çağrıyı yapın:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

##  <a name="setscrollsizes"></a>CScrollView:: Setscrollboyutlar

Görünüm `SetScrollSizes` Güncellenme geldiğinde çağırın.

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

|Eşleme modu|Mantıksal birim|Pozitif y ekseni genişletiliyor...|
|------------------|------------------|---------------------------------|
|MM_TEXT|1 piksel|Aşağıya|
|MM_HIMETRIC|0,01 mm|Yukarıya|
|MM_TWIPS|1/1440|Yukarıya|
|MM_HIENGLISH|0,001|Yukarıya|
|MM_LOMETRIC|0,1 mm|Yukarıya|
|MM_LOENGLISH|0,01|Yukarıya|

Tüm bu modlar Windows tarafından tanımlanır. İki standart eşleme modu, MM_ISOTROPIC ve MM_ANISOTROPIC, için `CScrollView`kullanılmaz. Sınıf kitaplığı, görünümü pencere `SetScaleToFitSize` boyutuna ölçeklemek için üye işlevi sağlar. Yukarıdaki tabloda üçüncü sütun, koordinat yönünü açıklar.

*Toplam Boyut*<br/>
Kaydırma görünümünün toplam boyutu. `cx` Üye yatay kapsamı içerir. `cy` Üye dikey kapsamı içerir. Boyutlar mantıksal birimlerdir. Her `cx` ikisi `cy` de 0 ' dan büyük veya buna eşit olmalıdır.

*sizePage*<br/>
Bir kaydırma çubuğu biçimlendirbir çubukta fare tıklaması sırasında her yönde kaydırılan yatay ve dikey tutarlar. `cx` Üye yatay miktarı içerir. `cy` Üye dikey miktarı içerir.

*sizeLine*<br/>
Bir kaydırma okuna fare tıklaması için her yönde kaydırılan yatay ve dikey tutarlar. `cx` Üye yatay miktarı içerir. `cy` Üye dikey miktarı içerir.

### <a name="remarks"></a>Açıklamalar

Örneğin, belge başlangıçta veya boyut değiştirdiğinde `OnUpdate` , kaydırma özelliklerini ayarlamak için üye işlevini geçersiz kılmanızda çağırın.

Genellikle, türetilmiş belge sınıfınız ile sağladığınız bir belge üye işlevini `GetMyDocSize`çağırarak görünümün ilişkili belgesinden boyut bilgilerini elde edersiniz. Aşağıdaki kod bu yaklaşımı göstermektedir:

[!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]

Alternatif olarak, aşağıdaki kodda olduğu gibi bazen sabit bir boyut ayarlamanız gerekebilir:

[!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]

Eşleme modunu MM_ISOTROPIC veya MM_ANISOTROPIC dışında herhangi bir Windows eşleme modundan birine ayarlamanız gerekir. Kısıtlanmış olmayan bir eşleme modunu kullanmak istiyorsanız, `SetScaleToFitSize` `SetScrollSizes`yerine üye işlevini çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CSplitterWnd Sınıfı](../../mfc/reference/csplitterwnd-class.md)
