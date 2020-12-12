---
description: 'Daha fazla bilgi edinin: CD2DPathGeometry Class'
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
ms.openlocfilehash: eb33d498436c887eb038b3312e2b98ca04d6620b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280540"
---
# <a name="cd2dpathgeometry-class"></a>CD2DPathGeometry sınıfı

ID2D1PathGeometry için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CD2DPathGeometry : public CD2DGeometry;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPathGeometry::CD2DPathGeometry](#cd2dpathgeometry)|Bir CD2DPathGeometry nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPathGeometry:: Attach](#attach)|Varolan kaynak arabirimini nesneye iliştirir|
|[CD2DPathGeometry:: Create](#create)|Bir CD2DPathGeometry oluşturur. (Geçersiz kılmalar [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DPathGeometry::D estroy](#destroy)|Bir CD2DPathGeometry nesnesini yok eder. (Geçersiz kılmalar [CD2DGeometry::D estroy](../../mfc/reference/cd2dgeometry-class.md#destroy).)|
|[CD2DPathGeometry::D etach](#detach)|Nesneden kaynak arabirimini ayırır|
|[CD2DPathGeometry::GetFigureCount](#getfigurecount)|Yol geometrisi içindeki şekil sayısını alır.|
|[CD2DPathGeometry::GetSegmentCount](#getsegmentcount)|Yol geometrisi içindeki segmentlerin sayısını alır.|
|[CD2DPathGeometry:: Open](#open)|Yol geometrisini rakamlar ve kesimlerle doldurmak için kullanılan geometri havuzunu alır.|
|[CD2DPathGeometry:: Stream](#stream)|Yol geometrisinin içeriğini belirtilen ID2D1GeometrySink kopyalar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPathGeometry:: m_pPathGeometry](#m_ppathgeometry)|Bir ID2D1PathGeometry işaretçisi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)

`CD2DPathGeometry`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dpathgeometryattach"></a><a name="attach"></a> CD2DPathGeometry:: Attach

Varolan kaynak arabirimini nesneye iliştirir

```cpp
void Attach(ID2D1PathGeometry* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz

## <a name="cd2dpathgeometrycd2dpathgeometry"></a><a name="cd2dpathgeometry"></a> CD2DPathGeometry::CD2DPathGeometry

Bir CD2DPathGeometry nesnesi oluşturur.

```
CD2DPathGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi işaretçisi.

*bAutoDestroy*<br/>
Nesnenin sahip tarafından (pParentTarget) yok edileceği anlamına gelir.

## <a name="cd2dpathgeometrycreate"></a><a name="create"></a> CD2DPathGeometry:: Create

Bir CD2DPathGeometry oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dpathgeometrydestroy"></a><a name="destroy"></a> CD2DPathGeometry::D estroy

Bir CD2DPathGeometry nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dpathgeometrydetach"></a><a name="detach"></a> CD2DPathGeometry::D etach

Nesneden kaynak arabirimini ayırır

```
ID2D1PathGeometry* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılan kaynak arabirimine yönelik işaretçi.

## <a name="cd2dpathgeometrygetfigurecount"></a><a name="getfigurecount"></a> CD2DPathGeometry::GetFigureCount

Yol geometrisi içindeki şekil sayısını alır.

```
int GetFigureCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol geometrisi içindeki şekil sayısını döndürür.

## <a name="cd2dpathgeometrygetsegmentcount"></a><a name="getsegmentcount"></a> CD2DPathGeometry::GetSegmentCount

Yol geometrisi içindeki segmentlerin sayısını alır.

```
int GetSegmentCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol geometrisi içindeki segmentlerin sayısını döndürür.

## <a name="cd2dpathgeometrym_ppathgeometry"></a><a name="m_ppathgeometry"></a> CD2DPathGeometry:: m_pPathGeometry

Bir ID2D1PathGeometry işaretçisi.

```
ID2D1PathGeometry* m_pPathGeometry;
```

## <a name="cd2dpathgeometryopen"></a><a name="open"></a> CD2DPathGeometry:: Open

Yol geometrisini rakamlar ve kesimlerle doldurmak için kullanılan geometri havuzunu alır.

```
ID2D1GeometrySink* Open();
```

### <a name="return-value"></a>Dönüş Değeri

Yol geometrisini rakamlar ve kesimlerle doldurmak için kullanılan ID2D1GeometrySink için bir işaretçi.

## <a name="cd2dpathgeometrystream"></a><a name="stream"></a> CD2DPathGeometry:: Stream

Yol geometrisinin içeriğini belirtilen ID2D1GeometrySink kopyalar.

```
BOOL Stream(ID2D1GeometrySink* geometrySink);
```

### <a name="parameters"></a>Parametreler

*geometrySink*<br/>
Yol geometrisinin içeriğinin kopyalandığı havuz. Bu havuz değiştirildiğinde, bu yol geometrisinin içeriği değişmez.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
