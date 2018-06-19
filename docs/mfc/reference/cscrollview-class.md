---
title: CScrollView sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82ffdb26c5766a0ff7cbada511c9bc9c82ebfd93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375548"
---
# <a name="cscrollview-class"></a>CScrollView sınıfı
A [CView](../../mfc/reference/cview-class.md) yetenekleri kaydırma ile.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CScrollView : public CView  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CScrollView::CScrollView](#cscrollview)|Oluşturan bir `CScrollView` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CScrollView::CheckScrollBars](#checkscrollbars)|Kaydırma görünüm yatay ve dikey kaydırma çubukları olup olmadığını gösterir.|  
|[CScrollView::FillOutsideRect](#filloutsiderect)|Kaydırma alanı dışında bir görünüm alanını doldurur.|  
|[CScrollView::GetDeviceScrollPosition](#getdevicescrollposition)|Cihaz birimlerindeki geçerli kaydırma konumunu alır.|  
|[CScrollView::GetDeviceScrollSizes](#getdevicescrollsizes)|Geçerli eşleme modunu, toplam boyutu ve kaydırılabilir görünüm satır ve sayfa boyutunu alır. Cihaz birimlerinde boyutlarıdır.|  
|[CScrollView::GetScrollPosition](#getscrollposition)|Mantıksal birimler geçerli kaydırma konumunu alır.|  
|[CScrollView::GetTotalSize](#gettotalsize)|Kaydırma görünüm toplam boyutu, mantıksal birimler cinsinden alır.|  
|[CScrollView::ResizeParentToFit](#resizeparenttofit)|Çerçevesini boyutunu dikte görünüme boyutunu neden olur.|  
|[CScrollView::ScrollToPosition](#scrolltoposition)|Mantıksal birimler cinsinden belirtilen verilen bir noktaya görünümüne kayar.|  
|[CScrollView::SetScaleToFitSize](#setscaletofitsize)|Kaydırma görünüm ölçek sığacak şekilde moduna geçirir.|  
|[CScrollView::SetScrollSizes](#setscrollsizes)|Kaydırma görünümün eşleme modu, toplam boyutu ve yatay ve dikey kaydırma tutarlar ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kendiniz türetilmiş herhangi bir sınıf kaydırma standart işleyebilir `CView` ileti eşlemeli kılarak [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) ve [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) üye işlevleri. Ancak `CScrollView` aşağıdaki özellikleri ekler, `CView` özellikleri:  
  
-   Pencere ve görünüm penceresinin boyutlarını ve eşleme modları yönetir.  
  
-   Kaydırma çubuğu iletilere yanıt olarak otomatik olarak kayar.  
  
-   Klavye, fare kaydırma olmayan ya da IntelliMouse tekerleği yanıt iletilerini otomatik olarak kayar.  
  
 Klavye yanıt iletilerini otomatik olarak kaydırmak için bir WM_KEYDOWN ileti ekleyin ve test VK_DOWN, VK_PREV ve görüşmesi için [SetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787597).  
  
 Fare tekerleği kendiniz ileti eşlemeli geçersiz kılarak kaydırma işleyebilir [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) ve [OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel) üye işlevleri. İçin oldukları gibi `CScrollView`, bu üye işlevleri desteklemek için önerilen davranışa [WM_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617), tekerleği döndürme ileti.  
  
 Otomatik kaydırma avantajlarından yararlanmak için Görünüm sınıfından türetilen `CScrollView` yerine gelen `CView`. Görünüm ilk oluşturulduğunda, belge, çağrı boyutuna göre kaydırılabilir görünüm boyutunu hesaplamak istiyorsanız `SetScrollSizes` geçersiz kılma herhangi birinin üyesi işlevinden [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) veya [ CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate). (Belgenin boyutunu sorgulamak için kendi kod yazmanız gerekir. Bir örnek için bkz: [karalama örnek](../../visual-cpp-samples.md).)  
  
 Çağrı `SetScrollSizes` üye işlevi görünümün eşleme modu, toplam boyut kaydırma görünümü ve yatay ve dikey olarak kaydırmak için tutarların ayarlar. Mantıksal birimleri tüm boyutlarıdır. Görünümün mantıksal boyutu genellikle belgede saklanan verilerden hesaplanır, ancak bazı durumlarda sabit bir boyuta belirtmek isteyebilirsiniz. Her iki yaklaşımın örnekleri için bkz: [CScrollView::SetScrollSizes](#setscrollsizes).  
  
 Yatay ve dikey olarak mantıksal birimler cinsinden kaydırma tutarlarının belirtin. Varsayılan olarak kullanıcı kaydırma çubuğu mil kaydırma kutusunun dışında tıklarsa, `CScrollView` "sayfası." kaydırır Kullanıcı her iki ucunda bir kaydırma çubuğunun kaydırma ok tıklarsa `CScrollView` bir "satırı." kaydırır Varsayılan olarak, bir görünüm toplam boyutu 1/10 sayfasıdır; Sayfa boyutu 1/10 satırıdır. Özel boyutlarında geçirerek bu varsayılan değerleri geçersiz kılmak `SetScrollSizes` üye işlevi. Örneğin, yatay boyutu toplam boyutu ve satırının yüksekliğini dikey boyuta genişliğinin bazı kesir için geçerli yazı tipini ayarlayabilirsiniz.  
  
 Kaydırma, yerine `CScrollView` geçerli pencere boyutu görünümüne otomatik olarak ölçeklendirebilirsiniz. Bu modda, hiç kaydırma çubukları görünüme sahiptir ve mantıksal görünümü uzatılabilir ya da pencerenin istemci alanını tam olarak sığması için küçültülebilir. Bu ölçek-fit özelliği kullanmak için arama [CScrollView::SetScaleToFitSize](#setscaletofitsize). (Ya da çağrısı `SetScaleToFitSize` veya `SetScrollSizes`, ancak ikisini.)  
  
 Önce `OnDraw` türetilmiş görünüm sınıfınızın üye işlevi çağrıldığında `CScrollView` otomatik olarak görünüm penceresinin başlangıç ayarlar `CPaintDC` bunu geçirir cihaz bağlamı nesne `OnDraw`.  
  
 Kayan pencere görünüm penceresinin başlangıç ayarlamak için `CScrollView` geçersiz kılmaları [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc). Bu düzeltme için otomatik `CPaintDC` cihaz bağlamı, `CScrollView` geçirir `OnDraw`, ancak çağırmalısınız **CScrollView::OnPrepareDC** kendiniz herhangi bir cihaz bağlamları, gibikullandığınız`CClientDC`. Geçersiz kılabilirsiniz **CScrollView::OnPrepareDC** Kalem, arka plan rengi ve diğer çizim öznitelikleri ayarlanmasına, ancak ölçeklendirme yapmak için temel sınıf çağırın.  
  
 Kaydırma çubukları aşağıdaki durumlarda gösterildiği gibi bir görünüm göre üç yerde görünebilir:  
  
-   Görünümü kullanmak için standart pencere stili kaydırma çubukları ayarlanabilir **WS_HSCROLL** ve **WS_VSCROLL**[Windows stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
-   Kaydırma çubuğu denetimleri de içinde durum framework iletir görünümü içeren çerçeve eklenmesi `WM_HSCROLL` ve `WM_VSCROLL` şu anda etkin görünüm çerçeve penceresinden iletileri.  
  
-   Framework de iletir kaydırma iletilerden bir `CSplitterWnd` Bölümlendirici denetimi şu anda etkin Bölümlendirici bölmesine (Görünüm). Konumlandırıldığında bir [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) paylaşılan kaydırma çubukları ile bir `CScrollView` nesne kendi oluşturmak yerine paylaşılan olanları kullanır.  
  
 Kullanma hakkında daha fazla bilgi için `CScrollView`, bkz: [belge/görünüm mimarisinin](../../mfc/document-view-architecture.md) ve [türetilmiş görünüm sınıfları kullanılabilir MFC'de](../../mfc/derived-view-classes-available-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CScrollView`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="checkscrollbars"></a>  CScrollView::CheckScrollBars  
 Kaydırma görünüm yatay ve dikey çubukları olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
void CheckScrollBars(
    BOOL& bHasHorzBar,  
    BOOL& bHasVertBar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *bHasHorzBar*  
 Yatay kaydırma çubuğu uygulaması olduğunu gösterir.  
  
 *bHasVertBar*  
 Dikey kaydırma çubuğu uygulaması olduğunu gösterir.  
  
##  <a name="cscrollview"></a>  CScrollView::CScrollView  
 Oluşturan bir `CScrollView` nesnesi.  
  
```  
CScrollView();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ya da çağırmalıdır `SetScrollSizes` veya `SetScaleToFitSize` önce kaydırma görünümü kullanılabilir.  
  
##  <a name="filloutsiderect"></a>  CScrollView::FillOutsideRect  
 Çağrı `FillOutsideRect` kaydırma alanının dışında görünür görünümün alanı dolduracak şekilde.  
  
```  
void FillOutsideRect(
    CDC* pDC,  
    CBrush* pBrush);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Doldurma yapılması olduğu cihaz bağlamı.  
  
 `pBrush`  
 Alan doldurulacak olduğu Fırçası.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `FillOutsideRect` kaydırma görünümün içinde `OnEraseBkgnd` aşırı arka plan yeniden çizerken önlemek için işleyici işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]  
  
##  <a name="getdevicescrollposition"></a>  CScrollView::GetDeviceScrollPosition  
 Çağrı `GetDeviceScrollPosition` geçerli yatay ve dikey konumda kaydırma kutularının kaydırma çubukları gerektiğinde.  
  
```  
CPoint GetDeviceScrollPosition() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yatay ve dikey konumları (aygıt birimleri) kaydırma kutuların bir `CPoint` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu koordinat çifti için görünümünün sol üst köşesinde kaydırılan belge konumda karşılık gelir. Fare aygıtı konumlar kaydırma görünüm aygıt konumlara kaydırma işlemi için kullanışlıdır.  
  
 `GetDeviceScrollPosition` cihaz birimlerinde değerleri döndürür. Mantıksal birimler istiyorsanız kullanın `GetScrollPosition` yerine.  
  
##  <a name="getdevicescrollsizes"></a>  CScrollView::GetDeviceScrollSizes  
 `GetDeviceScrollSizes` Geçerli eşleme modunu, toplam boyutu ve kaydırılabilir görünüm satır ve sayfa boyutunu alır.  
  
```  
void GetDeviceScrollSizes(
    int& nMapMode,  
    SIZE& sizeTotal,  
    SIZE& sizePage,  
    SIZE& sizeLine) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nMapMode`  
 Bu görünüm için geçerli eşleme modunu döndürür. Olası değerler listesi için bkz: `SetScrollSizes`.  
  
 `sizeTotal`  
 Kaydırma görünümü geçerli toplam boyutu aygıt birimlerinde döndürür.  
  
 `sizePage`  
 Bir kaydırma çubuğunun mil her yönde yanıt fare olarak kaydırmak için geçerli yatay ve dikey tutarlar tıklatın döndürür. **Cx** üyeyi içeren yatay tutar. **Cy** üyeyi içeren dikey tutar.  
  
 `sizeLine`  
 Her yönde yanıt fare olarak kaydırmak için geçerli yatay ve dikey tutarlar kaydırma okunu döndürür. **Cx** üyeyi içeren yatay tutar. **Cy** üyeyi içeren dikey tutar.  
  
### <a name="remarks"></a>Açıklamalar  
 Cihaz birimlerinde boyutlarıdır. Bu üye fonksiyonu nadiren çağrılır.  
  
##  <a name="getscrollposition"></a>  CScrollView::GetScrollPosition  
 Çağrı `GetScrollPosition` geçerli yatay ve dikey konumda kaydırma kutularının kaydırma çubukları gerektiğinde.  
  
```  
CPoint GetScrollPosition() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yatay ve dikey konumları (mantıksal birimleri) kaydırma kutuların bir `CPoint` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu koordinat çifti için görünümünün sol üst köşesinde kaydırılan belge konumda karşılık gelir.  
  
 `GetScrollPosition` değerleri mantıksal birimler cinsinden döndürür. Cihaz birimleri istiyorsanız kullanın `GetDeviceScrollPosition` yerine.  
  
##  <a name="gettotalsize"></a>  CScrollView::GetTotalSize  
 Çağrı `GetTotalSize` kaydırma görünümü geçerli yatay ve dikey boyutlarını alınamadı.  
  
```  
CSize GetTotalSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Mantıksal birimler kaydırma görünümünde toplam boyutu. Yatay olarak boyutudur **cx** üyesi `CSize` dönüş değeri. Dikey boyutu olarak **cy** üyesi.  
  
##  <a name="resizeparenttofit"></a>  CScrollView::ResizeParentToFit  
 Çağrı `ResizeParentToFit` çerçeve penceresi boyutunu dikte görünümünüzü boyutunu izin vermek için.  
  
```  
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bShrinkOnly*  
 Gerçekleştirmek için yeniden boyutlandırma türü. Varsayılan değer **doğru**, çerçeve penceresi uygunsa küçültür. Kaydırma çubukları hala büyük görünümleri veya küçük çerçeve pencereleri için görünür. Değerini **FALSE** her zaman çerçeve penceresi tam olarak yeniden boyutlandırmak görünüm neden olur. Çerçeve penceresi birden çok belge arabirimi (MDI) çerçeve penceresi veya ekran içinde sığmayacak kadar büyük aldığından bu biraz tehlikeli olabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu, yalnızca MDI alt çerçeve pencereleri görünümlerde için önerilir. Kullanım `ResizeParentToFit` içinde `OnInitialUpdate` türetilmiş işleyici işlevinin `CScrollView` sınıfı. Bu üye işlevi bir örnek için bkz: [CScrollView::SetScrollSizes](#setscrollsizes).  
  
 `ResizeParentToFit` Görünüm penceresi boyutu ayarlamış olduğunu varsayar. Görünüm penceresi boyutu ne zaman ayarlanmamış ise `ResizeParentToFit` olan adlı bir onaylama alırsınız. Bu gerçekleşmez emin olmak için aşağıdaki çağırmadan önce çağırmaya `ResizeParentToFit`:  
  
 [!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]  
  
##  <a name="scrolltoposition"></a>  CScrollView::ScrollToPosition  
 Çağrı `ScrollToPosition` görünümünde verilen bir noktaya gidin.  
  
```  
void ScrollToPosition(POINT pt);
```  
  
### <a name="parameters"></a>Parametreler  
 `pt`  
 İçin mantıksal birimler cinsinden kaydırma noktası. **x** üye pozitif bir değer (büyük veya eşit görünümü toplam boyutu en fazla 0) olması gerekir. Aynı için doğrudur **y** eşleme modu olduğunda üye `MM_TEXT`. **y** üyesidir modları dışında eşlemede negatif `MM_TEXT`.  
  
### <a name="remarks"></a>Açıklamalar  
 Böylece bu noktası pencerenin sol üst köşesinde görünümü kaydırılan. Bu üye işlevi çağrılmalıdır görünümü uyacak şekilde ölçeklendirilir durumunda değil.  
  
##  <a name="setscaletofitsize"></a>  CScrollView::SetScaleToFitSize  
 Çağrı `SetScaleToFitSize` geçerli pencere boyutu Görünüm penceresi boyutu otomatik olarak ölçeklendirme istediğinizde.  
  
```  
void SetScaleToFitSize(SIZE sizeTotal);
```  
  
### <a name="parameters"></a>Parametreler  
 `sizeTotal`  
 Görünüm ölçeklendirilmesi olduğu yatay ve dikey boyutları. Kaydırma görünümün boyutu mantıksal birimler cinsinden ölçülür. Yatay boyutu içinde yer alan **cx** üyesi. Dikey boyutu içinde yer alan **cy** üyesi. Her ikisi de **cx** ve **cy** değerinden büyük veya 0 değerine eşit olmalıdır.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaydırma çubukları ile yalnızca bir kısmını mantıksal görünümü herhangi bir zamanda görünür olmayabilir. Ancak ölçek sığacak şekilde özelliğine sahip hiçbir kaydırma çubukları görünüme sahiptir ve mantıksal görünümü uzatılabilir ya da pencerenin istemci alanını tam olarak sığması için küçültülebilir. Pencereyi yeniden boyutlandırıldığında, görünümü verilerini pencere boyutuna göre yeni bir ölçekte çizer.  
  
 Genellikle çağrısı ekleyeceğiniz `SetScaleToFitSize` görünümün, geçersiz kılma içinde `OnInitialUpdate` üye işlevi. Otomatik ölçeklendirme istemiyorsanız çağrı `SetScrollSizes` üye işlev yerine.  
  
 `SetScaleToFitSize` "Yakınlaştırma Sığdır" işlemi uygulamak için kullanılabilir. Kullanım `SetScrollSizes` kaydırma yeniden başlatmak için.  
  
 `SetScaleToFitSize` Görünüm penceresi boyutu ayarlamış olduğunu varsayar. Görünüm penceresi boyutu ne zaman ayarlanmamış ise `SetScaleToFitSize` olan adlı bir onaylama alırsınız. Bu gerçekleşmez emin olmak için aşağıdaki çağırmadan önce çağırmaya `SetScaleToFitSize`:  
  
 [!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]  
  
##  <a name="setscrollsizes"></a>  CScrollView::SetScrollSizes  
 Çağrı `SetScrollSizes` görünümü olduğunda hakkında güncelleştirilecek.  
  
```  
void SetScrollSizes(
    int nMapMode,  
    SIZE sizeTotal,  
    const SIZE& sizePage = sizeDefault,  
    const SIZE& sizeLine = sizeDefault);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMapMode`  
 Bu görünüm için ayarlamak için eşleme modu. Olası değerler şunlardır:  
  
|Eşleme modu|Mantıksal birim|Pozitif y ekseni Extends...|  
|------------------|------------------|---------------------------------|  
|`MM_TEXT`|1 piksel|Aşağı|  
|`MM_HIMETRIC`|0,01 mm|Yukarı|  
|`MM_TWIPS`|1/1440|Yukarı|  
|`MM_HIENGLISH`|0,001 inç|Yukarı|  
|`MM_LOMETRIC`|0,1 mm|Yukarı|  
|`MM_LOENGLISH`|0,01 inç|Yukarı|  
  
 Tüm bu modlarını Windows tarafından tanımlanır. İki standart eşleme modunu `MM_ISOTROPIC` ve `MM_ANISOTROPIC`, için kullanılmaz `CScrollView`. Sınıf kitaplığı sağlar `SetScaleToFitSize` pencere boyutu görünümüne ölçekleme için üye işlevi. Yukarıdaki tablodaki sütun üç koordinat yönlendirmeyi açıklar.  
  
 `sizeTotal`  
 Kaydırma görünüm toplam boyutu. **Cx** üye yatay ölçüde içerir. **Cy** üyeyi içeren Dikey uzantı. Mantıksal birimleri boyutlarıdır. Her ikisi de **cx** ve **cy** değerinden büyük veya 0 değerine eşit olmalıdır.  
  
 `sizePage`  
 Her yönde yanıt olarak Fare kaydırma yatay ve dikey tutarlarının bir kaydırma çubuğunun mil'ı tıklatın. **Cx** üyeyi içeren yatay tutar. **Cy** üyeyi içeren dikey tutar.  
  
 `sizeLine`  
 Her yönde yanıt olarak Fare kaydırma yatay ve dikey tutarlarının bir kaydırma oku tıklatın. **Cx** üyeyi içeren yatay tutar. **Cy** üyeyi içeren dikey tutar.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçersiz kılmada çağrı `OnUpdate` Örneğin, belge görüntülendiğinde, veya boyutu değiştiğinde kaydırma özelliklerini ayarlamak için üye işlevi.  
  
 Belki de adlı bir belge üye işlevini çağırarak boyutu bilgileri görünümün ilişkili belgeden genellikle alacak `GetMyDocSize`, türetilen belge sınıfıyla sağladığınız. Aşağıdaki kod bu yaklaşım gösterir:  
  
 [!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]  
  
 Alternatif olarak, aşağıdaki kod olduğu gibi sabit bir boyuta ayarlamak bazen gerekebilir:  
  
 [!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]  
  
 Herhangi bir Windows eşleme modu dışında eşleme modu ayarlamalısınız `MM_ISOTROPIC` veya `MM_ANISOTROPIC`. Kısıtlanmamış eşleme modu kullanmak istiyorsanız, çağrı `SetScaleToFitSize` üye işlevi yerine `SetScrollSizes`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek DIBLOOK](../../visual-cpp-samples.md)   
 [CView sınıfı](../../mfc/reference/cview-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CView sınıfı](../../mfc/reference/cview-class.md)   
 [CSplitterWnd Sınıfı](../../mfc/reference/csplitterwnd-class.md)
