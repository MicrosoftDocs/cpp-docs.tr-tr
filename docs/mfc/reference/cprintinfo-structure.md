---
title: CprintInfo Yapısı
ms.date: 11/04/2016
f1_keywords:
- CPrintInfo
helpviewer_keywords:
- CPrintInfo structure [MFC]
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
ms.openlocfilehash: 3b081b0728514c0fca2eb31462e1bcd9e91a47aa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753019"
---
# <a name="cprintinfo-structure"></a>CprintInfo Yapısı

Yazdırma veya yazdırma önizleme işi yle ilgili bilgileri depolar.

## <a name="syntax"></a>Sözdizimi

```
struct CPrintInfo
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPrintInfo::GetFromPage](#getfrompage)|Yazdırılan ilk sayfanın numarasını verir.|
|[CPrintInfo::GetMaxPage](#getmaxpage)|Belgenin son sayfasının numarasını verir.|
|[CPrintInfo::GetMinPage](#getminpage)|Belgenin ilk sayfasının numarasını verir.|
|[CPrintInfo::GetOffsetPage](#getoffsetpage)|Birleştirilmiş DocObject yazdırma işinde yazdırılan Bir DocObject öğesinin ilk sayfasından önceki sayfaların sayısını döndürür.|
|[CprintInfo::Gettopage](#gettopage)|Yazdırılan son sayfanın numarasını verir.|
|[CPrintInfo::SetMaxPage](#setmaxpage)|Belgenin son sayfasının numarasını ayarlar.|
|[CPrintInfo::SetMinPage](#setminpage)|Belgenin ilk sayfasının numarasını ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CPrintInfo::m_bContinuePrinting](#m_bcontinueprinting)|Çerçevenin yazdırma döngüsüne devam edip etmeyeceğini belirten bir bayrak içerir.|
|[CPrintInfo::m_bDirect](#m_bdirect)|Belgenin doğrudan yazdırılıp yazdırılmadığını belirten bir bayrak içerir (Yazdır iletişim kutusunu görüntülemeden).|
|[CPrintInfo::m_bDocObject](#m_bdocobject)|Yazdırılan belgenin DocObject olup olmadığını belirten bir bayrak içerir.|
|[CPrintInfo::m_bPreview](#m_bpreview)|Belgenin önizlemesini yapıp olmadığını belirten bir bayrak içerir.|
|[CPrintInfo::m_dwFlags](#m_dwflags)|DocObject yazdırma işlemlerini belirtir.|
|[CPrintInfo::m_lpUserData](#m_lpuserdata)|Kullanıcı tarafından oluşturulan yapıiçin bir işaretçi içerir.|
|[CPrintInfo::m_nCurPage](#m_ncurpage)|Şu anda yazdırılmakta olan sayfanın numarasını tanımlar.|
|[CPrintInfo::m_nJobNumber](#m_njobnumber)|Geçerli yazdırma işi için işletim sistemi tarafından atanan iş numarasını belirtir|
|[CPrintInfo::m_nNumPreviewPages](#m_nnumpreviewpages)|Önizleme penceresinde görüntülenen sayfa sayısını tanımlar; ya 1 ya da 2.|
|[CPrintInfo::m_nOffsetPage](#m_noffsetpage)|Birleştirilmiş DocObject yazdırma işinde belirli bir DocObject'in ilk sayfasının mahsup larını belirtir.|
|[CPrintInfo::m_pPD](#m_ppd)|Yazdır iletişim kutusu `CPrintDialog` için kullanılan nesneye bir işaretçi içerir.|
|[CPrintInfo::m_rectDraw](#m_rectdraw)|Geçerli kullanılabilir sayfa alanını tanımlayan bir dikdörtgen belirtir.|
|[CPrintInfo::m_strPageDesc](#m_strpagedesc)|Sayfa numarası görüntüleme için biçim dizesi içerir.|

## <a name="remarks"></a>Açıklamalar

`CPrintInfo`bir yapıdır ve taban sınıfa sahip değildir.

Çerçeve, Yazdır veya `CPrintInfo` Yazdır Önizleme komutu seçildiği her zaman bir nesne oluşturur ve komut tamamlandığında onu yok eder.

`CPrintInfo`yazdırılacak sayfa aralığı ve şu anda yazdırılmakta olan sayfa gibi yazdırma işinin geçerli durumu gibi hem bir bütün olarak yazdırma işi hakkında bilgi içerir. Bazı bilgiler ilişkili bir [CPrintDialog](../../mfc/reference/cprintdialog-class.md) nesnesinde depolanır; bu nesne, Yazdır iletişim kutusunda kullanıcı tarafından girilen değerleri içerir.

Yazdırma `CPrintInfo` işlemi sırasında çerçeve ve görünüm sınıfınız arasında bir nesne geçirilir ve ikisi arasında bilgi alışverişi için kullanılır. Örneğin, `m_nCurPage` çerçeve, üyeye bir değer atayarak belgenin hangi sayfasının yazdırılacayakadar yazdırılacayakadar görünüm sınıfına bilgi `CPrintInfo`verir; görünüm sınıfı değeri alır ve belirtilen sayfanın gerçek yazdırma gerçekleştirir.

Başka bir örnek, belgenin uzunluğu yazdırılana kadar bilinmez durumda. Bu durumda, bir sayfa her yazdırıldıklarında belgenin sonu için görünüm sınıfı sınanır. Sona ulaşıldığında, görünüm sınıfı üyeyi `m_bContinuePrinting` `CPrintInfo` FALSE olarak ayarlar; bu, yazdırma döngüsyenini durdurmak için çerçeveyi bildirir.

`CPrintInfo`altında `CView` listelenen üye işlevler tarafından kullanılır "Ayrıca bakınız." Microsoft Foundation Class Kitaplığı tarafından sağlanan yazdırma mimarisi hakkında daha fazla bilgi için Bkz. [Çerçeve Windows](../../mfc/frame-windows.md) ve [Belge/Görünüm Mimarisi](../../mfc/document-view-architecture.md) ve Yazdırma ve [Yazdırma](../../mfc/printing.md) [makaleleri: Çok Sayfalı Belgeler.](../../mfc/multipage-documents.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CPrintInfo`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext.h

