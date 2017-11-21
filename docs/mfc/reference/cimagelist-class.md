---
title: "Cımagelist sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 07065470a7dda56650224bc794579a5038c9b643
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cimagelist-class"></a>Cımagelist sınıfı
Windows ortak görüntü listesi denetimi işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CImageList : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CImageList::CImageList](#cimagelist)|Oluşturan bir `CImageList` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CImageList::Add](#add)|Bir resim veya görüntü bir görüntü listesine ekler.|  
|[CImageList::Attach](#attach)|Bir görüntü listesi bağlayan bir `CImageList` nesnesi.|  
|[CImageList::BeginDrag](#begindrag)|Bir görüntü sürükleme başlar.|  
|[CImageList::Copy](#copy)|İçinde bir görüntü kopyalar bir `CImageList` nesnesi.|  
|[CImageList::Create](#create)|Görüntü listesi başlatır ve ekleninceye bir `CImageList` nesnesi.|  
|[CImageList::DeleteImageList](#deleteimagelist)|Görüntü listesi siler.|  
|[CImageList::DeleteTempMap](#deletetempmap)|Tarafından çağrılır [CWinApp](../../mfc/reference/cwinapp-class.md) herhangi geçici silmek için boşta kalma süresi işleyici `CImageList` tarafından oluşturulan nesne `FromHandle`.|  
|[CImageList::Detach](#detach)|Görüntü listesi nesneden çıkarır bir `CImageList` nesne ve bir resim listesi için bir işleyici döner.|  
|[CImageList::DragEnter](#dragenter)|Sürükleme işlemi sırasında güncelleştirmeleri kilitler ve belirlenen bir konuma sürükleyin görüntüsünü görüntüler.|  
|[CImageList::DragLeave](#dragleave)|Pencerenin kilidini açar ve böylece penceresi güncelleştirilebilir Sürükle görüntü gizler.|  
|[CImageList::DragMove](#dragmove)|Bir Sürükle ve bırak işlemi sırasında sürüklenen görüntü taşır.|  
|[CImageList::DragShowNolock](#dragshownolock)|Gösterir veya pencere kilitlemeden Sürükle görüntü sürükleme işlemi sırasında gizler.|  
|[CImageList::Draw](#draw)|Bir Sürükle ve bırak işlemi sırasında sürüklenen resim çizer.|  
|[CImageList::DrawEx](#drawex)|Bir görüntü liste öğesi belirtilen cihaz bağlamında çizer. İşlevi, belirtilen çizim stili kullanır ve belirtilen renk görüntüsüyle karıştırır.|  
|[CImageList::DrawIndirect](#drawindirect)|Resim listesinden resim çizer.|  
|[CImageList::EndDrag](#enddrag)|Sürükleme işlemi sonlandırır.|  
|[CImageList::ExtractIcon](#extracticon)|Bir resim ve görüntü listesi maskesinde göre bir simge oluşturur.|  
|[CImageList::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CImageList` nesnesi tanıtıcı bir resim listesi verildiğinde. Varsa bir `CImageList` nesne tanıtıcısını, geçici bir iliştirilmemiş `CImageList` nesnesi oluşturulur ve bağlı.|  
|[CImageList::FromHandlePermanent](#fromhandlepermanent)|Bir işaretçi döndüren bir `CImageList` nesnesi tanıtıcı bir resim listesi verildiğinde. Varsa bir `CImageList` nesne tanıtıcısını, iliştirilmemiş **NULL** döndürülür.|  
|[CImageList::GetBkColor](#getbkcolor)|Görüntü listesi geçerli arka plan rengini alır.|  
|[CImageList::GetDragImage](#getdragimage)|Sürükleme için kullanılan geçici resim listesi alır.|  
|[CImageList::GetImageCount](#getimagecount)|Görüntü listesi görüntü sayısını alır.|  
|[CImageList::GetImageInfo](#getimageinfo)|Bir görüntü ile ilgili bilgileri alır.|  
|[CImageList::GetSafeHandle](#getsafehandle)|Alır **m_hImageList**.|  
|[CImageList::Read](#read)|Görüntü listesi arşivden okur.|  
|[CImageList::Remove](#remove)|Görüntü listesinden görüntü kaldırır.|  
|[CImageList::Replace](#replace)|Görüntü listesi görüntüdeki yeni bir görüntü ile değiştirir.|  
|[CImageList::SetBkColor](#setbkcolor)|Görüntü listesi arka plan rengini belirler.|  
|[CImageList::SetDragCursorImage](#setdragcursorimage)|Yeni bir Sürükle görüntüsü oluşturur.|  
|[CImageList::SetImageCount](#setimagecount)|Görüntü listesi görüntülerinde sayısını sıfırlar.|  
|[CImageList::SetOverlayImage](#setoverlayimage)|Görüntünün sıfır tabanlı dizini katmana maskeleri olarak kullanılacak görüntüleri listesine ekler.|  
|[CImageList::Write](#write)|Görüntü listesi arşive yazar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CImageList::operator HIMAGELIST](#operator_himagelist)|Döndürür `HIMAGELIST` bağlı `CImageList`.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CImageList::m_hImageList](#m_himagelist)|Bu nesneye bağlı görüntü listesi içeren bir tanıtıcı.|  
  
## <a name="remarks"></a>Açıklamalar  
 "Görüntü listesi", her biri için sıfır tabanlı diziniyle göre başvurulabilen aynı boyuta sahip görüntüleri koleksiyonudur. Görüntü listeleri simgeler veya bit eşlemler büyük kümelerini verimli bir şekilde yönetmek için kullanılır. Görüntü listesi tüm görüntüleri geniş, tek bit eşlem ekran aygıt biçiminde yer alır. Görüntü listesi görüntüleri şeffaf bir şekilde çizmek için kullanılan maskeleri (simge stil) içeren tek renkli bir bit eşlem de içerebilir. Microsoft Win32 uygulama programlama arabirimi (API) görüntü çizme, oluşturmak ve görüntü listeleri yok, eklemek ve görüntülerini Kaldır, görüntüleri değiştirmeyi, görüntüleri birleştirme ve görüntüleri sürükleme sağlayan görüntü listesi işlevleri sağlar.  
  
 Bu denetim (ve bu nedenle `CImageList` sınıfı) yalnızca Windows 95/98 ve Windows NT sürüm 3.51 altında çalışan programları için kullanılabilir ve üzerinde desteklenir.  
  
 Kullanma hakkında daha fazla bilgi için `CImageList`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [kullanarak Cımagelist](../../mfc/using-cimagelist.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CImageList`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="add"></a>CImageList::Add  
 Bir veya daha fazla görüntü veya bir simge bir görüntü listesine eklemek için bu işlevini çağırın.  
  
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
 `pbmImage`  
 Görüntüyü ya da görüntüleri içeren bit eşlem işaretçi. Görüntü sayısını bit eşlem genişliği algılanır.  
  
 `pbmMask`  
 Maske içeren bit eşlem işaretçi. Hiçbir maskesi ile resim listesi kullanılırsa, bu parametre yoksayılır.  
  
 `crMask`  
 Maske oluşturmak için kullanılan rengi. Belirtilen bit eşlem renkte her pikseli siyah olarak değiştirilir ve karşılık gelen bit maskesi bir olarak ayarlayın.  
  
 `hIcon`  
 Bit eşlem ve yeni görüntüyü maskesini içeren simge işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk yeni görüntüyü başarılıysa sıfır tabanlı dizini; Aksi takdirde - 1.  
  
### <a name="remarks"></a>Açıklamalar  
 İşiniz bittiğinde ile simgesi işleyici bırakılıyor için sorumlu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#1](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]  
  
##  <a name="attach"></a>CImageList::Attach  
 Bir görüntü listesine eklemek için bu işlevi çağırmak bir `CImageList` nesnesi.  
  
```  
BOOL Attach(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Parametreler  
 `hImageList`  
 Bir resim listesi nesnesi için bir tanıtıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eki başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#2](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]  
  
##  <a name="begindrag"></a>CImageList::BeginDrag  
 Bir görüntü sürükleme başlamak için bu işlevini çağırın.  
  
```  
BOOL BeginDrag(
    int nImage,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>Parametreler  
 `nImage`  
 Görüntünün sürüklemek için sıfır tabanlı dizini.  
  
 `ptHotSpot`  
 Başlangıç Sürükle konumu (genellikle, imleç konumu) koordinatları. Koordinatlar sol üst köşedeki görüntünün göre belirlenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev sürükleme için kullanılan geçici resim listesi oluşturur. Görüntüyü belirtilen görüntü ve onun maskesi geçerli imleç birleştirir. Yanıt olarak sonraki `WM_MOUSEMOVE` iletileri kullanarak sürükle görüntü taşıyabilirsiniz `DragMove` üye işlevi. Sürükleme işlemi sona erdirmek için kullanabileceğiniz `EndDrag` üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#3](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]  
  
##  <a name="cimagelist"></a>CImageList::CImageList  
 Oluşturan bir `CImageList` nesnesi.  
  
```  
CImageList();
```  
  
##  <a name="copy"></a>CImageList::Copy  
 Bu üye işlevi Win32 işlevi davranışını uygulayan [ImageList_Copy](http://msdn.microsoft.com/library/windows/desktop/bb761520), Windows SDK'ın açıklandığı gibi.  
  
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
 *iDst*  
 Kopyalama işleminin hedefi olarak kullanılacak görüntüyü sıfır tabanlı dizini.  
  
 `iSrc`  
 Kopyalama işlemi, kaynağı olarak kullanılacak görüntüyü sıfır tabanlı dizini.  
  
 `uFlags`  
 Kopyalama işlemi yapılmasına türünü belirtir bit bayrak değeri. Bu parametre aşağıdaki değerlerden biri olabilir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|`ILCF_MOVE`|Kaynak görüntü hedef görüntünün dizinine kopyalanır. Bu işlem belirli bir görüntü birden çok örneğini sonuçlanır. `ILCF_MOVE`varsayılandır.|  
|`ILCF_SWAP`|Kaynak ve hedef görüntüleri konumlar görüntü listesi içinde exchange.|  
  
 `pSrc`  
 Bir işaretçi bir `CImageList` kopyalama işleminin hedefi olan nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#6](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]  
  
##  <a name="create"></a>CImageList::Create  
 Görüntü listesi başlatır ve ekleninceye bir [Cımagelist](../../mfc/reference/cimagelist-class.md) nesnesi.  
  
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
 `cx`  
 Piksel cinsinden her görüntü boyutları.  
  
 `cy`  
 Piksel cinsinden her görüntü boyutları.  
  
 `nFlags`  
 Resim listesi oluşturmak için türünü belirtir. Bu parametre aşağıdaki değerlerden bir bileşimi olabilir, ancak yalnızca birini içerebilir `ILC_COLOR` değerleri.  
  
|Değer|Açıklama|  
|-----------|-------------|  
|`ILC_COLOR`|Varsayılan davranış diğer hiçbiri kullanırsanız `ILC_COLOR`* bayrakları belirtilir. Genellikle, varsayılan değer `ILC_COLOR4`; ancak daha eski görüntü sürücüler için varsayılan `ILC_COLORDDB`.|  
|`ILC_COLOR4`|Bir 4-bit (16 renk) CİHAZDAN bağımsız bit eşlem (DIB) bölümü için resim listesi bit eşlem'i kullanın.|  
|`ILC_COLOR8`|Bir 8 bit DIB bölümü kullanın. Renk tablosu için kullanılan renkler, aynı noktalı palet renkleri olur.|  
|`ILC_COLOR16`|16 bit kullanın (32 / 64k renk) DIB bölümü.|  
|`ILC_COLOR24`|24 bit DIB bölümü kullanın.|  
|`ILC_COLOR32`|32-bit DIB bölümü kullanın.|  
|`ILC_COLORDDB`|Bir aygıt bit eşlem kullanın.|  
|`ILC_MASK`|Maske kullanır. Resim listesi biri maske olarak kullanılan tek renkli bir bit eşlem olan iki bitmap içerir. Bu değer dahil edilmezse, yalnızca bir bit eşlem resim listesi içerir. Bkz: [resim listesi çizim görüntülerden](../../mfc/drawing-images-from-an-image-list.md) maskelenmiş görüntüler hakkında ek bilgi için.|  
  
 `nInitial`  
 Resim listesi başlangıçta içerir, görüntü sayısı.  
  
 `nGrow`  
 Sistemin yeni görüntüleri için yer açmak için listedeki yeniden boyutlandırmak gerektiğinde resim listesi'tarafından büyüyebileceği görüntüleri sayısı. Bu parametre yeniden boyutlandırılan resim listesi içerebilir yeni görüntü sayısını temsil eder.  
  
 `nBitmapID`  
 Resim listesi ile ilişkilendirilecek kaynak kimlikleri bitmap.  
  
 `crMask`  
 Maske oluşturmak için kullanılan rengi. Belirtilen bit eşlem renkte her pikseli siyah değiştirilir ve karşılık gelen bit maskesi bir olarak ayarlayın.  
  
 `lpszBitmapID`  
 Kaynak kimlikleri görüntülerinin içeren bir dize.  
  
 `imagelist1`  
 Bir başvuru bir `CImageList` nesnesi.  
  
 `nImage1`  
 İlk mevcut görüntü dizini.  
  
 `imagelist2`  
 Bir başvuru bir `CImageList` nesnesi.  
  
 `nImage2`  
 İkinci mevcut görüntü dizini.  
  
 `dx`  
 İkinci görüntüsünün piksel cinsinden ilk görüntüsüne ilişkisindeki ekseninin uzaklık.  
  
 `dy`  
 İkinci görüntüsünün piksel cinsinden ilk görüntüsüne ilişkisindeki y ekseninin uzaklık.  
  
 `pImageList`  
 Bir işaretçi bir `CImageList` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CImageList` iki adımda. İlk olarak, Oluşturucusu arayın ve ardından arama `Create`, resim listesi oluşturur ve ekler `CImageList` nesnesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#7](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]  
  
##  <a name="deleteimagelist"></a>CImageList::DeleteImageList  
 Görüntü listesi silmek için bu işlevini çağırın.  
  
```  
BOOL DeleteImageList();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#8](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]  
  
##  <a name="deletetempmap"></a>CImageList::DeleteTempMap  
 Tarafından otomatik olarak çağrılır `CWinApp` boşta kalma süresi işleyici `DeleteTempMap` herhangi geçici siler `CImageList` tarafından oluşturulan nesneler [FromHandle](#fromhandle), tanıtıcıları silmiyor ancak ( `hImageList`) geçici olarak ilişkili ile **ImageList** nesneleri.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#9](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]  
  
##  <a name="detach"></a>CImageList::Detach  
 Görüntü listesi nesneden ayırmak için bu işlevi çağırmak bir `CImageList` nesnesi.  
  
```  
HIMAGELIST Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir resim listesi nesnesi için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev bir tanıtıcı için resim listesi nesnesi döndürür.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CImageList::Attach](#attach).  
  
##  <a name="dragenter"></a>CImageList::DragEnter  
 Sürükleme işlemi sırasında tarafından belirtilen pencere güncelleştirmeleri kilitler `pWndLock` ve tarafından belirtilen konumdaki Sürükle görüntü görüntüler `point`.  
  
```  
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWndLock`  
 İşaretçi Sürükle görüntü sahibi penceresine.  
  
 `point`  
 Sürükleme görüntü görüntülenecek da konumunda. Koordinatlar (istemci alanını değil) penceresinin sol üst köşesindeki göre belirlenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınır, başlık çubuğu ve menü çubuğunda, gibi pencere öğeleri genişlikleri koordinatları belirtirken dengelemek gerekir böylece koordinatlar pencerenin sol üst köşesinin göre belirlenir.  
  
 Varsa `pWndLock` olan **NULL**, bu işlev, Masaüstü penceresiyle ilişkili görüntü bağlamda resim çizer ve koordinatlar ekranın sol üst köşesinde göre belirlenir.  
  
 Bu işlev sürükleme işlemi sırasında verilen penceresine diğer tüm güncelleştirmeleri kilitler. Sürükle ve bırak işlemi, hedef vurgulama gibi bir sürükleme işlemi sırasında herhangi bir çizim yapmanız gerekirse, geçici olarak sürüklenen görüntü kullanarak gizleyebilirsiniz [CImageList::DragLeave](#dragleave) işlevi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CImageList::BeginDrag](#begindrag).  
  
##  <a name="dragleave"></a>CImageList::DragLeave  
 Tarafından belirtilen pencere kilidini açarak `pWndLock` ve güncelleştirilmesi için penceresini izin vererek Sürükle görüntünün gizler.  
  
```  
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWndLock`  
 İşaretçi Sürükle görüntü sahibi penceresine.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CImageList::EndDrag](#enddrag).  
  
##  <a name="dragmove"></a>CImageList::DragMove  
 Bir Sürükle ve bırak işlemi sırasında sürüklenen görüntüyü taşımak için bu işlevini çağırın.  
  
```  
static BOOL PASCAL DragMove(CPoint pt);
```  
  
### <a name="parameters"></a>Parametreler  
 `pt`  
 Yeni konuma sürükleyin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev genellikle yanıt olarak adlandırılır bir `WM_MOUSEMOVE` ileti. Sürükleme işlemi başlatmak için kullanmak `BeginDrag` üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#4](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]  
  
##  <a name="dragshownolock"></a>CImageList::DragShowNolock  
 Gösterir veya pencere kilitlemeden Sürükle görüntü sürükleme işlemi sırasında gizler.  
  
```  
static BOOL PASCAL DragShowNolock(BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 `bShow`  
 Sürükleme görüntü gösterilecek olup olmadığını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 [CImageList::DragEnter](#dragenter) işlevi bir sürükleme işlemi sırasında tüm güncelleştirmeleri penceresine kilitler. Bu işlev penceresi ancak kilit yok.  
  
##  <a name="draw"></a>CImageList::Draw  
 Bir Sürükle ve bırak işlemi sırasında sürüklenen resim çizmek için bu işlevini çağırın.  
  
```  
BOOL Draw(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Hedef cihaz bağlamı işaretçi.  
  
 `nImage`  
 Görüntünün çizmek için sıfır tabanlı dizini.  
  
 `pt`  
 Belirtilen aygıt bağlamı içinde çizmek konumu.  
  
 `nStyle`  
 Çizim stili belirten bayrak. Bir veya daha fazla şu değerlerden biri olabilir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|`ILD_BLEND25`, **ILD_FOCUS**|Sistem vurgulama renk ile yüzde 25'i karıştırma resim çizer. Resim listesi maske içermiyorsa, bu değer bir etkisi yoktur.|  
|`ILD_BLEND50`, **ILD_SELECTED**, **ILD_BLEND**|Yüzde 50'sistem vurgulama renk ile karıştırma resim çizer. Resim listesi maske içermiyorsa, bu değer bir etkisi yoktur.|  
|**ILD_MASK**|Maske çizer.|  
|`ILD_NORMAL`|Arka plan rengi için resim listesi kullanma resim çizer. Arka plan rengini ise `CLR_NONE` değeri, resmin saydam maskesi kullanılarak çizilir.|  
|`ILD_TRANSPARENT`|Saydam arka plan rengini bakılmaksızın maskesi kullanarak resim çizer.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CImageList::SetOverlayImage](#setoverlayimage).  
  
##  <a name="drawex"></a>CImageList::DrawEx  
 Bir görüntü liste öğesi belirtilen cihaz bağlamında çizer.  
  
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
 `pDC`  
 Hedef cihaz bağlamı işaretçi.  
  
 `nImage`  
 Görüntünün çizmek için sıfır tabanlı dizini.  
  
 `pt`  
 Belirtilen aygıt bağlamı içinde çizmek konumu.  
  
 `sz`  
 Görüntünün sol üst köşesindeki göre çizmek için görüntünün kısmı boyutu. Bkz: `dx` ve *GN* içinde [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) Windows SDK.  
  
 *clrBk*  
 Görüntü, arka plan rengi. Bkz: *rgbBk* içinde [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) Windows SDK'sındaki.  
  
 *clrFg*  
 Görüntü arka plan rengi. Bkz: *rgbFg* içinde [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) Windows SDK'sındaki.  
  
 `nStyle`  
 Çizim stili belirten bayrak. Bkz: *fStyle* içinde [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) Windows SDK'sındaki.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevi, belirtilen çizim stili kullanır ve belirtilen renk görüntüsüyle karıştırır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#10](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]  
  
##  <a name="drawindirect"></a>CImageList::DrawIndirect  
 Resim listesinden resim çizme için bu üye işlevini çağırın.  
  
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
 *pimldp*  
 Bir işaretçi bir [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) çizim işlemiyle ilgili bilgi içeren yapısı.  
  
 `pDC`  
 Hedef cihaz bağlamı için bir işaretçi. Bu silmelisiniz [CDC](../../mfc/reference/cdc-class.md) nesnesi ile bittiğinde.  
  
 `nImage`  
 Çizilecek görüntünün sıfır tabanlı dizini.  
  
 `pt`  
 A [noktası](http://msdn.microsoft.com/library/windows/desktop/dd162805) x ve y-burada görüntü çizilmiş koordinatları içeren yapısı.  
  
 `sz`  
 A [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) çizilecek görüntü boyutunu belirten yapısı.  
  
 *ptOrigin*  
 A [noktası](http://msdn.microsoft.com/library/windows/desktop/dd162805) x ve y-resim çizim katmanlandırmasının sol üst köşesinin belirtme koordinatları içeren yapısı. X koordinatını ve y koordinatını üstünde sol olan görüntüsünün piksel çizilmiş değil.  
  
 `fStyle`  
 Çizim stili ve isteğe bağlı olarak katmana görüntü belirten bayrak. Katmana görüntüde bilgi için Açıklamalar bölümüne bakın. MFC varsayılan uygulaması `ILD_NORMAL`, arka plan rengi için resim listesi kullanma resim çizer. Arka plan rengini ise `CLR_NONE` değeri, resmin saydam bir maskesi kullanılarak çizilir.  
  
 Diğer olası stilleri altında açıklanan **fStyle** üyesi [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) yapısı.  
  
 *dwRop*  
 Bir tarama işlem kodu belirten değer. Bu kodları kaynak dikdörtgen renk verilerini son renk elde etmek için hedef dikdörtgeni rengi veri ile nasıl birleştirilebilir tanımlayın. MFC'nin varsayılan uygulaması, **SRCCOPY**, doğrudan hedef dikdörtgenin kaynak dikdörtgen kopyalar. Bu parametre yoksayılır `fStyle` parametre içermez **ILD_ROP** bayrağı.  
  
 Diğer olası değerler altında açıklanan **dwRop** üyesi [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) yapısı.  
  
 *rgbBack*  
 Görüntü arka plan rengi, varsayılan olarak `CLR_DEFAULT`. Bu parametre, bir uygulama tanımlı RGB değeri veya şu değerlerden biri olabilir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|`CLR_DEFAULT`|Varsayılan arka plan rengi. Görüntünün görüntü listesi arka plan rengini kullanarak çizilir.|  
|`CLR_NONE`|Arka plan rengi. Resmin saydam olarak çizilir.|  
  
 *rgbFore*  
 Ön plan rengini varsayılan görüntü `CLR_DEFAULT`. Bu parametre, bir uygulama tanımlı RGB değeri veya şu değerlerden biri olabilir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|`CLR_DEFAULT`|Varsayılan arka plan rengi. Görüntü ön plan rengini sistem vurgulama renk kullanarak çizilir.|  
|`CLR_NONE`|Hiçbir Karışım rengi. Görüntüyü hedef cihaz bağlamı renkle karıştırılan.|  
  
 Bu parametre yalnızca kullanılır `fStyle` içeren `ILD_BLEND25` veya `ILD_BLEND50` bayrağı.  
  
 *fState*  
 Çizim durumunu belirten bayrak. Bu üye, bir veya daha fazla görüntü listesi durumu bayraklar içerebilir.  
  
 *Çerçeve*  
 Saturate ve Alfa karışım efektleri davranışını etkiler.  
  
 İle kullanıldığında **ILS_SATURATE**, bu üye RGB Üçlü her piksel simgesi için her bir renk bileşeninin eklenme değeri tutar.  
  
 İle kullanıldığında **ILS_APLHA**, bu üye alfa kanal değeri tutar. Bu değer, 0 tamamen saydam ve 255 tamamen opak 255 için 0'dan olabilir.  
  
 *crEffect*  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Işıma ve gölge efektleri için kullanılan değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** görüntü başarıyla çizilmiş; Aksi takdirde ise **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Win32 yapısı kendiniz doldurmak istiyorsanız, ilk sürümü kullanın. Bir veya daha fazla MFC'nin varsayılan bağımsız değişkenler yararlanmak veya yapısı yönetme önlemek istiyorsanız ikinci sürümü kullanın.  
  
 Bu üye işlevi tarafından belirtilen birincil görüntüsü üstünde çizilmiş görüntünün bir katmana görüntüdür `nImage` parametresi. Bir katmana maskesi kullanarak çizin [çizin](#draw) üye işlevi kullanılarak belirtilen katmana maskesi tabanlı diziniyle [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) makrosu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#11](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]  
  
##  <a name="enddrag"></a>CImageList::EndDrag  
 Sürükleme işlemi sonlandırmak için bu işlevini çağırın.  
  
```  
static void PASCAL EndDrag();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sürükleme işlemi başlatmak için kullanmak `BeginDrag` üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#5](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]  
  
##  <a name="extracticon"></a>CImageList::ExtractIcon  
 Bir görüntü ile ilgili maskesi bir görüntü listesinde dayalı bir simge oluşturmak için bu işlevini çağırın.  
  
```  
HICON ExtractIcon(int nImage);
```  
  
### <a name="parameters"></a>Parametreler  
 `nImage`  
 Görüntünün sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa simgesi tanıtıcısı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem davranışını kullanır [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401) makrosu simgesini oluşturmak için. Başvurmak [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401) makrosu simgesi oluşturma ve temizleme hakkında daha fazla bilgi için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#12](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]  
  
##  <a name="fromhandle"></a>CImageList::FromHandle  
 Bir işaretçi döndüren bir `CImageList` nesnesi tanıtıcı bir resim listesi verildiğinde.  
  
```  
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Parametreler  
 `hImageList`  
 Resim listesi belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CImageList` nesne başarılı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa bir `CImageList` tanıtıcıyı, geçici bir bağlı olmayan `CImageList` nesnesi oluşturulur ve bağlı. Bu geçici `CImageList` nesnesi, sonraki açışınızda uygulama boşta kalma süresi, olay döngüde olana kadar aynı zamanda tüm geçici nesneler silinir yalnızca geçerli.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#13](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]  
  
##  <a name="fromhandlepermanent"></a>CImageList::FromHandlePermanent  
 Bir işaretçi döndüren bir `CImageList` nesnesi tanıtıcı bir resim listesi verildiğinde.  
  
```  
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Parametreler  
 `hImageList`  
 Resim listesi belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CImageList` nesne başarılı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa bir `CImageList` nesne tanıtıcısını, iliştirilmemiş **NULL** döndürülür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#14](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]  
  
##  <a name="getbkcolor"></a>CImageList::GetBkColor  
 Görüntü listesi geçerli arka plan rengini almak için bu işlevini çağırın.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 RGB renk değerini `CImageList` nesne arka plan rengi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CImageList::SetBkColor](#setbkcolor).  
  
##  <a name="getdragimage"></a>CImageList::GetDragImage  
 Sürükleme için kullanılan geçici resim listesi alır.  
  
```  
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,  
    LPPOINT lpPointHotSpot);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpPoint`  
 Adres bir [noktası](http://msdn.microsoft.com/library/windows/desktop/dd162805) geçerli alan yapısı konuma sürükleyin.  
  
 *lpPointHotSpot*  
 Adres bir **noktası** sürükleme görüntü sürükleme konumuna göre uzaklığı alır yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı bir işaretçi geçici resim listesi, sürükleme için; kullanılır Aksi takdirde, **NULL**.  
  
##  <a name="getimagecount"></a>CImageList::GetImageCount  
 Görüntü listesi görüntü sayısını almak için bu işlevini çağırın.  
  
```  
int GetImageCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görüntüleri sayısı.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CImageList::ExtractIcon](#extracticon).  
  
##  <a name="getimageinfo"></a>CImageList::GetImageInfo  
 Bir görüntü ile ilgili bilgileri almak için bu işlevini çağırın.  
  
```  
BOOL GetImageInfo(
    int nImage,  
    IMAGEINFO* pImageInfo) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nImage`  
 Görüntünün sıfır tabanlı dizini.  
  
 *pImageInfo*  
 İşaretçi bir [IMAGEINFO](http://msdn.microsoft.com/library/windows/desktop/bb761393) yapısı görüntü ile ilgili bilgileri alır. Bu yapı bilgileri doğrudan görüntüsü için bit eşlemler işlemek için kullanılabilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `IMAGEINFO` Yapısı bir resim listesi görüntüdeki hakkında bilgiler içerir.  
  
##  <a name="getsafehandle"></a>CImageList::GetSafeHandle  
 Almak için bu işlevi çağırmak **m_hImageList** veri üyesi.  
  
```  
HIMAGELIST GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ekli resim listesi için bir tanıtıcı; Aksi takdirde **NULL** hiçbir nesne bağlıysa.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#15](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]  
  
##  <a name="m_himagelist"></a>CImageList::m_hImageList  
 Bu nesneye bağlı görüntü listesi tanıtıcısı.  
  
 **HIMAGELIST m_hImageList;**  
  
### <a name="remarks"></a>Açıklamalar  
 **M_hImageList** veri üyesi olan bir ortak değişken türü `HIMAGELIST`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#23](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]  
  
##  <a name="operator_himagelist"></a>CImageList::operator HIMAGELIST  
 Ekli işleyicisini almak için bu işleci kullanın `CImageList` nesnesi.  
  
```  
operator HIMAGELIST() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, resim listesi için bir tanıtıcı tarafından temsil edilen varsa `CImageList` nesne; Aksi halde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç doğrudan kullanımını destekleyen bir atama işleci olan bir `HIMAGELIST` nesnesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#16](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]  
  
##  <a name="read"></a>CImageList::Read  
 Görüntü listesi arşivden okumak için bu işlevini çağırın.  
  
```  
BOOL Read(CArchive* pArchive);
```  
  
### <a name="parameters"></a>Parametreler  
 `pArchive`  
 Bir işaretçi bir `CArchive` resim listesi olduğu okumak için nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#18](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]  
  
##  <a name="remove"></a>CImageList::Remove  
 Görüntü listesi nesneden görüntüyü kaldırmak için bu işlevini çağırın.  
  
```  
BOOL Remove(int nImage);
```  
  
### <a name="parameters"></a>Parametreler  
 `nImage`  
 Görüntünün kaldırmak için sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 İzleyen tüm öğeleri `nImage` şimdi bir konum aşağı taşıma. Örneğin, bir resim listesi iki öğeler içeriyorsa, ilk öğe silinmesi şimdi ilk konumda kalan öğeyi neden olur. `nImage`ilk konumda öğesi için 0 =.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#19](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]  
  
##  <a name="replace"></a>CImageList::Replace  
 Görüntü listesi görüntüdeki ile yeni bir imaj değiştirmek için bu işlevini çağırın.  
  
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
 `nImage`  
 Değiştirmek için görüntünün sıfır tabanlı dizini.  
  
 `pbmImage`  
 Görüntüyü içeren bit eşlem için bir işaretçi.  
  
 `pbmMask`  
 Maske içeren bit eşlem için bir işaretçi. Hiçbir maskesi ile resim listesi kullanılırsa, bu parametre yoksayılır.  
  
 `hIcon`  
 Bit eşlem ve yeni görüntüyü maskesini içeren simge için bir tanıtıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürme sürüm **BOOL** sıfır olmayan başarılı; Aksi halde 0 durumunda döndürür.  
  
 Döndürme sürüm `int` görüntünün sıfır tabanlı dizinini döndürür başarılı - değilse 1.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevini çağırın çağrıldıktan sonra [SetImageCount](#setimagecount) yer tutucu geçerli görüntüleri yeni atamak için dizin numaralarını görüntü.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CImageList::SetImageCount](#setimagecount).  
  
##  <a name="setbkcolor"></a>CImageList::SetBkColor  
 Görüntü listesi arka plan rengini ayarlamak için bu işlevini çağırın.  
  
```  
COLORREF SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>Parametreler  
 `cr`  
 Ayarlamak için arka plan rengi. Bu olabilir `CLR_NONE`. Bu durumda, görüntüleri saydam maskesi kullanılarak çizilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki arka plan rengi başarılıysa; Aksi takdirde `CLR_NONE`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#20](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]  
  
##  <a name="setdragcursorimage"></a>CImageList::SetDragCursorImage  
 Geçerli Sürükle görüntüsüyle verilen görüntünün (genellikle bir fare imleci görüntüsü) birleştirerek yeni bir Sürükle görüntüsü oluşturur.  
  
```  
BOOL SetDragCursorImage(
    int nDrag,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>Parametreler  
 *nDrag*  
 Sürükleme görüntüsüyle birleştirilecek yeni görüntü dizini.  
  
 `ptHotSpot`  
 Etkin nokta yeni görüntüyü içindeki konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Sürükleme işlevleri sürükleme işlemi sırasında yeni görüntüyü kullandığından, Windows'un kullanması gereken [sayı değil geçiş](http://msdn.microsoft.com/library/windows/desktop/ms648396) çağrıldıktan sonra gerçek fare imlecini gizlemek için işlevi `CImageList::SetDragCursorImage`. Aksi takdirde, sistem iki fare imleçleri sürükleme işlemi boyunca görüntülenebilir.  
  
##  <a name="setimagecount"></a>CImageList::SetImageCount  
 Görüntü sayısını sıfırlamak için bu üye işlevini çağırın bir `CImageList` nesnesi.  
  
```  
BOOL SetImageCount(UINT uNewCount);
```  
  
### <a name="parameters"></a>Parametreler  
 *uNewCount*  
 Görüntü listesinde görüntüleri yeni toplam sayısını belirten değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Resim listesi görüntülerinde sayısını artırmak için bu üye işlevini çağırın, ardından çağıran [Değiştir](#replace) yeni dizinler geçerli görüntülere atamak her ek görüntüsünün. Geçerli görüntülere dizinleri atamak başarısız olursa yeni görüntüler oluşturmak çizim işlemleri öngörülemez olacaktır.  
  
 Bu işlevi kullanarak bir görüntü listesi boyutunu azaltırsanız kesilmiş görüntüleri kurtulurlar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#21](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]  
  
##  <a name="setoverlayimage"></a>CImageList::SetOverlayImage  
 Görüntünün sıfır tabanlı dizini katmana maskeleri olarak kullanılacak görüntüleri listesine eklemek için bu işlevini çağırın.  
  
```  
BOOL SetOverlayImage(
    int nImage,  
    int nOverlay);
```  
  
### <a name="parameters"></a>Parametreler  
 `nImage`  
 Bir katmana maske olarak kullanılacak görüntünün sıfır tabanlı dizini.  
  
 *nOverlay*  
 Bir katmana maskesi tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 En fazla dört dizinlerini listesine eklenebilir.  
  
 Bir katmana maskesi saydam başka bir görüntü çizilmiş resimdir. Bir katmana maskesi kullanarak bir görüntünün üzerinde çizin [CImageList::Draw](#draw) üye işlevi kullanılarak belirtilen katmana maskesi tabanlı diziniyle **INDEXTOOVERLAYMASK** makrosu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#22](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]  
  
##  <a name="write"></a>CImageList::Write  
 Bir resim listesi nesnesi arşive yazmak için bu işlevini çağırın.  
  
```  
BOOL Write(CArchive* pArchive);
```  
  
### <a name="parameters"></a>Parametreler  
 `pArchive`  
 Bir işaretçi bir `CArchive` resim listesi olduğu depolanması için nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CImageList#17](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CListCtrl sınıfı](../../mfc/reference/clistctrl-class.md)   
 [CTabCtrl sınıfı](../../mfc/reference/ctabctrl-class.md)
