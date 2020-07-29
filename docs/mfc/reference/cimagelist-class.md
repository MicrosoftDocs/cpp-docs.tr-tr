---
title: CImageList sınıfı
ms.date: 11/04/2016
f1_keywords:
- CImageList
- AFXCMN/CImageList
- AFXCMN/CImageList::CImageList
- AFXCMN/CImageList::Add
- AFXCMN/CImageList::Attach
- AFXCMN/CImageList::BeginDrag
- AFXCMN/CImageList::Copy
- AFXCMN/CImageList::Create
- AFXCMN/CImageList::DeleteImageList
- AFXCMN/CImageList::DeleteTempMap
- AFXCMN/CImageList::Detach
- AFXCMN/CImageList::DragEnter
- AFXCMN/CImageList::DragLeave
- AFXCMN/CImageList::DragMove
- AFXCMN/CImageList::DragShowNolock
- AFXCMN/CImageList::Draw
- AFXCMN/CImageList::DrawEx
- AFXCMN/CImageList::DrawIndirect
- AFXCMN/CImageList::EndDrag
- AFXCMN/CImageList::ExtractIcon
- AFXCMN/CImageList::FromHandle
- AFXCMN/CImageList::FromHandlePermanent
- AFXCMN/CImageList::GetBkColor
- AFXCMN/CImageList::GetDragImage
- AFXCMN/CImageList::GetImageCount
- AFXCMN/CImageList::GetImageInfo
- AFXCMN/CImageList::GetSafeHandle
- AFXCMN/CImageList::Read
- AFXCMN/CImageList::Remove
- AFXCMN/CImageList::Replace
- AFXCMN/CImageList::SetBkColor
- AFXCMN/CImageList::SetDragCursorImage
- AFXCMN/CImageList::SetImageCount
- AFXCMN/CImageList::SetOverlayImage
- AFXCMN/CImageList::Write
- AFXCMN/CImageList::m_hImageList
helpviewer_keywords:
- CImageList [MFC], CImageList
- CImageList [MFC], Add
- CImageList [MFC], Attach
- CImageList [MFC], BeginDrag
- CImageList [MFC], Copy
- CImageList [MFC], Create
- CImageList [MFC], DeleteImageList
- CImageList [MFC], DeleteTempMap
- CImageList [MFC], Detach
- CImageList [MFC], DragEnter
- CImageList [MFC], DragLeave
- CImageList [MFC], DragMove
- CImageList [MFC], DragShowNolock
- CImageList [MFC], Draw
- CImageList [MFC], DrawEx
- CImageList [MFC], DrawIndirect
- CImageList [MFC], EndDrag
- CImageList [MFC], ExtractIcon
- CImageList [MFC], FromHandle
- CImageList [MFC], FromHandlePermanent
- CImageList [MFC], GetBkColor
- CImageList [MFC], GetDragImage
- CImageList [MFC], GetImageCount
- CImageList [MFC], GetImageInfo
- CImageList [MFC], GetSafeHandle
- CImageList [MFC], Read
- CImageList [MFC], Remove
- CImageList [MFC], Replace
- CImageList [MFC], SetBkColor
- CImageList [MFC], SetDragCursorImage
- CImageList [MFC], SetImageCount
- CImageList [MFC], SetOverlayImage
- CImageList [MFC], Write
- CImageList [MFC], m_hImageList
ms.assetid: b6d1a704-1c82-4548-8a8f-77972adc98a5
ms.openlocfilehash: 28693aaa32ab5f4baaf773a7bac64c491d55cf78
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212403"
---
# <a name="cimagelist-class"></a>CImageList sınıfı

