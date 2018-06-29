---
title: CRectTracker sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRectTracker
- AFXEXT/CRectTracker
- AFXEXT/CRectTracker::CRectTracker
- AFXEXT/CRectTracker::AdjustRect
- AFXEXT/CRectTracker::Draw
- AFXEXT/CRectTracker::DrawTrackerRect
- AFXEXT/CRectTracker::GetHandleMask
- AFXEXT/CRectTracker::GetTrueRect
- AFXEXT/CRectTracker::HitTest
- AFXEXT/CRectTracker::NormalizeHit
- AFXEXT/CRectTracker::OnChangedRect
- AFXEXT/CRectTracker::SetCursor
- AFXEXT/CRectTracker::Track
- AFXEXT/CRectTracker::TrackRubberBand
- AFXEXT/CRectTracker::m_nHandleSize
- AFXEXT/CRectTracker::m_nStyle
- AFXEXT/CRectTracker::m_rect
- AFXEXT/CRectTracker::m_sizeMin
dev_langs:
- C++
helpviewer_keywords:
- CRectTracker [MFC], CRectTracker
- CRectTracker [MFC], AdjustRect
- CRectTracker [MFC], Draw
- CRectTracker [MFC], DrawTrackerRect
- CRectTracker [MFC], GetHandleMask
- CRectTracker [MFC], GetTrueRect
- CRectTracker [MFC], HitTest
- CRectTracker [MFC], NormalizeHit
- CRectTracker [MFC], OnChangedRect
- CRectTracker [MFC], SetCursor
- CRectTracker [MFC], Track
- CRectTracker [MFC], TrackRubberBand
- CRectTracker [MFC], m_nHandleSize
- CRectTracker [MFC], m_nStyle
- CRectTracker [MFC], m_rect
- CRectTracker [MFC], m_sizeMin
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c4ce3c4dbfbf49791673392a1e1234728a680611
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079674"
---
# <a name="crecttracker-class"></a>CRectTracker sınıfı
Bir öğenin görüntülenen taşınır ve farklı fashions yeniden boyutlandırılıp sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CRectTracker  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRectTracker::CRectTracker](#crecttracker)|Oluşturan bir `CRectTracker` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRectTracker::AdjustRect](#adjustrect)|Dikdörtgen yeniden boyutlandırıldığında çağrılır.|  
|[CRectTracker::Draw](#draw)|Dikdörtgen işler.|  
|[CRectTracker::DrawTrackerRect](#drawtrackerrect)|Kenarlığı çizerken adlı bir `CRectTracker` nesnesi.|  
|[CRectTracker::GetHandleMask](#gethandlemask)|Maskesini almak için çağrılan bir `CRectTracker` öğesi'nin tanıtıcıları yeniden boyutlandırın.|  
|[CRectTracker::GetTrueRect](#gettruerect)|Genişlik ve yükseklik boyutlandırma dahil olmak üzere dikdörtgenin döndürür.|  
|[CRectTracker::HitTest](#hittest)|İlişkili imleci geçerli konumunu döndürür `CRectTracker` nesnesi.|  
|[CRectTracker::NormalizeHit](#normalizehit)|İsabet testi kodu normalleştirir.|  
|[CRectTracker::OnChangedRect](#onchangedrect)|Dikdörtgen yeniden boyutlandırılmış veya çağrılır.|  
|[CRectTracker::SetCursor](#setcursor)|İmleç konumuna dikdörtgen üzerinden bağlı olarak ayarlar.|  
|[CRectTracker::Track](#track)|Dikdörtgen yönetmenize olanak tanır.|  
|[CRectTracker::TrackRubberBand](#trackrubberband)|"Bant dışı pencere" kullanıcıya seçilmesine izin verir.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRectTracker::m_nHandleSize](#m_nhandlesize)|Yeniden boyutlandırma boyutunu belirler.|  
|[CRectTracker::m_nStyle](#m_nstyle)|İzleyici'nin geçerli style(s).|  
|[CRectTracker::m_rect](#m_rect)|Dikdörtgen geçerli konumu (piksel cinsinden).|  
|[CRectTracker::m_sizeMin](#m_sizemin)|Minimum dikdörtgen genişlik ve yükseklik belirler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CRectTracker` bir taban sınıfı yok.  
  
 Ancak `CRectTracker` sınıfı bir grafik arabirimi kullanarak OLE öğeleri ile etkileşim kurmasına izin vermek için tasarlanmış, kullanımı OLE özellikli uygulamalar için sınırlı değildir. Kullanılabilir herhangi bir yeri gibi bir kullanıcı arabirimi gereklidir.  
  
 `CRectTracker` Kenarlıklar düz olabilir veya noktalı çizgiler. Öğe taranmış kenarlık verilen veya öğenin farklı durumlarını belirtmek için taranmış bir desen ile yayılan. Dış veya iç sekiz boyutlandırma yerleştirebilirsiniz öğenin kenarlık. (Yeniden boyutlandırma hakkında açıklama için bkz: [GetHandleMask](#gethandlemask).) Son olarak, bir `CRectTracker` yeniden boyutlandırma sırasında bir öğe yönünü değiştirmenize izin verir.  
  
 Kullanılacak `CRectTracker`, oluşturmak bir `CRectTracker` nesne ve hangi görüntü durumları başlatılmış belirtin. Ardından bu arabirimi kullanıcı visual ilişkili OLE öğesi geçerli durumu hakkında görüş için kullanabileceğiniz `CRectTracker` nesnesi.  
  
 Kullanma hakkında daha fazla bilgi için `CRectTracker`, makaleye bakın [izleyicileri](../../mfc/trackers.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CRectTracker`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxext.h  
  
##  <a name="adjustrect"></a>  CRectTracker::AdjustRect  
 İzleme dikdörtgen bir yeniden boyutlandırma tutamacını kullanarak yeniden boyutlandırıldığında çerçevesi tarafından çağrılır.  
  
```  
virtual void AdjustRect(
    int nHandle,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Parametreler  
 *nHandle*  
 Kullanılan işleyici dizini.  
  
 *lpRect*  
 Dikdörtgen boyutunu işaretçi. (Bir dikdörtgen boyutunun yüksekliğini ve genişliğini tarafından verilir.)  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan davranışını yalnızca değiştirmek dikdörtgenin yönlendirmesini sağlar `Track` ve `TrackRubberBand` izin ters çevirme ile denir.  
  
 İzleme dikdörtgen ayarlama sürükleme işlemi sırasında denetlemek için bu işlevi geçersiz kılar. Bir yöntemdir tarafından belirtilen koordinatları ayarlamak için *lpRect* dönmeden önce.  
  
 Tarafından doğrudan desteklenmeyen özelliklere `CRectTracker`, bu işlev geçersiz kılarak gibi ek kılavuz veya canlı-boyut oranı, uygulanabilir.  
  
##  <a name="crecttracker"></a>  CRectTracker::CRectTracker  
 Oluşturur ve başlatır bir `CRectTracker` nesnesi.  
  
```  
CRectTracker();

 
CRectTracker(
    LPCRECT lpSrcRect,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpSrcRect*  
 Dikdörtgen nesnenin koordinatları.  
  
 *nStyle*  
 Stilini belirtir `CRectTracker` nesnesi. Aşağıdaki stiller desteklenir:  
  
- **CRectTracker::solidLine** Kesiksiz bir çizgi Dikdörtgen kenarlık için kullanın.  
  
- **CRectTracker::dottedLine** noktalı çizgi Dikdörtgen kenarlık için kullanın.  
  
- **CRectTracker::hatchedBorder** taranmış bir desen Dikdörtgen kenarlık için kullanın.  
  
- **CRectTracker::resizeInside** dikdörtgende bulunan tanıtıcıları yeniden boyutlandırın.  
  
- **CRectTracker::resizeOutside** dikdörtgenin dışında bulunan tanıtıcıları yeniden boyutlandırın.  
  
- **CRectTracker::hatchInside** Hatched düzeni tüm dikdörtgen kapsar.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan Oluşturucu başlatır `CRectTracker` değerlerle nesne *lpSrcRect* ve diğer sistem varsayılanlarını boyutlarına başlatır. Nesne hiçbir parametrelerle oluşturduysanız `m_rect` ve `m_nStyle` veri üyeleri başlatılmamış.  
  
##  <a name="draw"></a>  CRectTracker::Draw  
 Dikdörtgenin dış çizgiler ve iç bölge çizmek için bu işlevini çağırın.  
  
```  
void Draw(CDC* pDC) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *pDC*  
 Üretileceği çizmek cihaz bağlamı işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Çizim yapma İzleyici stilini belirler. Oluşturucusu bkz `CRectTracker` kullanılabilir stilleri hakkında daha fazla bilgi için.  
  
##  <a name="drawtrackerrect"></a>  CRectTracker::DrawTrackerRect  
 İzleyici konumunu değişti zaman çerçevesi tarafından çağrılır while içinde `Track` veya `TrackRubberBand` üye işlevi.  
  
```  
virtual void DrawTrackerRect(
    LPCRECT lpRect,  
    CWnd* pWndClipTo,  
    CDC* pDC,  
    CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpRect*  
 İşaretçi `RECT` dikdörtgen çizmek için içerir.  
  
 *pWndClipTo*  
 Dikdörtgen kırpma kullanmak için pencereyi işaretçi.  
  
 *pDC*  
 Üretileceği çizmek cihaz bağlamı işaretçi.  
  
 *pWnd*  
 İşaretçi penceresine çizim meydana gelir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama için bir çağrı yapar `CDC::DrawFocusRect`, noktalı dikdörtgeni çizer.  
  
 İzleme işlemi sırasında farklı geri bildirim sağlamak için bu işlevi geçersiz kılar.  
  
##  <a name="gethandlemask"></a>  CRectTracker::GetHandleMask  
 Framework dikdörtgen tanıtıcıları yeniden boyutlandırmak için maskesi almak için bu üye işlevi çağırır.  
  
```  
virtual UINT GetHandleMask() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Maskesini bir `CRectTracker` öğesi'nin tanıtıcıları yeniden boyutlandırın.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden boyutlandırma yanları ve dikdörtgen köşelerinde görünür ve dikdörtgen boyutu ve şekli denetlemenize izin verin.  
  
 Dikdörtgene 0-7 numaralı 8 boyutlandırma sahiptir. Her yeniden boyutlandırma tutamacı bir bit maskesi gösterilir; 2 Bu bit değeri ^ *n*, burada *n* yeniden boyutlandırma tanıtıcısı sayısıdır. BITS 0-3 saat yönünde taşıma sol üstten başlayarak köşe boyutlandırma işleyicilerine karşılık gelir. BITS 4-7 kenara saat yönünde taşıma üstten başlayarak tanıtıcıları yeniden boyutlandırın. Aşağıdaki çizimde bir dikdörtgenin boyutlandırma işler ve karşılık gelen resize tanıtıcı numaraları ve değerleri gösterir:  
  
 ![Yeniden boyutlandırma tutamacı numaraları](../../mfc/reference/media/vc35dp1.gif "vc35dp1")  
  
 Varsayılan uygulaması **GetHandleMask** yeniden boyutlandırma görünmesini sağlayacak şekilde bit maskesi döndürür. Tek bit açıksa, karşılık gelen yeniden boyutlandırma tutamacı çizilir.  
  
 Belirtilen tanıtıcıları yeniden boyutlandırma göstermek veya gizlemek için bu üye işlevi geçersiz kılar.  
  
##  <a name="gettruerect"></a>  CRectTracker::GetTrueRect  
 Dikdörtgen koordinatlarını almak için bu işlevini çağırın.  
  
```  
void GetTrueRect(LPRECT lpTrueRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *lpTrueRect*  
 İşaretçi `RECT` cihaz içerecek yapısı koordinatları `CRectTracker` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Dikdörtgen boyutlarını dış kenarlık üzerinde bulunan tüm boyutlandırma genişliği ve yüksekliği içerir. Döndürme, bağlı *lpTrueRect* her zaman normalleştirilmiş dikdörtgene aygıt koordinatları olur.  
  
##  <a name="hittest"></a>  CRectTracker::HitTest  
 Olup kullanıcı yeniden boyutlandırma tutamacı gerçekleşti çıkışı bulmak için bu işlevini çağırın.  
  
```  
int HitTest(CPoint point) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *Noktası*  
 Test etmek için cihaz koordinatları noktası.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürülen değer numaralandırılmış türüne dayalıdır **CRectTracker::TrackerHit** ve şu değerlerden biri olabilir:  
  
- **CRectTracker::hitNothing** -1  
  
- **CRectTracker::hitTopLeft** 0  
  
- **CRectTracker::hitTopRight** 1  
  
- **CRectTracker::hitBottomRight** 2  
  
- **CRectTracker::hitBottomLeft** 3  
  
- **CRectTracker::hitTop** 4  
  
- **CRectTracker::hitRight** 5  
  
- **CRectTracker::hitBottom** 6  
  
- **CRectTracker::hitLeft** 7  
  
- **CRectTracker::hitMiddle** 8  
  
##  <a name="m_nhandlesize"></a>  CRectTracker::m_nHandleSize  
 Piksel cinsinden boyutu, `CRectTracker` tanıtıcıları yeniden boyutlandırın.  
  
```  
int m_nHandleSize;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan sistem değerle başlatıldı.  
  
##  <a name="m_rect"></a>  CRectTracker::m_rect  
 Geçerli konumu dikdörtgen istemci koordinatları (piksel cinsinden).  
  
```  
CRect m_rect;  
```  
  
##  <a name="m_sizemin"></a>  CRectTracker::m_sizeMin  
 Dikdörtgen minimum boyutu.  
  
```  
CSize m_sizeMin;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Her iki varsayılan değerleri **cx** ve **cy**, kenarlık genişliği için varsayılan sistem değerinden hesaplanır. Bu veri üyesi yalnızca kullanılan `AdjustRect` üye işlevi.  
  
##  <a name="m_nstyle"></a>  CRectTracker::m_nStyle  
 Dikdörtgen geçerli stili.  
  
```  
UINT m_nStyle;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [CRectTracker::CRectTracker](#crecttracker) olası stilleri listesi.  
  
##  <a name="normalizehit"></a>  CRectTracker::NormalizeHit  
 Potansiyel olarak ters tanıtıcı dönüştürmek için bu işlevini çağırın.  
  
```  
int NormalizeHit(int nHandle) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nHandle*  
 Kullanıcı tarafından seçilen işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Normalleştirilmiş tanıtıcı dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `CRectTracker::Track` veya `CRectTracker::TrackRubberBand` denir izin ters çevirme ile dikdörtgenin x ekseni, y veya her ikisi de ters mümkündür. Bu gerçekleştiğinde, `HitTest` dikdörtgenin göre de ters tanıtıcıları döndürür. Dikdörtgen olmayan değiştirilecek dikdörtgen veri yapısı kısmı ekran konumuna geri bildirim bağımlı olduğundan bu çizim imleç geri bildirim için uygun değil.  
  
##  <a name="onchangedrect"></a>  CRectTracker::OnChangedRect  
 İzleyici dikdörtgen bir arama sırasında değişti zaman çerçevesi tarafından çağrılır `Track`.  
  
```  
virtual void OnChangedRect(const CRect& rectOld);
```  
  
### <a name="parameters"></a>Parametreler  
 *rectOld*  
 Eski aygıt koordinatlarını içerir `CRectTracker` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Aynı anda bu işlev, tüm geri bildirim ile çizilmiş çağrılır `DrawTrackerRect` kaldırılmıştır. Bu işlev varsayılan uygulaması hiçbir şey yapmaz.  
  
 Dikdörtgen yeniden boyutlandırılmış sonra herhangi bir eylem gerçekleştirmek istediğinizde bu işlevi geçersiz kılar.  
  
##  <a name="setcursor"></a>  CRectTracker::SetCursor  
 Üzerinden ederken imleç şeklini değiştirmek için bu işlevi çağırmak `CRectTracker` nesnenin bölgesi.  
  
```  
BOOL SetCursor(
    CWnd* pWnd,  
    UINT nHitTest) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 Şu anda imlecin bulunduğu pencereyi noktalarına.  
  
 *nHitTest*  
 WM_SETCURSOR iletiden önceki isabet testi sonuçları.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki İsabet üzerine İzleyicisi dikdörtgen ise sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevden pencerenizin WM_SETCURSOR iletiyi işleyen işlev içinde arama (genellikle `OnSetCursor`).  
  
##  <a name="track"></a>  CRectTracker::Track  
 Dikdörtgen yeniden boyutlandırma için kullanıcı arabirimi görüntülemek için bu işlevini çağırın.  
  
```  
BOOL Track(
    CWnd* pWnd,  
    CPoint point,  
    BOOL bAllowInvert = FALSE,  
    CWnd* pWndClipTo = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 Dikdörtgen içeren pencere nesnesi.  
  
 *Noktası*  
 İstemci alanını göre geçerli fare konumunun cihaz koordinatları.  
  
 *bAllowInvert*  
 Varsa **TRUE**, dikdörtgen x ekseni veya y ekseni boyunca ters; Aksi takdirde **FALSE**.  
  
 *pWndClipTo*  
 Operations çizim için kırpılacak penceresini açın. Varsa **NULL**, *pWnd* dikdörtgen kırpma kullanılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 ESC tuşuna basılana, izleme işlemi durdu, İzleyici'depolanan dikdörtgen değiştirilmediğini ve 0 değeri döndürülür. Değişiklik tamamlanırsa, fareyi hareket ettirmek ve sol fare düğmesini bırakmadan yeni konumu ve/veya boyutunu kaydedilir İzleyici'nin dikdörtgende ve sıfır olmayan döndürülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu genellikle işlediği uygulamanızı işlevi içinde çağrılır `WM_LBUTTONDOWN` ileti (genellikle `OnLButtonDown`).  
  
 Kullanıcı sol fare düğmesini serbest, ESC tuşuna bastığında veya farenin sağ düğmesiyle bastığında kadar bu işlev fare yakalar. Kullanıcı fare imlecini taşınırken, geri bildirim arayarak güncelleştirilir `DrawTrackerRect` ve `OnChangedRect`.  
  
 Varsa *bAllowInvert* olan **doğru**, izleme dikdörtgenin x ekseni veya y ekseni üzerinde ters.  
  
##  <a name="trackrubberband"></a>  CRectTracker::TrackRubberBand  
 Bant dışı pencere seçim yapmak için bu işlevini çağırın.  
  
```  
BOOL TrackRubberBand(
    CWnd* pWnd,  
    CPoint point,  
    BOOL bAllowInvert = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 Dikdörtgen içeren pencere nesnesi.  
  
 *Noktası*  
 İstemci alanını göre geçerli fare konumunun cihaz koordinatları.  
  
 *bAllowInvert*  
 Varsa **TRUE,** dikdörtgen x ekseni veya y ekseni boyunca ters; Aksi takdirde **FALSE**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Fare taşınmıştır ve dikdörtgen boş değilse, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu genellikle WM_LBUTTONDOWN iletiyi işleyen uygulamanızı işlevi içinde çağrılır (genellikle `OnLButtonDown`).  
  
 Kullanıcı sol fare düğmesini serbest, ESC tuşuna bastığında veya farenin sağ düğmesiyle bastığında kadar bu işlev fare yakalar. Kullanıcı fare imlecini taşınırken, geri bildirim arayarak güncelleştirilir `DrawTrackerRect` ve `OnChangedRect`.  
  
 İzleme sağ alt tanıtıcı pencere bant türü seçimden ile gerçekleştirilir. Ters çevirme izin veriliyorsa, dikdörtgen ya da yukarı ve sola veya aşağı ve sağa sürükleyerek boyutlandırılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek İZLEYİCİSİ](../../visual-cpp-samples.md)   
 [MFC örnek DRAWCLI](../../visual-cpp-samples.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleResizeBar sınıfı](../../mfc/reference/coleresizebar-class.md)   
 [CRect Sınıfı](../../atl-mfc-shared/reference/crect-class.md)
