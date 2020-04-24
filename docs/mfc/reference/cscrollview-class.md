---
title: CScrollView Sınıfı
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
ms.openlocfilehash: 5d0eb163fae2aa5fc63470e1c499311ab1a402a6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754413"
---
# <a name="cscrollview-class"></a>CScrollView Sınıfı

Kaydırma özelliklerine sahip bir [CView.](../../mfc/reference/cview-class.md)

## <a name="syntax"></a>Sözdizimi

```
class CScrollView : public CView
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CScrollView::CScrollView](#cscrollview)|Bir `CScrollView` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CScrollView::CheckScrollBars](#checkscrollbars)|Kaydırma görünümünün yatay ve dikey kaydırma çubukları olup olmadığını gösterir.|
|[CScrollView::FillOutsideRect](#filloutsiderect)|Kaydırma alanının dışındaki görünümün alanını doldurur.|
|[CScrollView::GetDeviceScrollPosition](#getdevicescrollposition)|Aygıt birimlerinde geçerli kaydırma konumunu alır.|
|[CScrollView::GetDeviceScrollSizes](#getdevicescrollsizes)|Geçerli eşleme modunu, toplam boyutu ve kaydırılabilir görünümün satır ve sayfa boyutlarını alır. Boyutlar cihaz birimlerindedir.|
|[CScrollView::GetScrollPosition](#getscrollposition)|Geçerli kaydırma konumunu mantıksal birimler halinde alır.|
|[CScrollView::GetTotalSize](#gettotalsize)|Kaydırma görünümünün toplam boyutunu mantıksal birimler halinde alır.|
|[CScrollView::ResizeParentToFit](#resizeparenttofit)|Görünümün boyutunun çerçevesinin boyutunu dikte etmesine neden olur.|
|[CScrollView::Scrolltoposition](#scrolltoposition)|Görünümü mantıksal birimlerde belirtilen belirli bir noktaya kaydırır.|
|[CScrollView::SetscaleToFitSize](#setscaletofitsize)|Kaydırma görünümünü ölçeklendirme moduna sokar.|
|[CScrollView::SetScrollSizes](#setscrollsizes)|Kaydırma görünümünün eşleme modunu, toplam boyutunu ve yatay ve dikey kaydırma tutarlarını ayarlar.|

## <a name="remarks"></a>Açıklamalar

İleti eşlenen `CView` [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) ve [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) üye işlevlerini geçersiz kılarak, herhangi bir sınıfta niçin standart kaydırma yı işleyebilirsiniz. Ancak `CScrollView` `CView` yeteneklerine aşağıdaki özellikler ekler:

- Pencere ve görüntü alanı boyutlarını ve eşleme modlarını yönetir.

- Kaydırma çubuğu iletilerine yanıt olarak otomatik olarak kaydırılır.

- Klavyeden, kaydırma yapmayan bir fareden veya IntelliMouse tekerleğinden gelen iletilere yanıt olarak otomatik olarak kaydırılır.

Klavyeden gelen iletilere yanıt olarak otomatik olarak kaydırma katmak için, WM_KEYDOWN iletisi ekleyin ve VK_DOWN için test edin, VK_PREV ve [SetScrollPos'u](/windows/win32/api/winuser/nf-winuser-setscrollpos)arayın.

İleti eşlenen [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) ve [OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel) üye işlevlerini geçersiz kılarak fare tekerleği nin kaydırmasını işleyebilirsiniz. Onlar için `CScrollView`olduğu gibi , Bu üye işlevler [WM_MOUSEWHEEL](/windows/win32/inputdev/wm-mousewheel)için önerilen davranışı destekler , tekerlek rotasyon mesajı.

Otomatik kaydırma dan yararlanmak için görünüm sınıfınızı `CScrollView` 'dan' `CView`dan' dan türetin. Görünüm ilk oluşturulduğunda, belgenin boyutuna göre kaydırılabilir görünümün boyutunu hesaplamak istiyorsanız, `SetScrollSizes` [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) veya [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate)geçersiz kılmanızdan üye işlevi arayın. (Belgenin boyutunu sorgulamak için kendi kodunuzu yazmanız gerekir. Örneğin, [Karalama örneğine](../../overview/visual-cpp-samples.md)bakın.)

`SetScrollSizes` Üye işlevine yapılan çağrı, görünümün eşleme modunu, kaydırma görünümünün toplam boyutlarını ve yatay ve dikey kaydırma tutarlarını ayarlar. Tüm boyutlar mantıksal birimler halindedir. Görünümün mantıksal boyutu genellikle belgede depolanan verilerden hesaplanır, ancak bazı durumlarda sabit bir boyut belirtmek isteyebilirsiniz. Her iki yaklaşıma örnek olarak [Bkz. CScrollView::SetScrollSizes](#setscrollsizes).

Mantıksal birimlerde yatay ve dikey kaydırma tutarlarını belirtirsiniz. Varsayılan olarak, kullanıcı kaydırma kutusunun dışında bir kaydırma `CScrollView` çubuğu şaftını tıklatırsa, bir "sayfa" kaydırır. Kullanıcı kaydırma çubuğunun her iki ucundaki kaydırma `CScrollView` okunu tıklatırsa, bir "satır" kaydırır. Varsayılan olarak, bir sayfa görünümün toplam boyutunun 1/10'udur; bir satır sayfa boyutunun 1/10'udur. `SetScrollSizes` Üye işlevde özel boyutlar geçirerek bu varsayılan değerleri geçersiz kılın. Örneğin, yatay boyutu toplam boyutun genişliğinin bir kısmını ve dikey boyutu geçerli yazı tipindeki bir çizginin yüksekliğine ayarlayabilirsiniz.

Kaydırma yerine, `CScrollView` görünümü geçerli pencere boyutuna otomatik olarak ölçeklendirebilir. Bu modda, görünümkaydırma çubukları yoktur ve mantıksal görünüm pencerenin istemci alanına tam olarak uyacak şekilde uzatılır veya küçültülmüş. Bu sığacak şekilde bu özelliği kullanmak için [CScrollView::SetScaleToFitSize'ı](#setscaletofitsize)arayın. (Ya `SetScaleToFitSize` da, `SetScrollSizes`ama her ikisini de arayın.)

Türemiş `OnDraw` görünüm sınıfınızın üye işlevi `CScrollView` çağrılmadan önce, geçtiği `CPaintDC` aygıt bağlamı nesnesinin `OnDraw`görüntü bağlantı noktası kaynağını otomatik olarak ayarlar.

Kaydırma penceresiiçin görünüm kaynağının kaynağını `CScrollView` ayarlamak için [CView::OnPrepareDC'yi](../../mfc/reference/cview-class.md#onpreparedc)geçersiz kılar. Bu `CPaintDC` `CScrollView` `OnDraw`ayarlama, geçen aygıt bağlamı için otomatiktir, ancak kullandığınız diğer aygıt bağlamları için kendinizi aramanız `CScrollView::OnPrepareDC` gerekir, örneğin . `CClientDC` Kalemi, `CScrollView::OnPrepareDC` arka plan rengini ve diğer çizim özniteliklerini ayarlamak için geçersiz kılınabilir, ancak ölçeklendirme yapmak için taban sınıfı çağırabilirsiniz.

Kaydırma çubukları, aşağıdaki durumlarda gösterildiği gibi, görünüme göre üç yerde görünebilir:

- WS_HSCROLL ve WS_VSCROLL[Windows Stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles)kullanılarak görünüm için standart pencere tarzı kaydırma çubukları ayarlanabilir.

- Kaydırma çubuğu denetimleri görünümü içeren çerçeveye de eklenebilir ve bu durumda çerçeve çerçeve penceresinden şu anda etkin görünüme WM_HSCROLL ve WM_VSCROLL iletileri iletir.

- Çerçeve ayrıca kaydırma iletilerini bir `CSplitterWnd` ayırıcı denetiminden şu anda etkin olan ayırıcı bölmesine (görünüm) iletir. Paylaşılan kaydırma çubuklarına sahip bir [CSplitterWnd'e](../../mfc/reference/csplitterwnd-class.md) yerleştirildiğinde, bir `CScrollView` nesne kendi çubuklarını oluşturmak yerine paylaşılan olanları kullanır.

Kullanma `CScrollView`hakkında daha fazla bilgi için Bkz. [Belge/Görünüm Mimarisi](../../mfc/document-view-architecture.md) ve [Türetilmiş Görünüm Sınıfları MFC'de kullanılabilir.](../../mfc/derived-view-classes-available-in-mfc.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cview](../../mfc/reference/cview-class.md)

`CScrollView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cscrollviewcheckscrollbars"></a><a name="checkscrollbars"></a>CScrollView::CheckScrollBars

