---
title: "CSplitterWnd sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 706425dd8d729937d310da9cc2f09eac8ec1ad57
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csplitterwnd-class"></a>CSplitterWnd sınıfı
Birden çok bölmeleri içeren bir penceredir bir Bölümlendirici pencere işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSplitterWnd : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSplitterWnd::CSplitterWnd](#csplitterwnd)|Çağrı oluşturmak için bir `CSplitterWnd` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSplitterWnd::ActivateNext](#activatenext)|Sonraki Bölme veya önceki bölme komutu gerçekleştirir.|  
|[CSplitterWnd::CanActivateNext](#canactivatenext)|Sonraki Bölme veya önceki bölme komutu şu anda mümkün olup olmadığını denetler.|  
|[CSplitterWnd::Create](#create)|Dinamik Bölümlendirici pencere oluşturmak ve ona eklemek için arama `CSplitterWnd` nesnesi.|  
|[CSplitterWnd::CreateScrollBarCtrl](#createscrollbarctrl)|Paylaşılan kaydırma çubuğu denetimi oluşturur.|  
|[CSplitterWnd::CreateStatic](#createstatic)|Statik Bölümlendirici pencere oluşturmak ve ona eklemek için arama `CSplitterWnd` nesnesi.|  
|[CSplitterWnd::CreateView](#createview)|Bölümlendirici penceresinde bir bölme oluşturmak için çağırın.|  
|[CSplitterWnd::DeleteColumn](#deletecolumn)|Bir sütunu Bölümlendirici penceresinden siler.|  
|[CSplitterWnd::DeleteRow](#deleterow)|Bir satır ayırıcı penceresinden siler.|  
|[CSplitterWnd::DeleteView](#deleteview)|Bir görünüm Bölümlendirici penceresinden siler.|  
|[CSplitterWnd::DoKeyboardSplit](#dokeyboardsplit)|Komut, genellikle "Pencere Böl." Böl klavye gerçekleştirir|  
|[CSplitterWnd::DoScroll](#doscroll)|Eşitlenen bölünmüş windows kaydırma gerçekleştirir.|  
|[CSplitterWnd::DoScrollBy](#doscrollby)|Bölünmüş Pencereler belirli sayıda piksel kadar kaydırır.|  
|[CSplitterWnd::GetActivePane](#getactivepane)|Odağı veya çerçevede etkin görünüm etkin bölmesinden belirler.|  
|[CSplitterWnd::GetColumnCount](#getcolumncount)|Geçerli bölmesinde sütun sayısını döndürür.|  
|[CSplitterWnd::GetColumnInfo](#getcolumninfo)|Belirtilen sütunda bilgileri döndürür.|  
|[CSplitterWnd::GetPane](#getpane)|Belirtilen satır ve sütun bölmesinde döndürür.|  
|[CSplitterWnd::GetRowCount](#getrowcount)|Geçerli bölmesinde satır sayısını döndürür.|  
|[CSplitterWnd::GetRowInfo](#getrowinfo)|Bilgi belirtilen satır döndürür.|  
|[CSplitterWnd::GetScrollStyle](#getscrollstyle)|Paylaşılan kaydırma çubuğu stili döndürür.|  
|[CSplitterWnd::IdFromRowCol](#idfromrowcol)|Alt bölmesinde belirtilen satır ve sütun penceresi Kimliğini döndürür.|  
|[CSplitterWnd::IsChildPane](#ischildpane)|Pencere şu anda bu Bölümlendirici penceresinin alt bölmesinde olup olmadığını belirlemek için çağrılır.|  
|[CSplitterWnd::IsTracking](#istracking)|Bölümlendirici çubuğu şu anda taşınıyor varsa belirler.|  
|[CSplitterWnd::RecalcLayout](#recalclayout)|Bölümlendirici pencere satır veya sütun boyutu ayarladıktan sonra yeniden görüntülemek için çağırın.|  
|[CSplitterWnd::SetActivePane](#setactivepane)|Çerçevede etkin olmasını bölmesi ayarlar.|  
|[CSplitterWnd::SetColumnInfo](#setcolumninfo)|Belirtilen sütun bilgileri ayarlamak için çağırın.|  
|[CSplitterWnd::SetRowInfo](#setrowinfo)|Belirtilen satır bilgilerini ayarlamak için çağırın.|  
|[CSplitterWnd::SetScrollStyle](#setscrollstyle)|Bölümlendirici pencere için yeni kaydırma çubuğu stil paylaşılan kaydırma çubuğu desteği belirtir.|  
|[CSplitterWnd::SplitColumn](#splitcolumn)|Burada bir çerçeve penceresinde dikey olarak böler gösterir.|  
|[CSplitterWnd::SplitRow](#splitrow)|Burada bir çerçeve penceresinde yatay olarak böler gösterir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSplitterWnd::OnDraw](#ondraw)|Bölümlendirici pencere çizmek için çerçevesi tarafından çağrılır.|  
|[CSplitterWnd::OnDrawSplitter](#ondrawsplitter)|Bölünmüş bir pencereyi görüntüsü oluşturur.|  
|[CSplitterWnd::OnInvertTracker](#oninverttracker)|Pencere boyutu ve şekli çerçeve pencere olarak aynı olacak şekilde Böl görüntüsü oluşturur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir genellikle türetilmiş bir uygulamaya özgü nesne bölmesidir [CView](../../mfc/reference/cview-class.md), ancak herhangi bir olabilir [CWnd](../../mfc/reference/cwnd-class.md) uygun alt pencere kimliğine sahip nesne  
  
 A `CSplitterWnd` bir üst nesne katıştırılmış genellikle [CFrameWnd](../../mfc/reference/cframewnd-class.md) veya [Cmdıchildwnd](../../mfc/reference/cmdichildwnd-class.md) nesnesi. Oluşturma bir `CSplitterWnd` aşağıdaki adımları kullanarak nesnesi:  
  
1.  Embed bir `CSplitterWnd` üst çerçevesinde üye değişkeni.  
  
2.  Üst çerçeve geçersiz kılma [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) üye işlevi.  
  
3.  Gelen geçersiz kılınan içinde `OnCreateClient`, çağrı [oluşturma](#create) veya [CreateStatic](#createstatic) üye işlevini `CSplitterWnd`.  
  
 Çağrı **oluşturma** dinamik Bölümlendirici pencere oluşturmak için üye işlevi. Dinamik Bölümlendirici pencere genellikle oluşturmak ve tek tek bölmeleri veya görünümlerini aynı belge sayısını kaydırma için kullanılır. Framework bir ilk bölmesi bölme için otomatik olarak oluşturur; ardından framework oluşturur, yeniden boyutlandırır ve kullanıcı Bölümlendirici pencere denetimleri çalıştığı gibi ek bölmeleri siler.  
  
 Çağırdığınızda **oluşturma**, bölmeleri tam olarak görüntülenecek küçük olduğunda belirleyen en az satır yüksekliğini ve sütun genişliği belirtin. Çağırdıktan sonra **oluşturma**, bu alt limitlerin çağırarak ayarlayabilirsiniz [SetColumnInfo](#setcolumninfo) ve [SetRowInfo](#setrowinfo) üye işlevleri.  
  
 Aynı zamanda `SetColumnInfo` ve `SetRowInfo` bir sütun için bir "ideal" genişlik ve bir satır için "ideal" yükseklik ayarlamak için üye işlevleri. Framework Bölümlendirici pencere görüntülendiğinde, ilk olarak üst çerçeve, ardından Bölümlendirici pencere görüntüler. Framework sonra sol üst köşesinden Bölümlendirici pencere istemci alanının sağ alt köşedeki çalışma kendi ideal boyutlarını göre satırları ve sütunları bölmelerinde çıkışı oluşturur.  
  
 Dinamik Bölümlendirici pencere tüm bölmelerde aynı sınıfının olması gerekir. Dinamik Bölümlendirici pencereler destek tanıdık uygulamaları, Microsoft Word ve Microsoft Excel içerir.  
  
 Kullanım `CreateStatic` statik Bölümlendirici pencere oluşturmak için üye işlevi. Kullanıcının yalnızca bir statik Bölümlendirici pencere veya değil, kendi numarası sipariş bölmelerinde boyutunu değiştirebilirsiniz.  
  
 Statik Bölümlendirici oluşturduğunuzda, tüm statik Bölümlendirici 's bölmeleri özellikle oluşturmanız gerekir. Üst çerçeve önce tüm bölmeleri oluşturduğunuzdan emin olun `OnCreateClient` üye fonksiyonu döndürür veya pencere doğru görüntülememek framework olacaktır.  
  
 `CreateStatic` Üye işlevi statik Bölümlendirici en az satır yüksekliğini ve sütun genişliği 0 ile otomatik olarak başlatır. Çağırdıktan sonra **oluşturma**, bu alt limitlerin çağırarak ayarlamak [SetColumnInfo](#setcolumninfo) ve [SetRowInfo](#setrowinfo) üye işlevleri. Aynı zamanda `SetColumnInfo` ve `SetRowInfo` çağırdıktan sonra `CreateStatic` belirtmek için ideal bölmesinde boyutları istenen.  
  
 Statik Bölümlendirici tek tek bölmeleri genellikle farklı sınıflara ait. Statik Bölümlendirici pencereler örnekler için bkz: grafik Düzenleyicisi'ni ve Windows Dosya Yöneticisi.  
  
 Bölümlendirici pencere özel kaydırma çubukları (dışında bölmeleri olabilir kaydırma çubukları) destekler. Bu kaydırma çubukları alt öğeleri olan `CSplitterWnd` nesne ve bölmeleri ile paylaşılır.  
  
 Bölümlendirici pencere oluşturduğunuzda, bu özel kaydırma çubukları oluşturun. Örneğin, bir `CSplitterWnd` bir satır, iki sütun vardır ve **WS_VSCROLL** stili iki bölme tarafından paylaşılan bir dikey kaydırma çubuğu görüntülenir. Kullanıcı kaydırma çubuğu taşıdığında `WM_VSCROLL` iletileri hem bölmeleri gönderilir. Kaydırma çubuğu konumu bölmeleri ayarladığınızda, paylaşılan kaydırma çubuğu ayarlanır.  
  
 Bölümlendirici pencereler hakkında daha fazla bilgi için bkz:  
  
- [Teknik Not 29](../../mfc/tn029-splitter-windows.md)  
  
-   Bilgi Bankası makalesi Q262024: nasıl yapılır: kullanım CPropertySheet, bir alt CSplitterWnd olarak  
  
 Dinamik Bölümlendirici pencereler oluşturma hakkında daha fazla bilgi için bkz:  
  
-   MFC örnek [karalama](../../visual-cpp-samples.md)  
  
-   MFC örnek [VIEWEX](../../visual-cpp-samples.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSplitterWnd`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxext.h  
  
##  <a name="activatenext"></a>CSplitterWnd::ActivateNext  
 Sonraki Bölme veya önceki bölme komutu gerçekleştirmeyi çerçevesi tarafından çağrılır.  
  
```  
virtual void ActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bPrev`  
 Etkinleştirmek için pencereyi gösterir. **DOĞRU** için önceki; **FALSE** İleri için.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu tarafından kullanılan üst düzey bir komuttur [CView](../../mfc/reference/cview-class.md) için temsilci seçme için sınıf `CSplitterWnd` uygulaması.  
  
##  <a name="canactivatenext"></a>CSplitterWnd::CanActivateNext  
 Sonraki Bölme veya önceki bölme komutu şu anda mümkün olup olmadığını denetlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bPrev`  
 Etkinleştirmek için pencereyi gösterir. **DOĞRU** için önceki; **FALSE** İleri için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu tarafından kullanılan üst düzey bir komuttur [CView](../../mfc/reference/cview-class.md) için temsilci seçme için sınıf `CSplitterWnd` uygulaması.  
  
##  <a name="create"></a>CSplitterWnd::Create  
 Dinamik Bölümlendirici pencere oluşturmak için çağrı **oluşturma** üye işlevi.  
  
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
 `pParentWnd`  
 Bölümlendirici penceresinin üst çerçeve penceresi.  
  
 *nMaxRows*  
 Bölümlendirici pencere satır sayısı. Bu değer 2 aşmamalıdır.  
  
 *nMaxCols*  
 Bölümlendirici pencere sütunlardaki maksimum sayısı. Bu değer 2 aşmamalıdır.  
  
 `sizeMin`  
 Bir bölme görüntülenebilir en küçük boyutu belirtir.  
  
 `pContext`  
 Bir işaretçi bir [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısı. Çoğu durumda bu, `pContext` üst çerçeve pencere geçirildi.  
  
 `dwStyle`  
 Pencere stili belirtir.  
  
 `nID`  
 Pencerenin alt pencere kimliği. Kimliği olabilir **AFX_IDW_PANE_FIRST** Bölümlendirici pencere başka bir Bölümlendirici pencere içinde iç içe geçmiş sürece.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Katıştırmak bir `CSplitterWnd` , üst bir [CFrameWnd](../../mfc/reference/cframewnd-class.md) veya [Cmdıchildwnd](../../mfc/reference/cmdichildwnd-class.md) aşağıdaki adımları alarak nesnesi:  
  
1.  Embed bir `CSplitterWnd` üst çerçevesinde üye değişkeni.  
  
2.  Üst çerçeve geçersiz kılma [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) üye işlevi.  
  
3.  Çağrı **oluşturma** içinde geçersiz kılınan üye işlevinden `OnCreateClient`.  
  
 Bir üst çerçevesinde bir Bölümlendirici pencere oluşturduğunuzda, üst çerçeve geçirmek `pContext` Bölümlendirici pencere parametresi. Aksi takdirde, bu parametre olabilir **NULL**.  
  
 Dinamik Bölümlendirici pencere ilk en az satır yüksekliğini ve sütun genişliği tarafından belirlenen `sizeMin` parametresi. Bir bölme tamamının gösterilmesi için çok küçük olup olmadığını belirlemek, bu alt limitlerin değiştirilebilir [SetRowInfo](#setrowinfo) ve [SetColumnInfo](#setcolumninfo) üye işlevleri.  
  
 Dinamik Bölümlendirici pencereler hakkında daha fazla bilgi için "Bölümlendirici pencereler" makalesine bakın [birden çok belge türü, görünümler ve çerçeve pencereleri](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik Not 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfına genel bakış.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]  
  
##  <a name="createscrollbarctrl"></a>CSplitterWnd::CreateScrollBarCtrl  
 Paylaşılan kaydırma çubuğu denetimi oluşturmak için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Pencere stili belirtir.  
  
 `nID`  
 Pencerenin alt pencere kimliği. Kimliği olabilir **AFX_IDW_PANE_FIRST** Bölümlendirici pencere başka bir Bölümlendirici pencere içinde iç içe geçmiş sürece.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçersiz kılma `CreateScrollBarCtrl` bir kaydırma çubuğunun yanında ek denetimler eklenecek. Normal Windows kaydırma çubuğu denetimleri oluşturmak için varsayılan davranıştır.  
  
##  <a name="createstatic"></a>CSplitterWnd::CreateStatic  
 Statik Bölümlendirici pencere oluşturmak için çağrı `CreateStatic` üye işlevi.  
  
```  
virtual BOOL CreateStatic(
    CWnd* pParentWnd,  
    int nRows,  
    int nCols,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentWnd`  
 Bölümlendirici penceresinin üst çerçeve penceresi.  
  
 `nRows`  
 Satır sayısı. Bu değer, 16 aşmamalıdır.  
  
 *nCols*  
 Sütun sayısı. Bu değer, 16 aşmamalıdır.  
  
 `dwStyle`  
 Pencere stili belirtir.  
  
 `nID`  
 Pencerenin alt pencere kimliği. Kimliği olabilir **AFX_IDW_PANE_FIRST** Bölümlendirici pencere başka bir Bölümlendirici pencere içinde iç içe geçmiş sürece.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 A `CSplitterWnd` bir üst genellikle katıştırılmış `CFrameWnd` veya [Cmdıchildwnd](../../mfc/reference/cmdichildwnd-class.md) aşağıdaki adımları alarak nesnesi:  
  
1.  Embed bir `CSplitterWnd` üst çerçevesinde üye değişkeni.  
  
2.  Üst çerçeve geçersiz kılma `OnCreateClient` üye işlevi.  
  
3.  Çağrı `CreateStatic` içinde geçersiz kılınan üye işlevinden [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient).  
  
 Statik Bölümlendirici pencere bölmeleri, genellikle farklı sınıflardan sabit sayıda içerir.  
  
 Statik Bölümlendirici pencere oluşturduğunuzda, aynı anda tüm bölmeleri oluşturmanız gerekir. [Yapılan](#createview) üye işlevi bu amaç için genellikle kullanılır, ancak diğer nonview sınıfları de oluşturabilirsiniz.  
  
 Statik Bölümlendirici pencere ilk en az satır yüksekliğini ve sütun genişliği 0'dır. Bir bölme tamamının gösterilmesi için çok küçük olduğunda belirlemek, bu alt limitlerin değiştirilebilir [SetRowInfo](#setrowinfo) ve [SetColumnInfo](#setcolumninfo) üye işlevleri.  
  
 Statik Bölümlendirici pencere kaydırma çubukları eklemek için Ekle **WS_HSCROLL** ve **WS_VSCROLL** için stiller `dwStyle`.  
  
 "Bölümlendirici pencereler" makalesine bakın [birden çok belge türü, görünümler ve çerçeve pencereleri](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik Not 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` statik Bölümlendirici pencereler hakkında daha fazla bilgi için sınıfına genel bakış.  
  
##  <a name="createview"></a>CSplitterWnd::CreateView  
 Statik Bölümlendirici pencere bölmeleri oluşturur.  
  
```  
virtual BOOL CreateView(
    int row,  
    int col,  
    CRuntimeClass* pViewClass,  
    SIZE sizeInit,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>Parametreler  
 `row`  
 Bölümlendirici pencere satırın yeni görünüm yerleştirileceği belirtir.  
  
 `col`  
 Bölümlendirici pencere sütun yeni görünüm yerleştirileceği belirtir.  
  
 `pViewClass`  
 Belirtir [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yeni görünüm.  
  
 *sizeInit*  
 Yeni Görünüm başlangıç boyutunu belirtir.  
  
 `pContext`  
 Görünümü oluşturmak için kullanılan bir oluşturma bağlamı için bir işaretçi (genellikle `pContext` üst çerçeve geçersiz kılınan geçirilen [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) içinde Bölümlendirici pencere oluşturulmakta üye işlevi).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Statik Bölümlendirici penceresinin tüm bölmeleri Bölümlendirici çerçevesi görüntülemeden önce oluşturulması gerekir.  
  
 Framework de bölmesi, satır veya sütun bir dinamik Bölümlendirici pencere kullanıcı böler zaman yeni bölmeleri oluşturmak için bu üye işlevi çağırır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#4](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]  
  
##  <a name="csplitterwnd"></a>CSplitterWnd::CSplitterWnd  
 Çağrı oluşturmak için bir `CSplitterWnd` nesnesi.  
  
```  
CSplitterWnd();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CSplitterWnd` iki adımda nesne. İlk olarak, oluşturur Oluşturucusu çağrısı `CSplitterWnd` nesnesini genişletin ve ardından arama [oluşturma](#create) Bölümlendirici pencere oluşturur ve ona ekler üye işlevi `CSplitterWnd` nesnesi.  
  
##  <a name="deletecolumn"></a>CSplitterWnd::DeleteColumn  
 Bir sütunu Bölümlendirici penceresinden siler.  
  
```  
virtual void DeleteColumn(int colDelete);
```  
  
### <a name="parameters"></a>Parametreler  
 *colDelete*  
 Silinecek sütunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlev dinamik Bölümlendirici pencere mantığını uygulamak için çerçevesi tarafından çağrılır (diğer bir deyişle, bölümlendirici pencere varsa **SPLS_DYNAMIC_SPLIT** stili). Bunu, birlikte sanal işlev özelleştirilebilir [yapılan](#createview), daha gelişmiş dinamik ayırıcılar uygulamak için.  
  
##  <a name="deleterow"></a>CSplitterWnd::DeleteRow  
 Bir satır ayırıcı penceresinden siler.  
  
```  
virtual void DeleteRow(int rowDelete);
```  
  
### <a name="parameters"></a>Parametreler  
 *rowDelete*  
 Satırın silinmesi belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlev dinamik Bölümlendirici pencere mantığını uygulamak için çerçevesi tarafından çağrılır (diğer bir deyişle, bölümlendirici pencere varsa **SPLS_DYNAMIC_SPLIT** stili). Bunu, birlikte sanal işlev özelleştirilebilir [yapılan](#createview), daha gelişmiş dinamik ayırıcılar uygulamak için.  
  
##  <a name="deleteview"></a>CSplitterWnd::DeleteView  
 Bir görünüm Bölümlendirici penceresinden siler.  
  
```  
virtual void DeleteView(
    int row,  
    int col);
```  
  
### <a name="parameters"></a>Parametreler  
 `row`  
 Bölümlendirici pencere satırındaki görünümü silmek belirtir.  
  
 `col`  
 Bölümlendirici pencere sütunu görünümü silmek belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Etkin görünüm silinirse, sonraki görünüme etkin hale gelir. Varsayılan uygulama görünümü otomatik varsayar silmek [PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy).  
  
 Bu üye işlev dinamik Bölümlendirici pencere mantığını uygulamak için çerçevesi tarafından çağrılır (diğer bir deyişle, bölümlendirici pencere varsa **SPLS_DYNAMIC_SPLIT** stili). Bunu, birlikte sanal işlev özelleştirilebilir [yapılan](#createview), daha gelişmiş dinamik ayırıcılar uygulamak için.  
  
##  <a name="dokeyboardsplit"></a>CSplitterWnd::DoKeyboardSplit  
 Komut, genellikle "Pencere Böl." Böl klavye gerçekleştirir  
  
```  
virtual BOOL DoKeyboardSplit();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu tarafından kullanılan üst düzey bir komuttur [CView](../../mfc/reference/cview-class.md) için temsilci seçme için sınıf `CSplitterWnd` uygulaması.  
  
##  <a name="doscroll"></a>CSplitterWnd::DoScroll  
 Eşitlenen bölünmüş windows kaydırma gerçekleştirir.  
  
```  
virtual BOOL DoScroll(
    CView* pViewFrom,  
    UINT nScrollCode,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pViewFrom`  
 Kaydırma ileti kaynaklandığı görünüm için bir işaretçi.  
  
 `nScrollCode`  
 Kullanıcı gösteren bir kaydırma çubuğunun kod isteği kaydırma. Bu parametre iki bölümden oluşur: yatay kaydırma gerçekleşen türünü belirler, düşük düzey bir bayt ve dikey olarak gerçekleşen kaydırma türünü belirleyen bir yüksek düzey bayt:  
  
- **SB_BOTTOM** alt kaydırır.  
  
- **SB_LINEDOWN** bir satırı aşağı kaydırır.  
  
- **SB_LINEUP** bir satırı yukarı kaydırır.  
  
- **SB_PAGEDOWN** bir sayfa aşağı kaydırır.  
  
- **SB_PAGEUP** bir sayfa yukarı kaydırır.  
  
- **SB_TOP** dön birlikte kayar.  
  
 `bDoScroll`  
 Belirtilen kaydırma eylem mi gerçekleşeceğini belirler. Varsa `bDoScroll` olan **TRUE** (diğer bir deyişle, alt pencere varsa ve bölünmüş windows kaydırma aralığı varsa), belirtilen kaydırma eylem; varsa gerçekleştirilebildiği sonra `bDoScroll` olan **FALSE** (diğer bir deyişle, alt pencere var veya bölme görünüm hiçbir kaydırma aralığına sahip), sonra da kaydırma oluşmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşitlenen kaydırma oluşursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlev görünümü kaydırma iletisi aldığında eşitlenmiş bölünmüş windows kaydırma gerçekleştirmek için çerçevesi tarafından çağrılır. Eşitlenen kaydırma izin verilmeden önce kullanıcı tarafından bir eylem gerektiren için geçersiz kılın.  
  
##  <a name="doscrollby"></a>CSplitterWnd::DoScrollBy  
 Bölünmüş Pencereler belirli sayıda piksel kadar kaydırır.  
  
```  
virtual BOOL DoScrollBy(
    CView* pViewFrom,  
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pViewFrom`  
 Kaydırma ileti kaynaklandığı görünüm için bir işaretçi.  
  
 `sizeScroll`  
 Yatay ve dikey olarak kaydırılan piksel sayısı.  
  
 bDoScroll  
 Belirtilen kaydırma eylem mi gerçekleşeceğini belirler. Varsa `bDoScroll` olan **TRUE** (diğer bir deyişle, alt pencere varsa ve bölünmüş windows kaydırma aralığı varsa), belirtilen kaydırma eylem; varsa gerçekleştirilebildiği sonra `bDoScroll` olan **FALSE** (diğer bir deyişle, alt pencere var veya bölme görünüm hiçbir kaydırma aralığına sahip), sonra da kaydırma oluşmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşitlenen kaydırma oluşursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi kaydırma iletisine yanıt olarak çerçevesi tarafından çağrılır, gerçekleştirmek için belirttiği piksel cinsinden miktar bölünmüş pencerelerini kaydırma eşitlenen `sizeScroll`. Pozitif değerler aşağı ve sağa kaydırma gösterir; negatif değerler yukarı ve sola kaydırma gösterir.  
  
 Kaydırma izin vermeden önce kullanıcı tarafından bir eylem gerektiren için geçersiz kılın.  
  
##  <a name="getactivepane"></a>CSplitterWnd::GetActivePane  
 Odağı veya çerçevede etkin görünüm etkin bölmesinden belirler.  
  
```  
virtual CWnd* GetActivePane(
    int* pRow = NULL,  
    int* pCol = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pRow`  
 Bir işaretçi bir **int** etkin bölmeyi satır sayısı alınamadı.  
  
 `pCol`  
 Bir işaretçi bir **int** etkin bölmeyi sütun sayısı alınamadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Etkin bölmeyi işaretçi. **NULL** hiçbir etkin bölmeyi varsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Bölümlendirici pencere etkin bölmesinde belirlemek için çerçevesi tarafından çağrılır. Etkin bölmeyi alma önce kullanıcı tarafından bir eylem gerektiren için geçersiz kılın.  
  
##  <a name="getcolumncount"></a>CSplitterWnd::GetColumnCount  
 Geçerli bölmesinde sütun sayısını döndürür.  
  
```  
int GetColumnCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Mevcut sütun sayısı Bölümlendirici döndürür. Bir statik Bölümlendirici için bu maksimum sütun sayısını olacaktır.  
  
##  <a name="getcolumninfo"></a>CSplitterWnd::GetColumnInfo  
 Belirtilen sütunda bilgileri döndürür.  
  
```  
void GetColumnInfo(
    int col,  
    int& cxCur,  
    int& cxMin) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `col`  
 Bir sütunu belirtir.  
  
 *cxCur*  
 Bir başvuru bir `int` sütunun geçerli genişliği ayarlanacak.  
  
 `cxMin`  
 Bir başvuru bir `int` sütunu için geçerli en küçük genişliği ayarlanacak.  
  
##  <a name="getpane"></a>CSplitterWnd::GetPane  
 Belirtilen satır ve sütun bölmesinde döndürür.  
  
```  
CWnd* GetPane(
    int row,  
    int col) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `row`  
 Bir satır belirtir.  
  
 `col`  
 Bir sütunu belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen satır ve sütun bölmesinde döndürür. Döndürülen genellikle bölmesidir bir [CView](../../mfc/reference/cview-class.md)-türetilmiş sınıf.  
  
##  <a name="getrowcount"></a>CSplitterWnd::GetRowCount  
 Geçerli bölmesinde satır sayısını döndürür.  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölümlendirici penceresinde geçerli satır sayısını döndürür. Statik Bölümlendirici pencere için bu satır sayısının üst sınırını olacaktır.  
  
##  <a name="getrowinfo"></a>CSplitterWnd::GetRowInfo  
 Bilgi belirtilen satır döndürür.  
  
```  
void GetRowInfo(
    int row,  
    int& cyCur,  
    int& cyMin) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `row`  
 Bir satır belirtir.  
  
 `cyCur`  
 Başvuru `int` geçerli yüksekliğini piksel cinsinden ayarlanmalıdır.  
  
 `cyMin`  
 Başvuru `int` geçerli en küçük yükseklik piksel cinsinden satırın ayarlanacak.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen satır hakkında bilgi edinmek için bu üye işlevini çağırın. `cyCur` Parametresi belirtilen satır geçerli yüksekliği ile doldurulur ve `cyMin` en küçük yüksekliğini satır ile doldurulur.  
  
##  <a name="getscrollstyle"></a>CSplitterWnd::GetScrollStyle  
 Bölümlendirici pencere paylaşılan kaydırma çubuğu stili döndürür.  
  
```  
DWORD GetScrollStyle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir veya daha fazla aşağıdaki windows bayrakları, başarılı olursa stil:  
  
- **WS_HSCROLL** Bölümlendirici şu anda paylaşılan yatay kaydırma çubuklarını yönetiyorsa.  
  
- **WS_VSCROLL** Bölümlendirici şu anda paylaşılan dikey kaydırma çubukları yönetiyorsa.  
  
 Bölümlendirici pencere sıfır ise, şu anda tüm paylaşılan kaydırma çubukları yönetmez.  
  
##  <a name="idfromrowcol"></a>CSplitterWnd::IdFromRowCol  
 Alt pencere kimliği için belirtilen satır ve sütun bölmesinde alır.  
  
```  
int IdFromRowCol(
    int row,  
    int col) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `row`  
 Bölümlendirici pencere satır belirtir.  
  
 `col`  
 Bölümlendirici pencere sütunu belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Alt pencere kimliği bölmesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi nonviews bölmeleri olarak oluşturmak için kullanılır ve bölmesinde var. önce çağrılabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#5](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]  
  
##  <a name="ischildpane"></a>CSplitterWnd::IsChildPane  
 Belirler olup olmadığını `pWnd` şu anda bu Bölümlendirici penceresinin alt bölmesinde değil.  
  
```  
BOOL IsChildPane(
    CWnd* pWnd,  
    int* pRow,  
    int* pCol);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) sınanacak nesnesi.  
  
 `pRow`  
 Bir işaretçi bir `int` satır numarası depolanacağı.  
  
 `pCol`  
 Bir işaretçi bir `int` depolanacağı bir sütun numarası.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan, `pWnd` şu anda bu Bölümlendirici penceresinin alt bölmesinde olduğu ve `pRow` ve `pCol` Bölümlendirici pencere bölmesine konumu ile doldurulur. Varsa `pWnd` alt bölmesinde değil Bu Bölümlendirici pencere 0 değeri döndürülür.  
  
### <a name="remarks"></a>Açıklamalar  
 6.0 önce Visual C++ sürümlerinde, bu işlev olarak tanımlandı  
  
 `BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`  
  
 Bu sürümü artık kullanımdan kalkmıştır ve kullanılmamalıdır.  
  
##  <a name="istracking"></a>CSplitterWnd::IsTracking  
 Ayırıcı çubuğu penceresinde şu anda taşınıyor varsa belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsTracking();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölme işlemi devam ediyor, sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="ondrawsplitter"></a>CSplitterWnd::OnDrawSplitter  
 Bölünmüş bir pencereyi görüntüsü oluşturur.  
  
```  
virtual void OnDrawSplitter(
    CDC* pDC,  
    ESplitType nType,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Çizmek cihaz bağlamı için bir işaretçi. Varsa `pDC` olan **NULL**, ardından [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) çağrılır pencere çerçevesi ve bölme tarafından çizilir.  
  
 `nType`  
 Değerini **enum ESplitType**, olabilen şunlardan biri:  
  
- **splitBox** Bölümlendirici kutusuna sürükleyin.  
  
- `splitBar`İki Bölünmüş Pencereler arasında görünen çubuğu.  
  
- **splitIntersection** bölünmüş windows kesişimi. Bu öğe, Windows 95/98 çalıştırırken çağrılmaz.  
  
- **splitBorder** bölünmüş pencere kenarlıkları.  
  
 `rect`  
 Bir başvuru bir [CRect](../../atl-mfc-shared/reference/crect-class.md) boyutu ve şekli bölünmüş Windows belirtme nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlev çizme ve tam bir Bölümlendirici pencere özelliklerini belirtmek için çerçevesi tarafından çağrılır. Geçersiz kılma `OnDrawSplitter` gelişmiş özelleştirmesi için bir Bölümlendirici pencere çeşitli grafik bileşenlerini görüntüler. Ayırıcı çubukları bağlandıkları birlikte karıştırılan varsayılan görüntülerin içinde Windows ya da Microsoft Windows 95/98, Microsoft Works Bölümlendirici için benzer.  
  
 Dinamik Bölümlendirici pencereler hakkında daha fazla bilgi için "Bölümlendirici pencereler" makalesine bakın [birden çok belge türü, görünümler ve çerçeve pencereleri](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik Not 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfına genel bakış.  
  
##  <a name="oninverttracker"></a>CSplitterWnd::OnInvertTracker  
 Pencere boyutu ve şekli çerçeve pencere olarak aynı olacak şekilde Böl görüntüsü oluşturur.  
  
```  
virtual void OnInvertTracker(const CRect& rect);
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 Başvuru bir `CRect` izleme Dikdörtgen Belirtme nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlev ayırıcılar yeniden boyutlandırma sırasında çerçevesi tarafından çağrılır. Geçersiz kılma `OnInvertTracker` gelişmiş özelleştirmesi için Bölümlendirici pencere görüntüler. Ayırıcı çubukları bağlandıkları birlikte karıştırılan varsayılan görüntülerin içinde Windows ya da Microsoft Windows 95/98, Microsoft Works Bölümlendirici için benzer.  
  
 Dinamik Bölümlendirici pencereler hakkında daha fazla bilgi için "Bölümlendirici pencereler" makalesine bakın [birden çok belge türü, görünümler ve çerçeve pencereleri](../../mfc/multiple-document-types-views-and-frame-windows.md), [Teknik Not 29](../../mfc/tn029-splitter-windows.md)ve `CSplitterWnd` sınıfına genel bakış.  
  
##  <a name="recalclayout"></a>CSplitterWnd::RecalcLayout  
 Bölümlendirici pencere satır veya sütun boyutu ayarladıktan sonra yeniden görüntülemek için çağırın.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Satır ve sütun boyutlarıyla ayarlanan sonra Bölümlendirici penceresini düzgün görüntülemek için bu üye işlevini çağırın [SetRowInfo](#setrowinfo) ve [SetColumnInfo](#setcolumninfo) üye işlevleri. Bölümlendirici pencere görünür hale önce oluşturma işleminin bir parçası satır ve sütun boyutları değiştirirseniz, bu üye işlevi çağırmak gerekli değildir.  
  
 Her kullanıcı Bölümlendirici yeniden boyutlandırır veya bölme taşır framework bu üye işlevi çağırır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CSplitterWnd::SetColumnInfo](#setcolumninfo).  
  
##  <a name="setactivepane"></a>CSplitterWnd::SetActivePane  
 Çerçevede etkin olmasını bölmesi ayarlar.  
  
```  
virtual void SetActivePane(
    int row,  
    int col,  
    CWnd* pWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `row`  
 Varsa `pWnd` olan **NULL**, etkin kalacak bölmesinde satır belirtir.  
  
 `col`  
 Varsa `pWnd` olan **NULL**, etkin kalacak bölmesinde sütun belirtir.  
  
 `pWnd`  
 Bir işaretçi bir `CWnd` nesnesi. Varsa **NULL**, tarafından belirtilen bölmesinde `row` ve `col` etkin olarak ayarlayın. Aksi takdirde **NULL**, etkin olarak bölmesinde belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi, kullanıcı bölmesine çerçeve penceresi içinde odak değiştiğinde bir bölme etkin olarak ayarlamak için çerçevesi tarafından çağrılır. Açıkça çağırabilir `SetActivePane` odağı belirtilen görünümü değiştirmek için.  
  
 Satır ve sütun sağlayarak bölmesinde belirtin **veya** sağlayarak `pWnd`.  
  
##  <a name="setcolumninfo"></a>CSplitterWnd::SetColumnInfo  
 Belirtilen sütun bilgileri ayarlamak için çağırın.  
  
```  
void SetColumnInfo(
    int col,  
    int cxIdeal,  
    int cxMin);
```  
  
### <a name="parameters"></a>Parametreler  
 `col`  
 Bölümlendirici pencere sütunu belirtir.  
  
 *cxIdeal*  
 Bölümlendirici pencere sütun için ideal bir genişliğini piksel cinsinden belirtir.  
  
 `cxMin`  
 Bölümlendirici pencere sütun için en az bir genişlik piksel cinsinden belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni minimum genişlik ve bir sütun için ideal genişliğini ayarlamak için bu üye işlevini çağırın. Sütun en küçük değeri, zaman sütun tam olarak görüntülenecek küçük olacağını belirler.  
  
 Bölümlendirici pencere çerçevesi görüntülediğinde, sol üst köşesinden Bölümlendirici pencere istemci alanının sağ alt köşedeki çalışma kendi ideal boyutlarını göre satırları ve sütunları bölmelerinde çıkışı oluşturur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#6](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]  
  
##  <a name="setrowinfo"></a>CSplitterWnd::SetRowInfo  
 Belirtilen satır bilgilerini ayarlamak için çağırın.  
  
```  
void SetRowInfo(
    int row,  
    int cyIdeal,  
    int cyMin);
```  
  
### <a name="parameters"></a>Parametreler  
 `row`  
 Bölümlendirici pencere satır belirtir.  
  
 *cyIdeal*  
 Bölümlendirici pencere satır için ideal bir yüksekliğini piksel cinsinden belirtir.  
  
 `cyMin`  
 Bölümlendirici pencere satır için en küçük yükseklik piksel cinsinden belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir yeni en küçük yükseklik ve bir satır için ideal yükseklik ayarlamak için bu üye işlevini çağırın. Satır minimum değeri satır ne zaman tam olarak görüntülenecek küçük olacağını belirler.  
  
 Bölümlendirici pencere çerçevesi görüntülediğinde, sol üst köşesinden Bölümlendirici pencere istemci alanının sağ alt köşedeki çalışma kendi ideal boyutlarını göre satırları ve sütunları bölmelerinde çıkışı oluşturur.  
  
##  <a name="setscrollstyle"></a>CSplitterWnd::SetScrollStyle  
 Bölümlendirici pencere için yeni kaydırma stil paylaşılan kaydırma çubuğu desteği belirtir.  
  
```  
void SetScrollStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Bölümlendirici pencere için yeni kaydırma stil paylaşılan aşağıdaki değerlerden biri olabilir kaydırma çubuğu desteği:  
  
- **WS_HSCROLL** Oluştur/Göster yatay kaydırma çubukları paylaşılan.  
  
- **WS_VSCROLL** Oluştur/Göster dikey paylaşılan kaydırma çubukları.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kaydırma çubuğunun oluşturulduktan sonra onu değil yok edilir olsa bile `SetScrollStyle` bu stili; adlı bunun yerine bu kaydırma çubukları gizli. Bu, gizli olsa bile durumlarına korumak kaydırma çubuklarını sağlar. Çağırdıktan sonra `SetScrollStyle` çağırmak gerekli olan [RecalcLayout](#recalclayout) tüm değişikliklerin etkili olması.  
  
##  <a name="splitcolumn"></a>CSplitterWnd::SplitColumn  
 Burada bir çerçeve penceresinde dikey olarak böler gösterir.  
  
```  
virtual BOOL SplitColumn(int cxBefore);
```  
  
### <a name="parameters"></a>Parametreler  
 *cxBefore*  
 Bölünmüş önce oluştuğu piksel cinsinden konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dikey Bölümlendirici pencere oluşturulduğunda, bu üye işlev çağrılır. `SplitColumn`bölünmenin gerçekleştiği varsayılan konumu gösterir.  
  
 `SplitColumn`dinamik Bölümlendirici pencere mantığını uygulamak için çerçevesi tarafından çağrılır (diğer bir deyişle, bölümlendirici pencere varsa **SPLS_DYNAMIC_SPLIT** stili). Bunu, birlikte sanal işlev özelleştirilebilir [yapılan](#createview), daha gelişmiş dinamik ayırıcılar uygulamak için.  
  
##  <a name="splitrow"></a>CSplitterWnd::SplitRow  
 Burada bir çerçeve penceresinde yatay olarak böler gösterir.  
  
```  
virtual BOOL SplitRow(int cyBefore);
```  
  
### <a name="parameters"></a>Parametreler  
 *cyBefore*  
 Bölünmüş önce oluştuğu piksel cinsinden konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Yatay bölümlendirici pencere oluşturulduğunda bu üye işlev çağrılır. `SplitRow`bölünmenin gerçekleştiği varsayılan konumu gösterir.  
  
 `SplitRow`dinamik Bölümlendirici pencere mantığını uygulamak için çerçevesi tarafından çağrılır (diğer bir deyişle, bölümlendirici pencere varsa **SPLS_DYNAMIC_SPLIT** stili). Bunu, birlikte sanal işlev özelleştirilebilir [yapılan](#createview), daha gelişmiş dinamik ayırıcılar uygulamak için.  
  
##  <a name="ondraw"></a>CSplitterWnd::OnDraw  
 Bölümlendirici pencere çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek VIEWEX](../../visual-cpp-samples.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CView sınıfı](../../mfc/reference/cview-class.md)   
 [CWnd Sınıfı](../../mfc/reference/cwnd-class.md)
