---
description: 'Daha fazla bilgi edinin: CD2DGeometrySink Class'
title: CD2DGeometrySink sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::AddArc
- AFXRENDERTARGET/CD2DGeometrySink::AddBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddBeziers
- AFXRENDERTARGET/CD2DGeometrySink::AddLine
- AFXRENDERTARGET/CD2DGeometrySink::AddLines
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBeziers
- AFXRENDERTARGET/CD2DGeometrySink::BeginFigure
- AFXRENDERTARGET/CD2DGeometrySink::Close
- AFXRENDERTARGET/CD2DGeometrySink::EndFigure
- AFXRENDERTARGET/CD2DGeometrySink::Get
- AFXRENDERTARGET/CD2DGeometrySink::IsValid
- AFXRENDERTARGET/CD2DGeometrySink::SetFillMode
- AFXRENDERTARGET/CD2DGeometrySink::SetSegmentFlags
- AFXRENDERTARGET/CD2DGeometrySink::m_pSink
helpviewer_keywords:
- CD2DGeometrySink [MFC], CD2DGeometrySink
- CD2DGeometrySink [MFC], AddArc
- CD2DGeometrySink [MFC], AddBezier
- CD2DGeometrySink [MFC], AddBeziers
- CD2DGeometrySink [MFC], AddLine
- CD2DGeometrySink [MFC], AddLines
- CD2DGeometrySink [MFC], AddQuadraticBezier
- CD2DGeometrySink [MFC], AddQuadraticBeziers
- CD2DGeometrySink [MFC], BeginFigure
- CD2DGeometrySink [MFC], Close
- CD2DGeometrySink [MFC], EndFigure
- CD2DGeometrySink [MFC], Get
- CD2DGeometrySink [MFC], IsValid
- CD2DGeometrySink [MFC], SetFillMode
- CD2DGeometrySink [MFC], SetSegmentFlags
- CD2DGeometrySink [MFC], m_pSink
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
ms.openlocfilehash: e7916cdb39272e924a9d6ef6c0a8322d8ce6fb1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193428"
---
# <a name="cd2dgeometrysink-class"></a>CD2DGeometrySink sınıfı

