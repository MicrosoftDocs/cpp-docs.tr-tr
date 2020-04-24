---
title: CRgn Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CRgn
- AFXWIN/CRgn
- AFXWIN/CRgn::CRgn
- AFXWIN/CRgn::CombineRgn
- AFXWIN/CRgn::CopyRgn
- AFXWIN/CRgn::CreateEllipticRgn
- AFXWIN/CRgn::CreateEllipticRgnIndirect
- AFXWIN/CRgn::CreateFromData
- AFXWIN/CRgn::CreateFromPath
- AFXWIN/CRgn::CreatePolygonRgn
- AFXWIN/CRgn::CreatePolyPolygonRgn
- AFXWIN/CRgn::CreateRectRgn
- AFXWIN/CRgn::CreateRectRgnIndirect
- AFXWIN/CRgn::CreateRoundRectRgn
- AFXWIN/CRgn::EqualRgn
- AFXWIN/CRgn::FromHandle
- AFXWIN/CRgn::GetRegionData
- AFXWIN/CRgn::GetRgnBox
- AFXWIN/CRgn::OffsetRgn
- AFXWIN/CRgn::PtInRegion
- AFXWIN/CRgn::RectInRegion
- AFXWIN/CRgn::SetRectRgn
helpviewer_keywords:
- CRgn [MFC], CRgn
- CRgn [MFC], CombineRgn
- CRgn [MFC], CopyRgn
- CRgn [MFC], CreateEllipticRgn
- CRgn [MFC], CreateEllipticRgnIndirect
- CRgn [MFC], CreateFromData
- CRgn [MFC], CreateFromPath
- CRgn [MFC], CreatePolygonRgn
- CRgn [MFC], CreatePolyPolygonRgn
- CRgn [MFC], CreateRectRgn
- CRgn [MFC], CreateRectRgnIndirect
- CRgn [MFC], CreateRoundRectRgn
- CRgn [MFC], EqualRgn
- CRgn [MFC], FromHandle
- CRgn [MFC], GetRegionData
- CRgn [MFC], GetRgnBox
- CRgn [MFC], OffsetRgn
- CRgn [MFC], PtInRegion
- CRgn [MFC], RectInRegion
- CRgn [MFC], SetRectRgn
ms.assetid: d904da84-76aa-481e-8780-b09485f49e64
ms.openlocfilehash: e84526eec8f4fd4b1935fa39bc7f4ed3c4d5dd71
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754481"
---
# <a name="crgn-class"></a>CRgn Sınıfı

