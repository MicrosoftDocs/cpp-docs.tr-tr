---
title: CD2DPathGeometri Sınıfı
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
ms.openlocfilehash: 59ef82151983720b654502ccf3ca647e55366268
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369176"
---
# <a name="cd2dpathgeometry-class"></a>CD2DPathGeometri Sınıfı

ID2D1PathGeometry için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DPathGeometry : public CD2DGeometry;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DPathGeometri::CD2DPathGeometri](#cd2dpathgeometry)|BIR CD2DPathGeometri nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DPathGeometri::Ekle](#attach)|Nesneye varolan kaynak arabirimi ataştırır|
|[CD2DPathGeometri::Oluştur](#create)|CD2DPathGeometry oluşturur. [(CD2DResource geçersiz kılar::Oluştur](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DPathGeometri::Destroy](#destroy)|BIR CD2DPathGeometri nesnesini yok eder. [(Overrides CD2DGeometry::Destroy](../../mfc/reference/cd2dgeometry-class.md#destroy).)|
|[CD2DPathGeometri::Detach](#detach)|Kaynak arabirimini nesneden ayırıyor|
|[CD2DPathGeometry::GetFigureCount](#getfigurecount)|Yol geometrisindeki şekil sayısını alır.|
|[CD2DPathGeometry::GetSegmentCount](#getsegmentcount)|Yol geometrisindeki segment sayısını alır.|
|[CD2DPathGeometri::Aç](#open)|Yol geometrisini şekiller ve segmentlerle doldurmak için kullanılan geometri lavabosu alır.|
|[CD2DPathGeometri::Akış](#stream)|Yol geometrisinin içeriğini belirtilen ID2D1GeometrySink'e kopyalar.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CD2DPathGeometri::m_pPathGeometry](#m_ppathgeometry)|ID2D1PathGeometry için bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CD2DKaynak](../../mfc/reference/cd2dresource-class.md)

[CD2DGeometri](../../mfc/reference/cd2dgeometry-class.md)

`CD2DPathGeometry`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dpathgeometryattach"></a><a name="attach"></a>CD2DPathGeometri::Ekle

Nesneye varolan kaynak arabirimi ataştırır

```
void Attach(ID2D1PathGeometry* pResource);
```

### <a name="parameters"></a>Parametreler

*pKaynak*<br/>
Varolan kaynak arabirimi. NULL olamaz

## <a name="cd2dpathgeometrycd2dpathgeometry"></a><a name="cd2dpathgeometry"></a>CD2DPathGeometri::CD2DPathGeometri

BIR CD2DPathGeometri nesnesi oluşturuyor.

```
CD2DPathGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefine işaretçi.

*bAutoDestroy*<br/>
Nesnenin sahibi (pParentTarget) tarafından yok edileceğini gösterir.

## <a name="cd2dpathgeometrycreate"></a><a name="create"></a>CD2DPathGeometri::Oluştur

CD2DPathGeometry oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dpathgeometrydestroy"></a><a name="destroy"></a>CD2DPathGeometri::Destroy

BIR CD2DPathGeometri nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dpathgeometrydetach"></a><a name="detach"></a>CD2DPathGeometri::Detach

Kaynak arabirimini nesneden ayırıyor

```
ID2D1PathGeometry* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirimine işaretçi.

## <a name="cd2dpathgeometrygetfigurecount"></a><a name="getfigurecount"></a>CD2DPathGeometry::GetFigureCount

Yol geometrisindeki şekil sayısını alır.

```
int GetFigureCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol geometrisindeki şekil sayısını döndürür.

## <a name="cd2dpathgeometrygetsegmentcount"></a><a name="getsegmentcount"></a>CD2DPathGeometry::GetSegmentCount

Yol geometrisindeki segment sayısını alır.

```
int GetSegmentCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol geometrisindeki segment sayısını döndürür.

## <a name="cd2dpathgeometrym_ppathgeometry"></a><a name="m_ppathgeometry"></a>CD2DPathGeometri::m_pPathGeometry

ID2D1PathGeometry için bir işaretçi.

```
ID2D1PathGeometry* m_pPathGeometry;
```

## <a name="cd2dpathgeometryopen"></a><a name="open"></a>CD2DPathGeometri::Aç

Yol geometrisini şekiller ve segmentlerle doldurmak için kullanılan geometri lavabosu alır.

```
ID2D1GeometrySink* Open();
```

### <a name="return-value"></a>Dönüş Değeri

Yol geometrisini şekiller ve segmentlerle doldurmak için kullanılan ID2D1GeometrySink'inin işaretçisi.

## <a name="cd2dpathgeometrystream"></a><a name="stream"></a>CD2DPathGeometri::Akış

Yol geometrisinin içeriğini belirtilen ID2D1GeometrySink'e kopyalar.

```
BOOL Stream(ID2D1GeometrySink* geometrySink);
```

### <a name="parameters"></a>Parametreler

*geometriLavabo*<br/>
Yol geometrisinin içeriğinin kopyalandığı lavabo. Bu lavabonun değiştirilmesi, bu yol geometrisinin içeriğini değiştirmez.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
