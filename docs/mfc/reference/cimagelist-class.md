---
title: Cımagelist sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ca52f7a5940de3caa87f81ddf07625ab751927c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054546"
---
# <a name="cimagelist-class"></a>Cımagelist sınıfı

Windows ortak görüntü listesi denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CImageList : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CImageList::CImageList](#cimagelist)|Oluşturur bir `CImageList` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CImageList::Add](#add)|Görüntünün veya görüntü için görüntü listesi ekler.|
|[CImageList::Attach](#attach)|Bir görüntü listesine ekleyen bir `CImageList` nesne.|
|[CImageList::BeginDrag](#begindrag)|Bir görüntüyü sürükleyerek başlar.|
|[CImageList::Copy](#copy)|Bir görüntü içindeki kopyalar bir `CImageList` nesne.|
|[CImageList::Create](#create)|Görüntü listesi başlatır ve ona bağlanan bir `CImageList` nesne.|
|[CImageList::DeleteImageList](#deleteimagelist)|Görüntü listesi siler.|
|[CImageList::DeleteTempMap](#deletetempmap)|Çağıran [CWinApp](../../mfc/reference/cwinapp-class.md) herhangi bir geçici silme için boşta kalma süresi işleyicisi `CImageList` tarafından oluşturulan nesne `FromHandle`.|
|[CImageList::Detach](#detach)|Görüntü listesi nesneden çıkarır bir `CImageList` nesnesi ve bir görüntü listesi için bir tanıtıcı döndürür.|
|[CImageList::DragEnter](#dragenter)|Bir sürükleme işlemi sırasında güncelleştirmeleri kilitler ve belirtilen bir konumda görüntüyü Sürükle görüntüler.|
|[CImageList::DragLeave](#dragleave)|Pencerenin kilidini açar ve böylece penceresi güncelleştirilebilir görüntüyü Sürükle gizler.|
|[CImageList::DragMove](#dragmove)|Bir Sürükle ve bırak işlemi sırasında sürüklediğiniz görüntü taşır.|
|[CImageList::DragShowNolock](#dragshownolock)|Gösterir veya pencerenin kilitlemeden sürükleme işlemi sırasında görüntüyü Sürükle gizler.|
|[CImageList::Draw](#draw)|Bir Sürükle ve bırak işlemi sırasında sürüklediğiniz resim çizer.|
|[CImageList::DrawEx](#drawex)|Görüntü listesi öğeyi belirtilen cihaz bağlamında çizer. İşlevi, belirtilen çizim stili kullanır ve görüntüyü belirtilen rengi karıştırır.|
|[CImageList::DrawIndirect](#drawindirect)|Görüntü listesinden görüntü çizer.|
|[CImageList::EndDrag](#enddrag)|Bir sürükleme işlemi sonlandırır.|
|[CImageList::ExtractIcon](#extracticon)|Bir görüntü ve resim listesi maskesi göre bir simge oluşturur.|
|[CImageList::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CImageList` nesnesi bir işleyici için bir görüntü listesi verildiğinde. Varsa bir `CImageList` nesne tanıtıcısını, geçici bir iliştirilmemiş `CImageList` nesnesi oluşturulur ve bağlı.|
|[CImageList::FromHandlePermanent](#fromhandlepermanent)|Bir işaretçi döndüren bir `CImageList` nesnesi bir işleyici için bir görüntü listesi verildiğinde. Varsa bir `CImageList` nesne tanıtıcısını iliştirilmemiş, NULL döndürülür.|
|[CImageList::GetBkColor](#getbkcolor)|Görüntü listesi geçerli arka plan rengini alır.|
|[CImageList::GetDragImage](#getdragimage)|Sürükleme için kullanılan geçici görüntü listesini alır.|
|[CImageList::GetImageCount](#getimagecount)|Görüntü listesinden görüntü sayısını alır.|
|[CImageList::GetImageInfo](#getimageinfo)|Görüntü hakkındaki bilgileri alır.|
|[CImageList::GetSafeHandle](#getsafehandle)|Alır `m_hImageList`.|
|[CImageList::Read](#read)|Görüntü listesi bir arşivden okur.|
|[CImageList::Remove](#remove)|Görüntü listesinden görüntü kaldırır.|
|[CImageList::Replace](#replace)|Görüntü listesi görüntüde yeni bir görüntü ile değiştirir.|
|[CImageList::SetBkColor](#setbkcolor)|Görüntü listesi arka plan rengini ayarlar.|
|[CImageList::SetDragCursorImage](#setdragcursorimage)|Yeni bir Sürükle görüntüsü oluşturur.|
|[CImageList::SetImageCount](#setimagecount)|Görüntü listesinden görüntü sayısını sıfırlar.|
|[CImageList::SetOverlayImage](#setoverlayimage)|Katman maskeleri olarak kullanılan görüntülerin listesini görüntü sıfır tabanlı dizini ekler.|
|[CImageList::Write](#write)|Görüntü listesi arşive yazar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CImageList::operator HIMAGELIST](#operator_himagelist)|Ekli döndürür HIMAGELIST `CImageList`.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CImageList::m_hImageList](#m_himagelist)|Bu nesneye bağlı görüntü listesi içeren bir tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

"Görüntü listesi" aynı boyutta görüntülerin her biri sıfır tabanlı diziniyle tarafından başvurulabilen bir koleksiyondur. Görüntü listeleri büyük simgeler veya bit eşlemler kümelerini etkili bir şekilde yönetmek için kullanılır. Görüntü listesi'ndaki tüm görüntüler geniş, tek bit eşlem ekran cihaz biçiminde yer alır. Görüntü listesi görüntüleri şeffaf bir şekilde çizmek için kullanılan maskeleri (simge stili) içeren tek renkli bir bit eşlem de. Microsoft Win32 uygulama programlama arabirimi (API), görüntü çizme, oluşturma ve görüntü listeleri yok, eklemek ve görüntülerini kaldırmak, görüntüleri değiştirin, görüntüleri birleştirme ve görüntüleri sürükleme olanak sağlayan bir görüntü listesi işlevleri sağlar.

Bu denetimi (ve bu nedenle `CImageList` sınıfı) ve üzeri yalnızca Windows 95/98 ve Windows NT sürüm 3.51 altında çalışan programlar için kullanılabilir.

Kullanma hakkında daha fazla bilgi için `CImageList`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [Cımagelist kullanma](../../mfc/using-cimagelist.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CImageList`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

##  <a name="add"></a>  CImageList::Add

Görüntü listesi için bir veya daha fazla görüntü veya simge eklemek için bu işlevi çağırın.

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
Görüntüyü ya da görüntülerini içeren bit eşlem işaretçisi. Bit eşlemin genişliğini görüntülerinin sayısını algılanır.

*pbmMask*<br/>
Maske içeren bit eşlem işaretçisi. Maske sahip görüntü listesi kullanılırsa bu parametre yoksayılır.

*crMask*<br/>
Maske oluşturmak için kullanılan renk. Her piksel belirtilen bit eşlem bu renk siyah olarak değişir ve karşılık gelen bit maskesinde birine ayarlanır.

*hIcon*<br/>
Bit eşlem ve yeni görüntüyü maskesinin içeren simge tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

İlk yeni görüntüyü başarılı olursa sıfır tabanlı dizini; Aksi takdirde - 1.

### <a name="remarks"></a>Açıklamalar

Simge tanıtıcı ile işiniz bittiğinde serbest için sorumlu olursunuz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#1](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]

##  <a name="attach"></a>  CImageList::Attach

Bir görüntü listesine eklemek için bu işlevi çağırın bir `CImageList` nesne.

```
BOOL Attach(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Parametreler

*hImageList*<br/>
Bir görüntü listesi nesnesi için bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Ek başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#2](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]

##  <a name="begindrag"></a>  CImageList::BeginDrag

Bir görüntüyü sürükleyerek başlamak için bu işlevi çağırın.

```
BOOL BeginDrag(
    int nImage,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>Parametreler

*Bir*<br/>
Görüntünün sürüklemek için sıfır tabanlı dizini.

*ptHotSpot*<br/>
Koordinatları başlangıç Sürükle konumu (genellikle, imleç konumu). Sol üst köşesinde resmin göreli koordinatları.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev sürüklemek için kullanılan geçici görüntü listesini oluşturur. Görüntüyü belirtilen görüntü ile maskesi geçerli imleç ile birleştirir. Sonraki WM_MOUSEMOVE iletilere yanıt olarak, görüntüyü Sürükle kullanarak taşıyabilirsiniz `DragMove` üye işlevi. Sürükleme işlemi sona erdirmek için kullanabileceğiniz `EndDrag` üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#3](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]

##  <a name="cimagelist"></a>  CImageList::CImageList

Oluşturur bir `CImageList` nesne.

```
CImageList();
```

##  <a name="copy"></a>  CImageList::Copy

Bu üye işlevi Win32 işlevinin davranışı uygulayan [ImageList_Copy](/windows/desktop/api/commctrl/nf-commctrl-imagelist_copy)Windows SDK içinde açıklandığı gibi.

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
Kopyalama işleminin hedefi olarak kullanılacak görüntüyü sıfır tabanlı dizini.

*ISRC*<br/>
Kopyalama işlemi kaynağı olarak kullanılacak görüntüyü sıfır tabanlı dizini.

*uFlags*<br/>
Kopyalama işlemi yapılacak türünü belirten bit bayrak değeri. Bu parametre aşağıdaki değerlerden biri olabilir:

|Değer|Açıklama|
|-----------|-------------|
|ILCF_MOVE|Kaynak görüntüyü hedef görüntü dizinine kopyalanır. Bu işlem, belirli bir görüntüyü birden fazla örneğini sonuçlanır. ILCF_MOVE varsayılandır.|
|ILCF_SWAP|Konumlar görüntü listesi içinde kaynak ve hedef görüntülerini exchange.|

*pSrc*<br/>
Bir işaretçi bir `CImageList` kopyalama işleminin hedef nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#6](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]

##  <a name="create"></a>  CImageList::Create

Görüntü listesi başlatır ve ona bağlanan bir [Cımagelist](../../mfc/reference/cimagelist-class.md) nesne.

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

*CX*<br/>
Piksel cinsinden her görüntü boyutları.

*CY*<br/>
Piksel cinsinden her görüntü boyutları.

*nFlags*<br/>
Görüntü listesi oluşturmak için türünü belirtir. Bu parametre aşağıdaki değerlerden bir birleşimi olabilir, ancak yalnızca birini içerebilir `ILC_COLOR` değerleri.

|Değer|Açıklama|
|-----------|-------------|
|ILC_COLOR|Diğer ILC_COLOR * bayrakları hiçbiri belirtilmezse, varsayılan davranışı kullanın. Genellikle, varsayılan ILC_COLOR4 bulunur. Ancak, eski görüntü sürücüleri için ILC_COLORDDB varsayılandır.|
|ILC_COLOR4|4-bit (16 renk) CİHAZDAN bağımsız bit eşlem (DIB) bölümü için resim listesi bit eşlem olarak kullanın.|
|ILC_COLOR8|Bir 8 bit DIB bölümü kullanın. Aynı noktalı palet renkleri için renk tablosu kullanılan renkleri var.|
|ILC_COLOR16|16-bit kullanın (32 / 64k renk) DIB bölümü.|
|ILC_COLOR24|24 bit DIB bölümü kullanın.|
|ILC_COLOR32|Bir 32-bit DIB bölümü kullanın.|
|ILC_COLORDDB|Bir cihaza bağlı bit eşlem kullanın.|
|ILC_MASK|Maske kullanır. Görüntü listesi maske olarak kullanılan tek renkli bir bit eşlem biri olan iki bit eşlemler içerir. Bu değeri dahil değil, yalnızca bir bit eşlem resim listesi içerir. Bkz: [bir görüntü listesinden görüntü çizim](../../mfc/drawing-images-from-an-image-list.md) maskelenmiş görüntüleri hakkında daha fazla bilgi için.|

*nInitial*<br/>
Görüntü listesi başlangıçta içeren görüntü sayısı.

*nGrow*<br/>
Sistem listesi yer açmak için yeni görüntüleri yeniden boyutlandırma gerektiğinde, görüntü listesi büyüyebilir görüntüleri sayısı. Bu parametre, yeniden boyutlandırılan resim listesi içerebilir yeni görüntülerinin sayısını temsil eder.

*nBitmapID*<br/>
Görüntü listesi ile ilişkilendirilecek kaynak kimlikleri bit eşlem.

*crMask*<br/>
Maske oluşturmak için kullanılan renk. Her piksel belirtilen bit eşlem bu renk siyah olarak değişir ve karşılık gelen bit maskesinde birine ayarlanır.

*lpszBitmapID*<br/>
Kaynak kimliklerini resimleri içeren bir dize.

*imagelist1*<br/>
Bir başvuru bir `CImageList` nesne.

*nImage1*<br/>
İlk mevcut görüntü dizini.

*imagelist2*<br/>
Bir başvuru bir `CImageList` nesne.

*nImage2*<br/>
İkinci mevcut görüntü dizini.

*DX*<br/>
İkinci görüntüsünün piksel cinsinden ilk görüntüye ilişkisinde x ekseninin uzaklığı.

*GN*<br/>
İkinci görüntü ilk görüntüde piksel ilişki içindeki y ekseninin uzaklığı.

*pImageList*<br/>
Bir işaretçi bir `CImageList` nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CImageList` iki adımda. İlk olarak, oluşturucusunu çağırın ve ardından arama `Create`, görüntü listesi oluşturur ve ona ekler `CImageList` nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#7](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]

##  <a name="deleteimagelist"></a>  CImageList::DeleteImageList

Görüntü listesi silmek için bu işlevi çağırın.

```
BOOL DeleteImageList();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#8](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]

##  <a name="deletetempmap"></a>  CImageList::DeleteTempMap

Tarafından otomatik olarak adlandırılan `CWinApp` boşta kalma süresi işleyici `DeleteTempMap` herhangi bir geçici siler `CImageList` tarafından oluşturulmuş nesneleri [FromHandle](#fromhandle), tanıtıcıları yok eder ancak ( `hImageList`) geçici olarak ilişkili ile `ImageList` nesneleri.

```
static void PASCAL DeleteTempMap();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#9](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]

##  <a name="detach"></a>  CImageList::Detach

Görüntü listesi nesneden ayırmak için bu işlevi çağırın bir `CImageList` nesne.

```
HIMAGELIST Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Bir görüntü listesi nesnesi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu işlev için resim listesi nesnesi bir tanıtıcı döndürür.

### <a name="example"></a>Örnek

  Örneğin bakın [CImageList::Attach](#attach).

##  <a name="dragenter"></a>  CImageList::DragEnter

Bir sürükleme işlemi sırasında güncelleştirmeleri tarafından belirtilen pencereye kilitler *pWndLock* ve görüntüyü Sürükle tarafından belirtilen konumdaki görüntüler *noktası*.

```
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pWndLock*<br/>
Görüntüyü Sürükle sahip pencere işaretçisi.

*Noktası*<br/>
Görüntüyü Sürükle görüntülenecek da konumunda. Koordinatlar sol üst köşesinde penceresi (istemci alanını değil) göre belirlenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Koordinatları pencerenin sol üst köşesinin göreli olduğundan, kenarlık, başlık çubuğu ve menü çubuğu gibi Pencere öğelerinin genişlikleri koordinatları belirtirken dengelemek gerekir.

Varsa *pWndLock* null, bu işlev, masaüstü pencere ile ilgili görüntü bağlamında resim çizer ve ekranın sol üst köşe göreli koordinatları.

Bu işlev, belirtilen pencereye diğer tüm güncelleştirmeleri sürükleme işlemi sırasında kilitler. Bir Sürükle ve bırak işleminin hedef vurgulama gibi bir sürükleme işlemi sırasında herhangi bir çizim yapmanız gerekiyorsa, geçici olarak sürüklenen görüntüyü kullanarak gizleyebilirsiniz [CImageList::DragLeave](#dragleave) işlevi.

### <a name="example"></a>Örnek

  Örneğin bakın [CImageList::BeginDrag](#begindrag).

##  <a name="dragleave"></a>  CImageList::DragLeave

Tarafından belirtilen pencere kilidini açarak *pWndLock* ve güncelleştirilmesi için penceresini izin vererek Sürükle görüntünün gizler.

```
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```

### <a name="parameters"></a>Parametreler

*pWndLock*<br/>
Görüntüyü Sürükle sahip pencere işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

  Örneğin bakın [CImageList::EndDrag](#enddrag).

##  <a name="dragmove"></a>  CImageList::DragMove

Bir Sürükle ve bırak işlemi sırasında sürüklediğiniz görüntüyü taşımak için bu işlevi çağırın.

```
static BOOL PASCAL DragMove(CPoint pt);
```

### <a name="parameters"></a>Parametreler

*PT*<br/>
Yeni konuma sürükleyin.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, genellikle WM_MOUSEMOVE iletiye yanıt olarak adlandırılır. Bir sürükleme işlemi başlatmak için kullanmak `BeginDrag` üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#4](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]

##  <a name="dragshownolock"></a>  CImageList::DragShowNolock

Gösterir veya pencerenin kilitlemeden sürükleme işlemi sırasında görüntüyü Sürükle gizler.

```
static BOOL PASCAL DragShowNolock(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bBilgi Göster*<br/>
Görüntüyü Sürükle gösterilecek olup olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

[CImageList::DragEnter](#dragenter) işlevi bir sürükleme işlemi sırasında tüm güncelleştirmeleri penceresine kilitler. Bu işlev, ancak pencere kilitlemez.

##  <a name="draw"></a>  CImageList::Draw

Bir Sürükle ve bırak işlemi sırasında sürüklediğiniz resim çizmek için bu işlevi çağırın.

```
BOOL Draw(
    CDC* pDC,
    int nImage,
    POINT pt,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Hedef cihaz bağlamının işaretçisi.

*Bir*<br/>
Görüntünün çizmek için sıfır tabanlı dizini.

*PT*<br/>
Belirtilen cihaz bağlamında çizmek konumu.

*nStyle*<br/>
Çizim stili belirten bayrak. Bir veya daha fazla bu değerleri olabilir:

|Değer|Açıklama|
|-----------|-------------|
|ILD_BLEND25, ILD_FOCUS|Sistem vurgulama rengiyle yüzde 25 karıştırma resim çizer. Görüntü listesi maske içermiyorsa, bu değer etkisizdir.|
|ILD_BLEND50, ILD_SELECTED, ILD_BLEND|Sistem vurgulama rengiyle yüzde 50 karıştırma resim çizer. Görüntü listesi maske içermiyorsa, bu değer etkisizdir.|
|ILD_MASK|Maske çizer.|
|ILD_NORMAL|Görüntüyü arka plan rengi için resim listesi kullanarak çizer. Arka plan rengi CLR_NONE değeriyse, görüntünün saydam maskesi kullanılarak çizilir.|
|ILD_TRANSPARENT|Görüntünün saydam arka plan rengi bakılmaksızın maskesi kullanarak çizer.|

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

  Örneğin bakın [CImageList::SetOverlayImage](#setoverlayimage).

##  <a name="drawex"></a>  CImageList::DrawEx

Görüntü listesi öğeyi belirtilen cihaz bağlamında çizer.

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

*pDC*<br/>
Hedef cihaz bağlamının işaretçisi.

*Bir*<br/>
Görüntünün çizmek için sıfır tabanlı dizini.

*PT*<br/>
Belirtilen cihaz bağlamında çizmek konumu.

*SZ*<br/>
Görüntünün görüntü sol üst köşesine göre çizmek için bölümünü boyutu. Bkz: *dx* ve *GN* içinde [ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) Windows SDK.

*clrBk*<br/>
Görüntü, arka plan rengi. Bkz: *rgbBk* içinde [ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) Windows SDK.

*clrFg*<br/>
Görüntü ön plan rengi. Bkz: *rgbFg* içinde [ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) Windows SDK.

*nStyle*<br/>
Çizim stili belirten bayrak. Bkz: *fStyle* içinde [ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

İşlevi, belirtilen çizim stili kullanır ve görüntüyü belirtilen rengi karıştırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#10](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]

##  <a name="drawindirect"></a>  CImageList::DrawIndirect

Görüntü listesinden görüntü çizme için bu üye işlevini çağırın.

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
Bir işaretçi bir [IMAGELISTDRAWPARAMS](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams) çizim işlemiyle ilgili bilgi içeren yapısı.

*pDC*<br/>
Hedef cihaz bağlamının bir işaretçi. Bu silmelisiniz [CDC](../../mfc/reference/cdc-class.md) ile işiniz bittiğinde nesne.

*Bir*<br/>
Çizilecek görüntü sıfır tabanlı dizini.

*PT*<br/>
A [noktası](https://msdn.microsoft.com/library/windows/desktop/dd162805) x ve y-burada görüntü çizilmiş koordinatları içeren yapısı.

*SZ*<br/>
A [BOYUTU](https://msdn.microsoft.com/library/windows/desktop/dd145106) çizilecek görüntü boyutunu belirten yapısı.

*ptOrigin*<br/>
A [noktası](https://msdn.microsoft.com/library/windows/desktop/dd162805) x ve y-belirtme görüntünün kendisi ile ilgili çizim işlemi sol üst köşesinin koordinatlarının içeren yapısı. Sol x koordinatını ve y koordinatını yukarıda olan piksel görüntünün çizilmiş değil.

*fStyle*<br/>
Çizim stili ve isteğe bağlı olarak katman görüntü belirten bayrak. Katmana resmi bilgi için Açıklamalar bölümüne bakın. MFC varsayılan uygulamayı ILD_NORMAL, görüntüyü arka plan rengi için resim listesi kullanarak çizer. Arka plan rengi CLR_NONE değeriyse, görüntünün saydam bir maskesi kullanılarak çizilir.

Diğer olası stilleri altında açıklanan *fStyle* üyesi [IMAGELISTDRAWPARAMS](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams) yapısı.

*dwRop*<br/>
Bir tarama işlem kodu belirten değer. Kaynak dikdörtgenin için renk verileri son rengini elde etmek hedef dikdörtgenin için renk verilerle nasıl birleştirilecek bu kodları tanımlayın. MFC'nin varsayılan uygulama, SRCCOPY, kaynak dikdörtgenin doğrudan hedef dikdörtgene kopyalar. Bu parametre yoksayılır *fStyle* parametre ILD_ROP bayrağı dahil değildir.

Diğer olası değerler altında açıklanan *dwRop* üyesi [IMAGELISTDRAWPARAMS](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams) yapısı.

*rgbBack*<br/>
Varsayılan CLR_DEFAULT görüntü arka plan rengi. Bu parametre, bir uygulama tanımlı RGB değeri veya aşağıdaki değerlerden biri olabilir:

|Değer|Açıklama|
|-----------|-------------|
|CLR_DEFAULT|Varsayılan arka plan rengi. Görüntünün görüntü listesi arka plan rengiyle çizilir.|
|CLR_NONE|Arka plan rengi. Resmin saydam olarak çizilir.|

*rgbFore*<br/>
Varsayılan CLR_DEFAULT resmi ön plan rengi. Bu parametre, bir uygulama tanımlı RGB değeri veya aşağıdaki değerlerden biri olabilir:

|Değer|Açıklama|
|-----------|-------------|
|CLR_DEFAULT|Varsayılan arka plan rengi. Görüntü, ön plan rengi olarak sistem vurgulama rengiyle çizilir.|
|CLR_NONE|Blend renk yok. Görüntüyü hedef cihaz bağlamının rengi ile harmanlanan.|

Bu parametre yalnızca, kullanılan *fStyle* ILD_BLEND25 veya ILD_BLEND50 bayrak ekler.

*fState*<br/>
Çizim durumunu belirten bayrak. Bu üye, bir veya daha fazla görüntü listesi durumu bayraklar içerebilir.

*Çerçeve*<br/>
Saturate ve alfa karıştırma efektleri davranışını etkiler.

ILS_SATURATE ile kullanıldığında, bu üye için her piksel simgesi RGB Üçlü her renk bileşeni eklenen değer tutar.

ILS_APLHA ile kullanıldığında, bu üye alfa kanalı için bir değer tutar. Bu değer, 0 ile 255, 0 tamamen saydam ve 255 tamamen opak olabilir.

*crEffect*<br/>
A [COLORREF](/windows/desktop/gdi/colorref) parlaklık ve gölge efektleri için kullanılan değer.

### <a name="return-value"></a>Dönüş Değeri

Görüntü başarıyla çizilirse TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Win32 yapısı kendiniz doldurmak istiyorsanız, ilk sürümü kullanın. Dosyanın ikinci sürümü, bir veya daha fazla MFC'nin varsayılan bağımsız değişkenler yararlanın veya yapısı yönetme kaçınmak istiyorsanız kullanın.

Bu üye işlevi tarafından belirtilen birincil görüntünün üzerine çizilmiş bir görüntü bir katmana görüntüsüdür *bir* parametresi. Kullanarak bir katman maskesi çizme [çizmek](#draw) üye işlevi kullanılarak belirtilen katman maskesi tabanlı dizine sahip [INDEXTOOVERLAYMASK](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask) makrosu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#11](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]

##  <a name="enddrag"></a>  CImageList::EndDrag

Bir sürükleme işlemi sonlandırmak için bu işlevi çağırın.

```
static void PASCAL EndDrag();
```

### <a name="remarks"></a>Açıklamalar

Bir sürükleme işlemi başlatmak için kullanmak `BeginDrag` üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#5](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]

##  <a name="extracticon"></a>  CImageList::ExtractIcon

Görüntü ve resim listesi, ilgili maskesi göre bir simge oluşturmak için bu işlevi çağırın.

```
HICON ExtractIcon(int nImage);
```

### <a name="parameters"></a>Parametreler

*Bir*<br/>
Görüntü sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simge tanıtıcı; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Bu yöntem davranışını dayanır [ImageList_ExtractIcon](/windows/desktop/api/commctrl/nf-commctrl-imagelist_extracticon) simgesini oluşturmak için. Başvurmak [ImageList_ExtractIcon](/windows/desktop/api/commctrl/nf-commctrl-imagelist_extracticon) makrosu simge oluşturma ve temizleme hakkında daha fazla bilgi için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#12](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]

##  <a name="fromhandle"></a>  CImageList::FromHandle

Bir işaretçi döndüren bir `CImageList` nesnesi bir işleyici için bir görüntü listesi verildiğinde.

```
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Parametreler

*hImageList*<br/>
Görüntü listesi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CImageList` nesne başarılı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Varsa bir `CImageList` tanıtıcı, geçici bir bağlı olmayan `CImageList` nesnesi oluşturulur ve bağlı. Bu geçici `CImageList` nesne, sonraki açışınızda uygulama boşta kalma süresi kendi olay döngüsü olana kadar aynı zamanda tüm geçici nesneler silinir yalnızca geçerlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#13](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]

##  <a name="fromhandlepermanent"></a>  CImageList::FromHandlePermanent

Bir işaretçi döndüren bir `CImageList` nesnesi bir işleyici için bir görüntü listesi verildiğinde.

```
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Parametreler

*hImageList*<br/>
Görüntü listesi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CImageList` nesne başarılı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Varsa bir `CImageList` nesne tanıtıcısını iliştirilmemiş, NULL döndürülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#14](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]

##  <a name="getbkcolor"></a>  CImageList::GetBkColor

Görüntü listesi geçerli arka plan rengini almak için bu işlevi çağırın.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

RGB renk değeri `CImageList` nesne arka plan rengi.

### <a name="example"></a>Örnek

  Örneğin bakın [CImageList::SetBkColor](#setbkcolor).

##  <a name="getdragimage"></a>  CImageList::GetDragImage

Sürükleme için kullanılan geçici görüntü listesini alır.

```
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,
    LPPOINT lpPointHotSpot);
```

### <a name="parameters"></a>Parametreler

*Lppoınt*<br/>
Adresi bir [noktası](https://msdn.microsoft.com/library/windows/desktop/dd162805) geçerli alan yapısı konuma sürükleyin.

*lpPointHotSpot*<br/>
Adresi bir `POINT` görüntüyü Sürükle Sürükle konumuna göre uzaklığı alır yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı bir işaretçi geçici görüntüye listesi, sürükleyerek; kullanılır Aksi takdirde NULL.

##  <a name="getimagecount"></a>  CImageList::GetImageCount

Görüntü listesinden görüntü sayısını almak için bu işlevi çağırın.

```
int GetImageCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görüntüleri sayısı.

### <a name="example"></a>Örnek

  Örneğin bakın [CImageList::ExtractIcon](#extracticon).

##  <a name="getimageinfo"></a>  CImageList::GetImageInfo

Görüntü hakkında bilgi almak için bu işlevi çağırın.

```
BOOL GetImageInfo(
    int nImage,
    IMAGEINFO* pImageInfo) const;
```

### <a name="parameters"></a>Parametreler

*Bir*<br/>
Görüntü sıfır tabanlı dizini.

*pImageInfo*<br/>
İşaretçi bir [IMAGEINFO](/windows/desktop/api/commctrl/ns-commctrl-_imageinfo) yapısı görüntü ile ilgili bilgileri alır. Bu yapı bilgileri, bit eşlemler görüntüsü için doğrudan yönetmek için kullanılabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

`IMAGEINFO` Yapısı bir görüntüde görüntü listesi hakkında bilgiler içerir.

##  <a name="getsafehandle"></a>  CImageList::GetSafeHandle

Almak için bu işlevi çağırın `m_hImageList` veri üyesi.

```
HIMAGELIST GetSafeHandle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eklenen resmin listesi için bir tanıtıcı; hiçbir nesne bağlıysa, bulunmazsa null değerini DÖNDÜRÜR.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#15](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]

##  <a name="m_himagelist"></a>  CImageList::m_hImageList

Bu nesneye bağlı görüntü listesinin tanıtıcı.

`HIMAGELIST m_hImageList;`

### <a name="remarks"></a>Açıklamalar

`m_hImageList` Veri üyesi HIMAGELIST türü genel değişkenidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#23](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]

##  <a name="operator_himagelist"></a>  CImageList::operator HIMAGELIST

Ekli tanıtıcısını almak için bu işleci kullanın `CImageList` nesne.

```
operator HIMAGELIST() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı, görüntü listesi için bir tanıtıcı tarafından temsil edilen varsa `CImageList` nesne; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu işleç HIMAGELIST nesne doğrudan kullanımını destekleyen bir yayım işleciyle olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#16](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]

##  <a name="read"></a>  CImageList::Read

Görüntü listesi arşivden okumak için bu işlevi çağırın.

```
BOOL Read(CArchive* pArchive);
```

### <a name="parameters"></a>Parametreler

*pArchive*<br/>
Bir işaretçi bir `CArchive` görüntü listesi olduğu okumak için nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#18](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]

##  <a name="remove"></a>  CImageList::Remove

Görüntü listesi nesneden görüntüyü kaldırmak için bu işlevi çağırın.

```
BOOL Remove(int nImage);
```

### <a name="parameters"></a>Parametreler

*Bir*<br/>
Görüntüyü kaldırmak için sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tüm öğeleri *bir* artık bir pozisyon aşağı taşıyın. Örneğin, bir görüntü listesi iki öğe içeriyorsa, ilk öğenin silinmesi artık ilk konumda kalan öğeyi neden olur. *Bir*= 0 öğenin ilk konumu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#19](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]

##  <a name="replace"></a>  CImageList::Replace

Yeni bir görüntü ile bir resimdeki bir görüntü listesi değiştirmek için bu işlevi çağırın.

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

*Bir*<br/>
Resmi Değiştir sıfır tabanlı dizini.

*pbmImage*<br/>
Bit eşlem görüntüsünü içeren bir işaretçi.

*pbmMask*<br/>
Bit eşlem maskesi içeren bir işaretçi. Maske sahip görüntü listesi kullanılırsa bu parametre yoksayılır.

*hIcon*<br/>
Bit eşlem ve yeni görüntüyü maskesinin içeren simge bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

BOOL döndüren sürüm başarılı olursa sıfır dışı değer döndürür; Aksi durumda 0.

Döndüren sürüm **int** görüntünün sıfır tabanlı dizinini döndürür, başarılıysa; değilse - 1.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi çağırdıktan sonra çağırma [SetImageCount](#setimagecount) geçerli resimler için yer tutucu yeni atamak için dizin numaralarını görüntü.

### <a name="example"></a>Örnek

  Örneğin bakın [CImageList::SetImageCount](#setimagecount).

##  <a name="setbkcolor"></a>  CImageList::SetBkColor

Görüntü listesi arka plan rengini ayarlamak için bu işlevi çağırın.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>Parametreler

*CR*<br/>
Ayarlamak için arka plan rengi. CLR_NONE olabilir. Bu durumda, görüntüleri şeffaf bir şekilde maskesi kullanılarak çizilir.

### <a name="return-value"></a>Dönüş Değeri

Önceki arka plan rengi başarılıysa; Aksi takdirde CLR_NONE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#20](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]

##  <a name="setdragcursorimage"></a>  CImageList::SetDragCursorImage

Geçerli Sürükle görüntüyü belirtilen görüntünün (genellikle bir fare imleci görüntüsü) birleştirerek yeni bir Sürükle görüntüsü oluşturur.

```
BOOL SetDragCursorImage(
    int nDrag,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>Parametreler

*Naşağıda*<br/>
Görüntüyü Sürükle ile birleştirilecek yeni görüntü dizini.

*ptHotSpot*<br/>
Etkin nokta yeni resim içindeki konumu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Sürükleme işlevleri bir sürükleme işlemi sırasında yeni görüntüyü kullandığından, Windows kullanması gereken [sayı değil geçiş](/windows/desktop/api/winuser/nf-winuser-showcursor) işlevi çağırdıktan sonra gerçek fare imleci gizlemek için `CImageList::SetDragCursorImage`. Aksi takdirde, sistem sürükleme işlemi süresince iki fare imleçleri sahip görünebilir.

##  <a name="setimagecount"></a>  CImageList::SetImageCount

Görüntü sayısını sıfırlamak için bu üye işlevi çağrısı bir `CImageList` nesne.

```
BOOL SetImageCount(UINT uNewCount);
```

### <a name="parameters"></a>Parametreler

*uNewCount*<br/>
Görüntü listesinden görüntü yeni toplam sayısını belirten değer.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Görüntü listesinden görüntü sayısını artırmak için bu üye işlevini çağırın, sonra çağırma [değiştirin](#replace) yeni dizinleri geçerli görüntüleri atamak ek her görüntü için. Geçerli görüntüleri dizinleri atamak başarısız olursa, yeni görüntüleri oluşturma çizim operations öngörülemeyen olacaktır.

Bu işlevi kullanarak bir görüntü listesi boyutu azaltırsanız, kesilmiş görüntüleri kurtulurlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#21](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]

##  <a name="setoverlayimage"></a>  CImageList::SetOverlayImage

Katman maskeleri olarak kullanılan görüntülerin listesini görüntü sıfır tabanlı dizin eklemek için bu işlevi çağırın.

```
BOOL SetOverlayImage(
    int nImage,
    int nOverlay);
```

### <a name="parameters"></a>Parametreler

*Bir*<br/>
Bir katman maskesi kullanmak için görüntünün sıfır tabanlı dizini.

*nOverlay*<br/>
Katman maskesi tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

En fazla dört dizinleri listesine eklenebilir.

Bir katman maskesi şeffaf bir şekilde başka bir görüntünün üzerine çizilmiş bir görüntüsüdür. Bir katman maskesi kullanarak bir görüntü çizme [CImageList::Draw](#draw) INDEXTOOVERLAYMASK makrosu kullanılarak belirtilen katman maskesi tabanlı dizine sahip üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#22](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]

##  <a name="write"></a>  CImageList::Write

Bir arşiv bir görüntü listesi nesne yazmak için bu işlevi çağırın.

```
BOOL Write(CArchive* pArchive);
```

### <a name="parameters"></a>Parametreler

*pArchive*<br/>
Bir işaretçi bir `CArchive` görüntü listesi olduğu depolanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CImageList#17](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CListCtrl Sınıfı](../../mfc/reference/clistctrl-class.md)<br/>
[CTabCtrl Sınıfı](../../mfc/reference/ctabctrl-class.md)
