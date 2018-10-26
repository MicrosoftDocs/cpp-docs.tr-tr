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
ms.openlocfilehash: b8c1fb4d82bd1aaeb9f625fea66aa339a0ef4d97
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50082898"
---
# <a name="cprintinfo-structure"></a>Cprintınfo yapısı

Bir yazdırma ya da yazdırma önizleme işle ilgili bilgileri depolar.

## <a name="syntax"></a>Sözdizimi

```
struct CPrintInfo
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPrintInfo::GetFromPage](#getfrompage)|Yazdırılmasını ilk sayfa sayısını döndürür.|
|[CPrintInfo::GetMaxPage](#getmaxpage)|Son sayfa belge sayısını döndürür.|
|[CPrintInfo::GetMinPage](#getminpage)|İlk sayfa belge sayısını döndürür.|
|[CPrintInfo::GetOffsetPage](#getoffsetpage)|İlk sayfa birleşik DocObject yazdırma işi yazdırılmasını DocObject öğesinin önceki sayfa sayısını döndürür.|
|[CPrintInfo::GetToPage](#gettopage)|Yazdırılmasını son sayfa sayısını döndürür.|
|[CPrintInfo::SetMaxPage](#setmaxpage)|Son sayfa belge sayısını ayarlar.|
|[CPrintInfo::SetMinPage](#setminpage)|İlk sayfa belge sayısını ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPrintInfo::m_bContinuePrinting](#m_bcontinueprinting)|Framework yazdırma döngü devam olup olmadığını belirten bir bayrak içerir.|
|[CPrintInfo::m_bDirect](#m_bdirect)|Doğrudan (Yazdır iletişim kutusu görüntülenmeden) belge yazdırılmasını olmadığını belirten bir bayrak içerir.|
|[CPrintInfo::m_bDocObject](#m_bdocobject)|Belgenin yazdırılmasını DocObject olup olmadığını belirten bir bayrak içerir.|
|[CPrintInfo::m_bPreview](#m_bpreview)|Belge önizlemesi olup olmadığını belirten bir bayrak içerir.|
|[CPrintInfo::m_dwFlags](#m_dwflags)|DocObject yazdırma işlemleri belirtir.|
|[CPrintInfo::m_lpUserData](#m_lpuserdata)|Kullanıcı tarafından oluşturulan bir yapıya bir işaretçi içerir.|
|[CPrintInfo::m_nCurPage](#m_ncurpage)|Şu anda yazdırılmasını sayfa sayısını tanımlar.|
|[CPrintInfo::m_nJobNumber](#m_njobnumber)|Geçerli yazdırma işi için işletim sistemi tarafından atanan işi belirtir|
|[CPrintInfo::m_nNumPreviewPages](#m_nnumpreviewpages)|Önizleme penceresinde görüntülenen sayfa sayısını tanımlar; 1 veya 2.|
|[CPrintInfo::m_nOffsetPage](#m_noffsetpage)|Belirli bir DocObject'ın ilk sayfasında uzaklığı birleşik DocObject yazdırma işi belirtir.|
|[CPrintInfo::m_pPD](#m_ppd)|Bir işaretçi içeren `CPrintDialog` Yazdır iletişim kutusu için kullanılan nesne.|
|[CPrintInfo::m_rectDraw](#m_rectdraw)|Geçerli sayfa kullanılabilir alanı tanımlayan bir dikdörtgen belirtir.|
|[CPrintInfo::m_strPageDesc](#m_strpagedesc)|Sayfa numarası görüntüleme için bir biçim dizesi içerir.|

## <a name="remarks"></a>Açıklamalar

`CPrintInfo` bir yapı olduğunu ve bir temel sınıfa sahip değil.

Bir nesnenin framework oluşturur `CPrintInfo` her zaman yazdırma ya da yazdırma önizleme komutu seçilir ve komutu tamamlandığında yok eder.

`CPrintInfo` yazdırılacak sayfaların aralığı gibi bir bütün olarak yazdırma işi hem gibi şu anda yazdırılan sayfanın yazdırma işinin geçerli durumu hakkında bilgi içerir. Bazı bilgiler depolanır, ilişkili bir [CPrintDialog](../../mfc/reference/cprintdialog-class.md) nesne; bu nesne Yazdır iletişim kutusu kullanıcı tarafından girilen değerler içerir.

A `CPrintInfo` nesne framework ve görünüm sınıfınıza arasında yazdırma işlemi sırasında geçirilir ve ikisi arasında bilgi alışverişi için kullanılır. Örneğin, framework görünüm sınıfı için bir değer atayarak yazdırmak için belgenin hangi sayfası bildirir `m_nCurPage` üyesi `CPrintInfo`; sınıfı bir değer alır ve belirtilen sayfanın yazdırma gerçekleştirir görünümü.

Yazdırılan kadar belgenin uzunluğunu bilinmiyor çalışması başka bir örnektir. Bu durumda, görünüm sınıfı, her bir sayfa yazdırıldığında belgenin sonuna için test eder. Görünüm sınıfını sonuna ulaşıldığında ayarlar `m_bContinuePrinting` üyesi `CPrintInfo` için FALSE; Bu, yazdırma döngü durdurmak için framework bildirir.

`CPrintInfo` üye işlevleri tarafından kullanılan `CView` listelenen altında "Ayrıca bkz." Microsoft Foundation Class Kitaplığı tarafından sağlanan yazdırma mimarisi hakkında daha fazla bilgi için bkz: [çerçeve Windows](../../mfc/frame-windows.md) ve [belge/görünüm mimarisi](../../mfc/document-view-architecture.md) ve makaleleri [ Yazdırma](../../mfc/printing.md) ve [yazdırma: birden fazla belge](../../mfc/multipage-documents.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CPrintInfo`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxext.h

