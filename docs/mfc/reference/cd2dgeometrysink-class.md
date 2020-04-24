---
title: CD2DGeometrySink Sınıfı
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
ms.openlocfilehash: bb5d2b53fa5899ac84608dc4ace6a84a3e5a7575
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754770"
---
# <a name="cd2dgeometrysink-class"></a>CD2DGeometrySink Sınıfı

ID2D1GeometrySink için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DGeometrySink;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DGeometrySink::CD2DGeometrySink](#cd2dgeometrysink)|CD2DPathGeometry nesnesinden bir CD2DGeometrySink nesnesi oluşturmaz.|
|[CD2DGeometrySink::~CD2DGeometrySink](#_dtorcd2dgeometrysink)|Yıkıcı. D2D geometri stoklarında nesne yok edilirken çağrılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DGeometrySink::Addarc](#addarc)|Yol geometrisine tek bir yay ekler|
|[CD2DGeometrySink::AddBezier](#addbezier)|Geçerli nokta ile belirtilen bitiş noktası arasında bir kübik Bezier eğrisi oluşturur.|
|[CD2DGeometrySink::AddBeziers](#addbeziers)|Kübik Bezier eğrileri bir dizi oluşturur ve geometri lavabo bunları ekler.|
|[CD2DGeometrySink::AddLine](#addline)|Geçerli nokta ile belirtilen bitiş noktası arasında bir çizgi kesimi oluşturur ve geometri lavaboya ekler.|
|[CD2DGeometrySink::Addlines](#addlines)|Belirtilen noktaları kullanarak bir satır dizisi oluşturur ve bunları geometri lavaboya ekler.|
|[CD2DGeometrySink::AddQuadraticBezier](#addquadraticbezier)|Geçerli nokta ile belirtilen bitiş noktası arasında kuadratik bir Bezier eğrisi oluşturur.|
|[CD2DGeometrySink::AddQuadraticBeziers](#addquadraticbeziers)|Tek bir çağrıda bir dizi olarak kuadratik Bezier segmentleri dizisi ekler.|
|[CD2DGeometrySink::Başlangıç Şekli](#beginfigure)|Belirtilen noktada yeni bir rakam başlatır.|
|[CD2DGeometrySink::Kapat](#close)|Geometri lavabosu kapatır|
|[CD2DGeometrySink::EndFigure](#endfigure)|Geçerli rakamı sona erdirer; isteğe bağlı olarak kapatır.|
|[CD2DGeometrySink::Get](#get)|ID2D1GeometrySink arabirimi döndürür|
|[CD2DGeometrySink::Geçersiz](#isvalid)|Geometri lavabo geçerliliğini denetler|
|[CD2DGeometrySink::SetfillMode](#setfillmode)|Bu geometri lavabosu tarafından açıklanan geometri içinde hangi noktaların olduğunu ve hangi noktaların dışında olduğunu belirlemek için kullanılan yöntemi belirtir.|
|[CD2DGeometrySink::SetSegmentFlags](#setsegmentflags)|Geometri lavabosu için eklenen yeni segmentlere uygulanacak kontur ve birleştirme seçeneklerini belirtir.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DGeometrySink::operatör ID2D1GeometrySink*](#operator_id2d1geometrysink_star)|ID2D1GeometrySink arabirimi döndürür|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CD2DGeometriSink::m_pSink](#m_psink)|ID2D1GeometrySink için bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CD2DGeometrySink`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="_dtorcd2dgeometrysink"></a>CD2DGeometrySink::~CD2DGeometrySink

Yıkıcı. D2D geometri stoklarında nesne yok edilirken çağrılır.

```
virtual ~CD2DGeometrySink();
```

## <a name="cd2dgeometrysinkaddarc"></a><a name="addarc"></a>CD2DGeometrySink::Addarc

Yol geometrisine tek bir yay ekler

```cpp
void AddArc(const D2D1_ARC_SEGMENT& arc);
```

### <a name="parameters"></a>Parametreler

*Arc*<br/>
Şekle eklenecek yay kesimi

## <a name="cd2dgeometrysinkaddbezier"></a><a name="addbezier"></a>CD2DGeometrySink::AddBezier

Geçerli nokta ile belirtilen bitiş noktası arasında bir kübik Bezier eğrisi oluşturur.

```cpp
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>Parametreler

*Bezier*<br/>
Eklenecek Bezier eğrisinin denetim noktalarını ve bitiş noktasını açıklayan bir yapı.

## <a name="cd2dgeometrysinkaddbeziers"></a><a name="addbeziers"></a>CD2DGeometrySink::AddBeziers

Kübik Bezier eğrileri bir dizi oluşturur ve geometri lavabo bunları ekler.

```cpp
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,
    D2D1_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>Parametreler

*Beziers*<br/>
Oluşturmak için Bezier eğrileri açıklayan Bezier segmentleri bir dizi. Eğri, geometri lavabonun geçerli noktasından (çizilen son parçanın bitiş noktası veya BeginFigure tarafından belirtilen konum) dizideki ilk Bezier segmentinin bitiş noktasına çizilir. dizi ek Bezier segmentleri içeriyorsa, sonraki her Bezier kesimi başlangıç noktası olarak önceki Bezier kesiminin bitiş noktasını kullanır.

## <a name="cd2dgeometrysinkaddline"></a><a name="addline"></a>CD2DGeometrySink::AddLine

Geçerli nokta ile belirtilen bitiş noktası arasında bir çizgi kesimi oluşturur ve geometri lavaboya ekler.

```cpp
void AddLine(CD2DPointF point);
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
Çizilen çizginin bitiş noktası.

## <a name="cd2dgeometrysinkaddlines"></a><a name="addlines"></a>CD2DGeometrySink::Addlines

Belirtilen noktaları kullanarak bir satır dizisi oluşturur ve bunları geometri lavaboya ekler.

```cpp
void AddLines(
    const CArray<CD2DPointF,
    CD2DPointF>& points);
```

### <a name="parameters"></a>Parametreler

*Puan*<br/>
Çizecek çizgileri açıklayan bir veya daha fazla nokta dizisi. Bir çizgi, geometri lavabonun geçerli noktasından (çizilen son parçanın bitiş noktası veya BeginFigure tarafından belirtilen konum) dizideki ilk noktaya çizilir. dizi ek noktalar içeriyorsa, bir çizgi dizideki ilk noktadan ikinci noktaya, ikinci noktadan üçüncü noktaya kadar çizilir. Çizecek çizgilerin bitiş noktalarının bir dizi.

## <a name="cd2dgeometrysinkaddquadraticbezier"></a><a name="addquadraticbezier"></a>CD2DGeometrySink::AddQuadraticBezier

Geçerli nokta ile belirtilen bitiş noktası arasında kuadratik bir Bezier eğrisi oluşturur.

```cpp
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>Parametreler

*Bezier*<br/>
Eklemek için kuadratik Bezier eğrisinin kontrol noktası ve bitiş noktasını açıklayan bir yapı.

## <a name="cd2dgeometrysinkaddquadraticbeziers"></a><a name="addquadraticbeziers"></a>CD2DGeometrySink::AddQuadraticBeziers

Tek bir çağrıda bir dizi olarak kuadratik Bezier segmentleri dizisi ekler.

```cpp
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>Parametreler

*Beziers*<br/>
Bir dizi kuadratik Bezier segmenti.

## <a name="cd2dgeometrysinkbeginfigure"></a><a name="beginfigure"></a>CD2DGeometrySink::Başlangıç Şekli

Belirtilen noktada yeni bir rakam başlatır.

```cpp
void BeginFigure(
    CD2DPointF startPoint,
    D2D1_FIGURE_BEGIN figureBegin);
```

### <a name="parameters"></a>Parametreler

*başlangıçNoktası*<br/>
Yeni rakambaşlamak için hangi nokta.

*şekilBaşlangıç*<br/>
Yeni rakam içi boş veya dolu olmalıdır.

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="cd2dgeometrysink"></a>CD2DGeometrySink::CD2DGeometrySink

CD2DPathGeometry nesnesinden bir CD2DGeometrySink nesnesi oluşturmaz.

```
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```

### <a name="parameters"></a>Parametreler

*Pathgeometry*<br/>
Varolan bir CD2DPathGeometri nesnesi.

## <a name="cd2dgeometrysinkclose"></a><a name="close"></a>CD2DGeometrySink::Kapat

Geometri lavabosu kapatır

```
BOOL Close();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde YANLIŞ.

## <a name="cd2dgeometrysinkendfigure"></a><a name="endfigure"></a>CD2DGeometrySink::EndFigure

Geçerli rakamı sona erdirer; isteğe bağlı olarak kapatır.

```cpp
void EndFigure(D2D1_FIGURE_END figureEnd);
```

### <a name="parameters"></a>Parametreler

*figureEnd*<br/>
Geçerli şeklin kapalı olup olmadığını gösteren bir değer. Şekil kapatılırsa, geçerli nokta ile BeginFigure tarafından belirtilen başlangıç noktası arasında bir çizgi çizilir.

## <a name="cd2dgeometrysinkget"></a><a name="get"></a>CD2DGeometrySink::Get

ID2D1GeometrySink arabirimi döndürür

```
ID2D1GeometrySink* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1GeometrySink arabirimini işaretçi.

## <a name="cd2dgeometrysinkisvalid"></a><a name="isvalid"></a>CD2DGeometrySink::Geçersiz

Geometri lavabo geçerliliğini denetler

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geometri lavabo geçerli ise DOĞRU; aksi takdirde YANLIŞ.

## <a name="cd2dgeometrysinkm_psink"></a><a name="m_psink"></a>CD2DGeometriSink::m_pSink

ID2D1GeometrySink için bir işaretçi.

```
ID2D1GeometrySink* m_pSink;
```

## <a name="cd2dgeometrysinkoperator-id2d1geometrysink"></a><a name="operator_id2d1geometrysink_star"></a>CD2DGeometrySink::operatör ID2D1GeometrySink*

ID2D1GeometrySink arabirimi döndürür

```
operator ID2D1GeometrySink*();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1GeometrySink arabirimini işaretçi.

## <a name="cd2dgeometrysinksetfillmode"></a><a name="setfillmode"></a>CD2DGeometrySink::SetfillMode

Bu geometri lavabosu tarafından açıklanan geometri içinde hangi noktaların olduğunu ve hangi noktaların dışında olduğunu belirlemek için kullanılan yöntemi belirtir.

```cpp
void SetFillMode(D2D1_FILL_MODE fillMode);
```

### <a name="parameters"></a>Parametreler

*Fillmode*<br/>
Belirli bir noktanın geometrinin bir parçası olup olmadığını belirlemek için kullanılan yöntem.

## <a name="cd2dgeometrysinksetsegmentflags"></a><a name="setsegmentflags"></a>CD2DGeometrySink::SetSegmentFlags

Geometri lavabosu için eklenen yeni segmentlere uygulanacak kontur ve birleştirme seçeneklerini belirtir.

```cpp
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```

### <a name="parameters"></a>Parametreler

*tepe noktasıBayraklar*<br/>
Geometri lavabosu eklenen yeni segmentlere uygulanacak kontur ve birleştirme seçenekleri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