Kaydırma görünümünün yatay ve dikey çubuklara sahip olup olmadığını belirlemek için bu üye işlevi arayın.

```cpp
void CheckScrollBars(
    BOOL& bHasHorzBar,
    BOOL& bHasVertBar) const;
```

### <a name="parameters"></a>Parametreler

*bHasHorzBar*<br/>
Uygulamanın yatay kaydırma çubuğu olduğunu gösterir.

*bHasVertBar*<br/>
Uygulamanın dikey kaydırma çubuğu olduğunu gösterir.

## <a name="cscrollviewcscrollview"></a><a name="cscrollview"></a>CScrollView::CScrollView

Bir `CScrollView` nesne inşa eder.

```
CScrollView();
```

### <a name="remarks"></a>Açıklamalar

Kaydırma görünümü `SetScrollSizes` kullanılabilir `SetScaleToFitSize` hale gelmeden önce aramanız gerekir.

## <a name="cscrollviewfilloutsiderect"></a><a name="filloutsiderect"></a>CScrollView::FillOutsideRect

Kaydırma `FillOutsideRect` alanının dışında görünen görünümün alanını doldurmak için arayın.

```cpp
void FillOutsideRect(
    CDC* pDC,
    CBrush* pBrush);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Dolgunun yapılacağı aygıt bağlamı.

*pFırça*<br/>
Alanın doldurulması gereken fırça.

### <a name="remarks"></a>Açıklamalar

Aşırı `FillOutsideRect` arka plan yeniden `OnEraseBkgnd` boyamasını önlemek için kaydırma görünümünüzdeki işleyici işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]

## <a name="cscrollviewgetdevicescrollposition"></a><a name="getdevicescrollposition"></a>CScrollView::GetDeviceScrollPosition

Kaydırma `GetDeviceScrollPosition` çubuklarındaki kaydırma kutularının geçerli yatay ve dikey konumlarını istediğinizde arayın.

```
CPoint GetDeviceScrollPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırma kutularının `CPoint` nesne olarak yatay ve dikey konumları (aygıt birimlerinde).

