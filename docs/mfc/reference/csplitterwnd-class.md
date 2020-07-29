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
ms.openlocfilehash: 0f6d940ca123483f381231e6d34d98eebe101bf7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212390"
---
# <a name="csplitterwnd-class"></a>CSplitterWnd sınıfı

Birden çok bölme içeren bir pencere olan Bölümlendirici pencerenin işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CSplitterWnd : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSplitterWnd:: CSplitterWnd](#csplitterwnd)|Bir nesne oluşturmak için çağırın `CSplitterWnd` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSplitterWnd:: ActivateNext](#activatenext)|Sonraki bölmeyi veya önceki bölme komutunu uygular.|
|[CSplitterWnd:: CanActivateNext](#canactivatenext)|Sonraki bölme veya önceki bölme komutunun mümkün olup olmadığını denetler.|
|[CSplitterWnd:: Create](#create)|Dinamik Bölümlendirici penceresi oluşturma ve nesneye iliştirme çağrısı `CSplitterWnd` .|
|[CSplitterWnd:: CreateScrollBarCtrl](#createscrollbarctrl)|Paylaşılan bir kaydırma çubuğu denetimi oluşturur.|
|[CSplitterWnd:: CreateStatic](#createstatic)|Statik Bölümlendirici penceresi oluşturma ve nesneye iliştirme çağrısı `CSplitterWnd` .|
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

|Ad|Açıklama|
|----------|-----------------|
|[CSplitterWnd:: OnDraw](#ondraw)|Ayırıcı penceresini çizmek için Framework tarafından çağırılır.|
|[CSplitterWnd:: OnDrawSplitter](#ondrawsplitter)|Bölünmüş pencerenin bir görüntüsünü oluşturur.|
|[CSplitterWnd:: Onınevirttracker](#oninverttracker)|Bölünmüş pencerenin görüntüsünü, çerçeve penceresiyle aynı boyut ve şekle sahip olacak şekilde işler.|

## <a name="remarks"></a>Açıklamalar

Bir bölme genellikle [CView](../../mfc/reference/cview-class.md)'dan türetilmiş uygulamaya özel bir nesnedir, ancak uygun alt pencere kimliğine sahip herhangi bir [CWnd](../../mfc/reference/cwnd-class.md) nesnesi olabilir.

Bir `CSplitterWnd` nesne genellikle üst bir [CFrameWnd](../../mfc/reference/cframewnd-class.md) veya [Cmdictepdwnd](../../mfc/reference/cmdichildwnd-class.md) nesnesine katıştırılır. `CSplitterWnd`Aşağıdaki adımları kullanarak bir nesne oluşturun:

1. `CSplitterWnd`Ana çerçeveye bir üye değişkeni ekleyin.

2. Üst çerçevenin [CFrameWnd:: OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) üye işlevini geçersiz kılın.

3. Geçersiz kılınan içinden `OnCreateClient` [Create](#create) veya [CreateStatic](#createstatic) üye işlevini çağırın `CSplitterWnd` .

`Create`Dinamik bir ayırıcı penceresi oluşturmak için üye işlevini çağırın. Bir dinamik ayırıcı pencere, genellikle aynı belgenin bir dizi bölmeyi veya görünümünü oluşturmak ve kaydırmak için kullanılır. Çerçeve, Bölümlendirici için otomatik olarak bir başlangıç bölmesi oluşturur; daha sonra, Kullanıcı ayırıcı penceresinin denetimlerini yaptığı için çerçeve ek bölmeler oluşturur, yeniden boyutlandırır ve atar.

`Create`' İ çağırdığınızda, bölmelerin tam olarak ne zaman küçük gösterileceğini belirleyen bir minimum satır yüksekliği ve sütun genişliği belirtirsiniz. Öğesini çağırdıktan sonra `Create` , [SetColumnInfo](#setcolumninfo) ve [setrowinfo](#setrowinfo) üye işlevlerini çağırarak bu minimum değeri ayarlayabilirsiniz.

Ayrıca, `SetColumnInfo` `SetRowInfo` bir sütun için "ideal" bir genişlik ve bir satır için "ideal" yüksekliğini ayarlamak için ve üye işlevlerini kullanın. Çerçeve bir ayırıcı pencere görüntülediğinde, önce üst kareyi, sonra ayırıcı penceresini görüntüler. Daha sonra çerçeve, sütun ve satırlardaki bölmeleri, ayırıcı pencerenin istemci alanının sağ alt köşesine doğru olan en sol üst köşesinden çalışarak, en iyi boyutlarına göre sütunlar ve satırlar halinde yerleştirir.

Dinamik Bölümlendirici penceresindeki tüm bölmeler aynı sınıfta olmalıdır. Dinamik Bölümlendirici pencerelerini destekleyen tanıdık uygulamalar Microsoft Word ve Microsoft Excel içerir.

`CreateStatic`Statik Bölümlendirici penceresi oluşturmak için üye işlevini kullanın. Kullanıcı yalnızca bir statik Bölümlendirici penceresindeki bölmelerin boyutunu veya sıralarını değil, yalnızca bölmeleri değiştirebilir.

Statik bölücüyü oluştururken tüm statik Bölümlendirici bölmelerini özel olarak oluşturmanız gerekir. Üst çerçevenin üye işlevi döndürülmadan önce tüm bölmeleri oluştururken `OnCreateClient` veya çerçeve pencereyi doğru bir şekilde görüntülemediğinizden emin olun.

`CreateStatic`Üye işlevi, minimum satır yüksekliği ve sütun genişliği 0 olan statik bir ayırıcıyı otomatik olarak başlatır. Öğesini çağırdıktan sonra `Create` , [SetColumnInfo](#setcolumninfo) ve [setrowinfo](#setrowinfo) üye işlevlerini çağırarak bu en az UMS ayarlayın. Ayrıca `SetColumnInfo` , `SetRowInfo` `CreateStatic` istenen ideal bölme boyutlarını göstermek için öğesini çağırdıktan sonra ve öğesini kullanın.

Statik ayırıcının tek tek bölmeleri genellikle farklı sınıflara aittir. Statik Bölümlendirici pencereler örnekleri için bkz. grafik Düzenleyicisi ve Windows Dosya Yöneticisi.

Ayırıcı pencere, özel kaydırma çubuklarını destekler (Bu, bölmelerin sahip olabileceği kaydırma çubuklarından ayrı olarak). Bu kaydırma çubukları nesnenin alt öğesi `CSplitterWnd` ve bölmelerle paylaşılır.

Ayırıcı penceresini oluştururken bu özel kaydırma çubuklarını oluşturursunuz. Örneğin, bir `CSplitterWnd` satır, iki sütun ve ws_vscroll stil, iki bölme tarafından paylaşılan dikey bir kaydırma çubuğu görüntüler. Kullanıcı kaydırma çubuğunu taşıdıkça WM_VSCROLL iletiler her iki bölmeye de gönderilir. Bölmeler, kaydırma çubuğu konumunu ayarlandığında paylaşılan kaydırma çubuğu ayarlanır.

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

## <a name="csplitterwndactivatenext"></a><a name="activatenext"></a>CSplitterWnd:: ActivateNext

Bir sonraki bölmeyi veya önceki bölme komutunu gerçekleştirmek için Framework tarafından çağırılır.

```
virtual void ActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>Parametreler

*bÖnceki*<br/>
Hangi pencerenin etkinleşdiğini gösterir. Previous için **true** ; İleri için **false** .

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, [CView](../../mfc/reference/cview-class.md) sınıfı tarafından uygulamaya temsilci seçmek için kullanılan yüksek düzeyli bir komuttur `CSplitterWnd` .

## <a name="csplitterwndcanactivatenext"></a><a name="canactivatenext"></a>CSplitterWnd:: CanActivateNext

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

Bu üye işlevi, [CView](../../mfc/reference/cview-class.md) sınıfı tarafından uygulamaya temsilci seçmek için kullanılan yüksek düzeyli bir komuttur `CSplitterWnd` .

## <a name="csplitterwndcreate"></a><a name="create"></a>CSplitterWnd:: Create

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

`CSplitterWnd`Aşağıdaki adımları gerçekleştirerek bir üst [CFrameWnd](../../mfc/reference/cframewnd-class.md) veya [Cmdictepdwnd](../../mfc/reference/cmdichildwnd-class.md) nesnesine bir ekleyebilirsiniz:

1. `CSplitterWnd`Ana çerçeveye bir üye değişkeni ekleyin.

1. Üst çerçevenin [CFrameWnd:: OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) üye işlevini geçersiz kılın.

1. `Create`Geçersiz kılınan içinden üye işlevini çağırın `OnCreateClient` .

Üst çerçevenin içinden bir ayırıcı penceresi oluşturduğunuzda, üst çerçevenin *pContext* parametresini Bölümlendirici penceresine geçirin. Aksi takdirde, bu parametre NULL olabilir.

Dinamik Bölümlendirici penceresinin başlangıçtaki en küçük satır yüksekliği ve sütun genişliği *sizeMin* parametresine göre ayarlanır. Bir bölmenin tamamen gösterilemeyecek kadar küçük olup olmadığını belirleyen bu minimum değer, [Setrowinfo](#setrowinfo) ve [SetColumnInfo](#setcolumninfo) üye işlevleriyle değiştirilebilir.

Dinamik Bölümlendirici pencereleri hakkında daha fazla bilgi için bkz. [birden çok belge türü, görünüm ve çerçeve penceresi](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik notun 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfa genel bakış.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]

## <a name="csplitterwndcreatescrollbarctrl"></a><a name="createscrollbarctrl"></a>CSplitterWnd:: CreateScrollBarCtrl

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

`CreateScrollBarCtrl`Bir kaydırma çubuğunun yanına ek denetimler dahil etmek için geçersiz kılın. Varsayılan davranış, normal Windows kaydırma çubuğu denetimleri oluşturmaktır.

## <a name="csplitterwndcreatestatic"></a><a name="createstatic"></a>CSplitterWnd:: CreateStatic

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

Bir `CSplitterWnd` , genellikle aşağıdaki adımları uygulayarak bir üst `CFrameWnd` veya [Cmdictepdwnd](../../mfc/reference/cmdichildwnd-class.md) nesnesine katıştırılır:

1. `CSplitterWnd`Ana çerçeveye bir üye değişkeni ekleyin.

1. Üst çerçevenin `OnCreateClient` üye işlevini geçersiz kılın.

1. `CreateStatic`Geçersiz kılınan [CFrameWnd:: OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)içinden üye işlevini çağırın.

Statik Bölümlendirici penceresi, genellikle farklı sınıflardan sabit sayıda bölme içerir.

Bir statik Bölümlendirici penceresi oluşturduğunuzda, tüm bölmelerini de aynı zamanda oluşturmanız gerekir. [CreateView](#createview) üye işlevi genellikle bu amaçla kullanılır, ancak başka bir görünüm olmayan sınıflar da oluşturabilirsiniz.

Statik Bölümlendirici penceresi için başlangıçtaki en küçük satır yüksekliği ve sütun genişliği 0 ' dır. Bu minimum değer, bir bölmenin tamamen gösterilemeyecek kadar küçük olduğunu belirleyen, [Setrowinfo](#setrowinfo) ve [SetColumnInfo](#setcolumninfo) üye işlevleriyle değiştirilebilir.

Bir statik ayırıcı penceresine kaydırma çubukları eklemek için, WS_HSCROLL ve WS_VSCROLL stilleri *dwStyle*'a ekleyin.

Statik Bölümlendirici pencereleri hakkında daha fazla bilgi için bkz. [birden çok belge türü, görünüm ve çerçeve penceresi](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik notun 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfa genel bakış.

## <a name="csplitterwndcreateview"></a><a name="createview"></a>CSplitterWnd:: CreateView

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

## <a name="csplitterwndcsplitterwnd"></a><a name="csplitterwnd"></a>CSplitterWnd:: CSplitterWnd

Bir nesne oluşturmak için çağırın `CSplitterWnd` .

```
CSplitterWnd();
```

### <a name="remarks"></a>Açıklamalar

`CSplitterWnd`İki adımda bir nesne oluşturun. İlk olarak, nesnesini oluşturan oluşturucuyu çağırın `CSplitterWnd` ve ardından Bölümlendirici penceresini oluşturan ve nesneyi bağlayan üye [Oluştur](#create) işlevini çağırın `CSplitterWnd` .

## <a name="csplitterwnddeletecolumn"></a><a name="deletecolumn"></a>CSplitterWnd::D eleteColumn

Ayırıcı penceresinden bir sütun siler.

```
virtual void DeleteColumn(int colDelete);
```

### <a name="parameters"></a>Parametreler

*colDelete*<br/>
Silinecek sütunu belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, dinamik ayırıcı penceresinin mantığını (ayırıcı pencere SPLS_DYNAMIC_SPLIT stiline sahipse) uygulamak için çerçeve tarafından çağırılır. Daha gelişmiş dinamik bölümlendiricileri uygulamak için, [CreateView](#createview)sanal işleviyle birlikte özelleştirilebilir.

## <a name="csplitterwnddeleterow"></a><a name="deleterow"></a>CSplitterWnd::D eleteRow

Ayırıcı penceresinden bir satır siler.

```
virtual void DeleteRow(int rowDelete);
```

### <a name="parameters"></a>Parametreler

*rowDelete*<br/>
Silinecek satırı belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, dinamik ayırıcı penceresinin mantığını (ayırıcı pencere SPLS_DYNAMIC_SPLIT stiline sahipse) uygulamak için çerçeve tarafından çağırılır. Daha gelişmiş dinamik bölümlendiricileri uygulamak için, [CreateView](#createview)sanal işleviyle birlikte özelleştirilebilir.

## <a name="csplitterwnddeleteview"></a><a name="deleteview"></a>CSplitterWnd::D eleteView

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

## <a name="csplitterwnddokeyboardsplit"></a><a name="dokeyboardsplit"></a>CSplitterWnd::D oKeyboardSplit

Klavye bölme komutunu, genellikle "pencere Böl" gerçekleştirir.

```
virtual BOOL DoKeyboardSplit();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, [CView](../../mfc/reference/cview-class.md) sınıfı tarafından uygulamaya temsilci seçmek için kullanılan yüksek düzeyli bir komuttur `CSplitterWnd` .

## <a name="csplitterwnddoscroll"></a><a name="doscroll"></a>CSplitterWnd::D oScroll

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

## <a name="csplitterwnddoscrollby"></a><a name="doscrollby"></a>CSplitterWnd::D oScrollBy

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

## <a name="csplitterwndgetactivepane"></a><a name="getactivepane"></a>CSplitterWnd:: GetActivePane

Çerçevedeki odağın veya etkin görünümden etkin bölmeyi belirler.

```
virtual CWnd* GetActivePane(
    int* pRow = NULL,
    int* pCol = NULL);
```

### <a name="parameters"></a>Parametreler

*pRow*<br/>
**`int`** Etkin bölmenin satır numarasını almak için bir işaretçisi.

*pCol*<br/>
**`int`** Etkin bölmenin sütun numarasını almak için bir işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Etkin bölmeye yönelik işaretçi. Etkin bir bölme bulunmuyorsa NULL.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, bir bölücü penceresinde etkin bölmeyi belirlemede, Framework tarafından çağırılır. Etkin bölmeyi almadan önce Kullanıcı tarafından bir eylem gerektirecek şekilde geçersiz kılın.

## <a name="csplitterwndgetcolumncount"></a><a name="getcolumncount"></a>CSplitterWnd:: GetColumnCount

Geçerli bölme sütun sayısını döndürür.

```
int GetColumnCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölümlendirici içindeki geçerli sütun sayısını döndürür. Statik Bölümlendirici için, en fazla sütun sayısı da bu olacaktır.

## <a name="csplitterwndgetcolumninfo"></a><a name="getcolumninfo"></a>CSplitterWnd:: GetColumnInfo

Belirtilen sütundaki bilgileri döndürür.

```cpp
void GetColumnInfo(
    int col,
    int& cxCur,
    int& cxMin) const;
```

### <a name="parameters"></a>Parametreler

*sütun*<br/>
Bir sütunu belirtir.

*cxCur*<br/>
**`int`** Sütununun geçerli genişliğine ayarlanacak bir başvurusu.

*cxMin*<br/>
**`int`** Sütununun geçerli en küçük genişliğine ayarlanacak bir başvuru.

## <a name="csplitterwndgetpane"></a><a name="getpane"></a>CSplitterWnd:: GetPane

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

## <a name="csplitterwndgetrowcount"></a><a name="getrowcount"></a>CSplitterWnd:: GetRowCount

Geçerli bölme satırı sayısını döndürür.

```
int GetRowCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayırıcı penceresindeki geçerli satır sayısını döndürür. Statik Bölümlendirici penceresinde bu, en fazla satır sayısı olarak da olacaktır.

## <a name="csplitterwndgetrowinfo"></a><a name="getrowinfo"></a>CSplitterWnd:: Getrowinınfo

Belirtilen satırdaki bilgileri döndürür.

```cpp
void GetRowInfo(
    int row,
    int& cyCur,
    int& cyMin) const;
```

### <a name="parameters"></a>Parametreler

*sırada*<br/>
Bir satırı belirtir.

*Bu*<br/>
**`int`** Satırın geçerli yükseklik olarak piksel cinsinden ayarlanması için başvuru.

*Cydk*<br/>
**`int`** Satırın piksel cinsinden geçerli en küçük yüksekliği olarak ayarlanması için başvuru.

### <a name="remarks"></a>Açıklamalar

Belirtilen satır hakkında bilgi edinmek için bu üye işlevi çağırın. *Cyur* parametresi, belirtilen satırın geçerli yüksekliğiyle doldurulmuştur ve *cyMin* değeri satırın en küçük yüksekliğiyle doldurulur.

## <a name="csplitterwndgetscrollstyle"></a><a name="getscrollstyle"></a>CSplitterWnd:: GetScrollStyle

Ayırıcı pencerenin paylaşılan kaydırma çubuğu stilini döndürür.

```
DWORD GetScrollStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, aşağıdaki Windows stil bayraklarından bir veya daha fazlası:

- Ayırıcı şu anda paylaşılan yatay kaydırma çubuklarını yönetirse WS_HSCROLL.

- Ayırıcı şu anda paylaşılan dikey kaydırma çubuklarını yönetirse WS_VSCROLL.

Sıfır ise, ayırıcı pencere şu anda herhangi bir paylaşılan kaydırma çubuğunu yönetmez.

## <a name="csplitterwndidfromrowcol"></a><a name="idfromrowcol"></a>CSplitterWnd:: ıdfromrowcol

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

## <a name="csplitterwndischildpane"></a><a name="ischildpane"></a>CSplitterWnd:: ıschildpane

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
Satır numarasının kaydedileceği bir işaretçisi **`int`** .

*pCol*<br/>
Bir **`int`** sütun numarasının depolandığı bir işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Sıfır değilse, *pWnd* Şu anda bu ayırıcı pencerenin bir alt bölmesi ve *Prow* ve *pCol* , bölme penceresindeki bölmenin konumuyla doldurulmuştur. *PWnd* bu splitter penceresinin alt bölmesi değilse, 0 döndürülür.

### <a name="remarks"></a>Açıklamalar

6,0 ' den önceki Visual C++ sürümlerde, bu işlev şu şekilde tanımlanmıştır

`BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`

Bu sürüm artık kullanılmıyor ve kullanılmamalıdır.

## <a name="csplitterwndistracking"></a><a name="istracking"></a>CSplitterWnd:: IsTracking

Penceredeki Bölümlendirici çubuğunun Şu anda taşınıp taşınmadığını öğrenmek için bu üye işlevi çağırın.

```
BOOL IsTracking();
```

### <a name="return-value"></a>Dönüş Değeri

Bir Splitter işlemi devam ediyorsa sıfır dışı; Aksi takdirde 0.

## <a name="csplitterwndondrawsplitter"></a><a name="ondrawsplitter"></a>CSplitterWnd:: OnDrawSplitter

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
Öğesinin bir değeri `enum ESplitType` , aşağıdakilerden biri olabilir:

- `splitBox`Bölümlendirici sürükleme kutusu.

- `splitBar`İki bölünmüş pencere arasında görünen çubuk.

- `splitIntersection`Bölünmüş pencerelerin kesişimi. Bu öğe, Windows 95/98 üzerinde çalışırken çağrılmayacak.

- `splitBorder`Bölünmüş Pencere kenarlıkları.

*Rect*<br/>
Bölünmüş pencerelerin boyutunu ve şeklini belirten bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, bir splitter penceresinin tam özelliklerini çizmek ve belirtmek için Framework tarafından çağırılır. `OnDrawSplitter`Bir splitter penceresinin çeşitli grafik bileşenleri için canlandırın 'nin gelişmiş özelleştirmesi için geçersiz kılın. Varsayılan görüntü, Splitter çubuklarının Kesişimleriyle birlikte karıştırılmasının yanı sıra Windows veya Microsoft Windows 95/98 için Microsoft 'a yönelik bölümlendiricine benzer.

Dinamik Bölümlendirici pencereleri hakkında daha fazla bilgi için bkz. [birden çok belge türü, görünüm ve çerçeve penceresi](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik notun 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfa genel bakış.

## <a name="csplitterwndoninverttracker"></a><a name="oninverttracker"></a>CSplitterWnd:: Onınevirttracker

Bölünmüş pencerenin görüntüsünü, çerçeve penceresiyle aynı boyut ve şekle sahip olacak şekilde işler.

```
virtual void OnInvertTracker(const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
`CRect`İzleme dikdörtgenini belirten bir nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, bölümlendiricileri yeniden boyutlandırılırken Framework tarafından çağırılır. `OnInvertTracker`Ayırıcı penceresinin Imagery öğesinin gelişmiş özelleştirmesi için geçersiz kılın. Varsayılan görüntü, Splitter çubuklarının Kesişimleriyle birlikte karıştırılmasının yanı sıra Windows veya Microsoft Windows 95/98 için Microsoft 'a yönelik bölümlendiricine benzer.

Dinamik Bölümlendirici pencereleri hakkında daha fazla bilgi için bkz. [birden çok belge türü, görünüm ve çerçeve penceresi](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik notun 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfa genel bakış.

## <a name="csplitterwndrecalclayout"></a><a name="recalclayout"></a>CSplitterWnd:: RecalcLayout

Satır veya sütun boyutunu ayarladıktan sonra ayırıcı penceresini yeniden görüntülemek için çağırın.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Açıklamalar

Satır ve sütun boyutlarını [Setrowinfo](#setrowinfo) ve [SetColumnInfo](#setcolumninfo) üye işlevleriyle ayarladıktan sonra Bölümlendirici penceresini doğru şekilde yeniden görüntülemek için bu üye işlevi çağırın. Ayırıcı penceresi görünür olmadan önce, satır ve sütun boyutlarını oluşturma işleminin parçası olarak değiştirirseniz, bu üye işlevi çağırmak gerekli değildir.

Çerçeve, ayırıcı pencereyi yeniden boyutlandırdığında veya bir bölmeyi taşırken bu üye işlevini çağırır.

### <a name="example"></a>Örnek

  [CSplitterWnd:: SetColumnInfo](#setcolumninfo)örneğine bakın.

## <a name="csplitterwndsetactivepane"></a><a name="setactivepane"></a>CSplitterWnd:: SetActivePane

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
Bir `CWnd` nesne işaretçisi. NULL ise, *satır* ve *sütun* tarafından belirtilen bölme etkin ayarlanır. NULL değilse, etkin olarak ayarlanan bölmeyi belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Kullanıcı odağı çerçeve penceresi içindeki bir bölmeye değiştirdiğinde, bir bölmeyi etkin olarak ayarlamak için çerçeve tarafından çağrılır. `SetActivePane`Odağı belirtilen görünüme dönüştürmek için açıkça çağrı yapabilirsiniz.

Bir satır ve sütun belirterek **ya** da *pWnd*sağlayarak bölmeyi belirtin.

## <a name="csplitterwndsetcolumninfo"></a><a name="setcolumninfo"></a>CSplitterWnd:: SetColumnInfo

Belirtilen sütun bilgilerini ayarlamak için çağırın.

```cpp
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

## <a name="csplitterwndsetrowinfo"></a><a name="setrowinfo"></a>CSplitterWnd:: SetRowInfo

Belirtilen satır bilgilerini ayarlamak için çağırın.

```cpp
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

## <a name="csplitterwndsetscrollstyle"></a><a name="setscrollstyle"></a>CSplitterWnd:: SetScrollStyle

Ayırıcı pencerenin paylaşılan kaydırma çubuğu desteği için yeni kaydırma stilini belirtir.

```cpp
void SetScrollStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Ayırıcı pencerenin paylaşılan kaydırma çubuğu desteği için aşağıdaki değerlerden biri olabilecek yeni kaydırma stili:

- WS_HSCROLL yatay paylaşılan kaydırma çubuklarını oluşturun/görüntüleyin.

- WS_VSCROLL dikey paylaşılan kaydırma çubuklarını oluşturun/gösterin.

### <a name="remarks"></a>Açıklamalar

Bir kaydırma çubuğu oluşturulduktan sonra, bu `SetScrollStyle` Stil olmadan çağrılsa bile yok edilir; bunun yerine bu kaydırma çubukları gizlenir. Bu, kaydırma çubuklarının gizli olsalar bile durumlarını korumasını sağlar. Çağrıldıktan sonra `SetScrollStyle` tüm değişikliklerin etkili olması Için [RecalcLayout](#recalclayout) çağrısı yapmanız gerekir.

## <a name="csplitterwndsplitcolumn"></a><a name="splitcolumn"></a>CSplitterWnd:: SplitColumn

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

Bu üye işlevi dikey bir ayırıcı pencere oluşturulduğunda çağrılır. `SplitColumn`bölme işleminin gerçekleştiği varsayılan konumu gösterir.

`SplitColumn`, dinamik ayırıcı penceresinin mantığını (ayırıcı pencere SPLS_DYNAMIC_SPLIT stile sahipse) uygulamak için Framework tarafından çağırılır. Daha gelişmiş dinamik bölümlendiricileri uygulamak için, [CreateView](#createview)sanal işleviyle birlikte özelleştirilebilir.

## <a name="csplitterwndsplitrow"></a><a name="splitrow"></a>CSplitterWnd:: Sptrow

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

Bu üye işlevi, yatay bir ayırıcı pencere oluşturulduğunda çağrılır. `SplitRow`bölme işleminin gerçekleştiği varsayılan konumu gösterir.

`SplitRow`, dinamik ayırıcı penceresinin mantığını (ayırıcı pencere SPLS_DYNAMIC_SPLIT stile sahipse) uygulamak için Framework tarafından çağırılır. Daha gelişmiş dinamik bölümlendiricileri uygulamak için, [CreateView](#createview)sanal işleviyle birlikte özelleştirilebilir.

## <a name="csplitterwndondraw"></a><a name="ondraw"></a>CSplitterWnd:: OnDraw

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
[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CView sınıfı](../../mfc/reference/cview-class.md)<br/>
[CWnd sınıfı](../../mfc/reference/cwnd-class.md)
