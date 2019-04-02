---
title: CView sınıfı
ms.date: 11/04/2016
f1_keywords:
- CView
- AFXWIN/CView
- AFXWIN/CView::CView
- AFXWIN/CView::DoPreparePrinting
- AFXWIN/CView::GetDocument
- AFXWIN/CView::IsSelected
- AFXWIN/CView::OnDragEnter
- AFXWIN/CView::OnDragLeave
- AFXWIN/CView::OnDragOver
- AFXWIN/CView::OnDragScroll
- AFXWIN/CView::OnDrop
- AFXWIN/CView::OnDropEx
- AFXWIN/CView::OnInitialUpdate
- AFXWIN/CView::OnPrepareDC
- AFXWIN/CView::OnScroll
- AFXWIN/CView::OnScrollBy
- AFXWIN/CView::OnActivateFrame
- AFXWIN/CView::OnActivateView
- AFXWIN/CView::OnBeginPrinting
- AFXWIN/CView::OnDraw
- AFXWIN/CView::OnEndPrinting
- AFXWIN/CView::OnEndPrintPreview
- AFXWIN/CView::OnPreparePrinting
- AFXWIN/CView::OnPrint
- AFXWIN/CView::OnUpdate
helpviewer_keywords:
- CView [MFC], CView
- CView [MFC], DoPreparePrinting
- CView [MFC], GetDocument
- CView [MFC], IsSelected
- CView [MFC], OnDragEnter
- CView [MFC], OnDragLeave
- CView [MFC], OnDragOver
- CView [MFC], OnDragScroll
- CView [MFC], OnDrop
- CView [MFC], OnDropEx
- CView [MFC], OnInitialUpdate
- CView [MFC], OnPrepareDC
- CView [MFC], OnScroll
- CView [MFC], OnScrollBy
- CView [MFC], OnActivateFrame
- CView [MFC], OnActivateView
- CView [MFC], OnBeginPrinting
- CView [MFC], OnDraw
- CView [MFC], OnEndPrinting
- CView [MFC], OnEndPrintPreview
- CView [MFC], OnPreparePrinting
- CView [MFC], OnPrint
- CView [MFC], OnUpdate
ms.assetid: 9cff3c56-7564-416b-b9a4-71a9254ed755
ms.openlocfilehash: 06c6d4dff28399f3d8e6ac7f46d9ed751850036f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775315"
---
# <a name="cview-class"></a>CView sınıfı