### <a name="remarks"></a>Açıklamalar

Bu koordinat çifti, görünümün sol üst köşesinin kaydırıldığı belgedeki konuma karşılık gelir. Bu, fare aygıtı konumlarını aygıt konumlarını kaydırma-görüntülemek için kesmek için yararlıdır.

`GetDeviceScrollPosition`aygıt birimlerindeki değerleri döndürür. Mantıksal birimler istiyorsanız, `GetScrollPosition` bunun yerine kullanın.

## <a name="cscrollviewgetdevicescrollsizes"></a><a name="getdevicescrollsizes"></a>CScrollView::GetDeviceScrollSizes

`GetDeviceScrollSizes`geçerli eşleme modunu, toplam boyutu ve kaydırılabilir görünümün satır ve sayfa boyutlarını alır.

```cpp
void GetDeviceScrollSizes(
    int& nMapMode,
    SIZE& sizeTotal,
    SIZE& sizePage,
    SIZE& sizeLine) const;
```

### <a name="parameters"></a>Parametreler

*nMapMode*<br/>
Bu görünüm için geçerli eşleme modunu döndürür. Olası değerlerin listesi için `SetScrollSizes`bkz.

*boyutToplam*<br/>
Aygıt birimlerinde kaydırma görünümünün geçerli toplam boyutunu döndürür.

*boyutPage*<br/>
Kaydırma çubuğu şaftındaki bir fare tıklamasına yanıt olarak her yönde kaydırma yapmak için geçerli yatay ve dikey tutarları döndürür. Üye `cx` yatay tutarı içerir. Üye `cy` dikey miktarı içerir.

*boyutLine*<br/>
Kaydırma oktaki bir fare tıklamasına yanıt olarak her yönde kaydırma yapmak için geçerli yatay ve dikey tutarları döndürür. Üye `cx` yatay tutarı içerir. Üye `cy` dikey miktarı içerir.

### <a name="remarks"></a>Açıklamalar

Boyutlar cihaz birimlerindedir. Bu üye işlev nadiren çağrılır.

## <a name="cscrollviewgetscrollposition"></a><a name="getscrollposition"></a>CScrollView::GetScrollPosition

Kaydırma `GetScrollPosition` çubuklarındaki kaydırma kutularının geçerli yatay ve dikey konumlarını istediğinizde arayın.

