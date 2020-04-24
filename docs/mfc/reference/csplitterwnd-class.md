---
title: CSplitterWnd Sınıfı
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
ms.openlocfilehash: a872854af1695b8b2b347b21d73165d259b3a986
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753068"
---
# <a name="csplitterwnd-class"></a>CSplitterWnd Sınıfı

Birden çok bölme içeren bir pencere olan bir ayırıcı pencerenin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CSplitterWnd : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSplitterWnd::CSplitterWnd](#csplitterwnd)|Bir `CSplitterWnd` nesne oluşturmak için arayın.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSplitterWnd::ActivateNext](#activatenext)|Sonraki Bölme veya Önceki Bölme komutunu gerçekleştirir.|
|[CSplitterWnd::CanActivateNext](#canactivatenext)|Sonraki Bölme veya Önceki Bölme komutu şu anda mümkün olup olmadığını denetler.|
|[CSplitterWnd::Oluştur](#create)|Dinamik bir ayırıcı penceresi oluşturmak ve `CSplitterWnd` nesneye takmak için arayın.|
|[CSplitterWnd::CreateScrollBarCtrl](#createscrollbarctrl)|Paylaşılan kaydırma çubuğu denetimi oluşturur.|
|[CSplitterWnd::CreateStatic](#createstatic)|Statik bir ayırıcı penceresi oluşturmak ve `CSplitterWnd` nesneye takmak için arayın.|
|[CSplitterWnd::CreateView](#createview)|Bölücü penceresinde bölme oluşturmak için arayın.|
|[CSplitterWnd::DeleteSütun](#deletecolumn)|Bölme penceresinden bir sütunu siler.|
|[CSplitterWnd::DeleteRow](#deleterow)|Ayırıcı penceresinden bir satırı siler.|
|[CSplitterWnd::DeleteView](#deleteview)|Ayırıcı penceresinden bir görünümü siler.|
|[CSplitterWnd::DoKeyboardSplit](#dokeyboardsplit)|Klavye bölme komutunu gerçekleştirir, genellikle "Pencere Bölme" olur.|
|[CSplitterWnd::DoScroll](#doscroll)|Bölünmüş pencerelerin senkronize kaydırma gerçekleştirir.|
|[CSplitterWnd::DoScrollBy](#doscrollby)|Kaydırma, pencereleri belirli bir piksel sayısına böler.|
|[CSplitterWnd::GetActivePane](#getactivepane)|Etkin bölmeyi odaktan veya çerçevedeki etkin görünümden belirler.|
|[CSplitterWnd::GetColumnCount](#getcolumncount)|Geçerli bölme sütun sayısını döndürür.|
|[CSplitterWnd::GetColumnInfo](#getcolumninfo)|Belirtilen sütundaki bilgileri verir.|
|[CSplitterWnd::GetPane](#getpane)|Bölmesi belirtilen satır ve sütunda döndürür.|
|[CSplitterWnd::GetRowCount](#getrowcount)|Geçerli bölme satır sayısını döndürür.|
|[CSplitterWnd::GetRowInfo](#getrowinfo)|Belirtilen satırdaki bilgileri verir.|
|[CSplitterWnd::GetScrollStyle](#getscrollstyle)|Paylaşılan kaydırma çubuğu stilini döndürür.|
|[CSplitterWnd::IdFromRowCol](#idfromrowcol)|Belirtilen satır ve sütunda bölmenin alt pencere kimliğini verir.|
|[CSplitterWnd::IsChildPane](#ischildpane)|Pencerenin şu anda bu ayırıcı pencerenin alt bölmesi olup olmadığını belirlemek için arayın.|
|[CSplitterWnd::IsTracking](#istracking)|Splitter çubuğunun şu anda taşınıp taşınmayanlarını belirler.|
|[CSplitterWnd::RecalcLayout](#recalclayout)|Satır veya sütun boyutunu ayarladıktan sonra ayırıcı penceresini yeniden görüntülemek için arayın.|
|[CSplitterWnd::SetActivePane](#setactivepane)|Çerçevedeki etkin bölmeyi ayarlar.|
|[CSplitterWnd::SetColumnInfo](#setcolumninfo)|Belirtilen sütun bilgilerini ayarlamak için arayın.|
|[CSplitterWnd::SetRowInfo](#setrowinfo)|Belirtilen satır bilgilerini ayarlamak için arayın.|
|[CSplitterWnd::SetScrollStyle](#setscrollstyle)|Bölücü penceresinin paylaşılan kaydırma çubuğu desteği için yeni kaydırma çubuğu stilini belirtir.|
|[CSplitterWnd::SplitSütun](#splitcolumn)|Çerçeve penceresinin dikey olarak nerede bölündüğünü gösterir.|
|[CSplitterWnd::SplitRow](#splitrow)|Çerçeve penceresinin yatay olarak bölündüğü yeri gösterir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSplitterWnd::OnDraw](#ondraw)|Ayırıcı penceresini çizmek için çerçeve tarafından çağrılır.|
|[CSplitterWnd::OnDrawSplitter](#ondrawsplitter)|Bölünmüş bir pencerenin görüntüsünü görüntüler.|
|[CSplitterWnd::OnInvertTracker](#oninverttracker)|Bölünmüş pencerenin görüntüsünü çerçeve penceresiyle aynı boyut ve şekle bölüyor.|

## <a name="remarks"></a>Açıklamalar

Bölme genellikle [CView'dan](../../mfc/reference/cview-class.md)türetilen uygulamaya özgü bir nesnedir, ancak uygun alt pencere kimliğine sahip herhangi bir [CWnd](../../mfc/reference/cwnd-class.md) nesnesi olabilir.

Bir `CSplitterWnd` nesne genellikle bir üst [CFrameWnd](../../mfc/reference/cframewnd-class.md) veya [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) nesnesine katıştırılır. Aşağıdaki `CSplitterWnd` adımları kullanarak bir nesne oluşturun:

1. Üst çerçeveye bir `CSplitterWnd` üye değişken gömün.

2. Üst çerçevenin [CFrameWnd geçersiz kılın::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) üye işlevi.

3. Geçersiz kılınan `OnCreateClient`içinden, Create veya [CreateStatic](#createstatic) `CSplitterWnd`üye işlevini arayın. [Create](#create)

Dinamik `Create` bir ayırıcı penceresi oluşturmak için üye işlevi arayın. Dinamik bir ayırıcı penceresi genellikle aynı belgenin tek tek bölmeleri veya görünümleri bir dizi oluşturmak ve kaydırma kıtır. Çerçeve otomatik olarak ayırıcı için bir başlangıç bölmesi oluşturur; daha sonra, kullanıcı ayırıcı penceresinin denetimlerini çalıştırırken çerçeve ek bölmeleri oluşturur, yeniden boyutlandırır ve bertaraf eder.

Aradığınızda, `Create`bölmelerin tam olarak görüntülenemeyecek kadar küçük olduğunu belirleyen minimum satır yüksekliği ve sütun genişliği belirtirsiniz. Aradıktan `Create`sonra, [SetColumnInfo](#setcolumninfo) ve [SetRowInfo](#setrowinfo) üye işlevlerini arayarak bu minimum ları ayarlayabilirsiniz.

Ayrıca, `SetColumnInfo` bir `SetRowInfo` sütun için "ideal" genişlik ve bir satır için "ideal" yükseklik ayarlamak için ve üye işlevleri kullanın. Çerçeve bir ayırıcı penceresi görüntülediğinde, önce üst çerçeveyi, sonra da ayırıcı pencereyi görüntüler. Çerçeve daha sonra bölmeleri ideal boyutlarına göre sütunlar ve satırlar halinde sıralar halinde, bölücü pencerenin istemci alanının sağ alt köşesinden sol üst köşeye kadar çalışır.

Dinamik bir ayırıcı penceresindeki tüm bölmeler aynı sınıfta olmalıdır. Dinamik ayırıcı pencerelerini destekleyen tanıdık uygulamalar arasında Microsoft Word ve Microsoft Excel yer almaktadır.

Statik `CreateStatic` ayırıcı penceresi oluşturmak için üye işlevi kullanın. Kullanıcı, yalnızca statik ayırıcı penceresindeki bölmelerin boyutunu değiştirebilir, sayılarını veya siparişlerini değil.

Statik ayırıcıyı oluştururken özellikle tüm statik ayırıcı bölmelerini oluşturmanız gerekir. Üst çerçevenin `OnCreateClient` üye işlevi dönmeden önce tüm bölmeleri oluşturduğunuzdan emin olun, yoksa çerçeve pencereyi doğru şekilde görüntülemez.

`CreateStatic` Üye işlev, en az satır yüksekliği ve sütun genişliği 0 olan statik bir ayırıcıyı otomatik olarak başolarak alır. Aradıktan `Create` [sonra, SetColumnInfo](#setcolumninfo) ve [SetRowInfo](#setrowinfo) üye işlevlerini arayarak bu minimumları ayarlayın. Ayrıca `SetColumnInfo` kullanmak `SetRowInfo` ve `CreateStatic` sonra istenilen ideal bölme boyutları belirtmek için arayın.

Statik bir ayırıcının tek tek bölmeleri genellikle farklı sınıflara aittir. Statik ayırıcı pencere örnekleri için grafik düzenleyicisi ve Windows Dosya Yöneticisi'ne bakın.

Ayırıcı penceresi özel kaydırma çubuklarını destekler (bölmelerin sahip olabileceği kaydırma çubukları dışında). Bu kaydırma çubukları nesnenin `CSplitterWnd` alt larıdır ve bölmelerle paylaşılır.

Ayırıcı penceresini oluştururken bu özel kaydırma çubuklarını oluşturursunuz. Örneğin, bir `CSplitterWnd` satır, iki sütun ve WS_VSCROLL stili olan bir iki bölme tarafından paylaşılan dikey kaydırma çubuğu görüntüler. Kullanıcı kaydırma çubuğunu hareket ettirdiğinde, WM_VSCROLL iletileri her iki bölmeye de gönderilir. Bölmeler kaydırma çubuğu konumunu ayarladığında, paylaşılan kaydırma çubuğu ayarlanır.

Splitter pencereleri hakkında daha fazla bilgi için [Teknik Not 29'a](../../mfc/tn029-splitter-windows.md)bakın.

Dinamik ayırıcı pencereleri oluşturma hakkında daha fazla bilgi için bkz:

- MFC örnek [Karalama](../../overview/visual-cpp-samples.md)

- MFC örnek [VIEWEX](../../overview/visual-cpp-samples.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CSplitterWnd`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext.h

## <a name="csplitterwndactivatenext"></a><a name="activatenext"></a>CSplitterWnd::ActivateNext

Sonraki Bölme veya Önceki Bölme komutunu gerçekleştirmek için çerçeve tarafından çağrılır.

```
virtual void ActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>Parametreler

*bPrev*<br/>
Hangi pencerenin etkinleştirilen gösterir. Önceki için **DOĞRU;** Sonraki için **YANLIŞ.**

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, [CView](../../mfc/reference/cview-class.md) sınıfı tarafından uygulamaya temsilci vermek `CSplitterWnd` için kullanılan üst düzey bir komutdur.

## <a name="csplitterwndcanactivatenext"></a><a name="canactivatenext"></a>CSplitterWnd::CanActivateNext

Sonraki Bölme veya Önceki Bölme komutu şu anda mümkün olup olmadığını görmek için kontrol etmek için çerçeve tarafından çağrılır.

```
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>Parametreler

*bPrev*<br/>
Hangi pencerenin etkinleştirilen gösterir. Önceki için **DOĞRU;** Sonraki için **YANLIŞ.**

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, [CView](../../mfc/reference/cview-class.md) sınıfı tarafından uygulamaya temsilci vermek `CSplitterWnd` için kullanılan üst düzey bir komutdur.

## <a name="csplitterwndcreate"></a><a name="create"></a>CSplitterWnd::Oluştur

Dinamik bir ayırıcı penceresi oluşturmak `Create` için üye işlevi arayın.

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
Ayırıcı penceresinin ana çerçeve penceresi.

*nMaxRows*<br/>
Bölücü penceresindeki en fazla satır sayısı. Bu değer 2'yi geçmemelidir.

*nMaxCols*<br/>
Bölücü penceresindeki en fazla sütun sayısı. Bu değer 2'yi geçmemelidir.

*sizeMin*<br/>
Bölmenin görüntülenebileceği minimum boyutu belirtir.

*Pcontext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısıiçin bir işaretçi. Çoğu durumda, bu üst çerçeve penceresine geçirilen *pContext* olabilir.

*Dwstyle*<br/>
Pencere stilini belirtir.

*Nıd*<br/>
Pencerenin alt pencere kimliği. Ayırıcı penceresi başka bir ayırıcı penceresinin içine girmedikçe kimlik AFX_IDW_PANE_FIRST edilebilir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki adımları atarak `CSplitterWnd` bir üst [CFrameWnd](../../mfc/reference/cframewnd-class.md) veya [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) nesnesi gömebilirsiniz:

1. Üst çerçeveye bir `CSplitterWnd` üye değişken gömün.

1. Üst çerçevenin [CFrameWnd geçersiz kılın::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) üye işlevi.

1. `Create` Üye işlevini geçersiz kılından `OnCreateClient`arayın.

Bir üst çerçeve içinden bir ayırıcı penceresi oluşturduğunuzda, üst çerçevenin *pContext* parametresini bölücü penceresine geçirin. Aksi takdirde, bu parametre NULL olabilir.

Dinamik bir ayırıcı penceresinin ilk minimum satır yüksekliği ve sütun genişliği *sizeMin* parametresi tarafından ayarlanır. Bir bölmenin bütünüyle gösterilemeyecek kadar küçük olup olmadığını belirleyen bu minimum lar [SetRowInfo](#setrowinfo) ve [SetColumnInfo](#setcolumninfo) üye işlevleriyle değiştirilebilir.

Dinamik ayırıcı pencereler hakkında daha fazla bilgi için, birden [çok belge türleri, görünümler ve Çerçeve Windows,](../../mfc/multiple-document-types-views-and-frame-windows.md) [Teknik Not 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfa genel bakış makalesinde "Splitter Windows" bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]

## <a name="csplitterwndcreatescrollbarctrl"></a><a name="createscrollbarctrl"></a>CSplitterWnd::CreateScrollBarCtrl

Paylaşılan kaydırma çubuğu denetimi oluşturmak için çerçeve tarafından çağrılır.

```
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Pencere stilini belirtir.

*Nıd*<br/>
Pencerenin alt pencere kimliği. Ayırıcı penceresi başka bir ayırıcı penceresinin içine girmedikçe kimlik AFX_IDW_PANE_FIRST edilebilir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kaydırma `CreateScrollBarCtrl` çubuğunun yanına ek denetimler eklemek için geçersiz kılın. Varsayılan davranış, normal Windows kaydırma çubuğu denetimleri oluşturmaktır.

## <a name="csplitterwndcreatestatic"></a><a name="createstatic"></a>CSplitterWnd::CreateStatic

Statik bir ayırıcı penceresi oluşturmak `CreateStatic` için üye işlevi arayın.

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
Ayırıcı penceresinin ana çerçeve penceresi.

*Nrows*<br/>
Sıra sayısı. Bu değer 16'yı geçmemelidir.

*nCols*<br/>
Sütun sayısı. Bu değer 16'yı geçmemelidir.

*Dwstyle*<br/>
Pencere stilini belirtir.

*Nıd*<br/>
Pencerenin alt pencere kimliği. Ayırıcı penceresi başka bir ayırıcı penceresinin içine girmedikçe kimlik AFX_IDW_PANE_FIRST edilebilir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

A `CSplitterWnd` genellikle aşağıdaki adımları `CFrameWnd` atarak bir üst veya [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) nesnesine katıştırılır:

1. Üst çerçeveye bir `CSplitterWnd` üye değişken gömün.

1. Üst çerçevenin `OnCreateClient` üye işlevini geçersiz kılın.

1. `CreateStatic` Üye işlevini geçersiz kılınan [CFrameWnd içinden arayın::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient).

Statik ayırıcı penceresi, genellikle farklı sınıflardan gelen sabit sayıda bölme içerir.

Statik bir ayırıcı penceresi oluşturduğunuzda, aynı anda tüm bölmelerini oluşturmanız gerekir. [CreateView](#createview) üye işlevi genellikle bu amaç için kullanılır, ancak diğer nonview sınıfları da oluşturabilirsiniz.

Statik ayırıcı penceresi için ilk minimum satır yüksekliği ve sütun genişliği 0'dır. Bir bölmenin tam olarak gösterilemeyecek kadar küçük olduğunu belirleyen bu minimum lar [SetRowInfo](#setrowinfo) ve [SetColumnInfo](#setcolumninfo) üye işlevleriyle değiştirilebilir.

Statik ayırıcı penceresine kaydırma çubukları eklemek *için, dwStyle'a*WS_HSCROLL ve WS_VSCROLL stilleri ekleyin.

Birden [Çok Belge Türleri, Görünümler ve Çerçeve Windows](../../mfc/multiple-document-types-views-and-frame-windows.md), Teknik Not [29](../../mfc/tn029-splitter-windows.md)ve statik ayırıcı pencereler hakkında daha fazla bilgi için `CSplitterWnd` sınıf genel bakış makalede "Splitter Windows" bakın.

## <a name="csplitterwndcreateview"></a><a name="createview"></a>CSplitterWnd::CreateView

Statik bir ayırıcı penceresi için bölmeleri oluşturur.

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
Yeni görünümü yerleştirmek için ayırıcı pencere satırını belirtir.

*Albay*<br/>
Yeni görünümü yerleştirmek için ayırıcı pencere sütunu belirtir.

*pViewClass*<br/>
Yeni görünümün [CRuntimeClass'ını](../../mfc/reference/cruntimeclass-structure.md) belirtir.

*sizeInit*<br/>
Yeni görünümün başlangıç boyutunu belirtir.

*Pcontext*<br/>
Görünümü oluşturmak için kullanılan bir oluşturma bağlamına işaretçi (genellikle *alt* çerçevenin geçersiz kılınan [CFrameWnd'ine geçirilen bağlam::Ayırıcı](../../mfc/reference/cframewnd-class.md#oncreateclient) penceresinin oluşturulduğu OnCreateClient üye işlevi).

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çerçeve ayırıcıyı görüntülemeden önce statik ayırıcı pencerenin tüm bölmeleri oluşturulmalıdır.

Çerçeve ayrıca, dinamik bir ayırıcı penceresinin kullanıcısı bölmeyi, satırı veya sütunu böldüğünde yeni bölmeler oluşturmak için bu üye işlevi de çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#4](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]

## <a name="csplitterwndcsplitterwnd"></a><a name="csplitterwnd"></a>CSplitterWnd::CSplitterWnd

Bir `CSplitterWnd` nesne oluşturmak için arayın.

```
CSplitterWnd();
```

### <a name="remarks"></a>Açıklamalar

Bir `CSplitterWnd` nesneyi iki adımda oluştur. İlk olarak, `CSplitterWnd` nesneyi oluşturan oluşturucuyu çağırın ve ardından ayırıcı penceresini oluşturan ve `CSplitterWnd` nesneye bağlanan Üye [Oluştur](#create) işlevini çağırın.

## <a name="csplitterwnddeletecolumn"></a><a name="deletecolumn"></a>CSplitterWnd::DeleteSütun

Bölme penceresinden bir sütunu siler.

```
virtual void DeleteColumn(int colDelete);
```

### <a name="parameters"></a>Parametreler

*colDelete*<br/>
Silinecek sütunu belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, dinamik ayırıcı penceresinin mantığını uygulamak için çerçeve tarafından çağrılır (yani, ayırıcı penceresi SPLS_DYNAMIC_SPLIT stiline sahipse). Bu özelleştirilebilir, sanal fonksiyonu [CreateView](#createview)ile birlikte , daha gelişmiş dinamik bölücüler uygulamak için.

## <a name="csplitterwnddeleterow"></a><a name="deleterow"></a>CSplitterWnd::DeleteRow

Ayırıcı penceresinden bir satırı siler.

```
virtual void DeleteRow(int rowDelete);
```

### <a name="parameters"></a>Parametreler

*satırSilin*<br/>
Silinecek satırı belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, dinamik ayırıcı penceresinin mantığını uygulamak için çerçeve tarafından çağrılır (yani, ayırıcı penceresi SPLS_DYNAMIC_SPLIT stiline sahipse). Bu özelleştirilebilir, sanal fonksiyonu [CreateView](#createview)ile birlikte , daha gelişmiş dinamik bölücüler uygulamak için.

## <a name="csplitterwnddeleteview"></a><a name="deleteview"></a>CSplitterWnd::DeleteView

Ayırıcı penceresinden bir görünümü siler.

```
virtual void DeleteView(
    int row,
    int col);
```

### <a name="parameters"></a>Parametreler

*Satır*<br/>
Görünümü silmek için ayırıcı pencere satırını belirtir.

*Albay*<br/>
Görünümü silmek için ayırıcı pencere sütunu belirtir.

### <a name="remarks"></a>Açıklamalar

Etkin görünüm siliniyorsa, bir sonraki görünüm etkin olur. Varsayılan uygulama görünümü [PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy)otomatik siler varsayar.

Bu üye işlev, dinamik ayırıcı penceresinin mantığını uygulamak için çerçeve tarafından çağrılır (yani, ayırıcı penceresi SPLS_DYNAMIC_SPLIT stiline sahipse). Bu özelleştirilebilir, sanal fonksiyonu [CreateView](#createview)ile birlikte , daha gelişmiş dinamik bölücüler uygulamak için.

## <a name="csplitterwnddokeyboardsplit"></a><a name="dokeyboardsplit"></a>CSplitterWnd::DoKeyboardSplit

Klavye bölme komutunu gerçekleştirir, genellikle "Pencere Bölme" olur.

```
virtual BOOL DoKeyboardSplit();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, [CView](../../mfc/reference/cview-class.md) sınıfı tarafından uygulamaya temsilci vermek `CSplitterWnd` için kullanılan üst düzey bir komutdur.

## <a name="csplitterwnddoscroll"></a><a name="doscroll"></a>CSplitterWnd::DoScroll

Bölünmüş pencerelerin senkronize kaydırma gerçekleştirir.

```
virtual BOOL DoScroll(
    CView* pViewFrom,
    UINT nScrollCode,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parametreler

*pViewFrom*<br/>
Kaydırma iletisinin kaynağı olan görünüme işaretçi.

*nScrollCode*<br/>
Kullanıcının kaydırma isteğini gösteren bir kaydırma-barkod kodu. Bu parametre iki bölümden oluşur: yatay olarak gerçekleşen kaydırma türünü belirleyen düşük sıralı bayt ve dikey olarak gerçekleşen kaydırma türünü belirleyen yüksek sıralı bayt:

- SB_BOTTOM Kayar alta.

- SB_LINEDOWN Bir satır aşağı kaydırır.

- SB_LINEUP Bir sıra yukarı kaydırır.

- SB_PAGEDOWN Bir sayfa aşağı kaydırır.

- SB_PAGEUP bir sayfa yukarı kaydırır.

- SB_TOP Üst lere kaydırır.

*bDoScroll*<br/>
Belirtilen kaydırma eyleminin oluşup oluşmadığını belirler. *bDoScroll* TRUE ise (diğer bir alt pencere varsa ve bölünmüş pencerelerde kaydırma aralığı varsa), belirtilen kaydırma eylemi gerçekleşebilir; *bDoScroll* FALSE ise (yani, alt pencere yoksa veya bölünmüş görünümler kaydırma aralığı yoksa), kaydırma oluşmaz.

### <a name="return-value"></a>Dönüş Değeri

Senkronize kaydırma oluşursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, görünüm bir kaydırma iletisi aldığında bölünmüş pencerelerin eşitlenmiş kaydırma gerçekleştirmek için çerçeve tarafından çağrılır. Eşitlenmiş kaydırma izin verilmeden önce kullanıcı tarafından bir eylem gerektiren geçersiz kılma.

## <a name="csplitterwnddoscrollby"></a><a name="doscrollby"></a>CSplitterWnd::DoScrollBy

Kaydırma, pencereleri belirli bir piksel sayısına böler.

```
virtual BOOL DoScrollBy(
    CView* pViewFrom,
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parametreler

*pViewFrom*<br/>
Kaydırma iletisinin kaynağı olan görünüme işaretçi.

*boyutKaydırma*<br/>
Yatay ve dikey olarak kaydırılacak piksel sayısı.

*bDoScroll*<br/>
Belirtilen kaydırma eyleminin oluşup oluşmadığını belirler. *bDoScroll* TRUE ise (diğer bir alt pencere varsa ve bölünmüş pencerelerde kaydırma aralığı varsa), belirtilen kaydırma eylemi gerçekleşebilir; *bDoScroll* FALSE ise (yani, alt pencere yoksa veya bölünmüş görünümler kaydırma aralığı yoksa), kaydırma oluşmaz.

### <a name="return-value"></a>Dönüş Değeri

Senkronize kaydırma oluşursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, bölünmüş pencerelerin *boyutScroll*ile gösterilen piksel miktarına göre senkronize kaydırma yapmak için bir kaydırma iletisine yanıt olarak çerçeve tarafından çağrılır. Pozitif değerler aşağı ve sağa kaydırma gösterir; negatif değerler yukarı ve sola kaydırma gösterir.

Kaydırmaya izin vermeden önce kullanıcı tarafından bir eylem gerektirecek şekilde geçersiz kılın.

## <a name="csplitterwndgetactivepane"></a><a name="getactivepane"></a>CSplitterWnd::GetActivePane

Etkin bölmeyi odaktan veya çerçevedeki etkin görünümden belirler.

```
virtual CWnd* GetActivePane(
    int* pRow = NULL,
    int* pCol = NULL);
```

### <a name="parameters"></a>Parametreler

*pRow*<br/>
Etkin bölmenin satır numarasını almak için **int** için bir işaretçi.

*pCol*<br/>
Etkin bölmenin sütun numarasını almak için **int** için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Etkin bölmeye işaretçi. Etkin bölme yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, bir ayırıcı penceresinde etkin bölmeyi belirlemek için çerçeve tarafından çağrılır. Etkin bölmeyi almadan önce kullanıcı tarafından bir eylem gerektirecek şekilde geçersiz kılın.

## <a name="csplitterwndgetcolumncount"></a><a name="getcolumncount"></a>CSplitterWnd::GetColumnCount

Geçerli bölme sütun sayısını döndürür.

```
int GetColumnCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayırıcıdaki geçerli sütun sayısını verir. Statik bir ayırıcı için bu da en fazla sütun sayısı olacaktır.

## <a name="csplitterwndgetcolumninfo"></a><a name="getcolumninfo"></a>CSplitterWnd::GetColumnInfo

Belirtilen sütundaki bilgileri verir.

```cpp
void GetColumnInfo(
    int col,
    int& cxCur,
    int& cxMin) const;
```

### <a name="parameters"></a>Parametreler

*Albay*<br/>
Bir sütun belirtir.

*cxCur*<br/>
Sütunun geçerli genişliğine ayarlanacak bir **int** başvurusu.

*cxMin*<br/>
Sütunun geçerli minimum genişliğine ayarlanacak bir **int** başvurusu.

## <a name="csplitterwndgetpane"></a><a name="getpane"></a>CSplitterWnd::GetPane

Bölmesi belirtilen satır ve sütunda döndürür.

```
CWnd* GetPane(
    int row,
    int col) const;
```

### <a name="parameters"></a>Parametreler

*Satır*<br/>
Bir satır belirtir.

*Albay*<br/>
Bir sütun belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bölmesi belirtilen satır ve sütunda döndürür. Döndürülen bölme genellikle [CView](../../mfc/reference/cview-class.md)türetilmiş bir sınıftır.

## <a name="csplitterwndgetrowcount"></a><a name="getrowcount"></a>CSplitterWnd::GetRowCount

Geçerli bölme satır sayısını döndürür.

```
int GetRowCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayırıcı penceresindegeçerli satır sayısını verir. Statik ayırıcı penceresi için bu da en fazla satır sayısı olacaktır.

## <a name="csplitterwndgetrowinfo"></a><a name="getrowinfo"></a>CSplitterWnd::GetRowInfo

Belirtilen satırdaki bilgileri verir.

```cpp
void GetRowInfo(
    int row,
    int& cyCur,
    int& cyMin) const;
```

### <a name="parameters"></a>Parametreler

*Satır*<br/>
Bir satır belirtir.

*cyCur*<br/>
Satırın pikseldeki geçerli yüksekliğine ayarlanacak **int'e** başvuru.

*cyMin*<br/>
Satırın piksellerde geçerli minimum yüksekliğe ayarlanacak **int'e** başvuru.

### <a name="remarks"></a>Açıklamalar

Belirtilen satır hakkında bilgi almak için bu üye işlevini arayın. *CyCur* parametresi belirtilen satırın geçerli yüksekliğiyle doldurulur ve *cyMin* satırın minimum yüksekliğiyle doldurulur.

## <a name="csplitterwndgetscrollstyle"></a><a name="getscrollstyle"></a>CSplitterWnd::GetScrollStyle

Bölücü penceresi için paylaşılan kaydırma çubuğu stilini döndürür.

```
DWORD GetScrollStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, aşağıdaki windows stili bayraklarından biri veya birkaçı:

- WS_HSCROLL Bölücü şu anda paylaşılan yatay kaydırma çubuklarını yönetiyorsa.

- WS_VSCROLL Bölücü şu anda paylaşılan dikey kaydırma çubuklarını yönetiyorsa.

Sıfır ise, bölücü penceresi şu anda paylaşılan kaydırma çubuklarını yönetmez.

## <a name="csplitterwndidfromrowcol"></a><a name="idfromrowcol"></a>CSplitterWnd::IdFromRowCol

Belirtilen satır ve sütundaki bölmenin alt pencere kimliğini alır.

```
int IdFromRowCol(
    int row,
    int col) const;
```

### <a name="parameters"></a>Parametreler

*Satır*<br/>
Ayırıcı pencere satırını belirtir.

*Albay*<br/>
Ayırıcı pencere sütunu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bölmenin alt pencere kimliği.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, görünüm olmayan ları bölme olarak oluşturmak için kullanılır ve bölme var olmadan önce çağrılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#5](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]

## <a name="csplitterwndischildpane"></a><a name="ischildpane"></a>CSplitterWnd::IsChildPane

*pWnd'nin* şu anda bu ayırıcı pencerenin alt bölmesi olup olmadığını belirler.

```
BOOL IsChildPane(
    CWnd* pWnd,
    int* pRow,
    int* pCol);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Test edilecek bir [CWnd](../../mfc/reference/cwnd-class.md) nesnesine işaretçi.

*pRow*<br/>
Satır numarasını depolayabilmek için bir **int** işaretçisi.

*pCol*<br/>
Sütun numarasını depolayabilmek için bir **int** işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Sıfır değilse, *pWnd* şu anda bu bölücü penceresinin bir alt bölmesi ve *pRow* ve *pCol* ayırıcı penceresinde bölmekonumu ile doldurulur. *pWnd* bu ayırıcı penceresinin alt bölmesi değilse, 0 döndürülür.

### <a name="remarks"></a>Açıklamalar

6.0'dan önceki Visual C++ sürümlerinde bu işlev,

`BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`

Bu sürüm artık eskidir ve kullanılmamalıdır.

## <a name="csplitterwndistracking"></a><a name="istracking"></a>CSplitterWnd::IsTracking

Penceredeki ayırıcı çubuğunun şu anda taşınıp taşınmamakta olup olmadığını belirlemek için bu üye işlevi arayın.

```
BOOL IsTracking();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ayırıcı işlemi devam ediyorsa sıfır olmayan; aksi takdirde 0.

## <a name="csplitterwndondrawsplitter"></a><a name="ondrawsplitter"></a>CSplitterWnd::OnDrawSplitter

Bölünmüş bir pencerenin görüntüsünü görüntüler.

```
virtual void OnDrawSplitter(
    CDC* pDC,
    ESplitType nType,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Çizmek için aygıt bağlamına bir işaretçi. *pDC* NULL ise, [cwnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) çerçeve tarafından çağrılır ve hiçbir bölünmüş pencere çizilir.

*nTipi*<br/>
Bir değeri `enum ESplitType`, aşağıdakilerden biri olabilir:

- `splitBox`Ayırıcı sürükleme kutusu.

- `splitBar`İki bölme pencere arasında görünen çubuk.

- `splitIntersection`Bölünmüş pencerelerin kesiştiği yer. Bu öğe, Windows 95/98'de çalışırken çağrılmaz.

- `splitBorder`Bölünmüş pencere kenarlıkları.

*Rect*<br/>
Bölünmüş pencerelerin boyutunu ve şeklini belirten bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, bir ayırıcı pencerenin tam özelliklerini çizmek ve belirtmek için çerçeve tarafından çağrılır. Bir `OnDrawSplitter` ayırıcı pencerenin çeşitli grafik bileşenleri için görüntülerin gelişmiş özelleştirme için geçersiz kılma. Varsayılan görüntüler, bölünen çubukların kesişmelerinin bir araya getirilmiş olması nedeniyle Windows için Microsoft İşleri veya Microsoft Windows 95/98'deki ayırıcıya benzer.

Dinamik ayırıcı pencereler hakkında daha fazla bilgi için, birden [çok belge türleri, görünümler ve Çerçeve Windows,](../../mfc/multiple-document-types-views-and-frame-windows.md) [Teknik Not 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfa genel bakış makalesinde "Splitter Windows" bakın.

## <a name="csplitterwndoninverttracker"></a><a name="oninverttracker"></a>CSplitterWnd::OnInvertTracker

Bölünmüş pencerenin görüntüsünü çerçeve penceresiyle aynı boyut ve şekle bölüyor.

```
virtual void OnInvertTracker(const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
İzleme dikdörtgenini belirten bir `CRect` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, bölücülerin yeniden boyutlandırılması sırasında çerçeve tarafından çağrılır. Ayırıcı `OnInvertTracker` penceresinin görüntülerinin gelişmiş özelleştirmesi için geçersiz kılın. Varsayılan görüntüler, bölünen çubukların kesişmelerinin bir araya getirilmiş olması nedeniyle Windows için Microsoft İşleri veya Microsoft Windows 95/98'deki ayırıcıya benzer.

Dinamik ayırıcı pencereler hakkında daha fazla bilgi için, birden [çok belge türleri, görünümler ve Çerçeve Windows,](../../mfc/multiple-document-types-views-and-frame-windows.md) [Teknik Not 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfa genel bakış makalesinde "Splitter Windows" bakın.

## <a name="csplitterwndrecalclayout"></a><a name="recalclayout"></a>CSplitterWnd::RecalcLayout

Satır veya sütun boyutunu ayarladıktan sonra ayırıcı penceresini yeniden görüntülemek için arayın.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Açıklamalar

[SetRowInfo](#setrowinfo) ve [SetColumnInfo](#setcolumninfo) üye işlevleriyle satır ve sütun boyutlarını ayarladıktan sonra ayırıcı penceresini doğru bir şekilde yeniden görüntülemek için bu üye işlevi arayın. Bölünen pencere görünmeden önce oluşturma işleminin bir parçası olarak satır ve sütun boyutlarını değiştirirseniz, bu üye işlevi çağırmak gerekmez.

Çerçeve, kullanıcı ayırıcı penceresini yeniden boyutlandırır veya bir bölme taşırsa bu üye işlevi çağırır.

### <a name="example"></a>Örnek

  [CSplitterWnd örneğine bakın:SetColumnInfo](#setcolumninfo).

## <a name="csplitterwndsetactivepane"></a><a name="setactivepane"></a>CSplitterWnd::SetActivePane

Çerçevedeki etkin bölmeyi ayarlar.

```
virtual void SetActivePane(
    int row,
    int col,
    CWnd* pWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*Satır*<br/>
*pWnd* NULL ise, etkin olacak bölmedeki satırı belirtir.

*Albay*<br/>
*pWnd* NULL ise, etkin olacak bölmedeki sütunu belirtir.

*Pwnd*<br/>
Bir `CWnd` nesneye işaretçi. NULL ise, *satır* ve *col* tarafından belirtilen bölme etkin olarak ayarlanır. NULL değilse, etkin olarak ayarlanmış bölmeyi belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, kullanıcı çerçeve penceresi içindeki bir bölmeye odak değiştirdiğinde bir bölmeyi etkin olarak ayarlamak için çerçeve tarafından çağrılır. Odağı belirtilen görünüme değiştirmek için açıkça arayabilirsiniz. `SetActivePane`

Satır ve sütun sağlayarak **veya** *pWnd*sağlayarak bölmeyi belirtin.

## <a name="csplitterwndsetcolumninfo"></a><a name="setcolumninfo"></a>CSplitterWnd::SetColumnInfo

Belirtilen sütun bilgilerini ayarlamak için arayın.

```cpp
void SetColumnInfo(
    int col,
    int cxIdeal,
    int cxMin);
```

### <a name="parameters"></a>Parametreler

*Albay*<br/>
Ayırıcı pencere sütunu belirtir.

*cxİdeal*<br/>
Piksellerde ayırıcı pencere sütunu için ideal bir genişlik belirtir.

*cxMin*<br/>
Piksellerde bölücü pencere sütunu için minimum genişlik belirtir.

### <a name="remarks"></a>Açıklamalar

Bir sütun için yeni bir minimum genişlik ve ideal genişlik ayarlamak için bu üye işlevi arayın. Sütun minimum değeri, sütunun tam olarak görüntülenemeyecek kadar küçük olacağını belirler.

Çerçeve ayırıcı penceresini görüntülediğinde, bölmeleri sütunlar ve satırlar ideal boyutlarına göre düzenler ve bölme penceresinin istemci alanının sağ alt köşesinden sol üst köşesine çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#6](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]

## <a name="csplitterwndsetrowinfo"></a><a name="setrowinfo"></a>CSplitterWnd::SetRowInfo

Belirtilen satır bilgilerini ayarlamak için arayın.

```cpp
void SetRowInfo(
    int row,
    int cyIdeal,
    int cyMin);
```

### <a name="parameters"></a>Parametreler

*Satır*<br/>
Bir ayırıcı pencere satırını belirtir.

*cyİdeal*<br/>
Piksellerde ayırıcı pencere satırı için ideal bir yükseklik belirtir.

*cyMin*<br/>
Piksellerde ayırıcı pencere satırı için minimum yükseklik belirtir.

### <a name="remarks"></a>Açıklamalar

Bir satır için yeni bir minimum yükseklik ve ideal yükseklik ayarlamak için bu üye işlevi arayın. Satır minimum değeri, satırın tam olarak görüntülenemeyecek kadar küçük olacağını belirler.

Çerçeve ayırıcı penceresini görüntülediğinde, bölmeleri sütunlar ve satırlar ideal boyutlarına göre düzenler ve bölme penceresinin istemci alanının sağ alt köşesinden sol üst köşesine çalışır.

## <a name="csplitterwndsetscrollstyle"></a><a name="setscrollstyle"></a>CSplitterWnd::SetScrollStyle

Bölücü penceresinin paylaşılan kaydırma çubuğu desteği için yeni kaydırma stilini belirtir.

```cpp
void SetScrollStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Ayırıcı penceresinin paylaşılan kaydırma çubuğu desteği için aşağıdaki değerlerden biri olabilecek yeni kaydırma stili:

- WS_HSCROLL Yatay paylaşılan kaydırma çubuklarını oluşturun/gösterin.

- WS_VSCROLL Dikey paylaşılan kaydırma çubuklarını oluşturun/gösterin.

### <a name="remarks"></a>Açıklamalar

Bir kaydırma çubuğu oluşturulduktan sonra, bu `SetScrollStyle` stil olmadan çağrılsa bile yok edilmez; bunun yerine bu kaydırma çubukları gizlidir. Bu, kaydırma çubuklarının gizli olmalarına rağmen durumlarını korumalarını sağlar. Aradıktan `SetScrollStyle` sonra tüm değişikliklerin etkili olması için [RecalcLayout'ı](#recalclayout) aramak gerekir.

## <a name="csplitterwndsplitcolumn"></a><a name="splitcolumn"></a>CSplitterWnd::SplitSütun

Çerçeve penceresinin dikey olarak nerede bölündüğünü gösterir.

```
virtual BOOL SplitColumn(int cxBefore);
```

### <a name="parameters"></a>Parametreler

*cxBefore*<br/>
Piksellerde, bölmenin gerçekleştiği önce konum.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Dikey bir ayırıcı penceresi oluşturulduğunda bu üye işlev çağrılır. `SplitColumn`bölmenin gerçekleştiği varsayılan konumu gösterir.

`SplitColumn`dinamik ayırıcı penceresinin mantığını uygulamak için çerçeve tarafından çağrılır (yani, ayırıcı penceresi SPLS_DYNAMIC_SPLIT stiline sahipse). Bu özelleştirilebilir, sanal fonksiyonu [CreateView](#createview)ile birlikte , daha gelişmiş dinamik bölücüler uygulamak için.

## <a name="csplitterwndsplitrow"></a><a name="splitrow"></a>CSplitterWnd::SplitRow

Çerçeve penceresinin yatay olarak bölündüğü yeri gösterir.

```
virtual BOOL SplitRow(int cyBefore);
```

### <a name="parameters"></a>Parametreler

*cyBefore*<br/>
Piksellerde, bölmenin gerçekleştiği önce konum.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yatay bir ayırıcı penceresi oluşturulduğunda bu üye işlev çağrılır. `SplitRow`bölmenin gerçekleştiği varsayılan konumu gösterir.

`SplitRow`dinamik ayırıcı penceresinin mantığını uygulamak için çerçeve tarafından çağrılır (yani, ayırıcı penceresi SPLS_DYNAMIC_SPLIT stiline sahipse). Bu özelleştirilebilir, sanal fonksiyonu [CreateView](#createview)ile birlikte , daha gelişmiş dinamik bölücüler uygulamak için.

## <a name="csplitterwndondraw"></a><a name="ondraw"></a>CSplitterWnd::OnDraw

Ayırıcı penceresini çizmek için çerçeve tarafından çağrılır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Aygıt bağlamına işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)