Kullanıcı tanımlı görünüm sınıfları için temel işlevleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CView : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CView::CView](#cview)|Oluşturur bir `CView` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CView::DoPreparePrinting](#doprepareprinting)|Yazdır iletişim kutusunu görüntüler ve yazıcı cihaz bağlamı oluşturur. geçersiz kılarken çağrı `OnPreparePrinting` üye işlevi.|
|[CView::GetDocument](#getdocument)|Görünüm ile ilişkilendirilen belgeyi döndürür.|
|[CView::IsSelected](#isselected)|Bir belge öğesinin seçilip seçilmediğini olup olmadığını sınar. OLE desteği için gereklidir.|
|[CView::OnDragEnter](#ondragenter)|Bir öğenin ilk görünüm sürükle ve bırak bölgeye sürüklendiğinde çağırılır.|
|[CView::OnDragLeave](#ondragleave)|Sürüklenen öğe bir görünümünün sürükle ve bırak bölge ayrıldığında çağrılır.|
|[CView::OnDragOver](#ondragover)|Bir öğe bir görünüm sürükle ve bırak bölge sürüklendiğinde çağırılır.|
|[CView::OnDragScroll](#ondragscroll)|İmleç pencerenin kaydırma bölgeye sürüklediğiniz olup olmadığını belirlemek için çağrılır.|
|[CView::OnDrop](#ondrop)|Bir öğe bir görünüm varsayılan işleyici sürükle ve bırak bölgeye bırakıldı çağrılır.|
|[CView::OnDropEx](#ondropex)|Bir öğe bir görünüm birincil işleyici sürükle ve bırak bölgeye bırakıldı çağrılır.|
|[CView::OnInitialUpdate](#oninitialupdate)|Bir görünüm, ilk olarak bir belgeye eklendikten sonra çağırılır.|
|[CView::OnPrepareDC](#onpreparedc)|Önce çağırılır `OnDraw` üyesi çağrıldığında için ekran görüntüsünü veya `OnPrint` üye işlevi, yazdırma ya da yazdırma önizleme için çağrılır.|
|[CView::OnScroll](#onscroll)|OLE öğeleri, görünümün kenarlıklarının dışına sürüklendiğinde çağırılır.|
|[CView::OnScrollBy](#onscrollby)|Etkin yerinde OLE öğeleri içeren bir görünüm kaydırılan çağrılır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CView::OnActivateFrame](#onactivateframe)|Çerçeve penceresi görünümü etkin veya devre dışı olduğunda çağrılır.|
|[CView::OnActivateView](#onactivateview)|Bir görünüm etkinleştirildiğinde çağırılır.|
|[CView::OnBeginPrinting](#onbeginprinting)|Yazdırma işi başladığında çağrılır; Grafik cihaz arabirimi (GDI) kaynakları ayırmak için geçersiz kılın.|
|[CView::OnDraw](#ondraw)|Ekran görüntüsü, yazdırmayı ve Baskı Önizleme için belgenin bir görüntüsünü işlemek için çağrılır. Gerekli uygulama.|
|[CView::OnEndPrinting](#onendprinting)|Yazdırma işi sona erdiğinde çağrılır; GDI kaynaklarını serbest için geçersiz kılın.|
|[CView::OnEndPrintPreview](#onendprintpreview)|Önizleme modunu çıkıldı çağrılır.|
|[CView::OnPreparePrinting](#onprepareprinting)|Bir belge yazdırılmadan ya da önizlenmeden önce çağırılır; Yazdır iletişim kutusunu başlatmak için geçersiz kılın.|
|[CView::OnPrint](#onprint)|Belgenin bir sayfasını yazdıramaz veya çağrılır.|
|[CView::OnUpdate](#onupdate)|Kendi belge olan bir görünümü bildirmek için çağırılır değiştirdi.|

## <a name="remarks"></a>Açıklamalar

Görünüm bir belgeye ekli ve belge ile kullanıcı arasında aracı görevi görür: görünüm ekran veya yazıcı belgenin bir görüntü oluşturur ve işlemleri belge bağlı olarak kullanıcı girişini yorumlama.

Bir alt çerçeve penceresinin bir görünümüdür. Birden fazla görünümü, bölümlendirici pencereyi olduğu gibi bir çerçeve penceresi paylaşabilirsiniz. View sınıfı, bir çerçeve penceresi sınıfı ve belge sınıfı arasındaki ilişkiyi tarafından kurulan bir `CDocTemplate` nesne. Kullanıcı yeni bir pencere açılır veya mevcut bir ayıran bir framework yeni bir görünüm oluşturur ve bunu belgenin ekler.

Tek bir belgeye bir görünüm eklenebilecek, ancak bir belgede birden çok görünüm tek seferde bağlı olabilir — örneğin, belgeyi bir ayırıcı penceresi veya birden çok belge arabirimi (MDI) uygulamasında birden çok alt penceresi görüntülenir. Uygulamanızın belirli belge türü için Görünüm farklı türlerini destekler; Örneğin, bir sözcük programı yalnızca bölüm başlıkları gösteren bir anahat görünümü ve bir belge tam metin görünümü sağlayabilir. Ayırıcı penceresi kullanıyorsanız bu farklı türde ayrı çerçeve pencereleri veya bir tek çerçeve penceresinin ayrı bölmeleri yerleştirilebilir.

Bir görünüm girişi, klavye girişi, fare girişi veya komutları yanı sıra, sürükle ve bırak ile bir giriş menüler, araç çubukları ya da kaydırma çubukları gibi birkaç farklı türde işlenmesinden sorumludur. Bir görünüm alt çerçeve penceresi tarafından iletilen komutlarını alır. Görünümün belirli bir komut işlemez, komut, ilişkili belge için iletir. Tüm komut hedefleri gibi bir görünüm ileti eşlemesi üzerinden mesajları alıp işler.

Görünümdür sorumlu görüntüleme ve belgenin verilerini değiştirme, ancak bunu depolamayın. Belge verilerini hakkında gerekli bilgileri görünümüyle sağlar. Belgenin verilerini doğrudan üyeleri veya üye işlevleri çağırmak view sınıfı için belge sınıfında sağlayabilir görüntüleme erişimi sağlayabilirsiniz.

Bir belgenin veriler değiştiğinde görünüm değişikliklerin sorumlu genellikle çağırır [CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) işlevi için diğer tüm görünümlerin çağırarak bildirir belge `OnUpdate` için üye işlevi Her. Varsayılan uygulaması `OnUpdate` görünümün tüm istemci alanını geçersiz kılar. Bu yalnızca istemci alanını eşlemek için belgenin değiştirilmiş bölümleri bölgeleri geçersiz kılabilirsiniz.

Kullanılacak `CView`, bir sınıf türetmeniz ve uygulama `OnDraw` ekran gerçekleştirmek için üye işlevi. Ayrıca `OnDraw` yazdırmayı ve baskı önizlemeyi gerçekleştirilecek. Framework, yazdırma ve belge, Önizleme için yazdırma döngü işler.

Bir görünümü ile kaydırma çubuğu iletileri işleyen [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) ve [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) üye işlevleri. Bu işlevleri işleme kaydırma çubuğu ileti uygulayabilir veya kullanabileceğiniz `CView` türetilmiş sınıf [CScrollView](../../mfc/reference/cscrollview-class.md) sizin için kaydırma işlemek için.

Yanında `CScrollView`, türetilen dokuz diğer sınıflar Microsoft Foundation Class Kitaplığı sağlar `CView`:

- [CCtrlView](../../mfc/reference/cctrlview-class.md), belge - görünüm mimarisi ağacı, liste ve zengin düzenleme denetimleri kullanımını sağlayan bir görünüm.

- [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md), iletişim kutusu denetimlerde veritabanı kayıtlarını görüntüleyen bir görünüm.

- [CEditView](../../mfc/reference/ceditview-class.md), çok satırlı basit metin düzenleyicilerini sağlayan bir görünüm. Kullanabileceğiniz bir `CEditView` belgesinde bir görünüm yanı sıra bir iletişim kutusu denetimi olarak nesne.

- [CFormView](../../mfc/reference/cformview-class.md), iletişim kutusu denetimleri içeren ve bir iletişim şablon kaynağını temel kaydırılabilir bir görünüm.

- [CListView](../../mfc/reference/clistview-class.md), belge - görünüm mimarisinin liste denetimleri ile kullanımını sağlayan bir görünüm.

- [CRecordView](../../mfc/reference/crecordview-class.md), iletişim kutusu denetimlerde veritabanı kayıtlarını görüntüleyen bir görünüm.

- [CRichEditView](../../mfc/reference/cricheditview-class.md), belge - görünüm mimarisi ile zengin düzenleme denetimleri kullanımını sağlayan bir görünüm.

- [CScrollView](../../mfc/reference/cscrollview-class.md), otomatik olarak kaydırma desteği sağlayan bir görünüm.

- [CTreeView](../../mfc/reference/ctreeview-class.md), belge - görünüm mimarisinin ağaç denetimleri ile kullanımını sağlayan bir görünüm.

`CView` Ayrıca sınıfında adlı bir türetilen uygulamaya sınıf `CPreviewView`, yazdırma önizleme gerçekleştirmek için framework tarafından kullanılır. Bu sınıf gibi bir araç, tek veya çift sayfa önizleme Yazdır-Önizle penceresi için benzersiz özellikler için destek sağlar ve yakınlaştırma, önizlenen görüntü büyütme olan. Çağrı yapma veya herhangi bir geçersiz kılma gerekmez `CPreviewView`ait üye işlevleri (örneğin, yazdırma önizleme modunda düzenleme desteklemek istiyorsanız), yazdırma önizleme için kendi arabirimi uygulamak istemediğiniz sürece. Kullanma hakkında daha fazla bilgi için `CView`, bkz: [belge/görünüm mimarisi](../../mfc/document-view-architecture.md) ve [yazdırma](../../mfc/printing.md). Ayrıca bkz [Teknik Not 30](../../mfc/tn030-customizing-printing-and-print-preview.md) Baskı Önizlemeyi özelleştirme hakkında daha fazla ayrıntı için.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CView`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="cview"></a>  CView::CView

Oluşturur bir `CView` nesne.

```
CView();
```

### <a name="remarks"></a>Açıklamalar

Framework, yeni bir çerçeve penceresi oluşturulduğunda veya bir pencereyi bölme oluşturucuyu çağırır. Geçersiz kılma [OnInitialUpdate](#oninitialupdate) görünümü belgeye eklendikten sonra başlatmak için üye işlevi.

##  <a name="doprepareprinting"></a>  CView::DoPreparePrinting

Bu işlevi çağırın kılacağınızı [OnPreparePrinting](#onprepareprinting) Yazdır iletişim kutusunu çağırmak ve bir yazıcı cihaz bağlamı oluşturur.

```
BOOL DoPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*pInfo*<br/>
İşaret eden bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) geçerli yazdırma işi açıklayan yapısı.

### <a name="return-value"></a>Dönüş Değeri

Yazdırma ya da yazdırma önizleme başlayabilirsiniz olursa sıfır dışı; 0 işlemi iptal edildi.

### <a name="remarks"></a>Açıklamalar

Bu işlevin davranışı olup, yazdırma ya da yazdırma önizleme için Aranan üzerinde bağlıdır (tarafından belirtilen `m_bPreview` üyesi *pInfo* parametresi). Bir dosyaya yazdırılır, bu işlev değerleri Yazdır iletişim kutusunu çağırır [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) , yapı *pInfo* işaret; kullanıcı iletişim kutusunu kapattıktan sonra işlev oluşturur. bir Yazıcı cihaz bağlamı iletişim kutusunda belirtilen kullanıcı ayarlarınızı temel alan ve bu cihaz bağlamı aracılığıyla döndürür *pInfo* parametresi. Bu cihaz bağlamı, belge yazdırma için kullanılır.

Bir dosya önizlemesi, bu işlev geçerli yazıcı ayarları kullanarak bir yazıcı cihaz bağlamı oluşturur; Bu cihaz bağlamı, Önizleme sırasında yazıcı benzetimi için kullanılır.

##  <a name="getdocument"></a>  CView::GetDocument

Görünümün belgeye bir işaretçi almak için bu işlevi çağırın.

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi [CDocument](../../mfc/reference/cdocument-class.md) görüntüyle ilişkili nesne. Görünüm bir belgeye ekli değil yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bu belgenin üye işlevleri çağırmanızı sağlar.

##  <a name="isselected"></a>  CView::IsSelected

Belirtilen bir belge öğesinin seçilip seçilmediğini kontrol etmek için framework tarafından çağırılır.

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>Parametreler

*pDocItem*<br/>
Test edilen belge öğesi işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bir belge öğesinin seçilip olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan uygulaması false değerini döndürür. Seçimi kullanarak uyguluyorsanız, bu işlev geçersiz kılınamıyor [Cdocıtem](../../mfc/reference/cdocitem-class.md) nesneleri. Görünümünüzü OLE öğeleri içeriyorsa, bu işlev geçersiz kılmanız gerekir.

##  <a name="onactivateframe"></a>  CView::OnActivateFrame

Çerçeve penceresi görünümü etkin veya devre dışı olduğunda framework tarafından çağırılır.

```
virtual void OnActivateFrame(
    UINT nState,
    CFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>Parametreler

*nDurum*<br/>
Çerçeve penceresi olup olmadığını belirten etkin veya devre dışı. Aşağıdaki değerlerden biri olabilir:

- Çerçeve penceresi WA_INACTIVE devre dışı bırakılıyor.

- Çerçeve penceresi dışında bir fare bazı yöntem aracılığıyla etkinleştirildiğini WA_ACTIVE (örneğin, bir pencere seçmek için klavye arabirimi tarafından kullanımını) tıklayın.

- Çerçeve penceresi WA_CLICKACTIVE bir fare tıklatın etkinleştiriliyor

*pFrameWnd*<br/>
Etkinleştirilecek olan çerçeve işaretçisi.

### <a name="remarks"></a>Açıklamalar

Görünüm ile ilişkilendirilen çerçeve penceresi etkin veya devre dışı olduğunda özel işlem gerçekleştirmek istiyorsanız bu üye işlevini geçersiz kılar. Örneğin, [Cformview'yu](../../mfc/reference/cformview-class.md) kaydeder ve Denetim odağa sahip yükler, bu geçersiz kılma gerçekleştirir.

##  <a name="onactivateview"></a>  CView::OnActivateView

Bir görünümü etkin veya devre dışı olduğunda framework tarafından çağırılır.

```
virtual void OnActivateView(
    BOOL bActivate,
    CView* pActivateView,
    CView* pDeactiveView);
```

### <a name="parameters"></a>Parametreler

*bActivate*<br/>
Görünüm belirtir etkin veya devre dışı.

*pActivateView*<br/>
Etkinleştirilmekte olan view nesnesinin işaret eder.

*pDeactiveView*<br/>
Devre dışı bırakılıyor view nesnesinin işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan uygulamasını odak etkinleştirilmekte olan görünüme ayarlar. Bir görünümü etkin veya devre dışı olduğunda özel işlem gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar. Etkin olmayan görünümleri etkin görünüm ayırt özel görsel ipuçlarını sağlama istiyorsanız, örneğin, inceleyebilir *bActivate* parametresi ve görünümün görünüm uygun şekilde güncelleştirin.

*PActivateView* ve *pDeactiveView* parametreleri, etkin bir değişiklik ile uygulamanın ana çerçeve penceresinin etkinleştirilmişse aynı görünüme noktası — Örneğin, odak noktası olup olmadığını bir görünüm başka bir uygulamadaki veya yerine başka bir uygulama bu bir MDI alt pencereleri arasında geçiş yaparken aktardı. Gerekirse, paletinde yeniden hayata geçirmek bir görünüm sağlar.

Bu parametreleri farklı olduğunda [CFrameWnd::SetActiveView](../../mfc/reference/cframewnd-class.md#setactiveview) farklı bir görünüm adlı [CFrameWnd::GetActiveView](../../mfc/reference/cframewnd-class.md#getactiveview) döndürür. Bu, çoğunlukla Bölümlendirici pencereler ile gerçekleşir.

##  <a name="onbeginprinting"></a>  CView::OnBeginPrinting

Sonra bir yazdırma ya da yazdırma önizleme işinin başlangıcında framework tarafından çağırılır `OnPreparePrinting` çağrıldı.

```
virtual void OnBeginPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Yazıcı cihaz bağlamı işaret eder.

*pInfo*<br/>
İşaret eden bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) geçerli yazdırma işi açıklayan yapısı.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulama, hiçbir şey yapmaz. Bu işlev özellikle yazdırma için gerekli tüm GDI kaynaklarını, kalemler veya yazı tipleri gibi ayırmak için geçersiz kılın. GDI nesneleri içinden cihaz bağlamına seçme [OnPrint](#onprint) bunları kullandığı her sayfa için üye işlevi. Ekran görüntüsü hem de yazdırma gerçekleştirmek için aynı görünüm nesnesi kullanıyorsanız, her ekran için gereken GDI kaynakları için ayrı değişkenleri kullanın. Bu güncelleştirme sırasında yazdırma ekranı olanak sağlar.

Bu işlev, yazıcı cihaz bağlamının özelliklerine bağlıdır başlatmaların de kullanabilirsiniz. Örneğin, belge yazdırma için gereken sayfa sayısını (örneğin, sayfa uzunluğu) yazdırma iletişim kutusundan kullanıcının belirlediği ayarlara bağlı olabilir. Böyle bir durumda, belgenin uzunluğunu belirtemezsiniz [OnPreparePrinting](#onprepareprinting) üye işlevi, burada normalde bunu; yazıcı cihaz bağlamı ayarlar iletişim kutusu tabanlı oluşturuluncaya kadar beklemeniz gerekir. [OnBeginPrinting](#onbeginprinting) size ilk geçersiz kılınabilir işlevi erişmek için [CDC](../../mfc/reference/cdc-class.md) böylece belge uzunluğu bu işlevden ayarlayabilirsiniz yazıcı cihaz bağlamı temsil eden nesne. Belgenin uzunluğu bu zamana kadar belirtilmezse, kaydırma çubuğu yazdırma önizleme sırasında görüntülenmez unutmayın.

##  <a name="ondragenter"></a>  CView::OnDragEnter

Fare ilk açılan hedef penceresinin kaydırılmayan bölge girdiğinde framework tarafından çağırılır.

```
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pDataObject*<br/>
İşaret [COleDataObject](../../mfc/reference/coledataobject-class.md) görünümün bırakma alanına sürüklenen.

*dwKeyState*<br/>
Değiştirici tuşları durumunu içerir. Bu, aşağıdaki herhangi bir sayıda birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*Noktası*<br/>
Fare konumunu istemci alanına göre görüntüle.

### <a name="return-value"></a>Dönüş Değeri

DROPEFFECT arasında bir değer türü, kullanıcı, nesneyi bu konumda açtı. varsa, oluşacak bırakma türünü gösteren listelenmiş. Bırakma türü tarafından belirtilen anahtar geçerli durumu genellikle bağımlı *dwKeyState*. Standart eşlemesi aktarıyorsanız DROPEFFECT değerleri şöyledir:

- Bu pencerede veri nesnesi DROPEFFECT_NONE bırakılamaz.

- DROPEFFECT_LINK MK_CONTROL için &#124; MK_SHIFT nesne ve onun sunucusu arasında bir bağlantı oluşturur.

- DROPEFFECT_COPY MK_CONTROL için bırakılan nesnesinin bir kopyasını oluşturur.

- DROPEFFECT_MOVE MK_ALT için bırakılan nesne ve delete orijinal nesnenin bir kopyasını oluşturur. Görünüm bu verisi nesnesini kabul edebilir, bu genellikle varsayılan bırakma etkili olur.

Daha fazla bilgi için bkz. MFC Gelişmiş kavramlar örneği [OCLIENT](../../overview/visual-cpp-samples.md).

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, hiçbir şey yapma ve DROPEFFECT_NONE dönüş sağlamaktır.

Bu işlev gelecekteki çağrılar için hazırlamak için geçersiz kılma [OnDragOver](#ondragover) üye işlevi. Daha sonra kullanmak için şu anda veri nesnesinden gerekli herhangi bir veri alınacağını `OnDragOver` üye işlevi. Görünüm ayrıca kullanıcıya görsel geribildirim vermek için şu anda güncelleştirilmelidir. Daha fazla bilgi için bkz [sürükle ve bırak: Bir bırakma hedefi uygulama](../../mfc/drag-and-drop-implementing-a-drop-target.md).

##  <a name="ondragleave"></a>  CView::OnDragLeave

Fare Bu pencere için geçerli bırakma alanından çıktığında taşındığında bir sürükleme işlemi sırasında framework tarafından çağırılır.

```
virtual void OnDragLeave();
```

### <a name="remarks"></a>Açıklamalar

Geçerli görünümü sırasında gerçekleştirilen tüm eylemler temizlemek gerekiyorsa, bu işlevi geçersiz [OnDragEnter](#ondragenter) veya [OnDragOver](#ondragover) nesne sürüklenebilen ve bırakılan herhangi bir görsel kullanıcı geri bildirim kaldırma gibi çağrılar .

##  <a name="ondragover"></a>  CView::OnDragOver

Bırakma hedefi pencere üzerinde fareyi hareket ettiğinde bir sürükleme işlemi sırasında framework tarafından çağırılır.

```
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pDataObject*<br/>
İşaret [COleDataObject](../../mfc/reference/coledataobject-class.md) bırakma hedefi sürüklenen.

*dwKeyState*<br/>
Değiştirici tuşları durumunu içerir. Bu, aşağıdaki herhangi bir sayıda birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*Noktası*<br/>
Görünüm istemci alanına göre fare geçerli konumu.

### <a name="return-value"></a>Dönüş Değeri

DROPEFFECT arasında bir değer türü, kullanıcı, nesneyi bu konumda açtı. varsa, oluşacak bırakma türünü gösteren listelenmiş. Bırakma türü genellikle tarafından belirtildiği gibi anahtar geçerli durumuna bağlıdır *dwKeyState*. Standart eşlemesi aktarıyorsanız DROPEFFECT değerleri şöyledir:

- Bu pencerede veri nesnesi DROPEFFECT_NONE bırakılamaz.

- DROPEFFECT_LINK MK_CONTROL için &#124; MK_SHIFT nesne ve onun sunucusu arasında bir bağlantı oluşturur.

- DROPEFFECT_COPY MK_CONTROL için bırakılan nesnesinin bir kopyasını oluşturur.

- DROPEFFECT_MOVE MK_ALT için bırakılan nesne ve delete orijinal nesnenin bir kopyasını oluşturur. Görünüm veri nesnesini kabul edebilir, bu genellikle varsayılan bırakma etkili olur.

Daha fazla bilgi için bkz. MFC Gelişmiş kavramlar örneği [OCLIENT](../../overview/visual-cpp-samples.md).

### <a name="remarks"></a>Açıklamalar

Hiçbir şey yapma ve DROPEFFECT_NONE döndürmek için varsayılan uygulamasıdır.

Sürükleme işlemi sırasında kullanıcıya görsel geribildirim vermek için bu işlevi geçersiz kılar. Bu işlev sürekli olarak adlandırılır olduğundan, içerdiği herhangi bir kod mümkün olduğunca hale getirilmiştir. Daha fazla bilgi için bkz [sürükle ve bırak: Bir bırakma hedefi uygulama](../../mfc/drag-and-drop-implementing-a-drop-target.md).

##  <a name="ondragscroll"></a>  CView::OnDragScroll

Çağırmadan önce framework tarafından çağırılır [OnDragEnter](#ondragenter) veya [OnDragOver](#ondragover) noktası kaydırma bölgesinde olup olmadığını belirlemek için.

```
virtual DROPEFFECT OnDragScroll(
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*dwKeyState*<br/>
Değiştirici tuşları durumunu içerir. Bu, aşağıdaki herhangi bir sayıda birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*Noktası*<br/>
İmleç, piksel cinsinden ekranına göre konumunu içerir.

### <a name="return-value"></a>Dönüş Değeri

DROPEFFECT arasında bir değer türü, kullanıcı, nesneyi bu konumda açtı. varsa, oluşacak bırakma türünü gösteren listelenmiş. Bırakma türü tarafından belirtilen anahtar geçerli durumu genellikle bağımlı *dwKeyState*. Standart eşlemesi aktarıyorsanız DROPEFFECT değerleri şöyledir:

- Bu pencerede veri nesnesi DROPEFFECT_NONE bırakılamaz.

- DROPEFFECT_LINK MK_CONTROL için &#124; MK_SHIFT nesne ve onun sunucusu arasında bir bağlantı oluşturur.

- DROPEFFECT_COPY MK_CONTROL için bırakılan nesnesinin bir kopyasını oluşturur.

- DROPEFFECT_MOVE MK_ALT için bırakılan nesne ve delete orijinal nesnenin bir kopyasını oluşturur.

- DROPEFFECT_SCROLL sürükleme kaydırma işlemi gerçekleşmek üzere olan veya hedef Görünümü'nde oluştuğunu gösterir.

Daha fazla bilgi için bkz. MFC Gelişmiş kavramlar örneği [OCLIENT](../../overview/visual-cpp-samples.md).

### <a name="remarks"></a>Açıklamalar

Bu olay için özel davranış sağlamak istediğinizde bu işlev geçersiz kılar. İmleç varsayılan kaydırma bölgesi içinde her Pencere kenarlığını içine sürüklendiğinde varsayılan uygulama, windows otomatik olarak kayar. Daha fazla bilgi için bkz [sürükle ve bırak: Bir bırakma hedefi uygulama](../../mfc/drag-and-drop-implementing-a-drop-target.md).

##  <a name="ondraw"></a>  CView::OnDraw

Belgenin bir görüntüsünü işlemek için framework tarafından çağırılır.

```
virtual void OnDraw(CDC* pDC) = 0;
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Belge bir görüntüsünü işlemek için kullanılacak cihaz bağlamı işaret eder.

### <a name="remarks"></a>Açıklamalar

Framework ekran görüntüsü, yazdırmayı ve baskı önizlemeyi gerçekleştirmek için bu işlevi çağırır ve her durumda farklı bir cihaz bağlamı geçirir. Varsayılan uygulaması yok.

Belgenin görünümünü görüntülemek için bu işlevi geçersiz kılmanız gerekir. Grafik cihaz arabirimi (GDI) çağrıları kullanarak yapabileceğiniz [CDC](../../mfc/reference/cdc-class.md) nesne tarafından işaret edilen *pDC* parametresi. Çizim önce cihaz bağlamına kalemler veya yazı tipleri gibi GDI kaynaklarını'ı seçin ve ardından bunları daha sonra seçimini kaldırın. Genellikle, çizim kodu CİHAZDAN bağımsız olabilir. diğer bir deyişle, cihaz türüne, görüntüyü görüntüleme hakkında bilgi gerek yoktur.

Çizim iyileştirmek için çağrı [RectVisible](../../mfc/reference/cdc-class.md#rectvisible) olup belirtilen bir dikdörtgen çizileceğini bulmak için cihaz bağlamının üye işlevi. Normal bir ekran görüntüsünü ve yazdırma ayırt etmek istiyorsanız, çağrı [IsPrinting](../../mfc/reference/cdc-class.md#isprinting) cihaz bağlamının üye işlevi.

##  <a name="ondrop"></a>  CView::OnDrop

Kullanıcı bir veri nesnesi üzerinde bir geçerli bırakma hedefi bıraktığında framework tarafından çağırılır.

```
virtual BOOL OnDrop(
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

' pDataObject * noktalarına [COleDataObject](../../mfc/reference/coledataobject-class.md) bırakma hedefi bırakıldı.

*dropEffect*<br/>
Kullanıcının istediği bırakma efekti.

- DROPEFFECT_COPY bırakılan veri nesnesinin bir kopyasını oluşturur.

- DROPEFFECT_MOVE veri nesnesi geçerli fare konumuna taşır.

- DROPEFFECT_LINK bir veri nesnesine ve onun sunucusu arasında bir bağlantı oluşturur.

*Noktası*<br/>
Görünüm istemci alanına göre fare geçerli konumu.

### <a name="return-value"></a>Dönüş Değeri

Açılan başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, hiçbir şey yapmaz ve false değerini döndürür.

Bir OLE bırak etkisini görünümün istemci alanına uygulamak için bu işlevi geçersiz kılar. Veri nesnesi aracılığıyla incelenebilir *pDataObject* için Pano veri biçimlerini ve veri belirli bir noktada bırakıldı.

> [!NOTE]
>  Bir geçersiz kılma ise framework bu işlevi çağırmadığı [OnDropEx](#ondropex) , bu görünüm sınıfı.

##  <a name="ondropex"></a>  CView::OnDropEx

Kullanıcı bir veri nesnesi üzerinde bir geçerli bırakma hedefi bıraktığında framework tarafından çağırılır.

```
virtual DROPEFFECT OnDropEx(
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pDataObject*<br/>
İşaret [COleDataObject](../../mfc/reference/coledataobject-class.md) bırakma hedefi bırakıldı.

*dropDefault*<br/>
Geçerli anahtar durumunu temel alan varsayılan bırakma işlemi için kullanıcının seçtiği efekti. DROPEFFECT_NONE olabilir. Bırakma etkileri açıklamalar bölümünde ele alınmıştır.

*Listeyi*<br/>
Bırakma kaynağı destekleyen bırakma etkileri listesi. Bit düzeyinde OR kullanarak doğrudan etkisi değerleri birleştirilebilir ( **&#124;**) işlemi. Bırakma etkileri açıklamalar bölümünde ele alınmıştır.

*Noktası*<br/>
Görünüm istemci alanına göre fare geçerli konumu.

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen konumda bırakma denemesi kullanmasından bırakma etkisi *noktası*. Bu tarafından belirtilen değerlerden biri olmalıdır *dropEffectList*. Bırakma etkileri açıklamalar bölümünde ele alınmıştır.

### <a name="remarks"></a>Açıklamalar

Hiçbir şey yapma ve framework çağırmalıdır belirtmek için bir kukla değer (-1) döndürmek için varsayılan uygulamasıdır [OnDrop](#ondrop) işleyici.

Bu işlev bir sağ fare düğmesi sürükle ve bırak etkisini uygulamak için geçersiz kılın. Sağ fare düğmesi sürükle ve bırak genellikle bir menü görüntüler seçenekler sağ fare düğmesi bırakıldığında.

Kılacağınızı `OnDropEx` sağ fare düğmesi için sorgu. Çağırabilirsiniz [GetKeyState](/windows/desktop/api/winuser/nf-winuser-getkeystate) veya sağ fare düğmesi durumundan depolamak, [OnDragEnter](#ondragenter) işleyici.

- Sağ fare düğmesi kapalı ise, geçersiz kılma bırakma kaynağı tarafından açılan etkileri desteği sunan bir açılan menü görüntülemelidir.

   - İnceleme *listeyi* bırakma kaynağı tarafından desteklenen bırakma etkilerini belirlemek için. Yalnızca bu eylemler açılan menüsünde etkinleştirin.

   - Kullanım [SetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-setmenudefaultitem) dayalı olarak varsayılan eylem ayarlanacak *dropDefault*.

   - Son olarak, açılan menüden kullanıcı seçimine tarafından belirtilen eylemi gerçekleştirin.

- Geçersiz kılma sağ fare düğmesi aşağı değilse, bu standart bırakma istek olarak işlemelisiniz. Belirtilen bırakma efekti kullanmak *dropDefault*. Alternatif olarak, geçersiz kılma göstermek için kukla değer (-1) döndürebilir `OnDrop` bu bırakma işlemi işler.

Kullanım *pDataObject* incelemek için `COleDataObject` için Pano verileri biçimi ve veri belirli bir noktada bırakıldı.

Bir bırakma işlemi ile ilişkili eylemi açılan etkileri açıklanmaktadır. Bırakma etkileri aşağıdaki listeye bakın:

- DROPEFFECT_NONE bırakma izin.

- DROPEFFECT_COPY bir kopyalama işlemi gerçekleştirilmesi.

- DROPEFFECT_MOVE bir taşıma işlemi gerçekleştirilmesi.

- Özgün veriler bırakılan verilerden DROPEFFECT_LINK bir bağlantı kurulabilir.

- DROPEFFECT_SCROLL sürükleme kaydırma işlemi gerçekleşmek üzere olan veya hedef oluştuğunu gösterir.

Varsayılan menü komutu hakkında daha fazla bilgi için bkz. [SetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-setmenudefaultitem) Windows SDK ve [CMenu::GetSafeHmenu](../../mfc/reference/cmenu-class.md#getsafehmenu) bu toplu.

##  <a name="onendprinting"></a>  CView::OnEndPrinting

Bir belge yazdırıldığında ya da önizlendiğinde sonra framework tarafından çağırılır.

```
virtual void OnEndPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Yazıcı cihaz bağlamı işaret eder.

*pInfo*<br/>
İşaret eden bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) geçerli yazdırma işi açıklayan yapısı.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulama, hiçbir şey yapmaz. Bu işlev, ayrılmış GDI kaynakları serbest bırakmak için geçersiz kılma [OnBeginPrinting](#onbeginprinting) üye işlevi.

##  <a name="onendprintpreview"></a>  CView::OnEndPrintPreview

Kullanıcı yazdırma Önizleme modundan çıktığında framework tarafından çağırılır.

```
virtual void OnEndPrintPreview(
    CDC* pDC,
    CPrintInfo* pInfo,
    POINT point,
    CPreviewView* pView);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Yazıcı cihaz bağlamı işaret eder.

*pInfo*<br/>
İşaret eden bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) geçerli yazdırma işi açıklayan yapısı.

*Noktası*<br/>
En son önizleme modunda görüntülenen sayfadaki noktasını belirtir.

*pView*<br/>
Önizleme için kullanılan view nesnesinin işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan uygulamasını çağırır [OnEndPrinting](#onendprinting) üye işlevi ve geri yükler, bu önce Baskı önizlemeyi duruma ana çerçeve penceresinin başladı. Önizleme modunu sonlandırıldığında özel işlem gerçekleştirmek için bu işlevi geçersiz kılar. Önizleme modundan normal görüntüleme moduna geçerken kullanıcının belge içindeki konumunu korumak istiyorsanız, örneğin, tarafından açıklanan bir konuma kaydırma *noktası* parametresi ve `m_nCurPage` üyesi`CPrintInfo` , yapı *pInfo* parametresi işaret eder.

Her zaman temel sınıf sürümü çağrı `OnEndPrintPreview` genellikle işlevi sonunda geçersiz kılma, gelen.

##  <a name="oninitialupdate"></a>  CView::OnInitialUpdate

Görünüm ilk belgeye eklendikten sonra ancak görünüm başlangıçta görüntülenmeden önce framework tarafından çağırılır.

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan uygulamasını çağırır [OnUpdate](#onupdate) üye işlev hiçbir ipucu bilgilerle (diğer bir deyişle, varsayılan değerleri için 0'ı kullanarak *lHint* parametre ve NULL  *pHint* parametresi). Bu işlev, belge hakkındaki bilgileri gerektiren herhangi bir kez başlatma gerçekleştirmek için geçersiz kılın. Örneğin, uygulamanızın sabit boyutlu belgeleri varsa, belge boyutunu temel alan bir görünümün kaydırma limitleri başlatmak için bu işlevi kullanabilirsiniz. Uygulamanızın değişken boyutlu belgeleri destekliyorsa [OnUpdate](#onupdate) kaydırma güncelleştirilecek limitleri her zaman belge değişiklikleri.

##  <a name="onpreparedc"></a>  CView::OnPrepareDC

Önce framework tarafından çağırılır [OnDraw](#ondraw) ekran görüntüsünü ve önce üye işlevi çağrıldığında [OnPrint](#onprint) üye işlevi, her sayfa için yazdırma ya da yazdırma önizleme sırasında çağrılır.

```
virtual void OnPrepareDC(
    CDC* pDC,
    CPrintInfo* pInfo = NULL);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Belge bir görüntüsünü işlemek için kullanılacak cihaz bağlamı işaret eder.

*pInfo*<br/>
İşaret eden bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) geçerli yazdırma işinin olmadığını açıklayan yapısı `OnPrepareDC` yazdırma ya da yazdırma önizleme; adlı `m_nCurPage` üye hakkında yazdırılacak sayfayı belirtir. Bu parametre NULL ise `OnPrepareDC` ekran görüntüsü için çağrılır.

### <a name="remarks"></a>Açıklamalar

Ekran görüntüsü için işlev çağrılırsa, bu işlevin varsayılan uygulama, hiçbir şey yapmaz. Ancak, bu işlevi türetilmiş sınıflarda gibi geçersiz kılınır [CScrollView](../../mfc/reference/cscrollview-class.md), cihaz bağlamının; öznitelikleri ayarlamak için sonuç olarak, her zaman temel sınıf uygulamasına geçersiz kılma başında çağırmalısınız.

Yazdırma için işlev çağrılırsa, varsayılan uygulama depolanan sayfa bilgileri inceler *pInfo* parametresi. Belgenin uzunluğunu belirtilmediği takdirde `OnPrepareDC` uzun bir sayfası gibi belge varsayar ve bir sayfa yazdırılan sonra yazdırma döngü durdurur. İşlev ayarlayarak yazdırma döngü durdurur `m_bContinuePrinting` false yapısının üyesi.

Geçersiz kılma `OnPrepareDC` herhangi biri:

- Cihaz bağlamı özniteliklerini belirtilen sayfa için gerektiği şekilde ayarlamak için. Örneğin, eşleme modunu veya cihaz bağlamı diğer özelliklerini ayarlamak gerekiyorsa, bunu Bu işlevde harcanan yapın.

- Yazdırma zamanı sayfalandırma gerçekleştirilecek. Normalde yazdırma başladığında kullanarak belgenin uzunluğunu belirtmek [OnPreparePrinting](#onprepareprinting) üye işlevi. Ancak, bilmiyorsanız önceden ne kadar belge (örneğin, belirsiz bir kayıt sayısı bir veritabanından yazdırırken), geçersiz kılma `OnPrepareDC` bunu yazdırılırken belgenin sonuna için test etmek için. Olduğunda yazdırılması belgenin artık, ayarlama `m_bContinuePrinting` üyesi `CPrintInfo` yapısı false.

- Sayfa sayfa başına yazıcı atlatma kodları göndermek için. Çıkış kodlarından göndermek için `OnPrepareDC`, çağrı `Escape` üye işlevinin *pDC* parametresi.

Temel sınıf sürümü çağrı `OnPrepareDC` geçersiz kılma başında.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#183](../../mfc/codesnippet/cpp/cview-class_1.cpp)]

##  <a name="onprepareprinting"></a>  CView::OnPreparePrinting

Bir belge yazdırılmadan ya da önizlenmeden önce framework tarafından çağırılır.

```
virtual BOOL OnPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*pInfo*<br/>
İşaret eden bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) geçerli yazdırma işi açıklayan yapısı.

### <a name="return-value"></a>Dönüş Değeri

Yazdırma başlamak için sıfır olmayan; 0 yazdırma işi iptal edildi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, hiçbir şey yapmaz.

Yazdırmayı ve baskı önizlemeyi etkinleştirmek için bu işlevi geçersiz kılmanız gerekir. Çağrı [DoPreparePrinting](#doprepareprinting) iletmeden üye işlevini *pInfo* parametre ve dönüş değeri; dönün `DoPreparePrinting` Yazdır iletişim kutusunu görüntüler ve yazıcı cihaz bağlamı oluşturur. Yazdır iletişim kutusu varsayılan dışındaki değerler ile başlatmak istiyorsanız, üyelerine atayabilmeniz *pInfo*. Belgenin uzunluğunu biliyorsanız, örneğin, değerine geçirin [SetMaxPage](../../mfc/reference/cprintinfo-structure.md#setmaxpage) üye işlevinin *pInfo* çağırmadan önce `DoPreparePrinting`. Bu değer Kime görüntülenir: Yazdır iletişim kutusunu aralığı kısmında kutusu.

`DoPreparePrinting` Yazdır iletişim kutusunu bir önizleme iş için görüntülemez. Bir yazdırma işinin yazdırma iletişim kutusu atlamak istiyorsanız, bu maddeyi `m_bPreview` üyesi *pInfo* yanlış ve sonra TRUE öğesine iletmeden önce ayarlayın `DoPreparePrinting`; FALSE sonradan sıfırlayın.

Erişmesi başlatmaların ihtiyacınız varsa `CDC` (örneğin, sayfa boyutu belgenin uzunluğunu belirtmeden önce bilmeniz gereken,), yazıcı cihaz bağlamı temsil eden nesne geçersiz kılma `OnBeginPrinting` üyesi işlev.

Değerini ayarlamak istiyorsanız `m_nNumPreviewPages` veya `m_strPageDesc` üyeleri *pInfo* parametresi çağırdıktan sonra bunu `DoPreparePrinting`. `DoPreparePrinting` Üye işlev kümeleri `m_nNumPreviewPages` için uygulamanın bulunan değeri. INI dosya ve ayarlar `m_strPageDesc` varsayılan değerine.

### <a name="example"></a>Örnek

  Geçersiz kılma `OnPreparePrinting` ve çağrı `DoPreparePrinting` geçersiz kılma gelen framework Yazdır iletişim kutusunu görüntülemek ve sizin için bir yazıcı DC oluşturun.

[!code-cpp[NVC_MFCDocView#184](../../mfc/codesnippet/cpp/cview-class_2.cpp)]

Belgeyi içeren kaç sayfaları biliyorsanız, en fazla sayfa kümesinde `OnPreparePrinting` çağırmadan önce `DoPreparePrinting`. Framework Yazdır iletişim kutusu "için" kutusuna en fazla sayfa sayısını görüntüler.

[!code-cpp[NVC_MFCDocView#185](../../mfc/codesnippet/cpp/cview-class_3.cpp)]

##  <a name="onprint"></a>  CView::OnPrint

Belgenin bir sayfasını yazdıramaz veya framework tarafından çağırılır.

```
virtual void OnPrint(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Yazıcı cihaz bağlamı işaret eder.

*pInfo*<br/>
İşaret eden bir `CPrintInfo` geçerli yazdırma işi açıklayan yapısı.

### <a name="remarks"></a>Açıklamalar

Yazdırılmasını her sayfa için framework bu işlevi çağırdıktan hemen sonra çağıran [OnPrepareDC](#onpreparedc) üye işlevi. Yazdırılan sayfanın tarafından belirtilen `m_nCurPage` üyesi [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) , yapı *pInfo* işaret eder. Varsayılan Uygulama çağrıları [OnDraw](#ondraw) üye işlevi ve yazıcı cihaz bağlamı geçirir.

Bu işlev, aşağıdaki nedenlerden biriyle geçersiz kıl:

- Birden çok belge yazdırma izin verme. Yalnızca şu anda yazdırılmasını sayfasına karşılık gelen bir belge bölümü işleyin. Kullanıyorsanız `OnDraw` yalnızca uygun kısmını serileştirmeniz yazdırılması işleme gerçekleştirmek için Görünüm penceresi kaynak ayarlayabilirsiniz.

- Yazdırılan görüntünün (diğer bir deyişle, uygulamanızın WYSIWYG değilse) ekran görüntüsünden farklı görünmesini sağlamak için. Cihaz bağlamına yazıcı geçirmek yerine `OnDraw`, ekranda gösterilen değil öznitelikleri kullanarak bir görüntüsünü işlemek için cihaz bağlamı kullanma.

   GDI kaynaklarını ekran görüntüsü için kullanmayın yazdırma için gerekiyorsa, bunları çizim önce cihaz bağlamına seçin ve ardından seçimini kaldırın. Bu GDI kaynaklarını ayrılması gereken [OnBeginPrinting](#onbeginprinting) ve yayımlanan [OnEndPrinting](#onendprinting).

- Üstbilgilerinde veya altbilgilerinde uygulamak için. Kullanmaya devam edebilirsiniz `OnDraw` üzerinde yazdırabilir alan kısıtlayarak işleme yapmak için.

Unutmayın `m_rectDraw` üyesi *pInfo* parametre mantıksal birimler cinsinden sayfa yazdırılabilir alanı açıklar.

Çağırmayın `OnPrepareDC` kılacağınızı içinde `OnPrint`; framework çağrıları `OnPrepareDC` çağırmadan önce otomatik olarak `OnPrint`.

### <a name="example"></a>Örnek

Bir geçersiz kılınan bir çatısı aşağıda verilmiştir `OnPrint` işlevi:

[!code-cpp[NVC_MFCDocView#186](../../mfc/codesnippet/cpp/cview-class_4.cpp)]

Başka bir örnek için bkz: [CRichEditView::PrintInsideRect](../../mfc/reference/cricheditview-class.md#printinsiderect).

##  <a name="onscroll"></a>  CView::OnScroll

Kaydırma olup olmadığını belirlemek için framework tarafından çağırılır mümkündür.

```
virtual BOOL OnScroll(
    UINT nScrollCode,
    UINT nPos,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parametreler

*nScrollCode*<br/>
Kullanıcı gösteren bir kaydırma çubuğu kodu istek kaydırma. Bu parametre, iki bölümden oluşur: yatay kaydırma gerçekleşen türünü belirleyen bir alt sıra bayt ve dikey kaydırma gerçekleşen türünü belirleyen bir yüksek düzeyli bayt:

- Yukarıdan aşağıya SB_BOTTOM kaydırır.

- Bir satır aşağı SB_LINEDOWN kaydırır.

- Bir satır yukarı SB_LINEUP kaydırır.

- Bir sayfa aşağı SB_PAGEDOWN kaydırır.

- Bir sayfa yukarı SB_PAGEUP kaydırır.

- SB_THUMBTRACK etkileyen kutusunda belirtilen konuma gidin. Geçerli konumun belirtildiğinden *nPos*.

- En üste SB_TOP kaydırır.

*nPos*<br/>
Kaydırma çubuğu kodu SB_THUMBTRACK ise geçerli kaydırma kutusunun konumunu içerir. Aksi takdirde bu kullanılmaz. İlk kaydırma aralığı bağlı olarak *nPos* atamanız gerekir ve negatif bir **int** gerekirse.

*bDoScroll*<br/>
Belirtilen kayan eylem gerçekten yapmanız gerektiğini olup olmadığını belirler. TRUE ise, kaydırma sonra gerçekleşmesi gereken; FALSE ise, ardından kaydırma oluşmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

Varsa *bDoScroll* true'dur ve görünüm gerçekten kaydırılan, sıfır; Aksi takdirde iade 0. Varsa *bDoScroll* FALSE, ardından return, iade değer olduğu *bDoScroll* kaydırma gerçekten uygulamayın olsa da TRUE olan.

### <a name="remarks"></a>Açıklamalar

Framework tarafından bir durumda bu işlev çağrılır *bDoScroll* görünümü bir kaydırma çubuğu ileti aldığında, TRUE olarak ayarlayın. Bu durumda, aslında görünüme gitmeniz gerekir. Bu işlev çağrılır başka bir durumda *bDoScroll* kaydırma gerçekleşmeden önce bir OLE öğesini bir bırakma hedefi otomatik kaydırmayı bölgeye başlangıçta sürüklendiğinde FALSE olarak ayarlayın. Bu durumda, aslında görünüme gitmeniz gerekir değil.

##  <a name="onscrollby"></a>  CView::OnScrollBy

Kullanıcı mevcut belge ya da OLE öğesini karşı görünümün geçerli kenarlıkları sürükleyerek veya dikey veya yatay kaydırma çubukları düzenleme görünümünü ötesinde bir alana görüntülediğinde framework tarafından çağırılır.

```
virtual BOOL OnScrollBy(
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parametreler

*sizeScroll*<br/>
Piksel sayısı, yatay ve dikey olarak kaydırılan.

*bDoScroll*<br/>
Görünüm kaydırma oluşup oluşmadığını belirler. TRUE ise, ardından kaydırma yerini alır; FALSE ise, ardından kaydırma gerçekleşmez.

### <a name="return-value"></a>Dönüş Değeri

Görünüm kaydırılan mümkün olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Türetilen sınıflarda bu yöntemi görünümü kullanıcı istenen ve daha sonra gerekirse yeni bölge güncelleştirir yönde kaydırılabilir olup olmadığını denetler. Bu işlev otomatik olarak çağıran [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) ve [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) gerçek kayan isteği gerçekleştirmek için.

Bu yöntem varsayılan uygulaması, görünüm değiştirmez, ancak görünümü içinde Kaymaz çağrılmazsa, bir `CScrollView`-türetilmiş sınıf.

Belge genişliği veya yüksekliği 32767 piksel aşıyor, 32767 kaydırma nedeniyle başarısız olur `OnScrollBy` geçersiz bir adlı *sizeScroll* bağımsız değişken.

##  <a name="onupdate"></a>  CView::OnUpdate

Görünümün belge değiştirildikten sonra framework tarafından çağırılır; Bu işlevi çağıran [CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) ve bu değişiklikleri yansıtacak şekilde görünümünü güncelleştirmek görünümü sağlar.

```
virtual void OnUpdate(
    CView* pSender,
    LPARAM lHint,
    CObject* pHint);
```

### <a name="parameters"></a>Parametreler

*pSender*<br/>
Dokument görünümüne işaret eden veya tüm görünümlerin güncelleştirilmesi gerekmeyen yoksa NULL.

*lHint*<br/>
Değişiklikler hakkında bilgiler içerir.

*pHint*<br/>
Değişiklikler hakkında bilgi depolamak için bir nesneye işaret eder.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulaması tarafından çağrılır [OnInitialUpdate](#oninitialupdate). Varsayılan uygulama sonraki WM_PAINT iletisini aldığınızda boyama için işaretleme. tüm istemci alanını geçersiz kılar. Belgenin değiştirilmiş bölümleri için eşlenen bölgeleri güncelleştirmek istiyorsanız, bu işlev geçersiz kılar. Bunu yapmak için ipucu parametreleri kullanarak değişiklikler hakkında bilgi geçmesi gerekir.

Kullanılacak *lHint*özel ipucu değerler, genellikle bir bit maskesi veya bir listeden seçimli türü tanımlamak ve şu değerlerden biri olarak geçirmek belgemiz vardır. Kullanılacak *pHint*, bir ipucu sınıfından türetilir [CObject](../../mfc/reference/cobject-class.md) ve belgenin bir işaretçi bir ipucu nesnesine; geçersiz kılarken geçirmek `OnUpdate`, kullanın [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) İpucu nesnenin çalışma zamanı türünü belirlemek için üye işlevi.

Genellikle, herhangi bir doğrudan çizim gerçekleştirmemelisiniz `OnUpdate`. Bunun yerine, açıklayan, cihaz koordinatlarında güncelleştirilmesi alanı dikdörtgeni belirlemek; Bu dikdörtgene geçirmek [CWnd::InvalidateRect](../../mfc/reference/cwnd-class.md#invalidaterect). Bu boyama sonraki oluşmasına neden olan bir [WM_PAINT](/windows/desktop/gdi/wm-paint) iletisi aldı.

Varsa *lHint* 0'dır ve *pHint* null, belge genel güncelleştirme bildirim gönderdi. Bir görünüm genel güncelleştirme bildirim aldığında veya ipucu çözülemiyor, onun tüm istemci alanını geçersiz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[CSplitterWnd Sınıfı](../../mfc/reference/csplitterwnd-class.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[CDocument Sınıfı](../../mfc/reference/cdocument-class.md)