```
CPoint GetScrollPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırma kutularının `CPoint` nesne olarak yatay ve dikey konumları (mantıksal birimler halinde).

### <a name="remarks"></a>Açıklamalar

Bu koordinat çifti, görünümün sol üst köşesinin kaydırıldığı belgedeki konuma karşılık gelir.

`GetScrollPosition`mantıksal birimlerde değerleri döndürür. Aygıt birimleri istiyorsanız, `GetDeviceScrollPosition` bunun yerine kullanın.

## <a name="cscrollviewgettotalsize"></a><a name="gettotalsize"></a>CScrollView::GetTotalSize

Kaydırma `GetTotalSize` görünümünün geçerli yatay ve dikey boyutlarını almak için arayın.

```
CSize GetTotalSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mantıksal birimlerde kaydırma görünümünün toplam boyutu. Yatay boyut, iade `cx` değerinin `CSize` üyesindedir. Dikey boyut `cy` üyededir.

## <a name="cscrollviewresizeparenttofit"></a><a name="resizeparenttofit"></a>CScrollView::ResizeParentToFit

Görünümünüzün boyutunun çerçeve penceresinin boyutunu belirlemesine izin vermek için arayın. `ResizeParentToFit`

```cpp
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```

### <a name="parameters"></a>Parametreler

*bShrinkSadece*<br/>
Gerçekleştirmek için yeniden boyutlandırma tür. Varsayılan değer TRUE, uygunsa çerçeve penceresini küçültür. Kaydırma çubukları büyük görünümler veya küçük çerçeve pencereler için görünmeye devam edecektir. FALSE değeri, görünümün çerçeve penceresini her zaman tam olarak yeniden boyutlandırmasına neden olur. Çerçeve penceresi birden çok belge arabirimi (MDI) çerçeve penceresi veya ekran içine sığmayacak kadar büyük alabilirsiniz bu biraz tehlikeli olabilir.

### <a name="remarks"></a>Açıklamalar

