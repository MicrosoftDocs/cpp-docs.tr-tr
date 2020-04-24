---
title: CImageList Sınıfı
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
ms.openlocfilehash: 17cd2a94cb397e59e4622aea8ed7bb6fbe1eee43
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752690"
---
# <a name="cimagelist-class"></a>CImageList Sınıfı

Windows ortak resim listesi denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CImageList : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CImageList::CImageList](#cimagelist)|Bir `CImageList` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CImageList::Ekle](#add)|Resim listesine resim veya resim ekler.|
|[CImageList::Ekle](#attach)|Bir `CImageList` nesneye resim listesi bağlar.|
|[CImageList::BeginDrag](#begindrag)|Görüntüyü sürüklemeye başlar.|
|[CImageList::Kopyala](#copy)|Nesne içindeki `CImageList` görüntüyü kopyalar.|
|[CImageList::Oluştur](#create)|Bir görüntü listesini başharfe alarve bir `CImageList` nesneye bağlar.|
|[CImageList::DeleteImageList](#deleteimagelist)|Resim listesini siler.|
|[CImageList::DeleteTempMap](#deletetempmap)|[CWinApp](../../mfc/reference/cwinapp-class.md) boşta zaman işleyicisi tarafından `CImageList` `FromHandle`oluşturulan herhangi bir geçici nesneyi silmek için çağrılır.|
|[CImageList::Detach](#detach)|Görüntü listesi nesnesini bir `CImageList` nesneden ayırır ve bir tanıtıcıyı görüntü listesine döndürür.|
|[CImageList::DragEnter](#dragenter)|Sürükleme işlemi sırasında güncelleştirmeleri kilitler ve sürükleme görüntüsünü belirli bir konumda görüntüler.|
|[CImageList::DragYorum bırakın](#dragleave)|Pencerenin kilidini açar ve pencerenin güncelleştirilebilmeleri için sürükle görüntüsünü gizler.|
|[CImageList::DragTaşı](#dragmove)|Sürülve bırak işlemi sırasında sürüklenen görüntüyü taşır.|
|[CImageList::DragShowNolock](#dragshownolock)|Sürükleme işlemi sırasında sürükle görüntüsünü pencereyi kilitlemeden gösterir veya gizler.|
|[CImageList::Draw](#draw)|Sürükle ve bırak işlemi sırasında sürüklenen görüntüyü çizer.|
|[CImageList::DrawEx](#drawex)|Belirtilen aygıt bağlamında bir resim listesi öğesi çizer. İşlev belirtilen çizim stilini kullanır ve görüntüyü belirtilen renkle karıştırır.|
|[CImageList::DrawIndirect](#drawindirect)|Resim listesinden görüntü çizer.|
|[CImageList::EndDrag](#enddrag)|Sürükleme işlemini sona erdirer.|
|[CImageList::Extracticon](#extracticon)|Resim listesinde ki görüntü ve maskeyi temel alan bir simge oluşturur.|
|[CImageList::FromHandle](#fromhandle)|Görüntü listesine `CImageList` tutamacı verildiğinde işaretçiyi nesneye döndürür. Bir `CImageList` nesne tutamacına bağlı değilse, `CImageList` geçici bir nesne oluşturulur ve eklenir.|
|[CImageList::FromHandlePermanent](#fromhandlepermanent)|Görüntü listesine `CImageList` tutamacı verildiğinde işaretçiyi nesneye döndürür. Bir `CImageList` nesne tutamacına bağlı değilse, NULL döndürülür.|
|[CImageList::GetBkColor](#getbkcolor)|Resim listesi için geçerli arka plan rengini alır.|
|[CImageList::GetDragImage](#getdragimage)|Sürükleme için kullanılan geçici resim listesini alır.|
|[CImageList::GetImageCount](#getimagecount)|Resim listesindeki görüntü sayısını alır.|
|[CImageList::GetImageInfo](#getimageinfo)|Görüntü yle ilgili bilgileri alır.|
|[CImageList::GetSafeHandle](#getsafehandle)|`m_hImageList`Alır.|
|[CImageList::Oku](#read)|Arşivdeki resim listesini okur.|
|[CImageList::Kaldır](#remove)|Görüntüyü resim listesinden kaldırır.|
|[CImageList::Değiştir](#replace)|Resim listesindeki bir resmi yeni bir resimle değiştirir.|
|[CImageList::SetBkColor](#setbkcolor)|Resim listesiiçin arka plan rengini ayarlar.|
|[CImageList::SetDragCursorImage](#setdragcursorimage)|Yeni bir sürükleme görüntüsü oluşturur.|
|[CImageList::SetImageCount](#setimagecount)|Görüntü listesindeki görüntü sayısını sıfırlar.|
|[CImageList::SetOverlayImage](#setoverlayimage)|Bir görüntünün sıfır tabanlı dizinini, bindirme maskeleri olarak kullanılacak görüntüler listesine ekler.|
|[CImageList::Yaz](#write)|Arşive resim listesi yazar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CImageList::operatör HIMAGELIST](#operator_himagelist)|Ekli HIMAGELIST'i `CImageList`döndürür.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CImageList::m_hImageList](#m_himagelist)|Bu nesneye iliştirilen görüntü listesini içeren bir tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

"Resim listesi", her biri sıfır tabanlı dizintarafından atıfta bulunulabilen aynı boyuttaki görüntülerin bir koleksiyonudur. Resim listeleri, büyük simge kümelerini veya bit eşlemleri verimli bir şekilde yönetmek için kullanılır. Görüntü listesindeki tüm görüntüler, ekran aygıtı biçiminde tek ve geniş bir bit eşlemiçinde bulunur. Resim listesi, görüntüleri saydam olarak çizmek için kullanılan maskeleri içeren tek renkli bir bit eşlemi de içerebilir (simge stili). Microsoft Win32 uygulama programlama arabirimi (API), görüntü çizmenize, görüntü listeleri oluşturmanıza ve yok etmenizi, görüntüleri eklemenizi ve kaldırmanızı, görüntüleri değiştirmenizi, görüntüleri birleştirmenizi ve görüntüleri sürüklemenizi sağlayan görüntü listesi işlevleri sağlar.

Bu denetim (ve `CImageList` bu nedenle sınıf) yalnızca Windows 95/98 ve Windows NT sürüm 3.51 ve sonraki sürümler altında çalışan programlar için kullanılabilir.

Kullanma `CImageList`hakkında daha fazla bilgi için, [Bkz. Denetimler](../../mfc/controls-mfc.md) ve [CImageList kullanma.](../../mfc/using-cimagelist.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CImageList`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="cimagelistadd"></a><a name="add"></a>CImageList::Ekle

Bir veya daha fazla resim veya bir simgeyi bir resim listesine eklemek için bu işlevi arayın.

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

*pbmImage*<br/>
Görüntüyü veya görüntüleri içeren bit eşlenini işaretleyin. Görüntü sayısı bit eşlemi genişliğinden çıkarılır.

*pbmMask*<br/>
Maskeyi içeren bit eşlenini işaretleyin. Görüntü listesinde maske kullanılmazsa, bu parametre yoksayılır.

*crMask*<br/>
Maskeyi oluşturmak için kullanılan renk. Verilen bit eşönünde bu rengin her pikseli siyaha değiştirilir ve maskedeki karşılık gelen bit bir e göre ayarlanır.

*Hıcon*<br/>
Yeni görüntü için bit eşlemi ve maske içeren simgenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa ilk yeni görüntünün sıfır tabanlı dizin; aksi takdirde - 1.

### <a name="remarks"></a>Açıklamalar

Simge tutamacını, onunla yaptığınız iş bittiğinde serbest bırakmaksizin sorumlusunuz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#1](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]

## <a name="cimagelistattach"></a><a name="attach"></a>CImageList::Ekle

Bir `CImageList` nesneye görüntü listesi eklemek için bu işlevi çağırın.

```
BOOL Attach(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Parametreler

*hImageList*<br/>
Görüntü listesi nesnesine bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Eki başarılı olduysa sıfırolmayan; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#2](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]

## <a name="cimagelistbegindrag"></a><a name="begindrag"></a>CImageList::BeginDrag

Görüntüyü sürüklemeye başlamak için bu işlevi çağırın.

```
BOOL BeginDrag(
    int nImage,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>Parametreler

*nImage*<br/>
Sürüklemek için görüntünün sıfır tabanlı dizin.

*ptHotSpot*<br/>
Başlangıç sürükleme pozisyonunun koordinatları (genellikle imleç konumu). Koordinatlar görüntünün sol üst köşesine göredir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev sürükleme için kullanılan geçici bir görüntü listesi oluşturur. Görüntü, belirtilen görüntüyü ve maskesini geçerli imleçle birleştirir. Sonraki WM_MOUSEMOVE iletilerine yanıt olarak, `DragMove` üye işlevi kullanarak sürükle görüntüsünü taşıyabilirsiniz. Sürükleme işlemini sona erdirmek için `EndDrag` üye işlevi kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#3](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]

## <a name="cimagelistcimagelist"></a><a name="cimagelist"></a>CImageList::CImageList

Bir `CImageList` nesne inşa eder.

```
CImageList();
```

## <a name="cimagelistcopy"></a><a name="copy"></a>CImageList::Kopyala

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32 işlevinin ImageList_Copy](/windows/win32/api/commctrl/nf-commctrl-imagelist_copy)davranışını uygular.

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

*iDst*<br/>
Kopya işleminin hedefi olarak kullanılacak görüntünün sıfır tabanlı dizini.

*iSrc*<br/>
Kopya işleminin kaynağı olarak kullanılacak görüntünün sıfır tabanlı dizini.

*uBayraklar*<br/>
Yapılacak kopyalama işleminin türünü belirten bit bayrak değeri. Bu parametre aşağıdaki değerlerden biri olabilir:

|Değer|Anlamı|
|-----------|-------------|
|ILCF_MOVE|Kaynak görüntü hedef görüntünün dizinine kopyalanır. Bu işlem, belirli bir görüntünün birden çok örneğiyle sonuçlanır. ILCF_MOVE varsayılandır.|
|ILCF_SWAP|Kaynak ve hedef görüntüler, resim listesindeki konumları değiştirir.|

*pSrc*<br/>
Kopyalama işleminin `CImageList` hedefi olan bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#6](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]

## <a name="cimagelistcreate"></a><a name="create"></a>CImageList::Oluştur

Bir resim listesini başharfe alarır ve [cimagelist](../../mfc/reference/cimagelist-class.md) nesnesine bağlar.

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

*Cx*<br/>
Her görüntünün piksel boyutları.

*Cy*<br/>
Her görüntünün piksel boyutları.

*Nflags*<br/>
Oluşturulacak resim listesi türünü belirtir. Bu parametre aşağıdaki değerlerin bir leşimi olabilir, ancak `ILC_COLOR` değerlerden yalnızca birini içerebilir.

|Değer|Anlamı|
|-----------|-------------|
|ILC_COLOR|Diğer ILC_COLOR* bayraklarından hiçbiri belirtilmemişse varsayılan davranışı kullanın. Genellikle, varsayılan ILC_COLOR4; ancak eski ekran sürücüleri için varsayılan ILC_COLORDDB.|
|ILC_COLOR4|Görüntü listesinin bit haritası olarak 4 bit (16 renkli) aygıtbağımsız bit eşlemi (DIB) bölümünü kullanın.|
|ILC_COLOR8|8 bit DIB bölümü kullanın. Renk tablosu için kullanılan renkler, yarı ton paleti ile aynı renklerdir.|
|ILC_COLOR16|16 bit (32/64k renkli) DIB bölümü kullanın.|
|ILC_COLOR24|24 bit DIB bölümü kullanın.|
|ILC_COLOR32|32 bit DIB bölümü kullanın.|
|ILC_COLORDDB|Aygıta bağlı bit eşlemi kullanın.|
|ILC_MASK|Maske kullanıyor. Resim listesi, biri maske olarak kullanılan tek renkli bit eşlemi olmak üzere iki bit eşlem içerir. Bu değer dahil edilmezse, resim listesi yalnızca bir bit eşlemesi içerir. Maskeli resimler hakkında daha fazla bilgi için [Resim Listesinden Resim Çizim'e](../../mfc/drawing-images-from-an-image-list.md) bakın.|

*nInitial*<br/>
Resim listesinin başlangıçta içerdiği görüntü sayısı.

*nGrow*<br/>
Sistemin yeni görüntülere yer açmak için listeyi yeniden boyutlandırması gerektiğinde görüntü listesinin büyüyebileceği görüntü sayısı. Bu parametre, yeniden boyutlandırılmış resim listesinin içerebileceği yeni görüntülerin sayısını gösterir.

*nBitmapID*<br/>
Resim listesiyle ilişkilendirilecek bit eşlemin kaynak iD'leri.

*crMask*<br/>
Renk bir maske oluşturmak için kullanılır. Belirtilen bit eşönünde bu rengin her pikseli siyaha değiştirilir ve maskedeki karşılık gelen bit bir olarak ayarlanır.

*lpszBitmapID*<br/>
Görüntülerin kaynak işlelerini içeren bir dize.

*imagelist1*<br/>
Bir `CImageList` nesneye başvuru.

*nImage1*<br/>
İlk varolan görüntünün dizini.

*imagelist2*<br/>
Bir `CImageList` nesneye başvuru.

*nImage2*<br/>
İkinci varolan görüntüdizini.

*Dx*<br/>
İlk görüntüyle ilişki içinde ikinci görüntünün x ekseninin piksel olarak mahsup edilmiştir.

*Dy*<br/>
İlk görüntüyle ilişki içinde ikinci görüntünün y ekseninin piksel olarak mahsup edilmiştir.

*pImageList*<br/>
Bir `CImageList` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki adımda bir `CImageList` yapı inşa e. Önce oluşturucuyu çağırın `Create`ve ardından görüntü listesini oluşturan ve `CImageList` nesneye iliştiren , çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#7](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]

## <a name="cimagelistdeleteimagelist"></a><a name="deleteimagelist"></a>CImageList::DeleteImageList

Resim listesini silmek için bu işlevi arayın.

```
BOOL DeleteImageList();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#8](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]

## <a name="cimagelistdeletetempmap"></a><a name="deletetempmap"></a>CImageList::DeleteTempMap

Boşta kalan `CWinApp` zaman işleyicisi `DeleteTempMap` tarafından otomatik `CImageList` olarak çağrılır, [FromHandle](#fromhandle)tarafından oluşturulan `hImageList`geçici nesneleri siler, ancak `ImageList` nesnelerle geçici olarak ilişkili tüm tutamaçları () yok etmez.

```
static void PASCAL DeleteTempMap();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#9](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]

## <a name="cimagelistdetach"></a><a name="detach"></a>CImageList::Detach

Görüntü listesi nesnesini bir `CImageList` nesneden ayırmak için bu işlevi çağırın.

```
HIMAGELIST Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Görüntü listesi nesnesine bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, görüntü listesi nesnesine bir tanıtıcı döndürür.

### <a name="example"></a>Örnek

  CImageList için örneğe [bakın:Ekle.](#attach)

## <a name="cimagelistdragenter"></a><a name="dragenter"></a>CImageList::DragEnter

Sürükleme işlemi sırasında, *güncelleştirmeleri pWndLock* tarafından belirtilen pencereye kilitler ve sürükleme görüntüsünü *noktada*belirtilen konumda görüntüler.

```
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pWndLock*<br/>
Sürükleme görüntüsünün sahibi olan pencereyi işaretleyin.

*Nokta*<br/>
Sürükleme görüntüsünü görüntülemek için konumlandırın. Koordinatlar pencerenin sol üst köşesine göredir (istemci alanı değil).

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Koordinatlar pencerenin sol üst köşesine göredir, bu nedenle koordinatları belirtirken kenarlık, başlık çubuğu ve menü çubuğu gibi pencere öğelerinin genişliklerini telafi etmeniz gerekir.

*pWndLock* NULL ise, bu işlev görüntüyü masaüstü penceresiyle ilişkili görüntü bağlamında çizer ve koordinatlar ekranın sol üst köşesine göredir.

Bu işlev, sürükleme işlemi sırasında verilen penceredeki diğer tüm güncelleştirmeleri kilitler. Sürükle işlemi sırasında sürükle ve bırak işleminin hedefini vurgulamak gibi herhangi bir çizim yapmanız gerekiyorsa, [CImageList::DragLeave](#dragleave) işlevini kullanarak sürüklenen görüntüyü geçici olarak gizleyebilirsiniz.

### <a name="example"></a>Örnek

  CImageList için örneğe [bakın:BeginDrag](#begindrag).

## <a name="cimagelistdragleave"></a><a name="dragleave"></a>CImageList::DragYorum bırakın

*pWndLock* tarafından belirtilen pencerenin kilidini açar ve sürükle görüntüsünü gizleyerek pencerenin güncelleştirilebilmesine olanak sağlar.

```
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```

### <a name="parameters"></a>Parametreler

*pWndLock*<br/>
Sürükleme görüntüsünün sahibi olan pencereyi işaretleyin.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

  CImageList için örneğe [bakın:EndDrag](#enddrag).

## <a name="cimagelistdragmove"></a><a name="dragmove"></a>CImageList::DragTaşı

Sürükle ve bırak işlemi sırasında sürüklenen görüntüyü taşımak için bu işlevi çağırın.

```
static BOOL PASCAL DragMove(CPoint pt);
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
Yeni sürükleme pozisyonu.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle WM_MOUSEMOVE iletisine yanıt olarak çağrılır. Sürükleme işlemini başlatmak için `BeginDrag` üye işlevi kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#4](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]

## <a name="cimagelistdragshownolock"></a><a name="dragshownolock"></a>CImageList::DragShowNolock

Sürükleme işlemi sırasında sürükle görüntüsünü pencereyi kilitlemeden gösterir veya gizler.

```
static BOOL PASCAL DragShowNolock(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bGöster*<br/>
Sürükleme görüntüsünün gösterilip gösterilmeyeceğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[CImageList::DragEnter](#dragenter) işlevi, sürükleme işlemi sırasında penceredeki tüm güncelleştirmeleri kilitler. Ancak bu işlev pencereyi kilitlemez.

## <a name="cimagelistdraw"></a><a name="draw"></a>CImageList::Draw

Sürükle ve bırak işlemi sırasında sürüklenen görüntüyü çizmek için bu işlevi çağırın.

```
BOOL Draw(
    CDC* pDC,
    int nImage,
    POINT pt,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Hedef aygıt bağlamını işaretçi.

*nImage*<br/>
Çizecek görüntünün sıfır tabanlı dizini.

*Pt*<br/>
Belirtilen aygıt bağlamı içinde çizilen konum.

*nStyle*<br/>
Çizim stilini belirten bayrak. Bu değerlerden biri veya birkaçı olabilir:

|Değer|Anlamı|
|-----------|-------------|
|ILD_BLEND25, ILD_FOCUS|Görüntü çizer, sistem vurgu rengi ile yüzde 25 karıştırma. Görüntü listesi maske içermiyorsa, bu değerin bir etkisi yoktur.|
|ILD_BLEND50, ILD_SELECTED, ILD_BLEND|Sistem vurgu rengi yle yüzde 50'sini karıştırarak görüntüyü çizer. Görüntü listesi maske içermiyorsa, bu değerin bir etkisi yoktur.|
|ILD_MASK|Maskeyi çizer.|
|ILD_NORMAL|Görüntü listesinin arka plan rengini kullanarak görüntüyü çizer. Arka plan rengi CLR_NONE değeri ise, görüntü maske kullanılarak saydam olarak çizilir.|
|ILD_TRANSPARENT|Arka plan renginden bağımsız olarak maskeyi kullanarak görüntüyü saydam olarak çizer.|

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

  CImageList için örneğe [bakın:SetOverlayImage](#setoverlayimage).

## <a name="cimagelistdrawex"></a><a name="drawex"></a>CImageList::DrawEx

Belirtilen aygıt bağlamında bir resim listesi öğesi çizer.

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

*Pdc*<br/>
Hedef aygıt bağlamını işaretçi.

*nImage*<br/>
Çizecek görüntünün sıfır tabanlı dizini.

*Pt*<br/>
Belirtilen aygıt bağlamı içinde çizilen konum.

*Sz*<br/>
Görüntünün sol üst köşesine göre çizecek kısmı boyutu. Windows SDK'da [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) *dx* ve *dy'ye* bakın.

*clrBk*<br/>
Görüntünün arka plan rengi. Windows SDK'da [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) *rgbBk'ye* bakın.

*clrFg*<br/>
Görüntünün ön plan rengi. Windows SDK [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) *rgbFg* bakın.

*nStyle*<br/>
Çizim stilini belirten bayrak. Windows SDK'da [ImageList_DrawEx'daki](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) *fStyle'a* bakın.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İşlev belirtilen çizim stilini kullanır ve görüntüyü belirtilen renkle karıştırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#10](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]

## <a name="cimagelistdrawindirect"></a><a name="drawindirect"></a>CImageList::DrawIndirect

Görüntü listesinden görüntü çizmek için bu üye işlevi arayın.

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

*pimldp*<br/>
Çizim işlemi hakkında bilgi içeren [IMAGELISTDRAWPARAMS](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams) yapısına işaretçi.

*Pdc*<br/>
Hedef aygıt bağlamına işaretçi. Bu [CDC](../../mfc/reference/cdc-class.md) nesnesi ile bittiğinde silmeniz gerekir.

*nImage*<br/>
Çizilecek görüntünün sıfır tabanlı dizini.

*Pt*<br/>
Görüntünün çizileceği x- ve y koordinatlarını içeren bir [POINT](/windows/win32/api/windef/ns-windef-point) yapısı.

*Sz*<br/>
Çizilecek görüntünün boyutunu gösteren [bir BOYUT](/windows/win32/api/windef/ns-windef-size) yapısı.

*ptOrigin*<br/>
Çizim işleminin sol üst köşesini, görüntünün kendisine göre belirten x- ve y koordinatlarını içeren bir [POINT](/windows/win32/api/windef/ns-windef-point) yapısı. X-koordinatının solunda ve y-koordinatının üzerinde olan görüntünün pikselleri çizilmez.

*fStyle*<br/>
Çizim stilini ve isteğe bağlı olarak bindirme görüntüsünü belirten bayrak. Bindirme görüntüsü hakkında bilgi için Açıklamalar bölümüne bakın. MFC varsayılan uygulaması, ILD_NORMAL, görüntü listesiiçin arka plan rengini kullanarak görüntüyü çizer. Arka plan rengi CLR_NONE değeri ise, görüntü bir maske kullanılarak saydam olarak çizilir.

Diğer olası stiller [IMAGELISTDRAWPARAMS](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams) yapısının *fStyle* üyesi altında açıklanmıştır.

*dwRop*<br/>
Raster-işlem kodunu belirten değer. Bu kodlar, son rengi elde etmek için kaynak dikdörtgenin renk verilerinin hedef dikdörtgenin renk verileriyle nasıl birleştirileceğini tanımlar. MFC'nin varsayılan uygulaması Olan SRCCOPY, kaynak dikdörtgeni doğrudan hedef dikdörtgenin kopyalar. *fStyle* parametresi ILD_ROP bayrağını içermiyorsa, bu parametre yoksayılır.

[IMAGELISTDRAWPARAMS](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams) yapısının *dwRop* üyesi altında diğer olası değerler açıklanmıştır.

*rgbGeri*<br/>
Varsayılan olarak görüntü arka plan rengi CLR_DEFAULT. Bu parametre uygulama tanımlı Bir RGB değeri veya aşağıdaki değerlerden biri olabilir:

|Değer|Anlamı|
|-----------|-------------|
|CLR_DEFAULT|Varsayılan arka plan rengi. Görüntü, resim listesi arka plan rengi kullanılarak çizilir.|
|CLR_NONE|Arka plan rengi yok. Görüntü saydam olarak çizilir.|

*rgbFore*<br/>
Görüntü ön plan rengi, varsayılan olarak CLR_DEFAULT. Bu parametre uygulama tanımlı Bir RGB değeri veya aşağıdaki değerlerden biri olabilir:

|Değer|Anlamı|
|-----------|-------------|
|CLR_DEFAULT|Varsayılan ön plan rengi. Görüntü ön plan rengi olarak sistem vurgulamak renk kullanılarak çizilir.|
|CLR_NONE|Karışım rengi yok. Görüntü, hedef aygıt bağlamının rengiyle karıştırılır.|

Bu parametre yalnızca *fStyle* ILD_BLEND25 veya ILD_BLEND50 bayrağı içeriyorsa kullanılır.

*fDevlet*<br/>
Çizim durumunu belirten bayrak. Bu üye bir veya daha fazla resim listesi durum bayrakları içerebilir.

*Çerçeve*<br/>
Doygunluk ve alfa-karıştırma etkilerinin davranışını etkiler.

ILS_SATURATE kullanıldığında, bu üye simgedeki her piksel için RGB üçüzünün her renk bileşenine eklenen değeri tutar.

ILS_APLHA kullanıldığında, bu üye alfa kanalının değerini tutar. Bu değer 0'dan 255'e kadar olabilir, 0 tamamen saydam, 255 tamamen opak olabilir.

*crEffect*<br/>
Kızdırma ve gölge efektleri için kullanılan [COLORREF](/windows/win32/gdi/colorref) değeri.

### <a name="return-value"></a>Dönüş Değeri

Görüntü başarıyla çizilirse DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Win32 yapısını kendiniz doldurmak istiyorsanız ilk sürümü kullanın. MFC'nin varsayılan bağımsız değişkenlerinden bir veya daha fazlasını kullanmak veya yapıyı yönetmekten kaçınmak istiyorsanız ikinci sürümü kullanın.

Bindirme görüntüsü, *nImage* parametresi tarafından bu üye işlevde belirtilen birincil görüntünün üstüne çizilen bir görüntüdür. [INDEXTOOVERLAYMASK](/windows/win32/api/commctrl/nf-commctrl-indextooverlaymask) makrosu kullanılarak belirtilen bindirme maskesinin tek tabanlı diziniyle [Beraberlik](#draw) üye işlevini kullanarak bir bindirme maskesi çizin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#11](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]

## <a name="cimagelistenddrag"></a><a name="enddrag"></a>CImageList::EndDrag

Sürükleme işlemini sona erdirmek için bu işlevi çağırın.

```
static void PASCAL EndDrag();
```

### <a name="remarks"></a>Açıklamalar

Sürükleme işlemini başlatmak için `BeginDrag` üye işlevi kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#5](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]

## <a name="cimagelistextracticon"></a><a name="extracticon"></a>CImageList::Extracticon

Görüntü listesindeki görüntüve ilgili maskeyi temel alan bir simge oluşturmak için bu işlevi arayın.

```
HICON ExtractIcon(int nImage);
```

### <a name="parameters"></a>Parametreler

*nImage*<br/>
Görüntünün sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simgenin tutamacı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, simgeoluşturmak için [ImageList_ExtractIcon](/windows/win32/api/commctrl/nf-commctrl-imagelist_extracticon) makro davranışına dayanır. Simge oluşturma ve temizleme hakkında daha fazla bilgi için [ImageList_ExtractIcon](/windows/win32/api/commctrl/nf-commctrl-imagelist_extracticon) makroya bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#12](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]

## <a name="cimagelistfromhandle"></a><a name="fromhandle"></a>CImageList::FromHandle

Görüntü listesine `CImageList` tutamacı verildiğinde işaretçiyi nesneye döndürür.

```
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Parametreler

*hImageList*<br/>
Resim listesini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa `CImageList` nesneye işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

A `CImageList` tutamacına zaten bağlı değilse, `CImageList` geçici bir nesne oluşturulur ve eklenir. Bu `CImageList` geçici nesne yalnızca, uygulamanın olay döngüsünde boşta kalma süresine sahip olduğu ve tüm geçici nesnelerin silindiği bir sonraki zamana kadar geçerlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#13](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]

## <a name="cimagelistfromhandlepermanent"></a><a name="fromhandlepermanent"></a>CImageList::FromHandlePermanent

Görüntü listesine `CImageList` tutamacı verildiğinde işaretçiyi nesneye döndürür.

```
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Parametreler

*hImageList*<br/>
Resim listesini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa `CImageList` nesneye işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bir `CImageList` nesne tutamacına bağlı değilse, NULL döndürülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#14](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]

## <a name="cimagelistgetbkcolor"></a><a name="getbkcolor"></a>CImageList::GetBkColor

Görüntü listesi için geçerli arka plan rengini almak için bu işlevi arayın.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesne arka plan renginin `CImageList` RGB renk değeri.

### <a name="example"></a>Örnek

  CImageList için örneğe [bakın:SetBkColor](#setbkcolor).

## <a name="cimagelistgetdragimage"></a><a name="getdragimage"></a>CImageList::GetDragImage

Sürükleme için kullanılan geçici resim listesini alır.

```
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,
    LPPOINT lpPointHotSpot);
```

### <a name="parameters"></a>Parametreler

*lpPoint*<br/>
Geçerli sürükleme konumunu alan bir [POINT](/windows/win32/api/windef/ns-windef-point) yapısının adresi.

*lpPointHotSpot*<br/>
Sürükleme konumuna göre sürükleme görüntüsünün mahsup unu alan bir `POINT` yapının adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, sürükleme için kullanılan geçici görüntü listesine işaretçi; aksi takdirde, NULL.

## <a name="cimagelistgetimagecount"></a><a name="getimagecount"></a>CImageList::GetImageCount

Görüntü listesindeki görüntü sayısını almak için bu işlevi arayın.

```
int GetImageCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görüntü sayısı.

### <a name="example"></a>Örnek

  CImageList için örneğe [bakın:ExtractIcon](#extracticon).

## <a name="cimagelistgetimageinfo"></a><a name="getimageinfo"></a>CImageList::GetImageInfo

Görüntü hakkında bilgi almak için bu işlevi arayın.

```
BOOL GetImageInfo(
    int nImage,
    IMAGEINFO* pImageInfo) const;
```

### <a name="parameters"></a>Parametreler

*nImage*<br/>
Görüntünün sıfır tabanlı dizini.

*pImageInfo*<br/>
Görüntü hakkında bilgi alan bir [IMAGEINFO](/windows/win32/api/commctrl/ns-commctrl-imageinfo) yapısına işaretçi. Bu yapıdaki bilgiler, görüntünün bit eşlemlerini doğrudan işlemek için kullanılabilir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yapı, `IMAGEINFO` resim listesindeki bir resim hakkında bilgi içerir.

## <a name="cimagelistgetsafehandle"></a><a name="getsafehandle"></a>CImageList::GetSafeHandle

Veri üyesini `m_hImageList` almak için bu işlevi arayın.

```
HIMAGELIST GetSafeHandle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ekli resim listesine bir tanıtıcı; aksi takdirde hiçbir nesne eklenmişse NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#15](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]

## <a name="cimagelistm_himagelist"></a><a name="m_himagelist"></a>CImageList::m_hImageList

Bu nesneye iliştirilen görüntü listesinin tutamacı.

`HIMAGELIST m_hImageList;`

### <a name="remarks"></a>Açıklamalar

Veri `m_hImageList` üyesi, HIMAGELIST türünün ortak değişkenidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#23](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]

## <a name="cimagelistoperator-himagelist"></a><a name="operator_himagelist"></a>CImageList::operatör HIMAGELIST

`CImageList` Nesnenin bağlı tutamacını almak için bu işleci kullanın.

```
operator HIMAGELIST() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, `CImageList` nesne tarafından temsil edilen görüntü listesine bir tanıtıcı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu işleç, bir HIMAGELIST nesnesinin doğrudan kullanımını destekleyen bir döküm operatörüdür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#16](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]

## <a name="cimagelistread"></a><a name="read"></a>CImageList::Oku

Bir arşivdeki resim listesini okumak için bu işlevi arayın.

```
BOOL Read(CArchive* pArchive);
```

### <a name="parameters"></a>Parametreler

*pArşiv*<br/>
Görüntü listesinin `CArchive` okunabilmek için bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#18](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]

## <a name="cimagelistremove"></a><a name="remove"></a>CImageList::Kaldır

Görüntüyü görüntü listesi nesnesinden kaldırmak için bu işlevi çağırın.

```
BOOL Remove(int nImage);
```

### <a name="parameters"></a>Parametreler

*nImage*<br/>
Görüntünün sıfır tabanlı dizini kaldırmak için.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*nImage'i* izleyen tüm öğeler artık tek bir konumda aşağı hareket ediyor. Örneğin, bir resim listesi iki öğe içeriyorsa, ilk öğenin silmesi kalan öğenin şimdi ilk konumda olması gerekir. *nImage*=0 ilk konumdaki öğe için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#19](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]

## <a name="cimagelistreplace"></a><a name="replace"></a>CImageList::Değiştir

Görüntü listesindeki bir görüntüyü yeni bir resimle değiştirmek için bu işlevi çağırın.

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

*nImage*<br/>
Yerine geçecek görüntünün sıfır tabanlı dizini.

*pbmImage*<br/>
Görüntüyü içeren bit eşlemi için bir işaretçi.

*pbmMask*<br/>
Maskeyi içeren bit eşleninin işaretçisi. Görüntü listesinde maske kullanılmazsa, bu parametre yoksayılır.

*Hıcon*<br/>
Yeni görüntü için bit eşlemi ve maske içeren simgenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

BOOL'u döndüren sürüm başarılı olursa sıfırsız döndürür; aksi takdirde 0.

**Int** döndüren sürüm başarılı olursa görüntünün sıfır tabanlı dizinini döndürür; aksi takdirde - 1.

### <a name="remarks"></a>Açıklamalar

Yer tutucu görüntü dizini numaralarına yeni, geçerli görüntüler atamak için [SetImageCount'ı](#setimagecount) aradıktan sonra bu üye işlevini arayın.

### <a name="example"></a>Örnek

  CImageList için örneğe [bakın:SetImageCount](#setimagecount).

## <a name="cimagelistsetbkcolor"></a><a name="setbkcolor"></a>CImageList::SetBkColor

Bir resim listesiiçin arka plan rengini ayarlamak için bu işlevi arayın.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>Parametreler

*Cr*<br/>
Ayarlanan arka plan rengi. CLR_NONE olabilir. Bu durumda, görüntüler maske kullanılarak saydam olarak çizilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa önceki arka plan rengi; aksi takdirde CLR_NONE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#20](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]

## <a name="cimagelistsetdragcursorimage"></a><a name="setdragcursorimage"></a>CImageList::SetDragCursorImage

Verilen görüntüyü (genellikle fare imleci görüntüsü) geçerli sürükleme görüntüsüyle birleştirerek yeni bir sürükleme görüntüsü oluşturur.

```
BOOL SetDragCursorImage(
    int nDrag,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>Parametreler

*nDrag*<br/>
Sürükleme görüntüsüyle birlişecek yeni görüntüdizini.

*ptHotSpot*<br/>
Sıcak noktanın yeni görüntüdeki konumu.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Sürükleme işlevleri sürükleme işlemi sırasında yeni görüntüyü kullandığından, çağırdıktan `CImageList::SetDragCursorImage`sonra gerçek fare imlecini gizlemek için Windows [ShowCursor](/windows/win32/api/winuser/nf-winuser-showcursor) işlevini kullanmalısınız. Aksi takdirde, sistem sürükleme işlemi süresince iki fare imleci olabilir.

## <a name="cimagelistsetimagecount"></a><a name="setimagecount"></a>CImageList::SetImageCount

Bir `CImageList` nesnedeki görüntü sayısını sıfırlamak için bu üye işlevi arayın.

```
BOOL SetImageCount(UINT uNewCount);
```

### <a name="parameters"></a>Parametreler

*uNewCount*<br/>
Görüntü listesindeki yeni toplam görüntü sayısını belirten değer.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Görüntü listesindeki görüntü sayısını artırmak için bu üye işlevi ararsanız, geçerli görüntülere yeni dizinler atamak için her ek görüntü için [Değiştir'i](#replace) arayın. Dizinleri geçerli görüntülere atamazsanız, yeni görüntüler oluşturan işlemleri çizin öngörülemez olacaktır.

Bu işlevi kullanarak bir görüntü listesinin boyutunu küçültürseniz, kesilen görüntüler serbest bırakılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#21](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]

## <a name="cimagelistsetoverlayimage"></a><a name="setoverlayimage"></a>CImageList::SetOverlayImage

Bir görüntünün sıfır tabanlı dizinini bindirme maskeleri olarak kullanılacak resimler listesine eklemek için bu işlevi arayın.

```
BOOL SetOverlayImage(
    int nImage,
    int nOverlay);
```

### <a name="parameters"></a>Parametreler

*nImage*<br/>
Bindirme maskesi olarak kullanılacak görüntünün sıfır tabanlı dizini.

*nOverlay*<br/>
Bindirme maskesinin tek tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Listeye en fazla dört endeks eklenebilir.

Bindirme maskesi, başka bir görüntünün üzerine saydam olarak çizilmiş bir görüntüdür. [CImageList::DRAW](#draw) üye işlevi, INDEXTOOVERLAYMASK makrosu kullanılarak belirtilen bindirme maskesinin tek tabanlı diziniyle görüntünün üzerine bir bindirme maskesi çizin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#22](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]

## <a name="cimagelistwrite"></a><a name="write"></a>CImageList::Yaz

Bir arşive görüntü listesi nesnesi yazmak için bu işlevi arayın.

```
BOOL Write(CArchive* pArchive);
```

### <a name="parameters"></a>Parametreler

*pArşiv*<br/>
Görüntü listesinin `CArchive` depolanabilmek için bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#17](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CListCtrl Sınıfı](../../mfc/reference/clistctrl-class.md)<br/>
[CTabCtrl Sınıfı](../../mfc/reference/ctabctrl-class.md)