##  <a name="getfrompage"></a>  CPrintInfo::GetFromPage

Yazdırılacak ilk sayfa sayısını almak için bu işlevi çağırın.

```
UINT GetFromPage() const;

```

### <a name="return-value"></a>Dönüş Değeri

Yazdırılacak ilk sayfa numarası.

### <a name="remarks"></a>Açıklamalar

Yazdır iletişim kutusu kullanıcı tarafından belirtilen değere budur ve içinde depolanan `CPrintDialog` tarafından başvurulan nesne `m_pPD` üyesi. Kullanıcı bir değere belirtilmemişse, varsayılan belge ilk sayfadır.

##  <a name="getmaxpage"></a>  CPrintInfo::GetMaxPage

Belgenin son sayfa numarası almak için bu işlevi çağırın.

```
UINT GetMaxPage() const;

```

### <a name="return-value"></a>Dönüş Değeri

Belgenin son sayfa numarası.

### <a name="remarks"></a>Açıklamalar

Bu değer depolanan `CPrintDialog` tarafından başvurulan nesne `m_pPD` üyesi.

##  <a name="getminpage"></a>  CPrintInfo::GetMinPage

İlk sayfa belge sayısını almak için bu işlevi çağırın.

```
UINT GetMinPage() const;

```

### <a name="return-value"></a>Dönüş Değeri

Belgenin ilk sayfa numarası.

### <a name="remarks"></a>Açıklamalar

Bu değer depolanan `CPrintDialog` tarafından başvurulan nesne `m_pPD` üyesi.

##  <a name="getoffsetpage"></a>  CPrintInfo::GetOffsetPage

DocObject istemciden birden çok DocObject öğesini yazdırmayı zaman uzaklığını almak için bu işlevi çağırın.

```
UINT GetOffsetPage() const;

```

### <a name="return-value"></a>Dönüş Değeri

İlk sayfa birleşik DocObject yazdırma işi yazdırılmasını DocObject öğesinin önceki sayfa sayısı.

### <a name="remarks"></a>Açıklamalar

Bu değer tarafından başvurulan `m_nOffsetPage` üyesi. İlk sayfa belgenizin numaralı `m_nOffsetPage` değeri + diğer etkin belgeler ile DocObject olarak yazdırıldığında 1. `m_nOffsetPage` Üyesidir geçerli yalnızca `m_bDocObject` TRUE değeridir.

##  <a name="gettopage"></a>  CPrintInfo::GetToPage

Yazdırılacak son sayfa numarası almak için bu işlevi çağırın.

```
UINT GetToPage() const;

```

### <a name="return-value"></a>Dönüş Değeri

Yazdırılacak son sayfa numarası.

### <a name="remarks"></a>Açıklamalar

Yazdır iletişim kutusu kullanıcı tarafından belirtilen değere budur ve içinde depolanan `CPrintDialog` tarafından başvurulan nesne `m_pPD` üyesi. Kullanıcı bir değer belirtmediyse varsayılan belgenin son sayfasıdır.

##  <a name="m_bcontinueprinting"></a>  CPrintInfo::m_bContinuePrinting