Bu yalnızca MDI alt çerçeve pencerelerinde görünümler için önerilir. `ResizeParentToFit` Türemiş `OnInitialUpdate` `CScrollView` sınıfınızın işleyici işlevinde kullanın. Bu üye işlevin bir örneği için [Bkz. CScrollView::SetScrollSizes](#setscrollsizes).

`ResizeParentToFit`görünüm penceresinin boyutunun ayarlandığını varsayar. Görünüm penceresi boyutu çağrıldığında `ResizeParentToFit` ayarlanmadıysa, bir iddia alırsınız. Bunun olmamasını sağlamak için, aramadan `ResizeParentToFit`önce aşağıdaki aramayı yapın:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

## <a name="cscrollviewscrolltoposition"></a><a name="scrolltoposition"></a>CScrollView::Scrolltoposition

Görünümde belirli bir noktaya kaydırmak için arayın. `ScrollToPosition`

```cpp
void ScrollToPosition(POINT pt);
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
Mantıksal birimler halinde kaydırma noktası. `x` Üye pozitif bir değer olmalıdır (görünümün toplam boyutuna kadar 0'dan büyük veya eşit). Eşleme modu MM_TEXT `y` olduğunda aynı durum üye için de geçerlidir. Üye, `y` MM_TEXT dışındaki eşleme modlarında negatiftir.

### <a name="remarks"></a>Açıklamalar

Görünüm, bu nokta pencerenin sol üst köşesinde olacak şekilde kaydırılır. Görünüm uyacak şekilde ölçeklendirildiyse, bu üye işlev çağrılmamalıdır.

## <a name="cscrollviewsetscaletofitsize"></a><a name="setscaletofitsize"></a>CScrollView::SetscaleToFitSize

Görünüm `SetScaleToFitSize` portu boyutunu geçerli pencere boyutuna otomatik olarak ölçeklendirmek istediğinizde arayın.

```cpp
void SetScaleToFitSize(SIZE sizeTotal);
```

### <a name="parameters"></a>Parametreler

*boyutToplam*<br/>
Görünümün ölçeklendirilecek yatay ve dikey boyutları. Kaydırma görünümünün boyutu mantıksal birimlerle ölçülür. Yatay boyut `cx` üyede bulunur. Dikey boyut `cy` üye bulunur. Her `cx` `cy` ikisi de ve 0'dan büyük veya eşit olmalıdır.

### <a name="remarks"></a>Açıklamalar

Kaydırma çubuklarıyla, mantıksal görünümün yalnızca bir bölümü herhangi bir zamanda görülebilir. Ancak ölçek-to-fit özelliği ile görünümü kaydırma çubukları vardır ve mantıksal görünüm pencerenin istemci alanına tam olarak uyacak şekilde gerilir veya küçültülmüş. Pencere yeniden boyutlandırıldığında, görünüm verilerini pencerenin boyutuna göre yeni bir ölçekte çizer.

Aramayı `SetScaleToFitSize` genellikle görünümün `OnInitialUpdate` üye işlevini geçersiz kılmanıza yerebilirsiniz. Otomatik ölçekleme istemiyorsanız, bunun yerine `SetScrollSizes` üye işlevi arayın.

`SetScaleToFitSize`"Sığdırmak için Yakınlaştırma" işlemi uygulamak için kullanılabilir. Kaydırmayı yeniden başlatmayı kullanın. `SetScrollSizes`

`SetScaleToFitSize`görünüm penceresinin boyutunun ayarlandığını varsayar. Görünüm penceresi boyutu çağrıldığında `SetScaleToFitSize` ayarlanmadıysa, bir iddia alırsınız. Bunun olmamasını sağlamak için, aramadan `SetScaleToFitSize`önce aşağıdaki aramayı yapın:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

## <a name="cscrollviewsetscrollsizes"></a><a name="setscrollsizes"></a>CScrollView::SetScrollSizes

Görünümün güncellenmek üzere olduğu zaman arayın. `SetScrollSizes`

```cpp
void SetScrollSizes(
    int nMapMode,
    SIZE sizeTotal,
    const SIZE& sizePage = sizeDefault,
    const SIZE& sizeLine = sizeDefault);
```

### <a name="parameters"></a>Parametreler

*nMapMode*<br/>
Bu görünüm için ayarlanan eşleme modu. Olası değerler şunlardır:

|Haritalama Modu|Mantıksal Birim|Pozitif y ekseni Genişletir...|
|------------------|------------------|---------------------------------|
|Mm_text|1 piksel|Aşağı|
|MM_HIMETRIC|0,01 mm|Yukarı|
|MM_TWIPS|1/1440 içinde|Yukarı|
|MM_HIENGLISH|0.001 yılında|Yukarı|
|MM_LOMETRIC|0,1 mm|Yukarı|
|MM_LOENGLISH|0.01 içinde|Yukarı|

Bu modların tümü Windows tarafından tanımlanır. MM_ISOTROPIC ve MM_ANISOTROPIC olmak üzere iki standart `CScrollView`eşleme modu kullanılmaz. Sınıf kitaplığı, `SetScaleToFitSize` görünümü pencere boyutuna ölçeklemek için üye işlevi sağlar. Yukarıdaki tablodaki üçüncü sütun koordinat yönünü açıklar.

*boyutToplam*<br/>
Kaydırma görünümünün toplam boyutu. Üye `cx` yatay ölçüde içerir. Üye `cy` dikey ölçüde içerir. Boyutlar mantıksal birimler halindedir. Her `cx` `cy` ikisi de ve 0'dan büyük veya eşit olmalıdır.

*boyutPage*<br/>
Yatay ve dikey tutarlar bir kaydırma çubuğu şaftBir fare tıklamaya yanıt olarak her yönde kaydırma. Üye `cx` yatay tutarı içerir. Üye `cy` dikey miktarı içerir.

*boyutLine*<br/>
Yatay ve dikey tutarlar bir kaydırma ok bir fare tıklamayanıt olarak her yönde kaydırma. Üye `cx` yatay tutarı içerir. Üye `cy` dikey miktarı içerir.

### <a name="remarks"></a>Açıklamalar

Kaydırma özelliklerini ayarlamak için `OnUpdate` üye işlevin geçersiz kılınmasını, örneğin belge ilk görüntülendiğinde veya boyut değiştirdiğinde çağırın.

Genellikle, türemiş belge sınıfınızla sağladığınız bir belge üye işlevini `GetMyDocSize`arayarak görünümün ilişkili belgesinden boyut bilgileri elde elabilirsiniz. Aşağıdaki kod bu yaklaşımı gösterir:

[!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]

Alternatif olarak, bazen aşağıdaki kodda olduğu gibi sabit bir boyut ayarlamanız gerekebilir:

[!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]

Eşleme modunu MM_ISOTROPIC veya MM_ANISOTROPIC dışında Windows eşleme modlarından herhangi biri için ayarlamanız gerekir. Sınırlandırılmamış bir eşleme modu kullanmak istiyorsanız, `SetScaleToFitSize` `SetScrollSizes`'' yerine üye işlevi arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CSplitterWnd Sınıfı](../../mfc/reference/csplitterwnd-class.md)
