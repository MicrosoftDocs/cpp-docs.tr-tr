---
title: CView Sınıfı
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
ms.openlocfilehash: 763e36b0736ce588e7e2aded25e50347f9e0ca70
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373198"
---
# <a name="cview-class"></a>CView Sınıfı

Kullanıcı tanımlı görünüm sınıfları için temel işlevselliği sağlar.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CView : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CView::CView](#cview)|Bir `CView` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CView::DoPreparePrinting](#doprepareprinting)|Yazdır iletişim kutusunu görüntüler ve yazıcı aygıtı bağlamı oluşturur; `OnPreparePrinting` üye işlevi geçersiz kılınırken arayın.|
|[CView::Belge Alma](#getdocument)|Görünümle ilişkili belgeyi döndürür.|
|[CView::Seçili](#isselected)|Belge öğesinin seçilip seçilmediğini sınama. OLE desteği için gereklidir.|
|[CView::OndragEnter](#ondragenter)|Bir öğe görünümün sürükle ve bırak bölgesine ilk sürüklendiğinde çağrılır.|
|[CView::OnDragLeave](#ondragleave)|Sürüklenen bir öğe görünümün sürükle ve bırak bölgesinden ayrıldığında çağrılır.|
|[CView::Ondragover](#ondragover)|Bir öğe görünümün sürükle ve bırak bölgesi üzerinde sürüklendiğinde çağrılır.|
|[CView::OnDragScroll](#ondragscroll)|İmlecin pencerenin kaydırma bölgesine sürüklenip sürüklenmediğini belirlemek için çağrılır.|
|[CView::OnDrop](#ondrop)|Bir öğe görünümün sürükle ve bırak bölgesine bırakıldığında, varsayılan işleyici olarak adlandırılır.|
|[CView::OnDropex](#ondropex)|Bir öğe görünümün sürükle ve bırak bölgesine bırakıldığında, birincil işleyici olarak adlandırılır.|
|[CView::OnInitialUpdate](#oninitialupdate)|Bir görünüm önce belgeye iliştirildikten sonra çağrılır.|
|[CView::OnPrepareDC](#onpreparedc)|`OnDraw` Üye işlev ekran ekranı için çağrılmadan veya `OnPrint` üye işlev yazdırma veya yazdırma önizlemesi için çağrılmadan önce çağrılır.|
|[CView::OnScroll](#onscroll)|OLE öğeleri görünümün sınırlarının ötesine sürüklendiğinde çağrılır.|
|[CView::Onscrollby](#onscrollby)|Etkin yerinde OLE öğeleri içeren bir görünüm kaydırıldığında çağrılır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CView::OnActivateFrame](#onactivateframe)|Görünümü içeren çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında çağrılır.|
|[CView::OnActivateView](#onactivateview)|Bir görünüm etkinleştirildiğinde çağrılır.|
|[CView::OnBeginPrinting](#onbeginprinting)|Yazdırma işi başladığında çağrılır; grafik aygıtı arabirimi (GDI) kaynaklarını ayırmak için geçersiz kılın.|
|[CView::OnDraw](#ondraw)|Ekran ekranı, yazdırma veya yazdırma önizlemesi için belgenin görüntüsünü işlemek için çağrılır. Uygulama gereklidir.|
|[CView::OnEndPrinting](#onendprinting)|Yazdırma işi sona erdiğinde çağrılır; GDI kaynaklarının yerini almak için geçersiz kılın.|
|[CView::OnEndPrintPreview](#onendprintpreview)|Önizleme modu çıkarıldığında çağrılır.|
|[CView::OnPreparePrinting](#onprepareprinting)|Belge yazdırılmadan veya önizlemeden önce çağrılır; Yazdırma iletişim kutusunu başlatmayı geçersiz kılın.|
|[CView::Onprint](#onprint)|Belgenin bir sayfasını yazdırmak veya önizlemek için çağrılır.|
|[CView::Onupdate](#onupdate)|Bir görünümü belgenin değiştirildiğini bildirmek için çağrıldı.|

## <a name="remarks"></a>Açıklamalar

Görünüm belgeye eklenir ve belge ile kullanıcı arasında aracı görevi görür: görünüm belgenin ekrandaki veya yazıcıdaki görüntüsünü işler ve kullanıcı girişini belge üzerinde işlem olarak yorumlar.

Görünüm, çerçeve penceresinin alt bölümüdür. Bölünen pencerede olduğu gibi, birden fazla görünüm çerçeve penceresini paylaşabilir. Görünüm sınıfı, çerçeve penceresi sınıfı ve belge sınıfı arasındaki ilişki `CDocTemplate` bir nesne tarafından oluşturulur. Kullanıcı yeni bir pencere açtığında veya varolan bir pencereyi böldüğüzaman, çerçeve yeni bir görünüm inşa eder ve belgeye bağlar.

Bir görünüm yalnızca bir belgeye eklenebilir, ancak belgenin aynı anda birden çok görünümü olabilir (örneğin, belge bir ayırıcı penceresinde veya birden çok belge arabiriminde (MDI) uygulamasında birden çok alt pencerede görüntüleniyorsa. Uygulamanız belirli bir belge türü için farklı görünüm türlerini destekleyebilir; örneğin, sözcük işleme programı hem belgenin tam metin görünümünü hem de yalnızca bölüm başlıklarını gösteren bir anahat görünümünü sağlayabilir. Bu farklı görünüm türleri, ayırıcı pencere kullanıyorsanız ayrı çerçeve pencerelerine veya tek bir çerçeve penceresinin ayrı bölmelerine yerleştirilebilir.

Görünüm, klavye girişi, fare girişi veya sürükle-bırak yoluyla giriş gibi birkaç farklı giriş türünü ve menülerden, araç çubuklarından veya kaydırma çubuklarından komutları işlemekten sorumlu olabilir. Görünüm, çerçeve penceresi tarafından iletilen komutları alır. Görünüm belirli bir komutu işlemiyorsa, komutu ilişkili belgesine ileter. Tüm komut hedefleri gibi, bir görünüm iletileri bir ileti haritası üzerinden işler.

Görünüm, belgenin verilerini görüntülemek ve değiştirmekten sorumludur, ancak depolamaktan değil. Belge, verileri hakkında gerekli ayrıntıları görünümü sağlar. Görünümün belgenin veri üyelerine doğrudan erişmesine izin verebilir veya görünüm sınıfının araması için belge sınıfında üye işlevler sağlayabilirsiniz.

Bir belgenin verisi değiştiğinde, değişikliklerden sorumlu görünüm genellikle [CDocument'i çağırır::Belge için UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) işlevi, `OnUpdate` her biri için üye işlevi çağırarak diğer tüm görünümleri haber eder. Varsayılan uygulama `OnUpdate` görünümün tüm istemci alanını geçersiz klar. Yalnızca istemci alanının belgenin değiştirilen bölümleriyle eşleyen bölgelerini geçersiz kılmak için geçersiz kılınabilir.

Kullanmak `CView`için, ondan bir sınıf türetmek ve ekran ekranı gerçekleştirmek için `OnDraw` üye işlevi uygulayın. Yazdırma ve `OnDraw` yazdırma önizlemesini gerçekleştirmek için de kullanabilirsiniz. Çerçeve, belgenizi yazdırmak ve önizlemek için yazdırma döngülerini işler.

Görünüm, kaydırma çubuğu iletilerini [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) ve [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) üye işlevleriyle işler. Bu işlevlerde kaydırma çubuğu iletisi işleme yi `CView` uygulayabilir veya sizin için kaydırma işlemek için türetilmiş [CScrollView](../../mfc/reference/cscrollview-class.md) sınıfını kullanabilirsiniz.

Ayrıca, `CScrollView`Microsoft Hazırlık Sınıf Kitaplığı aşağıdakilerden `CView`türetilen dokuz sınıf sağlar:

- [CCtrlView](../../mfc/reference/cctrlview-class.md), belge kullanımına izin veren bir görünüm - ağaç, liste ve zengin düzenleme denetimleri ile mimari görüntüleyin.

- [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md), iletişim kutusu denetimlerinde veritabanı kayıtlarını görüntüleyen bir görünüm.

- [CEditView](../../mfc/reference/ceditview-class.md), basit bir çok satırlı metin düzenleyicisi sağlayan bir görünüm. Bir `CEditView` nesneyi iletişim kutusunda denetim olarak ve belgedeki görünüm olarak kullanabilirsiniz.

- [CFormView](../../mfc/reference/cformview-class.md), iletişim kutusu denetimleri içeren ve bir iletişim şablonu kaynağına dayalı bir kaydırılabilir görünüm.

- [CListView](../../mfc/reference/clistview-class.md), belge nin kullanımına izin veren bir görünüm - liste denetimleri ile mimari görüntüleyin.

- [CRecordView](../../mfc/reference/crecordview-class.md), iletişim kutusu denetimlerinde veritabanı kayıtlarını görüntüleyen bir görünüm.

- [CRichEditView](../../mfc/reference/cricheditview-class.md), belge kullanımına izin veren bir görünüm - zengin edit denetimleri ile görünüm mimarisi.

- [CScrollView](../../mfc/reference/cscrollview-class.md), otomatik olarak kaydırma desteği sağlayan bir görünüm.

- [CTreeView](../../mfc/reference/ctreeview-class.md), belgenin kullanımına izin veren bir görünüm - ağaç denetimleri ile mimari görüntüleyin.

Sınıf `CView` ayrıca, yazdırma önizleme `CPreviewView`gerçekleştirmek için çerçeve tarafından kullanılan adlı türemiş bir uygulama sınıfı vardır. Bu sınıf, araç çubuğu, tek veya çift sayfaönizleme ve önizleme görüntüsünü büyütme gibi yazdırma önizleme penceresine özgü özellikler için destek sağlar. Yazdırma önizlemesi için kendi arabirimeolduğunuzu uygulamak istemiyorsanız (örneğin, yazdırma önizleme modunda düzenlemeyi desteklemek istiyorsanız) `CPreviewView`'üye işlevlerin hiçbirini aramanız veya geçersiz kılmanız gerekmez). Kullanma `CView`hakkında daha fazla bilgi için bkz: [Belge/Görünüm Mimarisi](../../mfc/document-view-architecture.md) ve [Yazdırma.](../../mfc/printing.md) Ayrıca, yazdırma önizlemesini özelleştirme hakkında daha fazla bilgi için [Teknik Not 30'a](../../mfc/tn030-customizing-printing-and-print-preview.md) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cviewcview"></a><a name="cview"></a>CView::CView

Bir `CView` nesne inşa eder.

```
CView();
```

### <a name="remarks"></a>Açıklamalar

Yeni bir çerçeve penceresi oluşturulduğunda veya bir pencere bölündüğünde çerçeve oluşturucuyu çağırır. Belge iliştirildikten sonra görünümü başlatmak için [OnInitialUpdate](#oninitialupdate) üye işlevini geçersiz kılın.

## <a name="cviewdoprepareprinting"></a><a name="doprepareprinting"></a>CView::DoPreparePrinting

Yazdırma iletişim kutusunu çağırmak ve bir yazıcı aygıtı bağlamı oluşturmak için [OnPreparePrinting'i](#onprepareprinting) geçersiz kılmanızdan bu işlevi çağırın.

```
BOOL DoPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*Pınfo*<br/>
Geçerli yazdırma işini açıklayan bir [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısına işaret eden.

### <a name="return-value"></a>Dönüş Değeri

Yazdırma veya yazdırma önizlemesi başlayabilirse sıfırolmayan; İşlem iptal edildiyse 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin davranışı, yazdırma veya yazdırma önizlemesi için çağrılıp çağrılmadığına bağlıdır `m_bPreview` *(pInfo* parametresinin üyesi tarafından belirtilir). Bir dosya yazdırılıyorsa, bu *işlev, pInfo'nun* işaret ettiği [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısındaki değerleri kullanarak Yazdırma iletişim kutusunu çağırır; Kullanıcı iletişim kutusunu kapattıktan sonra, işlev iletişim kutusunda belirtilen kullanıcıayarlarını temel alan bir yazıcı aygıtı bağlamı oluşturur ve bu aygıt bağlamını *pInfo* parametresi aracılığıyla döndürür. Bu aygıt bağlamı belgeyi yazdırmak için kullanılır.

Bir dosya önizleniyorsa, bu işlev geçerli yazıcı ayarlarını kullanarak bir yazıcı aygıtı bağlamı oluşturur; bu aygıt bağlamı önizleme sırasında yazıcısimüle etmek için kullanılır.

## <a name="cviewgetdocument"></a><a name="getdocument"></a>CView::Belge Alma

Görünümün belgesine işaretçi almak için bu işlevi arayın.

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görünümle ilişkili [CDocument](../../mfc/reference/cdocument-class.md) nesnesine işaretçi. Görünüm belgeye eklenmemişse NULL.

### <a name="remarks"></a>Açıklamalar

Bu, belgenin üye işlevlerini aramanızı sağlar.

## <a name="cviewisselected"></a><a name="isselected"></a>CView::Seçili

Belirtilen belge öğesinin seçilip seçilmediğini denetlemek için çerçeve tarafından çağrılır.

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>Parametreler

*pDocItem*<br/>
Test edilen belge öğesine işaret edilir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen belge öğesi seçilirse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması FALSE döndürür. [CDocItem](../../mfc/reference/cdocitem-class.md) nesnelerini kullanarak seçim uyguluyorsanız bu işlevi geçersiz kılın. Görünümünüz OLE öğeleri içeriyorsa, bu işlevi geçersiz kılmanız gerekir.

## <a name="cviewonactivateframe"></a><a name="onactivateframe"></a>CView::OnActivateFrame

Görünümü içeren çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında çerçeve tarafından çağrılır.

```
virtual void OnActivateFrame(
    UINT nState,
    CFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>Parametreler

*Nstate*<br/>
Çerçeve penceresinin etkinleştirilip etkinleştirilmediğini veya devre dışı bırakıldığını belirtir. Aşağıdaki değerlerden biri olabilir:

- WA_INACTIVE Çerçeve penceresi devre dışı bırakılıyor.

- WA_ACTIVE Çerçeve penceresi fare tıklaması dışındaki bir yöntemle etkinleştiriliyor (örneğin, pencereyi seçmek için klavye arabirimini kullanarak).

- WA_CLICKACTIVE Çerçeve penceresi bir fare tıklaması ile etkinleştiriliyor

*pFrameWnd*<br/>
Etkinleştirilecek çerçeve penceresine işaretçi.

### <a name="remarks"></a>Açıklamalar

Görünümle ilişkili çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında özel işleme gerçekleştirmek istiyorsanız bu üye işlevi geçersiz kılın. Örneğin, [CFormView](../../mfc/reference/cformview-class.md) bu geçersiz kılmayı, odak noktası olan denetimi kaydeder ve geri yüklediğinde gerçekleştirir.

## <a name="cviewonactivateview"></a><a name="onactivateview"></a>CView::OnActivateView

Bir görünüm etkinleştirildiğinde veya devre dışı bırakıldığında çerçeve tarafından çağrılır.

```
virtual void OnActivateView(
    BOOL bActivate,
    CView* pActivateView,
    CView* pDeactiveView);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
Görünümün etkinleştirilip etkinleştirilmediğini veya devre dışı bırakıldığını gösterir.

*pActivateView*<br/>
Etkinleştirilmekte olan görünüm nesnesine işaret ediyor.

*pDeactiveView*<br/>
Devre dışı bırakılan görünüm nesnesine işaret ediyor.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması, odağı etkinleştirilen görünüme ayarlar. Bir görünüm etkinleştirildiğinde veya devre dışı bırakıldığında özel işleme gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın. Örneğin, etkin görünümü etkin olmayan görünümlerden ayıran özel görsel ipuçları sağlamak istiyorsanız, *bActivate* parametresini inceler ve görünümün görünümünü buna göre güncelleştirebilirsiniz.

*pActiveView* ve *pDeactiveView* parametreleri, uygulamanın ana çerçeve penceresi etkin görünümde herhangi bir değişiklik olmadan etkinleştirilirse aynı görünümü işaret eder — örneğin, odak noktası uygulama içinde bir görünümden diğerine değil, başka bir uygulamadan diğerine aktarılıyorsa veya MDI alt pencereler arasında geçiş yaparken. Bu, gerekirse paletini yeniden gerçekleştirmesini sağlar.

[Bu parametreler, CFrameWnd::SetActiveView CFrameWnd'den](../../mfc/reference/cframewnd-class.md#setactiveview) farklı bir görünümle çağrıldığında farklılık [gösterir::GetActiveView'in](../../mfc/reference/cframewnd-class.md#getactiveview) geri döneceği görünüm. Bu en sık splitter pencerelerile olur.

## <a name="cviewonbeginprinting"></a><a name="onbeginprinting"></a>CView::OnBeginPrinting

Bir yazdırma veya yazdırma önizleme işinin başındaki `OnPreparePrinting` çerçeve tarafından çağrıldıktan sonra çağrılır.

```
virtual void OnBeginPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Yazıcı aygıtı bağlamını işaret eder.

*Pınfo*<br/>
Geçerli yazdırma işini açıklayan bir [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısına işaret eden.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması hiçbir şey yapmaz. Özellikle yazdırma için gereken kalem veya yazı tipleri gibi GDI kaynaklarını ayırmak için bu işlevi geçersiz kılın. GDI nesnelerini, bunları kullanan her sayfa için [OnPrint](#onprint) üye işlevi içinden aygıt bağlamına seçin. Hem ekran ekranı hem de yazdırma gerçekleştirmek için aynı görünüm nesnesini kullanıyorsanız, her ekran için gereken GDI kaynakları için ayrı değişkenler kullanın; bu, yazdırma sırasında ekranı güncelleştirmenizi sağlar.

Yazıcı aygıtı bağlamının özelliklerine bağlı olarak başlatmaları gerçekleştirmek için de bu işlevi kullanabilirsiniz. Örneğin, belgeyi yazdırmak için gereken sayfa sayısı, kullanıcının Yazdır iletişim kutusunda belirttiği ayarlara (sayfa uzunluğu gibi) bağlı olabilir. Böyle bir durumda, normalde bunu yapacağınız [OnPreparePrinting](#onprepareprinting) üye işlevinde belge uzunluğunu belirtemezsiniz; iletişim kutusu ayarlarını temel alan yazıcı aygıtı bağlamı oluşturulana kadar beklemeniz gerekir. [OnBeginPrinting,](#onbeginprinting) yazıcı aygıtı bağlamını temsil eden [CDC](../../mfc/reference/cdc-class.md) nesnesine erişmenizi sağlayan ilk geçersiz işlevdir, böylece belge uzunluğunu bu işlevden ayarlayabilirsiniz. Belge uzunluğu bu saate kadar belirtilmemişse, yazdırma önizlemesi sırasında kaydırma çubuğu görüntülenmez.

## <a name="cviewondragenter"></a><a name="ondragenter"></a>CView::OndragEnter

Fare, hedef açılan pencerenin kaydırma olmayan bölgesine ilk girdiğinde çerçeve tarafından çağrılır.

```
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pDataObject*<br/>
[COleDataObject'in](../../mfc/reference/coledataobject-class.md) görünümün bırakma alanına sürüklendiğini işaret eden.

*dwKeyState*<br/>
Değiştirici anahtarların durumunu içerir. Bu, aşağıdakilerden herhangi birinin birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*Nokta*<br/>
Görünümün istemci alanına göre geçerli fare konumu.

### <a name="return-value"></a>Dönüş Değeri

DROPEFFECT numaralandırılmış türünden, kullanıcı nesneyi bu konuma düşürürse oluşacak düşüş türünü gösteren bir değer. Damla türü genellikle *dwKeyState*tarafından belirtilen geçerli anahtar durumuna bağlıdır. ANAHTAR DEVLETLERIN DROPEFFECT değerlerine standart eşleneği:

- DROPEFFECT_NONE Veri nesnesi bu pencereye bırakılamaz.

- MK_CONTROL &#124; MK_SHIFT için DROPEFFECT_LINK nesne ve sunucusu arasında bir bağlantı oluşturur.

- MK_CONTROL için DROPEFFECT_COPY Bırakılan nesnenin bir kopyasını oluşturur.

- MK_ALT için DROPEFFECT_MOVE Bırakılan nesnenin bir kopyasını oluşturur ve özgün nesneyi siler. Bu genellikle varsayılan bırakma efekti, görünüm bu veri nesnesi kabul edebilir.

Daha fazla bilgi için MFC Advanced Concepts örneği [OCLIENT'a](../../overview/visual-cpp-samples.md)bakın.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmak ve DROPEFFECT_NONE dönmektir.

[OnDragOver](#ondragover) üye işlevine gelecekteki çağrılara hazırlanmak için bu işlevi geçersiz kılın. `OnDragOver` Veri nesnesinden gerekli tüm veriler, üye işlevde daha sonra kullanılmak üzere şu anda alınmalıdır. Kullanıcıya görsel geri bildirim vermek için görünüm de şu anda güncelleştirilmelidir. Daha fazla bilgi [için, ole sürükle ve bırak makalesine bakın: Bir bırakma hedefi uygulayın.](../../mfc/drag-and-drop-ole.md#implement-a-drop-target)

## <a name="cviewondragleave"></a><a name="ondragleave"></a>CView::OnDragLeave

Fare, o pencere için geçerli bırakma alanından taşındığında sürükle işlemi sırasında çerçeve tarafından çağrılır.

```
virtual void OnDragLeave();
```

### <a name="remarks"></a>Açıklamalar

Geçerli [görünümün OnDragEnter](#ondragenter) veya [OnDragOver](#ondragover) çağrıları sırasında gerçekleştirilen nesneleri temizlemesi gerekiyorsa (örneğin, nesne sürüklenirken ve bırakılırken görsel kullanıcı geri bildirimlerini kaldırması gerekiyorsa bu işlevi geçersiz kılın.

## <a name="cviewondragover"></a><a name="ondragover"></a>CView::Ondragover

Fare açılan hedef penceresi nin üzerine taşındığında sürükleme işlemi sırasında çerçeve tarafından çağrılır.

```
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pDataObject*<br/>
[COleDataObject'in](../../mfc/reference/coledataobject-class.md) bırakma hedefinin üzerine sürüklendiğini işaret eden.

*dwKeyState*<br/>
Değiştirici anahtarların durumunu içerir. Bu, aşağıdakilerden herhangi birinin birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*Nokta*<br/>
Görünüm istemci alanına göre geçerli fare konumu.

### <a name="return-value"></a>Dönüş Değeri

DROPEFFECT numaralandırılmış türünden, kullanıcı nesneyi bu konuma düşürürse oluşacak düşüş türünü gösteren bir değer. Damla türü genellikle *dwKeyState*tarafından belirtildiği gibi geçerli anahtar durumuna bağlıdır. ANAHTAR DEVLETLERIN DROPEFFECT değerlerine standart eşleneği:

- DROPEFFECT_NONE Veri nesnesi bu pencereye bırakılamaz.

- MK_CONTROL &#124; MK_SHIFT için DROPEFFECT_LINK nesne ve sunucusu arasında bir bağlantı oluşturur.

- MK_CONTROL için DROPEFFECT_COPY Bırakılan nesnenin bir kopyasını oluşturur.

- MK_ALT için DROPEFFECT_MOVE Bırakılan nesnenin bir kopyasını oluşturur ve özgün nesneyi siler. Bu genellikle varsayılan bırakma efekti, görünüm veri nesnesi kabul edebilirsiniz.

Daha fazla bilgi için MFC Advanced Concepts örneği [OCLIENT'a](../../overview/visual-cpp-samples.md)bakın.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmak ve DROPEFFECT_NONE dönmektir.

Sürükleme işlemi sırasında kullanıcıya görsel geri bildirim vermek için bu işlevi geçersiz kılın. Bu işlev sürekli olarak çağrıldığından, içinde bulunan herhangi bir kod mümkün olduğunca optimize edilmelidir. Daha fazla bilgi [için, ole sürükle ve bırak makalesine bakın: Bir bırakma hedefi uygulayın.](../../mfc/drag-and-drop-ole.md#implement-a-drop-target)

## <a name="cviewondragscroll"></a><a name="ondragscroll"></a>CView::OnDragScroll

Noktanın kaydırma bölgesinde olup olmadığını belirlemek için [OnDragEnter](#ondragenter) veya [OnDragOver'ı](#ondragover) aramadan önce çerçeve tarafından çağrılır.

```
virtual DROPEFFECT OnDragScroll(
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*dwKeyState*<br/>
Değiştirici anahtarların durumunu içerir. Bu, aşağıdakilerden herhangi birinin birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*Nokta*<br/>
İmlecin konumunu, ekrana göre piksel olarak içerir.

### <a name="return-value"></a>Dönüş Değeri

DROPEFFECT numaralandırılmış türünden, kullanıcı nesneyi bu konuma düşürürse oluşacak düşüş türünü gösteren bir değer. Damla türü genellikle *dwKeyState*tarafından belirtilen geçerli anahtar durumuna bağlıdır. ANAHTAR DEVLETLERIN DROPEFFECT değerlerine standart eşleneği:

- DROPEFFECT_NONE Veri nesnesi bu pencereye bırakılamaz.

- MK_CONTROL &#124; MK_SHIFT için DROPEFFECT_LINK nesne ve sunucusu arasında bir bağlantı oluşturur.

- MK_CONTROL için DROPEFFECT_COPY Bırakılan nesnenin bir kopyasını oluşturur.

- MK_ALT için DROPEFFECT_MOVE Bırakılan nesnenin bir kopyasını oluşturur ve özgün nesneyi siler.

- DROPEFFECT_SCROLL Sürükle kaydırma işleminin gerçekleşmek üzere olduğunu veya hedef görünümünde oluştuğunu gösterir.

Daha fazla bilgi için MFC Advanced Concepts örneği [OCLIENT'a](../../overview/visual-cpp-samples.md)bakın.

### <a name="remarks"></a>Açıklamalar

Bu olay için özel davranış sağlamak istediğinizde bu işlevi geçersiz kılın. İmleç her pencerenin kenarlığı içindeki varsayılan kaydırma bölgesine sürüklendiğinde varsayılan uygulama pencereleri otomatik olarak kaydırır. Daha fazla bilgi [için, ole sürükle ve bırak makalesine bakın: Bir bırakma hedefi uygulayın.](../../mfc/drag-and-drop-ole.md#implement-a-drop-target)

## <a name="cviewondraw"></a><a name="ondraw"></a>CView::OnDraw

Belgenin bir görüntüsünü işlemek için çerçeve tarafından çağrılır.

```
virtual void OnDraw(CDC* pDC) = 0;
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Belgenin görüntüsünü işlemek için kullanılacak aygıt bağlamını işaret ediyor.

### <a name="remarks"></a>Açıklamalar

Çerçeve, ekran ekranı, yazdırma ve yazdırma önizlemesini gerçekleştirmek için bu işlevi çağırır ve her durumda farklı bir aygıt bağlamından geçer. Varsayılan uygulama yoktur.

Belgenin görünümünü görüntülemek için bu işlevi geçersiz kılmanız gerekir. *PDC* parametresinin işaret ettiği [CDC](../../mfc/reference/cdc-class.md) nesnesini kullanarak grafik aygıt arabirimi (GDI) aramaları yapabilirsiniz. Çizimden önce kalem veya yazı tipi gibi GDI kaynaklarını aygıt bağlamına seçebilir ve daha sonra bunları seçebilirsiniz. Çizim kodunuz genellikle aygıta bağımsız olabilir; diğer bir şekilde, görüntüyü ne tür bir aygıt görüntülediği hakkında bilgi gerektirmez.

Çizimi optimize etmek için, belirli bir dikdörtgenin çizilip çizilmeyeceğini öğrenmek için aygıt bağlamının [RectVisible](../../mfc/reference/cdc-class.md#rectvisible) üye işlevini arayın. Normal ekran ekranı ile yazdırma arasında ayrım yapmanız gerekiyorsa, aygıt bağlamının [IsPrinting](../../mfc/reference/cdc-class.md#isprinting) üye işlevini arayın.

## <a name="cviewondrop"></a><a name="ondrop"></a>CView::OnDrop

Kullanıcı geçerli bir bırakma hedefi üzerinde bir veri nesnesi serbest kaldığında çerçeve tarafından çağrılır.

```
virtual BOOL OnDrop(
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

'pDataObject* Açılan hedefe bırakılan [COleDataObject'e](../../mfc/reference/coledataobject-class.md) işaret ediyor.

*dropEffect*<br/>
Kullanıcının istediği bırakma efekti.

- DROPEFFECT_COPY Bırakılan veri nesnesinin bir kopyasını oluşturur.

- DROPEFFECT_MOVE Veri nesnesini geçerli fare konumuna taşır.

- DROPEFFECT_LINK Bir veri nesnesi ile sunucusu arasında bir bağlantı oluşturur.

*Nokta*<br/>
Görünüm istemci alanına göre geçerli fare konumu.

### <a name="return-value"></a>Dönüş Değeri

Damla başarılı olsaydı Nonzero; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz ve FALSE döndürür.

Görünümün istemci alanına bir OLE damlası etkisini uygulamak için bu işlevi geçersiz kılın. Veri nesnesi, Pano veri biçimleri için *pDataObject* üzerinden incelenebilir ve belirtilen noktada bırakılan veriler.

> [!NOTE]
> Bu görünüm sınıfında [OnDropEx'e](#ondropex) geçersiz kılma varsa çerçeve bu işlevi çağırmaz.

## <a name="cviewondropex"></a><a name="ondropex"></a>CView::OnDropex

Kullanıcı geçerli bir bırakma hedefi üzerinde bir veri nesnesi serbest kaldığında çerçeve tarafından çağrılır.

```
virtual DROPEFFECT OnDropEx(
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pDataObject*<br/>
Açılan hedefe bırakılan [COleDataObject'e](../../mfc/reference/coledataobject-class.md) işaret ediyor.

*dropVarsayılan*<br/>
Geçerli anahtar durumuna göre kullanıcının varsayılan bırakma işlemi için seçtiği etki. DROPEFFECT_NONE olabilir. Damla efektleri Açıklamalar bölümünde ele alınmıştır.

*dropList*<br/>
Bırakma kaynağının desteklediği bırakma efektlerinin listesi. Bırakma efekti değerleri bitwise OR **(&#124;**) işlemi kullanılarak birleştirilebilir. Damla efektleri Açıklamalar bölümünde ele alınmıştır.

*Nokta*<br/>
Görünüm istemci alanına göre geçerli fare konumu.

### <a name="return-value"></a>Dönüş Değeri

*Nokta*tarafından belirtilen konumdaki bırakma denemesinden kaynaklanan bırakma efekti. Bu, *dropEffectList*tarafından belirtilen değerlerden biri olmalıdır. Damla efektleri Açıklamalar bölümünde ele alınmıştır.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmak ve çerçeve [OnDrop](#ondrop) işleyicisi aramak gerektiğini belirtmek için bir kukla değeri ( -1 ) döndürmektir.

Sağ fare tuşu sürükle ve bırak efektini uygulamak için bu işlevi geçersiz kılın. Sağ fare tuşu sürükle ve bırak genellikle sağ fare düğmesi serbest bırakıldığında seçenekler menüsünü görüntüler.

Sağ fare `OnDropEx` düğmesi için gereken sorgu geçersiz kılma. [GetKeyState'i](/windows/win32/api/winuser/nf-winuser-getkeystate) arayabilir veya [OnDragEnter](#ondragenter) işleyicinizden sağ fare düğmesi durumunu saklayabilirsiniz.

- Sağ fare düğmesi aşağıdaysa, geçersiz kılmanız, bırakma kaynağıtarafından açılan efekt desteği sunan bir açılır menü görüntülemelidir.

  - Damla kaynağı tarafından desteklenen bırakma efektlerini belirlemek için *dropList'i* inceleyin. Açılan menüde yalnızca bu eylemleri etkinleştirin.

  - *DropDefault'a*dayalı varsayılan eylemi ayarlamak için [SetMenuDefaultItem'i](/windows/win32/api/winuser/nf-winuser-setmenudefaultitem) kullanın.

  - Son olarak, açılır menüden kullanıcı seçiminde belirtilen eylemi yapın.

- Sağ fare düğmesi çalışmıyorsa, geçersiz kılmanız bunu standart bir bırakma isteği olarak işlemelidir. *DropDefault'da*belirtilen bırakma efektini kullanın. Alternatif olarak, geçersiz kılma nız bu bırakma işlemini `OnDrop` işleyeceğini belirtmek için kukla değerini (-1) döndürebilir.

Pano `COleDataObject` veri biçimini ve belirtilen noktaya bırakılan verileri incelemek için *pDataObject'i* kullanın.

Bırakma efektleri, bir bırakma işlemiyle ilişkili eylemi açıklar. Aşağıdaki bırakma efektleri listesine bakın:

- DROPEFFECT_NONE Bir damlaya izin verilmeyecekti.

- DROPEFFECT_COPY Bir kopyalama işlemi gerçekleştirilir.

- DROPEFFECT_MOVE Bir hareket işlemi gerçekleştirilir.

- DROPEFFECT_LINK Bırakılan verilerden özgün verilere bir bağlantı kurulabilir.

- DROPEFFECT_SCROLL Bir sürükleme kaydırma işleminin gerçekleşmek üzere olduğunu veya hedefte meydana geldiğini gösterir.

Varsayılan menü komutunu ayarlama hakkında daha fazla bilgi için, windows sdk ve [CMenu::GetSafeHmenu](../../mfc/reference/cmenu-class.md#getsafehmenu) bu birimde [SetMenuDefaultItem](/windows/win32/api/winuser/nf-winuser-setmenudefaultitem) bakın.

## <a name="cviewonendprinting"></a><a name="onendprinting"></a>CView::OnEndPrinting

Belge yazdırıldıktan veya önizleme yapıldıktan sonra çerçeve tarafından çağrılır.

```
virtual void OnEndPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Yazıcı aygıtı bağlamını işaret eder.

*Pınfo*<br/>
Geçerli yazdırma işini açıklayan bir [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısına işaret eden.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması hiçbir şey yapmaz. [OnBeginPrinting](#onbeginprinting) üye işlevinde ayırdığınız GDI kaynaklarını serbest kılmak için bu işlevi geçersiz kılın.

## <a name="cviewonendprintpreview"></a><a name="onendprintpreview"></a>CView::OnEndPrintPreview

Kullanıcı yazdırma önizleme modundan çıktığında çerçeve tarafından çağrılır.

```
virtual void OnEndPrintPreview(
    CDC* pDC,
    CPrintInfo* pInfo,
    POINT point,
    CPreviewView* pView);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Yazıcı aygıtı bağlamını işaret eder.

*Pınfo*<br/>
Geçerli yazdırma işini açıklayan bir [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısına işaret eden.

*Nokta*<br/>
Sayfadaki en son önizleme modunda görüntülenen noktayı belirtir.

*pGörünüm*<br/>
Önizleme için kullanılan görünüm nesnesine işaret ediyor.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması [OnEndPrinting](#onendprinting) üye işlevini çağırır ve yazdırma önizlemesi başlamadan önce ana çerçeve penceresini olduğu duruma geri getirir. Önizleme modu sonlandırıldığında özel işleme gerçekleştirmek için bu işlevi geçersiz kılın. Örneğin, önizleme modundan normal ekran moduna geçerken kullanıcının belgedeki konumunu korumak istiyorsanız, *nokta* parametresi tarafından açıklanan `m_nCurPage` konuma `CPrintInfo` ve *pInfo* parametresinin işaret ettiği yapının üyesine kaydırabilirsiniz.

Geçersiz kılmanızın `OnEndPrintPreview` taban sınıf sürümünü genellikle işlevin sonunda çağırın.

## <a name="cviewoninitialupdate"></a><a name="oninitialupdate"></a>CView::OnInitialUpdate

Görünüm belgeye ilk iliştirildikten sonra çerçeve tarafından çağrılır, ancak görünüm ilk görüntülenmeden önce.

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan [uygulaması, OnUpdate](#onupdate) üye işlevini ipucu bilgisi olmadan çağırır (diğer bir şekilde *lHint* parametresi için 0 varsayılan değerlerini ve *pHint* parametresi için NULL'u kullanarak). Belge hakkında bilgi gerektiren tek seferlik başlatmayı gerçekleştirmek için bu işlevi geçersiz kılın. Örneğin, uygulamanızda sabit boyutlu belgeler varsa, belge boyutuna bağlı olarak görünümün kaydırma sınırlarını başlatmayı sağlamak için bu işlevi kullanabilirsiniz. Uygulamanız değişken boyutlu belgeleri destekliyorsa, belge her değiştiğinde kaydırma sınırlarını güncelleştirmek için [OnUpdate'i](#onupdate) kullanın.

## <a name="cviewonpreparedc"></a><a name="onpreparedc"></a>CView::OnPrepareDC

[OnDraw](#ondraw) üye işlevi ekran ekranı için çağrılmadan ve Yazdırma veya yazdırma önizlemesi sırasında her sayfa için [OnPrint](#onprint) üye işlevi çağrılmadan önce çerçeve tarafından çağrılır.

```
virtual void OnPrepareDC(
    CDC* pDC,
    CPrintInfo* pInfo = NULL);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Belgenin görüntüsünü işlemek için kullanılacak aygıt bağlamını işaret ediyor.

*Pınfo*<br/>
Yazdırma veya yazdırma önizlemesi için çağrılıyorsa, `OnPrepareDC` geçerli yazdırma işini açıklayan bir [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısına işaret; `m_nCurPage` üye, basılacak sayfayı belirtir. Ekran ekranı için `OnPrepareDC` çağrılmakta ise bu parametre NULL'dur.

### <a name="remarks"></a>Açıklamalar

İşlev ekran ekranı için çağrılırsa, bu işlevin varsayılan uygulaması hiçbir şey yapmaz. Ancak, bu işlev, aygıt bağlamının özniteliklerini ayarlamak için [CScrollView](../../mfc/reference/cscrollview-class.md)gibi türemiş sınıflarda geçersiz kılınır; sonuç olarak, geçersiz kılmanın başlangıcında her zaman taban sınıf uygulamasını çağırmalısınız.

İşlev yazdırma için çağrılırsa, varsayılan uygulama *pInfo* parametresinde depolanan sayfa bilgilerini inceler. Belgenin uzunluğu belirtilmemişse, `OnPrepareDC` belgenin bir sayfa uzunluğunda olduğunu varsayar ve bir sayfa yazdırıldıktan sonra yazdırma döngüyü durdurur. İşlev, yapının `m_bContinuePrinting` üyesini FALSE olarak ayarlayarak yazdırma döngüsünün durmasını sağlar.

Aşağıdaki `OnPrepareDC` nedenlerden herhangi biri için geçersiz kılma:

- Belirtilen sayfa için gerektiği gibi aygıt bağlamının özniteliklerini ayarlamak için. Örneğin, eşleme modunu veya aygıt bağlamının diğer özelliklerini ayarlamanız gerekiyorsa, bunu bu işlevde yapın.

- Baskı zamanı pagination gerçekleştirmek için. Normalde [Yazdırma Yazdır](#onprepareprinting) üye işlevini kullanarak yazdırma başladığında belgenin uzunluğunu belirtirsiniz. Ancak, belgenin ne kadar süreceğini önceden bilmiyorsanız (örneğin, veritabanından belirsiz sayıda kayıt yazdırırken), `OnPrepareDC` yazdırılırken belgenin sonunu sınamak için geçersiz kılın. Yazdırılacak belgenin sayısı kalmadıkça, yapının `m_bContinuePrinting` üyesini `CPrintInfo` FALSE olarak ayarlayın.

- Kaçış kodlarını sayfa sayfa göndermek için. Kaçış kodlarını `OnPrepareDC`göndermek için `Escape` *pDC* parametresinin üye işlevini arayın.

Geçersiz kılmanın başındaki taban sınıf sürümünü `OnPrepareDC` arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#183](../../mfc/codesnippet/cpp/cview-class_1.cpp)]

## <a name="cviewonprepareprinting"></a><a name="onprepareprinting"></a>CView::OnPreparePrinting

Belge yazdırılmadan veya önizlemeden önce çerçeve tarafından çağrılır.

```
virtual BOOL OnPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*Pınfo*<br/>
Geçerli yazdırma işini açıklayan bir [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısına işaret eden.

### <a name="return-value"></a>Dönüş Değeri

Sıfır olmayan yazdırmaya başlamak için; Yazdırma işi iptal edildiyse 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz.

Yazdırma ve yazdırma önizlemesini etkinleştirmek için bu işlevi geçersiz kılmanız gerekir. [DoPreparePrinting](#doprepareprinting) üye işlevini çağırın, *pInfo* parametresini geçirin ve sonra iade değerini döndürün; `DoPreparePrinting` Yazdır iletişim kutusunu görüntüler ve bir yazıcı aygıtı bağlamı oluşturur. Varsayılan değerler dışındaki değerlerle Yazdır iletişim kutusunu başlatmayı istiyorsanız, *değerler pInfo*üyelerine atayın. Örneğin, belgenin uzunluğunu biliyorsanız, aramadan `DoPreparePrinting`önce değeri *pInfo'nun* [SetMaxPage](../../mfc/reference/cprintinfo-structure.md#setmaxpage) üye işlevine geçirin. Bu değer, Yazdır iletişim kutusunun Aralık kısmındaki To: kutusunda görüntülenir.

`DoPreparePrinting`önizleme işi için Yazdır iletişim kutusunu görüntülemez. Yazdırma işi için Yazdırma iletişim kutusunu atlamak istiyorsanız, `m_bPreview` *pInfo* üyesinin FALSE olup olmadığını denetleyin ve bunu `DoPreparePrinting`geçirmeden önce TRUE olarak ayarlayın; daha sonra FALSE'a sıfırlayın.

Yazıcı aygıtı bağlamını `CDC` temsil eden nesneye erişim gerektiren başlatmalar gerçekleştirmeniz gerekiyorsa (örneğin, belgenin uzunluğunu belirtmeden önce sayfa boyutunu `OnBeginPrinting` bilmeniz gerekiyorsa), üye işlevi geçersiz kılın.

*pInfo* parametresinin `m_nNumPreviewPages` veya `m_strPageDesc` üyelerinin değerini ayarlamak istiyorsanız, bunu aradıktan `DoPreparePrinting`sonra yapın. `DoPreparePrinting` Üye işlev, `m_nNumPreviewPages` uygulamanın. INI dosya `m_strPageDesc` ve varsayılan değeri ayarlar.

### <a name="example"></a>Örnek

  Geçersiz `OnPreparePrinting` kılma `DoPreparePrinting` ve geçersiz kılmadan çağrı böylece çerçeve bir Yazdır iletişim kutusu görüntüler ve sizin için bir yazıcı DC oluşturun.

[!code-cpp[NVC_MFCDocView#184](../../mfc/codesnippet/cpp/cview-class_2.cpp)]

Belgenin kaç sayfa içerdiğini biliyorsanız, aramadan `OnPreparePrinting` `DoPreparePrinting`önce en büyük sayfayı ayarlayın. Çerçeve, Yazdır iletişim kutusunun "to" kutusunda en yüksek sayfa numarasını görüntüler.

[!code-cpp[NVC_MFCDocView#185](../../mfc/codesnippet/cpp/cview-class_3.cpp)]

## <a name="cviewonprint"></a><a name="onprint"></a>CView::Onprint

Belgenin bir sayfasını yazdırmak veya önizlemek için çerçeve tarafından çağrılır.

```
virtual void OnPrint(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Yazıcı aygıtı bağlamını işaret eder.

*Pınfo*<br/>
Geçerli yazdırma `CPrintInfo` işini açıklayan bir yapıyı işaret edin.

### <a name="remarks"></a>Açıklamalar

Yazdırılan her sayfa için çerçeve, [OnPrepareDC](#onpreparedc) üye işlevini aradıktan hemen sonra bu işlevi çağırır. Yazdırılan sayfa, `m_nCurPage` *pInfo'nun* işaret ettiği [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) yapısının üyesi tarafından belirtilir. Varsayılan uygulama [OnDraw](#ondraw) üye işlevini çağırır ve yazıcı aygıtı bağlamını geçirir.

Aşağıdaki nedenlerden herhangi biri için bu işlevi geçersiz kılın:

- Çok sayfalı belgelerin yazdırılabına izin vermek için. Belgenin yalnızca şu anda yazdırılmakta olan sayfaya karşılık gelen bölümünü oluşturma. İşlemi gerçekleştirmek `OnDraw` için kullanıyorsanız, görüntü bağlantı noktası kaynağını belgenin yalnızca uygun bölümünün yazdırılaması için ayarlayabilirsiniz.

- Yazdırılan görüntünün ekran görüntüsünden farklı görünmesini sağlamak için (uygulamanız WYSIWYG değilse). Yazıcı aygıtı bağlamını , `OnDraw`ekranda gösterilmeyen öznitelikleri kullanarak görüntüyü işlemek için aygıt bağlamını kullanmak yerine.

   Ekran ekranı için kullanmadığınız yazdırma için GDI kaynaklarına ihtiyacınız varsa, çizim yapmadan önce bunları aygıt bağlamına seçin ve daha sonra bunları seçin. Bu GDI kaynakları [OnBeginPrinting'de](#onbeginprinting) ayrılmalı ve [OnEndPrinting'de](#onendprinting)yayımlanmalıdır.

- Üstbilgi veya altbilgi uygulamak için. Yazdırabileceği alanı `OnDraw` kısıtlayarak işleme yi yapmaya devam edebilirsiniz.

*pInfo* `m_rectDraw` parametresinin üyesinin sayfanın yazdırılabilir alanını mantıksal birimler halinde açıkladığını unutmayın.

Geçersiz kılmanızı `OnPrepareDC` `OnPrint`aramayın; aramadan `OnPrint` `OnPrepareDC` önce çerçeve otomatik olarak çağırır.

### <a name="example"></a>Örnek

Geçersiz kılınan `OnPrint` bir işlev için aşağıdaki bir iskelet tir:

[!code-cpp[NVC_MFCDocView#186](../../mfc/codesnippet/cpp/cview-class_4.cpp)]

Başka bir örnek için, [Bkz. CRichEditView::PrintInsideRect](../../mfc/reference/cricheditview-class.md#printinsiderect).

## <a name="cviewonscroll"></a><a name="onscroll"></a>CView::OnScroll

Kaydırmanın mümkün olup olmadığını belirlemek için çerçeve tarafından çağrılır.

```
virtual BOOL OnScroll(
    UINT nScrollCode,
    UINT nPos,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parametreler

*nScrollCode*<br/>
Kullanıcının kaydırma isteğini gösteren bir kaydırma-barkod kodu. Bu parametre iki bölümden oluşur: yatay olarak gerçekleşen kaydırma türünü belirleyen düşük sıralı bayt ve dikey olarak gerçekleşen kaydırma türünü belirleyen yüksek sıralı bayt:

- SB_BOTTOM Kayar alta.

- SB_LINEDOWN Bir satır aşağı kaydırır.

- SB_LINEUP Bir sıra yukarı kaydırır.

- SB_PAGEDOWN Bir sayfa aşağı kaydırır.

- SB_PAGEUP bir sayfa yukarı kaydırır.

- SB_THUMBTRACK Kaydırma kutusunu belirtilen konuma sürükler. Geçerli konum *nPos'ta*belirtilir.

- SB_TOP Üst lere kaydırır.

*nPos*<br/>
Kaydırma-barkod SB_THUMBTRACK varsa geçerli kaydırma kutusu konumunu içerir; aksi takdirde kullanılmaz. İlk kaydırma aralığına bağlı olarak, *nPos* negatif olabilir ve gerekirse bir **int'e** atılmalıdır.

*bDoScroll*<br/>
Belirtilen kaydırma eylemini gerçekten yapıp yapmamanız gerektiğini belirler. TRUE ise, kaydırma yer almalıdır; FALSE ise, o zaman kaydırma oluşmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

*bDoScroll* TRUE ise ve görünüm gerçekten kaydırılmışsa, sıfırsız döndürün; aksi takdirde 0. *bDoScroll* FALSE ise, kaydırmayı gerçekten yapmasanız bile *bDoScroll* DOĞRU olsaydı döndürüleceğiniz değeri döndürün.

### <a name="remarks"></a>Açıklamalar

Bir durumda bu işlev, görünüm bir kaydırma çubuğu iletisi aldığında *bDoScroll* kümesi ile TRUE'ya ayarlanmış çerçeve tarafından çağrılır. Bu durumda, görünümü gerçekten kaydırmanız gerekir. Diğer durumda bu işlev, kaydırma gerçekleşmeden önce bir OLE öğesi başlangıçta bir bırakma hedefinin otomatik kaydırma bölgesine sürüklendiğinde *bDoScroll* kümesi yle FALSE olarak adlandırılır. Bu durumda, görünümü gerçekten kaydırmamalısınız.

## <a name="cviewonscrollby"></a><a name="onscrollby"></a>CView::Onscrollby

Kullanıcı, bir OLE öğesini görünümün geçerli kenarlıklarına sürükleyerek veya dikey veya yatay kaydırma çubuklarını manipüle ederek belgenin mevcut görünümünün ötesindeki bir alanı görüntülediğinde çerçeve tarafından çağrılır.

```
virtual BOOL OnScrollBy(
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Parametreler

*boyutKaydırma*<br/>
Yatay ve dikey olarak kaydırılan piksel sayısı.

*bDoScroll*<br/>
Görünümün kaydırma nın gerçekleşip gerçekleşmediğini belirler. DOĞRU ise, kaydırma gerçekleşir; FALSE ise, kaydırma oluşmaz.

### <a name="return-value"></a>Dönüş Değeri

Görünüm kaydırılabilir mümkünse sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Türetilen sınıflarda bu yöntem, görünümün kullanıcının istediği yönde kaydırılabilir olup olmadığını denetler ve gerekirse yeni bölgeyi güncelleştirir. Bu işlev, gerçek kaydırma isteğini gerçekleştirmek için [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) ve [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) tarafından otomatik olarak çağrılır.

Bu yöntemin varsayılan uygulaması görünümü değiştirmez, ancak çağrılmazsa, görünüm türetilmiş bir `CScrollView`sınıfta kaydırmaz.

Belge genişliği veya yüksekliği 32767 pikseli aşarsa, geçersiz bir `OnScrollBy` *boyutKaydırma* bağımsız değişkeni ile çağrıldığı için 32767'yi geçmek başarısız olur.

## <a name="cviewonupdate"></a><a name="onupdate"></a>CView::Onupdate

Görünümün belgesi değiştirildikten sonra çerçeve tarafından çağrılan; Bu işlev [CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) tarafından adlandırılır ve görünümün bu değişiklikleri yansıtacak şekilde ekranını güncelleştirmesine olanak tanır.

```
virtual void OnUpdate(
    CView* pSender,
    LPARAM lHint,
    CObject* pHint);
```

### <a name="parameters"></a>Parametreler

*pSender*<br/>
Belgeyi değiştiren görünüme veya tüm görünümler güncelleştirilecekse NULL'a işaret ediyor.

*Lhint*<br/>
Değişiklikler hakkında bilgi içerir.

*pHint*<br/>
Değişiklikler hakkında bilgi depolayan bir nesneyi işaret eder.

### <a name="remarks"></a>Açıklamalar

Ayrıca [OnInitialUpdate](#oninitialupdate)varsayılan uygulaması tarafından denir. Varsayılan uygulama, sonraki WM_PAINT iletisi aldığında boyama için işaretleme, tüm istemci alanı geçersiz kılınz. Yalnızca belgenin değiştirilen bölümleriyle eşlenebilen bölgeleri güncelleştirmek istiyorsanız bu işlevi geçersiz kılın. Bunu yapmak için ipucu parametrelerini kullanarak değişiklikler hakkında bilgi geçirmeniz gerekir.

*lHint'i*kullanmak için, özel ipucu değerlerini, genellikle bir bitmaskesi veya numaralandırılmış türü tanımlayın ve belgenin bu değerlerden birini geçirmesini sağlar. *pHint*kullanmak için, [CObject](../../mfc/reference/cobject-class.md) bir ipucu sınıfı türetmek ve belge bir ipucu nesnesine bir işaretçi geçmek var; geçersiz kılındığında, `OnUpdate`İpucu nesnesinin çalışma zamanı türünü belirlemek için [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) üye işlevini kullanın.

Genellikle doğrudan `OnUpdate`herhangi bir çizim gerçekleştirmemelisiniz. Bunun yerine, aygıt koordinatlarında güncelleştirilmesi gereken alanı açıklayan dikdörtgeni belirleyin; [Bu dikdörtgeni CWnd'ye geçirin::Geçersiz Rect](../../mfc/reference/cwnd-class.md#invalidaterect). Bu, [bir sonraki WM_PAINT](/windows/win32/gdi/wm-paint) iletisi aldığında boyama oluşmasına neden olur.

*lHint* 0 ise ve *pHint* NULL ise, belge genel bir güncelleştirme bildirimi gönderdi. Bir görünüm genel bir güncelleştirme bildirimi alıyorsa veya ipuçlarını çözemiyorsa, tüm istemci alanını geçersiz kılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[CSplitterWnd Sınıfı](../../mfc/reference/csplitterwnd-class.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[Kişniş Sınıfı](../../mfc/reference/cdocument-class.md)
