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
ms.openlocfilehash: 54018c3d59fe3d7e3d7a5062cda9b40da4f5d586
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372152"
---
# <a name="crgn-class"></a>CRgn sınıfı

Bir Windows grafik cihaz arabirimi (GDI) bölgesi kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CRgn : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRgn::CRgn](#crgn)|Oluşturur bir `CRgn` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRgn::CombineRgn](#combinergn)|Ayarlar bir `CRgn` böylece iki belirtilen birleşimini eşdeğer nesne `CRgn` nesneleri.|
|[CRgn::CopyRgn](#copyrgn)|Ayarlar bir `CRgn` böylece belirtilen bir kopyası olan nesne `CRgn` nesne.|
|[CRgn::CreateEllipticRgn](#createellipticrgn)|Başlatan bir `CRgn` elips bölgesi olan nesne.|
|[CRgn::CreateEllipticRgnIndirect](#createellipticrgnindirect)|Başlatan bir `CRgn` nesnesi tarafından tanımlanan bir elips bölgesi olan bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı.|
|[CRgn::CreateFromData](#createfromdata)|Bir bölge verilen bölge ve dönüştürme verileri oluşturur.|
|[CRgn::CreateFromPath](#createfrompath)|Belirli bir cihaz bağlamına seçilen yolun bir bölgesi oluşturur.|
|[CRgn::CreatePolygonRgn](#createpolygonrgn)|Başlatan bir `CRgn` Çokgen bölgesi olan nesne. Sistem Çokgen otomatik olarak gerekirse, öncelikle son Köşeden bir çizgi çizerek kapatır.|
|[CRgn::CreatePolyPolygonRgn](#createpolypolygonrgn)|Başlatan bir `CRgn` kapalı çokgenler bir dizi içeren bir bölge ile nesne. Çokgenler ayrık olabilir veya çakışma.|
|[CRgn::CreateRectRgn](#createrectrgn)|Başlatan bir `CRgn` dikdörtgen bir bölgesi olan nesne.|
|[CRgn::CreateRectRgnIndirect](#createrectrgnindirect)|Başlatan bir `CRgn` nesnesi tarafından tanımlanan dikdörtgen bir bölgesi olan bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı.|
|[CRgn::CreateRoundRectRgn](#createroundrectrgn)|Başlatan bir `CRgn` yuvarlak köşeli dikdörtgen bir bölgesi olan nesne.|
|[CRgn::EqualRgn](#equalrgn)|İki denetler `CRgn` nesneleri eşdeğer olup olmadığını belirlemek için.|
|[CRgn::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CRgn` nesne tanıtıcı bir Windows bölgeye verildiğinde.|
|[CRgn::GetRegionData](#getregiondata)|Belirtilen arabellek, belirli bir bölgeye açıklayan verileri ile doldurur.|
|[CRgn::GetRgnBox](#getrgnbox)|Sınırlayıcı dikdörtgenini koordinatlarını alır bir `CRgn` nesne.|
|[CRgn::OffsetRgn](#offsetrgn)|Taşır bir `CRgn` nesnesi tarafından belirtilen uzaklık.|
|[CRgn::PtInRegion](#ptinregion)|Belirli bir noktaya bölgesinde olup olmadığını belirler.|
|[CRgn::RectInRegion](#rectinregion)|Herhangi bir bölümünü belirtilen dikdörtgen bölge sınırlar içinde olup olmadığını belirler.|
|[CRgn::SetRectRgn](#setrectrgn)|Kümeleri `CRgn` nesne belirtilen dikdörtgen bölge.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[HRGN CRgn::operator](#operator_hrgn)|İçindeki Windows tanıtıcısını döndürür `CRgn` nesne.|

## <a name="remarks"></a>Açıklamalar

Bir elips veya Çokgen alan bir pencere içinde bölgedir. Bölgeleri kullanmak için sınıfın üye işlevleri kullanın. `CRgn` sınıfı üyeleri olarak tanımlanan kırpma işlevleri ile `CDC`.

Üye işlevlerinin `CRgn` oluşturmak, alter ve kendisi için çağrılır bölge nesne hakkında bilgi alın.

Kullanma hakkında daha fazla bilgi için `CRgn`, bkz: [grafik nesneleri](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CRgn`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="combinergn"></a>  CRgn::CombineRgn

Var olan iki bölgeleri birleştirerek yeni GDI bölgesi oluşturur.

```
int CombineRgn(
    CRgn* pRgn1,
    CRgn* pRgn2,
    int nCombineMode);
```

### <a name="parameters"></a>Parametreler

*pRgn1*<br/>
Varolan bir bölgeye tanımlar.

*pRgn2*<br/>
Varolan bir bölgeye tanımlar.

*nCombineMode*<br/>
İki kaynak bölgelerine birleştirilirken gerçekleştirilecek işlemini belirtir. Bu, aşağıdaki değerlerden biri olabilir:

- Her iki bölgeleri (kesişimi) alanlarını çakışan RGN_AND kullanır.

- RGN_COPY bölge 1 bir kopyasını oluşturur (tarafından tanımlanan *pRgn1*).

- Bölge 1 alanlarının oluşan bir bölge RGN_DIFF oluşturur (tarafından tanımlanan *pRgn1*) 2 bölgesinin bir parçası olmayan (tarafından tanımlanan *pRgn2*).

- Her iki bölgeleri (birleşimi) tamamen RGN_OR birleştirir.

- RGN_XOR iki bölgeleri bir araya getirir, ancak çakışan alanlarını kaldırır.

### <a name="return-value"></a>Dönüş Değeri

Sonuçta elde edilen bölge türünü belirtir. Aşağıdaki değerlerden biri olabilir:

- Kenarlıklar çakışan COMPLEXREGION yeni bölge yok.

- Yeni bölge oluşturulan bir hata OLUŞTU.

- NULLREGION yeni bölge boştur.

- Çakışan kenarlığı SIMPLEREGION yeni bölge yok.

### <a name="remarks"></a>Açıklamalar

Bölgeleri birleştirilir belirtildiği gibi *nCombineMode*.

Belirtilen iki bölgeleri birleştirilir ve sonuçta elde edilen bölge tanıtıcı depolanan `CRgn` nesne. Bu nedenle, her bölge içinde depolanan `CRgn` birleşik bölgeye göre nesne değiştirilir.

Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K sınırlıdır, hangisi daha küçükse.

Kullanım [CopyRgn](#copyrgn) yalnızca tek bir bölge başka bir bölgeye kopyalamak için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/cpp/crgn-class_1.cpp)]

##  <a name="copyrgn"></a>  CRgn::CopyRgn

Tarafından tanımlanan bir bölgeyi kopyalar *pRgnSrc* içine `CRgn` nesne.

```
int CopyRgn(CRgn* pRgnSrc);
```

### <a name="parameters"></a>Parametreler

*pRgnSrc*<br/>
Varolan bir bölgeye tanımlar.

### <a name="return-value"></a>Dönüş Değeri

Sonuçta elde edilen bölge türünü belirtir. Aşağıdaki değerlerden biri olabilir:

- Kenarlıklar çakışan COMPLEXREGION yeni bölge yok.

- Yeni bölge oluşturulan bir hata OLUŞTU.

- NULLREGION yeni bölge boştur.

- Çakışan kenarlığı SIMPLEREGION yeni bölge yok.

### <a name="remarks"></a>Açıklamalar

Yeni bölge değiştirir saklanan eski bölge `CRgn` nesne. Bu işlev bir özel durumu, [CombineRgn](#combinergn) üye işlevi.

### <a name="example"></a>Örnek

  Örneğin bakın [CRgn::CreateEllipticRgn](#createellipticrgn).

##  <a name="createellipticrgn"></a>  CRgn::CreateEllipticRgn

Bir elips bölgesi oluşturur.

```
BOOL CreateEllipticRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>Parametreler

*x1*<br/>
Mantıksal x koordinatını elipsin sınırlayıcı dikdörtgenin sol üst köşesinin belirtir.

*y1*<br/>
Mantıksal y koordinatını elipsin sınırlayıcı dikdörtgenin sol üst köşesinin belirtir.

*x2*<br/>
Mantıksal x koordinatını elips sınırlayıcı dikdörtgenini sağ alt köşesindeki belirtir.

*y2*<br/>
Mantıksal y koordinatını elips sınırlayıcı dikdörtgenini sağ alt köşesindeki belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Tarafından belirtilen dikdörtgen bölge tanımlanır *x1*, *y1*, *x2*, ve *y2*. Bölge içinde depolanan `CRgn` nesne.

Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K sınırlıdır, hangisi daha küçükse.

Olduğunda tamamlandı ile oluşturulan bir bölge kullanarak `CreateEllipticRgn` işlevi, bir uygulamanın kullanıma bölgesi kullanın ve cihaz bağlamı seçmelisiniz `DeleteObject` kaldırılacağı işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/cpp/crgn-class_2.cpp)]

##  <a name="createellipticrgnindirect"></a>  CRgn::CreateEllipticRgnIndirect

Bir elips bölgesi oluşturur.

```
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
İşaret eden bir `RECT` yapısı veya `CRect` elips sınırlayıcı dikdörtgenini sol ve sağ köşelerinde mantıksal koordinatları içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bölgeyi işaret ettiği nesne ya da yapı tarafından tanımlanan *lpRect* ve depolanan `CRgn` nesne.

Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K sınırlıdır, hangisi daha küçükse.

Olduğunda tamamlandı ile oluşturulan bir bölge kullanarak `CreateEllipticRgnIndirect` işlevi, bir uygulamanın kullanıma bölgesi kullanın ve cihaz bağlamı seçmelisiniz `DeleteObject` kaldırılacağı işlevi.

### <a name="example"></a>Örnek

  Örneğin bakın [CRgn::CreateRectRgnIndirect](#createrectrgnindirect).

##  <a name="createfromdata"></a>  CRgn::CreateFromData

Bir bölge verilen bölge ve dönüştürme verileri oluşturur.

```
BOOL CreateFromData(
    const XFORM* lpXForm,
    int nCount,
    const RGNDATA* pRgnData);
```

### <a name="parameters"></a>Parametreler

*lpXForm*<br/>
İşaret eden bir [XFORM](/windows/desktop/api/wingdi/ns-wingdi-tagxform) bölge üzerinde gerçekleştirilecek dönüşümü tanımlayan veri yapısı. Bu işaretçi NULL ise, kimlik dönüşümü kullanılır.

*nCount*<br/>
İşaret ettiği bayt sayısını belirtir *pRgnData*.

*pRgnData*<br/>
İşaret eden bir [RGNDATA](/windows/desktop/api/wingdi/ns-wingdi-_rgndata) bölge verileri içeren veri yapısı.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Uygulama verileri için bir bölge çağırarak alabilirsiniz `CRgn::GetRegionData` işlevi.

##  <a name="createfrompath"></a>  CRgn::CreateFromPath

Belirli bir cihaz bağlamına seçilen yolun bir bölgesi oluşturur.

```
BOOL CreateFromPath(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Kapalı bir yolunu içeren bir cihaz bağlamı tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Tarafından tanımlanan cihaz bağlamı *pDC* parametresi kapalı bir yol içermesi gerekir. Sonra `CreateFromPath` bir bölge Windows yola bir cihaz bağlamı kapalı yolundan atar.

##  <a name="createpolygonrgn"></a>  CRgn::CreatePolygonRgn

Çokgen bölgesi oluşturur.

```
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,
    int nCount,
    int nMode);
```

### <a name="parameters"></a>Parametreler

*lpPoints*<br/>
İşaret dizilerine `POINT` yapıları veya bir dizi `CPoint` nesneleri. Her yapı x koordinatını ve y koordinatını çokgenin bir köşe belirtir. `POINT` Yapısı aşağıdaki biçime sahiptir:

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*nCount*<br/>
Sayısını belirten `POINT` yapıları veya `CPoint` dizisindeki nesnelere tarafından işaret edilen *lpPoints*.

*nMode*<br/>
Bölge için doldurma modunu belirtir. Bu parametre, diğer ya da SARGI olabilir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Sistem Çokgen otomatik olarak gerekirse, öncelikle son Köşeden bir çizgi çizerek kapatır. Sonuçta elde edilen bölge depolanan `CRgn` nesne.

Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K sınırlıdır, hangisi daha küçükse.

Çokgen doldurma modu ALTERNATİF olduğunda, sistemin her tarama satırda tek sayılı ve tek sayılı Çokgen kenarı arasındaki alan doldurur. Diğer bir deyişle, sistemin ilk ve ikinci yan arasında üçüncü ve dördüncü yan vb. arasındaki alan doldurur.

Çokgen doldurma modu SARGI, sistemin bir alanı dolduracak şekilde belirlemek için bir şekil çizilmiş yönü kullanır. Bir çokgenin her bir satır segmentin bir saat yönünde veya saat yönünün tersi yönde çizilir. Bir saat yönünde çizgi kesimi dışındaki bir şekil için kapalı bir alandan çizilmiş hayali bir çizgi geçen zaman, bir sayı artırılır. Satırı bir saat yönünün tersine çizgi kesimi geçtiğinde sayısı azaltılır. Şekil dışındaki bir satıra ulaştığında sayısı sıfır değilse alan doldurulur.

Bir uygulama bittiğinde ile oluşturulan bir bölge kullanarak `CreatePolygonRgn` işlevi, out bölgesi kullanın ve cihaz bağlamı seçmek `DeleteObject` kaldırılacağı işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#146](../../mfc/codesnippet/cpp/crgn-class_3.cpp)]

##  <a name="createpolypolygonrgn"></a>  CRgn::CreatePolyPolygonRgn

Kapalı çokgenler bir dizi içeren bir bölge oluşturur.

```
BOOL CreatePolyPolygonRgn(
    LPPOINT lpPoints,
    LPINT lpPolyCounts,
    int nCount,
    int nPolyFillMode);
```

### <a name="parameters"></a>Parametreler

*lpPoints*<br/>
İşaret dizilerine `POINT` yapıları veya bir dizi `CPoint` çokgenler köşelerini tanımlayan nesne. Sistem otomatik olarak bunları kapatmadığını çünkü her bir Çokgen açıkça kapatılmalıdır. Çokgenler art arda belirtilir. `POINT` Yapısı aşağıdaki biçime sahiptir:

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*lpPolyCounts*<br/>
Bir dizi noktalarını tamsayı. İlk Çokgendeki ilk tamsayı köşelerin sayısını belirtir *lpPoints* dizinin ikinci tamsayı, ikinci Çokgen ve benzeri köşeler sayısını belirtir.

*nCount*<br/>
Tamsayılar toplam sayısını belirten *lpPolyCounts* dizisi.

*nPolyFillMode*<br/>
Bir çokgenin doldurma modunu belirtir. Bu değer, diğer ya da SARGI olabilir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Sonuçta elde edilen bölge depolanan `CRgn` nesne.

Çokgenler ayrık olabilir veya çakışma.

Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K sınırlıdır, hangisi daha küçükse.

Çokgen doldurma modu ALTERNATİF olduğunda, sistemin her tarama satırda tek sayılı ve tek sayılı Çokgen kenarı arasındaki alan doldurur. Diğer bir deyişle, sistemin ilk ve ikinci yan arasında üçüncü ve dördüncü yan vb. arasındaki alan doldurur.

Çokgen doldurma modu SARGI, sistemin bir alanı dolduracak şekilde belirlemek için bir şekil çizilmiş yönü kullanır. Bir çokgenin her bir satır segmentin bir saat yönünde veya saat yönünün tersi yönde çizilir. Bir saat yönünde çizgi kesimi dışındaki bir şekil için kapalı bir alandan çizilmiş hayali bir çizgi geçen zaman, bir sayı artırılır. Satırı bir saat yönünün tersine çizgi kesimi geçtiğinde sayısı azaltılır. Şekil dışındaki bir satıra ulaştığında sayısı sıfır değilse alan doldurulur.

Bir uygulama bittiğinde ile oluşturulan bir bölge kullanarak `CreatePolyPolygonRgn` işlevi, out bölgesi kullanın ve cihaz bağlamı seçmek [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) kaldırılacağı üye işlevi.

##  <a name="createrectrgn"></a>  CRgn::CreateRectRgn

Depolanan bir dikdörtgen bölge oluşturur `CRgn` nesne.

```
BOOL CreateRectRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>Parametreler

*x1*<br/>
Mantıksal x koordinatını bölge sol üst köşesinde belirtir.

*y1*<br/>
Mantıksal y koordinatını bölge sol üst köşesinde belirtir.

*x2*<br/>
Mantıksal x koordinatını alanının sağ alt köşedeki belirtir.

*y2*<br/>
Mantıksal y koordinatını alanının sağ alt köşedeki belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K sınırlıdır, hangisi daha küçükse.

Olduğunda tamamlandı tarafından oluşturulan bir bölge kullanarak `CreateRectRgn`, bir uygulamanın kullanması gereken [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) bölge kaldırmak için üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/cpp/crgn-class_4.cpp)]

Ek bir örnek için bkz. [CRgn::CombineRgn](#combinergn).

##  <a name="createrectrgnindirect"></a>  CRgn::CreateRectRgnIndirect

Depolanan bir dikdörtgen bölge oluşturur `CRgn` nesne.

```
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
İşaret eden bir `RECT` yapısı veya `CRect` bölge sol ve sağ köşelerinde mantıksal koordinatları içeren nesne. `RECT` Yapısı aşağıdaki biçime sahiptir:

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K sınırlıdır, hangisi daha küçükse.

Olduğunda tamamlandı tarafından oluşturulan bir bölge kullanarak `CreateRectRgnIndirect`, bir uygulamanın kullanması gereken [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) bölge kaldırmak için üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#148](../../mfc/codesnippet/cpp/crgn-class_5.cpp)]

##  <a name="createroundrectrgn"></a>  CRgn::CreateRoundRectRgn

Depolanan yuvarlak köşeli dikdörtgen bir bölgesi oluşturur `CRgn` nesne.

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
Mantıksal x koordinatını bölge sol üst köşesinde belirtir.

*y1*<br/>
Mantıksal y koordinatını bölge sol üst köşesinde belirtir.

*x2*<br/>
Mantıksal x koordinatını alanının sağ alt köşedeki belirtir.

*y2*<br/>
Mantıksal y koordinatını alanının sağ alt köşedeki belirtir.

*x3*<br/>
Yuvarlatılmış köşeler oluşturmak için kullanılan elips genişliğini belirtir.

*Y3*<br/>
Yuvarlatılmış köşeler oluşturmak için kullanılan elips yüksekliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K sınırlıdır, hangisi daha küçükse.

Bir uygulama bittiğinde ile oluşturulan bir bölge kullanarak `CreateRoundRectRgn` işlevi, out bölgesi kullanın ve cihaz bağlamı seçmek [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) kaldırılacağı üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/cpp/crgn-class_6.cpp)]

##  <a name="crgn"></a>  CRgn::CRgn

Oluşturur bir `CRgn` nesne.

```
CRgn();
```

### <a name="remarks"></a>Açıklamalar

`m_hObject` Veri üyesi bir veya daha fazla diğer nesne başlatılana kadar geçerli bir Windows GDI bölge içermiyor `CRgn` üye işlevleri.

### <a name="example"></a>Örnek

  Örneğin bakın [CRgn::CreateRoundRectRgn](#createroundrectrgn).

##  <a name="equalrgn"></a>  CRgn::EqualRgn

Belirli bir bölgeye depolanan bölgeye eşdeğer olup olmadığını belirler `CRgn` nesne.

```
BOOL EqualRgn(CRgn* pRgn) const;
```

### <a name="parameters"></a>Parametreler

*pRgn*<br/>
Bir bölgeyi tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İki bölgeleri eşdeğerdir olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/cpp/crgn-class_7.cpp)]

##  <a name="fromhandle"></a>  CRgn::FromHandle

Bir işaretçi döndüren bir `CRgn` nesne tanıtıcı bir Windows bölgeye verildiğinde.

```
static CRgn* PASCAL FromHandle(HRGN hRgn);
```

### <a name="parameters"></a>Parametreler

*hRgn*<br/>
Bir Windows bölge için bir tanıtıcı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CRgn` nesne. İşlev başarılı olmadıysa, döndürülen değer NULL olur.

### <a name="remarks"></a>Açıklamalar

Varsa bir `CRgn` nesne zaten iliştirilmemiş tanıtıcı, geçici bir `CRgn` nesnesi oluşturulur ve bağlı. Bu geçici `CRgn` tüm geçici grafik, zaman sonraki açışınızda uygulama boşta kalma süresi kendi olay döngüsü olana kadar nesneler silinir yalnızca nesne geçerlidir. Bunu belirten bir başka yolu geçici bir nesne yalnızca bir pencere iletisi işlenirken geçerli olmasıdır.

##  <a name="getregiondata"></a>  CRgn::GetRegionData

Belirtilen arabellek bölge açıklayan verileri ile doldurur.

```
int GetRegionData(
    LPRGNDATA lpRgnData,
    int nCount) const;
```

### <a name="parameters"></a>Parametreler

*lpRgnData*<br/>
İşaret eden bir [RGNDATA](/windows/desktop/api/wingdi/ns-wingdi-_rgndata) bilgileri alan veri yapısı. Bu parametre NULL ise, dönüş değeri için bölge veri gereken bayt sayısını içerir.

*nCount*<br/>
Bayt cinsinden boyutunu belirtir *lpRgnData* arabellek.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa ve *nCount* yeterli bir numarasını belirtir, bayt dönüş değeri her zaman olduğu *nCount*. İşlev başarısız olursa veya *nCount* daha az belirtir yeterli bayt, dönüş değeri 0 (hata) sayısıdır.

### <a name="remarks"></a>Açıklamalar

Bu veriler, bölgeyi oluşturan dikdörtgenlerin boyutlar içerir. Bu işlev ile birlikte kullanılan `CRgn::CreateFromData` işlevi.

##  <a name="getrgnbox"></a>  CRgn::GetRgnBox

Sınırlayıcı dikdörtgenini koordinatlarını alır `CRgn` nesne.

```
int GetRgnBox(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
İşaret eden bir `RECT` yapısı veya `CRect` dikdörtgen koordinatlarını almak için nesne. `RECT` Yapısı aşağıdaki biçime sahiptir:

`typedef struct tagRECT {`

`int left;`

`int top;`

`int right;`

`int bottom;`

`} RECT;`

### <a name="return-value"></a>Dönüş Değeri

Bölgenin türünü belirtir. Aşağıdaki değerlerden biri olabilir:

- Kenarlıklar çakışan COMPLEXREGION bölgesi vardır.

- NULLREGION bölge boştur.

- HATA `CRgn` nesne geçerli bölge belirtmiyor.

- Çakışan kenarlığı SIMPLEREGION bölge yok.

### <a name="example"></a>Örnek

  Örneğin bakın [CRgn::CreatePolygonRgn](#createpolygonrgn).

##  <a name="offsetrgn"></a>  CRgn::OffsetRgn

Depolanan bölge taşır `CRgn` nesnesi tarafından belirtilen uzaklık.

```
int OffsetRgn(
    int x,
    int y);

int OffsetRgn(POINT point);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Sola taşı için ya da sağ birim sayısını belirtir.

*Y*<br/>
Yukarı veya aşağı taşımak için birim sayısını belirtir.

*Noktası*<br/>
X koordinatını *noktası* sol taşımak ya da sağ birim sayısını belirtir. Y koordinatını *noktası* yukarı veya aşağı taşımak için birim sayısını belirtir. *Noktası* parametresi ya da olabilir bir `POINT` yapısı veya `CPoint` nesne.

### <a name="return-value"></a>Dönüş Değeri

Yeni bölgenin türü. Bu, aşağıdaki değerlerden biri olabilir:

- Kenarlıklar çakışan COMPLEXREGION bölgesi vardır.

- HATA Bölge tanıtıcısı geçerli değil.

- NULLREGION bölge boştur.

- Çakışan kenarlığı SIMPLEREGION bölge yok.

### <a name="remarks"></a>Açıklamalar

Bölge işlevi taşır *x* birim x ekseni boyunca ve *y* birim y ekseni boyunca.

Bir bölge koordinat değerlerini 32.767 ve büyük veya buna eşit -32.768 eşit veya daha az olmalıdır. *x* ve *y* parametreleri dikkatle seçilmelidir geçersiz bölge koordinatları önlemek için.

### <a name="example"></a>Örnek

  Örneğin bakın [CRgn::CreateEllipticRgn](#createellipticrgn).

##  <a name="operator_hrgn"></a>  HRGN CRgn::operator

Ekli Windows GDI tanıtıcısını almak için bu işleci kullanın `CRgn` nesne.

```
operator HRGN() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı, Windows GDI nesnesi için bir tanıtıcı tarafından temsil edilen varsa `CRgn` nesne; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

HRGN nesne doğrudan kullanımını destekleyen bir yayım işleciyle işlecidir.

Grafik nesneler kullanma hakkında daha fazla bilgi için bkz [grafik nesneleri](/windows/desktop/gdi/graphic-objects) Windows SDK.

##  <a name="ptinregion"></a>  CRgn::PtInRegion

Denetler olmadığını tarafından verilen nokta *x* ve *y* depolanan bölgede `CRgn` nesne.

```
BOOL PtInRegion(
    int x,
    int y) const;

BOOL PtInRegion(POINT point) const;
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Test için noktasının mantıksal x koordinatı belirtir.

*Y*<br/>
Test için noktasının mantıksal y koordinatı belirtir.

*Noktası*<br/>
X ve y-koordinatlarını *noktası* x ve y-koordinatları değerini test etmek için noktasının belirtin. *Noktası* parametresi olabilir ya da bir `POINT` yapısı veya `CPoint` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bölgede noktasıdır olursa sıfır dışı; Aksi durumda 0.

##  <a name="rectinregion"></a>  CRgn::RectInRegion

Dikdörtgenin herhangi bir bölümü tarafından belirtilen olup olmadığını belirler *lpRect* depolanan bölge sınırları içinde `CRgn` nesne.

```
BOOL RectInRegion(LPCRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
İşaret eden bir `RECT` yapısı veya `CRect` nesne. `RECT` Yapısı aşağıdaki biçime sahiptir:

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir bölümünü belirtilen dikdörtgen bölge sınırlar içinde yer alıyorsa sıfır; Aksi durumda 0.

##  <a name="setrectrgn"></a>  CRgn::SetRectRgn

Dikdörtgen bir bölgesi oluşturur.

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
Dikdörtgen bölge sol üst köşesinin x koordinatını belirtir.

*y1*<br/>
Dikdörtgen bölge sol üst köşesinin y koordinatını belirtir.

*x2*<br/>
Dikdörtgen bölge sağ alt köşesinin x koordinatını belirtir.

*y2*<br/>
Dikdörtgen bölge sağ alt köşesinin y koordinatını belirtir.

*lpRect*<br/>
Dikdörtgen bölge belirtir. İçin bir işaretçi olabilir bir `RECT` yapısı veya `CRect` nesne.

### <a name="remarks"></a>Açıklamalar

Farklı [CreateRectRgn](#createrectrgn), ancak bunu herhangi bir ek bellek yerel Windows uygulama yığından bırakmaz. Bunun yerine, bölge içinde depolanan için ayrılan alanı kullanır `CRgn` nesne. Diğer bir deyişle `CRgn` nesne gerekir zaten başlatıldı çağırmadan önce geçerli bir Windows bölgeyle `SetRectRgn`. Tarafından verilen noktaları *x1*, *y1*, *x2*, ve *y2* ayrılan alanı için en küçük boyut belirtin.

Bu işlevi yerine kullanın `CreateRectRgn` yerel bellek yöneticisi çağrıları önlemek için üye işlevi.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