## <a name="cprintinfogetfrompage"></a><a name="getfrompage"></a>CPrintInfo::GetFromPage

Yazdırılacak ilk sayfanın numarasını almak için bu işlevi arayın.

```
UINT GetFromPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırılacak ilk sayfanın numarası.

### <a name="remarks"></a>Açıklamalar

Bu, Kullanıcı tarafından Yazdır iletişim kutusunda belirtilen değerdir ve `CPrintDialog` `m_pPD` üye tarafından başvurulan nesnede depolanır. Kullanıcı bir değer belirtmemişse, varsayılan değer belgenin ilk sayfasıdır.

## <a name="cprintinfogetmaxpage"></a><a name="getmaxpage"></a>CPrintInfo::GetMaxPage

Belgenin son sayfasının numarasını almak için bu işlevi arayın.

```
UINT GetMaxPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin son sayfasının numarası.

### <a name="remarks"></a>Açıklamalar

Bu değer `CPrintDialog` `m_pPD` üye tarafından başvurulan nesnede depolanır.

## <a name="cprintinfogetminpage"></a><a name="getminpage"></a>CPrintInfo::GetMinPage

Belgenin ilk sayfasının numarasını almak için bu işlevi arayın.

```
UINT GetMinPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin ilk sayfasının numarası.

### <a name="remarks"></a>Açıklamalar

Bu değer `CPrintDialog` `m_pPD` üye tarafından başvurulan nesnede depolanır.

## <a name="cprintinfogetoffsetpage"></a><a name="getoffsetpage"></a>CPrintInfo::GetOffsetPage

Bir DocObject istemcisinden birden çok DocObject öğesi yazdırırken ofset almak için bu işlevi çağırın.

```
UINT GetOffsetPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birleştirilmiş DocObject yazdırma işinde yazdırılan Bir DocObject öğesinin ilk sayfasından önceki sayfa sayısı.

### <a name="remarks"></a>Açıklamalar

Bu değer `m_nOffsetPage` üye tarafından başvurulan. Belgenizin ilk sayfası, diğer `m_nOffsetPage` etkin belgelerle birlikte DocObject olarak yazdırıldığında + 1 değeri numaralandırılır. `m_nOffsetPage` Üye yalnızca `m_bDocObject` değer TRUE ise geçerlidir.

## <a name="cprintinfogettopage"></a><a name="gettopage"></a>CprintInfo::Gettopage

Yazdırılacak son sayfanın numarasını almak için bu işlevi arayın.

