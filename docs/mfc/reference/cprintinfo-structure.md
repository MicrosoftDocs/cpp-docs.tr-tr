---
title: Cprintınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPrintInfo
dev_langs:
- C++
helpviewer_keywords:
- CPrintInfo structure [MFC]
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e1da952e14158ab92d888a703aa8451c0ca39406
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cprintinfo-structure"></a>Cprintınfo yapısı
Yazdırma veya Baskı Önizleme işle ilgili bilgileri depolar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CPrintInfo  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPrintInfo::GetFromPage](#getfrompage)|Yazdırılmasını ilk sayfa sayısını döndürür.|  
|[CPrintInfo::GetMaxPage](#getmaxpage)|Belgenin son sayfa sayısını döndürür.|  
|[CPrintInfo::GetMinPage](#getminpage)|Belgenin ilk sayfa sayısını döndürür.|  
|[CPrintInfo::GetOffsetPage](#getoffsetpage)|Birleşik DocObject yazdırma işi yazdırılmasını DocObject öğesinin ilk sayfa önceki sayfa sayısını döndürür.|  
|[CPrintInfo::GetToPage](#gettopage)|Yazdırılmasını son sayfa sayısını döndürür.|  
|[CPrintInfo::SetMaxPage](#setmaxpage)|Belgenin son sayfa sayısını ayarlar.|  
|[CPrintInfo::SetMinPage](#setminpage)|Belgenin ilk sayfa sayısını ayarlar.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPrintInfo::m_bContinuePrinting](#m_bcontinueprinting)|Çerçeve yazdırma döngü devam olup olmadığını belirten bir bayrak içeriyor.|  
|[CPrintInfo::m_bDirect](#m_bdirect)|Doğrudan (Yazdır iletişim kutusu görüntülenmeden) belgenin yazdırılmasını olmadığını belirten bir bayrak içeriyor.|  
|[CPrintInfo::m_bDocObject](#m_bdocobject)|Belgenin yazdırılmasını DocObject olup olmadığını belirten bir bayrak içeriyor.|  
|[CPrintInfo::m_bPreview](#m_bpreview)|Belge önizlemesi olup olmadığını belirten bir bayrak içeriyor.|  
|[CPrintInfo::m_dwFlags](#m_dwflags)|DocObject yazdırma işlemleri belirtir.|  
|[CPrintInfo::m_lpUserData](#m_lpuserdata)|Bir kullanıcı tarafından oluşturulan yapısı için bir işaretçi içeriyor.|  
|[CPrintInfo::m_nCurPage](#m_ncurpage)|Şu anda yazdırılmasını sayfa sayısını tanımlar.|  
|[CPrintInfo::m_nJobNumber](#m_njobnumber)|Geçerli yazdırma işi için işletim sistemi tarafından atanan iş sayısını belirtir|  
|[CPrintInfo::m_nNumPreviewPages](#m_nnumpreviewpages)|Önizleme penceresinde görüntülenen sayfaların sayısını tanımlar; 1 veya 2.|  
|[CPrintInfo::m_nOffsetPage](#m_noffsetpage)|Birleşik DocObject yazdırma işi belirli DocObject'ın ilk sayfasında uzaklığını belirtir.|  
|[CPrintInfo::m_pPD](#m_ppd)|Bir işaretçi içeriyor `CPrintDialog` Yazdır iletişim kutusu için kullanılan nesne.|  
|[CPrintInfo::m_rectDraw](#m_rectdraw)|Geçerli kullanılabilir sayfa alanına tanımlama dikdörtgen belirtir.|  
|[CPrintInfo::m_strPageDesc](#m_strpagedesc)|Sayfa numarasını görüntülemek için bir biçim dizesi içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CPrintInfo` bir yapıdır ve bir taban sınıfı yok.  
  
 Bir nesnenin çerçevesini oluşturur `CPrintInfo` her zaman yazdır veya Baskı Önizleme komutu seçilir ve komutu tamamlandığında yok eder.  
  
 `CPrintInfo` yazdırma işi yazdırılmak üzere sayfa aralığını gibi bir bütün olarak ve yazdırma işi şu anda yazdırılmasını sayfa gibi geçerli durumu hakkında bilgi içerir. Bazı bilgiler saklanır, ilişkili bir [CPrintDialog](../../mfc/reference/cprintdialog-class.md) nesne; bu nesne Yazdır iletişim kutusunda kullanıcı tarafından girilen değerleri içerir.  
  
 A `CPrintInfo` nesnesi framework ve görünüm sınıfı arasında yazdırma işlemi sırasında geçirilir ve ikisi arasında bilgi alışverişi için kullanılır. Örneğin, çerçeve görünüm sınıfı için bir değer atayarak yazdırmak için belgenin hangi sayfası sizi bilgilendirir `m_nCurPage` üyesi `CPrintInfo`; görünümü sınıfı değeri alır ve belirtilen sayfasının gerçek yazdırma gerçekleştirir.  
  
 Başka bir örnek yazdırılan kadar belgenin uzunluğunu bilinmiyor durumdur. Bu durumda, görünüm sınıfı belgenin sonuna için her bir sayfa yazdırıldığında sınar. View sınıfı sonuna gelindiğinde, ayarlar `m_bContinuePrinting` üyesi `CPrintInfo` için **yanlış**; bu yazdırma döngü durdurmak için framework bildirir.  
  
 `CPrintInfo` üye işlevlerini tarafından kullanılan `CView` listelenen altında "Ayrıca bkz." Microsoft Foundation Class Kitaplığı tarafından sağlanan yazdırma mimarisi hakkında daha fazla bilgi için bkz: [çerçeve pencereleri](../../mfc/frame-windows.md) ve [belge/görünüm mimarisinin](../../mfc/document-view-architecture.md) ve makaleleri [ Yazdırma](../../mfc/printing.md) ve [yazdırma: birden çok belge](../../mfc/multipage-documents.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CPrintInfo`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxext.h  
  
##  <a name="getfrompage"></a>  CPrintInfo::GetFromPage  
 Yazdırılacak ilk sayfa sayısını almak için bu işlevini çağırın.  
  
```  
UINT GetFromPage() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazdırılacak ilk sayfa sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Yazdır iletişim kutusunda kullanıcı tarafından belirtilen değer budur ve depolanır `CPrintDialog` tarafından başvurulan nesne `m_pPD` üyesi. Kullanıcı bir değere belirtilmezse, varsayılan belgenin ilk sayfadır.  
  
##  <a name="getmaxpage"></a>  CPrintInfo::GetMaxPage  
 Belgenin son sayfa sayısını almak için bu işlevini çağırın.  
  
```  
UINT GetMaxPage() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belgenin son sayfa numarası.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer depolanan `CPrintDialog` tarafından başvurulan nesne `m_pPD` üyesi.  
  
##  <a name="getminpage"></a>  CPrintInfo::GetMinPage  
 Belgenin ilk sayfa sayısını almak için bu işlevini çağırın.  
  
```  
UINT GetMinPage() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belgenin ilk sayfa sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer depolanan `CPrintDialog` tarafından başvurulan nesne `m_pPD` üyesi.  
  
##  <a name="getoffsetpage"></a>  CPrintInfo::GetOffsetPage  
 Birden çok DocObject öğe DocObject istemciden yazdırılırken uzaklık almak için bu işlevini çağırın.  
  
```  
UINT GetOffsetPage() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik DocObject yazdırma işi yazdırılmasını DocObject öğesinin ilk sayfa önceki sayfa sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer tarafından başvuruluyor **m_nOffsetPage** üyesi. Belgenizi'nın ilk sayfasında numaralı **m_nOffsetPage** değeri + diğer etkin belgelerle DocObject olarak yazdırıldığında 1. **M_nOffsetPage** üye geçerli yalnızca **m_bDocObject** değer **doğru**.  
  
##  <a name="gettopage"></a>  CPrintInfo::GetToPage  
 Yazdırılacak son sayfayı sayısını almak üzere bu işlevini çağırın.  
  
```  
UINT GetToPage() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazdırılacak son sayfa numarası.  
  
### <a name="remarks"></a>Açıklamalar  
 Yazdır iletişim kutusunda kullanıcı tarafından belirtilen değer budur ve depolanır `CPrintDialog` tarafından başvurulan nesne `m_pPD` üyesi. Kullanıcı bir değere belirtilmezse, varsayılan belgenin son sayfadır.  
  
##  <a name="m_bcontinueprinting"></a>  CPrintInfo::m_bContinuePrinting  
 Çerçeve yazdırma döngü devam olup olmadığını belirten bir bayrak içeriyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Yazdırma zamanı sayfalandırma yapıyorsanız, bu üye ayarlayabileceğiniz **FALSE** geçersiz kılma içinde `CView::OnPrepareDC` sonra belgenin sonuna ulaşıldı. Yazdırma işi kullanmanın başında belgenin uzunluğunu belirttiyseniz, bu değişken değiştirmek zorunda değilsiniz `SetMaxPage` üye işlevi. `m_bContinuePrinting` Üye olan bir ortak değişken türü **BOOL**.  
  
##  <a name="m_bdirect"></a>  CPrintInfo::m_bDirect  
 Bu üye framework ayarlar **TRUE** Yazdır iletişim kutusu doğrudan yazdırma için; atlanır varsa **FALSE** Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Yazdır iletişim Kabuğu'ndan veya yazdırma yapıldığında yazdırırken normalde atlanır komut Kimliğini kullanarak **ID_FILE_PRINT_DIRECT**.  
  
 Normalde bu üye değişmez ancak, değiştirirseniz, onu önce değişiklik [CView::DoPreparePrinting](../../mfc/reference/cview-class.md#doprepareprinting) geçersiz kılma içinde [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).  
  
##  <a name="m_bdocobject"></a>  CPrintInfo::m_bDocObject  
 Belgenin yazdırılmasını DocObject olup olmadığını belirten bir bayrak içeriyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri üyeleri `m_dwFlags` ve **m_nOffsetPage** Bu bayrak olmadıkça geçersizdir **doğru**.  
  
##  <a name="m_bpreview"></a>  CPrintInfo::m_bPreview  
 Belge önizlemesi olup olmadığını belirten bir bayrak içeriyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu komutu kullanıcının hangi yürütülebilir çerçevesi tarafından ayarlanır. Yazdır iletişim kutusu için bir baskı önizleme işi görüntülenmez. **M_bPreview** üye olan bir ortak değişken türü **BOOL**.  
  
##  <a name="m_dwflags"></a>  CPrintInfo::m_dwFlags  
 Bayrak DocObject yazdırma işlemleri belirterek birleşimi içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli eksikse veri üyesi **m_bDocObject** olan **doğru**.  
  
 Bayrakları bir veya daha fazla aşağıdaki değerlerden biri olabilir:  
  
- **PRINTFLAG_MAYBOTHERUSER**  
  
- **PRINTFLAG_PROMPTUSER**  
  
- **PRINTFLAG_USERMAYCHANGEPRINTER**  
  
- **PRINTFLAG_RECOMPOSETODEVICE**  
  
- **PRINTFLAG_DONTACTUALLYPRINT**  
  
- **PRINTFLAG_FORCEPROPERTIES**  
  
- **PRINTFLAG_PRINTTOFILE**  
  
##  <a name="m_lpuserdata"></a>  CPrintInfo::m_lpUserData  
 Bir kullanıcı tarafından oluşturulan yapısı için bir işaretçi içeriyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu görünüm sınıfınızda depolamak istemediğiniz yazdırma özgü verileri depolamak için kullanabilirsiniz. **M_lpUserData** üye olan bir ortak değişken türü **LPVOID**.  
  
##  <a name="m_ncurpage"></a>  CPrintInfo::m_nCurPage  
 Geçerli sayfa numarasını içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework çağrıları `CView::OnPrepareDC` ve `CView::OnPrint` her zaman; bu üye için farklı bir değer belirterek belgenin her bir sayfa için kendi değerler kez aralığında tarafından döndürülen değerin `GetFromPage` tarafından döndürülen için `GetToPage`. Bu üye kılmalarınızın içinde kullanmak `CView::OnPrepareDC` ve `CView::OnPrint` belgenin belirtilen sayfa yazdırmak için.  
  
 Önizleme modunda ilk kez çağrıldığında framework belgenin hangi sayfasını başlangıçta önizlemesi belirlemek için bu üyenin değerini okur. Bu üye değeri geçersiz kılmada ayarlayabilirsiniz `CView::OnPreparePrinting` önizleme modunda girerken kullanıcının geçerli konumunu belgedeki korumak için. `m_nCurPage` Üye olan bir ortak değişken türü **UINT**.  
  
##  <a name="m_njobnumber"></a>  CPrintInfo::m_nJobNumber  
 Geçerli yazdırma işi için işletim sistemi tarafından atanan iş sayısını gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer olabilir **SP_ERROR** işi henüz çıkarırsa kurmadı (varsa, diğer bir deyişle, `CPrintInfo` nesnesi yeni oluşturulan ve henüz yazdırmak için kullanılmamış), veya varsa bir hata işi başlatılıyor.  
  
##  <a name="m_nnumpreviewpages"></a>  CPrintInfo::m_nNumPreviewPages  
 Önizleme modunda görüntülenen sayfaların sayısını içerir; 1 veya 2 olabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 **M_nNumPreviewPages** üye olan bir ortak değişken türü **UINT**.  
  
##  <a name="m_noffsetpage"></a>  CPrintInfo::m_nOffsetPage  
 Belirli bir DocObject'ın ilk sayfasında birleşik DocObject yazdırma işi önceki sayfa sayısını içerir.  
  
##  <a name="m_ppd"></a>  CPrintInfo::m_pPD  
 Bir işaretçi içeriyor `CPrintDialog` yazdırma işinin yazdırma iletişim kutusunu görüntülemek için kullanılan nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 `m_pPD` Üye olan bir işaretçi olarak bildirilen bir ortak değişken `CPrintDialog`.  
  
##  <a name="m_rectdraw"></a>  CPrintInfo::m_rectDraw  
 Sayfanın kullanılabilir çizim alanının mantıksal koordinatlarında belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu geçersiz kılmada başvurmak isteyebilirsiniz `CView::OnPrint`. Bu üye, üstbilgiler, altbilgiler ve benzeri yazdırdıktan sonra hangi alan kullanılabilir olmaya devam izlemek için kullanabilirsiniz. **M_rectDraw** üye olan bir ortak değişken türü `CRect`.  
  
##  <a name="m_strpagedesc"></a>  CPrintInfo::m_strPageDesc  
 Baskı Önizleme sırasında sayfa numaralarını görüntülemek için kullanılan biçim dizesi içerir; Bu dize iki alt dizeler, tek tek sayfa görüntülenmesi için ve biri her bir '\n' karakteriyle sonlandırıldı çift sayfa görüntüleme için oluşur.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve "Sayfa %u\nPages % u-%u\n" varsayılan değer olarak kullanır. Sayfa numaraları için farklı bir biçim istiyorsanız, bir biçim dizesine geçersiz kılmada belirtin `CView::OnPreparePrinting`. **M_strPageDesc** üye olan bir ortak değişken türü `CString`.  
  
##  <a name="setmaxpage"></a>  CPrintInfo::SetMaxPage  
 Belgenin son sayfa sayısını belirtmek için bu işlevini çağırın.  
  
```  
void SetMaxPage(UINT nMaxPage);
```  
  
### <a name="parameters"></a>Parametreler  
 *nMaxPage*  
 Belgenin son sayfa sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer depolanan `CPrintDialog` tarafından başvurulan nesne `m_pPD` üyesi. Yazdırılan önce belgenin uzunluğunu biliniyorsa, bu işlev geçersiz kılma çağrı `CView::OnPreparePrinting`. Yazdır iletişim kutusunda kullanıcı tarafından belirtilen bir ayar belgenin uzunluğunu bağlıdır bu işlev geçersiz kılma çağırır `CView::OnBeginPrinting`. Yazdırılan kadar belgenin uzunluğunu bilinmiyor kullanırsanız `m_bContinuePrinting` yazdırma döngü denetlemek için üye.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).  
  
##  <a name="setminpage"></a>  CPrintInfo::SetMinPage  
 Belgenin ilk sayfa sayısını belirtmek için bu işlevini çağırın.  
  
```  
void SetMinPage(UINT nMinPage);
```  
  
### <a name="parameters"></a>Parametreler  
 *nMinPage*  
 Belgenin ilk sayfa sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Sayfa numarası normal olarak 1'den başlar. Bu değer depolanan `CPrintDialog` tarafından başvurulan nesne `m_pPD` üyesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek DIBLOOK](../../visual-cpp-samples.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)   
 [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)   
 [CView::OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)   
 [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)   
 [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)   
 [CView::OnPrint](../../mfc/reference/cview-class.md#onprint)



