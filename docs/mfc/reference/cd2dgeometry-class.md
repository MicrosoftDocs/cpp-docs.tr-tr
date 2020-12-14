---
description: 'Daha fazla bilgi edinin: CD2DGeometry Class'
title: CD2DGeometry sınıfı
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
ms.openlocfilehash: 2c902554ba5377ce9f7a4a481d4001a9ef7a47f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193454"
---
# <a name="cd2dgeometry-class"></a>CD2DGeometry sınıfı

ID2D1Geometry için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CD2DGeometry : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometry::CD2DGeometry](#cd2dgeometry)|Bir CD2DGeometry nesnesi oluşturur.|
|[CD2DGeometry:: ~ CD2DGeometry](#_dtorcd2dgeometry)|Yok edicisi. Bir D2D Geometry nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometry:: Attach](#attach)|Varolan kaynak arabirimini nesneye iliştirir|
|[CD2DGeometry::CombineWithGeometry](#combinewithgeometry)|Bu geometriyi belirtilen geometriyle birleştirir ve sonucu bir ID2D1SimplifiedGeometrySink içinde depolar.|
|[CD2DGeometry:: CompareWithGeometry](#comparewithgeometry)|Bu geometri ve belirtilen geometri arasındaki kesişimini açıklar. Karşılaştırma, belirtilen düzleştirme toleransı kullanılarak gerçekleştirilir.|
|[CD2DGeometry::ComputeArea](#computearea)|Belirtilen matris tarafından dönüştürüldükten sonra geometrinin alanını hesaplar ve belirtilen tolerans kullanılarak düzleştirilir.|
|[CD2DGeometry::ComputeLength](#computelength)|Her segment bir satıra geri alınana rağmen geometri uzunluğunu hesaplar.|
|[CD2DGeometry::ComputePointAtLength](#computepointatlength)|Belirtilen matris ile dönüştürüldükten ve belirtilen tolerans kullanılarak düzleştirildiğinde, belirtilen uzaklığa göre belirtilen mesafede nokta ve teğet vektörünü hesaplar.|
|[CD2DGeometry::D estroy](#destroy)|Bir CD2DGeometry nesnesini yok eder. (Geçersiz kılmalar [CD2DResource::D estroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DGeometry::D etach](#detach)|Nesneden kaynak arabirimini ayırır|
|[CD2DGeometry:: FillContainsPoint](#fillcontainspoint)|Geometri tarafından doldurulmuş alanın belirtilen düzleştirme toleransı verilen noktayı içerip içermediğini gösterir.|
|[CD2DGeometry:: Get](#get)|ID2D1Geometry arabirimini döndürür|
|[CD2DGeometry:: Getsýnýrlarý](#getbounds)||
|[CD2DGeometry::GetWidenedBounds](#getwidenedbounds)|Belirtilen fırça genişliği ve stili tarafından iletildiklerinde ve belirtilen matris tarafından dönüştürüldükten sonra geometrinin sınırlarını alır.|
|[CD2DGeometry:: IsValid](#isvalid)|Kaynak geçerliliğini denetler (geçersiz kılmalar [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DGeometry:: Ana hat](#outline)|Geometri ana hattını hesaplar ve sonucu bir ID2D1SimplifiedGeometrySink yazar.|
|[CD2DGeometry:: Basitleştir](#simplify)|Yalnızca satırlar ve (isteğe bağlı olarak) üçüncü dereceden Bezier eğrileri içeren ve sonucu bir ID2D1SimplifiedGeometrySink yazar.|
|[CD2DGeometry:: StrokeContainsPoint](#strokecontainspoint)|Geometrinin konturunun belirtilen kontur kalınlığı, stili ve dönüştürmesi verilen noktayı içerip içermediğini belirler.|
|[CD2DGeometry:: Tesselgeç](#tessellate)|Belirtilen matris kullanılarak dönüştürüldükten sonra geometriyi kapsayan saat yönünde-wound üçgenler kümesi oluşturur ve belirtilen tolerans kullanılarak düzleştirilir.|
|[CD2DGeometry:: Genişlet](#widen)|Belirtilen kontura göre geometriyi widens ve belirtilen matris ile dönüştürüldükten sonra bir ID2D1SimplifiedGeometrySink öğesine yazar ve belirtilen tolerans kullanılarak düzleştirilir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometry:: operator ID2D1Geometry *](#operator_id2d1geometry_star)|ID2D1Geometry arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometry:: m_pGeometry](#m_pgeometry)|Bir ID2D1Geometry işaretçisi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DGeometry`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dgeometrycd2dgeometry"></a><a name="_dtorcd2dgeometry"></a> CD2DGeometry:: ~ CD2DGeometry

Yok edicisi. Bir D2D Geometry nesnesi yok edildiğinde çağırılır.

```
virtual ~CD2DGeometry();
```

## <a name="cd2dgeometryattach"></a><a name="attach"></a> CD2DGeometry:: Attach

Varolan kaynak arabirimini nesneye iliştirir

```cpp
void Attach(ID2D1Geometry* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz

## <a name="cd2dgeometrycd2dgeometry"></a><a name="cd2dgeometry"></a> CD2DGeometry::CD2DGeometry

Bir CD2DGeometry nesnesi oluşturur.

```
CD2DGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi işaretçisi.

*bAutoDestroy*<br/>
Nesnenin sahip tarafından (pParentTarget) yok edileceği anlamına gelir.

## <a name="cd2dgeometrycombinewithgeometry"></a><a name="combinewithgeometry"></a> CD2DGeometry::CombineWithGeometry

Bu geometriyi belirtilen geometriyle birleştirir ve sonucu bir ID2D1SimplifiedGeometrySink içinde depolar.

```
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,
    D2D1_COMBINE_MODE combineMode,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*ınputgeometry*<br/>
Bu örnekle birleştirilecek geometri.

*combineMode*<br/>
Gerçekleştirilecek birleştirme işleminin türü.

*ınputgeometrytransform*<br/>
Birleştirilmeden önce ınputgeometry 'e uygulanacak dönüşüm.

*geometrySink*<br/>
Birleştirme işleminin sonucu.

*düzet toleransı*<br/>
Geometrilerin Çokgen cinsinden noktaları arasındaki uzaklığın en fazla sınırı. Daha küçük değerler daha doğru sonuçlar üretir ancak yavaş yürütmeye neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrycomparewithgeometry"></a><a name="comparewithgeometry"></a> CD2DGeometry:: CompareWithGeometry

Bu geometri ve belirtilen geometri arasındaki kesişimini açıklar. Karşılaştırma, belirtilen düzleştirme toleransı kullanılarak gerçekleştirilir.

```
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*ınputgeometry*<br/>
Sınanacak geometri.

*ınputgeometrytransform*<br/>
Inputgeometry için uygulanacak dönüşüm.

*düzet toleransı*<br/>
Geometrilerin Çokgen cinsinden noktaları arasındaki uzaklığın en fazla sınırı. Daha küçük değerler daha doğru sonuçlar üretir ancak yavaş yürütmeye neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrycomputearea"></a><a name="computearea"></a> CD2DGeometry::ComputeArea

Belirtilen matris tarafından dönüştürüldükten sonra geometrinin alanını hesaplar ve belirtilen tolerans kullanılarak düzleştirilir.

```
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& area,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*worldTransform*<br/>
Alanını hesaplarken bu geometriye uygulanacak dönüşüm.

*alandır*<br/>
Bu yöntem döndüğünde, bu geometrinin dönüştürülmüş, düzleştirilmiş sürümünün alanı için bir işaretçi içerir. Bu parametre için depolama alanı ayırmanız gerekir.

*düzet toleransı*<br/>
Geometrinin Çokgen cinsinden noktaları arasındaki uzaklığın en fazla sınırı. Daha küçük değerler daha doğru sonuçlar üretir ancak yavaş yürütmeye neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrycomputelength"></a><a name="computelength"></a> CD2DGeometry::ComputeLength

Her segment bir satıra geri alınana rağmen geometri uzunluğunu hesaplar.

```
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& length,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*worldTransform*<br/>
Uzunluğunu hesaplamadan önce geometriye uygulanacak dönüşüm.

*length*<br/>
Bu yöntem döndüğünde, geometri uzunluğuna bir işaretçi içerir. Kapalı geometriler için, uzunluk örtük bir kapanış segmenti içerir. Bu parametre için depolama alanı ayırmanız gerekir.

*düzet toleransı*<br/>
Geometrinin Çokgen cinsinden noktaları arasındaki uzaklığın en fazla sınırı. Daha küçük değerler daha doğru sonuçlar üretir ancak yavaş yürütmeye neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrycomputepointatlength"></a><a name="computepointatlength"></a> CD2DGeometry::ComputePointAtLength

Belirtilen matris ile dönüştürüldükten ve belirtilen tolerans kullanılarak düzleştirildiğinde, belirtilen uzaklığa göre belirtilen mesafede nokta ve teğet vektörünü hesaplar.

```
BOOL ComputePointAtLength(
    FLOAT length,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DPointF& point,
    CD2DPointF& unitTangentVector,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*length*<br/>
Bulunacak noktanın geometrisi ve tanjantın uzaklığı. Bu mesafe daha küçükse 0 ise, bu yöntem geometrinin ilk noktasını hesaplar. Bu uzaklık geometri uzunluğundan büyükse, bu yöntem geometrinin son noktasını hesaplar.

*worldTransform*<br/>
Belirtilen nokta ve tanjantın hesaplanmasından önce geometriye uygulanacak dönüşüm.

*seçeneğinin*<br/>
Geometri üzerinde belirtilen uzaklıkta yer. Geometri boşsa, bu nokta x ve y değerleri olarak NaN değerini içerir.

*Unittangentvektörü*<br/>
Bu yöntem döndüğünde, geometri üzerinde belirtilen mesafede tanjant vektörünün bir işaretçisini içerir. Geometri boşsa, bu vektör x ve y değerleri olarak NaN 'yi içerir. Bu parametre için depolama alanı ayırmanız gerekir.

*düzet toleransı*<br/>
Geometrinin Çokgen cinsinden noktaları arasındaki uzaklığın en fazla sınırı. Daha küçük değerler daha doğru sonuçlar üretir ancak yavaş yürütmeye neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrydestroy"></a><a name="destroy"></a> CD2DGeometry::D estroy

Bir CD2DGeometry nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dgeometrydetach"></a><a name="detach"></a> CD2DGeometry::D etach

Nesneden kaynak arabirimini ayırır

```
ID2D1Geometry* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılan kaynak arabirimine yönelik işaretçi.

## <a name="cd2dgeometryfillcontainspoint"></a><a name="fillcontainspoint"></a> CD2DGeometry:: FillContainsPoint

Geometri tarafından doldurulmuş alanın belirtilen düzleştirme toleransı verilen noktayı içerip içermediğini gösterir.

```
BOOL FillContainsPoint(
    CD2DPointF point,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Sınanacak nokta.

*worldTransform*<br/>
Kapsama için test etmeden önce geometriye uygulanacak dönüşüm.

*vardır*<br/>
Bu yöntem döndüğünde, geometri tarafından doldurulmuş alan nokta içeriyorsa TRUE olan bir bool değeri içerir; Aksi takdirde, FALSE. Bu parametre için depolama alanı ayırmanız gerekir.

*düzet toleransı*<br/>
Kesin geometrik yol ve yol kesişimine göre hesaplanan sayısal doğruluk. Dolstan daha az olan dolgunun eksik olduğu noktaları içinde göz önünde bulundurulmakta. Daha küçük değerler daha doğru sonuçlar üretir ancak yavaş yürütmeye neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometryget"></a><a name="get"></a> CD2DGeometry:: Get

ID2D1Geometry arabirimini döndürür

```
ID2D1Geometry* Get();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1Geometry arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dgeometrygetbounds"></a><a name="getbounds"></a> CD2DGeometry:: Getsýnýrlarý

```
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,
CD2DRectF& bounds) const;
```

### <a name="parameters"></a>Parametreler

*worldTransform*<br/>
*sınırları*

### <a name="return-value"></a>Dönüş Değeri

## <a name="cd2dgeometrygetwidenedbounds"></a><a name="getwidenedbounds"></a> CD2DGeometry::GetWidenedBounds

Belirtilen fırça genişliği ve stili tarafından iletildiklerinde ve belirtilen matris tarafından dönüştürüldükten sonra geometrinin sınırlarını alır.

```
BOOL GetWidenedBounds(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DRectF& bounds,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*strokeWidth*<br/>
Ana hattını konturlayarak geometrinin genişleme miktarı.

*strokeStyle*<br/>
Geometriyi widens eden konturun stili.

*worldTransform*<br/>
Geometri dönüştürüldükten sonra ve geometri, konturlandıktan sonra geometriye uygulanacak bir dönüşüm.

*sınırları*<br/>
Bu yöntem döndüğünde, iletildiklerinde geometrisinin sınırlarını içerir. Bu parametre için depolama alanı ayırmanız gerekir.

*düzet toleransı*<br/>
Geometrilerin Çokgen cinsinden noktaları arasındaki uzaklığın en fazla sınırı. Daha küçük değerler daha doğru sonuçlar üretir ancak yavaş yürütmeye neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometryisvalid"></a><a name="isvalid"></a> CD2DGeometry:: IsValid

Kaynak geçerliliğini denetler

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerliyse doğru; Aksi halde yanlış.

## <a name="cd2dgeometrym_pgeometry"></a><a name="m_pgeometry"></a> CD2DGeometry:: m_pGeometry

Bir ID2D1Geometry işaretçisi.

```
ID2D1Geometry* m_pGeometry;
```

## <a name="cd2dgeometryoperator-id2d1geometry"></a><a name="operator_id2d1geometry_star"></a> CD2DGeometry:: operator ID2D1Geometry *

ID2D1Geometry arabirimini döndürür

```
operator ID2D1Geometry*();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1Geometry arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dgeometryoutline"></a><a name="outline"></a> CD2DGeometry:: Ana hat

Geometri ana hattını hesaplar ve sonucu bir ID2D1SimplifiedGeometrySink yazar.

```
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*worldTransform*<br/>
Geometri ana hattını uygulamak için dönüşüm.

*geometrySink*<br/>
Geometriyi dönüştürülen ana hattın eklendiği ID2D1SimplifiedGeometrySink.

*düzet toleransı*<br/>
Geometrinin Çokgen cinsinden noktaları arasındaki uzaklığın en fazla sınırı. Daha küçük değerler daha doğru sonuçlar üretir ancak yavaş yürütmeye neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrysimplify"></a><a name="simplify"></a> CD2DGeometry:: Basitleştir

Yalnızca satırlar ve (isteğe bağlı olarak) üçüncü dereceden Bezier eğrileri içeren ve sonucu bir ID2D1SimplifiedGeometrySink yazar.

```
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*simplificationOption*<br/>
Basitleştirilmiş geometrinin eğrileri içerip içermediğini belirten bir değer.

*worldTransform*<br/>
Basitleştirilmiş geometriye uygulanacak dönüşüm.

*geometrySink*<br/>
Basitleştirilmiş geometrinin eklendiği ID2D1SimplifiedGeometrySink.

*düzet toleransı*<br/>
Geometrinin Çokgen cinsinden noktaları arasındaki uzaklığın en fazla sınırı. Daha küçük değerler daha doğru sonuçlar üretir ancak yavaş yürütmeye neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrystrokecontainspoint"></a><a name="strokecontainspoint"></a> CD2DGeometry:: StrokeContainsPoint

Geometrinin konturunun belirtilen kontur kalınlığı, stili ve dönüştürmesi verilen noktayı içerip içermediğini belirler.

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

*seçeneğinin*<br/>
Kapsama için test edilecek nokta.

*strokeWidth*<br/>
Uygulanacak konturun kalınlığı.

*strokeStyle*<br/>
Uygulanacak konturun stili.

*worldTransform*<br/>
Konturlu geometriye uygulanacak dönüşüm.

*vardır*<br/>
Bu yöntem döndüğünde, geometrinin konturu belirtilen noktayı içeriyorsa, TRUE olarak ayarlanmış bir Boole değeri içerir; Aksi takdirde, FALSE. Bu parametre için depolama alanı ayırmanız gerekir.

*düzet toleransı*<br/>
Kesin geometrik yol ve yol kesişimine göre hesaplanan sayısal doğruluk. Kabul edilen bir vuruş, toleransı eksik olarak kabul edilir. Daha küçük değerler daha doğru sonuçlar üretir ancak yavaş yürütmeye neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrytessellate"></a><a name="tessellate"></a> CD2DGeometry:: Tesselgeç

Belirtilen matris kullanılarak dönüştürüldükten sonra geometriyi kapsayan saat yönünde-wound üçgenler kümesi oluşturur ve belirtilen tolerans kullanılarak düzleştirilir.

```
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1TessellationSink* tessellationSink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*worldTransform*<br/>
Bu geometriye uygulanacak dönüşüm veya NULL.

*tessellationSink*<br/>
Tesselin eklendiği ID2D1TessellationSink.

*düzet toleransı*<br/>
Geometrinin Çokgen cinsinden noktaları arasındaki uzaklığın en fazla sınırı. Daha küçük değerler daha doğru sonuçlar üretir ancak yavaş yürütmeye neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cd2dgeometrywiden"></a><a name="widen"></a> CD2DGeometry:: Genişlet

Belirtilen kontura göre geometriyi widens ve belirtilen matris ile dönüştürüldükten sonra bir ID2D1SimplifiedGeometrySink öğesine yazar ve belirtilen tolerans kullanılarak düzleştirilir.

```
BOOL Widen(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*strokeWidth*<br/>
Geometrinin genişleme miktarı.

*strokeStyle*<br/>
Geometriye uygulanacak konturun stili veya NULL.

*worldTransform*<br/>
Genişleyen sonra geometriye uygulanacak dönüşüm.

*geometrySink*<br/>
İletildiklerinde geometrisinin eklendiği ID2D1SimplifiedGeometrySink.

*düzet toleransı*<br/>
Geometrinin Çokgen cinsinden noktaları arasındaki uzaklığın en fazla sınırı. Daha küçük değerler daha doğru sonuçlar üretir ancak yavaş yürütmeye neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
