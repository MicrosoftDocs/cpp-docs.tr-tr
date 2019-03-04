---
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
ms.openlocfilehash: 4549b2e7981d5f8493ddf9f24477e75a94ddde8b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271235"
---
# <a name="cd2dgeometry-class"></a>CD2DGeometry sınıfı

ID2D1Geometry için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DGeometry : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometry::CD2DGeometry](#cd2dgeometry)|CD2DGeometry bir nesne oluşturur.|
|[CD2DGeometry:: ~ CD2DGeometry](#_dtorcd2dgeometry)|Yıkıcı. D2D geometri nesnesi yok ediliyorken çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometry::Attach](#attach)|Var olan kaynak arabirimi nesnesine ekler|
|[CD2DGeometry::CombineWithGeometry](#combinewithgeometry)|Bu geometri belirtilen geometri ile birleştirir ve sonuç bir ID2D1SimplifiedGeometrySink depolar.|
|[CD2DGeometry::CompareWithGeometry](#comparewithgeometry)|Bu geometry ve belirtilen geometri kesişimi açıklar. Karşılaştırma, belirtilen düzleştirme dayanıklılık kullanılarak gerçekleştirilir.|
|[CD2DGeometry::ComputeArea](#computearea)|Sonra geometri bölümünü hesaplar tarafından belirtilen matris dönüştürülür ve belirtilen tolerans kullanarak düzleştirilmiş.|
|[CD2DGeometry::ComputeLength](#computelength)|Her bir kesim gibi davranarak çizgiye unrolled geometri uzunluğunu hesaplar.|
|[CD2DGeometry::ComputePointAtLength](#computepointatlength)|Sonra geometri boyunca belirtilen uzaklıkta noktası ve tanjantı vektör hesaplar tarafından belirtilen matris dönüştürülür ve belirtilen tolerans kullanarak düzleştirilmiş.|
|[CD2DGeometry::Destroy](#destroy)|CD2DGeometry nesnesini yok eder. (Geçersiz kılmaları [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DGeometry::detach](#detach)|Kaynak arabirimi nesnesinden ayırır|
|[CD2DGeometry::FillContainsPoint](#fillcontainspoint)|Geometri tarafından dolu alan belirtilen düzleştirme tolerans verilen belirtilen nokta içerip gösterir.|
|[CD2DGeometry::get](#get)|Döndürür ID2D1Geometry arabirimi|
|[CD2DGeometry::GetBounds](#getbounds)||
|[CD2DGeometry::GetWidenedBounds](#getwidenedbounds)|Stil ve belirtilen darbe genişliği göre genişletilmiştir ve tarafından belirtilen matris dönüştürülmüş sonra geometri sınırları alır.|
|[CD2DGeometry::IsValid](#isvalid)|Kaynak geçerlilik denetler (geçersiz kılmaları [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DGeometry::Outline](#outline)|Ana hat geometrisi hesaplar ve sonucu bir ID2D1SimplifiedGeometrySink için yazar.|
|[CD2DGeometry::Simplify](#simplify)|Yalnızca satırları ve (isteğe bağlı olarak) üçüncü derece Bezier eğrileri içerir ve sonuç için bir ID2D1SimplifiedGeometrySink yazan geometri basitleştirilmiş bir sürümünü oluşturur.|
|[CD2DGeometry::StrokeContainsPoint](#strokecontainspoint)|Geometrisinin vuruş verilen belirtilen kontur kalınlığı, stil ve dönüştürme belirtilen nokta içerip içermediğini belirler.|
|[CD2DGeometry::Tessellate](#tessellate)|Belirtilen matris kullanarak dönüştürüldükten sonra geometri kapsar ve belirtilen tolerans kullanarak düzleştirilmiş sargılı saat yönünde üçgenler kümesi oluşturur.|
|[CD2DGeometry::Widen](#widen)|Geometri tarafından belirtilen vuruş widens ve sonra sonucu için bir ID2D1SimplifiedGeometrySink yazar tarafından belirtilen matris dönüştürülür ve belirtilen tolerans kullanarak düzleştirilmiş.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometry::operator ID2D1Geometry *](#operator_id2d1geometry_star)|Döndürür ID2D1Geometry arabirimi|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometry::m_pGeometry](#m_pgeometry)|Bir ID2D1Geometry işaretçisi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DGeometry`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="_dtorcd2dgeometry"></a>  CD2DGeometry:: ~ CD2DGeometry

Yıkıcı. D2D geometri nesnesi yok ediliyorken çağırılır.

```
virtual ~CD2DGeometry();
```

##  <a name="attach"></a>  CD2DGeometry::Attach

Var olan kaynak arabirimi nesnesine ekler

```
void Attach(ID2D1Geometry* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz

##  <a name="cd2dgeometry"></a>  CD2DGeometry::CD2DGeometry

CD2DGeometry bir nesne oluşturur.

```
CD2DGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi için bir işaretçi.

*bAutoDestroy*<br/>
Nesne sahibi tarafından (pParentTarget) edileceği gösterir.

##  <a name="combinewithgeometry"></a>  CD2DGeometry::CombineWithGeometry

Bu geometri belirtilen geometri ile birleştirir ve sonuç bir ID2D1SimplifiedGeometrySink depolar.

```
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,
    D2D1_COMBINE_MODE combineMode,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*inputGeometry*<br/>
Bu örnekle birleştirmek için geometri.

*combineMode*<br/>
Birleştirme işlemi gerçekleştirmek için türü.

*inputGeometryTransform*<br/>
Birleştirme öncesi inputGeometry uygulanacak dönüşüm.

*geometrySink*<br/>
Birleştirme işleminin sonucu.

*flatteningTolerance*<br/>
Uzaklık geometriler Çokgen yaklaşığını noktaları arasında en yüksek sınır. Küçük değerler, daha doğru sonuçlar ancak daha yavaş yürütme neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

##  <a name="comparewithgeometry"></a>  CD2DGeometry::CompareWithGeometry

Bu geometry ve belirtilen geometri kesişimi açıklar. Karşılaştırma, belirtilen düzleştirme dayanıklılık kullanılarak gerçekleştirilir.

```
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*inputGeometry*<br/>
Test etmek için geometri.

*inputGeometryTransform*<br/>
İnputGeometry için uygulanacak dönüşüm.

*flatteningTolerance*<br/>
Uzaklık geometriler Çokgen yaklaşığını noktaları arasında en yüksek sınır. Küçük değerler, daha doğru sonuçlar ancak daha yavaş yürütme neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

##  <a name="computearea"></a>  CD2DGeometry::ComputeArea

Sonra geometri bölümünü hesaplar tarafından belirtilen matris dönüştürülür ve belirtilen tolerans kullanarak düzleştirilmiş.

```
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& area,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*worldTransform*<br/>
Kendi alanı bilgi işlem önce bu geometriye uygulanacak dönüşüm.

*Alan*<br/>
Bu yöntem döndürüldüğünde, dönüştürülen düzleştirilmiş bu geometri sürümü alanı için bir işaretçi içerir. Bu parametre için depolama ayırmanız gerekir.

*flatteningTolerance*<br/>
Uzaklık geometri Çokgen yaklaşığını noktaları arasında en yüksek sınır. Küçük değerler, daha doğru sonuçlar ancak daha yavaş yürütme neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

##  <a name="computelength"></a>  CD2DGeometry::ComputeLength

Her bir kesim gibi davranarak çizgiye unrolled geometri uzunluğunu hesaplar.

```
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& length,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*worldTransform*<br/>
Geometriye uzunluğunu hesaplamak önce uygulanacak dönüşüm.

*Uzunluğu*<br/>
Bu yöntem döndürüldüğünde, geometri uzunluğunu bir işaretçi içerir. Kapalı geometriler için örtük kapanış segment uzunluğu içerir. Bu parametre için depolama ayırmanız gerekir.

*flatteningTolerance*<br/>
Uzaklık geometri Çokgen yaklaşığını noktaları arasında en yüksek sınır. Küçük değerler, daha doğru sonuçlar ancak daha yavaş yürütme neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

##  <a name="computepointatlength"></a>  CD2DGeometry::ComputePointAtLength

Sonra geometri boyunca belirtilen uzaklıkta noktası ve tanjantı vektör hesaplar tarafından belirtilen matris dönüştürülür ve belirtilen tolerans kullanarak düzleştirilmiş.

```
BOOL ComputePointAtLength(
    FLOAT length,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DPointF& point,
    CD2DPointF& unitTangentVector,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*Uzunluğu*<br/>
Nokta ve bulmak için tanjant'in geometrisini boyunca uzaklığı. Bu uzaklığı daha az sonra 0 ise, bu yöntem, geometri ilk noktanın hesaplar. Bu uzaklık, geometri uzunluğundan büyükse, bu yöntem, geometri son noktanın hesaplar.

*worldTransform*<br/>
Belirtilen nokta ve tanjantı hesaplama önce geometriye uygulanacak dönüşüm.

*Noktası*<br/>
Geometri boyunca belirtilen uzaklık konumunda. Geometri boşsa, bu nokta NaN x ve y içeren değerleri.

*unitTangentVector*<br/>
Bu yöntem döndürüldüğünde, geometri boyunca belirtilen uzaklıkta Eğim vektör bir işaretçi içerir. Geometri boşsa, bu vektörü NaN x ve y içeren değerleri. Bu parametre için depolama ayırmanız gerekir.

*flatteningTolerance*<br/>
Uzaklık geometri Çokgen yaklaşığını noktaları arasında en yüksek sınır. Küçük değerler, daha doğru sonuçlar ancak daha yavaş yürütme neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

##  <a name="destroy"></a>  CD2DGeometry::Destroy

CD2DGeometry nesnesini yok eder.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DGeometry::detach

Kaynak arabirimi nesnesinden ayırır

```
ID2D1Geometry* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirim işaretçisi.

##  <a name="fillcontainspoint"></a>  CD2DGeometry::FillContainsPoint

Geometri tarafından dolu alan belirtilen düzleştirme tolerans verilen belirtilen nokta içerip gösterir.

```
BOOL FillContainsPoint(
    CD2DPointF point,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
Test noktası.

*worldTransform*<br/>
Kapsama için test önce geometri uygulanacak dönüşüm.

*içerir*<br/>
Bu yöntem döndürüldüğünde, alan tarafından geometri doldurulmuş noktası içeriyorsa TRUE ise bir bool değeri içerir. Aksi takdirde FALSE. Bu parametre için depolama ayırmanız gerekir.

*flatteningTolerance*<br/>
Sayısal doğrulukla yolu kesişimi ve kesin geometrik yol hesaplanır. Dolgu tarafından tolerans değerinden eksik noktaları hala içinde olarak kabul edilir. Küçük değerler, daha doğru sonuçlar ancak daha yavaş yürütme neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

##  <a name="get"></a>  CD2DGeometry::get

Döndürür ID2D1Geometry arabirimi

```
ID2D1Geometry* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1Geometry arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="getbounds"></a>  CD2DGeometry::GetBounds

```
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,
CD2DRectF& bounds) const;
```

### <a name="parameters"></a>Parametreler

*worldTransform*<br/>
*Sınırları*

### <a name="return-value"></a>Dönüş Değeri

##  <a name="getwidenedbounds"></a>  CD2DGeometry::GetWidenedBounds

Stil ve belirtilen darbe genişliği göre genişletilmiştir ve tarafından belirtilen matris dönüştürülmüş sonra geometri sınırları alır.

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
Tutarı anahattı konturlayarak geometri genişletebilirsiniz.

*strokeStyle*<br/>
Geometri widens vuruş stili.

*worldTransform*<br/>
Geometriye geometri dönüştürüldükten sonra ve geometri konturlanan sonra uygulanacak dönüşüm.

*Sınırları*<br/>
Bu yöntem döndürüldüğünde, genişletti geometri sınırları içerir. Bu parametre için depolama ayırmanız gerekir.

*flatteningTolerance*<br/>
Uzaklık geometriler Çokgen yaklaşığını noktaları arasında en yüksek sınır. Küçük değerler, daha doğru sonuçlar ancak daha yavaş yürütme neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

##  <a name="isvalid"></a>  CD2DGeometry::IsValid

Kaynak geçerlilik denetimleri

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerli ise TRUE; Aksi durumda FALSE.

##  <a name="m_pgeometry"></a>  CD2DGeometry::m_pGeometry

Bir ID2D1Geometry işaretçisi.

```
ID2D1Geometry* m_pGeometry;
```

##  <a name="operator_id2d1geometry_star"></a>  CD2DGeometry::operator ID2D1Geometry *

Döndürür ID2D1Geometry arabirimi

```
operator ID2D1Geometry*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1Geometry arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="outline"></a>  CD2DGeometry::Outline

Ana hat geometrisi hesaplar ve sonucu bir ID2D1SimplifiedGeometrySink için yazar.

```
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*worldTransform*<br/>
Geometri anahattına uygulanacak dönüşüm.

*geometrySink*<br/>
İçin ana hat geometrisi dönüştürülmüş ID2D1SimplifiedGeometrySink eklenir.

*flatteningTolerance*<br/>
Uzaklık geometri Çokgen yaklaşığını noktaları arasında en yüksek sınır. Küçük değerler, daha doğru sonuçlar ancak daha yavaş yürütme neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

##  <a name="simplify"></a>  CD2DGeometry::Simplify

Yalnızca satırları ve (isteğe bağlı olarak) üçüncü derece Bezier eğrileri içerir ve sonuç için bir ID2D1SimplifiedGeometrySink yazan geometri basitleştirilmiş bir sürümünü oluşturur.

```
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*simplificationOption*<br/>
Basitleştirilmiş geometri eğrileri olup olmayacağını belirten bir değeri.

*worldTransform*<br/>
Basitleştirilmiş geometriye uygulanacak dönüşüm.

*geometrySink*<br/>
ID2D1SimplifiedGeometrySink için Basitleştirilmiş geometri eklenir.

*flatteningTolerance*<br/>
Uzaklık geometri Çokgen yaklaşığını noktaları arasında en yüksek sınır. Küçük değerler, daha doğru sonuçlar ancak daha yavaş yürütme neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

##  <a name="strokecontainspoint"></a>  CD2DGeometry::StrokeContainsPoint

Geometrisinin vuruş verilen belirtilen kontur kalınlığı, stil ve dönüştürme belirtilen nokta içerip içermediğini belirler.

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

*Noktası*<br/>
Kapsama için test noktası.

*strokeWidth*<br/>
Uygulanacak kontur kalınlığı.

*strokeStyle*<br/>
Uygulanacak stroke'un stili.

*worldTransform*<br/>
Konturlu geometriye uygulanacak dönüşüm.

*içerir*<br/>
Bu yöntem döndürüldüğünde, geometrisinin vuruş belirtilen nokta içermesi durumunda TRUE olarak ayarlayın. Bir Boole değeri içerir. Aksi takdirde FALSE. Bu parametre için depolama ayırmanız gerekir.

*flatteningTolerance*<br/>
Sayısal doğrulukla yolu kesişimi ve kesin geometrik yol hesaplanır. Tolerans değerinden tarafından vuruş eksik noktaları hala içinde olarak kabul edilir. Küçük değerler, daha doğru sonuçlar ancak daha yavaş yürütme neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

##  <a name="tessellate"></a>  CD2DGeometry::Tessellate

Belirtilen matris kullanarak dönüştürüldükten sonra geometri kapsar ve belirtilen tolerans kullanarak düzleştirilmiş sargılı saat yönünde üçgenler kümesi oluşturur.

```
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1TessellationSink* tessellationSink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametreler

*worldTransform*<br/>
Bu geometrik veya NULL'e uygulanacak dönüşüm.

*tessellationSink*<br/>
ID2D1TessellationSink olduğu grubun Mozaik eklenir.

*flatteningTolerance*<br/>
Uzaklık geometri Çokgen yaklaşığını noktaları arasında en yüksek sınır. Küçük değerler, daha doğru sonuçlar ancak daha yavaş yürütme neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

##  <a name="widen"></a>  CD2DGeometry::Widen

Geometri tarafından belirtilen vuruş widens ve sonra sonucu için bir ID2D1SimplifiedGeometrySink yazar tarafından belirtilen matris dönüştürülür ve belirtilen tolerans kullanarak düzleştirilmiş.

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
Geometri genişletmek üzere tutar.

*strokeStyle*<br/>
Geometri veya NULL uygulamak için vuruş stili.

*worldTransform*<br/>
Geometriye genişletme sonra uygulanacak dönüşüm.

*geometrySink*<br/>
ID2D1SimplifiedGeometrySink için genişletmiştir geometri eklenir.

*flatteningTolerance*<br/>
Uzaklık geometri Çokgen yaklaşığını noktaları arasında en yüksek sınır. Küçük değerler, daha doğru sonuçlar ancak daha yavaş yürütme neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
