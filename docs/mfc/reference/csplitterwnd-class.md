---
title: CSplitterWnd sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSplitterWnd
- AFXEXT/CSplitterWnd
- AFXEXT/CSplitterWnd::CSplitterWnd
- AFXEXT/CSplitterWnd::ActivateNext
- AFXEXT/CSplitterWnd::CanActivateNext
- AFXEXT/CSplitterWnd::Create
- AFXEXT/CSplitterWnd::CreateScrollBarCtrl
- AFXEXT/CSplitterWnd::CreateStatic
- AFXEXT/CSplitterWnd::CreateView
- AFXEXT/CSplitterWnd::DeleteColumn
- AFXEXT/CSplitterWnd::DeleteRow
- AFXEXT/CSplitterWnd::DeleteView
- AFXEXT/CSplitterWnd::DoKeyboardSplit
- AFXEXT/CSplitterWnd::DoScroll
- AFXEXT/CSplitterWnd::DoScrollBy
- AFXEXT/CSplitterWnd::GetActivePane
- AFXEXT/CSplitterWnd::GetColumnCount
- AFXEXT/CSplitterWnd::GetColumnInfo
- AFXEXT/CSplitterWnd::GetPane
- AFXEXT/CSplitterWnd::GetRowCount
- AFXEXT/CSplitterWnd::GetRowInfo
- AFXEXT/CSplitterWnd::GetScrollStyle
- AFXEXT/CSplitterWnd::IdFromRowCol
- AFXEXT/CSplitterWnd::IsChildPane
- AFXEXT/CSplitterWnd::IsTracking
- AFXEXT/CSplitterWnd::RecalcLayout
- AFXEXT/CSplitterWnd::SetActivePane
- AFXEXT/CSplitterWnd::SetColumnInfo
- AFXEXT/CSplitterWnd::SetRowInfo
- AFXEXT/CSplitterWnd::SetScrollStyle
- AFXEXT/CSplitterWnd::SplitColumn
- AFXEXT/CSplitterWnd::SplitRow
- AFXEXT/CSplitterWnd::OnDraw
- AFXEXT/CSplitterWnd::OnDrawSplitter
- AFXEXT/CSplitterWnd::OnInvertTracker
helpviewer_keywords:
- CSplitterWnd [MFC], CSplitterWnd
- CSplitterWnd [MFC], ActivateNext
- CSplitterWnd [MFC], CanActivateNext
- CSplitterWnd [MFC], Create
- CSplitterWnd [MFC], CreateScrollBarCtrl
- CSplitterWnd [MFC], CreateStatic
- CSplitterWnd [MFC], CreateView
- CSplitterWnd [MFC], DeleteColumn
- CSplitterWnd [MFC], DeleteRow
- CSplitterWnd [MFC], DeleteView
- CSplitterWnd [MFC], DoKeyboardSplit
- CSplitterWnd [MFC], DoScroll
- CSplitterWnd [MFC], DoScrollBy
- CSplitterWnd [MFC], GetActivePane
- CSplitterWnd [MFC], GetColumnCount
- CSplitterWnd [MFC], GetColumnInfo
- CSplitterWnd [MFC], GetPane
- CSplitterWnd [MFC], GetRowCount
- CSplitterWnd [MFC], GetRowInfo
- CSplitterWnd [MFC], GetScrollStyle
- CSplitterWnd [MFC], IdFromRowCol
- CSplitterWnd [MFC], IsChildPane
- CSplitterWnd [MFC], IsTracking
- CSplitterWnd [MFC], RecalcLayout
- CSplitterWnd [MFC], SetActivePane
- CSplitterWnd [MFC], SetColumnInfo
- CSplitterWnd [MFC], SetRowInfo
- CSplitterWnd [MFC], SetScrollStyle
- CSplitterWnd [MFC], SplitColumn
- CSplitterWnd [MFC], SplitRow
- CSplitterWnd [MFC], OnDraw
- CSplitterWnd [MFC], OnDrawSplitter
- CSplitterWnd [MFC], OnInvertTracker
ms.assetid: fd0de258-6dbe-4552-9e47-a39de0471d51
ms.openlocfilehash: 42913ddea7818636dce8d630ed2d79d13c19ce81
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302110"
---
# <a name="csplitterwnd-class"></a>CSplitterWnd sınıfı

