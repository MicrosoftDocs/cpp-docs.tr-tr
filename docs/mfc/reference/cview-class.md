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
ms.openlocfilehash: f6be846e80209ce94c84222d61c37a7964baad03
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127515"
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
|[CView:: CView](#cview)|`CView` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CView::D oPreparePrinting](#doprepareprinting)|Yazdır iletişim kutusunu görüntüler ve yazıcı cihaz bağlamı oluşturur; `OnPreparePrinting` üye işlevini geçersiz kılarken çağırın.|
|[CView:: GetDocument](#getdocument)|Görünümle ilişkili belgeyi döndürür.|
|[CView:: IsSelected](#isselected)|Bir belge öğesinin seçili olup olmadığını sınar. OLE desteği için gereklidir.|
|[CView:: OnDragEnter](#ondragenter)|Bir öğe bir görünümün sürükle ve bırak bölgesine ilk kez sürüklendiğinde çağırılır.|
|[CView:: OnDragLeave](#ondragleave)|Sürüklenen bir öğe bir görünümün sürükle ve bırak bölgesinden ayrıldığında çağırılır.|
|[CView:: Ondragon](#ondragover)|Bir öğe bir görünümün sürükle ve bırak bölgesinin üzerine sürüklendiğinde çağırılır.|
|[CView:: OnDragScroll](#ondragscroll)|İmlecin pencerenin kaydırma bölgesine sürüklenip sürüklamayacağını anlamak için çağırılır.|
|[CView:: OnDrop](#ondrop)|Bir öğe bir görünüm, varsayılan işleyicinin sürükle ve bırak bölgesine bırakıldığında çağırılır.|
|[CView:: OnDropEx](#ondropex)|Bir öğe bir görünümün sürükle ve bırak bölgesine bırakıldığında çağırılır, birincil işleyici.|
|[CView:: OnInitialUpdate](#oninitialupdate)|Bir görünüm belgeye ilk eklendikten sonra çağırılır.|
|[CView:: Onhazırlık EDC](#onpreparedc)|Ekran görüntüleme için `OnDraw` üye işlevi çağrılmadan önce veya yazdırma veya baskı önizleme için `OnPrint` üye işlevi çağrıldığında çağırılır.|
|[CView:: OnScroll](#onscroll)|OLE öğeleri görünümün kenarlıklarının dışına sürüklendiğinde çağırılır.|
|[CView:: OnScrollBy](#onscrollby)|Etkin bir yerinde OLE öğeleri içeren bir görünüm kaydırıldığında çağırılır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CView:: OnActivateFrame](#onactivateframe)|Görünümü içeren çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında çağırılır.|
|[CView:: OnActivateView](#onactivateview)|Bir görünüm etkinleştirildiğinde çağırılır.|
|[CView:: OnBeginPrinting](#onbeginprinting)|Bir yazdırma işi başladığında çağırılır; grafik cihaz arabirimi (GDI) kaynaklarını ayırmak için geçersiz kılın.|
|[CView:: OnDraw](#ondraw)|Ekran görüntüleme, yazdırma veya baskı önizleme için belgenin bir görüntüsünü işlemek üzere çağırılır. Uygulama gerekiyor.|
|[CView:: OnEndPrinting](#onendprinting)|Bir yazdırma işi sona erdiğinde çağırılır; GDI kaynaklarını serbest bırakmak için geçersiz kılın.|
|[CView:: OnEndPrintPreview](#onendprintpreview)|Önizleme moduna çıkıldığında çağırılır.|
|[CView:: OnPreparePrinting](#onprepareprinting)|Belge yazdırılmadan ya da önizlenmeden önce çağırılır; Yazdır iletişim kutusunu başlatmak için geçersiz kılın.|
|[CView:: OnPrint](#onprint)|Belgenin bir sayfasını yazdırmak ya da önizlemek için çağırılır.|
|[CView:: OnUpdate](#onupdate)|Belgenin değiştirildiğini bir görünüme bildirmek için çağırılır.|

## <a name="remarks"></a>Açıklamalar

Bir görünüm belgeye iliştirilir ve belge ve Kullanıcı arasında bir aracı görevi görür: görünüm, ekranda veya yazıcıda belgenin bir görüntüsünü oluşturur ve Kullanıcı girişini belge üzerinde işlemler olarak yorumlar.

Görünüm bir çerçeve penceresinin alt öğesidir. Ayırıcı pencere durumunda olduğu gibi, birden fazla görünüm bir çerçeve penceresini paylaşabilir. Bir görünüm sınıfı, bir çerçeve pencere sınıfı ve bir belge sınıfı arasındaki ilişki `CDocTemplate` nesne tarafından oluşturulur. Kullanıcı yeni bir pencere açtığında veya var olanı böler, çerçeve yeni bir görünüm oluşturur ve belgeyi belgeye ekler.

Bir görünüm yalnızca bir belgeye iliştirilebilir, ancak bir belgeye birden çok görünüm eklenmiş olabilir. Örneğin, belge bir Splitter penceresinde veya birden fazla belge arabirimi (MDI) uygulamasında birden çok alt pencere halinde görüntüleniyorsa. Uygulamanız, belirli bir belge türü için farklı görünüm türlerini destekleyebilir; Örneğin, bir sözcük işleme programı bir belgenin tam metin görünümünü ve yalnızca bölüm başlıklarının gösterildiği bir anahat görünümünü sağlayabilir. Ayırıcı pencere kullanıyorsanız, bu farklı görünüm türleri ayrı çerçeve pencereleri veya tek bir çerçeve penceresinin ayrı bölmelerinde yerleştirilebilir.

Bir görünüm, klavye girişi, fare giriş veya giriş, sürükleme ve bırakma aracılığıyla menü, araç çubukları veya kaydırma çubuklarının komutları gibi çeşitli farklı giriş türlerini işlemekten sorumlu olabilir. Bir görünüm, kendi çerçeve penceresi tarafından iletilen komutları alır. Görünüm belirli bir komutu işlemezse, komutu ilişkili belgesine iletir. Tüm komut hedefleri gibi, bir görünüm iletileri bir ileti eşlemesi aracılığıyla işler.

Görünüm, belgenin verilerini görüntüleme ve değiştirme işleminden sorumludur ancak depolanmıyor. Belge, görünümü, verileri hakkında gerekli ayrıntıları sağlar. Görünümün belgenin veri üyelerine doğrudan erişmesine izin verebilir veya bir görünüm sınıfının çağırabilmeniz için belge sınıfında üye işlevleri sağlayabilirsiniz.

Bir belgenin verileri değiştiğinde, değişikliklerden sorumlu olan görünüm genellikle belge için [CDocument:: UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) işlevini çağırır, bu da her biri için `OnUpdate` üye işlevini çağırarak diğer tüm görünümlere bildirir. `OnUpdate` varsayılan uygulama, görünümün tüm istemci alanını geçersiz kılar. Yalnızca belgenin değiştirilen bölümlerine eşlenen istemci alanının bölgelerini geçersiz kılmak için bunu geçersiz kılabilirsiniz.

`CView`kullanmak için, bundan bir sınıf türetirsiniz ve ekran görüntüsünü gerçekleştirmek için `OnDraw` üye işlevini uygulayın. Yazdırma ve baskı önizleme işlemleri gerçekleştirmek için `OnDraw` de kullanabilirsiniz. Çerçeve, belgenizin yazdırılması ve önizlemesini görüntülemek için yazdırma döngüsünü işler.

Bir görünüm, [CWnd:: OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) ve [CWnd:: OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) üye işlevlerini içeren kaydırma çubuğu iletilerini işler. Bu işlevlerde kaydırma çubuğu ileti işleme uygulayabilir veya `CView` türetilmiş sınıf [CScrollView](../../mfc/reference/cscrollview-class.md) kullanarak sizin için kaydırmayı idare edebilirsiniz.

`CScrollView`yanı sıra, Microsoft Foundation Class Kitaplığı `CView`türetilmiş dokuz farklı sınıf sağlar:

- Ağaç, liste ve zengin düzenleme denetimleriyle belge görünümü mimarisinin kullanılmasına izin veren bir görünüm olan [CCtrlView](../../mfc/reference/cctrlview-class.md).

- [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md), veritabanı kayıtlarını iletişim kutusu denetimlerinde görüntüleyen bir görünüm.

- [CEditView](../../mfc/reference/ceditview-class.md), basit bir çok satırlı metin Düzenleyicisi sağlayan bir görünüm. Bir `CEditView` nesnesini bir iletişim kutusunda denetim olarak ve bir belgedeki görünümü kullanabilirsiniz.

- [CFormView](../../mfc/reference/cformview-class.md), iletişim kutusu denetimlerini içeren ve bir iletişim kutusu şablon kaynağını temel alan kaydırılabilir bir görünüm.

- Liste denetimleriyle belge görünümü mimarisinin kullanılmasına izin veren bir görünüm olan [Clienstview](../../mfc/reference/clistview-class.md).

- [](../../mfc/reference/crecordview-class.md)İletişim kutusu denetimlerinde veritabanı kayıtlarını görüntüleyen bir görünüm.

- [CRichEditView](../../mfc/reference/cricheditview-class.md), zengin düzenleme denetimleriyle belge görünümü mimarisinin kullanılmasına izin veren bir görünüm.

- [CScrollView](../../mfc/reference/cscrollview-class.md), otomatik olarak kaydırma desteği sağlayan bir görünüm.

- [CTreeView](../../mfc/reference/ctreeview-class.md), ağaç denetimleriyle belge görünümü mimarisinin kullanılmasına izin veren bir görünüm.

`CView` sınıfı ayrıca, baskı önizleme gerçekleştirmek için Framework tarafından kullanılan `CPreviewView`adlı türetilmiş bir uygulama sınıfına sahiptir. Bu sınıf, bir araç çubuğu, tek veya çift sayfalı Önizleme gibi yazdırma-önizleme penceresine özgü özellikler için destek sağlar, yani Önizlemesi görüntülenen görüntüyü büyütme. Yazdırma önizlemesi için kendi arabiriminizi uygulamak istemiyorsanız (örneğin, baskı önizleme modunda düzenlemenizi desteklemek istiyorsanız) `CPreviewView`üye işlevlerini çağırmanız veya geçersiz kılmanız gerekmez. `CView`kullanma hakkında daha fazla bilgi için bkz. [belge/görünüm mimarisi](../../mfc/document-view-architecture.md) ve [yazdırma](../../mfc/printing.md). Ayrıca, Baskı Önizlemeyi özelleştirme hakkında daha fazla bilgi için bkz. [Teknik İnceleme 30](../../mfc/tn030-customizing-printing-and-print-preview.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="cview"></a>CView:: CView

`CView` nesnesi oluşturur.

```
CView();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, yeni bir çerçeve penceresi oluşturulduğunda veya pencere bölündüğünde oluşturucuyu çağırır. Belge eklendikten sonra görünümü başlatmak için [OnInitialUpdate](#oninitialupdate) üye işlevini geçersiz kılın.

##  <a name="doprepareprinting"></a>CView::D oPreparePrinting

Yazdır iletişim kutusunu çağırmak ve bir yazıcı cihaz bağlamı oluşturmak için [OnPreparePrinting](#onprepareprinting) 'in geçersiz kılmada bu işlevi çağırın.

```
BOOL DoPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*pInfo*<br/>
Geçerli yazdırma işini açıklayan bir [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Yazdırma veya baskı önizleme başlayamazsa sıfır dışı; işlem iptal edildiyse 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin davranışı, yazdırma veya Baskı Önizleme ( *pInfo* parametresinin `m_bPreview` üyesi tarafından belirtilen) için çağırıldığınıza bağlıdır. Bir dosya yazdırıldıysa, bu işlev, *pInfo* 'ın Işaret ettiği [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısındaki değerleri kullanarak Yazdır iletişim kutusunu çağırır; Kullanıcı iletişim kutusunu kapattıktan sonra, işlev iletişim kutusunda belirtilen kullanıcı ayarlarına bağlı olarak bir yazıcı cihaz bağlamı oluşturur ve bu cihaz bağlamını *pInfo* parametresi aracılığıyla döndürür. Bu cihaz bağlamı belgeyi yazdırmak için kullanılır.

Bir dosyanın önizlemesi varsa, bu işlev geçerli yazıcı ayarlarını kullanarak bir yazıcı cihaz bağlamı oluşturur; Bu cihaz bağlamı, önizleme sırasında yazıcının benzetimini yapmak için kullanılır.

##  <a name="getdocument"></a>CView:: GetDocument

Görünümün belgesine bir işaretçi almak için bu işlevi çağırın.

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görünümle ilişkili [CDocument](../../mfc/reference/cdocument-class.md) nesnesine yönelik bir işaretçi. Görünüm bir belgeye iliştirilmişse NULL.

### <a name="remarks"></a>Açıklamalar

Bu, belgenin üye işlevlerini çağıralmanıza olanak sağlar.

##  <a name="isselected"></a>CView:: IsSelected

Belirtilen belge öğesinin seçili olup olmadığını denetlemek için Framework tarafından çağırılır.

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>Parametreler

*pDocItem*<br/>
Sınanmakta olan belge öğesine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen belge öğesi seçildiyse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulamasında FALSE değeri döndürülür. [CDocItem](../../mfc/reference/cdocitem-class.md) nesnelerini kullanarak seçimi uyguladığınızda bu işlevi geçersiz kılın. Görünümlerinizin OLE öğeleri içermesi durumunda bu işlevi geçersiz kılmalısınız.

##  <a name="onactivateframe"></a>CView:: OnActivateFrame

Görünümü içeren çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında Framework tarafından çağırılır.

```
virtual void OnActivateFrame(
    UINT nState,
    CFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>Parametreler

*nDurum*<br/>
Çerçeve penceresinin etkinleştirilip etkinleştirilmediğini veya devre dışı bırakıldığını belirtir. Aşağıdaki değerlerden biri olabilir:

- Çerçeve penceresi devre dışı WA_INACTIVE.

- WA_ACTIVE çerçeve penceresi fare tıklaması dışında bazı yöntemler aracılığıyla etkinleştiriliyor (örneğin, pencereyi seçmek için klavye arabirimi kullanılarak).

- WA_CLICKACTIVE çerçeve penceresi fare tıklaması tarafından etkinleştiriliyor

*pFrameWnd*<br/>
Etkinleştirilecek çerçeve penceresine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Görünümle ilişkili çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında özel işlem gerçekleştirmek istiyorsanız bu üye işlevini geçersiz kılın. Örneğin, [CFormView](../../mfc/reference/cformview-class.md) , odağa sahip olan denetimi kaydettiğinde ve geri yüklediğinde bu geçersiz kılma işlemini gerçekleştirir.

##  <a name="onactivateview"></a>CView:: OnActivateView

Bir görünüm etkinleştirildiğinde veya devre dışı bırakıldığında Framework tarafından çağırılır.

```
virtual void OnActivateView(
    BOOL bActivate,
    CView* pActivateView,
    CView* pDeactiveView);
```

### <a name="parameters"></a>Parametreler

*Bacetkinleştir*<br/>
Görünümün etkinleştirildiğini veya devre dışı bırakıldığını gösterir.

*pActivateView*<br/>
Etkinleştirilmekte olan görünüm nesnesine işaret eder.

*pDeactiveView*<br/>
Devre dışı bırakılmakta olan görünüm nesnesine işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması, odağı etkinleştirilmekte olan görünüme ayarlar. Bir görünüm etkinleştirildiğinde veya devre dışı bırakıldığında özel işlem gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın. Örneğin, etkin görünümü etkin olmayan görünümlerden ayırt eden özel görsel ipuçları sağlamak istiyorsanız, *bacıaktif* parametresini inceleyerek görünümün görünümünü buna göre güncelleştirmeniz gerekir.

*PActivateView* ve *pDeactiveView* parametreleri, etkin görünümde hiçbir değişiklik yapmadan uygulamanın ana çerçevesi penceresi etkinleştirilmişse aynı görünüme işaret ediyor — Örneğin, odak başka bir uygulamadan, uygulamadaki başka BIR görünümden diğerine veya MDI alt pencereleri arasında geçiş yaparken değil, bu bir uygulamadan diğerine aktarılmaktadır. Bu, gerekirse, bir görünümün paleti yeniden belirlemesine izin verir.

[CFrameWnd:: GetActiveView](../../mfc/reference/cframewnd-class.md#setactiveview) , [CFrameWnd:: GetActiveView](../../mfc/reference/cframewnd-class.md#getactiveview) 'ın döndürdüğü bir görünümle farklı olduğunda bu parametreler farklılık gösterir. Bu, en sık bölünmüş pencereler ile gerçekleşir.

##  <a name="onbeginprinting"></a>CView:: OnBeginPrinting

`OnPreparePrinting` çağrıldıktan sonra, bir yazdırma veya baskı önizleme işinin başlangıcında Framework tarafından çağırılır.

```
virtual void OnBeginPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Yazıcı cihazı bağlamını işaret eder.

*pInfo*<br/>
Geçerli yazdırma işini açıklayan bir [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısına işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması hiçbir şey yapmaz. Özellikle yazdırmak için gereken, kalem veya yazı tipi gibi herhangi bir GDI kaynağını ayırmak için bu işlevi geçersiz kılın. GDI nesnelerini, kendisini kullanan her sayfa için [OnPrint](#onprint) üye işlevinin içinden cihaz bağlamında seçin. Ekran görüntüleme ve yazdırma işlemleri için aynı görünüm nesnesini kullanıyorsanız, her ekran için gereken GDI kaynakları için ayrı değişkenler kullanın; Bu, yazdırma sırasında ekranı güncelleştirmenizi sağlar.

Bu işlevi, yazıcı cihaz bağlamının özelliklerine bağlı olan başlatma işlemleri gerçekleştirmek için de kullanabilirsiniz. Örneğin, belgeyi yazdırmak için gereken sayfa sayısı, kullanıcının Yazdır iletişim kutusu (sayfa uzunluğu gibi) tarafından belirtilen ayarlara bağlı olabilir. Böyle bir durumda, belge uzunluğunu, normalde bunu yaptığınız [OnPreparePrinting](#onprepareprinting) üye işlevinde belirtemezsiniz; iletişim kutusu ayarlarına bağlı olarak, yazıcı cihaz bağlamı oluşturuluncaya kadar beklemeniz gerekir. [OnBeginPrinting](#onbeginprinting) , yazıcı cihazı bağlamını temsil eden [CDC](../../mfc/reference/cdc-class.md) nesnesine erişmenizi sağlayan ilk geçersiz kılınabilir işlevdir, bu sayede belge uzunluğunu Bu işlevden ayarlayabilirsiniz. Belge uzunluğu bu süre içinde belirtilmemişse, baskı önizleme sırasında bir kaydırma çubuğu gösterilmediğini unutmayın.

##  <a name="ondragenter"></a>CView:: OnDragEnter

Fare ilk kez bırakma hedefi penceresinin kaydırılmamış bölgesine girdiğinde Framework tarafından çağırılır.

```
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pDataObject*<br/>
Görünümün bırakma alanına sürüklenen [birlikte](../../mfc/reference/coledataobject-class.md) bulunan bir işaret gösterir.

*dwKeyState*<br/>
Değiştirici anahtarlarının durumunu içerir. Bu, aşağıdakilerden herhangi bir sayıda bir birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*seçeneğinin*<br/>
Görünümün istemci alanına göre geçerli fare konumu.

### <a name="return-value"></a>Dönüş Değeri

DROPEFFECT numaralandırılmış türden bir değer; Kullanıcı bu konumda nesneyi bırakması durumunda oluşabilecek bırakma türünü gösterir. Bırakma türü genellikle *dwKeyState*tarafından belirtilen geçerli anahtar durumuna bağlıdır. Anahtar durumlarının DROPEFFECT değerlere standart eşlemesi:

- Veri nesnesi bu pencerede bırakılamaz DROPEFFECT_NONE.

- MK_CONTROL &#124; MK_SHIFT için DROPEFFECT_LINK, nesne ve sunucu arasında bir bağlantı oluşturur.

- MK_CONTROL için DROPEFFECT_COPY, bırakılan nesnenin bir kopyasını oluşturur.

- MK_ALT için DROPEFFECT_MOVE, bırakılan nesnenin bir kopyasını oluşturur ve özgün nesneyi siler. Bu, genellikle görünümün bu veri nesnesini kabul edebilmesi durumunda varsayılan bırakma etkiyiydir.

Daha fazla bilgi için bkz. MFC gelişmiş kavramlar örnek [Oclient](../../overview/visual-cpp-samples.md).

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz ve DROPEFFECT_NONE döndürmesidir.

[Ondragon](#ondragover) üye işlevine gelecekteki çağrılara hazırlanmak için bu işlevi geçersiz kılın. Veri nesnesinden gereken tüm veriler, daha sonra `OnDragOver` üye işlevinde kullanılmak üzere şu anda alınmalıdır. Ayrıca, kullanıcıya görsel geri bildirimde bulunmak için Görünüm şu anda güncellenmelidir. Daha fazla bilgi için [OLE sürükle ve bırak: bir bırakma hedefi uygulama](../../mfc/drag-and-drop-ole.md#implement-a-drop-target)makalesine bakın.

##  <a name="ondragleave"></a>CView:: OnDragLeave

Fare bu pencere için geçerli bırakma alanından taşındığında, bir sürükleme işlemi sırasında Framework tarafından çağırılır.

```
virtual void OnDragLeave();
```

### <a name="remarks"></a>Açıklamalar

Geçerli görünümün, nesne sürüklendiğinde ve bırakıldığında hiçbir görsel Kullanıcı geri bildirimini kaldırma gibi, [OnDragEnter](#ondragenter) veya [OnDragOver](#ondragover) çağrılarında gerçekleştirilen herhangi bir eylemi temizlemesi gerekiyorsa bu işlevi geçersiz kılın.

##  <a name="ondragover"></a>CView:: Ondragon

Fare bırakma hedefi penceresi üzerine taşındığında bir sürükleme işlemi sırasında Framework tarafından çağırılır.

```
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pDataObject*<br/>
Bırakma hedefinin üzerine sürüklenen [birlikte](../../mfc/reference/coledataobject-class.md) bırakılacak bir işaret gösterir.

*dwKeyState*<br/>
Değiştirici anahtarlarının durumunu içerir. Bu, aşağıdakilerden herhangi bir sayıda bir birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*seçeneğinin*<br/>
Görüntüleme istemci alanına göre geçerli fare konumu.

### <a name="return-value"></a>Dönüş Değeri

DROPEFFECT numaralandırılmış türden bir değer; Kullanıcı bu konumda nesneyi bırakması durumunda oluşabilecek bırakma türünü gösterir. Bırakma türü genellikle *dwKeyState*tarafından gösterildiği gibi geçerli anahtar durumuna bağlıdır. Anahtar durumlarının DROPEFFECT değerlere standart eşlemesi:

- Veri nesnesi bu pencerede bırakılamaz DROPEFFECT_NONE.

- MK_CONTROL &#124; MK_SHIFT için DROPEFFECT_LINK, nesne ve sunucu arasında bir bağlantı oluşturur.

- MK_CONTROL için DROPEFFECT_COPY, bırakılan nesnenin bir kopyasını oluşturur.

- MK_ALT için DROPEFFECT_MOVE, bırakılan nesnenin bir kopyasını oluşturur ve özgün nesneyi siler. Bu, genellikle görünümün veri nesnesini kabul edebilmesi durumunda varsayılan bırakma etkiyiydir.

Daha fazla bilgi için bkz. MFC gelişmiş kavramlar örnek [Oclient](../../overview/visual-cpp-samples.md).

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz ve DROPEFFECT_NONE döndürmesidir.

Sürükleme işlemi sırasında kullanıcıya görsel geribildirim vermek için bu işlevi geçersiz kılın. Bu işlev sürekli çağrıldığından, içinde yer alan tüm kodlar mümkün olduğunca en iyi duruma gelmelidir. Daha fazla bilgi için [OLE sürükle ve bırak: bir bırakma hedefi uygulama](../../mfc/drag-and-drop-ole.md#implement-a-drop-target)makalesine bakın.

##  <a name="ondragscroll"></a>CView:: OnDragScroll

Noktanın kaydırma bölgesinde olup olmadığını anlamak için [OnDragEnter](#ondragenter) veya [OnDragOver](#ondragover) çağrılmadan önce Framework tarafından çağırılır.

```
virtual DROPEFFECT OnDragScroll(
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*dwKeyState*<br/>
Değiştirici anahtarlarının durumunu içerir. Bu, aşağıdakilerden herhangi bir sayıda bir birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*seçeneğinin*<br/>
İmlecin, ekrana göre piksel cinsinden konumunu içerir.

### <a name="return-value"></a>Dönüş Değeri

DROPEFFECT numaralandırılmış türden bir değer; Kullanıcı bu konumda nesneyi bırakması durumunda oluşabilecek bırakma türünü gösterir. Bırakma türü genellikle *dwKeyState*tarafından belirtilen geçerli anahtar durumuna bağlıdır. Anahtar durumlarının DROPEFFECT değerlere standart eşlemesi:

- Veri nesnesi bu pencerede bırakılamaz DROPEFFECT_NONE.

- MK_CONTROL &#124; MK_SHIFT için DROPEFFECT_LINK, nesne ve sunucu arasında bir bağlantı oluşturur.

- MK_CONTROL için DROPEFFECT_COPY, bırakılan nesnenin bir kopyasını oluşturur.

- MK_ALT için DROPEFFECT_MOVE, bırakılan nesnenin bir kopyasını oluşturur ve özgün nesneyi siler.

- DROPEFFECT_SCROLL, bir sürükleme kaydırma işleminin gerçekleşmekte olduğunu veya hedef görünümde gerçekleşmekte olduğunu gösterir.

Daha fazla bilgi için bkz. MFC gelişmiş kavramlar örnek [Oclient](../../overview/visual-cpp-samples.md).

### <a name="remarks"></a>Açıklamalar

Bu olay için özel davranış sağlamak istediğinizde bu işlevi geçersiz kılın. Varsayılan uygulama, imleç her pencerenin kenarlığının içindeki varsayılan kaydırma bölgesine sürüklendiğinde otomatik olarak pencereleri kaydırır. Daha fazla bilgi için [OLE sürükle ve bırak: bir bırakma hedefi uygulama](../../mfc/drag-and-drop-ole.md#implement-a-drop-target)makalesine bakın.

##  <a name="ondraw"></a>CView:: OnDraw

Belgenin bir görüntüsünü işlemek için Framework tarafından çağırılır.

```
virtual void OnDraw(CDC* pDC) = 0;
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Belgenin bir görüntüsünü işlemek için kullanılacak cihaz bağlamına işaret eder.

### <a name="remarks"></a>Açıklamalar

Çerçeve, ekran görüntüleme, yazdırma ve baskı önizleme işlemleri gerçekleştirmek için bu işlevi çağırır ve her durumda farklı bir cihaz bağlamı geçirir. Varsayılan uygulama yok.

Belgenin görünümünü görüntülemek için bu işlevi geçersiz kılmanız gerekir. *PDC* parametresi tarafından Işaret edilen [CDC](../../mfc/reference/cdc-class.md) nesnesini kullanarak GRAFIK cihaz arabirimi (GDI) çağrıları yapabilirsiniz. Çizimden önce cihaz bağlamına kalemler veya yazı tipleri gibi GDI kaynaklarını seçebilirsiniz ve ardından bu öğeleri daha sonra seçimden kaldırabilirsiniz. Çizim kodunuz genellikle cihazdan bağımsız olabilir; Yani, görüntüyü görüntüleyen cihaz türü hakkında bilgi gerektirmez.

Çizimi iyileştirmek için, belirli bir dikdörtgenin çizilip çizilmeyeceğini öğrenmek için cihaz bağlamının [RectVisible](../../mfc/reference/cdc-class.md#rectvisible) üye işlevini çağırın. Normal ekran görüntüleme ve yazdırma arasında ayrım yapmanız gerekiyorsa, cihaz bağlamının [IsPrinting](../../mfc/reference/cdc-class.md#isprinting) üye işlevini çağırın.

##  <a name="ondrop"></a>CView:: OnDrop

Kullanıcı geçerli bir bırakma hedefi üzerinden bir veri nesnesi yayımlarsa Framework tarafından çağırılır.

```
virtual BOOL OnDrop(
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

' pDataObject *, bırakma hedefine bırakılan [ortak dili](../../mfc/reference/coledataobject-class.md) işaret eder.

*dropEffect*<br/>
Kullanıcının istediği bırakma efekti.

- DROPEFFECT_COPY, bırakılan veri nesnesinin bir kopyasını oluşturur.

- DROPEFFECT_MOVE veri nesnesini geçerli fare konumuna taşıdıkça.

- DROPEFFECT_LINK, bir veri nesnesi ve sunucusu arasında bir bağlantı oluşturur.

*seçeneğinin*<br/>
Görüntüleme istemci alanına göre geçerli fare konumu.

### <a name="return-value"></a>Dönüş Değeri

Bırakma başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz ve FALSE döndürür.

Bir OLE bırakma efektinin görünümün istemci alanına uygulanması için bu işlevi geçersiz kılın. Veri nesnesi, Pano veri biçimleri ve belirtilen noktada bırakılan veriler için *pDataObject* aracılığıyla incelenebilir.

> [!NOTE]
>  Bu görünüm sınıfında [OnDropEx](#ondropex) için bir geçersiz kılma varsa Framework bu işlevi çağırmaz.

##  <a name="ondropex"></a>CView:: OnDropEx

Kullanıcı geçerli bir bırakma hedefi üzerinden bir veri nesnesi yayımlarsa Framework tarafından çağırılır.

```
virtual DROPEFFECT OnDropEx(
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pDataObject*<br/>
Bırakma hedefine bırakılan [Colet](../../mfc/reference/coledataobject-class.md) 'e işaret eder.

*Varsayılan Drop*<br/>
Kullanıcının geçerli anahtar durumuna göre varsayılan bırakma işlemi için seçtiği efekt. DROPEFFECT_NONE olabilir. Bırakma etkileri, açıklamalar bölümünde ele alınmıştır.

*Açılan liste*<br/>
Bırakma kaynağının desteklediği bırakma efektlerinin bir listesi. Bırakma efekti değerleri bit düzeyinde OR ( **&#124;** ) işlemi kullanılarak birleştirilebilir. Bırakma etkileri, açıklamalar bölümünde ele alınmıştır.

*seçeneğinin*<br/>
Görüntüleme istemci alanına göre geçerli fare konumu.

### <a name="return-value"></a>Dönüş Değeri

*İşaret*tarafından belirtilen konumdaki bırakma denemesinden kaynaklanan bırakma etkisi. Bu, *dropEffectList*tarafından belirtilen değerlerden biri olmalıdır. Bırakma etkileri, açıklamalar bölümünde ele alınmıştır.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz ve Framework 'ün [OnDrop](#ondrop) işleyicisini çağırması gerektiğini göstermek için bir kukla değer (-1) döndürür.

Sağ fare düğmesi sürükle ve bırak efektini uygulamak için bu işlevi geçersiz kılın. Sağ fare düğmesi sürükleme ve bırakma genellikle sağ fare düğmesi bırakıldığında bir seçenek menüsünü görüntüler.

`OnDropEx` geçersiz kıldığınızda sağ fare düğmesi için sorgu gerekir. [OnDragEnter](#ondragenter) Işleyicinizden [GetKeyState](/windows/win32/api/winuser/nf-winuser-getkeystate) ' i çağırabilir veya sağ fare düğmesi durumunu kaydedebilirsiniz.

- Sağ fare düğmesi kapalıysa, geçersiz kılmada bırakma kaynağı tarafından bırakma efekti desteği sunan bir açılan menü görüntülenmelidir.

   - Bırakma kaynağının desteklediği bırakma efektlerini öğrenmek için *droplist* ' i inceleyin. Yalnızca açılan menüde bu eylemleri etkinleştirin.

   - Varsayılan eylemi *DropDefault*'a göre ayarlamak Için [SetMenuDefaultItem](/windows/win32/api/winuser/nf-winuser-setmenudefaultitem) kullanın.

   - Son olarak, açılır menüden Kullanıcı seçimiyle belirtilen eylemi gerçekleştirin.

- Sağ fare düğmesi kapalıysa, geçersiz kılma bunu standart bir bırakma isteği olarak işlemelidir. *DropDefault*'da belirtilen bırakma efektini kullanın. Alternatif olarak, geçersiz kılma bu bırakma işlemini işleyeceği `OnDrop` belirtmek için kukla değeri (-1) döndürebilir.

Pano veri biçimi için `COleDataObject` ve belirtilen noktada bırakılan verileri incelemek için *pDataObject* kullanın.

Bırakma etkileri, bir bırakma işlemiyle ilişkili eylemi anlatmaktadır. Aşağıdaki bırakma etkileri listesine bakın:

- DROPEFFECT_NONE bırakmaya izin verilmez.

- Kopyalama işlemi DROPEFFECT_COPY gerçekleştirilir.

- DROPEFFECT_MOVE bir taşıma işlemi gerçekleştirilecek.

- Bırakılan verilerden özgün verilere bir bağlantı DROPEFFECT_LINK oluşturulur.

- DROPEFFECT_SCROLL, bir sürükleme kaydırma işleminin gerçekleşmekte olduğunu veya hedefte meydana geldiğini belirtir.

Varsayılan menü komutunu ayarlama hakkında daha fazla bilgi için, bu birimdeki Windows SDK ve [CMenu:: GetSafeHmenu](../../mfc/reference/cmenu-class.md#getsafehmenu) Içindeki [SetMenuDefaultItem](/windows/win32/api/winuser/nf-winuser-setmenudefaultitem) bölümüne bakın.

##  <a name="onendprinting"></a>CView:: OnEndPrinting

Bir belge yazdırıldıktan veya önizlendikten sonra Framework tarafından çağırılır.

```
virtual void OnEndPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Yazıcı cihazı bağlamını işaret eder.

*pInfo*<br/>
Geçerli yazdırma işini açıklayan bir [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısına işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması hiçbir şey yapmaz. [OnBeginPrinting](#onbeginprinting) üye işlevinde ayrıldığınız HERHANGI bir GDI kaynağını serbest bırakmak için bu işlevi geçersiz kılın.

##  <a name="onendprintpreview"></a>CView:: OnEndPrintPreview

Kullanıcı baskı önizleme modundan çıktığında Framework tarafından çağırılır.

```
virtual void OnEndPrintPreview(
    CDC* pDC,
    CPrintInfo* pInfo,
    POINT point,
    CPreviewView* pView);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Yazıcı cihazı bağlamını işaret eder.

*pInfo*<br/>
Geçerli yazdırma işini açıklayan bir [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısına işaret eder.

*seçeneğinin*<br/>
En son önizleme modunda görüntülenen sayfanın noktasını belirtir.

*pView*<br/>
Önizleme için kullanılan görünüm nesnesine işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması [OnEndPrinting](#onendprinting) üye işlevini çağırır ve ana çerçeve penceresini, baskı önizleme başlamadan önce bulunduğu duruma geri yükler. Önizleme modu sonlandırıldığı zaman özel işleme gerçekleştirmek için bu işlevi geçersiz kılın. Örneğin, önizleme modundan Normal görüntüleme moduna geçiş yaparken kullanıcının belgedeki konumunu korumak istiyorsanız, *nokta* parametresi tarafından tanımlanan konuma ve *pInfo* parametresinin işaret ettiği `CPrintInfo` yapısının `m_nCurPage` üyesine kaydırma yapabilirsiniz.

Genellikle işlevin sonunda, `OnEndPrintPreview` taban sınıf sürümünü her zaman geçersiz kılınızdan çağırın.

##  <a name="oninitialupdate"></a>CView:: OnInitialUpdate

Görünüm belgeye ilk iliştirildikten sonra, ancak görünüm ilk görüntülenmeden önce Framework tarafından çağırılır.

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması, bir ipucu bilgisi olmadan [OnUpdate](#onupdate) üye işlevini çağırır (diğer bir deyişle, *lipucu* parametresi için 0 varsayılan değerlerini kullanarak ve *phınt* parametresi için null). Belge hakkında bilgi gerektiren tek seferlik başlatma gerçekleştirmek için bu işlevi geçersiz kılın. Örneğin, uygulamanız sabit boyutlu belgeler içeriyorsa, belgenin boyutuna bağlı olarak bir görünümün kaydırma sınırlarını başlatmak için bu işlevi kullanabilirsiniz. Uygulamanız değişken boyutlu belgeleri destekliyorsa, belge her değiştiğinde kaydırma sınırlarını güncelleştirmek için [OnUpdate](#onupdate) kullanın.

##  <a name="onpreparedc"></a>CView:: Onhazırlık EDC

[OnDraw](#ondraw) üye işlevi ekran görüntüsü için çağrılmadan önce ve yazdırma ya da baskı önizleme sırasında her sayfa için [OnPrint](#onprint) üye işlevi çağrılmadan önce Framework tarafından çağırılır.

```
virtual void OnPrepareDC(
    CDC* pDC,
    CPrintInfo* pInfo = NULL);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Belgenin bir görüntüsünü işlemek için kullanılacak cihaz bağlamına işaret eder.

*pInfo*<br/>
`OnPrepareDC` yazdırma veya baskı önizleme için çağrılırsa geçerli yazdırma işini açıklayan bir [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısına işaret eder; `m_nCurPage` üyesi yazdırılacak sayfayı belirtir. Ekran görüntüleme için `OnPrepareDC` çağrılırsa Bu parametre NULL olur.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması, işlev ekran görüntüsü için çağrılırsa hiçbir şey yapmaz. Ancak, bu işlev, cihaz bağlamının özniteliklerini ayarlamak için [CScrollView](../../mfc/reference/cscrollview-class.md)gibi türetilmiş sınıflarda geçersiz kılınır; Sonuç olarak, her zaman geçersiz kılmanın başlangıcında temel sınıf uygulamasını çağırmanız gerekir.

İşlev yazdırma için çağrılırsa, varsayılan uygulama *pInfo* parametresinde depolanan sayfa bilgilerini inceler. Belge uzunluğu belirtilmemişse, `OnPrepareDC` belgenin bir sayfa uzunluğunda olduğunu varsayar ve bir sayfa yazdırıldıktan sonra yazdırma döngüsünü sonlandırır. İşlevi, yapının `m_bContinuePrinting` üyesini FALSE olarak ayarlayarak PRINT döngüsünü sonlandırır.

Aşağıdaki nedenlerden herhangi biri için `OnPrepareDC` geçersiz kılın:

- Belirtilen sayfa için gerektiğinde cihaz bağlamının özniteliklerini ayarlamak için. Örneğin, eşleme modunu veya cihaz bağlamının diğer özelliklerini ayarlamanız gerekirse, bu işlevi izleyin.

- Yazdırma zamanı sayfalandırmayı gerçekleştirmek için. Normalde, yazdırma başladığında, [OnPreparePrinting](#onprepareprinting) üye işlevini kullanarak belgenin uzunluğunu belirtirsiniz. Ancak, belgenin ne kadar süreyle olduğunu bilmiyorsanız (örneğin, bir veritabanından belirlenmeyen bir kayıt sayısı yazdırılırken), yazdırılırken belgenin sonuna kadar olan `OnPrepareDC` geçersiz kılın. Yazdırılacak belge yoksa, `CPrintInfo` yapısının `m_bContinuePrinting` üyesini FALSE olarak ayarlayın.

- Çıkış kodlarını yazıcıya sayfa temelinde göndermek için. `OnPrepareDC`kaçış kodları göndermek için *PDC* parametresinin `Escape` üye işlevini çağırın.

Geçersiz kılmanın başlangıcında `OnPrepareDC` temel sınıf sürümünü çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#183](../../mfc/codesnippet/cpp/cview-class_1.cpp)]

##  <a name="onprepareprinting"></a>CView:: OnPreparePrinting

Bir belge yazdırılmadan ya da önizlenmeden önce Framework tarafından çağırılır.

```
virtual BOOL OnPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*pInfo*<br/>
Geçerli yazdırma işini açıklayan bir [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Yazdırmaya başlamak için sıfır dışında; yazdırma işi iptal edildiyse 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz.

Yazdırma ve baskı önizlemeyi etkinleştirmek için bu işlevi geçersiz kılmanız gerekir. [DoPreparePrinting](#doprepareprinting) üye işlevini çağırın, *pInfo* parametresini geçirerek dönüş değerini döndürün; `DoPreparePrinting` Yazdır iletişim kutusunu görüntüler ve bir yazıcı cihaz bağlamı oluşturur. Yazdır iletişim kutusunu varsayılanlar dışındaki değerlerle başlatmak istiyorsanız, *pInfo*üyelerine değerler atayın. Örneğin, belgenin uzunluğunu biliyorsanız, `DoPreparePrinting`çağrılmadan önce değeri *pInfo* 'ın [SetMaxPage](../../mfc/reference/cprintinfo-structure.md#setmaxpage) üye işlevine geçirin. Bu değer, Yazdır iletişim kutusunun Aralık bölümündeki to: kutusunda görüntülenir.

`DoPreparePrinting`, bir önizleme işi için Yazdır iletişim kutusunu görüntülemez. Bir yazdırma işinin Yazdır iletişim kutusunu atlamak istiyorsanız, *pInfo* 'nun `m_bPreview` üyesinin false olup olmadığını denetleyin ve ardından `DoPreparePrinting`GEÇIRMEDEN önce true olarak ayarlayın. daha sonra FALSE olarak sıfırlayın.

Yazıcı cihaz bağlamını temsil eden `CDC` nesnesine erişim gerektiren başlatma işlemleri yapmanız gerekiyorsa (örneğin, belge uzunluğunu belirtmeden önce sayfa boyutunu bilmeniz gerekirse) `OnBeginPrinting` üye işlevini geçersiz kılın.

`m_nNumPreviewPages` değerini veya *pInfo* parametresinin `m_strPageDesc` üyelerini ayarlamak istiyorsanız, `DoPreparePrinting`çağrıldıktan sonra bunu yapın. `DoPreparePrinting` member işlevi, `m_nNumPreviewPages` uygulamanın bulunduğu değere ayarlar. INı dosyası ve `m_strPageDesc` varsayılan değerine ayarlar.

### <a name="example"></a>Örnek

  Framework 'ün bir Yazdır iletişim kutusu görüntülemesi ve sizin için bir yazıcı DC oluşturması için `OnPreparePrinting` geçersiz kılın ve `DoPreparePrinting` geçersiz kılmada çağırın.

[!code-cpp[NVC_MFCDocView#184](../../mfc/codesnippet/cpp/cview-class_2.cpp)]

Belgenin kaç sayfa içerdiğini biliyorsanız, `DoPreparePrinting`çağrılmadan önce `OnPreparePrinting` en yüksek sayfayı ayarlayın. Çerçeve, Yazdır iletişim kutusunun "to" kutusunda maksimum sayfa numarasını görüntüler.

[!code-cpp[NVC_MFCDocView#185](../../mfc/codesnippet/cpp/cview-class_3.cpp)]

##  <a name="onprint"></a>CView:: OnPrint

Belgenin bir sayfasını yazdırmak veya önizlemek için Framework tarafından çağırılır.

```
virtual void OnPrint(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Yazıcı cihazı bağlamını işaret eder.

*pInfo*<br/>
Geçerli yazdırma işini açıklayan `CPrintInfo` yapısını gösterir.

### <a name="remarks"></a>Açıklamalar

Yazdırılmakta olan her sayfa için Framework, [Onhazırlık EDC](#onpreparedc) üye işlevini çağırdıktan hemen sonra bu işlevi çağırır. Yazdırılan sayfa, *pInfo* 'ın Işaret ettiği [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısının `m_nCurPage` üyesi tarafından belirtilir. Varsayılan uygulama, [OnDraw](#ondraw) üye işlevini çağırır ve yazıcı cihazı bağlamını geçirir.

Aşağıdaki nedenlerden herhangi biri için bu işlevi geçersiz kılın:

- Çok sayfalı belgelerin yazdırmaya izin vermek için. Belgenin yalnızca Yazdırılmakta olan sayfaya karşılık gelen kısmını işle. Oluşturma işlemini gerçekleştirmek için `OnDraw` kullanıyorsanız, Görünüm penceresi başlangıcını yalnızca belgenin uygun kısmının yazdırılması için ayarlayabilirsiniz.

- Yazdırılmış görüntünün ekran görüntüsünden farklı görünmesini sağlamak için (yani, uygulamanız WYSıWYG değilse). Yazıcı cihazı bağlamını `OnDraw`geçirmek yerine, ekranda gösterilmeyen öznitelikleri kullanarak bir görüntüyü işlemek için cihaz bağlamını kullanın.

   Ekran görüntüsü için kullanmıyorsanız, yazdırma için GDI kaynaklarına ihtiyacınız varsa, bunları çizimden önce cihaz bağlamına seçip daha sonra seçimini kaldırın. Bu GDI kaynakları [OnBeginPrinting](#onbeginprinting) 'e ayrılmalı ve [OnEndPrinting](#onendprinting)içinde yayımlanır.

- Üst bilgileri veya altbilgileri uygulamak. `OnDraw`, üzerine yazdırabilecek alanı kısıtlayarak işleme yapmak için kullanmaya devam edebilirsiniz.

*PInfo* parametresinin `m_rectDraw` üyesi, sayfanın yazdırılabilir alanını mantıksal birimlerde açıklar.

`OnPrint`geçersiz kılmada `OnPrepareDC` çağırmayın; çerçeve, `OnPrint`çağrılmadan önce otomatik olarak `OnPrepareDC` çağırır.

### <a name="example"></a>Örnek

Geçersiz kılınan `OnPrint` işlevi için bir iskelet aşağıda verilmiştir:

[!code-cpp[NVC_MFCDocView#186](../../mfc/codesnippet/cpp/cview-class_4.cpp)]

Diğer bir örnek için bkz. [CRichEditView::P rintinsiderect](../../mfc/reference/cricheditview-class.md#printinsiderect).

##  <a name="onscroll"></a>CView:: OnScroll

Kaydırmanın mümkün olup olmadığını anlamak için Framework tarafından çağırılır.

```
virtual BOOL OnScroll(
    UINT nScrollCode,
    UINT nPos,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parametreler

*nScrollCode*<br/>
Kullanıcının kaydırma isteğini gösteren bir kaydırma çubuğu kodu. Bu parametre iki bölümden oluşur: yatay olarak oluşan kaydırma türünü belirleyen düşük sıralı bir bayt ve dikey olarak oluşan kaydırma türünü belirleyen yüksek sıralı bir bayt.

- SB_BOTTOM en alta kayar.

- SB_LINEDOWN bir satır aşağı kaydırır.

- SB_LINEUP bir satır yukarı kaydırır.

- SB_PAGEDOWN bir sayfa aşağı kaydırır.

- SB_PAGEUP bir sayfa yukarı kaydırır.

- SB_THUMBTRACK kaydırma kutusunu belirtilen konuma sürükler. Geçerli konum *nPos*içinde belirtilmiştir.

- SB_TOP üste kayar.

*nPos*<br/>
Kaydırma çubuğu kodu SB_THUMBTRACK ise, geçerli kaydırma kutusu konumunu içerir; Aksi takdirde kullanılmaz. İlk kaydırma aralığına bağlı olarak, *nPos* negatif olabilir ve gerekirse bir **int** 'e atamalısınız.

*bDoScroll*<br/>
Belirtilen kaydırma eylemini gerçekten yapıp yapamayacağını belirler. DOĞRU ise, kaydırma gerçekleşmelidir; YANLıŞSA, kaydırma gerçekleşmemelidir.

### <a name="return-value"></a>Dönüş Değeri

*BDoScroll* true ise ve görünümün gerçekten kaydırıldığı takdirde sıfır dışında bir değer döndürür; Aksi takdirde 0. *BDOSCROLL* yanlış ise, kaydırma işlemini gerçekten yapmasanız bile *BDOSCROLL* true ise, döndürülecek değeri döndürün.

### <a name="remarks"></a>Açıklamalar

Tek bir durumda bu işlev, görünüm bir kaydırma çubuğu iletisi aldığında *bDoScroll* değeri true olarak ayarlanmış çerçeve tarafından çağırılır. Bu durumda, gerçekten görünümü kaydırmanız gerekir. Diğer durumlarda bu işlev, bir OLE öğesi başlangıçta bir bırakma hedefinin otomatik kaydırma bölgesine sürüklendiğinde, gerçekte kaymadan önce, *bDoScroll* değeri false olarak çağrılır. Bu durumda, gerçekten görünümü kaydırmamalıdır.

##  <a name="onscrollby"></a>CView:: OnScrollBy

Kullanıcı, görünümün geçerli kenarlıklarına karşı bir OLE öğesi sürükleyerek veya dikey ya da yatay kaydırma çubuklarını düzenleyerek çerçeve tarafından çağırılır.

```
virtual BOOL OnScrollBy(
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parametreler

*sizeScroll*<br/>
Yatay ve dikey olarak kaydırılan piksel sayısı.

*bDoScroll*<br/>
Görünümün kaydırmasını oluşup oluşmadığını belirler. DOĞRU ise, kaydırma gerçekleşir; YANLıŞSA, kaydırma gerçekleşmez.

### <a name="return-value"></a>Dönüş Değeri

Görünüm kaydırılabilse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Türetilmiş sınıflarda bu yöntem, görünümün Kullanıcı tarafından istenen yönde kaydırılabilir olup olmadığını denetler ve gerekirse yeni bölgeyi günceller. Bu işlev, gerçek kaydırma isteğini gerçekleştirmek için [CWnd:: OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) ve [CWnd:: OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) tarafından otomatik olarak çağrılır.

Bu yöntemin varsayılan uygulanması görünümü değiştirmez, ancak çağrılmadığında görünüm `CScrollView`türetilmiş bir sınıfta kaydırılmaz.

Belge genişliği veya yüksekliği 32767 pikseli aşarsa, `OnScrollBy` geçersiz bir *sizeScroll* bağımsız değişkeniyle çağrıldığı için, son 32767 kaydırma başarısız olur.

##  <a name="onupdate"></a>CView:: OnUpdate

Görünümün belgesi değiştirildikten sonra Framework tarafından çağırılır; Bu işlev [CDocument:: UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) tarafından çağrılır ve görünümün bu değişiklikleri yansıtacak şekilde görünümünü güncelleştirmesine izin verir.

```
virtual void OnUpdate(
    CView* pSender,
    LPARAM lHint,
    CObject* pHint);
```

### <a name="parameters"></a>Parametreler

*pSender*<br/>
Belgeyi değiştiren görünümü işaret eder veya tüm görünümler güncelleniyorsa NULL olur.

*Lipucu*<br/>
Değişiklikler hakkında bilgi içerir.

*Phınt*<br/>
Değişiklikler hakkında bilgi depolayan bir nesneye işaret eder.

### <a name="remarks"></a>Açıklamalar

Ayrıca, [OnInitialUpdate](#oninitialupdate)'in varsayılan uygulamasıyla de çağrılır. Varsayılan uygulama tüm istemci alanını geçersiz kılar ve sonraki WM_PAINT iletisi alındığında boyama için işaretler. Yalnızca belgenin değiştirilen bölümlerine eşlenen bölgeleri güncelleştirmek istiyorsanız bu işlevi geçersiz kılın. Bunu yapmak için, ipucu parametrelerini kullanarak değişiklikler hakkında bilgi geçirmeniz gerekir.

*Lipucu*kullanmak için, özel ipucu değerleri, genellikle bir bit maskesi veya numaralandırılmış bir tür tanımlayın ve belgenin bu değerlerden birini iletmektir. *PHint*kullanmak için [CObject](../../mfc/reference/cobject-class.md) 'ten bir ipucu sınıfı türetirsiniz ve belgenin bir ipucu nesnesine işaretçi geçirmesini sağlar; `OnUpdate`geçersiz kıldığınızda, ipucu nesnesinin çalışma zamanı türünü öğrenmek için [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof) üye işlevini kullanın.

Genellikle `OnUpdate`doğrudan bir çizim gerçekleştirmemelisiniz. Bunun yerine, güncelleştirilmesi gereken alanı cihaz koordinatları ' nde açıklayan dikdörtgeni saptayın. Bu dikdörtgeni [CWnd:: InvalidateRect](../../mfc/reference/cwnd-class.md#invalidaterect)öğesine geçirin. Bu, bir [WM_PAINT](/windows/win32/gdi/wm-paint) iletisinin bir sonraki açılışında boyama oluşmasına neden olur.

*Lipucu* 0 Ise ve *pHint* null ise, belge bir genel güncelleştirme bildirimi göndermiştir. Bir görünüm genel bir güncelleştirme bildirimi alırsa veya ipuçlarının kodunu çözemediği takdirde, tüm istemci alanını geçersiz kılar.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDıDOCVW](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[CSplitterWnd Sınıfı](../../mfc/reference/csplitterwnd-class.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[CDocument Sınıfı](../../mfc/reference/cdocument-class.md)