```
UINT GetToPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırılacak son sayfanın numarası.

### <a name="remarks"></a>Açıklamalar

Bu, Kullanıcı tarafından Yazdır iletişim kutusunda belirtilen değerdir ve `CPrintDialog` `m_pPD` üye tarafından başvurulan nesnede depolanır. Kullanıcı bir değer belirtmemişse, varsayılan değer belgenin son sayfasıdır.

## <a name="cprintinfom_bcontinueprinting"></a><a name="m_bcontinueprinting"></a>CPrintInfo::m_bContinuePrinting

Çerçevenin yazdırma döngüsüne devam edip etmeyeceğini belirten bir bayrak içerir.

### <a name="remarks"></a>Açıklamalar

Yazdırma zamanı pagination yapıyorsanız, belgenin sonuna `CView::OnPrepareDC` ulaşıldıktan sonra geçersiz kılmada bu üyeyi FALSE olarak ayarlayabilirsiniz. `SetMaxPage` Üye işlevi kullanarak yazdırma işinin başında belgenin uzunluğunu belirttiyseniz, bu değişkeni değiştirmeniz gerekmez. `m_bContinuePrinting` Üye, BOOL türünün ortak değişkenidir.

## <a name="cprintinfom_bdirect"></a><a name="m_bdirect"></a>CPrintInfo::m_bDirect

Print iletişim kutusu doğrudan yazdırma için atlanacaksa, çerçeve bu üyeyi TRUE olarak ayarlar; YANLIŞ aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Yazdırma iletişim kutusu, kabuktan yazdırDığınızda veya komut kimliği ID_FILE_PRINT_DIRECT kullanarak yazdırma yapıldığında normalde atlanır.

Normalde bu üyeyi değiştirmezsiniz, ancak değiştirirseniz, [CView::DoPreparePrinting'i](../../mfc/reference/cview-class.md#doprepareprinting) [cview::OnPreparePrinting'i](../../mfc/reference/cview-class.md#onprepareprinting)aramadan önce değiştirin.

## <a name="cprintinfom_bdocobject"></a><a name="m_bdocobject"></a>CPrintInfo::m_bDocObject

Yazdırılan belgenin DocObject olup olmadığını belirten bir bayrak içerir.

### <a name="remarks"></a>Açıklamalar

Veri `m_dwFlags` üyeleri `m_nOffsetPage` ve bu bayrak DOĞRU olmadığı sürece geçersizdir.

## <a name="cprintinfom_bpreview"></a><a name="m_bpreview"></a>CPrintInfo::m_bPreview

Belgenin önizlemesini yapıp olmadığını belirten bir bayrak içerir.

### <a name="remarks"></a>Açıklamalar

Bu, kullanıcının hangi komutu yürüttüğüne bağlı olarak çerçeve tarafından ayarlanır. Yazdırma iletişim kutusu yazdırma önizleme işi için görüntülenmez. `m_bPreview` Üye, BOOL türünün ortak değişkenidir.

## <a name="cprintinfom_dwflags"></a><a name="m_dwflags"></a>CPrintInfo::m_dwFlags

DocObject yazdırma işlemlerini belirten bayrakların birleşimini içerir.

### <a name="remarks"></a>Açıklamalar

Yalnızca veri üyesi `m_bDocObject` TRUE ise geçerlidir.

Bayraklar aşağıdaki değerlerden biri veya birkaçı olabilir:

- PRINTFLAG_MAYBOTHERUSER

- PRINTFLAG_PROMPTUSER

- PRINTFLAG_USERMAYCHANGEPRINTER

- PRINTFLAG_RECOMPOSETODEVICE

- PRINTFLAG_DONTACTUALLYPRINT

- PRINTFLAG_FORCEPROPERTIES

- PRINTFLAG_PRINTTOFILE

## <a name="cprintinfom_lpuserdata"></a><a name="m_lpuserdata"></a>CPrintInfo::m_lpUserData

Kullanıcı tarafından oluşturulan yapıiçin bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Bunu, görünüm sınıfınızda depolamak istemediğiniz yazdırmaya özgü verileri depolamak için kullanabilirsiniz. `m_lpUserData` Üye, LPVOID türünün ortak değişkenidir.

## <a name="cprintinfom_ncurpage"></a><a name="m_ncurpage"></a>CPrintInfo::m_nCurPage

Geçerli sayfanın numarasını içerir.

### <a name="remarks"></a>Açıklamalar

Çerçeve çağrıları `CView::OnPrepareDC` `CView::OnPrint` ve belgenin her sayfası için bir kez, bu üye için her zaman farklı bir değer belirten; değerleri tarafından `GetFromPage` döndürülen değerden döndürülen `GetToPage`değere kadar değişmektedir. Bu üyeyi `CView::OnPrepareDC` geçersiz kılmalarınızda ve `CView::OnPrint` belgenin belirtilen sayfasını yazdırmak için kullanın.

Önizleme modu ilk çağrıldığınızda, çerçeve belgenin hangi sayfasının başlangıçta önizlemesi gerektiğini belirlemek için bu üyenin değerini okur. Önizleme moduna girerken kullanıcının belgedeki `CView::OnPreparePrinting` geçerli konumunu korumak için bu üyenin değerini geçersiz kılmanızda ayarlayabilirsiniz. `m_nCurPage` Üye, UINT türünün ortak değişkenidir.

## <a name="cprintinfom_njobnumber"></a><a name="m_njobnumber"></a>CPrintInfo::m_nJobNumber

Geçerli yazdırma işi için işletim sistemi tarafından atanan iş numarasını gösterir.

### <a name="remarks"></a>Açıklamalar

Bu değer, iş henüz yazdırılmamışsa (diğer bir deyişle, `CPrintInfo` nesne yeni oluşturulmuşsa ve henüz yazdırmak için kullanılmamışsa) veya işi başlatmada bir hata varsa SP_ERROR olabilir.

## <a name="cprintinfom_nnumpreviewpages"></a><a name="m_nnumpreviewpages"></a>CPrintInfo::m_nNumPreviewPages

Önizleme modunda görüntülenen sayfa sayısını içerir; 1 veya 2 olabilir.

### <a name="remarks"></a>Açıklamalar

`m_nNumPreviewPages` Üye, UINT türünün ortak değişkenidir.

## <a name="cprintinfom_noffsetpage"></a><a name="m_noffsetpage"></a>CPrintInfo::m_nOffsetPage

Birleştirilmiş DocObject yazdırma işinde belirli bir DocObject'in ilk sayfasından önceki sayfa sayısını içerir.

## <a name="cprintinfom_ppd"></a><a name="m_ppd"></a>CPrintInfo::m_pPD

Yazdırma işi için `CPrintDialog` Yazdır iletişim kutusunu görüntülemek için kullanılan nesneye bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Üye, `m_pPD` `CPrintDialog`işaretçi olarak bildirilen genel bir değişkendir.

## <a name="cprintinfom_rectdraw"></a><a name="m_rectdraw"></a>CPrintInfo::m_rectDraw

Sayfanın kullanılabilir çizim alanını mantıksal koordinatlarla belirtir.

### <a name="remarks"></a>Açıklamalar

Bu sizin geçersiz kılma başvurmak isteyebilirsiniz `CView::OnPrint`. Üstbilgi, altbilgi ve benzeri yazdırdıktan sonra hangi alanın kullanılabilir kaldığını izlemek için bu üyeyi kullanabilirsiniz. Üye, `m_rectDraw` genel bir tür `CRect`değişkenidir.

## <a name="cprintinfom_strpagedesc"></a><a name="m_strpagedesc"></a>CPrintInfo::m_strPageDesc

Yazdırma önizlemesi sırasında sayfa numaralarını görüntülemek için kullanılan biçim dizesi içerir; bu dize, biri tek sayfalı ekran ve diğeri çift sayfalı ekran için olmak üzere iki alt dizeden oluşur ve her biri '\n' karakteri yle sonlandırılır.

### <a name="remarks"></a>Açıklamalar

Çerçeve varsayılan değer olarak "Sayfa %u\nPages %u-%u\n" kullanır. Sayfa numaraları için farklı bir biçim istiyorsanız, geçersiz kılmanızda `CView::OnPreparePrinting`bir biçim dizesi belirtin. Üye, `m_strPageDesc` genel bir tür `CString`değişkenidir.

## <a name="cprintinfosetmaxpage"></a><a name="setmaxpage"></a>CPrintInfo::SetMaxPage

Belgenin son sayfasının numarasını belirtmek için bu işlevi arayın.

```cpp
void SetMaxPage(UINT nMaxPage);
```

### <a name="parameters"></a>Parametreler

*nMaxPage*<br/>
Belgenin son sayfasının numarası.

### <a name="remarks"></a>Açıklamalar

Bu değer `CPrintDialog` `m_pPD` üye tarafından başvurulan nesnede depolanır. Belgenin uzunluğu yazdırılmadan önce biliniyorsa, `CView::OnPreparePrinting`geçersiz kılmanızdan bu işlevi arayın. Belgenin uzunluğu Yazdır iletişim kutusunda kullanıcı tarafından belirtilen bir ayara bağlıysa, bu işlevi `CView::OnBeginPrinting`geçersiz kılmanızdan arayın Belgenin uzunluğu yazdırılına kadar bilinmiyorsa, `m_bContinuePrinting` yazdırma döngüsünün denetimini denetlemek için üyeyi kullanın.

### <a name="example"></a>Örnek

  CView örneğine [bakın::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).

## <a name="cprintinfosetminpage"></a><a name="setminpage"></a>CPrintInfo::SetMinPage

Belgenin ilk sayfasının numarasını belirtmek için bu işlevi arayın.

```cpp
void SetMinPage(UINT nMinPage);
```

### <a name="parameters"></a>Parametreler

*nMinPage*<br/>
Belgenin ilk sayfasının numarası.

### <a name="remarks"></a>Açıklamalar

Sayfa numaraları normalde 1'den başlar. Bu değer `CPrintDialog` `m_pPD` üye tarafından başvurulan nesnede depolanır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)<br/>
[CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)<br/>
[CView::OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)<br/>
[CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)<br/>
[CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)<br/>
[CView::Onprint](../../mfc/reference/cview-class.md#onprint)
