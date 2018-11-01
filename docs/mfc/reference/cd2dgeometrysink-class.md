---
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
ms.openlocfilehash: ff68cc737f28763e5545b0ccaf2c0122e78cb051
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654693"
---
# <a name="cd2dgeometrysink-class"></a>CD2DGeometrySink sınıfı

ID2D1GeometrySink için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DGeometrySink;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometrySink::CD2DGeometrySink](#cd2dgeometrysink)|CD2DPathGeometry nesnesinden CD2DGeometrySink bir nesne oluşturur.|
|[CD2DGeometrySink:: ~ CD2DGeometrySink](#_dtorcd2dgeometrysink)|Yıkıcı. D2D geometri havuz nesnesi yok ediliyorken çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometrySink::AddArc](#addarc)|Tek bir yay yolu geometriye ekler|
|[CD2DGeometrySink::AddBezier](#addbezier)|Bir üçüncü dereceden Bezier eğrisi arasında geçerli nokta ile belirtilen uç noktası oluşturur.|
|[CD2DGeometrySink::AddBeziers](#addbeziers)|Üçüncü derece Bezier eğrileri bir dizi oluşturur ve bunları geometri havuza ekler.|
|[CD2DGeometrySink::AddLine](#addline)|Geçerli nokta ile belirtilen bitiş noktası arasında bir çizgi kesimi oluşturur ve geometri havuza ekler.|
|[CD2DGeometrySink::AddLines](#addlines)|Bir dizi satır belirtilen kullanarak oluşturur ve bunları geometri havuza ekler.|
|[CD2DGeometrySink::AddQuadraticBezier](#addquadraticbezier)|Geçerli nokta ile belirtilen bitiş noktası arasında bir ikinci dereceden Bezier eğrisi oluşturur.|
|[CD2DGeometrySink::AddQuadraticBeziers](#addquadraticbeziers)|İkinci dereceden Bezier parçaları bir dizi bir dizi tek bir çağrı olarak ekler.|
|[CD2DGeometrySink::BeginFigure](#beginfigure)|Belirli bir noktada yeni bir şekil başlatır.|
|[CD2DGeometrySink::Close](#close)|Geometri havuz kapatır|
|[CD2DGeometrySink::EndFigure](#endfigure)|Geçerli şekil sona erer; İsteğe bağlı olarak kapatılır.|
|[CD2DGeometrySink::get](#get)|Döndürür ID2D1GeometrySink arabirimi|
|[CD2DGeometrySink::IsValid](#isvalid)|Geometri havuz geçerlilik denetler|
|[CD2DGeometrySink::SetFillMode](#setfillmode)|Noktaları dışında olan ve içinde bu geometri havuzu tarafından açıklanan geometri noktaları olan belirlemek için kullanılan yöntemi belirtir.|
|[CD2DGeometrySink::SetSegmentFlags](#setsegmentflags)|Geometri havuza eklenen yeni kesimleri uygulanacak vuruş ve birleştirme seçeneklerini belirtir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometrySink::operator ID2D1GeometrySink *](#operator_id2d1geometrysink_star)|Döndürür ID2D1GeometrySink arabirimi|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGeometrySink::m_pSink](#m_psink)|Bir ID2D1GeometrySink işaretçisi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CD2DGeometrySink`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="_dtorcd2dgeometrysink"></a>  CD2DGeometrySink:: ~ CD2DGeometrySink

Yıkıcı. D2D geometri havuz nesnesi yok ediliyorken çağırılır.

```
virtual ~CD2DGeometrySink();
```

##  <a name="addarc"></a>  CD2DGeometrySink::AddArc

Tek bir yay yolu geometriye ekler

```
void AddArc(const D2D1_ARC_SEGMENT& arc);
```

### <a name="parameters"></a>Parametreler

*Yay*<br/>
Yay kesimi eklemek için Şekil

##  <a name="addbezier"></a>  CD2DGeometrySink::AddBezier

Bir üçüncü dereceden Bezier eğrisi arasında geçerli nokta ile belirtilen uç noktası oluşturur.

```
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>Parametreler

*Bezier*<br/>
Denetim noktalarını ve uç noktası eklemek için Bezier eğrisinin açıklar yapısı.

##  <a name="addbeziers"></a>  CD2DGeometrySink::AddBeziers

Üçüncü derece Bezier eğrileri bir dizi oluşturur ve bunları geometri havuza ekler.

```
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,
    D2D1_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>Parametreler

*bezierler*<br/>
Bezier parçaları oluşturmak için Bezier eğrileri açıklayan dizisi. Eğri geometri havuz'ın geçerli noktasından (bitiş noktası çizilmiş son segmenti veya BeginFigure tarafından belirtilen konuma) uç noktasına dizideki ilk Bezier kesiminin çizilir. bir dizi ek Bezier segmentler içeriyorsa, her bir sonraki Bezier kesim önceki Bezier kesiminin uç noktası, başlangıç noktası olarak kullanır.

##  <a name="addline"></a>  CD2DGeometrySink::AddLine

Geçerli nokta ile belirtilen bitiş noktası arasında bir çizgi kesimi oluşturur ve geometri havuza ekler.

```
void AddLine(CD2DPointF point);
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
Çizmek için çizginin bitiş noktası.

##  <a name="addlines"></a>  CD2DGeometrySink::AddLines

Bir dizi satır belirtilen kullanarak oluşturur ve bunları geometri havuza ekler.

```
void AddLines(
    const CArray<CD2DPointF,
    CD2DPointF>& points);
```

### <a name="parameters"></a>Parametreler

*noktaları*<br/>
Çizilecek satırları tanımlayan bir veya daha fazla noktaları dizisi. Bir çizgi, dizideki ilk noktasına geometri havuz'ın geçerli noktasından (bitiş noktası çizilmiş son segmenti veya BeginFigure tarafından belirtilen konuma) çizilir. bir dizi ek noktaları içeriyorsa, bir çizgi dizisinde ikinci noktasına ikinci noktasından üçüncü noktası vb. ilk noktasından çizilir. Bir dizi çizgileri çizmek için uç noktaları dizisi.

##  <a name="addquadraticbezier"></a>  CD2DGeometrySink::AddQuadraticBezier

Geçerli nokta ile belirtilen bitiş noktası arasında bir ikinci dereceden Bezier eğrisi oluşturur.

```
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>Parametreler

*Bezier*<br/>
Denetim noktası ve bitiş noktası eklemek için ikinci dereceden Bezier eğrisi açıklar yapısı.

##  <a name="addquadraticbeziers"></a>  CD2DGeometrySink::AddQuadraticBeziers

İkinci dereceden Bezier parçaları bir dizi bir dizi tek bir çağrı olarak ekler.

```
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>Parametreler

*bezierler*<br/>
İkinci dereceden Bezier parçaları bir dizi dizisi.

##  <a name="beginfigure"></a>  CD2DGeometrySink::BeginFigure

Belirli bir noktada yeni bir şekil başlatır.

```
void BeginFigure(
    CD2DPointF startPoint,
    D2D1_FIGURE_BEGIN figureBegin);
```

### <a name="parameters"></a>Parametreler

*startPoint*<br/>
Yeni şekil başlanacak noktası.

*figureBegin*<br/>
Yeni şekil boş veya doldurulmuş olması gerekir.

##  <a name="cd2dgeometrysink"></a>  CD2DGeometrySink::CD2DGeometrySink

CD2DPathGeometry nesnesinden CD2DGeometrySink bir nesne oluşturur.

```
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```

### <a name="parameters"></a>Parametreler

*pathGeometry*<br/>
Mevcut bir CD2DPathGeometry nesne.

##  <a name="close"></a>  CD2DGeometrySink::Close

Geometri havuz kapatır

```
BOOL Close();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda FALSE.

##  <a name="endfigure"></a>  CD2DGeometrySink::EndFigure

Geçerli şekil sona erer; İsteğe bağlı olarak kapatılır.

```
void EndFigure(D2D1_FIGURE_END figureEnd);
```

### <a name="parameters"></a>Parametreler

*figureEnd*<br/>
Geçerli şekil kapalı olup olmadığını belirten bir değer. Şekil kapalı ise, bir çizgi geçerli nokta ile BeginFigure tarafından belirtilen başlangıç noktası arasındaki çizilir.

##  <a name="get"></a>  CD2DGeometrySink::get

Döndürür ID2D1GeometrySink arabirimi

```
ID2D1GeometrySink* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1GeometrySink arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="isvalid"></a>  CD2DGeometrySink::IsValid

Geometri havuz geçerlilik denetler

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geometri havuz geçerli ise TRUE; Aksi durumda FALSE.

##  <a name="m_psink"></a>  CD2DGeometrySink::m_pSink

Bir ID2D1GeometrySink işaretçisi.

```
ID2D1GeometrySink* m_pSink;
```

##  <a name="operator_id2d1geometrysink_star"></a>  CD2DGeometrySink::operator ID2D1GeometrySink *

Döndürür ID2D1GeometrySink arabirimi

```
operator ID2D1GeometrySink*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1GeometrySink arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="setfillmode"></a>  CD2DGeometrySink::SetFillMode

Noktaları dışında olan ve içinde bu geometri havuzu tarafından açıklanan geometri noktaları olan belirlemek için kullanılan yöntemi belirtir.

```
void SetFillMode(D2D1_FILL_MODE fillMode);
```

### <a name="parameters"></a>Parametreler

*fillMode*<br/>
Belirli bir noktaya parçası olup olmadığını belirlemek için kullanılan yöntem.

##  <a name="setsegmentflags"></a>  CD2DGeometrySink::SetSegmentFlags

Geometri havuza eklenen yeni kesimleri uygulanacak vuruş ve birleştirme seçeneklerini belirtir.

```
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```

### <a name="parameters"></a>Parametreler

*vertexFlags*<br/>
Geometri havuza eklenen yeni kesimleri uygulanacak vuruş ve Birleştirme Seçenekleri.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
