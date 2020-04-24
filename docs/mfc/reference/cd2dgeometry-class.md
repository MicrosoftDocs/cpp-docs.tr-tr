---
title: CD2DGeometri Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::Attach
- AFXRENDERTARGET/CD2DGeometry::CombineWithGeometry
- AFXRENDERTARGET/CD2DGeometry::CompareWithGeometry
- AFXRENDERTARGET/CD2DGeometry::ComputeArea
- AFXRENDERTARGET/CD2DGeometry::ComputeLength
- AFXRENDERTARGET/CD2DGeometry::ComputePointAtLength
- AFXRENDERTARGET/CD2DGeometry::Destroy
- AFXRENDERTARGET/CD2DGeometry::Detach
- AFXRENDERTARGET/CD2DGeometry::FillContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Get
- AFXRENDERTARGET/CD2DGeometry::GetBounds
- AFXRENDERTARGET/CD2DGeometry::GetWidenedBounds
- AFXRENDERTARGET/CD2DGeometry::IsValid
- AFXRENDERTARGET/CD2DGeometry::Outline
- AFXRENDERTARGET/CD2DGeometry::Simplify
- AFXRENDERTARGET/CD2DGeometry::StrokeContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Tessellate
- AFXRENDERTARGET/CD2DGeometry::Widen
- AFXRENDERTARGET/CD2DGeometry::m_pGeometry
helpviewer_keywords:
- CD2DGeometry [MFC], CD2DGeometry
- CD2DGeometry [MFC], Attach
- CD2DGeometry [MFC], CombineWithGeometry
- CD2DGeometry [MFC], CompareWithGeometry
- CD2DGeometry [MFC], ComputeArea
- CD2DGeometry [MFC], ComputeLength
- CD2DGeometry [MFC], ComputePointAtLength
- CD2DGeometry [MFC], Destroy
- CD2DGeometry [MFC], Detach
- CD2DGeometry [MFC], FillContainsPoint
- CD2DGeometry [MFC], Get
- CD2DGeometry [MFC], GetBounds
- CD2DGeometry [MFC], GetWidenedBounds
- CD2DGeometry [MFC], IsValid
- CD2DGeometry [MFC], Outline
- CD2DGeometry [MFC], Simplify
- CD2DGeometry [MFC], StrokeContainsPoint
- CD2DGeometry [MFC], Tessellate
- CD2DGeometry [MFC], Widen
- CD2DGeometry [MFC], m_pGeometry
ms.assetid: 3f95054b-fdb8-4e87-87f2-9fc3df7279ec
ms.openlocfilehash: 4727f7b1799604001134ee2f4d2d2e1ce6db87fa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754777"
---
# <a name="cd2dgeometry-class"></a>CD2DGeometri Sınıfı

