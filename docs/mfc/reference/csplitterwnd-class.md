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
ms.openlocfilehash: 065735c13a3e763208142eb6bc989d3a496221f0
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78890960"
---
# <a name="csplitterwnd-class"></a>CSplitterWnd sınıfı

Birden çok bölme içeren bir pencere olan Bölümlendirici pencerenin işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CSplitterWnd : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSplitterWnd:: CSplitterWnd](#csplitterwnd)|`CSplitterWnd` nesnesi oluşturmak için çağırın.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSplitterWnd:: ActivateNext](#activatenext)|Sonraki bölmeyi veya önceki bölme komutunu uygular.|
|[CSplitterWnd:: CanActivateNext](#canactivatenext)|Sonraki bölme veya önceki bölme komutunun mümkün olup olmadığını denetler.|
|[CSplitterWnd:: Create](#create)|Dinamik Bölümlendirici penceresi oluşturma ve `CSplitterWnd` nesnesine iliştirme çağrısı.|
|[CSplitterWnd:: CreateScrollBarCtrl](#createscrollbarctrl)|Paylaşılan bir kaydırma çubuğu denetimi oluşturur.|
|[CSplitterWnd:: CreateStatic](#createstatic)|Statik Bölümlendirici penceresi oluşturma ve `CSplitterWnd` nesnesine iliştirme çağrısı.|
|[CSplitterWnd:: CreateView](#createview)|Bölümlendirici penceresinde bölme oluşturma çağrısı.|
|[CSplitterWnd::D eleteColumn](#deletecolumn)|Ayırıcı penceresinden bir sütun siler.|
|[CSplitterWnd::D eleteRow](#deleterow)|Ayırıcı penceresinden bir satır siler.|
|[CSplitterWnd::D eleteView](#deleteview)|Ayırıcı penceresinden bir görünüm siler.|
|[CSplitterWnd::D oKeyboardSplit](#dokeyboardsplit)|Klavye bölme komutunu, genellikle "pencere Böl" gerçekleştirir.|
|[CSplitterWnd::D oScroll](#doscroll)|Bölünmüş pencerelerin eşitlenmiş kaydırmasını gerçekleştirir.|
|[CSplitterWnd::D oScrollBy](#doscrollby)|Bölünmüş pencereleri verilen sayıda pikselle kaydırır.|
|[CSplitterWnd:: GetActivePane](#getactivepane)|Çerçevedeki odağın veya etkin görünümden etkin bölmeyi belirler.|
|[CSplitterWnd:: GetColumnCount](#getcolumncount)|Geçerli bölme sütun sayısını döndürür.|
|[CSplitterWnd:: GetColumnInfo](#getcolumninfo)|Belirtilen sütundaki bilgileri döndürür.|
|[CSplitterWnd:: GetPane](#getpane)|Belirtilen satır ve sütundaki bölmeyi döndürür.|
|[CSplitterWnd:: GetRowCount](#getrowcount)|Geçerli bölme satırı sayısını döndürür.|
|[CSplitterWnd:: Getrowinınfo](#getrowinfo)|Belirtilen satırdaki bilgileri döndürür.|
|[CSplitterWnd:: GetScrollStyle](#getscrollstyle)|Paylaşılan kaydırma çubuğu stilini döndürür.|
|[CSplitterWnd:: ıdfromrowcol](#idfromrowcol)|Belirtilen satırda ve sütunda bölmenin alt pencere KIMLIĞINI döndürür.|
|[CSplitterWnd:: ıschildpane](#ischildpane)|Pencerenin Şu anda bu splitter penceresinin alt bölmesi olup olmadığını belirleme çağrısı.|
|[CSplitterWnd:: IsTracking](#istracking)|Ayırıcı çubuğun Şu anda taşınıp taşınmadığını belirler.|
|[CSplitterWnd:: RecalcLayout](#recalclayout)|Satır veya sütun boyutunu ayarladıktan sonra ayırıcı penceresini yeniden görüntülemek için çağırın.|
|[CSplitterWnd:: SetActivePane](#setactivepane)|Çerçevede etkin bir bölme olacak şekilde ayarlar.|
|[CSplitterWnd:: SetColumnInfo](#setcolumninfo)|Belirtilen sütun bilgilerini ayarlamak için çağırın.|
|[CSplitterWnd:: SetRowInfo](#setrowinfo)|Belirtilen satır bilgilerini ayarlamak için çağırın.|
|[CSplitterWnd:: SetScrollStyle](#setscrollstyle)|Ayırıcı pencerenin paylaşılan kaydırma çubuğu desteği için yeni kaydırma çubuğu stilini belirtir.|
|[CSplitterWnd:: SplitColumn](#splitcolumn)|Bir çerçeve penceresinin dikey olarak bölündüğünü gösterir.|
|[CSplitterWnd:: Sptrow](#splitrow)|Bir çerçeve penceresinin yatay olarak bölündüğünü gösterir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSplitterWnd:: OnDraw](#ondraw)|Ayırıcı penceresini çizmek için Framework tarafından çağırılır.|
|[CSplitterWnd:: OnDrawSplitter](#ondrawsplitter)|Bölünmüş pencerenin bir görüntüsünü oluşturur.|
|[CSplitterWnd:: Onınevirttracker](#oninverttracker)|Bölünmüş pencerenin görüntüsünü, çerçeve penceresiyle aynı boyut ve şekle sahip olacak şekilde işler.|

## <a name="remarks"></a>Açıklamalar

Bir bölme genellikle [CView](../../mfc/reference/cview-class.md)'dan türetilmiş uygulamaya özel bir nesnedir, ancak uygun alt pencere kimliğine sahip herhangi bir [CWnd](../../mfc/reference/cwnd-class.md) nesnesi olabilir.

`CSplitterWnd` nesnesi genellikle üst bir [CFrameWnd](../../mfc/reference/cframewnd-class.md) veya [Cmdictepdwnd](../../mfc/reference/cmdichildwnd-class.md) nesnesine katıştırılır. Aşağıdaki adımları kullanarak bir `CSplitterWnd` nesnesi oluşturun:

1. Ana çerçeveye bir `CSplitterWnd` üye değişkeni ekleyin.

2. Üst çerçevenin [CFrameWnd:: OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) üye işlevini geçersiz kılın.

3. Geçersiz kılınan `OnCreateClient`içinden `CSplitterWnd`[Create](#create) veya [CreateStatic](#createstatic) üye işlevini çağırın.

Dinamik bir Splitter penceresi oluşturmak için `Create` member işlevini çağırın. Bir dinamik ayırıcı pencere, genellikle aynı belgenin bir dizi bölmeyi veya görünümünü oluşturmak ve kaydırmak için kullanılır. Çerçeve, Bölümlendirici için otomatik olarak bir başlangıç bölmesi oluşturur; daha sonra, Kullanıcı ayırıcı penceresinin denetimlerini yaptığı için çerçeve ek bölmeler oluşturur, yeniden boyutlandırır ve atar.

`Create`çağırdığınızda, bölmelerin tam olarak ne zaman küçük gösterileceğini belirleyen bir minimum satır yüksekliği ve sütun genişliği belirtirsiniz. `Create`çağırdıktan sonra, [SetColumnInfo](#setcolumninfo) ve [Setrowinfo](#setrowinfo) üye işlevlerini çağırarak bu en düşük düzeyde UMS ayarlayabilirsiniz.

Ayrıca, bir sütun için "ideal" bir genişlik ve bir satır için "ideal" yüksekliğini ayarlamak için `SetColumnInfo` ve `SetRowInfo` üye işlevlerini kullanın. Çerçeve bir ayırıcı pencere görüntülediğinde, önce üst kareyi, sonra ayırıcı penceresini görüntüler. Daha sonra çerçeve, sütun ve satırlardaki bölmeleri, ayırıcı pencerenin istemci alanının sağ alt köşesine doğru olan en sol üst köşesinden çalışarak, en iyi boyutlarına göre sütunlar ve satırlar halinde yerleştirir.

Dinamik Bölümlendirici penceresindeki tüm bölmeler aynı sınıfta olmalıdır. Dinamik Bölümlendirici pencerelerini destekleyen tanıdık uygulamalar Microsoft Word ve Microsoft Excel içerir.

Statik Bölümlendirici penceresi oluşturmak için `CreateStatic` member işlevini kullanın. Kullanıcı yalnızca bir statik Bölümlendirici penceresindeki bölmelerin boyutunu veya sıralarını değil, yalnızca bölmeleri değiştirebilir.

Statik bölücüyü oluştururken tüm statik Bölümlendirici bölmelerini özel olarak oluşturmanız gerekir. Üst çerçevenin `OnCreateClient` üye işlevi döndürülmadan önce tüm bölmeleri oluşturun veya Framework pencereyi doğru bir şekilde görüntülemediğinizden emin olun.

`CreateStatic` member işlevi, minimum satır yüksekliği ve sütun genişliği 0 olan statik bir ayırıcıyı otomatik olarak başlatır. `Create`çağırdıktan sonra, [SetColumnInfo](#setcolumninfo) ve [Setrowinfo](#setrowinfo) üye işlevlerini çağırarak bu en az UMS ayarlayın. Ayrıca, istenen ideal bölme boyutlarını göstermek için `CreateStatic` çağırdıktan sonra `SetColumnInfo` ve `SetRowInfo` kullanın.

Statik ayırıcının tek tek bölmeleri genellikle farklı sınıflara aittir. Statik Bölümlendirici pencereler örnekleri için bkz. grafik Düzenleyicisi ve Windows Dosya Yöneticisi.

Ayırıcı pencere, özel kaydırma çubuklarını destekler (Bu, bölmelerin sahip olabileceği kaydırma çubuklarından ayrı olarak). Bu kaydırma çubukları `CSplitterWnd` nesnenin alt öğesi ve bölmelerle paylaşılır.

Ayırıcı penceresini oluştururken bu özel kaydırma çubuklarını oluşturursunuz. Örneğin, tek satıra sahip bir `CSplitterWnd`, iki sütun ve WS_VSCROLL stili, iki bölme tarafından paylaşılan dikey bir kaydırma çubuğu görüntüler. Kullanıcı kaydırma çubuğunu taşıdıkça WM_VSCROLL iletiler her iki bölmeye de gönderilir. Bölmeler, kaydırma çubuğu konumunu ayarlandığında paylaşılan kaydırma çubuğu ayarlanır.

Bölünmüş pencereler hakkında daha fazla bilgi için bkz. [teknik notta 29](../../mfc/tn029-splitter-windows.md).

Dinamik Bölümlendirici pencereleri oluşturma hakkında daha fazla bilgi için bkz.:

- MFC örnek [karalama](../../overview/visual-cpp-samples.md)

- MFC örnek [Viewex](../../overview/visual-cpp-samples.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSplitterWnd`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext. h

##  <a name="activatenext"></a>CSplitterWnd:: ActivateNext

Bir sonraki bölmeyi veya önceki bölme komutunu gerçekleştirmek için Framework tarafından çağırılır.

```
virtual void ActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>Parametreler

*bÖnceki*<br/>
Hangi pencerenin etkinleşdiğini gösterir. Previous için **true** ; İleri için **false** .

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, `CSplitterWnd` uygulamasına temsilci seçmek için [CView](../../mfc/reference/cview-class.md) sınıfı tarafından kullanılan yüksek düzeyli bir komuttur.

##  <a name="canactivatenext"></a>CSplitterWnd:: CanActivateNext

Sonraki bölme veya önceki bölme komutunun mümkün olup olmadığını denetlemek için Framework tarafından çağırılır.

```
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>Parametreler

*bÖnceki*<br/>
Hangi pencerenin etkinleşdiğini gösterir. Previous için **true** ; İleri için **false** .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, `CSplitterWnd` uygulamasına temsilci seçmek için [CView](../../mfc/reference/cview-class.md) sınıfı tarafından kullanılan yüksek düzeyli bir komuttur.

##  <a name="create"></a>CSplitterWnd:: Create

Dinamik bir ayırıcı penceresi oluşturmak için `Create` üye işlevini çağırın.

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
Bölümlendirici penceresindeki en fazla satır sayısı. Bu değer 2 ' den fazla olmamalıdır.

*nMaxCols*<br/>
Bölümlendirici penceresindeki en fazla sütun sayısı. Bu değer 2 ' den fazla olmamalıdır.

*sizeMin*<br/>
Bir bölmenin gösterileceği en küçük boyutu belirtir.

*pContext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısına yönelik bir işaretçi. Çoğu durumda bu, üst çerçeve penceresine geçirilen *pContext* olabilir.

*dwStyle*<br/>
Pencere stilini belirtir.

*NID*<br/>
Pencerenin alt pencere KIMLIĞI. Ayırıcı pencere başka bir ayırıcı penceresinin içinde iç içe olmadığı takdirde KIMLIK AFX_IDW_PANE_FIRST olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki adımları gerçekleştirerek bir `CSplitterWnd` üst [CFrameWnd](../../mfc/reference/cframewnd-class.md) veya [Cmdicchild dwnd](../../mfc/reference/cmdichildwnd-class.md) nesnesine ekleyebilirsiniz:

1. Ana çerçeveye bir `CSplitterWnd` üye değişkeni ekleyin.

1. Üst çerçevenin [CFrameWnd:: OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) üye işlevini geçersiz kılın.

1. Geçersiz kılınan `OnCreateClient`içinden `Create` member işlevini çağırın.

Üst çerçevenin içinden bir ayırıcı penceresi oluşturduğunuzda, üst çerçevenin *pContext* parametresini Bölümlendirici penceresine geçirin. Aksi takdirde, bu parametre NULL olabilir.

Dinamik Bölümlendirici penceresinin başlangıçtaki en küçük satır yüksekliği ve sütun genişliği *sizeMin* parametresine göre ayarlanır. Bir bölmenin tamamen gösterilemeyecek kadar küçük olup olmadığını belirleyen bu minimum değer, [Setrowinfo](#setrowinfo) ve [SetColumnInfo](#setcolumninfo) üye işlevleriyle değiştirilebilir.

Dinamik Bölümlendirici pencereleri hakkında daha fazla bilgi için bkz. [birden çok belge türü, görünümler ve çerçeve pencereleri](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik notun 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfına genel bakış makalesindeki "Splitter pencereleri".

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]

##  <a name="createscrollbarctrl"></a>CSplitterWnd:: CreateScrollBarCtrl

Paylaşılan bir kaydırma çubuğu denetimi oluşturmak için Framework tarafından çağırılır.

```
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Pencere stilini belirtir.

*NID*<br/>
Pencerenin alt pencere KIMLIĞI. Ayırıcı pencere başka bir ayırıcı penceresinin içinde iç içe olmadığı takdirde KIMLIK AFX_IDW_PANE_FIRST olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir kaydırma çubuğunun yanına daha fazla denetim eklemek için `CreateScrollBarCtrl` geçersiz kılın. Varsayılan davranış, normal Windows kaydırma çubuğu denetimleri oluşturmaktır.

##  <a name="createstatic"></a>CSplitterWnd:: CreateStatic

Statik Bölümlendirici penceresi oluşturmak için `CreateStatic` üye işlevini çağırın.

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

*nsatırlar*<br/>
Sıra sayısı. Bu değer 16 ' yı aşmamalıdır.

*nCols*<br/>
Sütun sayısı. Bu değer 16 ' yı aşmamalıdır.

*dwStyle*<br/>
Pencere stilini belirtir.

*NID*<br/>
Pencerenin alt pencere KIMLIĞI. Ayırıcı pencere başka bir ayırıcı penceresinin içinde iç içe olmadığı takdirde KIMLIK AFX_IDW_PANE_FIRST olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CSplitterWnd`, genellikle aşağıdaki adımları uygulayarak bir üst `CFrameWnd` veya [Cmdictepdwnd](../../mfc/reference/cmdichildwnd-class.md) nesnesine katıştırılır:

1. Ana çerçeveye bir `CSplitterWnd` üye değişkeni ekleyin.

1. Üst çerçevenin `OnCreateClient` üye işlevini geçersiz kılın.

1. Geçersiz kılınan [CFrameWnd:: OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)içinden `CreateStatic` member işlevini çağırın.

Statik Bölümlendirici penceresi, genellikle farklı sınıflardan sabit sayıda bölme içerir.

Bir statik Bölümlendirici penceresi oluşturduğunuzda, tüm bölmelerini de aynı zamanda oluşturmanız gerekir. [CreateView](#createview) üye işlevi genellikle bu amaçla kullanılır, ancak başka bir görünüm olmayan sınıflar da oluşturabilirsiniz.

Statik Bölümlendirici penceresi için başlangıçtaki en küçük satır yüksekliği ve sütun genişliği 0 ' dır. Bu minimum değer, bir bölmenin tamamen gösterilemeyecek kadar küçük olduğunu belirleyen, [Setrowinfo](#setrowinfo) ve [SetColumnInfo](#setcolumninfo) üye işlevleriyle değiştirilebilir.

Bir statik ayırıcı penceresine kaydırma çubukları eklemek için, WS_HSCROLL ve WS_VSCROLL stilleri *dwStyle*'a ekleyin.

Statik Bölümlendirici pencereleri hakkında daha fazla bilgi için, bkz. [birden çok belge türü, görünüm ve çerçeve penceresi](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik notun 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfına genel bakış.

##  <a name="createview"></a>CSplitterWnd:: CreateView

Bir statik ayırıcı pencere için bölmeleri oluşturur.

```
virtual BOOL CreateView(
    int row,
    int col,
    CRuntimeClass* pViewClass,
    SIZE sizeInit,
    CCreateContext* pContext);
```

### <a name="parameters"></a>Parametreler

*sırada*<br/>
Yeni görünümün yerleştirileceği ayırıcı pencere satırını belirtir.

*sütun*<br/>
Yeni görünümün yerleştirileceği ayırıcı pencere sütununu belirtir.

*pViewClass*<br/>
Yeni görünümün [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) öğesini belirtir.

*sizeInit*<br/>
Yeni görünümün başlangıç boyutunu belirtir.

*pContext*<br/>
Görünümü oluşturmak için kullanılan oluşturma bağlamına yönelik bir işaretçi (genellikle üst *çerçeveye geçirilen geçersiz* kılınan [CFrameWnd:: OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) üye işlevine ayırıcı pencerenin oluşturulduğu).

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çerçeve ayırıcıyı görüntülemeden önce statik Bölümlendirici penceresinin tüm bölmeleri oluşturulmalıdır.

Çerçeve ayrıca bir dinamik ayırıcı penceresinin kullanıcısı bir bölmeyi, satırı veya sütunu böldüğünü yeni bölmeler oluşturmak için bu üye işlevini çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#4](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]

##  <a name="csplitterwnd"></a>CSplitterWnd:: CSplitterWnd

`CSplitterWnd` nesnesi oluşturmak için çağırın.

```
CSplitterWnd();
```

### <a name="remarks"></a>Açıklamalar

İki adımda `CSplitterWnd` nesnesi oluşturun. İlk olarak, `CSplitterWnd` nesnesini oluşturan oluşturucuyu çağırın ve ardından Bölümlendirici penceresini oluşturan ve `CSplitterWnd` nesnesine ekleyen üye [Oluştur](#create) işlevini çağırın.

##  <a name="deletecolumn"></a>CSplitterWnd::D eleteColumn

Ayırıcı penceresinden bir sütun siler.

```
virtual void DeleteColumn(int colDelete);
```

### <a name="parameters"></a>Parametreler

*colDelete*<br/>
Silinecek sütunu belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, dinamik ayırıcı penceresinin mantığını (ayırıcı pencere SPLS_DYNAMIC_SPLIT stiline sahipse) uygulamak için çerçeve tarafından çağırılır. Daha gelişmiş dinamik bölümlendiricileri uygulamak için, [CreateView](#createview)sanal işleviyle birlikte özelleştirilebilir.

##  <a name="deleterow"></a>CSplitterWnd::D eleteRow

Ayırıcı penceresinden bir satır siler.

```
virtual void DeleteRow(int rowDelete);
```

### <a name="parameters"></a>Parametreler

*rowDelete*<br/>
Silinecek satırı belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, dinamik ayırıcı penceresinin mantığını (ayırıcı pencere SPLS_DYNAMIC_SPLIT stiline sahipse) uygulamak için çerçeve tarafından çağırılır. Daha gelişmiş dinamik bölümlendiricileri uygulamak için, [CreateView](#createview)sanal işleviyle birlikte özelleştirilebilir.

##  <a name="deleteview"></a>CSplitterWnd::D eleteView

Ayırıcı penceresinden bir görünüm siler.

```
virtual void DeleteView(
    int row,
    int col);
```

### <a name="parameters"></a>Parametreler

*sırada*<br/>
Görünümün silineceği ayırıcı pencere satırını belirtir.

*sütun*<br/>
Görünümün silineceği ayırıcı pencere sütununu belirtir.

### <a name="remarks"></a>Açıklamalar

Etkin görünüm siliniyorsa, sonraki görünüm etkin olur. Varsayılan uygulama, görünümün [PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy)'da otomatik olarak silineceğini varsayar.

Bu üye işlevi, dinamik ayırıcı penceresinin mantığını (ayırıcı pencere SPLS_DYNAMIC_SPLIT stiline sahipse) uygulamak için çerçeve tarafından çağırılır. Daha gelişmiş dinamik bölümlendiricileri uygulamak için, [CreateView](#createview)sanal işleviyle birlikte özelleştirilebilir.

##  <a name="dokeyboardsplit"></a>CSplitterWnd::D oKeyboardSplit

Klavye bölme komutunu, genellikle "pencere Böl" gerçekleştirir.

```
virtual BOOL DoKeyboardSplit();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, `CSplitterWnd` uygulamasına temsilci seçmek için [CView](../../mfc/reference/cview-class.md) sınıfı tarafından kullanılan yüksek düzeyli bir komuttur.

##  <a name="doscroll"></a>CSplitterWnd::D oScroll

Bölünmüş pencerelerin eşitlenmiş kaydırmasını gerçekleştirir.

```
virtual BOOL DoScroll(
    CView* pViewFrom,
    UINT nScrollCode,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parametreler

*pViewFrom*<br/>
Kaydırılan iletinin kaynaklandığı görünüme yönelik bir işaretçi.

*nScrollCode*<br/>
Kullanıcının kaydırma isteğini gösteren bir kaydırma çubuğu kodu. Bu parametre iki bölümden oluşur: yatay olarak oluşan kaydırma türünü belirleyen düşük sıralı bir bayt ve dikey olarak oluşan kaydırma türünü belirleyen yüksek sıralı bir bayt.

    - SB_BOTTOM en alta kayar.

    - SB_LINEDOWN bir satır aşağı kaydırır.

    - SB_LINEUP bir satır yukarı kaydırır.

    - SB_PAGEDOWN bir sayfa aşağı kaydırır.

    - SB_PAGEUP bir sayfa yukarı kaydırır.

    - SB_TOP üste kayar.

*bDoScroll*<br/>
Belirtilen kaydırma eyleminin oluşup oluşmadığını belirler. *BDoScroll* true ise (yani, bir alt pencere varsa ve bölünmüş pencerelerin bir kaydırma aralığı varsa), belirtilen kaydırma eylemi gerçekleştirilebilir; *bDoScroll* false ise (yani, alt pencere yoksa veya bölünmüş görünümlerin hiçbir kaydırma aralığı yoksa), kaydırma gerçekleşmez.

### <a name="return-value"></a>Dönüş Değeri

Eşitlenmiş kaydırma oluşursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, görünüm bir kaydırma iletisi aldığında bölünmüş pencerelerin eşitlenmiş kaydırmasını gerçekleştirmek için çerçevesi tarafından çağırılır. Eşitlenmiş kaydırmaya izin verilmediğinden Kullanıcı tarafından bir eylem gerektirecek şekilde geçersiz kılın.

##  <a name="doscrollby"></a>CSplitterWnd::D oScrollBy

Bölünmüş pencereleri verilen sayıda pikselle kaydırır.

```
virtual BOOL DoScrollBy(
    CView* pViewFrom,
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parametreler

*pViewFrom*<br/>
Kaydırılan iletinin kaynaklandığı görünüme yönelik bir işaretçi.

*sizeScroll*<br/>
Yatay ve dikey olarak kaydırılacağı piksel sayısı.

*bDoScroll*<br/>
Belirtilen kaydırma eyleminin oluşup oluşmadığını belirler. *BDoScroll* true ise (yani, bir alt pencere varsa ve bölünmüş pencerelerin bir kaydırma aralığı varsa), belirtilen kaydırma eylemi gerçekleştirilebilir; *bDoScroll* false ise (yani, alt pencere yoksa veya bölünmüş görünümlerin hiçbir kaydırma aralığı yoksa), kaydırma gerçekleşmez.

### <a name="return-value"></a>Dönüş Değeri

Eşitlenmiş kaydırma oluşursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, bir kaydırma iletisine yanıt olarak çerçeve tarafından, bölünmüş pencerelerin, *sizeScroll*tarafından belirtilen piksel cinsinden miktarı eşitlenmiş şekilde kaymasını gerçekleştirecek şekilde çağrılır. Pozitif değerler aşağı kaydırmayı ve sağa doğru gösterir; negatif değerler yukarı ve sola kaydırma gösterir.

Kaydırmaya izin vermeden önce Kullanıcı tarafından bir eylem gerektirecek şekilde geçersiz kılın.

##  <a name="getactivepane"></a>CSplitterWnd:: GetActivePane

Çerçevedeki odağın veya etkin görünümden etkin bölmeyi belirler.

```
virtual CWnd* GetActivePane(
    int* pRow = NULL,
    int* pCol = NULL);
```

### <a name="parameters"></a>Parametreler

*pRow*<br/>
Etkin bölmenin satır numarasını almak için bir **int** işaretçisi.

*pCol*<br/>
Etkin bölmenin sütun numarasını almak için bir **int** işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Etkin bölmeye yönelik işaretçi. Etkin bir bölme bulunmuyorsa NULL.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, bir bölücü penceresinde etkin bölmeyi belirlemede, Framework tarafından çağırılır. Etkin bölmeyi almadan önce Kullanıcı tarafından bir eylem gerektirecek şekilde geçersiz kılın.

##  <a name="getcolumncount"></a>CSplitterWnd:: GetColumnCount

Geçerli bölme sütun sayısını döndürür.

```
int GetColumnCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölümlendirici içindeki geçerli sütun sayısını döndürür. Statik Bölümlendirici için, en fazla sütun sayısı da bu olacaktır.

##  <a name="getcolumninfo"></a>CSplitterWnd:: GetColumnInfo

Belirtilen sütundaki bilgileri döndürür.

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
Sütunun geçerli genişliğine ayarlanacak bir **int** başvurusu.

*cxMin*<br/>
Sütunun geçerli en küçük genişliğine ayarlanacak bir **int** başvurusu.

##  <a name="getpane"></a>CSplitterWnd:: GetPane

Belirtilen satır ve sütundaki bölmeyi döndürür.

```
CWnd* GetPane(
    int row,
    int col) const;
```

### <a name="parameters"></a>Parametreler

*sırada*<br/>
Bir satırı belirtir.

*sütun*<br/>
Bir sütunu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen satır ve sütundaki bölmeyi döndürür. Döndürülen bölme genellikle bir [CView](../../mfc/reference/cview-class.md)ile türetilmiş sınıftır.

##  <a name="getrowcount"></a>CSplitterWnd:: GetRowCount

Geçerli bölme satırı sayısını döndürür.

```
int GetRowCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayırıcı penceresindeki geçerli satır sayısını döndürür. Statik Bölümlendirici penceresinde bu, en fazla satır sayısı olarak da olacaktır.

##  <a name="getrowinfo"></a>CSplitterWnd:: Getrowinınfo

Belirtilen satırdaki bilgileri döndürür.

```
void GetRowInfo(
    int row,
    int& cyCur,
    int& cyMin) const;
```

### <a name="parameters"></a>Parametreler

*sırada*<br/>
Bir satırı belirtir.

*Bu*<br/>
Satırın piksel cinsinden geçerli yüksekliğine ayarlanması için **tamsayı** başvurusu.

*Cydk*<br/>
Satırın piksel cinsinden geçerli minimum yüksekliğine ayarlanması için **tamsayı** başvurusu.

### <a name="remarks"></a>Açıklamalar

Belirtilen satır hakkında bilgi edinmek için bu üye işlevi çağırın. *Cyur* parametresi, belirtilen satırın geçerli yüksekliğiyle doldurulmuştur ve *cyMin* değeri satırın en küçük yüksekliğiyle doldurulur.

##  <a name="getscrollstyle"></a>CSplitterWnd:: GetScrollStyle

Ayırıcı pencerenin paylaşılan kaydırma çubuğu stilini döndürür.

```
DWORD GetScrollStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, aşağıdaki Windows stil bayraklarından bir veya daha fazlası:

    - Ayırıcı şu anda paylaşılan yatay kaydırma çubuklarını yönetirse WS_HSCROLL.

    - Ayırıcı şu anda paylaşılan dikey kaydırma çubuklarını yönetirse WS_VSCROLL.

Sıfır ise, ayırıcı pencere şu anda herhangi bir paylaşılan kaydırma çubuğunu yönetmez.

##  <a name="idfromrowcol"></a>CSplitterWnd:: ıdfromrowcol

Bölme için alt pencere KIMLIĞINI belirtilen satırda ve sütunda alır.

```
int IdFromRowCol(
    int row,
    int col) const;
```

### <a name="parameters"></a>Parametreler

*sırada*<br/>
Ayırıcı pencere satırını belirtir.

*sütun*<br/>
Ayırıcı pencere sütununu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bölmenin alt pencere KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, görünüm olmayan görünümler oluşturmak için kullanılır ve bölme mevcut olmadan önce çağrılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#5](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]

##  <a name="ischildpane"></a>CSplitterWnd:: ıschildpane

*PWnd* 'in Şu anda bu splitter penceresinin alt bölmesi olup olmadığını belirler.

```
BOOL IsChildPane(
    CWnd* pWnd,
    int* pRow,
    int* pCol);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Sınanacak [CWnd](../../mfc/reference/cwnd-class.md) nesnesine yönelik bir işaretçi.

*pRow*<br/>
Satır numarasının kaydedileceği bir **int** işaretçisi.

*pCol*<br/>
Sütun numarasının depolandığı bir **int** için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfır değilse, *pWnd* Şu anda bu ayırıcı pencerenin bir alt bölmesi ve *Prow* ve *pCol* , bölme penceresindeki bölmenin konumuyla doldurulmuştur. *PWnd* bu splitter penceresinin alt bölmesi değilse, 0 döndürülür.

### <a name="remarks"></a>Açıklamalar

6,0 ' C++ dan önceki Visual sürümlerinde bu işlev şu şekilde tanımlanmıştır

`BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`

Bu sürüm artık kullanılmıyor ve kullanılmamalıdır.

##  <a name="istracking"></a>CSplitterWnd:: IsTracking

Penceredeki Bölümlendirici çubuğunun Şu anda taşınıp taşınmadığını öğrenmek için bu üye işlevi çağırın.

```
BOOL IsTracking();
```

### <a name="return-value"></a>Dönüş Değeri

Bir Splitter işlemi devam ediyorsa sıfır dışı; Aksi takdirde 0.

##  <a name="ondrawsplitter"></a>CSplitterWnd:: OnDrawSplitter

Bölünmüş pencerenin bir görüntüsünü oluşturur.

```
virtual void OnDrawSplitter(
    CDC* pDC,
    ESplitType nType,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
İçinde çizilecek cihaz bağlamına yönelik bir işaretçi. *PDC* null Ise, [CWnd:: RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) Framework tarafından çağrılır ve bölünmüş pencere çizilmez.

*nTür*<br/>
`enum ESplitType`bir değeri, aşağıdakilerden biri olabilir:

    - Bölümlendirici sürükleme kutusunu `splitBox`.

    - iki bölünmüş pencere arasında görünen çubuğu `splitBar`.

    - bölünmüş pencerelerin kesişimini `splitIntersection`. Bu öğe, Windows 95/98 üzerinde çalışırken çağrılmayacak.

    - Bölünmüş pencere kenarlıklarını `splitBorder`.

*Rect*<br/>
Bölünmüş pencerelerin boyutunu ve şeklini belirten bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, bir splitter penceresinin tam özelliklerini çizmek ve belirtmek için Framework tarafından çağırılır. Bir ayırıcı penceresinin çeşitli grafik bileşenleri için canlandırın 'nin gelişmiş özelleştirmesi için `OnDrawSplitter` geçersiz kılın. Varsayılan görüntü, Splitter çubuklarının Kesişimleriyle birlikte karıştırılmasının yanı sıra Windows veya Microsoft Windows 95/98 için Microsoft 'a yönelik bölümlendiricine benzer.

Dinamik Bölümlendirici pencereleri hakkında daha fazla bilgi için bkz. [birden çok belge türü, görünümler ve çerçeve pencereleri](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik notun 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfına genel bakış makalesindeki "Splitter pencereleri".

##  <a name="oninverttracker"></a>CSplitterWnd:: Onınevirttracker

Bölünmüş pencerenin görüntüsünü, çerçeve penceresiyle aynı boyut ve şekle sahip olacak şekilde işler.

```
virtual void OnInvertTracker(const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
İzleme dikdörtgenini belirten `CRect` nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, bölümlendiricileri yeniden boyutlandırılırken Framework tarafından çağırılır. Ayırıcı penceresinin Imagery öğesinin gelişmiş özelleştirmesi için `OnInvertTracker` geçersiz kılın. Varsayılan görüntü, Splitter çubuklarının Kesişimleriyle birlikte karıştırılmasının yanı sıra Windows veya Microsoft Windows 95/98 için Microsoft 'a yönelik bölümlendiricine benzer.

Dinamik Bölümlendirici pencereleri hakkında daha fazla bilgi için bkz. [birden çok belge türü, görünümler ve çerçeve pencereleri](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik notun 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfına genel bakış makalesindeki "Splitter pencereleri".

##  <a name="recalclayout"></a>CSplitterWnd:: RecalcLayout

Satır veya sütun boyutunu ayarladıktan sonra ayırıcı penceresini yeniden görüntülemek için çağırın.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Açıklamalar

Satır ve sütun boyutlarını [Setrowinfo](#setrowinfo) ve [SetColumnInfo](#setcolumninfo) üye işlevleriyle ayarladıktan sonra Bölümlendirici penceresini doğru şekilde yeniden görüntülemek için bu üye işlevi çağırın. Ayırıcı penceresi görünür olmadan önce, satır ve sütun boyutlarını oluşturma işleminin parçası olarak değiştirirseniz, bu üye işlevi çağırmak gerekli değildir.

Çerçeve, ayırıcı pencereyi yeniden boyutlandırdığında veya bir bölmeyi taşırken bu üye işlevini çağırır.

### <a name="example"></a>Örnek

  [CSplitterWnd:: SetColumnInfo](#setcolumninfo)örneğine bakın.

##  <a name="setactivepane"></a>CSplitterWnd:: SetActivePane

Çerçevede etkin bir bölme olacak şekilde ayarlar.

```
virtual void SetActivePane(
    int row,
    int col,
    CWnd* pWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*sırada*<br/>
*PWnd* null ise, bölmedeki etkin olacak satırı belirtir.

*sütun*<br/>
*PWnd* null ise, bölmedeki etkin olacak sütunu belirtir.

*pWnd*<br/>
`CWnd` nesnesine yönelik bir işaretçi. NULL ise, *satır* ve *sütun* tarafından belirtilen bölme etkin ayarlanır. NULL değilse, etkin olarak ayarlanan bölmeyi belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Kullanıcı odağı çerçeve penceresi içindeki bir bölmeye değiştirdiğinde, bir bölmeyi etkin olarak ayarlamak için çerçeve tarafından çağrılır. Odağı belirtilen görünüme değiştirmek için `SetActivePane` açıkça çağırabilirsiniz.

Bir satır ve sütun belirterek **ya** da *pWnd*sağlayarak bölmeyi belirtin.

##  <a name="setcolumninfo"></a>CSplitterWnd:: SetColumnInfo

Belirtilen sütun bilgilerini ayarlamak için çağırın.

```
void SetColumnInfo(
    int col,
    int cxIdeal,
    int cxMin);
```

### <a name="parameters"></a>Parametreler

*sütun*<br/>
Ayırıcı pencere sütununu belirtir.

*cxIdeal*<br/>
Ayırıcı pencere sütunu için piksel cinsinden ideal bir genişlik belirtir.

*cxMin*<br/>
Ayırıcı pencere sütunu için piksel cinsinden minimum genişliği belirtir.

### <a name="remarks"></a>Açıklamalar

Bir sütun için yeni bir en düşük genişlik ve ideal genişlik ayarlamak için bu üye işlevi çağırın. Sütun en küçük değeri, sütunun tam olarak görüntülenmek için ne zaman küçük olacağını belirler.

Çerçeve Bölümlendirici penceresini görüntülediğinde, bölme penceresinin istemci alanının sağ alt köşesine doğru çalışarak, sütun ve satırlardaki bölmeleri ideal boyutlara göre yerleştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#6](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]

##  <a name="setrowinfo"></a>CSplitterWnd:: SetRowInfo

Belirtilen satır bilgilerini ayarlamak için çağırın.

```
void SetRowInfo(
    int row,
    int cyIdeal,
    int cyMin);
```

### <a name="parameters"></a>Parametreler

*sırada*<br/>
Ayırıcı pencere satırını belirtir.

*cyIdeal*<br/>
Ayırıcı pencere satırı için piksel cinsinden ideal bir yükseklik belirtir.

*Cydk*<br/>
Ayırıcı pencere satırı için piksel cinsinden minimum yüksekliği belirtir.

### <a name="remarks"></a>Açıklamalar

Bir satır için yeni bir minimum yükseklik ve ideal yükseklik ayarlamak için bu üye işlevini çağırın. Satır en küçük değeri, satırın tam olarak görüntülenemeyecek kadar küçük olacağını belirler.

Çerçeve Bölümlendirici penceresini görüntülediğinde, bölme penceresinin istemci alanının sağ alt köşesine doğru çalışarak, sütun ve satırlardaki bölmeleri ideal boyutlara göre yerleştirir.

##  <a name="setscrollstyle"></a>CSplitterWnd:: SetScrollStyle

Ayırıcı pencerenin paylaşılan kaydırma çubuğu desteği için yeni kaydırma stilini belirtir.

```
void SetScrollStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Ayırıcı pencerenin paylaşılan kaydırma çubuğu desteği için aşağıdaki değerlerden biri olabilecek yeni kaydırma stili:

- WS_HSCROLL yatay paylaşılan kaydırma çubuklarını oluşturun/görüntüleyin.

- WS_VSCROLL dikey paylaşılan kaydırma çubuklarını oluşturun/gösterin.

### <a name="remarks"></a>Açıklamalar

Bir kaydırma çubuğu oluşturulduktan sonra, `SetScrollStyle` bu stil olmadan çağrılsa bile yok edilmez; Bunun yerine, bu kaydırma çubukları gizlenir. Bu, kaydırma çubuklarının gizli olsalar bile durumlarını korumasını sağlar. `SetScrollStyle` çağrıldıktan sonra tüm değişikliklerin etkili olması için [RecalcLayout](#recalclayout) çağrısı yapmanız gerekir.

##  <a name="splitcolumn"></a>CSplitterWnd:: SplitColumn

Bir çerçeve penceresinin dikey olarak bölündüğünü gösterir.

```
virtual BOOL SplitColumn(int cxBefore);
```

### <a name="parameters"></a>Parametreler

*cxBefore*<br/>
Bölme işleminin gerçekleştiği konum (piksel cinsinden).

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi dikey bir ayırıcı pencere oluşturulduğunda çağrılır. `SplitColumn`, bölme işleminin gerçekleştiği varsayılan konumu gösterir.

`SplitColumn`, çerçeve tarafından dinamik ayırıcı penceresinin mantığını uygulamak için çağrılır (ayırıcı pencerenin SPLS_DYNAMIC_SPLIT stili varsa). Daha gelişmiş dinamik bölümlendiricileri uygulamak için, [CreateView](#createview)sanal işleviyle birlikte özelleştirilebilir.

##  <a name="splitrow"></a>CSplitterWnd:: Sptrow

Bir çerçeve penceresinin yatay olarak bölündüğünü gösterir.

```
virtual BOOL SplitRow(int cyBefore);
```

### <a name="parameters"></a>Parametreler

*cyBefore*<br/>
Bölme işleminin gerçekleştiği konum (piksel cinsinden).

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, yatay bir ayırıcı pencere oluşturulduğunda çağrılır. `SplitRow`, bölme işleminin gerçekleştiği varsayılan konumu gösterir.

`SplitRow`, çerçeve tarafından dinamik ayırıcı penceresinin mantığını uygulamak için çağrılır (ayırıcı pencerenin SPLS_DYNAMIC_SPLIT stili varsa). Daha gelişmiş dinamik bölümlendiricileri uygulamak için, [CreateView](#createview)sanal işleviyle birlikte özelleştirilebilir.

##  <a name="ondraw"></a>CSplitterWnd:: OnDraw

Ayırıcı penceresini çizmek için Framework tarafından çağırılır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Cihaz bağlamına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)