Framework yazdırma döngü devam olup olmadığını belirten bir bayrak içerir.

### <a name="remarks"></a>Açıklamalar

Yazdırma zamanı sayfalandırma yapıyorsanız, FALSE geçersiz kılma için bu üye ayarlayabilirsiniz `CView::OnPrepareDC` sonra belgenin sonuna ulaşıldı. Belge yazdırma işi kullanarak başında uzunluğunu belirttiyseniz, bu değişkeni değiştirmek zorunda değilsiniz `SetMaxPage` üye işlevi. `m_bContinuePrinting` Üye BOOL türü genel değişkenidir.

##  <a name="m_bdirect"></a>  CPrintInfo::m_bDirect

Framework doğrudan yazdırma için yazdırma iletişim kutusu atlanır, bu üye TRUE olarak ayarlar; FALSE Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Yazdır iletişim kabuğu veya ne zaman yazdırmayı yazdırırken normalde atlanır kimliği ID_FILE_PRINT_DIRECT komutunu kullanarak.

Normalde bu üye değiştirmez ancak siz, bunu önce çağrı değiştirirseniz [CView::DoPreparePrinting](../../mfc/reference/cview-class.md#doprepareprinting) kılacağınızı içinde [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).

##  <a name="m_bdocobject"></a>  CPrintInfo::m_bDocObject

Belgenin yazdırılmasını DocObject olup olmadığını belirten bir bayrak içerir.

### <a name="remarks"></a>Açıklamalar

Veri üyeleri `m_dwFlags` ve `m_nOffsetPage` bu bayrağı TRUE olmadıkça geçersizdir.

##  <a name="m_bpreview"></a>  CPrintInfo::m_bPreview

Belge önizlemesi olup olmadığını belirten bir bayrak içerir.

### <a name="remarks"></a>Açıklamalar

Bu komut kullanıcının bağlı olarak yürütüldüğü framework tarafından ayarlanır. Yazdır iletişim kutusu için bir baskı önizleme işi görüntülenmez. `m_bPreview` Üye BOOL türü genel değişkenidir.

##  <a name="m_dwflags"></a>  CPrintInfo::m_dwFlags

DocObject yazdırma işlemleri belirten bayrak birleşimini içerir.

### <a name="remarks"></a>Açıklamalar

Yalnızca şu durumlarda geçerli veri üyesi `m_bDocObject` true'dur.

Bayraklar, bir veya daha fazla aşağıdaki değerlerden biri olabilir:

- PRINTFLAG_MAYBOTHERUSER

- PRINTFLAG_PROMPTUSER

- PRINTFLAG_USERMAYCHANGEPRINTER

- PRINTFLAG_RECOMPOSETODEVICE

- PRINTFLAG_DONTACTUALLYPRINT

- PRINTFLAG_FORCEPROPERTIES

- PRINTFLAG_PRINTTOFILE

##  <a name="m_lpuserdata"></a>  CPrintInfo::m_lpUserData

Kullanıcı tarafından oluşturulan bir yapıya bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Bu görünüm Sınıfınız içinde depolamak istemediğiniz yazdırma özgü verileri depolamak için kullanabilirsiniz. `m_lpUserData` Üye LPVOID türü genel değişkenidir.

##  <a name="m_ncurpage"></a>  CPrintInfo::m_nCurPage

Geçerli sayfa numarası içerir.

### <a name="remarks"></a>Açıklamalar

Framework çağrıları `CView::OnPrepareDC` ve `CView::OnPrint` değerlerinin her zaman; bu üye için farklı bir değer belirterek bu belgenin her sayfa için bir kez aralığı tarafından döndürülen değerin `GetFromPage` tarafından döndürülen için `GetToPage`. Bu üye, geçersiz kılmalarda kullanın `CView::OnPrepareDC` ve `CView::OnPrint` belgenin belirtilen sayfasını yazdırmak için.

Önizleme modunu ilk kez çağrıldığında, çerçeve belgenin hangi sayfası başlangıçta önizlemesi belirlemek için bu üyenin değerini okur. Bu üyenin değeri geçersiz kılmada ayarlayabilirsiniz `CView::OnPreparePrinting` Önizleme modunu girerken kullanıcının geçerli konumun belgenin korumak için. `m_nCurPage` Üye UINT türü genel değişkenidir.

##  <a name="m_njobnumber"></a>  CPrintInfo::m_nJobNumber

Geçerli yazdırma işi için işletim sistemi tarafından atanan işi sayıyı belirtir.

### <a name="remarks"></a>Açıklamalar

İşi henüz çıkarırsa henüz bu değer SP_ERROR olabilir (diğer bir deyişle, `CPrintInfo` nesne yeni oluşturulur ve henüz yazdırmak için kullanılmamış), veya bir hata olduğunda iş başlatmadaki.

##  <a name="m_nnumpreviewpages"></a>  CPrintInfo::m_nNumPreviewPages

Önizleme modunda görüntülenen sayfa sayısını içerir. 1 veya 2 olabilir.

### <a name="remarks"></a>Açıklamalar

`m_nNumPreviewPages` Üye UINT türü genel değişkenidir.

##  <a name="m_noffsetpage"></a>  CPrintInfo::m_nOffsetPage

Birleşik DocObject yazdırma işi DocObject belirli'nın ilk sayfasında önceki sayfa sayısını içerir.

##  <a name="m_ppd"></a>  CPrintInfo::m_pPD

Bir işaretçi içeren `CPrintDialog` yazdırma işinin yazdırma iletişim kutusunu görüntülemek için kullanılan nesne.

### <a name="remarks"></a>Açıklamalar

`m_pPD` Üyesi olan bir işaretçi olarak bildirilen bir genel değişken `CPrintDialog`.

##  <a name="m_rectdraw"></a>  CPrintInfo::m_rectDraw

Sayfa kullanılabilir çizim alanı mantıksal koordinatlarını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu geçersiz kılmada başvurmak isteyebilirsiniz `CView::OnPrint`. Bu üye, üstbilgiler, altbilgiler ve benzeri yazdırdıktan sonra hangi alan kullanılabilir kalır izlemek için kullanabilirsiniz. `m_rectDraw` Üye türü genel değişkenidir `CRect`.

##  <a name="m_strpagedesc"></a>  CPrintInfo::m_strPageDesc

Baskı Önizleme sırasında sayfa numaralarını göstermek için kullanılan biçim dizesi içerir. Bu dize, iki alt dizeler, tek tek sayfa görüntüleme için ve biri için iki sayfa görüntüleme, her bir '\n' karakteriyle bitmelidir oluşur.

### <a name="remarks"></a>Açıklamalar

Çerçeve, varsayılan değer olarak "Sayfası %u\nPages % u-%u\n" kullanır. Sayfa sayıları farklı bir biçim isterseniz geçersiz kılmada bir biçim dizesi belirtin `CView::OnPreparePrinting`. `m_strPageDesc` Üye türü genel değişkenidir `CString`.

##  <a name="setmaxpage"></a>  CPrintInfo::SetMaxPage

Belgenin son sayfa numarası belirtmek için bu işlevi çağırın.

```
void SetMaxPage(UINT nMaxPage);
```

### <a name="parameters"></a>Parametreler

*nMaxPage*<br/>
Belgenin son sayfa numarası.

### <a name="remarks"></a>Açıklamalar

Bu değer depolanan `CPrintDialog` tarafından başvurulan nesne `m_pPD` üyesi. Yazdırmadan önce belgenin uzunluğunu biliniyorsa geçersiz kılma bu işlevi çağırın `CView::OnPreparePrinting`. Belgenin uzunluğunu Yazdır iletişim kutusu kullanıcı tarafından belirtilen bir ayara bağlı olduğu durumlarda geçersiz kılma bu işlevi çağırın `CView::OnBeginPrinting`. Yazdırılan kadar belgenin uzunluğunu bilinmiyor kullanırsanız `m_bContinuePrinting` yazdırma döngüyü denetlemek üzere üyesi.

### <a name="example"></a>Örnek

  Örneğin bakın [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).

##  <a name="setminpage"></a>  CPrintInfo::SetMinPage

İlk sayfa belge sayısını belirtmek için bu işlevi çağırın.

```
void SetMinPage(UINT nMinPage);
```

### <a name="parameters"></a>Parametreler

*nMinPage*<br/>
Belgenin ilk sayfa numarası.

### <a name="remarks"></a>Açıklamalar

Sayfa numarası, normalde 1'den başlar. Bu değer depolanan `CPrintDialog` tarafından başvurulan nesne `m_pPD` üyesi.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek DIBLOOK](../../visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)<br/>
[CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)<br/>
[CView::OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)<br/>
[CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)<br/>
[CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)<br/>
[CView::OnPrint](../../mfc/reference/cview-class.md#onprint)

