---
title: CRgn sınıfı
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
ms.openlocfilehash: 66721f34a8ac2b6dac6addcfa04a88b46a37ee60
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916824"
---
# <a name="crgn-class"></a>CRgn sınıfı

Bir Windows grafik cihaz arabirimi (GDI) bölgesini kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CRgn : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRgn:: CRgn](#crgn)|Bir `CRgn` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRgn:: CombineRgn](#combinergn)|Bir `CRgn` nesneyi belirtilen `CRgn` iki nesnenin birleşimi ile eşdeğer olacak şekilde ayarlar.|
|[CRgn:: CopyRgn](#copyrgn)|Bir `CRgn` nesneyi belirtilen `CRgn` nesnenin kopyası olacak şekilde ayarlar.|
|[CRgn:: CreateEllipticRgn](#createellipticrgn)|Elips bölge `CRgn` içeren bir nesnesi başlatır.|
|[CRgn:: CreateEllipticRgnIndirect](#createellipticrgnindirect)|Bir Rect `CRgn` yapısı tarafından tanımlanan elips bölge ile bir nesne [](/windows/desktop/api/windef/ns-windef-tagrect) başlatır.|
|[CRgn:: CreateFromData](#createfromdata)|Verilen bölge ve dönüşüm verilerinden bir bölge oluşturur.|
|[CRgn:: CreateFromPath](#createfrompath)|Verilen cihaz bağlamına seçili olan yoldan bir bölge oluşturur.|
|[CRgn:: CreatePolygonRgn](#createpolygonrgn)|`CRgn` Bir nesneyi Çokgen bölge ile başlatır. Sistem, gerekirse, en son köşenin ilk köşesini bir çizgi çizerek otomatik olarak çokgeni kapatır.|
|[CRgn:: CreatePolyPolygonRgn](#createpolypolygonrgn)|Kapalı çokgenlerin bulunduğu bir bölgeden oluşan bir nesneyibaşlatır.`CRgn` Çokgenler kopuk olabilir veya örtüşebilir.|
|[CRgn:: CreateRectRgn](#createrectrgn)|Dikdörtgen bir `CRgn` bölgeyle bir nesne başlatır.|
|[CRgn:: Createrectrgndolaylı](#createrectrgnindirect)|Bir Rect `CRgn` yapısı tarafından tanımlanan dikdörtgen bölge ile bir nesneyi [](/windows/desktop/api/windef/ns-windef-tagrect) başlatır.|
|[CRgn:: CreateRoundRectRgn](#createroundrectrgn)|Yuvarlak köşeler `CRgn` içeren dikdörtgen bölge içeren bir nesneyi başlatır.|
|[CRgn:: EqualRgn](#equalrgn)|Eşdeğer olup `CRgn` olmadığını anlamak için iki nesneyi denetler.|
|[CRgn:: FromHandle](#fromhandle)|Bir Windows bölgesine bir tanıtıcı `CRgn` verildiğinde, nesne için bir işaretçi döndürür.|
|[CRgn:: GetRegionData](#getregiondata)|Belirtilen bir bölgeyi tanımlayan verilerle belirtilen arabelleği doldurur.|
|[CRgn:: GetRgnBox](#getrgnbox)|Bir `CRgn` nesnenin sınırlayıcı dikdörtgeninin koordinatlarını alır.|
|[CRgn:: OffsetRgn](#offsetrgn)|Bir `CRgn` nesneyi belirtilen uzaklıklara göre kaydırır.|
|[CRgn::P tInRegion](#ptinregion)|Belirtilen noktanın bölgede olup olmadığını belirler.|
|[CRgn:: Recınregion](#rectinregion)|Belirtilen dikdörtgenin herhangi bir kısmının bölge sınırları içinde olup olmadığını belirler.|
|[CRgn:: SetRectRgn](#setrectrgn)|`CRgn` Nesneyi belirtilen dikdörtgen bölgeye ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CRgn:: operator HRGN](#operator_hrgn)|`CRgn` Nesnesinde içerilen Windows işleyicisini döndürür.|

## <a name="remarks"></a>Açıklamalar

Bölge, bir pencere içindeki elips veya Çokgen bir alandır. Bölgeleri kullanmak için, sınıfının üye işlevlerini `CRgn` sınıfının `CDC`üyeleri olarak tanımlanan kırpma işlevleriyle birlikte kullanırsınız.

Aranan bölge nesnesi hakkında `CRgn` bilgi oluşturma, değiştirme ve alma için üye işlevleri.

Kullanma `CRgn`hakkında daha fazla bilgi için bkz. [grafik nesneleri](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CRgn`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="combinergn"></a>CRgn:: CombineRgn

Mevcut iki bölgeyi birleştirerek yeni bir GDI bölgesi oluşturur.

```
int CombineRgn(
    CRgn* pRgn1,
    CRgn* pRgn2,
    int nCombineMode);
```

### <a name="parameters"></a>Parametreler

*pRgn1*<br/>
Mevcut bir bölgeyi tanımlar.

*pRgn2*<br/>
Mevcut bir bölgeyi tanımlar.

*nCombineMode*<br/>
İki kaynak bölge birleştirilirken gerçekleştirilecek işlemi belirtir. Aşağıdaki değerlerden herhangi biri olabilir:

- RGN_AND her iki bölgenin de örtüşen alanları kullanır (kesişme).

- RGN_COPY, bölge 1 ' in bir kopyasını oluşturur ( *pRgn1*tarafından tanımlanır).

- RGN_DIFF, bölge 2 ' nin ( *pRgn2*tarafından tanımlanan) parçası olmayan bölge 1 ' ın ( *pRgn1*tarafından tanımlanan) alanlarından oluşan bir bölge oluşturur.

- RGN_OR her iki bölgeyi de tamamen (UNION) birleştirir.

- RGN_XOR her iki bölgeyi de birleştirir, ancak çakışan alanları kaldırır.

### <a name="return-value"></a>Dönüş Değeri

Elde edilen bölgenin türünü belirtir. Aşağıdaki değerlerden biri olabilir:

- COMPLEXREGION yeni bölgesinde çakışan kenarlıklar vardır.

- Yeni bölge oluşturma hatası.

- NULLREGION yeni bölgesi boş.

- Yeni bölgedeki SIMPLEREGIÇAKıŞAN kenarlık yok.

### <a name="remarks"></a>Açıklamalar

Bölgeler, *nCombineMode*tarafından belirtilen şekilde birleştirilir.

Belirtilen iki bölge birleştirilir ve sonuçta elde edilen bölge tutamacı `CRgn` nesnesinde depolanır. Bu nedenle, `CRgn` nesnesinde depolanan her bölge birleştirilmiş bölge ile değiştirilmiştir.

Bir bölgenin boyutu, 32.767 mantıksal birim veya 64K bellek, hangisi daha küçükse, 32.767 ile sınırlıdır.

Yalnızca bir bölgeyi başka bir bölgeye kopyalamak için [CopyRgn](#copyrgn) komutunu kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/cpp/crgn-class_1.cpp)]

##  <a name="copyrgn"></a>CRgn:: CopyRgn

*Prgnsrc* `CRgn` tarafından tanımlanan bölgeyi nesnesine kopyalar.

```
int CopyRgn(CRgn* pRgnSrc);
```

### <a name="parameters"></a>Parametreler

*pRgnSrc*<br/>
Mevcut bir bölgeyi tanımlar.

### <a name="return-value"></a>Dönüş Değeri

Elde edilen bölgenin türünü belirtir. Aşağıdaki değerlerden biri olabilir:

- COMPLEXREGION yeni bölgesinde çakışan kenarlıklar vardır.

- Yeni bölge oluşturma hatası.

- NULLREGION yeni bölgesi boş.

- Yeni bölgedeki SIMPLEREGIÇAKıŞAN kenarlık yok.

### <a name="remarks"></a>Açıklamalar

Yeni bölge, daha önce `CRgn` nesnede depolanan bölgenin yerini alır. Bu işlev, [CombineRgn](#combinergn) member işlevinin özel bir durumdur.

### <a name="example"></a>Örnek

  [CRgn:: CreateEllipticRgn](#createellipticrgn)için örneğe bakın.

##  <a name="createellipticrgn"></a>CRgn:: CreateEllipticRgn

Elips bölge oluşturur.

```
BOOL CreateEllipticRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>Parametreler

*x1*<br/>
Elipsin sınırlayıcı dikdörtgeninin sol üst köşesinin mantıksal x koordinatını belirtir.

*Y1*<br/>
Elipsin sınırlayıcı dikdörtgeninin sol üst köşesinin mantıksal y koordinatını belirtir.

*x2*<br/>
Elipsin sınırlayıcı dikdörtgeninin sağ alt köşesinin mantıksal x koordinatını belirtir.

*Y2*<br/>
Elipsin sınırlayıcı dikdörtgeninin sağ alt köşesinin mantıksal y koordinatını belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bölge, *x1*, *Y1*, *x2*ve *Y2*tarafından belirtilen sınırlayıcı dikdörtgen tarafından tanımlanır. Bölge, `CRgn` nesnesinde depolanır.

Bir bölgenin boyutu, 32.767 mantıksal birim veya 64K bellek, hangisi daha küçükse, 32.767 ile sınırlıdır.

`CreateEllipticRgn` İşlevi ile oluşturulmuş bir bölgeyi kullanmayı bitirdiğinde bir uygulama, cihaz bağlamından bölge seçip onu kaldırmak için `DeleteObject` fonksiyonunu kullanmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/cpp/crgn-class_2.cpp)]

##  <a name="createellipticrgnindirect"></a>CRgn:: CreateEllipticRgnIndirect

Elips bölge oluşturur.

```
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
Elipsin sınırlayıcı dikdörtgeninin `RECT` sol üst ve `CRect` sağ alt köşelerinden oluşan mantıksal koordinatları içeren bir yapıya veya nesneye işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bölge, *lpRect* tarafından işaret edilen yapı veya nesne tarafından tanımlanır ve `CRgn` nesnesinde depolanır.

Bir bölgenin boyutu, 32.767 mantıksal birim veya 64K bellek, hangisi daha küçükse, 32.767 ile sınırlıdır.

`CreateEllipticRgnIndirect` İşlevi ile oluşturulmuş bir bölgeyi kullanmayı bitirdiğinde bir uygulama, cihaz bağlamından bölge seçip onu kaldırmak için `DeleteObject` fonksiyonunu kullanmalıdır.

### <a name="example"></a>Örnek

  [CRgn:: CreateRectRgnIndirect](#createrectrgnindirect)için örneğe bakın.

##  <a name="createfromdata"></a>CRgn:: CreateFromData

Verilen bölge ve dönüşüm verilerinden bir bölge oluşturur.

```
BOOL CreateFromData(
    const XFORM* lpXForm,
    int nCount,
    const RGNDATA* pRgnData);
```

### <a name="parameters"></a>Parametreler

*lpXForm*<br/>
Bölgede gerçekleştirilecek dönüşümü tanımlayan bir [XFORM](/windows/desktop/api/wingdi/ns-wingdi-tagxform) veri yapısına işaret eder. Bu işaretçi NULL ise, kimlik dönüştürmesi kullanılır.

*nCount*<br/>
*PRgnData*tarafından işaret edilen bayt sayısını belirtir.

*pRgnData*<br/>
Bölge verilerini içeren bir [rgndata](/windows/desktop/api/wingdi/ns-wingdi-rgndata) veri yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir uygulama, `CRgn::GetRegionData` işlevi çağırarak bir bölge için veri alabilir.

##  <a name="createfrompath"></a>CRgn:: CreateFromPath

Verilen cihaz bağlamına seçili olan yoldan bir bölge oluşturur.

```
BOOL CreateFromPath(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Kapalı bir yol içeren bir cihaz bağlamını tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

*PDC* parametresi tarafından tanımlanan cihaz bağlamı kapalı bir yol içermelidir. Bir `CreateFromPath` yolu bir bölgeye dönüştürdükten sonra, Windows kapalı yolu cihaz bağlamından atar.

##  <a name="createpolygonrgn"></a>CRgn:: CreatePolygonRgn

Bir çokgen bölgesi oluşturur.

```
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,
    int nCount,
    int nMode);
```

### <a name="parameters"></a>Parametreler

*lpPoints*<br/>
Bir `POINT` yapı dizisine veya `CPoint` nesne dizisine işaret eder. Her yapı, çokgenin bir köşesinin x koordinatını ve y koordinatını belirtir. `POINT` Yapı aşağıdaki biçimdedir:

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*nCount*<br/>
Dizi içinde `POINT` *lpPoints*tarafından işaret `CPoint` edilen yapıların veya nesnelerin sayısını belirtir.

*nMode*<br/>
Bölgenin doldurma modunu belirtir. Bu parametre ALTERNATIF ya da SARGı olabilir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Sistem, gerekirse, en son köşenin ilk köşesini bir çizgi çizerek otomatik olarak çokgeni kapatır. Elde edilen bölge, `CRgn` nesnesinde depolanır.

Bir bölgenin boyutu, 32.767 mantıksal birim veya 64K bellek, hangisi daha küçükse, 32.767 ile sınırlıdır.

Çokgen doldurma modu ALTERNATIF olduğunda, sistem, her tarama satırındaki tek sayılı ve çift numaralı Çokgen kenarları arasında alanı doldurur. Diğer bir deyişle, sistem alanı birinci ve ikinci kenar arasında, üçüncü ve dördüncü taraf arasında doldurur ve bu şekilde devam eder.

Çokgen doldurma modu SARGı olduğunda, sistem bir alanın doldurulup doldurulmayacağını belirleyen yönü kullanır. Bir Çokgendeki her çizgi segmenti saat yönünde veya saatin tersi yönde çizilir. Kapalı bir alandan bir şeklin dışına çizilen bir sanal çizgi saat yönünde bir satır segmentinde geçtiğinde bir sayı artırılır. Satır saatin tersi bir satır segmentinden geçtiğinde, sayı azaltılır. Satır, şekil şeklin dışına ulaştığında sayı sıfır değilse, alan doldurulur.

Bir uygulama, `CreatePolygonRgn` işlevle oluşturulmuş bir bölgeyi kullanmayı bitirdiğinde, cihaz bağlamından bölgeyi seçip onu kaldırmak için `DeleteObject` işlevini kullanmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#146](../../mfc/codesnippet/cpp/crgn-class_3.cpp)]

##  <a name="createpolypolygonrgn"></a>CRgn:: CreatePolyPolygonRgn

Kapalı çokgenlerin serisini içeren bir bölge oluşturur.

```
BOOL CreatePolyPolygonRgn(
    LPPOINT lpPoints,
    LPINT lpPolyCounts,
    int nCount,
    int nPolyFillMode);
```

### <a name="parameters"></a>Parametreler

*lpPoints*<br/>
Bir `POINT` yapı dizisine veya poligonun köşelerini tanımlayan bir `CPoint` nesne dizisine işaret eder. Sistem onları otomatik olarak kapatmadığından her bir çokgen açıkça kapatılmalıdır. Çokgenler ardışık olarak belirtilir. `POINT` Yapı aşağıdaki biçimdedir:

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*lpPolyCounts*<br/>
Bir tamsayılar dizisine işaret eder. İlk tamsayı, *lpPoints* dizisindeki ilk Çokgen içindeki köşelerin sayısını belirtir, ikinci tamsayı ikinci Çokgendeki köşe sayısını belirtir ve bu şekilde devam eder.

*nCount*<br/>
*LpPolyCounts* dizisindeki toplam tamsayı sayısını belirtir.

*nPolyFillMode*<br/>
Çokgen doldurma modunu belirtir. Bu değer ALTERNATIF ya da SARGı olabilir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Elde edilen bölge, `CRgn` nesnesinde depolanır.

Çokgenler kopuk olabilir veya örtüşebilir.

Bir bölgenin boyutu, 32.767 mantıksal birim veya 64K bellek, hangisi daha küçükse, 32.767 ile sınırlıdır.

Çokgen doldurma modu ALTERNATIF olduğunda, sistem, her tarama satırındaki tek sayılı ve çift numaralı Çokgen kenarları arasında alanı doldurur. Diğer bir deyişle, sistem alanı birinci ve ikinci kenar arasında, üçüncü ve dördüncü taraf arasında doldurur ve bu şekilde devam eder.

Çokgen doldurma modu SARGı olduğunda, sistem bir alanın doldurulup doldurulmayacağını belirleyen yönü kullanır. Bir Çokgendeki her çizgi segmenti saat yönünde veya saatin tersi yönde çizilir. Kapalı bir alandan bir şeklin dışına çizilen bir sanal çizgi saat yönünde bir satır segmentinde geçtiğinde bir sayı artırılır. Satır saatin tersi bir satır segmentinden geçtiğinde, sayı azaltılır. Satır, şekil şeklin dışına ulaştığında sayı sıfır değilse, alan doldurulur.

Bir uygulama, `CreatePolyPolygonRgn` işlevle oluşturulmuş bir bölgeyi kullanmayı bitirdiğinde, cihaz bağlamından bölge seçin ve bunu kaldırmak için [CGdiObject::D eleteobject](../../mfc/reference/cgdiobject-class.md#deleteobject) üye işlevini kullanın.

##  <a name="createrectrgn"></a>CRgn:: CreateRectRgn

`CRgn` Nesnesinde depolanan dikdörtgen bir bölge oluşturur.

```
BOOL CreateRectRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>Parametreler

*x1*<br/>
Bölgenin sol üst köşesinin mantıksal x koordinatını belirtir.

*Y1*<br/>
Bölgenin sol üst köşesinin mantıksal y koordinatını belirtir.

*x2*<br/>
Bölgenin sağ alt köşesinin mantıksal x koordinatını belirtir.

*Y2*<br/>
Bölgenin sağ alt köşesinin mantıksal y koordinatını belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir bölgenin boyutu, 32.767 mantıksal birim veya 64K bellek, hangisi daha küçükse, 32.767 ile sınırlıdır.

Tarafından `CreateRectRgn`oluşturulan bir bölgeyi kullanmayı bitirdiğinde, bir uygulamanın, bölgeyi kaldırmak için [CGdiObject::D eleteobject](../../mfc/reference/cgdiobject-class.md#deleteobject) üye işlevini kullanması gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/cpp/crgn-class_4.cpp)]

Ek bir örnek için bkz. [CRgn:: CombineRgn](#combinergn).

##  <a name="createrectrgnindirect"></a>CRgn:: Createrectrgndolaylı

`CRgn` Nesnesinde depolanan dikdörtgen bir bölge oluşturur.

```
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
Bölgenin sol üst `RECT` ve sağ `CRect` alt köşelerinden oluşan mantıksal koordinatları içeren bir yapıya veya nesneye işaret eder. `RECT` Yapı aşağıdaki biçimdedir:

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir bölgenin boyutu, 32.767 mantıksal birim veya 64K bellek, hangisi daha küçükse, 32.767 ile sınırlıdır.

Tarafından `CreateRectRgnIndirect`oluşturulan bir bölgeyi kullanmayı bitirdiğinde, bir uygulamanın, bölgeyi kaldırmak için [CGdiObject::D eleteobject](../../mfc/reference/cgdiobject-class.md#deleteobject) üye işlevini kullanması gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#148](../../mfc/codesnippet/cpp/crgn-class_5.cpp)]

##  <a name="createroundrectrgn"></a>CRgn:: CreateRoundRectRgn

`CRgn` Nesnede depolanan yuvarlak köşeler içeren dikdörtgen bir bölge oluşturur.

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
Bölgenin sol üst köşesinin mantıksal x koordinatını belirtir.

*Y1*<br/>
Bölgenin sol üst köşesinin mantıksal y koordinatını belirtir.

*x2*<br/>
Bölgenin sağ alt köşesinin mantıksal x koordinatını belirtir.

*Y2*<br/>
Bölgenin sağ alt köşesinin mantıksal y koordinatını belirtir.

*x3*<br/>
Yuvarlatılmış köşeleri oluşturmak için kullanılan elipsin genişliğini belirtir.

*Y3*<br/>
Yuvarlatılmış köşeleri oluşturmak için kullanılan elipsin yüksekliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir bölgenin boyutu, 32.767 mantıksal birim veya 64K bellek, hangisi daha küçükse, 32.767 ile sınırlıdır.

Bir uygulama, `CreateRoundRectRgn` işlevle oluşturulmuş bir bölgeyi kullanmayı bitirdiğinde, cihaz bağlamından bölge seçin ve bunu kaldırmak için [CGdiObject::D eleteobject](../../mfc/reference/cgdiobject-class.md#deleteobject) üye işlevini kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/cpp/crgn-class_6.cpp)]

##  <a name="crgn"></a>CRgn:: CRgn

Bir `CRgn` nesnesi oluşturur.

```
CRgn();
```

### <a name="remarks"></a>Açıklamalar

Veri üyesi, nesne başka `CRgn` bir veya daha fazla üye fonksiyonunda başlatılana kadar geçerli bir Windows GDI bölgesi içermez. `m_hObject`

### <a name="example"></a>Örnek

  [CRgn:: CreateRoundRectRgn](#createroundrectrgn)için örneğe bakın.

##  <a name="equalrgn"></a>CRgn:: EqualRgn

Verilen bölgenin `CRgn` nesnede depolanan bölgeye eşdeğer olup olmadığını belirler.

```
BOOL EqualRgn(CRgn* pRgn) const;
```

### <a name="parameters"></a>Parametreler

*pRgn*<br/>
Bir bölgeyi tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İki bölge eşdeğer ise sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/cpp/crgn-class_7.cpp)]

##  <a name="fromhandle"></a>CRgn:: FromHandle

Bir Windows bölgesine bir tanıtıcı `CRgn` verildiğinde, nesne için bir işaretçi döndürür.

```
static CRgn* PASCAL FromHandle(HRGN hRgn);
```

### <a name="parameters"></a>Parametreler

*hRgn*<br/>
Bir Windows bölgesine yönelik bir tanıtıcı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir `CRgn` nesne işaretçisi. İşlev başarılı olmazsa, dönüş değeri NULL olur.

### <a name="remarks"></a>Açıklamalar

Bir `CRgn` nesne zaten tanıtıcıya iliştirilmişse, geçici `CRgn` bir nesne oluşturulur ve eklenir. Bu geçici `CRgn` nesne yalnızca uygulamanın olay döngüsünde bir sonraki kez boşta kalması durumunda geçerlidir. bu süre, tüm geçici grafik nesneleri silinir. Bunun başka bir yolu, geçici nesnenin yalnızca bir pencere iletisinin işlenmesi sırasında geçerli olduğu durumdur.

##  <a name="getregiondata"></a>CRgn:: GetRegionData

Belirtilen arabelleği bölgeyi açıklayan verilerle doldurur.

```
int GetRegionData(
    LPRGNDATA lpRgnData,
    int nCount) const;
```

### <a name="parameters"></a>Parametreler

*lpRgnData*<br/>
Bilgileri alan bir [rgndata](/windows/desktop/api/wingdi/ns-wingdi-rgndata) veri yapısına işaret eder. Bu parametre NULL ise, dönüş değeri bölge verileri için gereken bayt sayısını içerir.

*nCount*<br/>
*LpRgnData* buffer boyutunu bayt cinsinden belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa ve *nCount* yeterli sayıda bayt belirtiyorsa, dönüş değeri her zaman *nsay*olur. İşlev başarısız olursa veya *nCount* , yeterli sayıda bayttan daha az bir değer belirtiyorsa, dönüş değeri 0 (hata) olur.

### <a name="remarks"></a>Açıklamalar

Bu veriler, bölgeyi oluşturan dikdörtgenlerin boyutlarını içerir. Bu işlev, `CRgn::CreateFromData` işleviyle birlikte kullanılır.

##  <a name="getrgnbox"></a>CRgn:: GetRgnBox

`CRgn` Nesnenin sınırlayıcı dikdörtgeninin koordinatlarını alır.

```
int GetRgnBox(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
Sınırlayıcı dikdörtgenin koordinatlarını `RECT` almak için `CRect` bir yapıya veya nesneye işaret eder. `RECT` Yapı aşağıdaki biçimdedir:

`typedef struct tagRECT {`

`int left;`

`int top;`

`int right;`

`int bottom;`

`} RECT;`

### <a name="return-value"></a>Dönüş Değeri

Bölgenin türünü belirtir. Aşağıdaki değerlerden herhangi biri olabilir:

- COMPLEXREGION bölgesinde çakışan kenarlıklar vardır.

- NULLREGION bölgesi boş.

- Hata `CRgn` nesnesi geçerli bir bölge belirtmiyor.

- SIMPLELEREGION bölgesinde çakışan kenarlık yok.

### <a name="example"></a>Örnek

  [CRgn:: CreatePolygonRgn](#createpolygonrgn)için örneğe bakın.

##  <a name="offsetrgn"></a>CRgn:: OffsetRgn

`CRgn` Nesnede depolanan bölgeyi belirtilen uzaklıklara göre kaydırır.

```
int OffsetRgn(
    int x,
    int y);

int OffsetRgn(POINT point);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Sol veya sağ taşınacak birim sayısını belirtir.

*Iz*<br/>
Yukarı veya aşağı taşınacak birim sayısını belirtir.

*seçeneğinin*<br/>
*Noktanın* x koordinatı, sol veya sağ taşınacak birim sayısını belirtir. *Noktanın* y koordinatı, yukarı veya aşağı taşınacak birim sayısını belirtir. *Point* parametresi bir `POINT` yapı ya da bir `CPoint` nesne olabilir.

### <a name="return-value"></a>Dönüş Değeri

Yeni bölgenin türü. Aşağıdaki değerlerden herhangi biri olabilir:

- COMPLEXREGION bölgesinde çakışan kenarlıklar vardır.

- HATA bölgesi tanıtıcısı geçerli değil.

- NULLREGION bölgesi boş.

- SIMPLELEREGION bölgesinde çakışan kenarlık yok.

### <a name="remarks"></a>Açıklamalar

İşlevi x-ekseni ve *y* birimlerinin bölge *x* birimlerini y ekseni üzerinde taşır.

Bir bölgenin koordinat değerleri 32.767 ' e eşit veya daha küçük ve-32.768 ' e eşit veya daha büyük olmalıdır. Geçersiz bölge koordinatlarını engellemek için *x* ve *y* parametrelerinin dikkatle seçilmesi gerekir.

### <a name="example"></a>Örnek

  [CRgn:: CreateEllipticRgn](#createellipticrgn)için örneğe bakın.

##  <a name="operator_hrgn"></a>CRgn:: operator HRGN

`CRgn` Nesnenin ekli Windows GDI işleyicisini almak için bu işleci kullanın.

```
operator HRGN() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, `CRgn` nesne tarafından temsil edilen Windows GDI nesnesine yönelik bir tanıtıcı; Aksi takdirde null.

### <a name="remarks"></a>Açıklamalar

Bu işleç, bir HRGN nesnesinin doğrudan kullanımını destekleyen bir atama işleçtir.

Grafik nesnelerini kullanma hakkında daha fazla bilgi için, Windows SDK [grafik nesneleri](/windows/desktop/gdi/graphic-objects) makalesine bakın.

##  <a name="ptinregion"></a>CRgn::P tInRegion

*X* ve *y* tarafından verilen noktanın `CRgn` nesnesinde depolanan bölgede olup olmadığını denetler.

```
BOOL PtInRegion(
    int x,
    int y) const;

BOOL PtInRegion(POINT point) const;
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Sınanacak noktanın mantıksal x koordinatını belirtir.

*Iz*<br/>
Sınanacak noktanın mantıksal y koordinatını belirtir.

*seçeneğinin*<br/>
*Noktanın* x ve y koordinatları, değerini test etmek için noktanın x ve y koordinatlarını belirtir. *Nokta* parametresi bir `POINT` yapı ya `CPoint` da nesne olabilir.

### <a name="return-value"></a>Dönüş Değeri

Nokta bölgedeyse sıfır dışı; Aksi takdirde 0.

##  <a name="rectinregion"></a>CRgn:: Recınregion

*LpRect* tarafından belirtilen dikdörtgenin herhangi bir kısmının `CRgn` nesnede depolanan bölgenin sınırları içinde olup olmadığını belirler.

```
BOOL RectInRegion(LPCRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
Bir `RECT` yapıya veya `CRect` nesneye işaret eder. `RECT` Yapı aşağıdaki biçimdedir:

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dikdörtgenin herhangi bir bölümü bölgenin sınırları içinde yer alıyorsa sıfır dışı. Aksi takdirde 0.

##  <a name="setrectrgn"></a>CRgn:: SetRectRgn

Dikdörtgen bir bölge oluşturur.

```
void SetRectRgn(
    int x1,
    int y1,
    int x2,
    int y2);

void SetRectRgn(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*x1*<br/>
Dikdörtgen bölgenin sol üst köşesinin x koordinatını belirtir.

*Y1*<br/>
Dikdörtgen bölgenin sol üst köşesinin y koordinatını belirtir.

*x2*<br/>
Dikdörtgen bölgenin sağ alt köşesinin x koordinatını belirtir.

*Y2*<br/>
Dikdörtgen bölgenin sağ alt köşesinin y koordinatını belirtir.

*lpRect*<br/>
Dikdörtgen bölgeyi belirtir. Bir `RECT` yapıya`CRect` ya da nesneye yönelik bir işaretçi olabilir.

### <a name="remarks"></a>Açıklamalar

Ancak, [CreateRectRgn](#createrectrgn)aksine, yerel Windows uygulama yığınından ek bellek ayırmaz. Bunun yerine, `CRgn` nesnesinde depolanan bölge için ayrılan alanı kullanır. Bu, `CRgn` bir nesnenin çağrılmadan `SetRectRgn`önce geçerli bir Windows bölgesiyle zaten başlatılmış olması gerektiği anlamına gelir. *X1*, *Y1*, *x2*ve *Y2* tarafından verilen noktaları, ayrılan alanın en küçük boyutunu belirtir.

Yerel bellek yöneticisine yapılan çağrılardan `CreateRectRgn` kaçınmak için üye işlevi yerine bu işlevi kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