Windows ortak görüntü listesi denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CImageList : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CImageList:: CImageList](#cimagelist)|Bir `CImageList` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CImageList:: Add](#add)|Görüntü listesine bir resim veya resim ekler.|
|[CImageList:: Attach](#attach)|Bir nesne için bir görüntü listesi ekler `CImageList` .|
|[CImageList:: BeginDrag](#begindrag)|Bir görüntüyü sürüklemeye başlar.|
|[CImageList:: Copy](#copy)|Bir nesne içindeki bir görüntüyü kopyalar `CImageList` .|
|[CImageList:: Create](#create)|Bir görüntü listesini başlatır ve bir `CImageList` nesneye ekler.|
|[CImageList::D Eleteımagelist](#deleteimagelist)|Bir görüntü listesini siler.|
|[CImageList::D eleteTempMap](#deletetempmap)|Tarafından oluşturulan geçici nesneleri silmek için [CWinApp](../../mfc/reference/cwinapp-class.md) boşta kalma süresi işleyicisi tarafından çağırılır `CImageList` `FromHandle` .|
|[CImageList::D etach](#detach)|Bir görüntü listesi nesnesini bir nesneden ayırır `CImageList` ve bir görüntü listesine bir tanıtıcı döndürür.|
|[CImageList::D Oygenter](#dragenter)|Sürükleme işlemi sırasında güncelleştirmeleri kilitler ve sürükle görüntüsünü belirtilen konumda görüntüler.|
|[CImageList::D ragLeave](#dragleave)|Pencerenin kilidini açar ve pencere güncelleştirileyebilmesi için sürükle resmini gizler.|
|[CImageList::D ragMove](#dragmove)|Sürükle ve bırak işlemi sırasında sürüklediğiniz resmi taşıdır.|
|[CImageList::D ragShowNolock](#dragshownolock)|Pencereyi kilitlemeden sürükleme işlemi sırasında sürükle resmini gösterir veya gizler.|
|[CImageList::D RAW](#draw)|Sürükle ve bırak işlemi sırasında sürüklediğiniz görüntüyü çizer.|
|[CImageList::D rawEx](#drawex)|Belirtilen cihaz bağlamına bir resim listesi öğesi çizer. İşlevi belirtilen çizim stilini kullanır ve görüntüyü belirtilen renkle karıştırır.|
|[CImageList::D Rampadıwindirect](#drawindirect)|Görüntü listesinden bir resim çizer.|
|[CImageList:: EndDrag](#enddrag)|Bir sürükleme işlemini sonlandırır.|
|[CImageList:: ExtractIcon](#extracticon)|Görüntü listesindeki bir görüntüye ve maskeye dayalı bir simge oluşturur.|
|[CImageList:: FromHandle](#fromhandle)|`CImageList`Görüntü listesine bir tanıtıcı verildiğinde nesnenin işaretçisini döndürür. Bir `CImageList` nesne tutamaya iliştirilmişse, geçici bir `CImageList` nesne oluşturulur ve eklenir.|
|[CImageList:: Fromhandlekalıcı](#fromhandlepermanent)|`CImageList`Görüntü listesine bir tanıtıcı verildiğinde nesnenin işaretçisini döndürür. Bir `CImageList` nesne tutamaya ILIŞTIRILMEZSE null döndürülür.|
|[CImageList:: GetBkColor](#getbkcolor)|Bir görüntü listesi için geçerli arka plan rengini alır.|
|[CImageList:: GetDragImage](#getdragimage)|Sürükleme için kullanılan geçici görüntü listesini alır.|
|[CImageList:: GetImageCount](#getimagecount)|Bir görüntü listesindeki görüntü sayısını alır.|
|[CImageList:: GetImageInfo](#getimageinfo)|Bir görüntüyle ilgili bilgileri alır.|
|[CImageList:: GetSafeHandle](#getsafehandle)|Alır `m_hImageList` .|
|[CImageList:: Read](#read)|Bir arşivden görüntü listesini okur.|
|[CImageList:: Remove](#remove)|Görüntü listesinden bir görüntüyü kaldırır.|
|[CImageList:: Replace](#replace)|Görüntü listesindeki bir görüntüyü yeni bir görüntüyle değiştirir.|
|[CImageList:: SetBkColor](#setbkcolor)|Bir görüntü listesi için arka plan rengini ayarlar.|
|[CImageList:: SetDragCursorImage](#setdragcursorimage)|Yeni bir sürükleme görüntüsü oluşturur.|
|[CImageList:: SetImageCount](#setimagecount)|Bir görüntü listesindeki görüntü sayısını sıfırlar.|
|[CImageList:: SetOverlayImage](#setoverlayimage)|Görüntünün sıfır tabanlı dizinini, kaplama maskeleri olarak kullanılacak görüntü listesine ekler.|
|[CImageList:: Write](#write)|Bir arşive görüntü listesi yazar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CImageList:: operator HıMAGELIST](#operator_himagelist)|Öğesine eklenen HıMAGELIST 'i döndürür `CImageList` .|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CImageList:: m_hImageList](#m_himagelist)|Bu nesneye eklenen görüntü listesini içeren bir tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

"Görüntü listesi", her biri sıfır tabanlı dizin tarafından başvurulabilen, aynı boyutlu görüntülerin bir koleksiyonudur. Görüntü listeleri, büyük simge veya bit eşlem kümelerini verimli bir şekilde yönetmek için kullanılır. Bir görüntü listesindeki tüm görüntüler, ekran aygıtı biçiminde tek ve geniş bir bit eşlem içinde yer alır. Görüntü listesi, görüntüleri saydam olarak çizmek için kullanılan maskeleri içeren tek renkli bir bit eşlem de içerebilir (simge stili). Microsoft Win32 uygulama programlama arabirimi (API), görüntü çizmenizi, görüntü listeleri oluşturmanıza ve yok, görüntü ekleyip kaldırmanıza, görüntülerin değiştirilmesini, görüntüleri birleştirmeye ve görüntüleri sürüklemeye olanak sağlayan görüntü listesi işlevleri sağlar.

Bu denetim (ve bu nedenle `CImageList` sınıfı) yalnızca windows 95/98 ve WINDOWS NT sürüm 3,51 ve üzeri sürümlerde çalışan programlar için kullanılabilir.

Kullanma hakkında daha fazla bilgi için `CImageList` bkz. [denetimler](../../mfc/controls-mfc.md) ve [CImageList kullanma](../../mfc/using-cimagelist.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CImageList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

## <a name="cimagelistadd"></a><a name="add"></a>CImageList:: Add

Bir görüntü listesine bir veya daha fazla görüntü ya da simge eklemek için bu işlevi çağırın.

```
int Add(
    CBitmap* pbmImage,
    CBitmap* pbmMask);

int Add(
    CBitmap* pbmImage,
    COLORREF crMask);

int Add(HICON hIcon);
```

### <a name="parameters"></a>Parametreler

*Pbmımage*<br/>
Görüntüyü veya görüntüleri içeren bit eşlem işaretçisi. Görüntünün sayısı, bit eşlemin genişliğinden itibaren belirlenir.

*pbmMask*<br/>
Maskeyi içeren bit eşlem işaretçisi. Görüntü listesi ile hiçbir maske kullanılmazsa, bu parametre yoksayılır.

*crMask*<br/>
Maskeyi oluşturmak için kullanılan renk. Verilen bit eşlemdeki bu rengin her pikseli siyah olarak değişir ve maskede karşılık gelen bit bir olarak ayarlanır.

*HICON*<br/>
Yeni görüntünün bit eşlemini ve maskesini içeren simgenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa ilk yeni görüntünün sıfır tabanlı dizini; Aksi takdirde-1.

### <a name="remarks"></a>Açıklamalar

İşiniz bittiğinde simge tutamacını serbest bırakmaktan siz sorumlusunuz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#1](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]

## <a name="cimagelistattach"></a><a name="attach"></a>CImageList:: Attach

Bir nesneye görüntü listesi eklemek için bu işlevi çağırın `CImageList` .

```
BOOL Attach(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Parametreler

*hImageList*<br/>
Görüntü listesi nesnesine yönelik bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Ek başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#2](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]

## <a name="cimagelistbegindrag"></a><a name="begindrag"></a>CImageList:: BeginDrag

Bir görüntüyü sürüklemeye başlamak için bu işlevi çağırın.

```
BOOL BeginDrag(
    int nImage,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>Parametreler

*Ngörüntü*<br/>
Sürüklediğiniz görüntünün sıfır tabanlı dizini.

*Pthotleke*<br/>
Başlangıç sürükleme konumunun koordinatları (genellikle imleç konumu). Koordinatlar görüntünün sol üst köşesine göre değişir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, sürüklemek için kullanılan geçici bir görüntü listesi oluşturur. Görüntü, belirtilen görüntüyü ve maskesini geçerli imleç ile birleştirir. Sonraki WM_MOUSEMOVE iletilerine yanıt olarak, üye işlevini kullanarak sürükleme görüntüsünü taşıyabilirsiniz `DragMove` . Sürükleme işlemini sonlandırmak için `EndDrag` üye işlevini kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#3](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]

## <a name="cimagelistcimagelist"></a><a name="cimagelist"></a>CImageList:: CImageList

Bir `CImageList` nesnesi oluşturur.

```
CImageList();
```

## <a name="cimagelistcopy"></a><a name="copy"></a>CImageList:: Copy

Bu üye işlevi, Windows SDK açıklanan [ImageList_Copy](/windows/win32/api/commctrl/nf-commctrl-imagelist_copy)Win32 işlevinin davranışını uygular.

```
BOOL Copy(
    int iDst,
    int iSrc,
    UINT uFlags = ILCF_MOVE);

BOOL Copy(
    int iDst,
    CImageList* pSrc,
    int iSrc,
    UINT uFlags = ILCF_MOVE);
```

### <a name="parameters"></a>Parametreler

*ıdst*<br/>
Kopyalama işleminin hedefi olarak kullanılacak görüntünün sıfır tabanlı dizini.

*iSrc*<br/>
Kopyalama işleminin kaynağı olarak kullanılacak görüntünün sıfır tabanlı dizini.

*uFlags*<br/>
Yapılacak kopyalama işleminin türünü belirten bit bayrak değeri. Bu parametre aşağıdaki değerlerden biri olabilir:

|Değer|Anlamı|
|-----------|-------------|
|ILCF_MOVE|Kaynak görüntü, hedef görüntünün dizinine kopyalanır. Bu işlem belirli bir görüntünün birden fazla örneğine neden olur. ILCF_MOVE varsayılandır.|
|ILCF_SWAP|Kaynak ve hedef görüntüleri Exchange görüntü listesi içinde konumlandırır.|

*pSrc*<br/>
`CImageList`Kopyalama işleminin hedefi olan nesneye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#6](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]

## <a name="cimagelistcreate"></a><a name="create"></a>CImageList:: Create

Bir görüntü listesini başlatır ve onu bir [CImageList](../../mfc/reference/cimagelist-class.md) nesnesine ekler.

```
BOOL Create(
    int cx,
    int cy,
    UINT nFlags,
    int nInitial,
    int nGrow);

BOOL Create(
    UINT nBitmapID,
    int cx,
    int nGrow,
    COLORREF crMask);

BOOL Create(
    LPCTSTR lpszBitmapID,
    int cx,
    int nGrow,
    COLORREF crMask);

BOOL Create(
    CImageList& imagelist1,
    int nImage1,
    CImageList& imagelist2,
    int nImage2,
    int dx,
    int dy);

BOOL Create(CImageList* pImageList);
```

### <a name="parameters"></a>Parametreler

*yazmaç*<br/>
Her resmin piksel cinsinden boyutları.

*lı*<br/>
Her resmin piksel cinsinden boyutları.

*nFlags*<br/>
Oluşturulacak görüntü listesinin türünü belirtir. Bu parametre aşağıdaki değerlerin bir birleşimi olabilir, ancak değerlerden yalnızca birini içerebilir `ILC_COLOR` .

|Değer|Anlamı|
|-----------|-------------|
|ILC_COLOR|Diğer ILC_COLOR * bayraklarının Hiçbiri belirtilmediyse, varsayılan davranışı kullanın. Genellikle, varsayılan ILC_COLOR4; Ancak, daha eski görüntü sürücüleri için varsayılan değer ILC_COLORDDB.|
|ILC_COLOR4|Görüntü listesi için bit eşlem olarak 4 bit (16 renk) cihazdan bağımsız bit eşlem (DIB) bölümü kullanın.|
|ILC_COLOR8|8 bit DIB bölümü kullanın. Renk tablosu için kullanılan renkler, yarı ton paletle aynı renklerdir.|
|ILC_COLOR16|16 bit (32/64K renk) DIB bölümü kullanın.|
|ILC_COLOR24|24 bit DIB bölümü kullanın.|
|ILC_COLOR32|32 bitlik bir DIB bölümü kullanın.|
|ILC_COLORDDB|Cihaza bağımlı bir bit eşlem kullanın.|
|ILC_MASK|Bir maske kullanır. Görüntü listesi, biri maske olarak kullanılan tek renkli bir bit eşlem olan iki bit eşlem içerir. Bu değer dahil değilse, görüntü listesi yalnızca bir bit eşlem içerir. Maskelenmiş görüntüler hakkında ek bilgi için bkz. [görüntü listesinden resim çizme](../../mfc/drawing-images-from-an-image-list.md) .|

*Nınitial*<br/>
Başlangıçta görüntü listesinin içerdiği görüntü sayısı.

*nGrow*<br/>
Yeni görüntüler için yer açmak üzere sistemin listeyi yeniden boyutlandırması gerektiğinde resim listesinin büyüyebileceği görüntü sayısı. Bu parametre, yeniden boyutlandırılan görüntü listesinin içerebileceği yeni görüntü sayısını temsil eder.

*Nbitmapıd*<br/>
Görüntü listesiyle ilişkilendirilecek bit eşlemin kaynak kimlikleri.

*crMask*<br/>
Maske oluşturmak için kullanılan renk. Belirtilen bit eşlemdeki bu rengin her bir pikseli siyah olarak değiştirilir ve maskede karşılık gelen bit bir olarak ayarlanır.

*lpszBitmapID*<br/>
Görüntülerin kaynak kimliklerini içeren bir dize.

*imagelist1*<br/>
Bir `CImageList` nesneye başvuru.

*nImage1*<br/>
İlk var olan görüntünün dizini.

*imagelist2*<br/>
Bir `CImageList` nesneye başvuru.

*nImage2*<br/>
İkinci var olan görüntünün dizini.

*DX*<br/>
İlk görüntüyle ilişkili ikinci görüntünün x ekseninin piksel cinsinden boşluğu.

*rengi*<br/>
İlk görüntüyle ilişkili ikinci görüntünün y ekseninin piksel cinsinden boşluğu.

*pImageList*<br/>
Bir `CImageList` nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CImageList`İki adımda oluşturursunuz. İlk olarak, oluşturucuyu çağırın ve sonra `Create` , görüntü listesini oluşturan ve bunu nesnesine ekleyen çağırın `CImageList` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#7](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]

## <a name="cimagelistdeleteimagelist"></a><a name="deleteimagelist"></a>CImageList::D Eleteımagelist

Bir görüntü listesini silmek için bu işlevi çağırın.

```
BOOL DeleteImageList();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#8](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]

## <a name="cimagelistdeletetempmap"></a><a name="deletetempmap"></a>CImageList::D eleteTempMap

`CWinApp`Boşta kalma süresi işleyicisi tarafından otomatik olarak çağrıldığında, `DeleteTempMap` `CImageList` [FromHandle](#fromhandle)tarafından oluşturulan geçici nesneleri siler, ancak nesnelerle ilişkili herhangi bir tanıtıcıyı ( `hImageList` ) `ImageList` yok etmez.

```
static void PASCAL DeleteTempMap();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#9](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]

## <a name="cimagelistdetach"></a><a name="detach"></a>CImageList::D etach

Bir görüntü listesi nesnesini bir nesneden ayırmak için bu işlevi çağırın `CImageList` .

```
HIMAGELIST Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Görüntü listesi nesnesine yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, görüntü listesi nesnesine bir tanıtıcı döndürür.

### <a name="example"></a>Örnek

  [CImageList:: Attach](#attach)örneğine bakın.

## <a name="cimagelistdragenter"></a><a name="dragenter"></a>CImageList::D Oygenter

Bir sürükleme işlemi sırasında, güncelleştirmeleri *pWndLock* tarafından belirtilen pencerede kilitler ve sürükle resmini *işaret*tarafından belirtilen konumda görüntüler.

```
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pWndLock*<br/>
Sürükleme resminin sahibi olan pencerenin işaretçisi.

*seçeneğinin*<br/>
Sürükleme resminin görüntüleneceği konum. Koordinatlar pencerenin sol üst köşesine (istemci alanı değil) göre değişir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Koordinatlar pencerenin sol üst köşesine görelidir. bu nedenle, koordinatları belirtirken kenarlık, başlık çubuğu ve menü çubuğu gibi pencere öğelerinin genişliklerini telafi etmeniz gerekir.

*PWndLock* null ise, bu işlev görüntüyü masaüstü penceresiyle ilişkili görüntüleme bağlamına çizer ve koordinatlar ekranın sol üst köşesine göre belirlenir.

Bu işlev, sürükleme işlemi sırasında verilen penceredeki diğer tüm güncelleştirmeleri kilitler. Bir sürükleme işlemi sırasında bir sürükle ve bırak işleminin hedefini vurgulama gibi herhangi bir çizim yapmanız gerekiyorsa, ' nin, ' yi, [CImageList::D ragLeave](#dragleave) işlevini kullanarak geçici olarak gizleyebilirsiniz.

### <a name="example"></a>Örnek

  [CImageList:: BeginDrag](#begindrag)örneğine bakın.

## <a name="cimagelistdragleave"></a><a name="dragleave"></a>CImageList::D ragLeave

*PWndLock* tarafından belirtilen pencerenin kilidini açar ve sürükleme görüntüsünü gizler ve pencerenin güncelleştirilmesine izin verir.

```
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```

### <a name="parameters"></a>Parametreler

*pWndLock*<br/>
Sürükleme resminin sahibi olan pencerenin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

  [CImageList:: EndDrag](#enddrag)örneğine bakın.

## <a name="cimagelistdragmove"></a><a name="dragmove"></a>CImageList::D ragMove

Sürükle ve bırak işlemi sırasında sürüklediğiniz görüntüyü taşımak için bu işlevi çağırın.

```
static BOOL PASCAL DragMove(CPoint pt);
```

### <a name="parameters"></a>Parametreler

*yönergelerinin*<br/>
Yeni sürükleme konumu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle WM_MOUSEMOVE iletisine yanıt olarak çağırılır. Bir sürükleme işlemine başlamak için `BeginDrag` üye işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#4](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]

## <a name="cimagelistdragshownolock"></a><a name="dragshownolock"></a>CImageList::D ragShowNolock

Pencereyi kilitlemeden sürükleme işlemi sırasında sürükle resmini gösterir veya gizler.

```
static BOOL PASCAL DragShowNolock(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bShow*<br/>
Sürükleme resminin gösterilip gösterilmeyeceğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[CImageList::D Oygenter](#dragenter) işlevi, bir sürükleme işlemi sırasında penceredeki tüm güncelleştirmeleri kilitler. Ancak bu işlev, pencereyi kilitlemez.

## <a name="cimagelistdraw"></a><a name="draw"></a>CImageList::D RAW

Sürükle ve bırak işlemi sırasında sürüklediğiniz görüntüyü çizmek için bu işlevi çağırın.

```
BOOL Draw(
    CDC* pDC,
    int nImage,
    POINT pt,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Hedef cihaz bağlamına yönelik işaretçi.

*Ngörüntü*<br/>
Çizilecek görüntünün sıfır tabanlı dizini.

*yönergelerinin*<br/>
Belirtilen cihaz bağlamı içinde çizilecek konum.

*nStyle*<br/>
Çizim stilini belirten bayrak. Bu değerlerden biri veya daha fazlası olabilir:

|Değer|Anlamı|
|-----------|-------------|
|ILD_BLEND25, ILD_FOCUS|Görüntüyü, sistem vurgu rengiyle yüzde 25 ' i karıştırarak çizer. Görüntü listesi bir maske içermiyorsa, bu değerin etkisi yoktur.|
|ILD_BLEND50, ILD_SELECTED, ILD_BLEND|Görüntüyü, sistem vurgu rengi ile yüzde 50 karıştırma halinde çizer. Görüntü listesi bir maske içermiyorsa, bu değerin etkisi yoktur.|
|ILD_MASK|Maskeyi çizer.|
|ILD_NORMAL|Görüntü listesi için arka plan rengini kullanarak görüntüyü çizer. Arka plan rengi CLR_NONE değer ise, görüntü maske kullanılarak saydam olarak çizilir.|
|ILD_TRANSPARENT|Arka plan renginden bağımsız olarak maskeyi kullanarak görüntüyü saydam şekilde çizer.|

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

  [CImageList:: SetOverlayImage](#setoverlayimage)örneğine bakın.

## <a name="cimagelistdrawex"></a><a name="drawex"></a>CImageList::D rawEx

Belirtilen cihaz bağlamına bir resim listesi öğesi çizer.

```
BOOL DrawEx(
    CDC* pDC,
    int nImage,
    POINT pt,
    SIZE sz,
    COLORREF clrBk,
    COLORREF clrFg,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Hedef cihaz bağlamına yönelik işaretçi.

*Ngörüntü*<br/>
Çizilecek görüntünün sıfır tabanlı dizini.

*yönergelerinin*<br/>
Belirtilen cihaz bağlamı içinde çizilecek konum.

*SZ*<br/>
Görüntünün görüntünün sol üst köşesine göre çizilecek bölümünün boyutu. Windows SDK [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) *DX* ve *DY* ' i inceleyin.

*clrBk*<br/>
Görüntünün arka plan rengi. Windows SDK [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) *rgbbk* bölümüne bakın.

*clrFg*<br/>
Görüntünün ön plan rengi. Windows SDK [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) *rgbfg* bölümüne bakın.

*nStyle*<br/>
Çizim stilini belirten bayrak. Windows SDK [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) *fStyle* bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İşlevi belirtilen çizim stilini kullanır ve görüntüyü belirtilen renkle karıştırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#10](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]

## <a name="cimagelistdrawindirect"></a><a name="drawindirect"></a>CImageList::D Rampadıwindirect

Görüntü listesinden bir resim çizmek için bu üye işlevini çağırın.

```
BOOL DrawIndirect(IMAGELISTDRAWPARAMS* pimldp);

BOOL DrawIndirect(
    CDC* pDC,
    int nImage,
    POINT pt,
    SIZE sz,
    POINT ptOrigin,
    UINT fStyle = ILD_NORMAL,
    DWORD dwRop = SRCCOPY,
    COLORREF rgbBack = CLR_DEFAULT,
    COLORREF rgbFore = CLR_DEFAULT,
    DWORD fState = ILS_NORMAL,
    DWORD Frame = 0,
    COLORREF crEffect = CLR_DEFAULT);
```

### <a name="parameters"></a>Parametreler

*pımldp*<br/>
Çizim işlemi hakkında bilgi içeren bir [IMAGELISTDRAWPARAMS](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams) yapısına yönelik işaretçi.

*Kökündeki*<br/>
Hedef cihaz bağlamına yönelik bir işaretçi. İşiniz bittiğinde bu [CDC](../../mfc/reference/cdc-class.md) nesnesini silmeniz gerekir.

*Ngörüntü*<br/>
Çizilecek görüntünün sıfır tabanlı dizini.

*yönergelerinin*<br/>
Görüntünün çizildiği x ve y koordinatlarını içeren bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı.

*SZ*<br/>
Çizilecek görüntünün boyutunu gösteren bir [Boyut](/windows/win32/api/windef/ns-windef-size) yapısı.

*Ptorgın*<br/>
Görüntünün kendisiyle ilgili olarak çizim işleminin sol üst köşesini belirten x ve y koordinatlarını içeren bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı. X koordinatının solunda ve y koordinatı üzerinde bulunan görüntünün pikselleri çizilmez.

*fStyle*<br/>
Çizim stilini ve isteğe bağlı olarak, kaplama görüntüsünü belirten bayrak. Kaplama görüntüsü hakkında bilgi için açıklamalar bölümüne bakın. MFC varsayılan uygulamasının ILD_NORMAL, görüntü listesi için arka plan rengini kullanarak görüntüyü çizer. Arka plan rengi CLR_NONE değer ise, görüntü bir maske kullanılarak saydam olarak çizilir.

Diğer olası stiller [IMAGELISTDRAWPARAMS](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams) yapısının *fStyle* üyesi altında açıklanmıştır.

*dwRop*<br/>
Raster işlem kodunu belirten değer. Bu kodlar, kaynak dikdörtgenin renk verilerinin, son renge ulaşmak için hedef dikdörtgenin renk verileriyle nasıl birleştirileceğini tanımlar. MFC 'nin varsayılan uygulamasının SRCCOPY, kaynak dikdörtgeni doğrudan hedef dikdörtgene kopyalar. *FStyle* parametresi ILD_ROP bayrağını içermiyorsa, bu parametre yoksayılır.

Diğer olası değerler [IMAGELISTDRAWPARAMS](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams) yapısının *dwRop* üyesi altında açıklanmıştır.

*rgbBack*<br/>
Görüntünün arka plan rengi, varsayılan CLR_DEFAULT. Bu parametre, uygulama tanımlı bir RGB değeri veya aşağıdaki değerlerden biri olabilir:

|Değer|Anlamı|
|-----------|-------------|
|CLR_DEFAULT|Varsayılan arka plan rengi. Görüntü, görüntü listesi arka plan rengi kullanılarak çizilir.|
|CLR_NONE|Arka plan rengi yok. Görüntü saydam olarak çizilir.|

*Rgbön*<br/>
Varsayılan CLR_DEFAULT görüntü ön plan rengi. Bu parametre, uygulama tanımlı bir RGB değeri veya aşağıdaki değerlerden biri olabilir:

|Değer|Anlamı|
|-----------|-------------|
|CLR_DEFAULT|Varsayılan ön plan rengi. Görüntü, ön plan rengi olarak sistem vurgu rengi kullanılarak çizilir.|
|CLR_NONE|Blend rengi yok. Görüntü, hedef cihaz bağlamının rengi ile karıştırkaydedilir.|

Bu parametre yalnızca *fStyle* ILD_BLEND25 veya ILD_BLEND50 bayrağını içeriyorsa kullanılır.

*fState*<br/>
Çizim durumunu belirten bayrak. Bu üye, bir veya daha fazla görüntü listesi durumu bayrağı içerebilir.

*Çerçeve*<br/>
, Doygunluğu Azalt ve alfa karıştırma efektlerinin davranışını etkiler.

ILS_SATURATE ile kullanıldığında, bu üye simgenin her bir pikselinin her bir renk bileşenine eklenen değeri tutar.

ILS_APLHA ile kullanıldığında, bu üye Alfa kanalının değerini tutar. Bu değer 0 ile 255 arasında, 0 tamamen şeffaf ve 255 tamamen donuk olabilir.

*crEffect*<br/>
Parlama ve gölge etkileri için kullanılan [colorref](/windows/win32/gdi/colorref) değeri.

### <a name="return-value"></a>Dönüş Değeri

Görüntü başarıyla çizildiyse doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Win32 yapısını kendiniz doldurmanız istiyorsanız ilk sürümü kullanın. Bir veya daha fazla MFC 'nin varsayılan bağımsız değişkenlerinden yararlanmak istiyorsanız ikinci sürümü kullanın veya yapının yönetilmesini önleyin.

Bir kaplama görüntüsü, bu üye işlevinde *nImage* parametresi tarafından belirtilen birincil görüntünün üzerine çizilen bir görüntüdür. [INDEXTOOVERLAYMASK](/windows/win32/api/commctrl/nf-commctrl-indextooverlaymask) makrosu kullanılarak belirtilen yer paylaşımı maskesinin tek tabanlı diziniyle [Çiz](#draw) üye işlevini kullanarak bir kaplama maskesi çizin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#11](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]

## <a name="cimagelistenddrag"></a><a name="enddrag"></a>CImageList:: EndDrag

Bir sürükleme işlemini sonlandırmak için bu işlevi çağırın.

```
static void PASCAL EndDrag();
```

### <a name="remarks"></a>Açıklamalar

Bir sürükleme işlemine başlamak için `BeginDrag` üye işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#5](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]

## <a name="cimagelistextracticon"></a><a name="extracticon"></a>CImageList:: ExtractIcon

Görüntü listesinde bir görüntüye ve ilgili maskeye dayalı bir simge oluşturmak için bu işlevi çağırın.

```
HICON ExtractIcon(int nImage);
```

### <a name="parameters"></a>Parametreler

*Ngörüntü*<br/>
Görüntünün sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simgenin tutamacı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, simgeyi oluşturmak için [ImageList_ExtractIcon](/windows/win32/api/commctrl/nf-commctrl-imagelist_extracticon) makrosunun davranışını kullanır. Simge oluşturma ve temizleme hakkında daha fazla bilgi için [ImageList_ExtractIcon](/windows/win32/api/commctrl/nf-commctrl-imagelist_extracticon) makroya bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#12](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]

## <a name="cimagelistfromhandle"></a><a name="fromhandle"></a>CImageList:: FromHandle

`CImageList`Görüntü listesine bir tanıtıcı verildiğinde nesnenin işaretçisini döndürür.

```
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Parametreler

*hImageList*<br/>
Görüntü listesini belirtir.

### <a name="return-value"></a>Dönüş Değeri

`CImageList`Başarılı olursa nesne için bir işaretçi; aksi takdırde null.

### <a name="remarks"></a>Açıklamalar

Zaten bir `CImageList` tanıtıcıya ekli değilse, geçici bir `CImageList` nesne oluşturulur ve eklenir. Bu geçici `CImageList` nesne yalnızca, uygulamanın olay döngüsünde süresi bir sonraki sefer, tüm geçici nesneler silindiği zaman geçerli olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#13](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]

## <a name="cimagelistfromhandlepermanent"></a><a name="fromhandlepermanent"></a>CImageList:: Fromhandlekalıcı

`CImageList`Görüntü listesine bir tanıtıcı verildiğinde nesnenin işaretçisini döndürür.

```
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Parametreler

*hImageList*<br/>
Görüntü listesini belirtir.

### <a name="return-value"></a>Dönüş Değeri

`CImageList`Başarılı olursa nesne için bir işaretçi; aksi takdırde null.

### <a name="remarks"></a>Açıklamalar

Bir `CImageList` nesne tutamaya ILIŞTIRILMEZSE null döndürülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#14](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]

## <a name="cimagelistgetbkcolor"></a><a name="getbkcolor"></a>CImageList:: GetBkColor

Bir görüntü listesinin geçerli arka plan rengini almak için bu işlevi çağırın.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CImageList`Nesne arka plan RENGININ RGB renk değeri.

### <a name="example"></a>Örnek

  [CImageList:: SetBkColor](#setbkcolor)örneğine bakın.

## <a name="cimagelistgetdragimage"></a><a name="getdragimage"></a>CImageList:: GetDragImage

Sürükleme için kullanılan geçici görüntü listesini alır.

```
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,
    LPPOINT lpPointHotSpot);
```

### <a name="parameters"></a>Parametreler

*Lppoınt*<br/>
Geçerli sürükleme konumunu alan bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısının adresi.

*Lppointhotleke*<br/>
Sürükleme `POINT` konumuna göre sürükleme resminin sapmasını alan bir yapının adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, sürükleme için kullanılan geçici görüntü listesine yönelik bir işaretçi; Aksi takdirde, NULL.

## <a name="cimagelistgetimagecount"></a><a name="getimagecount"></a>CImageList:: GetImageCount

Bir görüntü listesindeki görüntü sayısını almak için bu işlevi çağırın.

```
int GetImageCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görüntü sayısı.

### <a name="example"></a>Örnek

  [CImageList:: ExtractIcon](#extracticon)için örneğe bakın.

## <a name="cimagelistgetimageinfo"></a><a name="getimageinfo"></a>CImageList:: GetImageInfo

Bir görüntüyle ilgili bilgi almak için bu işlevi çağırın.

```
BOOL GetImageInfo(
    int nImage,
    IMAGEINFO* pImageInfo) const;
```

### <a name="parameters"></a>Parametreler

*Ngörüntü*<br/>
Görüntünün sıfır tabanlı dizini.

*Pımageınfo*<br/>
Görüntüyle ilgili bilgi alan bir [IMAGEINFO](/windows/win32/api/commctrl/ns-commctrl-imageinfo) yapısına yönelik işaretçi. Bu yapıdaki bilgiler, görüntünün bit eşlemlerini doğrudan işlemek için kullanılabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`IMAGEINFO`Yapı, bir görüntü listesindeki bir görüntüyle ilgili bilgiler içerir.

## <a name="cimagelistgetsafehandle"></a><a name="getsafehandle"></a>CImageList:: GetSafeHandle

Veri üyesini almak için bu işlevi çağırın `m_hImageList` .

```
HIMAGELIST GetSafeHandle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eklenen görüntü listesine yönelik bir tanıtıcı; Aksi takdirde, hiçbir nesne iliştirilmişse NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#15](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]

## <a name="cimagelistm_himagelist"></a><a name="m_himagelist"></a>CImageList:: m_hImageList

Bu nesneye eklenen görüntü listesinin bir tutamacı.

`HIMAGELIST m_hImageList;`

### <a name="remarks"></a>Açıklamalar

`m_hImageList`Veri ÜYESI HıMAGELIST türünde ortak bir değişkendir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#23](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]

## <a name="cimagelistoperator-himagelist"></a><a name="operator_himagelist"></a>CImageList:: operator HıMAGELIST

Nesnenin ekli tanıtıcısını almak için bu işleci kullanın `CImageList` .

```
operator HIMAGELIST() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, nesne tarafından temsil edilen görüntü listesine yönelik bir tanıtıcı `CImageList` ; aksi takdırde null.

### <a name="remarks"></a>Açıklamalar

Bu işleç, bir HıMAGELIST nesnesinin doğrudan kullanımını destekleyen bir atama işleçtir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#16](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]

## <a name="cimagelistread"></a><a name="read"></a>CImageList:: Read

Bir arşivden bir görüntü listesi okumak için bu işlevi çağırın.

```
BOOL Read(CArchive* pArchive);
```

### <a name="parameters"></a>Parametreler

*pArchive*<br/>
`CArchive`Görüntü listesinin okunacağı nesne için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#18](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]

## <a name="cimagelistremove"></a><a name="remove"></a>CImageList:: Remove

Görüntü listesi nesnesinden bir görüntüyü kaldırmak için bu işlevi çağırın.

```
BOOL Remove(int nImage);
```

### <a name="parameters"></a>Parametreler

*Ngörüntü*<br/>
Kaldırılacak görüntünün sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*NImage* izleyen tüm öğeler şimdi bir konum aşağı taşınır. Örneğin, bir görüntü listesi iki öğe içeriyorsa, ilk öğeyi silmek kalan öğenin artık ilk konumda olmasına neden olur. ilk konumdaki öğe için *Nimage*= 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#19](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]

## <a name="cimagelistreplace"></a><a name="replace"></a>CImageList:: Replace

Görüntü listesindeki bir görüntüyü yeni bir görüntüyle değiştirmek için bu işlevi çağırın.

```
BOOL Replace(
    int nImage,
    CBitmap* pbmImage,
    CBitmap* pbmMask);

int Replace(
    int nImage,
    HICON hIcon);
```

### <a name="parameters"></a>Parametreler

*Ngörüntü*<br/>
Değiştirilecek görüntünün sıfır tabanlı dizini.

*Pbmımage*<br/>
Görüntünün bulunduğu bit eşlem işaretçisi.

*pbmMask*<br/>
Maskeyi içeren bit eşlem işaretçisi. Görüntü listesi ile hiçbir maske kullanılmazsa, bu parametre yoksayılır.

*HICON*<br/>
Yeni görüntünün bit eşlemini ve maskesini içeren simgeye yönelik bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

BOOL döndüren sürüm, başarılıysa sıfır dışında bir değer döndürür; Aksi takdirde 0.

Döndürülen sürüm, **`int`** başarılı olursa görüntünün sıfır tabanlı dizinini döndürür; Aksi takdirde-1.

### <a name="remarks"></a>Açıklamalar

Yeni, geçerli görüntüleri yer tutucu görüntüsü dizin numaralarına atamak için [SetImageCount](#setimagecount) çağrıldıktan sonra bu üye işlevini çağırın.

### <a name="example"></a>Örnek

  [CImageList:: SetImageCount](#setimagecount)örneğine bakın.

## <a name="cimagelistsetbkcolor"></a><a name="setbkcolor"></a>CImageList:: SetBkColor

Bir görüntü listesinin arka plan rengini ayarlamak için bu işlevi çağırın.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>Parametreler

*Return*<br/>
Ayarlanacak arka plan rengi. CLR_NONE olabilir. Bu durumda, görüntüler maske kullanılarak saydam olarak çizilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa önceki arka plan rengi; Aksi takdirde CLR_NONE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#20](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]

## <a name="cimagelistsetdragcursorimage"></a><a name="setdragcursorimage"></a>CImageList:: SetDragCursorImage

Belirtilen görüntüyü (genellikle bir fare imleç görüntüsünü) geçerli sürükleme görüntüsüyle birleştirerek yeni bir sürükleme görüntüsü oluşturur.

```
BOOL SetDragCursorImage(
    int nDrag,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>Parametreler

*Nsürükle*<br/>
Sürükleme görüntüsüyle birleştirilecek yeni görüntünün dizini.

*Pthotleke*<br/>
Yeni görüntü içindeki etkin noktanın konumu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Sürükleme işlevleri bir sürükleme işlemi sırasında yeni görüntüyü kullandığından, çağrıldıktan sonra asıl fare imlecini gizlemek için Windows [ShowCursor](/windows/win32/api/winuser/nf-winuser-showcursor) işlevini kullanmanız gerekir `CImageList::SetDragCursorImage` . Aksi takdirde, sistem sürükleme işleminin süresi boyunca iki fare imleç gibi görünebilir.

## <a name="cimagelistsetimagecount"></a><a name="setimagecount"></a>CImageList:: SetImageCount

Bir nesnedeki görüntü sayısını sıfırlamak için bu üye işlevini çağırın `CImageList` .

```
BOOL SetImageCount(UINT uNewCount);
```

### <a name="parameters"></a>Parametreler

*uNewCount*<br/>
Görüntü listesindeki yeni toplam görüntü sayısını belirten değer.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Görüntü listesindeki görüntü sayısını artırmak için bu üye işlevi çağırırsanız, yeni dizinleri geçerli görüntülere atamak için her bir ek görüntünün [Değiştir](#replace) ' i çağırın. Dizinleri geçerli görüntülere atamadıysanız, yeni görüntüleri oluşturan çizim işlemleri öngörülemeyen olur.

Bu işlevi kullanarak bir görüntü listesinin boyutunu azaltırsanız, kesilen görüntüler serbest bırakılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#21](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]

## <a name="cimagelistsetoverlayimage"></a><a name="setoverlayimage"></a>CImageList:: SetOverlayImage

Görüntünün sıfır tabanlı dizinini, kaplama maskeleri olarak kullanılacak görüntü listesine eklemek için bu işlevi çağırın.

```
BOOL SetOverlayImage(
    int nImage,
    int nOverlay);
```

### <a name="parameters"></a>Parametreler

*Ngörüntü*<br/>
Bir kaplama maskesi olarak kullanılacak görüntünün sıfır tabanlı dizini.

*nOverlay*<br/>
Yer paylaşımı maskesinin tek tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Listeye kadar en fazla dört Dizin eklenebilir.

Bir kaplama maskesi, başka bir görüntünün üzerinde saydam olarak çizilen bir görüntüdür. INDEXTOOVERLAYMASK makrosu kullanılarak belirtilen yer paylaşımı maskesinin tek tabanlı diziniyle, [CImageList::D RAW](#draw) üye işlevini kullanarak bir görüntü üzerinden bir kaplama maskesi çizin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#22](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]

## <a name="cimagelistwrite"></a><a name="write"></a>CImageList:: Write

Bir arşive görüntü listesi nesnesi yazmak için bu işlevi çağırın.

```
BOOL Write(CArchive* pArchive);
```

### <a name="parameters"></a>Parametreler

*pArchive*<br/>
`CArchive`Görüntü listesinin depolanacağı nesneye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#17](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CListCtrl sınıfı](../../mfc/reference/clistctrl-class.md)<br/>
[CTabCtrl sınıfı](../../mfc/reference/ctabctrl-class.md)
