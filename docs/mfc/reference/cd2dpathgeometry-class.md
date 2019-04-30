---
title: CD2DPathGeometry sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::Attach
- AFXRENDERTARGET/CD2DPathGeometry::Create
- AFXRENDERTARGET/CD2DPathGeometry::Destroy
- AFXRENDERTARGET/CD2DPathGeometry::Detach
- AFXRENDERTARGET/CD2DPathGeometry::GetFigureCount
- AFXRENDERTARGET/CD2DPathGeometry::GetSegmentCount
- AFXRENDERTARGET/CD2DPathGeometry::Open
- AFXRENDERTARGET/CD2DPathGeometry::Stream
- AFXRENDERTARGET/CD2DPathGeometry::m_pPathGeometry
helpviewer_keywords:
- CD2DPathGeometry [MFC], CD2DPathGeometry
- CD2DPathGeometry [MFC], Attach
- CD2DPathGeometry [MFC], Create
- CD2DPathGeometry [MFC], Destroy
- CD2DPathGeometry [MFC], Detach
- CD2DPathGeometry [MFC], GetFigureCount
- CD2DPathGeometry [MFC], GetSegmentCount
- CD2DPathGeometry [MFC], Open
- CD2DPathGeometry [MFC], Stream
- CD2DPathGeometry [MFC], m_pPathGeometry
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
ms.openlocfilehash: 8657421e67239cdeb782cffbbd42e0c50f6c0e96
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396359"
---
# <a name="cd2dpathgeometry-class"></a>CD2DPathGeometry sınıfı

ID2D1PathGeometry için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DPathGeometry : public CD2DGeometry;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPathGeometry::CD2DPathGeometry](#cd2dpathgeometry)|CD2DPathGeometry bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPathGeometry::Attach](#attach)|Var olan kaynak arabirimi nesnesine ekler|
|[CD2DPathGeometry::Create](#create)|Bir CD2DPathGeometry oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DPathGeometry::Destroy](#destroy)|CD2DPathGeometry nesnesini yok eder. (Geçersiz kılmaları [CD2DGeometry::Destroy](../../mfc/reference/cd2dgeometry-class.md#destroy).)|
|[CD2DPathGeometry::detach](#detach)|Kaynak arabirimi nesnesinden ayırır|
|[CD2DPathGeometry::GetFigureCount](#getfigurecount)|Yol geometrisini rakamı sayısını alır.|
|[CD2DPathGeometry::GetSegmentCount](#getsegmentcount)|Yol geometrisini segmentler sayısını alır.|
|[CD2DPathGeometry::Open](#open)|Şekiller ve kesimleri ile yol geometri doldurmak için kullanılan geometri havuz alır.|
|[CD2DPathGeometry::Stream](#stream)|Belirtilen ID2D1GeometrySink yolu geometriye içeriğini kopyalar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPathGeometry::m_pPathGeometry](#m_ppathgeometry)|Bir ID2D1PathGeometry işaretçisi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)

`CD2DPathGeometry`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="attach"></a>  CD2DPathGeometry::Attach

Var olan kaynak arabirimi nesnesine ekler

```
void Attach(ID2D1PathGeometry* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz

##  <a name="cd2dpathgeometry"></a>  CD2DPathGeometry::CD2DPathGeometry

CD2DPathGeometry bir nesne oluşturur.

```
CD2DPathGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi için bir işaretçi.

*bAutoDestroy*<br/>
Nesne sahibi tarafından (pParentTarget) edileceği gösterir.

##  <a name="create"></a>  CD2DPathGeometry::Create

Bir CD2DPathGeometry oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="destroy"></a>  CD2DPathGeometry::Destroy

CD2DPathGeometry nesnesini yok eder.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DPathGeometry::detach

Kaynak arabirimi nesnesinden ayırır

```
ID2D1PathGeometry* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirim işaretçisi.

##  <a name="getfigurecount"></a>  CD2DPathGeometry::GetFigureCount

Yol geometrisini rakamı sayısını alır.

```
int GetFigureCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şekil yol geometri döndürür.

##  <a name="getsegmentcount"></a>  CD2DPathGeometry::GetSegmentCount

Yol geometrisini segmentler sayısını alır.

```
int GetSegmentCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Segment sayısı yol geometri döndürür.

##  <a name="m_ppathgeometry"></a>  CD2DPathGeometry::m_pPathGeometry

Bir ID2D1PathGeometry işaretçisi.

```
ID2D1PathGeometry* m_pPathGeometry;
```

##  <a name="open"></a>  CD2DPathGeometry::Open

Şekiller ve kesimleri ile yol geometri doldurmak için kullanılan geometri havuz alır.

```
ID2D1GeometrySink* Open();
```

### <a name="return-value"></a>Dönüş Değeri

Şekiller ve kesimleri ile yol geometri doldurmak için kullanılan ID2D1GeometrySink işaretçisi.

##  <a name="stream"></a>  CD2DPathGeometry::Stream

Belirtilen ID2D1GeometrySink yolu geometriye içeriğini kopyalar.

```
BOOL Stream(ID2D1GeometrySink* geometrySink);
```

### <a name="parameters"></a>Parametreler

*geometrySink*<br/>
Havuz için yol geometrisinin içeriği kopyalanır. Bu havuz değiştirerek bu yolu geometri içeriğini değiştirmez.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
