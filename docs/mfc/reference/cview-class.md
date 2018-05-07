---
title: CView sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ca94e9d1f870fe028faec413a79f13d8a3b8eaa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cview-class"></a>CView sınıfı
Temel işlevleri için kullanıcı tanımlı görünüm sınıfları sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class AFX_NOVTABLE CView : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CView::CView](#cview)|Oluşturan bir `CView` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CView::DoPreparePrinting](#doprepareprinting)|Yazdır iletişim kutusu görüntüler ve yazıcı cihaz bağlamı oluşturur; geçersiz kılarken çağrı `OnPreparePrinting` üye işlevi.|  
|[CView::GetDocument](#getdocument)|Görünüm ile ilişkilendirilen belgeyi döndürür.|  
|[CView::IsSelected](#isselected)|Bir belge öğesi seçili olup olmadığını sınar. OLE desteği için gereklidir.|  
|[CView::OnDragEnter](#ondragenter)|Öğe bir görünüm sürükle ve bırak bölgeye ilk sürüklendiğinde çağrılır.|  
|[CView::OnDragLeave](#ondragleave)|Sürüklenen öğenin bir görünüm sürükle ve bırak bölgede çıktığında çağrılır.|  
|[CView::OnDragOver](#ondragover)|Öğe bir görünüm sürükle ve bırak bölge sürüklendiğinde çağrılır.|  
|[CView::OnDragScroll](#ondragscroll)|İmleç kaydırma bölgeye penceresinin sürüklenen olup olmadığını belirlemek için çağrılır.|  
|[CView::OnDrop](#ondrop)|Öğe bir görünüm, varsayılan işleyici sürükle ve bırak bölgeye bırakıldı çağrılır.|  
|[CView::OnDropEx](#ondropex)|Öğe bir görünüm birincil işleyici sürükle ve bırak bölgeye bırakıldı çağrılır.|  
|[CView::OnInitialUpdate](#oninitialupdate)|Bir görünüm ilk belgeye eklendikten sonra çağrılır.|  
|[CView::OnPrepareDC](#onpreparedc)|Önce adlı `OnDraw` ekran görüntüsü için üye fonksiyonu olarak adlandırılan veya `OnPrint` üye işlevi, yazdırma veya Baskı Önizleme için çağrılır.|  
|[CView::OnScroll](#onscroll)|OLE öğeleri görünüm Kenarlıklar sürüklendiğinde çağrılır.|  
|[CView::OnScrollBy](#onscrollby)|Etkin yerinde OLE öğeleri içeren bir görünüm kaydırılan çağrılır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CView::OnActivateFrame](#onactivateframe)|Görünümü içeren çerçeve penceresi etkin veya devre dışı olduğunda çağrılır.|  
|[CView::OnActivateView](#onactivateview)|Bir görünüm etkinleştirildiğinde çağrılır.|  
|[CView::OnBeginPrinting](#onbeginprinting)|Yazdırma işi başladığında çağrılır; Grafik cihaz arabirimi (GDI) kaynakları ayırmak için geçersiz kılın.|  
|[CView::OnDraw](#ondraw)|Ekran görüntüsü, yazdırma ve Baskı Önizleme için belgenin bir görüntü oluşturmak için çağrılır. Gerekli uygulama.|  
|[CView::OnEndPrinting](#onendprinting)|Yazdırma işi sona erdiğinde çağrılır; GDI kaynaklarını serbest bırakma için geçersiz kılın.|  
|[CView::OnEndPrintPreview](#onendprintpreview)|Önizleme modunda çıkıldı çağrılır.|  
|[CView::OnPreparePrinting](#onprepareprinting)|Bir belge yazdırılması veya önizlemesi önce çağrılır; Yazdır iletişim kutusunu başlatmak için geçersiz kılın.|  
|[CView::OnPrint](#onprint)|Belge sayfasının yazdıramaz veya çağrılır.|  
|[CView::OnUpdate](#onupdate)|Kendi belge boyunca görünüm bildirmek için adlı değiştirdi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir görünüm belgeye eklenir ve belge ve kullanıcı arasındaki bir aracı gibi davranır: görünüm belgeyi ekran veya yazıcı görüntüsünü oluşturur ve işlemleri belge bağlı olarak kullanıcı girişini yorumlama.  
  
 Bir çerçeve penceresinde alt görülmektedir. Birden çok görünüm Bölümlendirici pencere durumunda olduğu gibi bir çerçeve penceresinde paylaşabilirsiniz. View sınıfı, bir çerçeve pencere sınıfı ve belge sınıfı arasındaki ilişkiyi tarafından oluşturulan bir `CDocTemplate` nesnesi. Kullanıcı yeni bir pencerede açar veya varolan böler olduğunda bir framework yeni bir görünüm oluşturur ve belgeye ekler.  
  
 Bir görünüm yalnızca bir belgeye eklenebilir, ancak bir belgede aynı anda bağlı birden çok görünüm olabilir — örneğin, belgeyi bir Bölümlendirici pencere veya birden çok belge arabirimi (MDI) uygulaması birden fazla alt pencerede görüntülenir. Uygulamanız için verilen belge türü farklı türde destekler; Örneğin, bir sözcük işlem programı hem bir belgenin tam metin görünümü hem de yalnızca bölüm başlıkları gösteren bir anahat görünümü sağlayabilir. Bölümlendirici pencere kullanırsanız, bu farklı türde ayrı çerçeve pencereleri veya ayrı bir tek çerçeve pencere bölmeleri yerleştirilebilir.  
  
 Bir görünüm giriş klavye girişi, fare giriş veya giriş sürükle ve bırak gibi komutları aracılığıyla menüleri, araç çubukları ya da kaydırma çubukları gibi birkaç farklı türde işlenmesinden sorumludur olabilir. Bir görünüm, çerçeve penceresi tarafından iletilen komutlarını alır. Görünüm verilen komut işlemez, ilgili belge komutuna iletir. Tüm komut hedefleri gibi bir ileti eşlemesi aracılığıyla iletileri bir görünümü işler.  
  
 Görünüm sorumludur görüntüleme ve belgenin verileri değiştirme ancak onu depolamayın. Belge verilerini hakkında gerekli bilgileri görünümüyle sağlar. Belgenin veri doğrudan üyeleri veya üye işlevleri çağırmak view sınıfı için belge sınıfında sağlayabilir görünüm erişimi sağlayabilirsiniz.  
  
 Bir belgenin veriler değiştiğinde, değişikliklerin sorumlu görünüm genellikle çağırır [CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) işlevini çağırarak tüm görünümleri bildirir belge için `OnUpdate` için üye işlevi Her. Varsayılan uygulaması `OnUpdate` görünümün tüm istemci alanını geçersiz kılar. Yalnızca istemci alanını belgenin değiştirilmiş bölümleri eşleme bölgelerinin geçersiz kılmak için geçersiz kılabilirsiniz.  
  
 Kullanılacak `CView`, buradan bir sınıf türetin ve uygulama `OnDraw` ekran görüntüsü gerçekleştirmek için üye işlevi. Aynı zamanda `OnDraw` yazdırmayı ve baskı önizlemeyi gerçekleştirmek için. Yazdırma ve belgenizi Önizleme için yazdırma döngü framework işler.  
  
 Bir görünümü ile kaydırma çubuğu iletilerini işleme [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) ve [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) üye işlevleri. Kaydırma çubuğu ileti bu işlevler işleme uygulayabilir veya kullanabilirsiniz `CView` türetilmiş sınıf [CScrollView](../../mfc/reference/cscrollview-class.md) sizin için kaydırma işlemek için.  
  
 Yanında `CScrollView`, Microsoft Foundation Class Kitaplığı türetilmiş dokuz sınıfları sağlar `CView`:  
  
- [CCtrlView](../../mfc/reference/cctrlview-class.md), belge - görünümünü mimarisiyle ağaç, liste ve zengin düzenleme denetimleri kullanımını veren bir görünümü.  
  
- [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md), iletişim kutusu denetimleri veritabanı kayıtlarını görüntüleyen bir görünüm.  
  
- [CEditView](../../mfc/reference/ceditview-class.md), basit bir çok satırlı metin düzenleyici sağlayan bir görünüm. Kullanabileceğiniz bir `CEditView` nesnesi bir görünüm belgesinde yanı sıra bir iletişim kutusu denetiminde olarak.  
  
- [Cformview'yu](../../mfc/reference/cformview-class.md), iletişim kutusu denetimleri içeren ve bir iletişim şablon kaynağını temel kaydırılabilir bir görünüm.  
  
- [CListView](../../mfc/reference/clistview-class.md), belge - görünüm mimarisi liste denetimleri ile kullanımını veren bir görünümü.  
  
- [CRecordView](../../mfc/reference/crecordview-class.md), iletişim kutusu denetimleri veritabanı kayıtlarını görüntüleyen bir görünüm.  
  
- [CRichEditView](../../mfc/reference/cricheditview-class.md), belge - görünümünü mimarisiyle zengin düzenleme denetimleri kullanımını veren bir görünümü.  
  
- [CScrollView](../../mfc/reference/cscrollview-class.md), otomatik olarak kaydırma destek sağlayan bir görünüm.  
  
- [CTreeView](../../mfc/reference/ctreeview-class.md), belge - görünüm mimarisi ağaç denetimleri ile kullanımını veren bir görünümü.  
  
 `CView` Sınıfı ayrıca adlı bir türetilmiş uygulamasına sınıf sahip **CPreviewView**, hangi çerçevesi tarafından Baskı Önizleme gerçekleştirmek için kullanılır. Bu sınıf, Baskı Önizleme penceresine tek veya çift sayfa Önizleme'de, araç çubuğu gibi benzersiz özellikleri için destek sağlar ve yakınlaştırma, bu önizlemede görüntülenen görüntünün büyütme olan. Arama veya herhangi bir geçersiz kılma gerekmez **CPreviewView**'s üye işlevleri (örneğin, baskı önizleme modunda düzenleme desteklemek istiyorsanız) Baskı Önizleme için kendi arabirimi uygulamak istemediğiniz sürece. Kullanma hakkında daha fazla bilgi için `CView`, bkz: [belge/görünüm mimarisinin](../../mfc/document-view-architecture.md) ve [yazdırma](../../mfc/printing.md). Ayrıca bkz [Teknik Not 30](../../mfc/tn030-customizing-printing-and-print-preview.md) Baskı Önizlemeyi özelleştirme hakkında daha fazla bilgi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CView`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cview"></a>  CView::CView  
 Oluşturan bir `CView` nesnesi.  
  
```  
CView();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bir çerçeve penceresi oluşturulduğunda veya bir pencereyi bölmek framework Oluşturucusu çağırır. Geçersiz kılma [OnInitialUpdate](#oninitialupdate) üye işlevi belge eklendikten sonra başlatın.  
  
##  <a name="doprepareprinting"></a>  CView::DoPreparePrinting  
 Bu işlev geçersiz kılma çağrı [OnPreparePrinting](#onprepareprinting) Yazdır iletişim kutusunu çağırmak ve bir yazıcı cihaz bağlamı oluşturmak için.  
  
```  
BOOL DoPreparePrinting(CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 `pInfo`  
 İşaret eden bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) geçerli yazdırma işi açıklar yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazdırma veya Baskı Önizleme başlayabilir, sıfır olmayan; 0 işlemi iptal edildi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevin davranışı olup, yazdırma veya Baskı Önizleme için çağrıldığından üzerinde bağlıdır (tarafından belirtilen **m_bPreview** üyesi `pInfo` parametresi). Dosyanın yazdırılması varsa, bu işlev değerleri kullanarak yazdırma iletişim kutusunu çağırır [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) , yapı `pInfo` ; işaret kullanıcı iletişim kutusunu kapattıktan sonra işlev yazıcı cihaz bağlamı oluşturur. iletişim kutusunda belirtilen kullanıcı ayarlarınızı temel alan ve bu cihaz bağlamı aracılığıyla döndürür `pInfo` parametresi. Bu cihaz bağlamı belgeyi yazdırmak için kullanılır.  
  
 Bir dosyanın önizlemesi, bu işlev geçerli yazıcı ayarlarını kullanarak yazıcı cihaz bağlamı oluşturur; Bu cihaz bağlamı, Önizleme süresince yazıcı benzetimi için kullanılır.  
  
##  <a name="getdocument"></a>  CView::GetDocument  
 Görünümün belge için bir işaretçi almak için bu işlevini çağırın.  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [CDocument](../../mfc/reference/cdocument-class.md) görünümle ilişkili nesne. **NULL** görünümü belgeye bağlı değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu belgenin üye işlevleri çağırma olanak sağlar.  
  
##  <a name="isselected"></a>  CView::IsSelected  
 Belirtilen belge öğesi seçili olup olmadığını denetlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDocItem`  
 Sınanan belge öğesi noktalarına.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen belge öğesi seçiliyse, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulamasını döndürür **FALSE**. Seçim kullanarak uyguluyorsanız, bu işlevi geçersiz kılma [CDocItem](../../mfc/reference/cdocitem-class.md) nesneleri. OLE öğeleri görünümü içeriyorsa, bu işlev geçersiz kılmanız gerekir.  
  
##  <a name="onactivateframe"></a>  CView::OnActivateFrame  
 Görünümü içeren çerçeve penceresi etkin veya devre dışı olduğunda çerçevesi tarafından çağrılır.  
  
```  
virtual void OnActivateFrame(
    UINT nState,  
    CFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `nState`  
 Çerçeve penceresi yüklenmekte olan olup olmadığını belirtir etkin veya devre dışı. Aşağıdaki değerlerden biri olabilir:  
  
- **WA_INACTIVE** çerçeve penceresi devre dışı bırakılıyor.  
  
- **WA_ACTIVE** fare tıklayın (örneğin, pencerenin seçmek için klavye arabirimi tarafından kullanımını) dışında çerçeve penceresi bazı yöntemle etkinleştiriliyor.  
  
- **WA_CLICKACTIVE** çerçeve penceresi tarafından fare tıklatma etkinleştiriliyor  
  
 `pFrameWnd`  
 Etkinleştirilecek olan çerçeve penceresi işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Görünüm ile ilişkilendirilen çerçeve penceresi etkin veya devre dışı olduğunda özel işlem gerçekleştirmek istiyorsanız, bu üye işlevi geçersiz kılar. Örneğin, [Cformview'yu](../../mfc/reference/cformview-class.md) kaydeder ve odaklanmış denetimi yükler, bu geçersiz kılma gerçekleştirir.  
  
##  <a name="onactivateview"></a>  CView::OnActivateView  
 Bir görünüm etkinleştirilmiş veya devre dışı olduğunda çerçevesi tarafından çağrılır.  
  
```  
virtual void OnActivateView(
    BOOL bActivate,  
    CView* pActivateView,  
    CView* pDeactiveView);
```  
  
### <a name="parameters"></a>Parametreler  
 `bActivate`  
 Görünüm belirtir etkin veya devre dışı.  
  
 `pActivateView`  
 Etkinleştirilmekte olan Görünüm nesnesi noktalarına.  
  
 `pDeactiveView`  
 Devre dışı bırakılıyor Görünüm nesnesi noktalarına.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulaması odağı etkinleştirilmekte olan görünüme ayarlar. Bir görünüm etkinleştirilmiş veya devre dışı olduğunda özel işlem gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar. Örneğin, etkin olmayan görünümlerinden etkin görünüm ayırt özel görsel ipuçları sağlamak istiyorsanız, incelemeniz `bActivate` parametre ve görünümün görünüm uygun şekilde güncelleştirilir.  
  
 `pActivateView` Ve `pDeactiveView` parametreleri uygulamanın ana çerçeve penceresi etkin görünümünde değişiklik etkinleştirilmişse aynı görünüme noktası — Örneğin, bu bir başka bir uygulamadan yerine birinden odağı aktarıldığı başka bir uygulama içinde veya MDI alt pencereleri arasında geçiş yaparken görüntüleyin. Gerekirse, paletini yeniden hayata geçirmek bir görünüm sağlar.  
  
 Bu parametreler farklı olduğunda [CFrameWnd::SetActiveView](../../mfc/reference/cframewnd-class.md#setactiveview) farklı bir görünümle adlı [CFrameWnd::GetActiveView](../../mfc/reference/cframewnd-class.md#getactiveview) döndürür. Bu çoğunlukla Bölümlendirici pencereler ile gerçekleşir.  
  
##  <a name="onbeginprinting"></a>  CView::OnBeginPrinting  
 Sonra bir yazdırın veya Önizleme iş başında framework tarafından çağrılan `OnPreparePrinting` çağrıldı.  
  
```  
virtual void OnBeginPrinting(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Yazıcı cihaz bağlamı noktalarına.  
  
 `pInfo`  
 İşaret eden bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) geçerli yazdırma işi açıklar yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulaması hiçbir şey yapmaz. Özellikle yazdırma için gerekli tüm GDI gibi kaynaklar kalemler veya yazı tiplerini, ayırmak için bu işlevi geçersiz kılar. GDI nesneleri içinden cihaz bağlamı içine seçin [OnPrint](#onprint) bunları kullanan her bir sayfa için üye işlevi. Ekran görüntüsü hem de yazdırma gerçekleştirmek için aynı görünüm nesnesi kullanıyorsanız, her bir ekran için gereken GDI kaynakları için ayrı değişkenlerini kullanın; Bu ekran yazdırma sırasında güncelleştirmenize olanak sağlar.  
  
 Bu işlev, yazıcı cihaz bağlamı özelliklerindeki bağımlı başlatmaları gerçekleştirmek için de kullanabilirsiniz. Örneğin, belge yazdırmak için gereken sayfa sayısı, (örneğin, sayfa uzunluğu) yazdırma iletişim kutusundan kullanıcı belirtilen ayarlara bağlı olabilir. Böyle bir durumda, belge uzunluğu belirtemezsiniz [OnPreparePrinting](#onprepareprinting) üye işlevi, burada normalde bunu; yazıcı cihaz bağlamı iletişim kutusu ayarlar tabanlı oluşturuluncaya kadar beklemeniz gerekir. [OnBeginPrinting](#onbeginprinting) sağlayan ilk geçersiz kılınabilir işlev erişmek için [CDC](../../mfc/reference/cdc-class.md) bu işlevden belge uzunluğunu ayarlayabilirsiniz yazıcı cihaz bağlamı temsil eden nesne. Belgenin uzunluğu bu zamana kadar belirtilmezse, bir kaydırma çubuğunun Baskı Önizleme sırasında görüntülenmez unutmayın.  
  
##  <a name="ondragenter"></a>  CView::OnDragEnter  
 Fare ilk açılan hedef penceresinin kaydırılamayan bölge girdiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDataObject`  
 İşaret [COleDataObject](../../mfc/reference/coledataobject-class.md) görünümü bırakma alanına sürüklenen.  
  
 `dwKeyState`  
 Değiştirici tuşları durumunu içerir. Bu aşağıdaki herhangi bir sayıda birleşiminden oluşur: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, ve **MK_RBUTTON**.  
  
 `point`  
 Geçerli fare konumuna göre istemci alanını görünüm.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arasında bir değer `DROPEFFECT` numaralandırılmış kullanıcı bu konumda nesne düştüğünde oluşacak açılan türünü gösterir türü. Bırakma türü tarafından belirtilen anahtar geçerli durumu genellikle bağlıdır `dwKeyState`. Aktarıyorsanız için standart eşlemesi `DROPEFFECT` değerler:  
  
- `DROPEFFECT_NONE` Veri nesnesi bu pencerede bırakılamıyor.  
  
- `DROPEFFECT_LINK` için **MK_CONTROL &#124; MK_SHIFT** nesne sunucusu arasındaki bir bağlantı oluşturur.  
  
- `DROPEFFECT_COPY` için **MK_CONTROL** bırakılan nesnesinin bir kopyasını oluşturur.  
  
- `DROPEFFECT_MOVE` için **MK_ALT** bırakılan nesnesinin bir kopyasını oluşturur ve özgün nesne silin. Görünümü Bu verisi nesnesini kabul edebilir, bu genellikle varsayılan açılan etkili olur.  
  
 Daha fazla bilgi için bkz: MFC Gelişmiş kavramları örnek [OCLIENT](../../visual-cpp-samples.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulamadır hiçbir şey yapma ve dönmek için `DROPEFFECT_NONE`.  
  
 Sonraki çağrılar için hazırlamak için bu işlevi geçersiz [OnDragOver](#ondragover) üye işlevi. Daha sonra kullanmak için şu anda veri nesnesinden gerekli herhangi bir veri alınan `OnDragOver` üye işlevi. Görünüm kullanıcı visual geribildirim vermek için şu anda da güncelleştirilmesi gerekir. Daha fazla bilgi için bkz: [sürükle ve bırak: bir bırakma hedefi uygulama](../../mfc/drag-and-drop-implementing-a-drop-target.md).  
  
##  <a name="ondragleave"></a>  CView::OnDragLeave  
 Fare Bu pencere için geçerli bırak alanı dışına taşındığında bir sürükleme işlemi sırasında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDragLeave();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli görünümü sırasında gerçekleştirilecek eylemler temizleme gerekiyorsa, bu işlevi geçersiz kılma [OnDragEnter](#ondragenter) veya [OnDragOver](#ondragover) nesnesi sürüklenebilir ve bırakılan gibi herhangi bir görsel kullanıcı geribildirim kaldırma çağrıları .  
  
##  <a name="ondragover"></a>  CView::OnDragOver  
 Fare açılan hedef pencere üzerinde taşındığında bir sürükleme işlemi sırasında çerçevesi tarafından çağrılır.  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDataObject`  
 İşaret [COleDataObject](../../mfc/reference/coledataobject-class.md) bırakma hedefi sürüklenen.  
  
 `dwKeyState`  
 Değiştirici tuşları durumunu içerir. Bu aşağıdaki herhangi bir sayıda birleşiminden oluşur: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, ve **MK_RBUTTON**.  
  
 `point`  
 Görünüm istemci alanını göreli fare geçerli konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arasında bir değer `DROPEFFECT` numaralandırılmış kullanıcı bu konumda nesne düştüğünde oluşacak açılan türünü gösterir türü. Bırakma türü genellikle belirtildiği gibi geçerli anahtar durumuna bağlıdır `dwKeyState`. Aktarıyorsanız için standart eşlemesi `DROPEFFECT` değerler:  
  
- `DROPEFFECT_NONE` Veri nesnesi bu pencerede bırakılamıyor.  
  
- `DROPEFFECT_LINK` için **MK_CONTROL &#124; MK_SHIFT** nesne sunucusu arasındaki bir bağlantı oluşturur.  
  
- `DROPEFFECT_COPY` için **MK_CONTROL** bırakılan nesnesinin bir kopyasını oluşturur.  
  
- `DROPEFFECT_MOVE` için **MK_ALT** bırakılan nesnesinin bir kopyasını oluşturur ve özgün nesne silin. Görünüm Verisi nesnesini kabul edebilir, bu genellikle varsayılan açılan etkili olur.  
  
 Daha fazla bilgi için bkz: MFC Gelişmiş kavramları örnek [OCLIENT](../../visual-cpp-samples.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir şey yapma ve dönmek için varsayılan uygulamadır `DROPEFFECT_NONE`.  
  
 Sürükleme işlemi sırasında kullanıcı visual geribildirim vermek için bu işlevi geçersiz kılar. Bu işlev sürekli olarak adlandırılır olduğundan, içerdiği herhangi bir kod mümkün olduğunca hale getirilmiştir. Daha fazla bilgi için bkz: [sürükle ve bırak: bir bırakma hedefi uygulama](../../mfc/drag-and-drop-implementing-a-drop-target.md).  
  
##  <a name="ondragscroll"></a>  CView::OnDragScroll  
 Çağırmadan önce framework tarafından çağrılan [OnDragEnter](#ondragenter) veya [OnDragOver](#ondragover) noktası kaydırma bölgede olup olmadığını belirlemek için.  
  
```  
virtual DROPEFFECT OnDragScroll(
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwKeyState`  
 Değiştirici tuşları durumunu içerir. Bu aşağıdaki herhangi bir sayıda birleşiminden oluşur: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, ve **MK_RBUTTON**.  
  
 `point`  
 İmleç, piksel cinsinden ekran göreli konumunu içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arasında bir değer `DROPEFFECT` numaralandırılmış kullanıcı bu konumda nesne düştüğünde oluşacak açılan türünü gösterir türü. Bırakma türü tarafından belirtilen anahtar geçerli durumu genellikle bağlıdır `dwKeyState`. Aktarıyorsanız için standart eşlemesi `DROPEFFECT` değerler:  
  
- `DROPEFFECT_NONE` Veri nesnesi bu pencerede bırakılamıyor.  
  
- `DROPEFFECT_LINK` için **MK_CONTROL &#124; MK_SHIFT** nesne sunucusu arasındaki bir bağlantı oluşturur.  
  
- `DROPEFFECT_COPY` için **MK_CONTROL** bırakılan nesnesinin bir kopyasını oluşturur.  
  
- `DROPEFFECT_MOVE` için **MK_ALT** bırakılan nesnesinin bir kopyasını oluşturur ve özgün nesne silin.  
  
- `DROPEFFECT_SCROLL` Sürükleme kaydırma işlemi gerçekleşmek üzere veya hedef görünümünde oluştuğunu gösterir.  
  
 Daha fazla bilgi için bkz: MFC Gelişmiş kavramları örnek [OCLIENT](../../visual-cpp-samples.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu olay için özel davranışı sağlamak istediğinizde bu işlevi geçersiz kılar. İmleç varsayılan kaydırma bölgesi iç kenarlık her penceresinin içine sürüklendiğinde varsayılan uygulaması windows otomatik olarak kayar. Daha fazla bilgi için bkz: [sürükle ve bırak: bir bırakma hedefi uygulama](../../mfc/drag-and-drop-implementing-a-drop-target.md).  
  
##  <a name="ondraw"></a>  CView::OnDraw  
 Belge görüntüsü oluşturmak için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDraw(CDC* pDC) = 0;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Belge görüntüsünü çizmek için kullanılacak cihaz bağlamı noktalarına.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework ekran görüntüsü, yazdırma ve Baskı Önizleme gerçekleştirmek için bu işlevi çağırır ve her durumda farklı cihaz bağlamı geçirir. Varsayılan uygulama yok.  
  
 Belgeyi görüntülemek için bu işlevi geçersiz kılmanız gerekir. Grafik cihaz arabirimi (GDI) çağrıları kullanarak yapabilirsiniz [CDC](../../mfc/reference/cdc-class.md) tarafından için nesne işaret `pDC` parametresi. Çizim önce aygıt bağlam içine kalemler veya yazı tipleri gibi GDI kaynaklarını seçin ve ardından bunları daha sonra seçimini kaldırın. Genellikle CİHAZDAN bağımsız çizim kodunuzu olabilir; diğer bir deyişle, cihaz türüne görüntü görüntüleme hakkında bilgi gerektirmez.  
  
 Çizim iyileştirmek için çağrı [RectVisible](../../mfc/reference/cdc-class.md#rectvisible) üye işlevini olup belirtilen dikdörtgen çizileceğini bulmak için cihaz bağlamı. Normal ekran görüntüsünü yazdırma arasında ayrım yapmak gereksinim duyarsanız, çağrı [IsPrinting](../../mfc/reference/cdc-class.md#isprinting) üye işlevini cihaz bağlamı.  
  
##  <a name="ondrop"></a>  CView::OnDrop  
 Kullanıcı bir veri nesnesi geçerli bırakma hedefi bıraktığında çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnDrop(
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDataObject`  
 İşaret [COleDataObject](../../mfc/reference/coledataobject-class.md) açılan hedef bırakıldı.  
  
 `dropEffect`  
 Kullanıcının istediği açılan etkisi.  
  
- `DROPEFFECT_COPY` Bırakılan veri nesnesinin bir kopyasını oluşturur.  
  
- `DROPEFFECT_MOVE` Veri nesnesi geçerli fare konuma taşır.  
  
- `DROPEFFECT_LINK` Bir veri nesnesi sunucusu arasındaki bir bağlantı oluşturur.  
  
 `point`  
 Görünüm istemci alanını göreli fare geçerli konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açılan başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama hiçbir şey yapmaz ve döndürür **FALSE**.  
  
 OLE bırak etkisini görünümü istemci alanına uygulamak için bu işlevi geçersiz kılar. Veri nesnesi aracılığıyla incelenebilir `pDataObject` için Pano veri biçimlerini ve veri belirtilen noktada bırakıldı.  
  
> [!NOTE]
>  Bir geçersiz kılma ise bu işlev framework çağırmaz [OnDropEx](#ondropex) bu görünüm sınıfta.  
  
##  <a name="ondropex"></a>  CView::OnDropEx  
 Kullanıcı bir veri nesnesi geçerli bırakma hedefi bıraktığında çerçevesi tarafından çağrılır.  
  
```  
virtual DROPEFFECT OnDropEx(
    COleDataObject* pDataObject,  
    DROPEFFECT dropDefault,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDataObject`  
 İşaret [COleDataObject](../../mfc/reference/coledataobject-class.md) açılan hedef bırakıldı.  
  
 `dropDefault`  
 Geçerli anahtar durumuna göre varsayılan bırakma işlemi için kullanıcının seçtiği etkisi. Bu olabilir `DROPEFFECT_NONE`. Açılan efektler açıklamalar bölümünde ele alınmıştır.  
  
 `dropList`  
 Bırakma kaynağı destekleyen açılan etkilerini listesi. Bit düzeyinde OR kullanarak doğrudan etkisi değerleri birleştirilebilir ( **&#124;**) işlemi. Açılan efektler açıklamalar bölümünde ele alınmıştır.  
  
 `point`  
 Görünüm istemci alanını göreli fare geçerli konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından belirtilen konumda bırak girişimi kullanmasından kaynaklanan açılan etkisi `point`. Bu belirtilen değerlerden biri olmalıdır *dropEffectList*. Açılan efektler açıklamalar bölümünde ele alınmıştır.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir şey yapma ve framework çağırmalıdır belirtmek için bir kukla değer (-1) dönmek için varsayılan uygulamadır [OnDrop](#ondrop) işleyicisi.  
  
 Bu işlev bir sağ fare düğmesini sürükle ve bırak etkisini uygulamak için geçersiz kılar. Sağ fare düğmesini sürükle ve bırak genellikle görüntüler Seçenekler menüsüne sağ fare düğmesini serbest bırakıldığında.  
  
 Geçersiz kılma, `OnDropEx` sağ fare düğmesini için sorgu. Çağırabilirsiniz [GetKeyState](http://msdn.microsoft.com/library/windows/desktop/ms646301) veya sağ fare düğmesini durumundan depolamak, [OnDragEnter](#ondragenter) işleyicisi.  
  
-   Sağ fare düğmesini basılı ise, geçersiz kılma bırakma kaynağı tarafından açılan etkileri desteği sunan bir açılır menü görüntülemelidir.  
  
    -   İncelemek `dropList` bırakma kaynağı tarafından desteklenen açılan etkilerini belirlemek için. Yalnızca bu eylemleri açılan menüsünde etkinleştirin.  
  
    -   Kullanım [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996) göre varsayılan eylem ayarlamak için `dropDefault`.  
  
    -   Son olarak, açılan menüden kullanıcı seçimi tarafından belirtilen eylemi gerçekleştirin.  
  
-   Sağ fare düğmesini aşağı değilse, geçersiz kılma bu standart açılan istek işleme. Belirtilen açılan efekti kullanmak `dropDefault`. Alternatif olarak, geçersiz kılma belirtmek için kukla değer (-1) geri dönebilirsiniz `OnDrop` bu bırakma işlemi işleyecek.  
  
 Kullanım `pDataObject` incelemek için `COleDataObject` için Pano verileri biçimi ve verileri belirtilen noktada bırakıldı.  
  
 Açılan etkileri açılan işlemle ilişkili eylemi açıklar. Açılan etkileri aşağıdaki listeye bakın:  
  
- `DROPEFFECT_NONE` Bir açılan izin verilmez.  
  
- `DROPEFFECT_COPY` Bir kopyalama işlemi gerçekleştirilmesi.  
  
- `DROPEFFECT_MOVE` Bir taşıma işlemi gerçekleştirilmesi.  
  
- `DROPEFFECT_LINK` Özgün veriler bırakılan verilerden bir bağlantı kurulamıyor.  
  
- `DROPEFFECT_SCROLL` Sürükleme kaydırma işlemi gerçekleşmek üzere veya hedef oluştuğunu gösterir.  
  
 Varsayılan menü komutu ayarlama hakkında daha fazla bilgi için bkz: [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996) Windows SDK ve [CMenu::GetSafeHmenu](../../mfc/reference/cmenu-class.md#getsafehmenu) bu birimdeki.  
  
##  <a name="onendprinting"></a>  CView::OnEndPrinting  
 Bir belge yazdırılması veya önizlemesi sonra çerçevesi tarafından çağrılır.  
  
```  
virtual void OnEndPrinting(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Yazıcı cihaz bağlamı noktalarına.  
  
 `pInfo`  
 İşaret eden bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) geçerli yazdırma işi açıklar yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulaması hiçbir şey yapmaz. Bu işlev, ayrılan tüm GDI kaynaklarını serbest geçersiz kılma [OnBeginPrinting](#onbeginprinting) üye işlevi.  
  
##  <a name="onendprintpreview"></a>  CView::OnEndPrintPreview  
 Kullanıcı Baskı Önizleme modunu çıktığında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnEndPrintPreview(
    CDC* pDC,  
    CPrintInfo* pInfo,  
    POINT point,  
    CPreviewView* pView);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Yazıcı cihaz bağlamı noktalarına.  
  
 `pInfo`  
 İşaret eden bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) geçerli yazdırma işi açıklar yapısı.  
  
 `point`  
 En son önizleme modunda görüntülenen sayfasında noktasını belirtir.  
  
 `pView`  
 Önizleme için kullanılan Görünüm nesnesi noktalarına.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulamasını çağıran [OnEndPrinting](#onendprinting) üye fonksiyonu ve geri yükler, içinde önce Baskı Önizleme duruma ana çerçeve penceresi başladı. Bu işlevi önizleme modunda sonlandırıldığında özel işlem gerçekleştirmek için geçersiz kılar. Önizleme modundan normal görüntüleme moduna geçerken belgedeki kullanıcının konumunu korumak istiyorsanız, örneğin, size tarafından açıklanan konuma kaydırabilirsiniz `point` parametre ve `m_nCurPage` üyesi `CPrintInfo` yapısı `pInfo` parametresi işaret eder.  
  
 Her zaman temel sınıf sürümü çağrı `OnEndPrintPreview` genellikle işlevi sonunda geçersiz kılma, gelen.  
  
##  <a name="oninitialupdate"></a>  CView::OnInitialUpdate  
 Görünüm ilk belgeye eklendikten sonra ancak görünümü başlangıçta görüntülenmeden önce çerçevesi tarafından çağrılır.  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulamasını çağıran [in](#onupdate) hiçbir ipucu bilgilerle üye işlevi (diğer bir deyişle, 0 için varsayılan değerleri kullanılarak `lHint` parametre ve **NULL** için`pHint` parametresi). Belge hakkındaki bilgileri gerektiren herhangi bir kerelik başlatma gerçekleştirmek için bu işlevi geçersiz kılar. Örneğin, sabit boyutlu belgeleri uygulamanız varsa, belge boyutuna göre bir görünümün kayan sınırları başlatmak için bu işlevi kullanabilirsiniz. Uygulamanızın değişken boyutlu belgeleri destekliyorsa kullanın [in](#onupdate) kaydırma güncelleştirmek için belge değişiklikleri her zaman sınırlar.  
  
##  <a name="onpreparedc"></a>  CView::OnPrepareDC  
 Önce framework tarafından çağrılan [OnDraw](#ondraw) üye işlevi çağrılmadan önce ve ekran görüntüsü için [OnPrint](#onprint) üye işlevi, yazdırma veya Baskı Önizleme sırasında her bir sayfa için çağrılır.  
  
```  
virtual void OnPrepareDC(
    CDC* pDC,  
    CPrintInfo* pInfo = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Belge görüntüsünü çizmek için kullanılacak cihaz bağlamı noktalarına.  
  
 `pInfo`  
 İşaret eden bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) durumunda geçerli yazdırma işi açıklanmıştır yapısı `OnPrepareDC` yazdırma veya Baskı Önizleme; adlı `m_nCurPage` üye hakkında yazdırılacak sayfayı belirtir. Bu parametre **NULL** varsa `OnPrepareDC` ekran görüntüsü için çağrılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Ekran görüntüsü için işlevi çağrıldıysa bu işlev varsayılan uygulaması hiçbir şey yapmaz. Ancak, bu işlevi türetilmiş sınıflarda gibi kılınmadığı [CScrollView](../../mfc/reference/cscrollview-class.md), cihaz bağlamı; özniteliklerini ayarlamak için sonuç olarak, her zaman temel sınıf uygulamasını geçersiz kılma başında çağırmalısınız.  
  
 Yazdırma için işlevi çağrılırsa, varsayılan uygulama depolanan sayfası bilgileri inceler `pInfo` parametresi. Belgenin uzunluğunu belirtilmediği takdirde `OnPrepareDC` uzun bir sayfa olarak belge varsayar ve bir sayfa yazdırılan sonra yazdırma döngü durur. Ayarlayarak yazdırma döngü işlevi durdurur `m_bContinuePrinting` yapısına üyesi **FALSE**.  
  
 Geçersiz kılma `OnPrepareDC` aşağıdaki nedenlerden biriyle için:  
  
-   Cihaz bağlamı özniteliklerini belirtilen sayfa için gerektiği şekilde ayarlamak için. Eşleme modu veya diğer cihaz bağlamı özelliklerini ayarlamanız gerekir, örneğin, bu işlevde bunu.  
  
-   Yazdırma zamanı sayfalandırma gerçekleştirmek için. Normalde yazdırma başladığında kullanarak belgenin uzunluğunu belirtmek [OnPreparePrinting](#onprepareprinting) üye işlevi. Ancak, bilmiyorsanız önceden ne kadar süreyle belge (örneğin, bir belirlenmemiş kayıt sayısı, bir veritabanından yazdırırken), geçersiz kılma `OnPrepareDC` yazdırılmasını sırada belgenin sonuna için test etmek için. Olduğunda yazdırılması belgenin artık, ayarlamak `m_bContinuePrinting` üyesi `CPrintInfo` için yapı **FALSE**.  
  
-   Sayfa tarafından temelinde yazıcı çıkış kodları göndermek için. Çıkış kodları göndermek için `OnPrepareDC`, çağrı **kaçış** üye işlevini `pDC` parametresi.  
  
 Temel sınıf sürümü çağrı `OnPrepareDC` geçersiz kılma işleminin başında.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#183](../../mfc/codesnippet/cpp/cview-class_1.cpp)]  
  
##  <a name="onprepareprinting"></a>  CView::OnPreparePrinting  
 Bir belge yazdırılması veya önizlemesi önce çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnPreparePrinting(CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 `pInfo`  
 İşaret eden bir [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) geçerli yazdırma işi açıklar yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazdırmaya başlamak için sıfır olmayan; 0 yazdırma işi iptal edildi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama hiçbir şey yapmaz.  
  
 Yazdırma ve baskı önizlemeyi etkinleştirmek için bu işlevi geçersiz kılmanız gerekir. Çağrı [DoPreparePrinting](#doprepareprinting) onu üye işlevi `pInfo` parametre ve dönüş değerini; döndürür `DoPreparePrinting` yazıcı cihaz bağlamı oluşturur ve Yazdır iletişim kutusu görüntüler. Yazdır iletişim kutusu dışındaki varsayılan değerlerle başlatmak istiyorsanız, üyelerine atayabilmeniz `pInfo`. Belgenin uzunluğunu biliyorsanız, örneğin, değerine geçirmek [SetMaxPage](../../mfc/reference/cprintinfo-structure.md#setmaxpage) üye işlevini `pInfo` çağırmadan önce `DoPreparePrinting`. Bu değer Kime görüntülenir: Yazdır iletişim kutusu aralığı kısmı kutusu.  
  
 `DoPreparePrinting` Yazdır iletişim kutusu Önizleme işi için görüntülemez. Bir yazdırma işinin yazdırma iletişim kutusunda atlamak istiyorsanız, denetleyin **m_bPreview** üyesi `pInfo` olan **FALSE** ve daha sonra ayarlamak **TRUE** kendisine geçirmeden önce `DoPreparePrinting`; için sıfırlayın **FALSE** daha sonra.  
  
 Erişim gerektiren başlatmaları yapmanız gereken `CDC` (örneğin, sayfa boyutu belgenin uzunluğunu belirtmeden önce bilmeniz gereken,), yazıcı cihaz bağlamı temsil eden nesnesi geçersiz kılma `OnBeginPrinting` üyesi işlev.  
  
 Değerini ayarlamak istiyorsanız **m_nNumPreviewPages** veya **m_strPageDesc** üyeleri `pInfo` parametresi çağrıldıktan sonra bunu `DoPreparePrinting`. `DoPreparePrinting` Üye fonksiyonu kümeleri **m_nNumPreviewPages** uygulamanın içinde bulunan değere. INI dosyası ve ayarlar **m_strPageDesc** varsayılan değerine.  
  
### <a name="example"></a>Örnek  
  Geçersiz kılma `OnPreparePrinting` ve arama `DoPreparePrinting` geçersiz kılma gelen framework Yazdır iletişim kutusunu görüntülemek ve sizin için bir yazıcı DC oluşturun.  
  
 [!code-cpp[NVC_MFCDocView#184](../../mfc/codesnippet/cpp/cview-class_2.cpp)]  
  
 Belgeyi içeren kaç sayfa biliyorsanız, en fazla sayfa kümesinde `OnPreparePrinting` çağırmadan önce `DoPreparePrinting`. Framework Yazdır iletişim kutusu "için" kutusunda en fazla sayfa sayısını görüntüler.  
  
 [!code-cpp[NVC_MFCDocView#185](../../mfc/codesnippet/cpp/cview-class_3.cpp)]  
  
##  <a name="onprint"></a>  CView::OnPrint  
 Belge sayfasının yazdıramaz veya çerçevesi tarafından çağrılır.  
  
```  
virtual void OnPrint(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Yazıcı cihaz bağlamı noktalarına.  
  
 `pInfo`  
 İşaret eden bir `CPrintInfo` geçerli yazdırma işi açıklar yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Yazdırılmasını her bir sayfa için framework hemen çağrıldıktan sonra bu işlev çağrıları [OnPrepareDC](#onpreparedc) üye işlevi. Yazdırılmasını sayfası tarafından belirtilen `m_nCurPage` üyesi [Cprintınfo](../../mfc/reference/cprintinfo-structure.md) , yapı `pInfo` işaret eder. Varsayılan Uygulama çağrıları [OnDraw](#ondraw) üye işlevini ve yazıcı cihaz bağlamı geçirir.  
  
 Bu işlevi aşağıdaki nedenlerden biriyle geçersiz kıl:  
  
-   Birden çok belge yazdırma izin vermek için. Yalnızca şu anda yazdırılmasını sayfasına karşılık gelen belgeye bölümü işlenemiyor. Kullanıyorsanız, `OnDraw` belgeyi yalnızca uygun kısmı yazdırılması işleme gerçekleştirmek için Görünüm penceresi kaynak ayarlayabilirsiniz.  
  
-   Yazdırılan görüntünün (diğer bir deyişle, uygulamanızın WYSIWYG değilse) ekran görüntüsünü farklı görünmesini sağlamak için. Yazıcı cihaz bağlamına geçirme yerine `OnDraw`, cihaz bağlamı ekranda gösterilmez özniteliklerini kullanarak bir görüntü oluşturmak için kullanın.  
  
     GDI kaynaklarını ekran görüntüsü için kullanmayın yazdırma için ihtiyacınız varsa, bunları çizim önce aygıt bağlam içine seçin ve daha sonra seçimini kaldırın. Bu GDI kaynaklarını ayrılması gereken [OnBeginPrinting](#onbeginprinting) ve de serbest [OnEndPrinting](#onendprinting).  
  
-   Üstbilgiler ve altbilgiler uygulamak için. Kullanmaya devam edebilirsiniz `OnDraw` üzerinde yazdırabilirsiniz alanı kısıtlayarak işleme yapmak için.  
  
 Unutmayın **m_rectDraw** üyesi `pInfo` parametresi mantıksal birimler sayfasının yazdırılabilir alan açıklar.  
  
 Çağırmayın `OnPrepareDC` geçersiz kılma içinde `OnPrint`; framework çağrıları `OnPrepareDC` çağırmadan önce otomatik olarak `OnPrint`.  
  
### <a name="example"></a>Örnek  
 Geçersiz kılınan bir için çatıyı aşağıdadır `OnPrint` işlevi:  
  
 [!code-cpp[NVC_MFCDocView#186](../../mfc/codesnippet/cpp/cview-class_4.cpp)]  
  
 Başka bir örnek için bkz: [CRichEditView::PrintInsideRect](../../mfc/reference/cricheditview-class.md#printinsiderect).  
  
##  <a name="onscroll"></a>  CView::OnScroll  
 Kaydırma olup olmadığını belirlemek için çerçevesi tarafından çağrılır mümkündür.  
  
```  
virtual BOOL OnScroll(
    UINT nScrollCode,  
    UINT nPos,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `nScrollCode`  
 Kullanıcı gösteren bir kaydırma çubuğunun kod isteği kaydırma. Bu parametre iki bölümden oluşur: yatay kaydırma gerçekleşen türünü belirler, düşük düzey bir bayt ve dikey olarak gerçekleşen kaydırma türünü belirleyen bir yüksek düzey bayt:  
  
- **SB_BOTTOM** alt kaydırır.  
  
- **SB_LINEDOWN** bir satırı aşağı kaydırır.  
  
- **SB_LINEUP** bir satırı yukarı kaydırır.  
  
- **SB_PAGEDOWN** bir sayfa aşağı kaydırır.  
  
- **SB_PAGEUP** bir sayfa yukarı kaydırır.  
  
- **SB_THUMBTRACK** Drags kaydırma kutusunun belirtilen konuma. Geçerli konumu belirtilen `nPos`.  
  
- **SB_TOP** dön birlikte kayar.  
  
 `nPos`  
 Kaydırma çubuğu kodu ise geçerli kaydırma kutusunun konumunu içeren **SB_THUMBTRACK**; Aksi halde kullanılmaz. İlk kaydırma aralığı bağlı olarak `nPos` negatif olabilir ve için atamalısınız bir `int` gerekiyorsa.  
  
 `bDoScroll`  
 Belirtilen kaydırma eylem gerçekte yapmanız gerektiğini olup olmadığını belirler. Varsa **TRUE,** kaydırma; varsa gerçekleşeceğini sonra **yanlış**, kaydırma gerçekleşmeyeceğini sonra.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsa `bDoScroll` olan **doğru** ve görünüm gerçekte kaydırılan, ardından sıfır olmayan; Aksi takdirde 0. Varsa `bDoScroll` olan **FALSE**, varsa iade değerini döndürür `bDoScroll` olan **TRUE**rağmen kaydırma gerçekte yapmayın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir durumda bu işlev ile çerçevesi tarafından çağrılır `bDoScroll` kümesine **TRUE** zaman görünümü scrollbar iletisi alır. Bu durumda, aslında görünüme gitmeniz gerekir. Bu işlev çağrılır başka bir durumda `bDoScroll` kümesine **FALSE** zaman OLE öğeyi başlangıçta sürüklenebilir bir bırakma hedefi otomatik kaydırma bölgeye kaydırma gerçekte gerçekleşmeden önce. Bu durumda, aslında görünüme gitmeniz gerekir değil.  
  
##  <a name="onscrollby"></a>  CView::OnScrollBy  
 Kullanıcı bir alan ya bir OLE öğesi görünümün geçerli Kenarlıklar karşı sürükleyerek veya dikey veya yatay kaydırma çubukları düzenleme belge mevcut görünümünü ötesinde görüntülediğinde çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnScrollBy(
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `sizeScroll`  
 Piksel sayısı yatay ve dikey olarak kaydırılan.  
  
 `bDoScroll`  
 Görünümünü kaydırma mi gerçekleşeceğini belirler. Varsa **TRUE,** kaydırma; durumunda gerçekleşir sonra **yanlış**, kaydırma oluşmaz sonra.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görünüm kaydırılan mümkün olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilmiş sınıflarda bu yöntem görünümü kullanıcı istenir ve ardından gerekirse, yeni bölge güncelleştirir yönünü kaydırılabilir olup olmadığını denetler. Bu işlev otomatik olarak çağrılır [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) ve [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) gerçek kaydırma isteği gerçekleştirmek için.  
  
 Bu yöntem varsayılan uygulaması görünümü değiştirmez, ancak görünümü içinde Kaymaz çağrılmazsa, bir `CScrollView`-türetilmiş sınıf.  
  
 Belge genişliği veya yüksekliği 32767 piksel aşıyor, 32767 kaydırma başarısız olur `OnScrollBy` geçersiz bir adlı `sizeScroll` bağımsız değişkeni.  
  
##  <a name="onupdate"></a>  CView::OnUpdate  
 Görünümün belge değiştirildikten sonra çerçevesi tarafından çağrılır; Bu işlev tarafından çağrılır [CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) ve görünümünü bu değişiklikleri yansıtacak şekilde güncelleştirmek görünümü sağlar.  
  
```  
virtual void OnUpdate(
    CView* pSender,  
    LPARAM lHint,  
    CObject* pHint);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSender`  
 İşaret belge değiştiren görünümüne veya **NULL** tüm görünümleri güncelleştirilmesi gerekiyorsa.  
  
 `lHint`  
 Değişiklikler hakkında bilgiler içerir.  
  
 `pHint`  
 Değişiklikler hakkında bilgi depolamak nesneye noktaları.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulaması da adlandırılır [OnInitialUpdate](#oninitialupdate). Varsayılan uygulama boyama için işaretleme tüm istemci alanını geçersiz kılar sonraki `WM_PAINT` iletisi alındığında. Belgenin değiştirilmiş bölümleri eşlenen bölgeleri güncelleştirmek isterseniz, bu işlev geçersiz kılar. Bunu yapmak için ipucu parametrelerini kullanarak değişiklikler hakkında bilgi geçmesi gerekir.  
  
 Kullanılacak `lHint`özel ipucu değerleri, genellikle bir bit maskesi veya numaralandırılmış türü tanımlamak ve bu değerlerden birini geçirmek belge sahip. Kullanılacak `pHint`, bir ipucu sınıfından türetilen [CObject](../../mfc/reference/cobject-class.md) ve geçersiz kılma olduğunda bir işaretçi bir ipucu nesnesine; geçir belge `OnUpdate`, kullanın [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) üye işlevi İpucu nesnesinin çalışma zamanı türü belirler.  
  
 Genellikle, herhangi bir doğrudan çizim uygulamalısınız değil `OnUpdate`. Bunun yerine, cihaz koordinatlarında güncelleştirilmesi alanı açıklayan dikdörtgen belirler; Bu dikdörtgen geçirmek [CWnd::InvalidateRect](../../mfc/reference/cwnd-class.md#invalidaterect). Bu sonraki kapatmasında boyama neden olan bir [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) iletisi alındığında.  
  
 Varsa `lHint` 0'dır ve `pHint` olan **NULL**, belgeyi bir genel güncelleştirme bildirimi gönderdi. Bir görünüm genel güncelleştirme bildirimi alırsa veya ipucu çözülemiyor, kendi tüm istemci alanı geçersiz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MDIDOCVW](../../visual-cpp-samples.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)   
 [CSplitterWnd sınıfı](../../mfc/reference/csplitterwnd-class.md)   
 [CDC sınıfı](../../mfc/reference/cdc-class.md)   
 [CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument Sınıfı](../../mfc/reference/cdocument-class.md)