Bir Windows grafik aygıtı arabirimi (GDI) bölgesini kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CRgn : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CRgn::CRgn](#crgn)|Bir `CRgn` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRgn::CombineRgn](#combinergn)|Bir `CRgn` nesneyi, belirtilen `CRgn` iki nesnenin birleşimine eşdeğer olacak şekilde ayarlar.|
|[CRgn::CopyRgn](#copyrgn)|Nesneyi, `CRgn` belirtilen `CRgn` bir nesnenin kopyası olacak şekilde ayarlar.|
|[CRgn::CreateEllipticRgn](#createellipticrgn)|Eliptik `CRgn` bir bölge ile bir nesne başharfleri.|
|[CRgn::CreateEllipticRgnDolaylı](#createellipticrgnindirect)|[RECT](/windows/win32/api/windef/ns-windef-rect) yapısı `CRgn` tarafından tanımlanan eliptik bir bölge ile bir nesneyi başharfe çeker.|
|[CRgn::CreateFromData](#createfromdata)|Verilen bölgeden ve dönüşüm verilerinden bir bölge oluşturur.|
|[CRgn::CreateFromPath](#createfrompath)|Verilen aygıt bağlamına seçilen yoldan bir bölge oluşturur.|
|[CRgn::CreatePolygonRgn](#createpolygonrgn)|Çokgen bir `CRgn` bölge ile bir nesne baş harfize eder. Sistem, gerekirse, son tepe noktasından ilk tepeye bir çizgi çizerek çokgeni otomatik olarak kapatır.|
|[CRgn::CreatePolypolygonRgn](#createpolypolygonrgn)|Bir dizi `CRgn` kapalı çokgenden oluşan bir bölgeye sahip bir nesneyi başharfe ait hale. Çokgenler kopuk olabilir veya çakışabilir.|
|[CRgn::CreateRectRgn](#createrectrgn)|Dikdörtgen bir `CRgn` bölge ile bir nesne başharfleri.|
|[CRgn::CreateRectRgnDolaylı](#createrectrgnindirect)|`CRgn` [RECT](/windows/win32/api/windef/ns-windef-rect)tructure ile tanımlanan dikdörtgen bir bölge ile bir nesneyi başharfe çeker.|
|[CRgn::CreateRoundRectRgn](#createroundrectrgn)|Yuvarlak köşeli `CRgn` dikdörtgen bir bölge ile bir nesne baş harfize eder.|
|[CRgn::EqualRgn](#equalrgn)|Eşdeğer `CRgn` olup olmadıklarını belirlemek için iki nesneyi denetler.|
|[CRgn::FromHandle](#fromhandle)|Bir Windows bölgesine tanıtıcı verildiğinde bir `CRgn` nesneye işaretçi döndürür.|
|[CRgn::GetRegionData](#getregiondata)|Belirtilen arabelleği verilen bölgeyi açıklayan verilerle doldurur.|
|[CRgn::GetRgnBox](#getrgnbox)|Bir `CRgn` nesnenin sınırlayıcı dikdörtgeninin koordinatlarını alır.|
|[CRgn::OfsetRgn](#offsetrgn)|Nesneyi `CRgn` belirtilen uzaklıklara göre taşır.|
|[CRgn::PtInRegion](#ptinregion)|Bölgede belirli bir nokta olup olmadığını belirler.|
|[CRgn::RectInRegion](#rectinregion)|Belirtilen dikdörtgenin herhangi bir bölümünün bölge sınırları içinde olup olmadığını belirler.|
|[CRgn::SetRectRgn](#setrectrgn)|Nesneyi `CRgn` belirtilen dikdörtgen bölgeye ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CRgn::operatör HRGN](#operator_hrgn)|Nesnede bulunan Windows `CRgn` tutamacını döndürür.|

## <a name="remarks"></a>Açıklamalar

Bölge, pencere içindeki eliptik veya çokgen bir alandır. Bölgeleri kullanmak için sınıfın üye işlevlerini, sınıfın `CRgn` `CDC`üyeleri olarak tanımlanan kırpma işlevleriyle kullanırsınız.

Oluşturdukları, `CRgn` değiştirdikleri ve aldıkları bölge nesnesi hakkında bilgi almanın üye işlevleri.

Kullanma `CRgn`hakkında daha fazla bilgi için [Bkz. Grafik Nesneler.](../../mfc/graphic-objects.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cgdiobject](../../mfc/reference/cgdiobject-class.md)

`CRgn`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="crgncombinergn"></a><a name="combinergn"></a>CRgn::CombineRgn

Varolan iki bölgeyi birleştirerek yeni bir GDI bölgesi oluşturur.

```
int CombineRgn(
    CRgn* pRgn1,
    CRgn* pRgn2,
    int nCombineMode);
```

### <a name="parameters"></a>Parametreler

*pRgn1*<br/>
Varolan bir bölgeyi tanımlar.

*pRgn2*<br/>
Varolan bir bölgeyi tanımlar.

*nCombineMode*<br/>
İki kaynak bölgeyi birleştirirken gerçekleştirilecek işlemi belirtir. Aşağıdaki değerlerden herhangi biri olabilir:

- RGN_AND Her iki bölgenin çakışan alanlarını kullanır (kesişim).

- RGN_COPY Bölge 1 'in bir kopyasını oluşturur *(pRgn1*ile tanımlanır).

- RGN_DIFF Bölge 1 *(pRgn1*ile tanımlanan) bölge 2 'nin parçası olmayan *(pRgn2*ile tanımlanan) alanlarından oluşan bir bölge oluşturur.

- RGN_OR her iki bölgeyi de bütünüyle (birleşim) birleştirir.

- RGN_XOR Her iki bölgeyi de birleştirir, ancak çakışan alanları kaldırır.

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan bölgenin türünü belirtir. Aşağıdaki değerlerden biri olabilir:

- COMPLEXREGION Yeni bölgenin üst üste binen sınırları vardır.

- HATA Yeni bölge oluşturulmama.

- NULLREGION Yeni bölge boş.

- SIMPLEREGION Yeni bölgenin çakışan sınırları yoktur.

### <a name="remarks"></a>Açıklamalar

Bölgeler *nCombineMode*tarafından belirtildiği gibi birleştirilir.

Belirtilen iki bölge birleştirilir ve ortaya çıkan bölge tanıtıcısı `CRgn` nesnede depolanır. Böylece, `CRgn` nesnede depolanan bölge ne olursa olsun, birleştirilmiş bölge ile değiştirilir.

Bir bölgenin boyutu 32.767 ile 32.767 mantıksal birim veya 64K bellek ile sınırlıdır( hangisi daha küçükse).

Bir bölgeyi başka bir bölgeye kopyalamak için [CopyRgn'i](#copyrgn) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/cpp/crgn-class_1.cpp)]

## <a name="crgncopyrgn"></a><a name="copyrgn"></a>CRgn::CopyRgn

*pRgnSrc* tarafından tanımlanan bölgeyi nesneye `CRgn` kopyalar.

```
int CopyRgn(CRgn* pRgnSrc);
```

### <a name="parameters"></a>Parametreler

*pRgnSrc*<br/>
Varolan bir bölgeyi tanımlar.

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan bölgenin türünü belirtir. Aşağıdaki değerlerden biri olabilir:

- COMPLEXREGION Yeni bölgenin üst üste binen sınırları vardır.

- HATA Yeni bölge oluşturulmama.

- NULLREGION Yeni bölge boş.

- SIMPLEREGION Yeni bölgenin çakışan sınırları yoktur.

### <a name="remarks"></a>Açıklamalar

Yeni bölge, daha önce `CRgn` nesnede depolanan bölgenin yerini alır. Bu işlev [CombineRgn](#combinergn) üye işlevinin özel bir örneğidir.

### <a name="example"></a>Örnek

  CRgn için örnek [bakın:CreateEllipticRgn](#createellipticrgn).

## <a name="crgncreateellipticrgn"></a><a name="createellipticrgn"></a>CRgn::CreateEllipticRgn

Eliptik bir bölge oluşturur.

```
BOOL CreateEllipticRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>Parametreler

*x1*<br/>
Elipsin sınırlayıcı dikdörtgeninin sol üst köşesindeki mantıksal x-koordinatını belirtir.

*y1*<br/>
Elipsin sınırlayıcı dikdörtgeninin sol üst köşesindeki mantıksal y-koordinatını belirtir.

*x2*<br/>
Elipsin sınırlayıcı dikdörtgeninin sağ alt köşesinin mantıksal x-koordinatını belirtir.

*y2*<br/>
Elipsin sınırlayıcı dikdörtgeninin sağ alt köşesinin mantıksal y-koordinatını belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bölge *x1*, *y1*, *x2*, ve *y2*ile belirtilen sınırlayıcı dikdörtgen ile tanımlanır. Bölge `CRgn` nesnede depolanır.

Bir bölgenin boyutu 32.767 ile 32.767 mantıksal birim veya 64K bellek ile sınırlıdır( hangisi daha küçükse).

`CreateEllipticRgn` İşlevle oluşturulan bir bölgeyi kullanmayı bitirdiğinde, bir uygulama aygıtın bağlamının `DeleteObject` dışına bölge seçmeli ve işlevi kaldırmak için kullanmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/cpp/crgn-class_2.cpp)]

## <a name="crgncreateellipticrgnindirect"></a><a name="createellipticrgnindirect"></a>CRgn::CreateEllipticRgnDolaylı

Eliptik bir bölge oluşturur.

```
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*Lprect*<br/>
Elipsin `RECT` sınırlayan `CRect` dikdörtgeninin sol üst ve alt-sağ köşelerinin mantıksal koordinatlarını içeren bir yapıya veya nesneye işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bölge, *lpRect* tarafından işaret edilen yapı veya nesne tarafından `CRgn` tanımlanır ve nesnede depolanır.

Bir bölgenin boyutu 32.767 ile 32.767 mantıksal birim veya 64K bellek ile sınırlıdır( hangisi daha küçükse).

`CreateEllipticRgnIndirect` İşlevle oluşturulan bir bölgeyi kullanmayı bitirdiğinde, bir uygulama aygıtın bağlamının `DeleteObject` dışına bölge seçmeli ve işlevi kaldırmak için kullanmalıdır.

### <a name="example"></a>Örnek

  CRgn için örnek [bakınız::CreateRectRgnDolaylı](#createrectrgnindirect).

## <a name="crgncreatefromdata"></a><a name="createfromdata"></a>CRgn::CreateFromData

Verilen bölgeden ve dönüşüm verilerinden bir bölge oluşturur.

```
BOOL CreateFromData(
    const XFORM* lpXForm,
    int nCount,
    const RGNDATA* pRgnData);
```

### <a name="parameters"></a>Parametreler

*lpXForm*<br/>
Bölgede yapılacak dönüşümü tanımlayan bir [XFORM](/windows/win32/api/wingdi/ns-wingdi-xform)ata yapısına işaret eder. Bu işaretçi NULL ise, kimlik dönüşümü kullanılır.

*nSayısı*<br/>
*pRgnData*tarafından işaret edilen bayt sayısını belirtir.

*pRgnData*<br/>
Bölge verilerini içeren bir [RGNDATA](/windows/win32/api/wingdi/ns-wingdi-rgndata) veri yapısına işaret ediyor.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir uygulama `CRgn::GetRegionData` işlevi çağırarak bir bölge için veri alabilir.

## <a name="crgncreatefrompath"></a><a name="createfrompath"></a>CRgn::CreateFromPath

Verilen aygıt bağlamına seçilen yoldan bir bölge oluşturur.

```
BOOL CreateFromPath(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Kapalı yol içeren bir aygıt bağlamı tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

*pDC* parametresi tarafından tanımlanan aygıt bağlamı kapalı bir yol içermelidir. Bir `CreateFromPath` yolu bir bölgeye dönüştürdükten sonra, Windows kapalı yolu aygıt bağlamından atar.

## <a name="crgncreatepolygonrgn"></a><a name="createpolygonrgn"></a>CRgn::CreatePolygonRgn

Çokgen bir bölge oluşturur.

```
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,
    int nCount,
    int nMode);
```

### <a name="parameters"></a>Parametreler

*Lppoints*<br/>
Bir dizi `POINT` yapıya veya bir `CPoint` nesne dizisini işaret eder. Her yapı, çokgenin bir tepe noktasının x-koordinatını ve y-koordinatını belirtir. Yapı `POINT` aşağıdaki forma sahiptir:

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*nSayısı*<br/>
*LPPoints*tarafından işaret `POINT` edilen `CPoint` dizideki yapıların veya nesnelerin sayısını belirtir.

*nMode*<br/>
Bölge için dolum modunu belirtir. Bu parametre ALTERNATİf veya WINDING olabilir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Sistem, gerekirse, son tepe noktasından ilk tepeye bir çizgi çizerek çokgeni otomatik olarak kapatır. Ortaya çıkan bölge `CRgn` nesnede depolanır.

Bir bölgenin boyutu 32.767 ile 32.767 mantıksal birim veya 64K bellek ile sınırlıdır( hangisi daha küçükse).

Çokgen doldurma modu ALTERNATE olduğunda, sistem her tetkik satırında tek numaralı ve çift numaralı çokgen kenarlar arasındaki alanı doldurur. Diğer bir tarihte, sistem birinci ve ikinci taraf arasındaki alanı, üçüncü ve dördüncü taraf arasındaki alanı doldurur, ve saire.

Çokgen doldurma modu SARMA olduğunda, sistem bir alanı doldurup doldurmayacağını belirlemek için bir şeklin çizildiği yönü kullanır. Çokgendeki her çizgi kesimi saat yönünde veya saat yönünün tersine çizilir. Kapalı bir alandan bir figürün dışına çizilen hayali bir çizgi saat yönünde bir çizgi parçasından geçse, bir sayı artımlanır. Hat saat yönünün tersine bir çizgi parçasından geçtiğinde, sayım azat edilir. Satır şeklin dışına ulaştığında sayım sıfır değilse alan doldurulur.

Bir uygulama `CreatePolygonRgn` işlevle oluşturulan bir bölge kullanmayı bitirdiğinde, aygıtın bağlamının dışına `DeleteObject` bölge seçmeli ve onu kaldırmak için işlevi kullanmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#146](../../mfc/codesnippet/cpp/crgn-class_3.cpp)]

## <a name="crgncreatepolypolygonrgn"></a><a name="createpolypolygonrgn"></a>CRgn::CreatePolypolygonRgn

Kapalı çokgenlerden oluşan bir bölge oluşturur.

```
BOOL CreatePolyPolygonRgn(
    LPPOINT lpPoints,
    LPINT lpPolyCounts,
    int nCount,
    int nPolyFillMode);
```

### <a name="parameters"></a>Parametreler

*Lppoints*<br/>
Çokgenlerin `POINT` tepe noktalarını tanımlayan `CPoint` bir dizi yapıya veya nesnelere işaret eder. Sistem bunları otomatik olarak kapatmadığından, her çokgenin açıkça kapatılması gerekir. Çokgenler art arda belirtilir. Yapı `POINT` aşağıdaki forma sahiptir:

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*lpPolyCounts*<br/>
Bir dizi tümseci işaret eder. İlk tamsayı *lpPoints* dizisindeki ilk çokgendeki vertices sayısını, ikinci tamsayı ikinci çokgendeki vertices sayısını ve benzeri belirtir.

*nSayısı*<br/>
*lpPolyCounts* dizisindeki toplam tamsayı sayısını belirtir.

*nPolyFillMode*<br/>
Çokgen dolum modunu belirtir. Bu değer ALTERNATİf veya SARMA olabilir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Ortaya çıkan bölge `CRgn` nesnede depolanır.

Çokgenler kopuk olabilir veya çakışabilir.

Bir bölgenin boyutu 32.767 ile 32.767 mantıksal birim veya 64K bellek ile sınırlıdır( hangisi daha küçükse).

Çokgen doldurma modu ALTERNATE olduğunda, sistem her tetkik satırında tek numaralı ve çift numaralı çokgen kenarlar arasındaki alanı doldurur. Diğer bir tarihte, sistem birinci ve ikinci taraf arasındaki alanı, üçüncü ve dördüncü taraf arasındaki alanı doldurur, ve saire.

Çokgen doldurma modu SARMA olduğunda, sistem bir alanı doldurup doldurmayacağını belirlemek için bir şeklin çizildiği yönü kullanır. Çokgendeki her çizgi kesimi saat yönünde veya saat yönünün tersine çizilir. Kapalı bir alandan bir figürün dışına çizilen hayali bir çizgi saat yönünde bir çizgi parçasından geçse, bir sayı artımlanır. Hat saat yönünün tersine bir çizgi parçasından geçtiğinde, sayım azat edilir. Satır şeklin dışına ulaştığında sayım sıfır değilse alan doldurulur.

Bir uygulama `CreatePolyPolygonRgn` işlevle oluşturulan bir bölgeyi kullanmayı bitirdiğinde, aygıtın bağlamının dışına bölge seçmeli ve kaldırmak için [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) üye işlevini kullanmalıdır.

## <a name="crgncreaterectrgn"></a><a name="createrectrgn"></a>CRgn::CreateRectRgn

`CRgn` Nesnede depolanan dikdörtgen bir bölge oluşturur.

```
BOOL CreateRectRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>Parametreler

*x1*<br/>
Bölgenin sol üst köşesindeki mantıksal x-koordinatını belirtir.

*y1*<br/>
Bölgenin sol üst köşesindeki mantıksal y-koordinatını belirtir.

*x2*<br/>
Bölgenin sağ alt köşesinin mantıksal x-koordinatını belirtir.

*y2*<br/>
Bölgenin sağ alt köşesinin mantıksal y-koordinatını belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir bölgenin boyutu 32.767 ile 32.767 mantıksal birim veya 64K bellek ile sınırlıdır( hangisi daha küçükse).

Tarafından oluşturulan bir bölge kullanılarak `CreateRectRgn`tamamlandığında, bir uygulama [cgdiobject kullanmalıdır::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) üye işlevi bölge kaldırmak için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/cpp/crgn-class_4.cpp)]

Ek bir örnek için [crgn::CombineRgn'ye](#combinergn)bakın.

## <a name="crgncreaterectrgnindirect"></a><a name="createrectrgnindirect"></a>CRgn::CreateRectRgnDolaylı

`CRgn` Nesnede depolanan dikdörtgen bir bölge oluşturur.

```
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*Lprect*<br/>
Bölgenin sol `RECT` üst `CRect` ve alt sağ köşelerinin mantıksal koordinatlarını içeren bir yapıya veya nesneye işaret eder. Yapı `RECT` aşağıdaki forma sahiptir:

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir bölgenin boyutu 32.767 ile 32.767 mantıksal birim veya 64K bellek ile sınırlıdır( hangisi daha küçükse).

Tarafından oluşturulan bir bölge kullanılarak `CreateRectRgnIndirect`tamamlandığında, bir uygulama [cgdiobject kullanmalıdır::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) üye işlevi bölge kaldırmak için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#148](../../mfc/codesnippet/cpp/crgn-class_5.cpp)]

## <a name="crgncreateroundrectrgn"></a><a name="createroundrectrgn"></a>CRgn::CreateRoundRectRgn

`CRgn` Nesnede depolanan yuvarlak köşeleri olan dikdörtgen bir bölge oluşturur.

```
BOOL CreateRoundRectRgn(
    int x1,
    int y1,
    int x2,
    int y2,
    int x3,
    int y3);
```

### <a name="parameters"></a>Parametreler

*x1*<br/>
Bölgenin sol üst köşesindeki mantıksal x-koordinatını belirtir.

*y1*<br/>
Bölgenin sol üst köşesindeki mantıksal y-koordinatını belirtir.

*x2*<br/>
Bölgenin sağ alt köşesinin mantıksal x-koordinatını belirtir.

*y2*<br/>
Bölgenin sağ alt köşesinin mantıksal y-koordinatını belirtir.

*x3*<br/>
Yuvarlatılmış köşeleri oluşturmak için kullanılan elipsin genişliğini belirtir.

*y3*<br/>
Yuvarlatılmış köşeleri oluşturmak için kullanılan elipsin yüksekliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir bölgenin boyutu 32.767 ile 32.767 mantıksal birim veya 64K bellek ile sınırlıdır( hangisi daha küçükse).

Bir uygulama `CreateRoundRectRgn` işlevle oluşturulan bir bölgeyi kullanmayı bitirdiğinde, aygıtın bağlamının dışına bölge seçmeli ve kaldırmak için [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) üye işlevini kullanmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/cpp/crgn-class_6.cpp)]

## <a name="crgncrgn"></a><a name="crgn"></a>CRgn::CRgn

Bir `CRgn` nesne inşa eder.

```
CRgn();
```

### <a name="remarks"></a>Açıklamalar

`m_hObject` Nesne diğer `CRgn` üye işlevlerden biri veya daha fazlası ile baş harfe çevrilene kadar veri üyesi geçerli bir Windows GDI bölgesi içermez.

### <a name="example"></a>Örnek

  CRgn için örnek [bakınız::CreateRoundRectRgn](#createroundrectrgn).

## <a name="crgnequalrgn"></a><a name="equalrgn"></a>CRgn::EqualRgn

Verilen bölgenin `CRgn` nesnede depolanan bölgeye eşdeğer olup olmadığını belirler.

```
BOOL EqualRgn(CRgn* pRgn) const;
```

### <a name="parameters"></a>Parametreler

*pRgn*<br/>
Bir bölgeyi tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İki bölge eşdeğerse sıfır olmayan; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/cpp/crgn-class_7.cpp)]

## <a name="crgnfromhandle"></a><a name="fromhandle"></a>CRgn::FromHandle

Bir Windows bölgesine tanıtıcı verildiğinde bir `CRgn` nesneye işaretçi döndürür.

```
static CRgn* PASCAL FromHandle(HRGN hRgn);
```

### <a name="parameters"></a>Parametreler

*hRgn*<br/>
Bir Windows bölgesine bir tanıtıcı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir `CRgn` nesneye işaretçi. İşlev başarılı olmadıysa, iade değeri NULL'dur.

### <a name="remarks"></a>Açıklamalar

Bir `CRgn` nesne tutamacına zaten eklenmiş değilse, geçici `CRgn` bir nesne oluşturulur ve eklenir. Bu `CRgn` geçici nesne yalnızca, uygulamanın olay döngüsünde boşta kalma süresine sahip olduğu ve tüm geçici grafik nesnelerinin silindiği bir sonraki zamana kadar geçerlidir. Bunu söylemenin başka bir yolu, geçici nesnenin yalnızca bir pencere iletisinin işlenmesi sırasında geçerli olmasıdır.

## <a name="crgngetregiondata"></a><a name="getregiondata"></a>CRgn::GetRegionData

Belirtilen arabelleği bölgeyi açıklayan verilerle doldurur.

```
int GetRegionData(
    LPRGNDATA lpRgnData,
    int nCount) const;
```

### <a name="parameters"></a>Parametreler

*lpRgnData*<br/>
Bilgileri alan [bir RGNDATA](/windows/win32/api/wingdi/ns-wingdi-rgndata) veri yapısına işaret ediyor. Bu parametre NULL ise, iade değeri bölge verileri için gereken bayt sayısını içerir.

*nSayısı*<br/>
*lpRgnData* arabelleği boyutu, bayt, belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa ve *nCount* yeterli sayıda bayt belirtirse, iade değeri her zaman *nCount'dir.* İşlev başarısız olursa veya *nCount* yeterli bayt sayısından daha az belirtirse, iade değeri 0'dır (hata).

### <a name="remarks"></a>Açıklamalar

Bu veriler, bölgeyi oluşturan dikdörtgenlerin boyutlarını içerir. Bu işlev `CRgn::CreateFromData` işlevle birlikte kullanılır.

## <a name="crgngetrgnbox"></a><a name="getrgnbox"></a>CRgn::GetRgnBox

`CRgn` Nesnenin sınırlayıcı dikdörtgeninin koordinatlarını alır.

```
int GetRgnBox(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*Lprect*<br/>
Sınırlayan `RECT` dikdörtgenin `CRect` koordinatlarını almak için bir yapıya veya nesneye işaret eder. Yapı `RECT` aşağıdaki forma sahiptir:

`typedef struct tagRECT {`

`int left;`

`int top;`

`int right;`

`int bottom;`

`} RECT;`

### <a name="return-value"></a>Dönüş Değeri

Bölgenin türünü belirtir. Aşağıdaki değerlerden herhangi biri olabilir:

- COMPLEXREGION Bölge çakışan sınırları vardır.

- NULLREGION Bölgesi boş.

- ERROR `CRgn` nesnesi geçerli bir bölge belirtmez.

- SIMPLEREGION Bölge çakışan kenarlıkları vardır.

### <a name="example"></a>Örnek

  CRgn için örnek [bakınız::CreatePolygonRgn](#createpolygonrgn).

## <a name="crgnoffsetrgn"></a><a name="offsetrgn"></a>CRgn::OfsetRgn

`CRgn` Nesnede depolanan bölgeyi belirtilen uzaklıklarla hareket ettirir.

```
int OffsetRgn(
    int x,
    int y);

int OffsetRgn(POINT point);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Sola veya sağa hareket ettirecek birim sayısını belirtir.

*Y*<br/>
Yukarı veya aşağı hareket etmek için birim sayısını belirtir.

*Nokta*<br/>
*Noktanın* x-koordinatı sola veya sağa hareket etmek için birim sayısını belirtir. *Noktanın* y-koordinatı yukarı veya aşağı hareket etmek için birim sayısını belirtir. *Nokta* parametresi bir `POINT` yapı veya `CPoint` nesne olabilir.

### <a name="return-value"></a>Dönüş Değeri

Yeni bölgenin türü. Aşağıdaki değerlerden herhangi biri olabilir:

- COMPLEXREGION Bölge çakışan sınırları vardır.

- HATA Bölge işlaması geçerli değildir.

- NULLREGION Bölgesi boş.

- SIMPLEREGION Bölge çakışan kenarlıkları vardır.

### <a name="remarks"></a>Açıklamalar

İşlev, bölge *x* birimlerini x ekseni boyunca, *y* birimlerini ise y ekseni boyunca hareket ettirir.

Bir bölgenin koordinat değerleri 32.767'den az veya eşit ve -32.768'den büyük veya eşit olmalıdır. Geçersiz bölge koordinatlarını önlemek için *x* ve *y* parametreleri dikkatle seçilmelidir.

### <a name="example"></a>Örnek

  CRgn için örnek [bakın:CreateEllipticRgn](#createellipticrgn).

## <a name="crgnoperator-hrgn"></a><a name="operator_hrgn"></a>CRgn::operatör HRGN

`CRgn` Nesnenin ekli Windows GDI tutamacını almak için bu işleci kullanın.

```
operator HRGN() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, nesne tarafından temsil edilen Windows `CRgn` GDI nesnesine bir tanıtıcı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu işleç, bir HRGN nesnesinin doğrudan kullanımını destekleyen bir döküm operatörüdür.

Grafik nesneleri kullanma hakkında daha fazla bilgi için Windows SDK'daki [Grafik Nesneler](/windows/win32/gdi/graphic-objects) makalesine bakın.

## <a name="crgnptinregion"></a><a name="ptinregion"></a>CRgn::PtInRegion

*x* ve *y* tarafından verilen noktanın `CRgn` nesnede depolanan bölgede olup olmadığını denetler.

```
BOOL PtInRegion(
    int x,
    int y) const;

BOOL PtInRegion(POINT point) const;
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Test etmek için noktanın mantıksal x-koordinatını belirtir.

*Y*<br/>
Test etmek için noktanın mantıksal y-koordinatını belirtir.

*Nokta*<br/>
*Noktanın* x- ve y-koordinatları, noktanın değerini test etmek için noktanın x- ve y-koordinatlarını belirtir. *Nokta* parametresi bir `POINT` yapı veya `CPoint` nesne olabilir.

### <a name="return-value"></a>Dönüş Değeri

Nokta bölgede ise sıfır değil; aksi takdirde 0.

## <a name="crgnrectinregion"></a><a name="rectinregion"></a>CRgn::RectInRegion

*lpRect* tarafından belirtilen dikdörtgenin herhangi bir bölümünün `CRgn` nesnede depolanan bölgenin sınırları içinde olup olmadığını belirler.

```
BOOL RectInRegion(LPCRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*Lprect*<br/>
Bir `RECT` yapıyı `CRect` veya nesneyi işaret edin. Yapı `RECT` aşağıdaki forma sahiptir:

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dikdörtgenin herhangi bir bölümü bölge sınırları içinde yatıyorsa sıfır olmayan; aksi takdirde 0.

## <a name="crgnsetrectrgn"></a><a name="setrectrgn"></a>CRgn::SetRectRgn

Dikdörtgen bir bölge oluşturur.

```cpp
void SetRectRgn(
    int x1,
    int y1,
    int x2,
    int y2);

void SetRectRgn(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*x1*<br/>
Dikdörtgen bölgenin sol üst köşesinin x-koordinatını belirtir.

*y1*<br/>
Dikdörtgen bölgenin sol üst köşesinin y-koordinatını belirtir.

*x2*<br/>
Dikdörtgen bölgenin sağ alt köşesinin x-koordinatını belirtir.

*y2*<br/>
Dikdörtgen bölgenin sağ alt köşesinin y-koordinatını belirtir.

*Lprect*<br/>
Dikdörtgen bölgeyi belirtir. Bir `RECT` yapıya veya `CRect` nesneye işaretçi olabilir.

### <a name="remarks"></a>Açıklamalar

[CreateRectRgn](#createrectrgn)aksine, ancak, yerel Windows uygulama yığınından herhangi bir ek bellek ayırmaz. Bunun yerine, `CRgn` nesnede depolanan bölge için ayrılan alanı kullanır. Bu, nesnenin `CRgn` aramadan `SetRectRgn`önce geçerli bir Windows bölgesiyle zaten baş harflere paralaştırılmış olması gerektiği anlamına gelir. *x1*, *y1*, *x2*ve *y2* tarafından verilen noktalar, ayrılan alanın minimum boyutunu belirtir.

Yerel bellek yöneticisine `CreateRectRgn` yapılan çağrıları önlemek için üye işlev yerine bu işlevi kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