ID2D1GeometrySink için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CD2DGeometrySink;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometrySink::CD2DGeometrySink](#cd2dgeometrysink)|CD2DPathGeometry nesnesinden bir CD2DGeometrySink nesnesi oluşturur.|
|[CD2DGeometrySink:: ~ CD2DGeometrySink](#_dtorcd2dgeometrysink)|Yok edicisi. Bir D2D Geometry havuz nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometrySink:: AddArc](#addarc)|Yol geometrisine tek bir yay ekler|
|[CD2DGeometrySink:: AddBezier](#addbezier)|Geçerli nokta ile belirtilen bitiş noktası arasında üçüncü dereceden Bezier eğrisi oluşturur.|
|[CD2DGeometrySink:: AddBeziers](#addbeziers)|Üçüncü dereceden Bezier eğrilerinin bir dizisini oluşturur ve bunları geometri havuzuna ekler.|
|[CD2DGeometrySink:: AddLine](#addline)|Geçerli nokta ile belirtilen bitiş noktası arasında bir çizgi segmenti oluşturur ve bunu geometri havuzuna ekler.|
|[CD2DGeometrySink:: AddLines](#addlines)|Belirtilen noktaları kullanarak bir satır dizisi oluşturur ve bunları geometri havuzuna ekler.|
|[CD2DGeometrySink:: Addquadkıticbezier](#addquadraticbezier)|Geçerli nokta ile belirtilen bitiş noktası arasında ikinci dereceden Bezier eğrisi oluşturur.|
|[CD2DGeometrySink:: Addquadtiticbeziers](#addquadraticbeziers)|Tek bir çağrıda bir dizi olarak ikinci dereceden Bezier segmentinin bir dizisini ekler.|
|[CD2DGeometrySink:: Beginşekil](#beginfigure)|Belirtilen noktada yeni bir şekil başlatır.|
|[CD2DGeometrySink:: Close](#close)|Geometri havuzunu kapatır|
|[CD2DGeometrySink:: Endşekil](#endfigure)|Geçerli şekli sonlandırır; isteğe bağlı olarak kapatır.|
|[CD2DGeometrySink:: Get](#get)|ID2D1GeometrySink arabirimini döndürür|
|[CD2DGeometrySink:: IsValid](#isvalid)|Geometri havuz geçerliliğini denetler|
|[CD2DGeometrySink:: SetFillMode](#setfillmode)|Bu geometri havuzu tarafından tanımlanan ve hangi noktaların dışında olduğunu belirlemede kullanılan yöntemi belirtir.|
|[CD2DGeometrySink::SetSegmentFlags](#setsegmentflags)|Geometri havuzuna eklenen yeni segmentlere uygulanacak vuruş ve ekleme seçeneklerini belirtir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometrySink:: operator ID2D1GeometrySink *](#operator_id2d1geometrysink_star)|ID2D1GeometrySink arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometrySink:: m_pSink](#m_psink)|Bir ID2D1GeometrySink işaretçisi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CD2DGeometrySink`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="_dtorcd2dgeometrysink"></a> CD2DGeometrySink:: ~ CD2DGeometrySink

Yok edicisi. Bir D2D Geometry havuz nesnesi yok edildiğinde çağırılır.

```
virtual ~CD2DGeometrySink();
```

## <a name="cd2dgeometrysinkaddarc"></a><a name="addarc"></a> CD2DGeometrySink:: AddArc

Yol geometrisine tek bir yay ekler

```cpp
void AddArc(const D2D1_ARC_SEGMENT& arc);
```

### <a name="parameters"></a>Parametreler

*çizil*<br/>
Şekle eklenecek yay segmenti

## <a name="cd2dgeometrysinkaddbezier"></a><a name="addbezier"></a> CD2DGeometrySink:: AddBezier

Geçerli nokta ile belirtilen bitiş noktası arasında üçüncü dereceden Bezier eğrisi oluşturur.

```cpp
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>Parametreler

*Bezier*<br/>
Eklenecek Bezier eğrisinin denetim noktalarını ve bitiş noktasını açıklayan bir yapı.

## <a name="cd2dgeometrysinkaddbeziers"></a><a name="addbeziers"></a> CD2DGeometrySink:: AddBeziers

Üçüncü dereceden Bezier eğrilerinin bir dizisini oluşturur ve bunları geometri havuzuna ekler.

```cpp
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,
    D2D1_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>Parametreler

*bezierler*<br/>
Oluşturulacak Bezier eğrilerini açıklayan bir Bezier kesimleri dizisi. Bir eğri, geometri havuzunun geçerli noktasından (çizilen son segmentin veya Beginşekil tarafından belirtilen konumun bitiş noktası) dizideki ilk Bezier segmentinin bitiş noktasına çizilir. dizi ek Bezier kesimleri içeriyorsa, izleyen her bir Bezier segmenti, başlangıç noktası olarak önceki Bezier segmentinin bitiş noktasını kullanır.

## <a name="cd2dgeometrysinkaddline"></a><a name="addline"></a> CD2DGeometrySink:: AddLine

Geçerli nokta ile belirtilen bitiş noktası arasında bir çizgi segmenti oluşturur ve bunu geometri havuzuna ekler.

```cpp
void AddLine(CD2DPointF point);
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Çizilecek çizginin bitiş noktası.

## <a name="cd2dgeometrysinkaddlines"></a><a name="addlines"></a> CD2DGeometrySink:: AddLines

Belirtilen noktaları kullanarak bir satır dizisi oluşturur ve bunları geometri havuzuna ekler.

```cpp
void AddLines(
    const CArray<CD2DPointF,
    CD2DPointF>& points);
```

### <a name="parameters"></a>Parametreler

*bakış*<br/>
Çizilecek satırları tanımlayan bir veya daha fazla noktaya ait dizi. Geometri havuzunun geçerli noktasından (çizilen son segmentin veya Beginşekil tarafından belirtilen konumun bitiş noktası) dizideki ilk noktaya doğru bir çizgi çizilir. dizi ek noktaları içeriyorsa, ilk noktadan dizideki ikinci noktaya, ikinci noktadan üçüncü noktaya, vb. bir çizgi çizilir. Çizilecek satırların bitiş noktaları dizisinin dizisi.

## <a name="cd2dgeometrysinkaddquadraticbezier"></a><a name="addquadraticbezier"></a> CD2DGeometrySink:: Addquadkıticbezier

Geçerli nokta ile belirtilen bitiş noktası arasında ikinci dereceden Bezier eğrisi oluşturur.

```cpp
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>Parametreler

*Bezier*<br/>
Eklenecek ikinci dereceden Bezier eğrisinin bitiş noktasını ve denetim noktasını tanımlayan bir yapı.

## <a name="cd2dgeometrysinkaddquadraticbeziers"></a><a name="addquadraticbeziers"></a> CD2DGeometrySink:: Addquadtiticbeziers

Tek bir çağrıda bir dizi olarak ikinci dereceden Bezier segmentinin bir dizisini ekler.

```cpp
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>Parametreler

*bezierler*<br/>
İkinci dereceden Bezier segmentlerinin dizi dizisi.

## <a name="cd2dgeometrysinkbeginfigure"></a><a name="beginfigure"></a> CD2DGeometrySink:: Beginşekil

Belirtilen noktada yeni bir şekil başlatır.

```cpp
void BeginFigure(
    CD2DPointF startPoint,
    D2D1_FIGURE_BEGIN figureBegin);
```

### <a name="parameters"></a>Parametreler

*startPoint*<br/>
Yeni şeklin başlayacağı nokta.

*figureBegin*<br/>
Yeni şeklin boş veya doldurulmuş olması gerekip gerekmediğini belirtir.

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="cd2dgeometrysink"></a> CD2DGeometrySink::CD2DGeometrySink

CD2DPathGeometry nesnesinden bir CD2DGeometrySink nesnesi oluşturur.

```
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```

### <a name="parameters"></a>Parametreler

*pathGeometry*<br/>
Var olan bir CD2DPathGeometry nesnesi.

## <a name="cd2dgeometrysinkclose"></a><a name="close"></a> CD2DGeometrySink:: Close

Geometri havuzunu kapatır

```
BOOL Close();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde yanlış.

## <a name="cd2dgeometrysinkendfigure"></a><a name="endfigure"></a> CD2DGeometrySink:: Endşekil

Geçerli şekli sonlandırır; isteğe bağlı olarak kapatır.

```cpp
void EndFigure(D2D1_FIGURE_END figureEnd);
```

### <a name="parameters"></a>Parametreler

*figureEnd*<br/>
Geçerli şeklin kapalı olup olmadığını gösteren bir değer. Şekil kapalıysa, geçerli nokta ile Beginşekil tarafından belirtilen başlangıç noktası arasında bir çizgi çizilir.

## <a name="cd2dgeometrysinkget"></a><a name="get"></a> CD2DGeometrySink:: Get

ID2D1GeometrySink arabirimini döndürür

```
ID2D1GeometrySink* Get();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1GeometrySink arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dgeometrysinkisvalid"></a><a name="isvalid"></a> CD2DGeometrySink:: IsValid

Geometri havuz geçerliliğini denetler

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geometri havuzu geçerliyse TRUE; Aksi halde yanlış.

## <a name="cd2dgeometrysinkm_psink"></a><a name="m_psink"></a> CD2DGeometrySink:: m_pSink

Bir ID2D1GeometrySink işaretçisi.

```
ID2D1GeometrySink* m_pSink;
```

## <a name="cd2dgeometrysinkoperator-id2d1geometrysink"></a><a name="operator_id2d1geometrysink_star"></a> CD2DGeometrySink:: operator ID2D1GeometrySink *

ID2D1GeometrySink arabirimini döndürür

```
operator ID2D1GeometrySink*();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1GeometrySink arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dgeometrysinksetfillmode"></a><a name="setfillmode"></a> CD2DGeometrySink:: SetFillMode

Bu geometri havuzu tarafından tanımlanan ve hangi noktaların dışında olduğunu belirlemede kullanılan yöntemi belirtir.

```cpp
void SetFillMode(D2D1_FILL_MODE fillMode);
```

### <a name="parameters"></a>Parametreler

*fillMode*<br/>
Verilen noktanın geometrinin bir parçası olup olmadığını belirlemede kullanılan yöntem.

## <a name="cd2dgeometrysinksetsegmentflags"></a><a name="setsegmentflags"></a> CD2DGeometrySink::SetSegmentFlags

Geometri havuzuna eklenen yeni segmentlere uygulanacak vuruş ve ekleme seçeneklerini belirtir.

```cpp
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```

### <a name="parameters"></a>Parametreler

*vertexFlags*<br/>
Geometri havuzuna eklenen yeni segmentlere uygulanan vuruş ve ekleme seçenekleri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
