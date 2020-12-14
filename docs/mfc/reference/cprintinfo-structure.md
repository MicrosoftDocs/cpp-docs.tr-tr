---
description: 'Daha fazla bilgi edinin: CPrintInfo yapısı'
title: CPrintInfo yapısı
ms.date: 11/04/2016
f1_keywords:
- CPrintInfo
helpviewer_keywords:
- CPrintInfo structure [MFC]
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
ms.openlocfilehash: 355bcf2f04b32756ae16147465054e945d70cf78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343394"
---
# <a name="cprintinfo-structure"></a>CPrintInfo yapısı

Yazdırma veya baskı önizleme işi hakkında bilgi depolar.

## <a name="syntax"></a>Syntax

```
struct CPrintInfo
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPrintInfo:: GetFromPage](#getfrompage)|Yazdırılan ilk sayfanın numarasını döndürür.|
|[CPrintInfo:: GetMaxPage](#getmaxpage)|Belgenin son sayfasının numarasını döndürür.|
|[CPrintInfo:: GetMinPage](#getminpage)|Belgenin ilk sayfasının numarasını döndürür.|
|[CPrintInfo:: GetOffsetPage](#getoffsetpage)|Birleşik bir DocObject yazdırma işinde yazdırılan bir DocObject öğesinin ilk sayfasından önceki sayfa sayısını döndürür.|
|[CPrintInfo:: GetToPage](#gettopage)|Yazdırılmakta olan son sayfanın numarasını döndürür.|
|[CPrintInfo:: SetMaxPage](#setmaxpage)|Belgenin son sayfasının numarasını ayarlar.|
|[CPrintInfo:: SetMinPage](#setminpage)|Belgenin ilk sayfasının numarasını ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPrintInfo:: m_bContinuePrinting](#m_bcontinueprinting)|Framework 'ün yazdırma döngüsüne devam edip etmediğini belirten bir bayrak içerir.|
|[CPrintInfo:: m_bDirect](#m_bdirect)|Belgenin doğrudan yazdırılıp yazdırılmadığını gösteren bir bayrak içerir (Yazdır iletişim kutusu görüntülenmeden).|
|[CPrintInfo:: m_bDocObject](#m_bdocobject)|Yazdırılan belgenin bir DocObject olup olmadığını belirten bir bayrak içerir.|
|[CPrintInfo:: m_bPreview](#m_bpreview)|Belgenin önizlemesi yapılıp yapılmayacağını belirten bir bayrak içerir.|
|[CPrintInfo:: m_dwFlags](#m_dwflags)|DocObject yazdırma işlemlerini belirtir.|
|[CPrintInfo:: m_lpUserData](#m_lpuserdata)|Kullanıcı tarafından oluşturulan yapıya yönelik bir işaretçi içerir.|
|[CPrintInfo:: m_nCurPage](#m_ncurpage)|Yazdırılmakta olan sayfanın numarasını tanımlar.|
|[CPrintInfo:: m_nJobNumber](#m_njobnumber)|Geçerli yazdırma işi için işletim sistemi tarafından atanan iş numarasını belirtir|
|[CPrintInfo:: m_nNumPreviewPages](#m_nnumpreviewpages)|Önizleme penceresinde görünen sayfa sayısını belirler; ya da 1 veya 2.|
|[CPrintInfo:: m_nOffsetPage](#m_noffsetpage)|Belirli bir DocObject 'in Birleşik bir DocObject yazdırma işinde ilk sayfasının sapmasını belirtir.|
|[CPrintInfo:: m_pPD](#m_ppd)|`CPrintDialog`Yazdır iletişim kutusu için kullanılan nesneye yönelik bir işaretçi içerir.|
|[CPrintInfo:: m_rectDraw](#m_rectdraw)|Geçerli kullanılabilir sayfa alanını tanımlayan bir dikdörtgen belirtir.|
|[CPrintInfo:: m_strPageDesc](#m_strpagedesc)|Sayfa numarası görüntüleme için bir biçim dizesi içerir.|

## <a name="remarks"></a>Açıklamalar

`CPrintInfo` bir yapıdır ve temel bir sınıfa sahip değildir.

Çerçeve, `CPrintInfo` yazdırma veya baskı önizleme komutunun seçildiği her seferinde bir nesne oluşturur ve komut tamamlandığında onu yok eder.

`CPrintInfo` yazdırma işinin tamamı hakkında, yazdırılacak sayfa aralığı ve yazdırma işinin geçerli durumu gibi (Yazdırılmakta olan sayfa gibi) ilgili bilgileri içerir. Bazı bilgiler ilişkili bir [CPrintDialog](../../mfc/reference/cprintdialog-class.md) nesnesinde depolanır; Bu nesne, Yazdır iletişim kutusunda Kullanıcı tarafından girilen değerleri içerir.

`CPrintInfo`Yazdırma işlemi sırasında çerçeve ile görünüm sınıfınız arasında bir nesne geçirilir ve iki arasındaki bilgileri değiş tokuş etmek için kullanılır. Örneğin, çerçeve, öğesinin üyesine bir değer atayarak görünüm sınıfına belgenin hangi sayfada yazdırılacağını bildirir `m_nCurPage` `CPrintInfo` ; View sınıfı değeri alır ve belirtilen sayfanın gerçek baskısını gerçekleştirir.

Başka bir örnek, belgenin uzunluğunun yazdırılana kadar bilinmediğini belirten durumdur. Bu durumda, görünüm sınıfı her sayfa yazdırıldığında belgenin sonuna kadar sınar. Sona ulaşıldığında, görünüm sınıfı `m_bContinuePrinting` öğesinin ÜYESINI `CPrintInfo` false olarak ayarlar; bu, çerçeveye yazdırma döngüsünü durdurmasını bildirir.

`CPrintInfo` , `CView` "Ayrıca bkz." altında listelenen üye işlevleri tarafından kullanılır. Microsoft Foundation Class Kitaplığı tarafından sunulan yazdırma mimarisi hakkında daha fazla bilgi için bkz. [çerçeve pencereleri](../../mfc/frame-windows.md) ve [belge/görünüm mimarisi](../../mfc/document-view-architecture.md) ve [yazdırma](../../mfc/printing.md) ve yazdırma makaleleri [: çok sayfalı belgeler](../../mfc/multipage-documents.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CPrintInfo`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext. h