ID2D1Geometry için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DGeometry : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DGeometri::CD2DGeometri](#cd2dgeometry)|BIR CD2DGeometri nesnesi oluşturuyor.|
|[CD2DGeometri::~CD2DGeometri](#_dtorcd2dgeometry)|Yıkıcı. D2D geometri nesnesi yok edilirken çağrılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DGeometri::Ekle](#attach)|Nesneye varolan kaynak arabirimi ataştırır|
|[CD2DGeometry::Birleştirme Geometrisi](#combinewithgeometry)|Bu geometriyi belirtilen geometriyle birleştirir ve sonucu BIR ID2D1BasitleştirilmişGeometrySink'te depolar.|
|[CD2DGeometry::Karşılaştırma Geometrisi](#comparewithgeometry)|Bu geometri ile belirtilen geometri arasındaki kesişimi açıklar. Karşılaştırma belirtilen düzleme toleransı kullanılarak gerçekleştirilir.|
|[CD2DGeometri::ComputeArea](#computearea)|Geometrinin alanını, belirtilen matris tarafından dönüştürüldükten ve belirtilen tolerans kullanılarak düzleştirilmiş olarak hesaplar.|
|[CD2DGeometri::ComputeLength](#computelength)|Geometrinin uzunluğunu, her bir parça bir satıra sarılmış gibi hesaplar.|
|[CD2DGeometri::ComputePointAtLength](#computepointatlength)|Belirtilen matris tarafından dönüştürüldükten ve belirtilen tolerans kullanılarak düzleştirilmiş sonra geometri boyunca belirtilen mesafedeki nokta ve teğet vektörü hesaplar.|
|[CD2DGeometri::Destroy](#destroy)|BIR CD2DGeometry nesnesini yok eder. (GEÇERSIZ Kılar [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DGeometri::Detach](#detach)|Kaynak arabirimini nesneden ayırıyor|
|[CD2DGeometri::FillContainsPoint](#fillcontainspoint)|Geometri tarafından doldurulan alanın belirtilen düzleme toleransı göz önüne alındığında belirtilen noktayı içerip içermeyeceğini gösterir.|
|[CD2DGeometry::Get](#get)|ID2D1Geometri arabirimi döndürür|
|[CD2DGeometri::GetBounds](#getbounds)||
|[CD2DGeometry::GetWidenedBounds](#getwidenedbounds)|Geometrinin sınırlarını, belirtilen kontur genişliği ve stili tarafından genişletildikten ve belirtilen matris tarafından dönüştürüldükten sonra alır.|
|[CD2DGeometry::Geçersiz](#isvalid)|Kaynak geçerliliğini denetler [(CD2DResource geçersiz kılar::Geçerlidir](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DGeometri::Anahat](#outline)|Geometrinin anahatlarını hesaplar ve sonucu bir ID2D1SimplifiedGeometrySink'e yazar.|
|[CD2DGeometry::Basitleştir](#simplify)|Geometrinin yalnızca çizgileri ve (isteğe bağlı olarak) kübik Bezier eğrilerini içeren basitleştirilmiş bir sürümünü oluşturur ve sonucu bir ID2D1SimplifiedGeometrySink'e yazar.|
|[CD2DGeometri::StrokeContainsPoint](#strokecontainspoint)|Geometrinin konturun belirtilen kontur kalınlığı, stili ve dönüşümü göz önüne alındığında belirtilen noktayı bulunup içermediğini belirler.|
|[CD2DGeometri::Tessellate](#tessellate)|Belirtilen matris kullanılarak dönüştürüldükten ve belirtilen tolerans kullanılarak düzleştirilmiş sonra geometriyi kaplayan saat yönünde bir üçgen kümesi oluşturur.|
|[CD2DGeometri::Genişlet](#widen)|Geometriyi belirtilen konturla genişletir ve belirtilen matris tarafından dönüştürüldükten ve belirtilen tolerans kullanılarak düzleştirildikten sonra sonucu BIR ID2D1BasitleştirilmişGeometrySink'e yazar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DGeometri::operatör ID2D1Geometri*](#operator_id2d1geometry_star)|ID2D1Geometri arabirimi döndürür|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CD2DGeometri::m_pGeometry](#m_pgeometry)|ID2D1Geometry için bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CD2DKaynak](../../mfc/reference/cd2dresource-class.md)

`CD2DGeometry`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dgeometrycd2dgeometry"></a><a name="_dtorcd2dgeometry"></a>CD2DGeometri::~CD2DGeometri

Yıkıcı. D2D geometri nesnesi yok edilirken çağrılır.

```
virtual ~CD2DGeometry();
```

## <a name="cd2dgeometryattach"></a><a name="attach"></a>CD2DGeometri::Ekle

Nesneye varolan kaynak arabirimi ataştırır

```cpp
void Attach(ID2D1Geometry* pResource);
```

### <a name="parameters"></a>Parametreler

*pKaynak*<br/>
Varolan kaynak arabirimi. NULL olamaz

## <a name="cd2dgeometrycd2dgeometry"></a><a name="cd2dgeometry"></a>CD2DGeometri::CD2DGeometri

BIR CD2DGeometri nesnesi oluşturuyor.

```
CD2DGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefine işaretçi.

*bAutoDestroy*<br/>
Nesnenin sahibi (pParentTarget) tarafından yok edileceğini gösterir.

## <a name="cd2dgeometrycombinewithgeometry"></a><a name="combinewithgeometry"></a>CD2DGeometry::Birleştirme Geometrisi

Bu geometriyi belirtilen geometriyle birleştirir ve sonucu BIR ID2D1BasitleştirilmişGeometrySink'te depolar.

```
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,
    D2D1_COMBINE_MODE combineMode,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*inputGeometri*<br/>
Bu örnekle birleştirecek geometri.

*Combinemode*<br/>
Gerçekleştirmek için birleştirme işlemi türü.

*inputGeometryTransform*<br/>
Birleştirmeden önce inputGeometry'a uygulanacak dönüştürme.

*geometriLavabo*<br/>
Birleştirme işleminin sonucu.

*düzlemeToleransToleransı*<br/>
Geometrilerin poligonal yaklaşıkdeğeri ndeki noktalar arasındaki mesafenin maksimum sınırları. Daha küçük değerler daha doğru sonuçlar üretir, ancak yürütmenin daha yavaş olmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrycomparewithgeometry"></a><a name="comparewithgeometry"></a>CD2DGeometry::Karşılaştırma Geometrisi

Bu geometri ile belirtilen geometri arasındaki kesişimi açıklar. Karşılaştırma belirtilen düzleme toleransı kullanılarak gerçekleştirilir.

```
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*inputGeometri*<br/>
Test etmek için geometri.

*inputGeometryTransform*<br/>
inputGeometry'a uygulanacak dönüştürme.

*düzlemeToleransToleransı*<br/>
Geometrilerin poligonal yaklaşıkdeğeri ndeki noktalar arasındaki mesafenin maksimum sınırları. Daha küçük değerler daha doğru sonuçlar üretir, ancak yürütmenin daha yavaş olmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrycomputearea"></a><a name="computearea"></a>CD2DGeometri::ComputeArea

Geometrinin alanını, belirtilen matris tarafından dönüştürüldükten ve belirtilen tolerans kullanılarak düzleştirilmiş olarak hesaplar.

```
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& area,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*worldTransform*<br/>
Alanı hesaplamadan önce bu geometriye uygulanacak dönüşüm.

*Alan*<br/>
Bu yöntem döndüğünde, bu geometrinin dönüştürülmüş, düzleştirilmiş sürümünün alanına bir işaretçi içerir. Bu parametre için depolama alanı ayırmanız gerekir.

*düzlemeToleransToleransı*<br/>
Geometrinin poligonal yaklaşıkdeğerindeki noktalar arasındaki mesafenin maksimum sınırları. Daha küçük değerler daha doğru sonuçlar üretir, ancak yürütmenin daha yavaş olmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrycomputelength"></a><a name="computelength"></a>CD2DGeometri::ComputeLength

Geometrinin uzunluğunu, her bir parça bir satıra sarılmış gibi hesaplar.

```
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& length,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*worldTransform*<br/>
Uzunlukhesaplamadan önce geometri uygulamak için dönüştürme.

*Uzun -luğu*<br/>
Bu yöntem döndüğünde, geometrinin uzunluğuna işaretçi içerir. Kapalı geometriler için uzunluk örtülü bir kapanış kesimi içerir. Bu parametre için depolama alanı ayırmanız gerekir.

*düzlemeToleransToleransı*<br/>
Geometrinin poligonal yaklaşıkdeğerindeki noktalar arasındaki mesafenin maksimum sınırları. Daha küçük değerler daha doğru sonuçlar üretir, ancak yürütmenin daha yavaş olmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrycomputepointatlength"></a><a name="computepointatlength"></a>CD2DGeometri::ComputePointAtLength

Belirtilen matris tarafından dönüştürüldükten ve belirtilen tolerans kullanılarak düzleştirilmiş sonra geometri boyunca belirtilen mesafedeki nokta ve teğet vektörü hesaplar.

```
BOOL ComputePointAtLength(
    FLOAT length,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DPointF& point,
    CD2DPointF& unitTangentVector,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*Uzun -luğu*<br/>
Nokta ve teğet geometrisi boyunca mesafe bulmak. Bu uzaklık 0'dan azsa, bu yöntem geometrideki ilk noktayı hesaplar. Bu uzaklık geometrinin uzunluğundan büyükse, bu yöntem geometrideki son noktayı hesaplar.

*worldTransform*<br/>
Belirtilen nokta ve teğet hesaplamadan önce geometri uygulamak için dönüştürme.

*Nokta*<br/>
Geometri boyunca belirtilen mesafedeki konum. Geometri boşsa, bu nokta x ve y değerleri olarak NaN içerir.

*unitTangentVektör*<br/>
Bu yöntem döndüğünde, geometri boyunca belirtilen mesafede teğet vektöriçin bir işaretçi içerir. Geometri boşsa, bu vektör x ve y değerleri olarak NaN içerir. Bu parametre için depolama alanı ayırmanız gerekir.

*düzlemeToleransToleransı*<br/>
Geometrinin poligonal yaklaşıkdeğerindeki noktalar arasındaki mesafenin maksimum sınırları. Daha küçük değerler daha doğru sonuçlar üretir, ancak yürütmenin daha yavaş olmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrydestroy"></a><a name="destroy"></a>CD2DGeometri::Destroy

BIR CD2DGeometry nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dgeometrydetach"></a><a name="detach"></a>CD2DGeometri::Detach

Kaynak arabirimini nesneden ayırıyor

```
ID2D1Geometry* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirimine işaretçi.

## <a name="cd2dgeometryfillcontainspoint"></a><a name="fillcontainspoint"></a>CD2DGeometri::FillContainsPoint

Geometri tarafından doldurulan alanın belirtilen düzleme toleransı göz önüne alındığında belirtilen noktayı içerip içermeyeceğini gösterir.

```
BOOL FillContainsPoint(
    CD2DPointF point,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
Test etmek için nokta.

*worldTransform*<br/>
Çevreleme için test önce geometri uygulamak için dönüştürme.

*Içerir*<br/>
Bu yöntem döndüğünde, geometri ile doldurulan alan nokta içeriyorsa TRUE olan bir bool değeri içerir; aksi takdirde, YANLIŞ. Bu parametre için depolama alanı ayırmanız gerekir.

*düzlemeToleransToleransı*<br/>
Kesin geometrik yol ve yol kesişiminin hesaplandığı sayısal doğruluk. Toleranstan daha az dolgu eksik noktaları hala içinde kabul edilir. Daha küçük değerler daha doğru sonuçlar üretir, ancak yürütmenin daha yavaş olmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometryget"></a><a name="get"></a>CD2DGeometry::Get

ID2D1Geometri arabirimi döndürür

```
ID2D1Geometry* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1Geometri arabirimini işaretçi.

## <a name="cd2dgeometrygetbounds"></a><a name="getbounds"></a>CD2DGeometri::GetBounds

```
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,
CD2DRectF& bounds) const;
```

### <a name="parameters"></a>Parametreler

*worldTransform*<br/>
*Sınır -ları*

### <a name="return-value"></a>Dönüş Değeri

## <a name="cd2dgeometrygetwidenedbounds"></a><a name="getwidenedbounds"></a>CD2DGeometry::GetWidenedBounds

Geometrinin sınırlarını, belirtilen kontur genişliği ve stili tarafından genişletildikten ve belirtilen matris tarafından dönüştürüldükten sonra alır.

```
BOOL GetWidenedBounds(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DRectF& bounds,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*konturGenişliği*<br/>
Anahatlarını okşayarak geometriyi genişletmek için hangi miktar.

*strokeStyle*<br/>
Geometriyi genişleten konturun stili.

*worldTransform*<br/>
Geometri dönüştürüldükten ve geometri okşandıktan sonra geometriye uygulanacak dönüşüm.

*Sınır -ları*<br/>
Bu yöntem döndüğünde, genleştirilmiş geometrinin sınırlarını içerir. Bu parametre için depolama alanı ayırmanız gerekir.

*düzlemeToleransToleransı*<br/>
Geometrilerin poligonal yaklaşıkdeğeri ndeki noktalar arasındaki mesafenin maksimum sınırları. Daha küçük değerler daha doğru sonuçlar üretir, ancak yürütmenin daha yavaş olmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometryisvalid"></a><a name="isvalid"></a>CD2DGeometry::Geçersiz

Kaynak geçerliliğini denetler

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerliyse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cd2dgeometrym_pgeometry"></a><a name="m_pgeometry"></a>CD2DGeometri::m_pGeometry

ID2D1Geometry için bir işaretçi.

```
ID2D1Geometry* m_pGeometry;
```

## <a name="cd2dgeometryoperator-id2d1geometry"></a><a name="operator_id2d1geometry_star"></a>CD2DGeometri::operatör ID2D1Geometri*

ID2D1Geometri arabirimi döndürür

```
operator ID2D1Geometry*();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1Geometri arabirimini işaretçi.

## <a name="cd2dgeometryoutline"></a><a name="outline"></a>CD2DGeometri::Anahat

Geometrinin anahatlarını hesaplar ve sonucu bir ID2D1SimplifiedGeometrySink'e yazar.

```
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*worldTransform*<br/>
Geometri anahattına uygulanacak dönüşüm.

*geometriLavabo*<br/>
Geometrinin anahat değiştirdiği ID2D1BasitleştirilmişGeometriSink.

*düzlemeToleransToleransı*<br/>
Geometrinin poligonal yaklaşıkdeğerindeki noktalar arasındaki mesafenin maksimum sınırları. Daha küçük değerler daha doğru sonuçlar üretir, ancak yürütmenin daha yavaş olmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrysimplify"></a><a name="simplify"></a>CD2DGeometry::Basitleştir

Geometrinin yalnızca çizgileri ve (isteğe bağlı olarak) kübik Bezier eğrilerini içeren basitleştirilmiş bir sürümünü oluşturur ve sonucu bir ID2D1SimplifiedGeometrySink'e yazar.

```
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*basitleştirmeSeçeneği*<br/>
Basitleştirilmiş geometrinin eğriler içerip içermeyeceğini belirten bir değer.

*worldTransform*<br/>
Basitleştirilmiş geometriye uygulanacak dönüşüm.

*geometriLavabo*<br/>
Basitleştirilmiş geometrinin eklendiği ID2D1Basitleştirilmiş GeometriSink.

*düzlemeToleransToleransı*<br/>
Geometrinin poligonal yaklaşıkdeğerindeki noktalar arasındaki mesafenin maksimum sınırları. Daha küçük değerler daha doğru sonuçlar üretir, ancak yürütmenin daha yavaş olmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrystrokecontainspoint"></a><a name="strokecontainspoint"></a>CD2DGeometri::StrokeContainsPoint

Geometrinin konturun belirtilen kontur kalınlığı, stili ve dönüşümü göz önüne alındığında belirtilen noktayı bulunup içermediğini belirler.

```
BOOL StrokeContainsPoint(
    CD2DPointF point,
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
Kapsama için test etmek için nokta.

*konturGenişliği*<br/>
Kontur kalınlığı uygulanacak.

*strokeStyle*<br/>
Uygulanacak kontur stili.

*worldTransform*<br/>
Konturlu geometriye uygulanacak dönüşüm.

*Içerir*<br/>
Bu yöntem döndüğünde, geometrinin kontur belirtilen noktayı içeriyorsa TRUE için ayarlanmış bir boolean değeri içerir; aksi takdirde, YANLIŞ. Bu parametre için depolama alanı ayırmanız gerekir.

*düzlemeToleransToleransı*<br/>
Kesin geometrik yol ve yol kesişiminin hesaplandığı sayısal doğruluk. Toleranstan daha az kontur eksik noktaları hala içinde kabul edilir. Daha küçük değerler daha doğru sonuçlar üretir, ancak yürütmenin daha yavaş olmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrytessellate"></a><a name="tessellate"></a>CD2DGeometri::Tessellate

Belirtilen matris kullanılarak dönüştürüldükten ve belirtilen tolerans kullanılarak düzleştirilmiş sonra geometriyi kaplayan saat yönünde bir üçgen kümesi oluşturur.

```
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1TessellationSink* tessellationSink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*worldTransform*<br/>
Bu geometriye uygulanacak dönüştürme veya NULL.

*tessellationLavabo*<br/>
Tessellated eklenmiş olduğu ID2D1TessellationSink.

*düzlemeToleransToleransı*<br/>
Geometrinin poligonal yaklaşıkdeğerindeki noktalar arasındaki mesafenin maksimum sınırları. Daha küçük değerler daha doğru sonuçlar üretir, ancak yürütmenin daha yavaş olmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrywiden"></a><a name="widen"></a>CD2DGeometri::Genişlet

Geometriyi belirtilen konturla genişletir ve belirtilen matris tarafından dönüştürüldükten ve belirtilen tolerans kullanılarak düzleştirildikten sonra sonucu BIR ID2D1BasitleştirilmişGeometrySink'e yazar.

```
BOOL Widen(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*konturGenişliği*<br/>
Geometriyi genişletmek için hangi miktar.

*strokeStyle*<br/>
Geometriye uygulanacak kontur stili veya NULL.

*worldTransform*<br/>
Genişlettikten sonra geometriye uygulanacak dönüştürme.

*geometriLavabo*<br/>
Genişleyen geometrinin eklendiği ID2D1Basitleştirilmiş GeometriSink.

*düzlemeToleransToleransı*<br/>
Geometrinin poligonal yaklaşıkdeğerindeki noktalar arasındaki mesafenin maksimum sınırları. Daha küçük değerler daha doğru sonuçlar üretir, ancak yürütmenin daha yavaş olmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