Birden fazla bölme içeren bir pencere olan Bölümlendirici penceresinin işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CSplitterWnd : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSplitterWnd::CSplitterWnd](#csplitterwnd)|Çağrı oluşturmak için bir `CSplitterWnd` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSplitterWnd::ActivateNext](#activatenext)|Sonraki bölüm ya da önceki bölüm komut gerçekleştirir.|
|[CSplitterWnd::CanActivateNext](#canactivatenext)|Sonraki bölüm ya da önceki bölüm komut komutlarının mümkün olup olmadığını denetler.|
|[CSplitterWnd::Create](#create)|Dinamik Bölümlendirici pencere oluşturma ve buna eklemek için çağrı `CSplitterWnd` nesne.|
|[CSplitterWnd::CreateScrollBarCtrl](#createscrollbarctrl)|Paylaşılan bir kaydırma çubuğu denetimi oluşturur.|
|[CSplitterWnd::CreateStatic](#createstatic)|Statik Bölümlendirici pencereyi oluşturun ve buna eklemek için çağrı `CSplitterWnd` nesne.|
|[CSplitterWnd::CreateView](#createview)|Ayırıcı penceresi içinde bir bölme oluşturmak için çağırın.|
|[CSplitterWnd::DeleteColumn](#deletecolumn)|Ayırıcı penceresinden bir sütun siler.|
|[CSplitterWnd::DeleteRow](#deleterow)|Ayırıcı penceresinden bir satır siler.|
|[CSplitterWnd::DeleteView](#deleteview)|Ayırıcı penceresinden bir görünüm siler.|
|[CSplitterWnd::DoKeyboardSplit](#dokeyboardsplit)|Komutu, genellikle "Window Split." klavye gerçekleştirir|
|[CSplitterWnd::DoScroll](#doscroll)|Eşitlenmiş bölünmüş pencereyi eşzamanlı olarak kaydırmayı çalıştırır.|
|[CSplitterWnd::DoScrollBy](#doscrollby)|Bölünmüş Pencereler verilen sayıda piksel kadar kaydırır.|
|[CSplitterWnd::GetActivePane](#getactivepane)|Girintinin ya da çerçevedeki etkin görünüm etkin bölmeyi belirler.|
|[CSplitterWnd::GetColumnCount](#getcolumncount)|Geçerli bölmesinde sütun sayısını döndürür.|
|[CSplitterWnd::GetColumnInfo](#getcolumninfo)|Belirtilen sütunda bilgileri döndürür.|
|[CSplitterWnd::GetPane](#getpane)|Belirtilen satır ve sütunları bölmesine döndürür.|
|[CSplitterWnd::GetRowCount](#getrowcount)|Geçerli bölmesinde satır sayısını döndürür.|
|[CSplitterWnd::GetRowInfo](#getrowinfo)|Belirtilen sıra bilgi döndürür.|
|[CSplitterWnd::GetScrollStyle](#getscrollstyle)|Paylaşılan bir kaydırma çubuğu stili döndürür.|
|[CSplitterWnd::IdFromRowCol](#idfromrowcol)|Alt bölmesinde belirtilen satır ve sütunları penceresi Kimliğini döndürür.|
|[CSplitterWnd::IsChildPane](#ischildpane)|Pencerenin şu anda bu ayırıcı penceresi için bir alt bölme olup olmadığını belirlemek için çağrılır.|
|[CSplitterWnd::IsTracking](#istracking)|Ayırıcıyı şu anda taşınırken, belirler.|
|[CSplitterWnd::RecalcLayout](#recalclayout)|Ayırıcı penceresi satır veya sütun boyutu ayarladıktan sonra görüntülemek için çağırın.|
|[CSplitterWnd::SetActivePane](#setactivepane)|Çerçevede etkin olmasını bölmesi ayarlar.|
|[CSplitterWnd::SetColumnInfo](#setcolumninfo)|Belirtilen sütun bilgisi ayarlamak için çağrılır.|
|[CSplitterWnd::SetRowInfo](#setrowinfo)|Belirtilen satır ayarlamak için çağrılır.|
|[CSplitterWnd::SetScrollStyle](#setscrollstyle)|Bölme pencerenin yeni kaydırma çubuğu stili paylaşılan kaydırma çubuğu desteği belirtir.|
|[CSplitterWnd::SplitColumn](#splitcolumn)|Bir çerçeve penceresinin dikey olarak bölündüğünü belirtir.|
|[CSplitterWnd::SplitRow](#splitrow)|Bir çerçeve penceresinin yatay olarak bölündüğünü belirtir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSplitterWnd::OnDraw](#ondraw)|Ayırıcı penceresi çizmek için framework tarafından çağırılır.|
|[CSplitterWnd::OnDrawSplitter](#ondrawsplitter)|Bölünmüş pencere görüntüsünü işler.|
|[CSplitterWnd::OnInvertTracker](#oninverttracker)|Boyutu ve şekli çerçeve penceresi olarak aynı olacak şekilde bir bölünmüş pencere görüntüsünü işler.|

## <a name="remarks"></a>Açıklamalar

Bir bölme genellikle türetilen bir uygulamaya özgü nesnedir [CView](../../mfc/reference/cview-class.md), ancak herhangi olabilir [CWnd](../../mfc/reference/cwnd-class.md) uygun alt penceresi kimliğe sahip nesne

A `CSplitterWnd` nesne bir üst genellikle katıştırılmış [CFrameWnd](../../mfc/reference/cframewnd-class.md) veya [Cmdıchildwnd](../../mfc/reference/cmdichildwnd-class.md) nesne. Oluşturma bir `CSplitterWnd` aşağıdaki adımları kullanarak nesne:

1. Ekleme bir `CSplitterWnd` üst çerçevenin üye değişkeni.

2. Geçersiz kılma üst çerçeve [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) üye işlevi.

3. Gelen geçersiz kılınan içinde `OnCreateClient`, çağrı [Oluştur](#create) veya [CreateStatic](#createstatic) üye işlevini `CSplitterWnd`.

Çağrı `Create` dinamik Bölümlendirici pencere oluşturmak için üye işlevi. Dinamik Bölümlendirici pencere genellikle oluşturup birkaç tek tek bölmeleri ya da aynı belgede görünümlerini kaydırma için kullanılır. Framework bölme için bir başlangıç bölmesinde otomatik olarak oluşturur. ardından framework oluşturur, yeniden boyutlandırır ve kullanıcı Bölümlendirici pencere denetimleri çalıştığı gibi çalışır, ek bölmeleri siler.

Çağırdığınızda `Create`, belirlemek bölmelerini tam olarak görüntülenecek çok küçük olduğunda bir en küçük satır yüksekliğini ve sütun genişliğini belirtin. Çağırdıktan sonra `Create`, bu alt sınır çağırarak yapabilirsiniz [SetColumnInfo](#setcolumninfo) ve [SetRowInfo](#setrowinfo) üye işlevleri.

Ayrıca `SetColumnInfo` ve `SetRowInfo` üye işlevleri, bir sütun için "en uygun" bir genişlik ve bir satır için "en uygun" yükseklik ayarlamak için. Framework bir ayırıcı penceresi görüntülendiğinde, ilk ayırıcı penceresi üst çerçeve görüntüler. Framework sonra sol üst köşesinden bölme pencerenin istemci alanının sağ alt köşesindeki çalışma kendi ideal boyutlarını göre satırları ve sütunları bölmelerinde düzenlediğinden.

Dinamik Bölümlendirici pencere tüm bölmelerde aynı sınıfı olmalıdır. Dinamik Bölümlendirici pencereler destekleyen tanıdık uygulamalar, Microsoft Word ve Microsoft Excel içerir.

Kullanım `CreateStatic` statik Bölümlendirici pencere oluşturmak için üye işlevi. Kullanıcının yalnızca bir statik Bölümlendirici pencere veya değil, kendi numarası sipariş bölmelerinde boyutunu değiştirebilirsiniz.

Statik Bölümlendirici oluşturduğunuzda, tüm statik Bölümlendirici 's bölmeleri özellikle oluşturmanız gerekir. Ana çerçeve önce tüm bölmeleri oluşturduğunuzdan emin olun `OnCreateClient` üye işlevi döndürür veya pencerenin doğru görüntüleme framework olacaktır.

`CreateStatic` Üye işlevi, en küçük satır yüksekliğini ve sütun genişliği 0 olan bir statik Bölümlendirici otomatik olarak başlatır. Çağırdıktan sonra `Create`, bu alt sınır çağırarak ayarlamak [SetColumnInfo](#setcolumninfo) ve [SetRowInfo](#setrowinfo) üye işlevleri. Ayrıca `SetColumnInfo` ve `SetRowInfo` çağırdıktan sonra `CreateStatic` belirtmek için ideal bölmesinde boyutları istenen.

Statik Bölümlendirici tek tek bölmeleri genellikle farklı sınıflara ait. Statik Bölümlendirici pencereler örnekleri için grafik düzenleyiciyi ve Windows Dosya Yöneticisi bakın.

Ayırıcı penceresi özel kaydırma çubukları (dışında bir bölmeye sahip olabilirsiniz kaydırma çubukları) destekler. Bu kaydırma çubukları alt öğeleri olan `CSplitterWnd` nesne ve bölmeleri ile paylaşılır.

Ayırıcı penceresi oluşturduğunuzda, bu özel kaydırma çubukları oluşturun. Örneğin, bir `CSplitterWnd` sahip bir satır, iki sütun ve WS_VSCROLL stili iki bölme tarafından paylaşılan bir dikey kaydırma çubuğu görüntülenir. Kullanıcı kaydırma çubuğunu hareket ettirdiğinde WM_VSCROLL iletileri için her iki bölmenin gönderilir. Bölmeleri kaydırma çubuğu konumu ayarladığınızda, paylaşılan bir kaydırma çubuğunun ayarlanır.

Bölümlendirici pencereler hakkında daha fazla bilgi için bkz: [Teknik Not 29](../../mfc/tn029-splitter-windows.md).

Dinamik Bölümlendirici pencereler oluşturma hakkında daha fazla bilgi için bkz:

- MFC örnek [karalama](../../visual-cpp-samples.md)

- MFC örnek [VIEWEX](../../visual-cpp-samples.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSplitterWnd`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxext.h

##  <a name="activatenext"></a>  CSplitterWnd::ActivateNext

Sonraki bölüm ya da önceki bölüm komutu gerçekleştirmek için framework tarafından çağırılır.

```
virtual void ActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>Parametreler

*bPrev*<br/>
Etkinleştirmek için pencereyi gösterir. **DOĞRU** için önceki; **FALSE** sonraki için.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi tarafından kullanılan üst düzey bir komuttur [CView](../../mfc/reference/cview-class.md) sınıfı temsilci olarak `CSplitterWnd` uygulaması.

##  <a name="canactivatenext"></a>  CSplitterWnd::CanActivateNext

Sonraki bölüm ya da önceki bölüm komutu şu anda mümkün olup olmadığını denetlemek için framework tarafından çağırılır.

```
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>Parametreler

*bPrev*<br/>
Etkinleştirmek için pencereyi gösterir. **DOĞRU** için önceki; **FALSE** sonraki için.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi tarafından kullanılan üst düzey bir komuttur [CView](../../mfc/reference/cview-class.md) sınıfı temsilci olarak `CSplitterWnd` uygulaması.

##  <a name="create"></a>  CSplitterWnd::Create

Dinamik Bölümlendirici pencere oluşturmak için arama `Create` üye işlevi.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    int nMaxRows,
    int nMaxCols,
    SIZE sizeMin,
    CCreateContext* pContext,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_HSCROLL | WS_VSCROLL | SPLS_DYNAMIC_SPLIT,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Bölümlendirici penceresinin üst çerçeve penceresi.

*nMaxRows*<br/>
Ayırıcı penceresi satır sayısı. Bu değer, 2 aşmamalıdır.

*nMaxCols*<br/>
Ayırıcı penceresi sütunlardaki maksimum sayısı. Bu değer, 2 aşmamalıdır.

*sizeMin*<br/>
Bir bölme görüntülenebilir en küçük boyutu belirtir.

*pContext*<br/>
Bir işaretçi bir [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısı. Çoğu durumda, bu olabilir *pContext* ana çerçeve penceresine geçirildi.

*dwStyle*<br/>
Pencere stilini belirtir.

*nID*<br/>
Pencerenin alt penceresi kimliği. Ayırıcı penceresi başka bir ayırıcı penceresi içinde iç içe sürece kimlik AFX_IDW_PANE_FIRST olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Katıştırabilirsiniz bir `CSplitterWnd` , üst bir [CFrameWnd](../../mfc/reference/cframewnd-class.md) veya [Cmdıchildwnd](../../mfc/reference/cmdichildwnd-class.md) aşağıdaki adımların atılmasından nesnesi:

1. Ekleme bir `CSplitterWnd` üst çerçevenin üye değişkeni.

1. Geçersiz kılma üst çerçeve [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) üye işlevi.

1. Çağrı `Create` içinde geçersiz kılınan üye işlev `OnCreateClient`.

Üst çerçevenin üst çerçeve içinde bir ayırıcı penceresi oluşturduğunuzda geçirmek *pContext* ayırıcı penceresi için parametre. Aksi takdirde, bu parametre NULL olabilir.

Dinamik Bölümlendirici penceresinin başlangıç en küçük satır yüksekliğini ve sütun genişliğini ayarlanmış *sizeMin* parametresi. Bir bölme sunabilen gösterilecek küçük olup olmadığını belirlemek, bu alt sınır değiştirilebilir [SetRowInfo](#setrowinfo) ve [SetColumnInfo](#setcolumninfo) üye işlevleri.

Dinamik Bölümlendirici pencereler hakkında daha fazla bilgi için "Bölücü Windows" makalesine bakın [birden çok belge türü, görünümler ve çerçeve Windows](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik Not 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfına genel bakış.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]

##  <a name="createscrollbarctrl"></a>  CSplitterWnd::CreateScrollBarCtrl

Paylaşılan bir kaydırma çubuğu denetimi oluşturmak için framework tarafından çağırılır.

```
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Pencere stilini belirtir.

*nID*<br/>
Pencerenin alt penceresi kimliği. Ayırıcı penceresi başka bir ayırıcı penceresi içinde iç içe sürece kimlik AFX_IDW_PANE_FIRST olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Geçersiz kılma `CreateScrollBarCtrl` için bir kaydırma çubuğunun yanındaki ek denetimleri içerir. Normal Windows kaydırma çubuğu denetimleri oluşturmak için varsayılan davranıştır.

##  <a name="createstatic"></a>  CSplitterWnd::CreateStatic

Statik Bölümlendirici pencere oluşturmak için arama `CreateStatic` üye işlevi.

```
virtual BOOL CreateStatic(
    CWnd* pParentWnd,
    int nRows,
    int nCols,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Bölümlendirici penceresinin üst çerçeve penceresi.

*nRows*<br/>
Satır sayısı. Bu değer, 16 aşmamalıdır.

*nCols*<br/>
Sütun sayısı. Bu değer, 16 aşmamalıdır.

*dwStyle*<br/>
Pencere stilini belirtir.

*nID*<br/>
Pencerenin alt penceresi kimliği. Ayırıcı penceresi başka bir ayırıcı penceresi içinde iç içe sürece kimlik AFX_IDW_PANE_FIRST olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

A `CSplitterWnd` genellikle bir üst katıştırılmış `CFrameWnd` veya [Cmdıchildwnd](../../mfc/reference/cmdichildwnd-class.md) aşağıdaki adımların atılmasından nesnesi:

1. Ekleme bir `CSplitterWnd` üst çerçevenin üye değişkeni.

1. Geçersiz kılma üst çerçeve `OnCreateClient` üye işlevi.

1. Çağrı `CreateStatic` içinde geçersiz kılınan üye işlev [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient).

Statik Bölümlendirici pencere bölmeleri, genellikle farklı sınıflardan sabit sayıda içerir.

Statik Bölümlendirici pencere oluşturduğunuzda, aynı anda tüm bölmeleri oluşturmanız gerekir. [CreateView](#createview) üye işlevi, bu amaç için genellikle kullanılır, ancak diğer nonview sınıfları da oluşturabilirsiniz.

Statik Bölümlendirici pencere ilk en küçük satır yüksekliğini ve sütun genişliği 0'dır. Bir bölme sunabilen gösterilecek küçük olduğunda belirlemek, bu alt sınır değiştirilebilir [SetRowInfo](#setrowinfo) ve [SetColumnInfo](#setcolumninfo) üye işlevleri.

Statik Bölümlendirici pencere kaydırma çubukları eklemek, WS_HSCROLL ve WS_VSCROLL stillerine ekleme *dwStyle*.

"Bölücü Windows" makalesine bakın [birden çok belge türü, görünümler ve çerçeve Windows](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik Not 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfı genel statik Bölümlendirici pencereler hakkında daha fazla bilgi.

##  <a name="createview"></a>  CSplitterWnd::CreateView

Statik ayırıcı penceresi için paneller oluşturur.

```
virtual BOOL CreateView(
    int row,
    int col,
    CRuntimeClass* pViewClass,
    SIZE sizeInit,
    CCreateContext* pContext);
```

### <a name="parameters"></a>Parametreler

*Satır*<br/>
Yeni Görünüm yerleştirileceği Bölümlendirici pencere satırı belirtir.

*sütun*<br/>
Yeni Görünüm yerleştirileceği Bölümlendirici pencere sütunu belirtir.

*pViewClass*<br/>
Belirtir [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yeni görünümün.

*sizeInit*<br/>
Yeni Görünüm başlangıç boyutunu belirtir.

*pContext*<br/>
Görünümü oluşturmak için kullanılan bir oluşturma bağlamına bir işaretçi (genellikle *pContext* üst çerçeve geçersiz kılınan geçirilen [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) ayırıcı penceresi olduğu üye işlevi oluşturulan).

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Statik Bölümlendirici penceresinin tüm bölmeleri framework Bölümlendirici görüntülemeden önce oluşturulması gerekir.

Framework ayrıca kullanıcının dinamik Bölümlendirici pencere bölmesi, satır veya sütun bölündüğünde yeni bölmesi oluşturmak için bu üye işlevini çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#4](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]

##  <a name="csplitterwnd"></a>  CSplitterWnd::CSplitterWnd

Çağrı oluşturmak için bir `CSplitterWnd` nesne.

```
CSplitterWnd();
```

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CSplitterWnd` iki adımda nesne. İlk olarak, oluşturan oluşturucu çağrısı `CSplitterWnd` nesnesi ve ardından çağırın [Oluştur](#create) ayırıcı penceresi oluşturur ve ona ekler üye işlevi `CSplitterWnd` nesne.

##  <a name="deletecolumn"></a>  CSplitterWnd::DeleteColumn

Ayırıcı penceresinden bir sütun siler.

```
virtual void DeleteColumn(int colDelete);
```

### <a name="parameters"></a>Parametreler

*colDelete*<br/>
Silinecek sütunu belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi (diğer bir deyişle, ayırıcı penceresi SPLS_DYNAMIC_SPLIT stili yoksa) mantığı dinamik Bölümlendirici penceresinin uygulamak için framework tarafından çağırılır. Bu, sanal işlev birlikte özelleştirilebilir [CreateView](#createview), daha gelişmiş dinamik ayırıcılar uygulamak için.

##  <a name="deleterow"></a>  CSplitterWnd::DeleteRow

Ayırıcı penceresinden bir satır siler.

```
virtual void DeleteRow(int rowDelete);
```

### <a name="parameters"></a>Parametreler

*rowDelete*<br/>
Silinecek satırın belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi (diğer bir deyişle, ayırıcı penceresi SPLS_DYNAMIC_SPLIT stili yoksa) mantığı dinamik Bölümlendirici penceresinin uygulamak için framework tarafından çağırılır. Bu, sanal işlev birlikte özelleştirilebilir [CreateView](#createview), daha gelişmiş dinamik ayırıcılar uygulamak için.

##  <a name="deleteview"></a>  CSplitterWnd::DeleteView

Ayırıcı penceresinden bir görünüm siler.

```
virtual void DeleteView(
    int row,
    int col);
```

### <a name="parameters"></a>Parametreler

*Satır*<br/>
Ayırıcı penceresi satır görünümü silmek istediğiniz sonunda belirtir.

*sütun*<br/>
Bölümlendirici pencere sütununda görünümü silmek istediğiniz belirtir.

### <a name="remarks"></a>Açıklamalar

Etkin görünüm siliniyor, sonraki görünüme etkin hale gelir. Varsayılan uygulama görünümü otomatik varsayar sildiğiniz [PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy).

Bu üye işlevi (diğer bir deyişle, ayırıcı penceresi SPLS_DYNAMIC_SPLIT stili yoksa) mantığı dinamik Bölümlendirici penceresinin uygulamak için framework tarafından çağırılır. Bu, sanal işlev birlikte özelleştirilebilir [CreateView](#createview), daha gelişmiş dinamik ayırıcılar uygulamak için.

##  <a name="dokeyboardsplit"></a>  CSplitterWnd::DoKeyboardSplit

Komutu, genellikle "Window Split." klavye gerçekleştirir

```
virtual BOOL DoKeyboardSplit();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi tarafından kullanılan üst düzey bir komuttur [CView](../../mfc/reference/cview-class.md) sınıfı temsilci olarak `CSplitterWnd` uygulaması.

##  <a name="doscroll"></a>  CSplitterWnd::DoScroll

Eşitlenmiş bölünmüş pencereyi eşzamanlı olarak kaydırmayı çalıştırır.

```
virtual BOOL DoScroll(
    CView* pViewFrom,
    UINT nScrollCode,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parametreler

*pViewFrom*<br/>
Kaydırma ileti kaynaklandığı görünümü için bir işaretçi.

*nScrollCode*<br/>
Kullanıcı gösteren bir kaydırma çubuğu kodu istek kaydırma. Bu parametre, iki bölümden oluşur: yatay kaydırma gerçekleşen türünü belirleyen bir alt sıra bayt ve dikey kaydırma gerçekleşen türünü belirleyen bir yüksek düzeyli bayt:

    - Yukarıdan aşağıya SB_BOTTOM kaydırır.

    - Bir satır aşağı SB_LINEDOWN kaydırır.

    - Bir satır yukarı SB_LINEUP kaydırır.

    - Bir sayfa aşağı SB_PAGEDOWN kaydırır.

    - Bir sayfa yukarı SB_PAGEUP kaydırır.

    - En üste SB_TOP kaydırır.

*bDoScroll*<br/>
Belirtilen kayan eylem oluşup oluşmadığını belirler. Varsa *bDoScroll* olduğu yerde; belirtilen kayan eylem sürebilir (diğer bir deyişle, bir alt penceresi olup olmadığını ve bölünmüş windows kaydırma aralığı varsa) ise TRUE *bDoScroll* FALSE (diğer bir deyişle, alt penceresi yok ise yoksa, veya bölünmüş görünümleri kaydırma aralık yok), sonra kaydırma oluşmaz.

### <a name="return-value"></a>Dönüş Değeri

Eşitlenmiş kaydırma olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi görünümü kaydırma ileti aldığında bölünmüş pencereyi eşzamanlı kaydırma gerçekleştirmek için framework tarafından çağırılır. Eşitleme kaydırma izin verilmeden önce bir eylem kullanıcı tarafından zorunlu tutmak için geçersiz kılın.

##  <a name="doscrollby"></a>  CSplitterWnd::DoScrollBy

Bölünmüş Pencereler verilen sayıda piksel kadar kaydırır.

```
virtual BOOL DoScrollBy(
    CView* pViewFrom,
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parametreler

*pViewFrom*<br/>
Kaydırma ileti kaynaklandığı görünümü için bir işaretçi.

*sizeScroll*<br/>
Yatay ve dikey olarak kaydırılan piksel sayısı.

*bDoScroll*<br/>
Belirtilen kayan eylem oluşup oluşmadığını belirler. Varsa *bDoScroll* olduğu yerde; belirtilen kayan eylem sürebilir (diğer bir deyişle, bir alt penceresi olup olmadığını ve bölünmüş windows kaydırma aralığı varsa) ise TRUE *bDoScroll* FALSE (diğer bir deyişle, alt penceresi yok ise yoksa, veya bölünmüş görünümleri kaydırma aralık yok), sonra kaydırma oluşmaz.

### <a name="return-value"></a>Dönüş Değeri

Eşitlenmiş kaydırma olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi kaydırma iletiye yanıt olarak çerçevesi tarafından çağrılır, piksel cinsinden tarafından belirtilen miktara göre bölünmüş pencereyi kaydırma gerçekleştirmek için eşitlenmiş *sizeScroll*. Pozitif değerler aşağı ve sağa doğru kaydırma gösterir; Yukarı ve sola kaydırma, negatif değerleri göstermek.

Kaydırma izin vermeden önce bir eylem kullanıcı tarafından zorunlu tutmak için geçersiz kılın.

##  <a name="getactivepane"></a>  CSplitterWnd::GetActivePane

Girintinin ya da çerçevedeki etkin görünüm etkin bölmeyi belirler.

```
virtual CWnd* GetActivePane(
    int* pRow = NULL,
    int* pCol = NULL);
```

### <a name="parameters"></a>Parametreler

*pRow*<br/>
Bir işaretçi bir **int** etkin bölmeyi satır sayısı alınamıyor.

*pCol*<br/>
Bir işaretçi bir **int** etkin bölmede sütun sayısını almak için.

### <a name="return-value"></a>Dönüş Değeri

Etkin bölmede işaretçisi. Hiçbir etkin bölmeyi yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, bir ayırıcı penceresi etkin bölmede belirlemek için framework tarafından çağırılır. Etkin bölmede alma önce bir eylem kullanıcı tarafından zorunlu tutmak için geçersiz kılın.

##  <a name="getcolumncount"></a>  CSplitterWnd::GetColumnCount

Geçerli bölmesinde sütun sayısını döndürür.

```
int GetColumnCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayırıcı geçerli sütun sayısı döndürür. Statik bir ayırıcı için bu maksimum sütun sayısını olacaktır.

##  <a name="getcolumninfo"></a>  CSplitterWnd::GetColumnInfo

Belirtilen sütunda bilgileri döndürür.

```
void GetColumnInfo(
    int col,
    int& cxCur,
    int& cxMin) const;
```

### <a name="parameters"></a>Parametreler

*sütun*<br/>
Bir sütunu belirtir.

*cxCur*<br/>
Bir başvuru bir **int** geçerli sütunun genişliği için ayarlanacak.

*cxMin*<br/>
Bir başvuru bir **int** sütun geçerli minimum genişliğini ayarlamak için.

##  <a name="getpane"></a>  CSplitterWnd::GetPane

Belirtilen satır ve sütunları bölmesine döndürür.

```
CWnd* GetPane(
    int row,
    int col) const;
```

### <a name="parameters"></a>Parametreler

*Satır*<br/>
Bir satır belirtir.

*sütun*<br/>
Bir sütunu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen satır ve sütunları bölmesine döndürür. Döndürülen genellikle bölmesidir bir [CView](../../mfc/reference/cview-class.md)-türetilmiş sınıf.

##  <a name="getrowcount"></a>  CSplitterWnd::GetRowCount

Geçerli bölmesinde satır sayısını döndürür.

```
int GetRowCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mevcut satır sayısı Bölümlendirici pencereyi döndürür. Statik Bölümlendirici pencere için bu maksimum satır sayısı olacaktır.

##  <a name="getrowinfo"></a>  CSplitterWnd::GetRowInfo

Belirtilen sıra bilgi döndürür.

```
void GetRowInfo(
    int row,
    int& cyCur,
    int& cyMin) const;
```

### <a name="parameters"></a>Parametreler

*Satır*<br/>
Bir satır belirtir.

*cyCur*<br/>
Başvuru **int** geçerli yüksekliğini piksel cinsinden ayarlanması.

*cyMin*<br/>
Başvuru **int** geçerli en küçük yüksekliğini piksel cinsinden satır için ayarlanacak.

### <a name="remarks"></a>Açıklamalar

Belirtilen satırın hakkında bilgi edinmek için bu üye işlevini çağırın. *CyCur* parametresi geçerli belirtilen satırın yüksekliği ile doldurulur ve *cyMin* satırın minimum yükseklik ile doldurulur.

##  <a name="getscrollstyle"></a>  CSplitterWnd::GetScrollStyle

Ayırıcı penceresi için paylaşılan bir kaydırma çubuğu stili döndürür.

```
DWORD GetScrollStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir veya daha fazla aşağıdaki windows bayrakları, başarılı olursa stili:

    - WS_HSCROLL Bölümlendirici şu anda yönetiyorsa yatay kaydırma çubuklarını paylaşılan.

    - WS_VSCROLL Bölümlendirici şu anda yönetiyorsa dikey kaydırma çubukları paylaşılan.

Ayırıcı penceresi sıfır ise, şu anda paylaşılan bir kaydırma çubuğu yönetmez.

##  <a name="idfromrowcol"></a>  CSplitterWnd::IdFromRowCol

Alt pencere bölmesinde belirtilen satır ve sütun kimliği alır.

```
int IdFromRowCol(
    int row,
    int col) const;
```

### <a name="parameters"></a>Parametreler

*Satır*<br/>
Ayırıcı penceresi satır belirtir.

*sütun*<br/>
Bölümlendirici pencere sütunu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Alt pencere bölmesi için kimliği.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi nonviews bölmeleri olarak oluşturmak için kullanılır ve bölmesi var. önce çağrılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#5](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]

##  <a name="ischildpane"></a>  CSplitterWnd::IsChildPane

Belirler olmadığını *pWnd* şu anda bu ayırıcı penceresi için bir alt bölme aşamasındadır.

```
BOOL IsChildPane(
    CWnd* pWnd,
    int* pRow,
    int* pCol);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) sınanacak nesne.

*pRow*<br/>
Bir işaretçi bir **int** depolanacağı satır numarası.

*pCol*<br/>
Bir işaretçi bir **int** depolanacağı bir sütun numarası.

### <a name="return-value"></a>Dönüş Değeri

Sıfır olmayan, *pWnd* şu anda bir alt bu Bölümlendirici penceresinin bölmesidir ve *pRow* ve *pCol* ayırıcı penceresi bölmesinin konumu doldurulur. Varsa *pWnd* alt bölmesi bu ayırıcı penceresi 0 olarak döndürülür.

### <a name="remarks"></a>Açıklamalar

' Sürümlerinde Visual C++ 6.0 önce bu işlev olarak tanımlandı

`BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`

Bu sürümü artık kullanımdan kalkmıştır ve kullanılmamalıdır.

##  <a name="istracking"></a>  CSplitterWnd::IsTracking

Ayırıcıyı penceresinde şu anda taşınırken, belirlemek için bu üye işlevini çağırın.

```
BOOL IsTracking();
```

### <a name="return-value"></a>Dönüş Değeri

Bölme işlemi devam ederken olursa sıfır dışı; Aksi durumda 0.

##  <a name="ondrawsplitter"></a>  CSplitterWnd::OnDrawSplitter

Bölünmüş pencere görüntüsünü işler.

```
virtual void OnDrawSplitter(
    CDC* pDC,
    ESplitType nType,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Cihaz bağlamında çizmek için bir işaretçi. Varsa *pDC* NULL ise [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) çağrılır pencere çerçevesi ve bölme tarafından çizilir.

*nTür*<br/>
Değerini `enum ESplitType`, olabilen aşağıdakilerden biri:

    - `splitBox` Bölümlendirici Sürükle kutusu.

    - `splitBar` Çubuk iki Bölünmüş Pencereler arasında görünür.

    - `splitIntersection` Bölünmüş pencereyi kesişimidir. Bu öğe Windows 95/98 çalıştırılırken çağrılacak değil.

    - `splitBorder` Bölünmüş pencere kenarlıklarını.

*Rect*<br/>
Bir başvuru bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesne boyutu ve şekli bölünmüş Windows belirtme.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi çizmek ve tam bir ayırıcı penceresi özelliklerini belirlemek için framework tarafından çağırılır. Geçersiz kılma `OnDrawSplitter` gözünüzde bir ayırıcı penceresi çeşitli grafik bileşenleri için Gelişmiş özelleştirme için. Ayırıcı çubukları bağlandıkları birlikte karıştırılan, varsayılan tanımayı içinde Windows ya da Microsoft Windows 95/98, Microsoft Works Bölümlendirici benzer.

Dinamik Bölümlendirici pencereler hakkında daha fazla bilgi için "Bölücü Windows" makalesine bakın [birden çok belge türü, görünümler ve çerçeve Windows](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik Not 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfına genel bakış.

##  <a name="oninverttracker"></a>  CSplitterWnd::OnInvertTracker

Boyutu ve şekli çerçeve penceresi olarak aynı olacak şekilde bir bölünmüş pencere görüntüsünü işler.

```
virtual void OnInvertTracker(const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Başvuru bir `CRect` izleme dikdörtgen belirterek nesne.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi ayırıcılar yeniden boyutlandırma sırasında framework tarafından çağırılır. Geçersiz kılma `OnInvertTracker` Bölümlendirici penceresinin tanımayı Gelişmiş özelleştirme için. Ayırıcı çubukları bağlandıkları birlikte karıştırılan, varsayılan tanımayı içinde Windows ya da Microsoft Windows 95/98, Microsoft Works Bölümlendirici benzer.

Dinamik Bölümlendirici pencereler hakkında daha fazla bilgi için "Bölücü Windows" makalesine bakın [birden çok belge türü, görünümler ve çerçeve Windows](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik Not 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfına genel bakış.

##  <a name="recalclayout"></a>  CSplitterWnd::RecalcLayout

Ayırıcı penceresi satır veya sütun boyutu ayarladıktan sonra görüntülemek için çağırın.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Açıklamalar

Ayırıcı penceresi satır ve sütun boyutları ile ayarlanan sonra doğru şekilde görüntülemek için bu üye işlevini çağırın [SetRowInfo](#setrowinfo) ve [SetColumnInfo](#setcolumninfo) üye işlevleri. Ayırıcı penceresi görünür hale gelmeden önce oluşturma işleminin bir parçası satır ve sütun boyutları değiştirirseniz, bu üye işlevini çağırmak gerekli değildir.

Her kullanıcının ayırıcı penceresi yeniden boyutlandırır veya bir bölme taşır framework bu üye işlevini çağırır.

### <a name="example"></a>Örnek

  Örneğin bakın [CSplitterWnd::SetColumnInfo](#setcolumninfo).

##  <a name="setactivepane"></a>  CSplitterWnd::SetActivePane

Çerçevede etkin olmasını bölmesi ayarlar.

```
virtual void SetActivePane(
    int row,
    int col,
    CWnd* pWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*Satır*<br/>
Varsa *pWnd* null, etkin olan bölmesinde satırı belirtir.

*sütun*<br/>
Varsa *pWnd* null, etkin olan bölmesinde sütun belirtir.

*pWnd*<br/>
Bir işaretçi bir `CWnd` nesne. NULL ise, bölmesinde belirtilen *satır* ve *sütun* etkin olarak ayarlanır. BOŞ değilse, etkin olarak bölmesinde belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, kullanıcı bir bölmeye çerçeve penceresi içinde odağı değiştiğinde bir bölme etkin olarak ayarlamak için framework tarafından çağırılır. Açıkça çağırabilirsiniz `SetActivePane` odağı belirtilen görünümünü değiştirmek için.

Ya da satır ve sütun sağlayarak bölmesinde belirtin **veya** sağlayarak *pWnd*.

##  <a name="setcolumninfo"></a>  CSplitterWnd::SetColumnInfo

Belirtilen sütun bilgisi ayarlamak için çağrılır.

```
void SetColumnInfo(
    int col,
    int cxIdeal,
    int cxMin);
```

### <a name="parameters"></a>Parametreler

*sütun*<br/>
Bölümlendirici pencere sütunu belirtir.

*cxIdeal*<br/>
Bölümlendirici pencere sütun için ideal bir genişlik piksel cinsinden belirtir.

*cxMin*<br/>
Bölümlendirici pencere sütun için en az bir genişlik piksel cinsinden belirtir.

### <a name="remarks"></a>Açıklamalar

Bir yeni en düşük genişlik ve ideal bir sütun genişliğini ayarlamak için bu üye işlevini çağırın. Sütun en düşük değer sütunun ne zaman tam olarak görüntülenecek küçük olacağını belirler.

Framework ayırıcı penceresi görüntülendiğinde, sütunları ve satırları göre bölme pencerenin istemci alanının sağ alt köşedeki için sol üst köşesinden çalışma kendi ideal boyutlarını bölmelerinde kullanıma yerleştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#6](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]

##  <a name="setrowinfo"></a>  CSplitterWnd::SetRowInfo

Belirtilen satır ayarlamak için çağrılır.

```
void SetRowInfo(
    int row,
    int cyIdeal,
    int cyMin);
```

### <a name="parameters"></a>Parametreler

*Satır*<br/>
Ayırıcı penceresi satır belirtir.

*cyIdeal*<br/>
İdeal bir ayırıcı penceresi satır yüksekliğini piksel cinsinden belirtir.

*cyMin*<br/>
Ayırıcı penceresi satır için bir minimum yükseklik piksel cinsinden belirtir.

### <a name="remarks"></a>Açıklamalar

Bir yeni en az yükseklik ve bir satır için ideal yüksekliği ayarlamak için bu üye işlevini çağırın. Satır en düşük değeri satır ne zaman tam olarak görüntülenecek küçük olacağını belirler.

Framework ayırıcı penceresi görüntülendiğinde, sütunları ve satırları göre bölme pencerenin istemci alanının sağ alt köşedeki için sol üst köşesinden çalışma kendi ideal boyutlarını bölmelerinde kullanıma yerleştirir.

##  <a name="setscrollstyle"></a>  CSplitterWnd::SetScrollStyle

Paylaşılan kaydırma çubuğu desteği bölme pencerenin yeni kaydırma stilini belirtir.

```
void SetScrollStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Bölme pencerenin yeni kaydırma stilini paylaşılan kaydırma çubuğu desteği bulunan ve yeniden aşağıdaki değerlerden biri olabilir:

- WS_HSCROLL paylaşılan yatay kaydırma çubuklarını Oluştur/göster.

- WS_VSCROLL Oluştur/Göster paylaşılan dikey kaydırma çubukları.

### <a name="remarks"></a>Açıklamalar

Bir kaydırma çubuğu oluşturulduktan sonra yok edileceği bile `SetScrollStyle` o stilin; adlı bunun yerine bu kaydırma çubukları gizli. Bu, gizli olsa da, bunların durumunu korumak kaydırma çubukları sağlar. Arama sonra `SetScrollStyle` çağırmak için gereken [RecalcLayout](#recalclayout) tüm değişikliklerin etkili olması.

##  <a name="splitcolumn"></a>  CSplitterWnd::SplitColumn

Bir çerçeve penceresinin dikey olarak bölündüğünü belirtir.

```
virtual BOOL SplitColumn(int cxBefore);
```

### <a name="parameters"></a>Parametreler

*cxBefore*<br/>
Piksel cinsinden bölme önce oluştuğu konumu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi bir yatay bölme penceresi oluşturulduğunda çağırılır. `SplitColumn` bölünmenin gerçekleştiği varsayılan konumu gösterir.

`SplitColumn` (diğer bir deyişle, ayırıcı penceresi SPLS_DYNAMIC_SPLIT stili yoksa) mantığı dinamik Bölümlendirici penceresinin uygulamak için framework tarafından çağırılır. Bu, sanal işlev birlikte özelleştirilebilir [CreateView](#createview), daha gelişmiş dinamik ayırıcılar uygulamak için.

##  <a name="splitrow"></a>  CSplitterWnd::SplitRow

Bir çerçeve penceresinin yatay olarak bölündüğünü belirtir.

```
virtual BOOL SplitRow(int cyBefore);
```

### <a name="parameters"></a>Parametreler

*cyBefore*<br/>
Piksel cinsinden bölme önce oluştuğu konumu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi bir Yatay bölümlendirici pencere oluşturulduğunda çağırılır. `SplitRow` bölünmenin gerçekleştiği varsayılan konumu gösterir.

`SplitRow` (diğer bir deyişle, ayırıcı penceresi SPLS_DYNAMIC_SPLIT stili yoksa) mantığı dinamik Bölümlendirici penceresinin uygulamak için framework tarafından çağırılır. Bu, sanal işlev birlikte özelleştirilebilir [CreateView](#createview), daha gelişmiş dinamik ayırıcılar uygulamak için.

##  <a name="ondraw"></a>  CSplitterWnd::OnDraw

Ayırıcı penceresi çizmek için framework tarafından çağırılır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Bir cihaz bağlamı için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek VIEWEX](../../visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)