## <a name="cprintinfogetfrompage"></a><a name="getfrompage"></a> CPrintInfo:: GetFromPage

Yazdırılacak ilk sayfanın numarasını almak için bu işlevi çağırın.

```
UINT GetFromPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırılacak ilk sayfa sayısı.

### <a name="remarks"></a>Açıklamalar

Bu, Yazdır iletişim kutusunda Kullanıcı tarafından belirtilen değerdir ve `CPrintDialog` üyenin başvurduğu nesnede saklanır `m_pPD` . Kullanıcı bir değer belirtmediğinden, varsayılan olarak belgenin ilk sayfasıdır.

## <a name="cprintinfogetmaxpage"></a><a name="getmaxpage"></a> CPrintInfo:: GetMaxPage

Belgenin son sayfasının numarasını almak için bu işlevi çağırın.

```
UINT GetMaxPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin son sayfa sayısı.

### <a name="remarks"></a>Açıklamalar

Bu değer `CPrintDialog` , üyenin başvurduğu nesnede saklanır `m_pPD` .

## <a name="cprintinfogetminpage"></a><a name="getminpage"></a> CPrintInfo:: GetMinPage

Belgenin ilk sayfasının numarasını almak için bu işlevi çağırın.

```
UINT GetMinPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin ilk sayfa sayısı.

### <a name="remarks"></a>Açıklamalar

Bu değer `CPrintDialog` , üyenin başvurduğu nesnede saklanır `m_pPD` .

## <a name="cprintinfogetoffsetpage"></a><a name="getoffsetpage"></a> CPrintInfo:: GetOffsetPage

Bir DocObject istemcisinden birden çok DocObject öğesi yazdırırken sapmayı almak için bu işlevi çağırın.

```
UINT GetOffsetPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir DocObject öğesinin ilk sayfasından önceki ve birleştirilmiş bir DocObject yazdırma işinde yazdırılan sayfa sayısı.

### <a name="remarks"></a>Açıklamalar

Bu değere üye tarafından başvurulur `m_nOffsetPage` . Belgenizin ilk sayfası, `m_nOffsetPage` diğer etkin belgelerle bir DocObject olarak yazdırıldığında + 1 değeri numaralandırılır. `m_nOffsetPage`Üye yalnızca `m_bDocObject` değeri true olduğunda geçerlidir.

## <a name="cprintinfogettopage"></a><a name="gettopage"></a> CPrintInfo:: GetToPage

Yazdırılacak son sayfanın numarasını almak için bu işlevi çağırın.

```
UINT GetToPage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazdırılacak son sayfa sayısı.

### <a name="remarks"></a>Açıklamalar

Bu, Yazdır iletişim kutusunda Kullanıcı tarafından belirtilen değerdir ve `CPrintDialog` üyenin başvurduğu nesnede saklanır `m_pPD` . Kullanıcı bir değer belirtmediğinden, varsayılan olarak belgenin son sayfasıdır.

## <a name="cprintinfom_bcontinueprinting"></a><a name="m_bcontinueprinting"></a> CPrintInfo:: m_bContinuePrinting

Framework 'ün yazdırma döngüsüne devam edip etmediğini belirten bir bayrak içerir.

### <a name="remarks"></a>Açıklamalar

Yazdırma zamanı sayfalandırma yapıyorsanız, belgenin sonuna ulaşıldığında bu üyeyi geçersiz kılmanızda FALSE olarak ayarlayabilirsiniz `CView::OnPrepareDC` . Üye işlevini kullanarak yazdırma işinin başlangıcında belge uzunluğunu belirttiyseniz, bu değişkeni değiştirmeniz gerekmez `SetMaxPage` . `m_bContinuePrinting`Üye bool türünde ortak bir değişkendir.

## <a name="cprintinfom_bdirect"></a><a name="m_bdirect"></a> CPrintInfo:: m_bDirect

Yazdırma iletişim kutusu doğrudan yazdırma için atlanacağı Framework bu üyeyi TRUE olarak ayarlar; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Genellikle, kabuktan yazdırdığınızda veya komut KIMLIĞI ID_FILE_PRINT_DIRECT kullanılarak yazdırma tamamlandığında Yazdır iletişim kutusu atlanır.

Normalde bu üyeyi değiştirmeyin, ancak değişikliği yaparsanız CView: [: OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)geçersiz kılmada [cview::D oprepareprinting](../../mfc/reference/cview-class.md#doprepareprinting) öğesini çağırmadan önce onu değiştirin.

## <a name="cprintinfom_bdocobject"></a><a name="m_bdocobject"></a> CPrintInfo:: m_bDocObject

Yazdırılan belgenin bir DocObject olup olmadığını belirten bir bayrak içerir.

### <a name="remarks"></a>Açıklamalar

Veri üyeleri `m_dwFlags` ve `m_nOffsetPage` Bu bayrak true olmadığı takdirde geçersizdir.

## <a name="cprintinfom_bpreview"></a><a name="m_bpreview"></a> CPrintInfo:: m_bPreview

Belgenin önizlemesi yapılıp yapılmayacağını belirten bir bayrak içerir.

### <a name="remarks"></a>Açıklamalar

Bu, kullanıcının yürüttüğü komuta bağlı olarak Framework tarafından ayarlanır. Yazdır iletişim kutusu, yazdırma-önizleme işi için gösterilmez. `m_bPreview`Üye bool türünde ortak bir değişkendir.

## <a name="cprintinfom_dwflags"></a><a name="m_dwflags"></a> CPrintInfo:: m_dwFlags

DocObject yazdırma işlemlerini belirten bayrakların bir birleşimini içerir.

### <a name="remarks"></a>Açıklamalar

Yalnızca veri üyesi TRUE ise geçerlidir `m_bDocObject` .

Bayraklar aşağıdaki değerlerden biri veya daha fazlası olabilir:

- PRINTFLAG_MAYBOTHERUSER

- PRINTFLAG_PROMPTUSER

- PRINTFLAG_USERMAYCHANGEPRINTER

- PRINTFLAG_RECOMPOSETODEVICE

- PRINTFLAG_DONTACTUALLYPRINT

- PRINTFLAG_FORCEPROPERTIES

- PRINTFLAG_PRINTTOFILE

## <a name="cprintinfom_lpuserdata"></a><a name="m_lpuserdata"></a> CPrintInfo:: m_lpUserData

Kullanıcı tarafından oluşturulan yapıya yönelik bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Bunu, görünüm sınıfınıza depolamak istemediğiniz, yazdırmaya özgü verileri depolamak için kullanabilirsiniz. `m_lpUserData`Üye, LPVOID türünde ortak bir değişkendir.

## <a name="cprintinfom_ncurpage"></a><a name="m_ncurpage"></a> CPrintInfo:: m_nCurPage

Geçerli sayfanın numarasını içerir.

### <a name="remarks"></a>Açıklamalar

Çerçeve, `CView::OnPrepareDC` `CView::OnPrint` her seferinde bu üye için farklı bir değer belirterek, belgenin her sayfası için ve bir kez çağırır; değeri, tarafından döndürülen değerden tarafından döndürülen değerden bu değere `GetFromPage` göre değişir `GetToPage` . `CView::OnPrepareDC` `CView::OnPrint` Belgenin belirtilen sayfasını yazdırmak için ve Geçersiz kılmalarınızın bu üyesini kullanın.

Önizleme modu ilk kez çağrıldığında, çerçeve ilk olarak belgenin hangi sayfasının önizlenmesi gerektiğini belirleyen Bu üyenin değerini okur. `CView::OnPreparePrinting`Önizleme moduna girerken kullanıcının belgedeki geçerli konumunu korumak için, geçersiz kılmanızda Bu üyenin değerini ayarlayabilirsiniz. `m_nCurPage`Üye, UINT türünde ortak bir değişkendir.

## <a name="cprintinfom_njobnumber"></a><a name="m_njobnumber"></a> CPrintInfo:: m_nJobNumber

Geçerli yazdırma işi için işletim sistemi tarafından atanan iş numarasını gösterir.

### <a name="remarks"></a>Açıklamalar

Bu değer, iş henüz yazdırılmamışsa (yani, `CPrintInfo` nesne yeni oluşturulmuşsa ve henüz yazdırmak için kullanılmıyorsa) SP_ERROR olabilir veya işi başlatırken bir hata oluşursa.

## <a name="cprintinfom_nnumpreviewpages"></a><a name="m_nnumpreviewpages"></a> CPrintInfo:: m_nNumPreviewPages

Önizleme modunda gösterilecek sayfa sayısını içerir; Bu, 1 veya 2 olabilir.

### <a name="remarks"></a>Açıklamalar

`m_nNumPreviewPages`Üye, UINT türünde ortak bir değişkendir.

## <a name="cprintinfom_noffsetpage"></a><a name="m_noffsetpage"></a> CPrintInfo:: m_nOffsetPage

Birleştirilmiş bir DocObject yazdırma işinde belirli bir DocObject 'in ilk sayfasından önceki sayfa sayısını içerir.

## <a name="cprintinfom_ppd"></a><a name="m_ppd"></a> CPrintInfo:: m_pPD

`CPrintDialog`Yazdırma Işinin Yazdır iletişim kutusunu göstermek için kullanılan nesneye yönelik bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

`m_pPD`Üye, işaretçisi olarak belirtilen bir ortak değişkendir `CPrintDialog` .

## <a name="cprintinfom_rectdraw"></a><a name="m_rectdraw"></a> CPrintInfo:: m_rectDraw

Mantıksal koordinatlardaki sayfanın kullanılabilir çizim alanını belirtir.

### <a name="remarks"></a>Açıklamalar

Geçersiz kılmanızda buna başvurmak isteyebilirsiniz `CView::OnPrint` . Bu üyeyi, üst bilgileri, altbilgileri ve benzerlerini yazdırırken hangi alanın kullanılabilir durumda kaldığını izlemek için kullanabilirsiniz. `m_rectDraw`Üye türünde ortak bir değişkendir `CRect` .

## <a name="cprintinfom_strpagedesc"></a><a name="m_strpagedesc"></a> CPrintInfo:: m_strPageDesc

Baskı Önizleme sırasında sayfa numaralarını görüntülemek için kullanılan bir biçim dizesi içerir; Bu dize, biri tek sayfalı görüntü için ve diğeri bir ' \n ' karakteriyle sonlanarak çift sayfalı görüntü için olmak üzere iki alt dizeden oluşur.

### <a name="remarks"></a>Açıklamalar

Çerçeve, varsayılan değer olarak "sayfa%u\nPages% u-%u\n" kullanır. Sayfa numaraları için farklı bir biçim istiyorsanız, geçersiz kılmada bir biçim dizesi belirtin `CView::OnPreparePrinting` . `m_strPageDesc`Üye türünde ortak bir değişkendir `CString` .

## <a name="cprintinfosetmaxpage"></a><a name="setmaxpage"></a> CPrintInfo:: SetMaxPage

Belgenin son sayfasının numarasını belirtmek için bu işlevi çağırın.

```cpp
void SetMaxPage(UINT nMaxPage);
```

### <a name="parameters"></a>Parametreler

*nMaxPage*<br/>
Belgenin son sayfa sayısı.

### <a name="remarks"></a>Açıklamalar

Bu değer `CPrintDialog` , üyenin başvurduğu nesnede saklanır `m_pPD` . Belgenin uzunluğu yazdırılmadan önce biliniyorsa, bu işlevi geçersiz kılmadan çağırın `CView::OnPreparePrinting` . Belge uzunluğu, Yazdır iletişim kutusunda Kullanıcı tarafından belirtilen bir ayara bağımlıysa, bu işlevi geçersiz kılmanızda çağırın `CView::OnBeginPrinting` . Belgenin uzunluğu yazdırılana kadar bilinmiyorsa, `m_bContinuePrinting` yazdırma döngüsünü denetlemek için üyeyi kullanın.

### <a name="example"></a>Örnek

  [CView:: OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)örneğine bakın.

## <a name="cprintinfosetminpage"></a><a name="setminpage"></a> CPrintInfo:: SetMinPage

Belgenin ilk sayfasının numarasını belirtmek için bu işlevi çağırın.

```cpp
void SetMinPage(UINT nMinPage);
```

### <a name="parameters"></a>Parametreler

*nMinPage*<br/>
Belgenin ilk sayfa sayısı.

### <a name="remarks"></a>Açıklamalar

Sayfa numaraları normalde 1 ' den başlar. Bu değer `CPrintDialog` , üyenin başvurduğu nesnede saklanır `m_pPD` .

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CView:: OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)<br/>
[CView:: OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)<br/>
[CView:: OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)<br/>
[CView:: Onhazırlık EDC](../../mfc/reference/cview-class.md#onpreparedc)<br/>
[CView:: OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)<br/>
[CView:: OnPrint](../../mfc/reference/cview-class.md#onprint)
