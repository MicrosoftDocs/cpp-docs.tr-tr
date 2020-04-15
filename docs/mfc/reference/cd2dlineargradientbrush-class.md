---
title: CD2DLinearGradientBrush Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::Attach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Create
- AFXRENDERTARGET/CD2DLinearGradientBrush::Destroy
- AFXRENDERTARGET/CD2DLinearGradientBrush::Detach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Get
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_LinearGradientBrushProperties
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_pLinearGradientBrush
helpviewer_keywords:
- CD2DLinearGradientBrush [MFC], CD2DLinearGradientBrush
- CD2DLinearGradientBrush [MFC], Attach
- CD2DLinearGradientBrush [MFC], Create
- CD2DLinearGradientBrush [MFC], Destroy
- CD2DLinearGradientBrush [MFC], Detach
- CD2DLinearGradientBrush [MFC], Get
- CD2DLinearGradientBrush [MFC], GetEndPoint
- CD2DLinearGradientBrush [MFC], GetStartPoint
- CD2DLinearGradientBrush [MFC], SetEndPoint
- CD2DLinearGradientBrush [MFC], SetStartPoint
- CD2DLinearGradientBrush [MFC], m_LinearGradientBrushProperties
- CD2DLinearGradientBrush [MFC], m_pLinearGradientBrush
ms.assetid: d4be9ff9-0ea8-45e6-9b8d-f3bc5673cbac
ms.openlocfilehash: 6c488d66962f26b6ca9b8c63cb387fc75191085a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369194"
---
# <a name="cd2dlineargradientbrush-class"></a>CD2DLinearGradientBrush Sınıfı

ID2D1LinearGradientBrush için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DLinearGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DLinearGradientBrush::CD2DLinearGradientBrush](#cd2dlineargradientbrush)|CD2DLinearGradientBrush nesnesi oluşturuyor.|
|[CD2DLinearGradientBrush::~CD2DLinearGradientBrush](#_dtorcd2dlineargradientbrush)|Yıkıcı. D2D doğrusal degradeli fırça nesnesi yok edildiğinde çağrılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DLinearGradientBrush::Ekle](#attach)|Nesneye varolan kaynak arabirimi ataştırır|
|[CD2DLinearGradientBrush::Oluştur](#create)|BIR CD2DLinearGradientBrush oluşturur. [(CD2DResource geçersiz kılar::Oluştur](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DLinearGradientBrush::Destroy](#destroy)|BIR CD2DLinearGradientBrush nesnesini yok eder. [(CD2DGradientBrush geçersiz kılar: :Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|
|[CD2DLinearGradientBrush::Detach](#detach)|Kaynak arabirimini nesneden ayırıyor|
|[CD2DLinearGradientBrush::Alın](#get)|ID2D1LinearGradientBrush arabirimi döndürür|
|[CD2DLinearGradientBrush::GetEndPoint](#getendpoint)|Doğrusal degradenin bitiş koordinatlarını alır|
|[CD2DLinearGradientBrush::GetStartPoint](#getstartpoint)|Doğrusal degradenin başlangıç koordinatlarını alır|
|[CD2DLinearGradientBrush::SetEndPoint](#setendpoint)|Fırçanın koordinat uzayında doğrusal degradenin bitiş koordinatlarını ayarlar|
|[CD2DLinearGradientBrush::SetStartPoint](#setstartpoint)|Fırçanın koordinat uzayında doğrusal degradenin başlangıç koordinatlarını ayarlar|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DLinearGradientBrush::operatör ID2D1LinearGradientBrush*](#operator_id2d1lineargradientbrush_star)|ID2D1LinearGradientBrush arabirimi döndürür|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CD2DLinearGradientBrush::m_LinearGradientBrushProperties](#m_lineargradientbrushproperties)|Degradenin başlangıç ve bitiş noktaları.|
|[CD2DLinearGradientBrush::m_pLinearGradientBrush](#m_plineargradientbrush)|ID2D1LinearGradientBrush için bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CD2DKaynak](../../mfc/reference/cd2dresource-class.md)

[CD2DFırça](../../mfc/reference/cd2dbrush-class.md)

[CD2DGradientFırça](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DLinearGradientBrush`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="_dtorcd2dlineargradientbrush"></a>CD2DLinearGradientBrush::~CD2DLinearGradientBrush

Yıkıcı. D2D doğrusal degradeli fırça nesnesi yok edildiğinde çağrılır.

```
virtual ~CD2DLinearGradientBrush();
```

## <a name="cd2dlineargradientbrushattach"></a><a name="attach"></a>CD2DLinearGradientBrush::Ekle

Nesneye varolan kaynak arabirimi ataştırır

```
void Attach(ID2D1LinearGradientBrush* pResource);
```

### <a name="parameters"></a>Parametreler

*pKaynak*<br/>
Varolan kaynak arabirimi. NULL olamaz

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="cd2dlineargradientbrush"></a>CD2DLinearGradientBrush::CD2DLinearGradientBrush

CD2DLinearGradientBrush nesnesi oluşturuyor.

```
CD2DLinearGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES LinearGradientBrushProperties,
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefine işaretçi.

*degradeDuraklar*<br/>
D2D1_GRADIENT_STOP yapıları dizisi için bir işaretçi.

*degradeStopsCount*<br/>
Degrade Duraklar dizisindeki degrade duraklarının sayısını belirten 1'den büyük veya eşit bir değer.

*LinearGradientBrushProperties*<br/>
Degradenin başlangıç ve bitiş noktaları.

*colorInterpolationGamma*<br/>
Degrade durakları arasında renk enterpolasyonunun gerçekleştirildiği alan.

*extendMode*<br/>
[0,1] normalleştirilmiş aralığın dışındaki degradenin davranışı.

*pBrushProperties*<br/>
Bir fırçanın opaklığına ve dönüşümüne işaret eden bir işaretçi.

*bAutoDestroy*<br/>
Nesnenin sahibi (pParentTarget) tarafından yok edileceğini gösterir.

## <a name="cd2dlineargradientbrushcreate"></a><a name="create"></a>CD2DLinearGradientBrush::Oluştur

BIR CD2DLinearGradientBrush oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dlineargradientbrushdestroy"></a><a name="destroy"></a>CD2DLinearGradientBrush::Destroy

BIR CD2DLinearGradientBrush nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dlineargradientbrushdetach"></a><a name="detach"></a>CD2DLinearGradientBrush::Detach

Kaynak arabirimini nesneden ayırıyor

```
ID2D1LinearGradientBrush* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirimine işaretçi.

## <a name="cd2dlineargradientbrushget"></a><a name="get"></a>CD2DLinearGradientBrush::Alın

ID2D1LinearGradientBrush arabirimi döndürür

```
ID2D1LinearGradientBrush* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1LinearGradientBrush arabirimine veya NULL'a işaretçi.

## <a name="cd2dlineargradientbrushgetendpoint"></a><a name="getendpoint"></a>CD2DLinearGradientBrush::GetEndPoint

Doğrusal degradenin bitiş koordinatlarını alır

```
CD2DPointF GetEndPoint() const;
```

### <a name="return-value"></a>Dönüş Değeri

Doğrusal degradenin bitiş iki boyutlu koordinatları, fırçanın koordinat uzayında

## <a name="cd2dlineargradientbrushgetstartpoint"></a><a name="getstartpoint"></a>CD2DLinearGradientBrush::GetStartPoint

Doğrusal degradenin başlangıç koordinatlarını alır

```
CD2DPointF GetStartPoint() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fırçanın koordinat uzayında doğrusal degradenin başlangıç iki boyutlu koordinatları

## <a name="cd2dlineargradientbrushm_lineargradientbrushproperties"></a><a name="m_lineargradientbrushproperties"></a>CD2DLinearGradientBrush::m_LinearGradientBrushProperties

Degradenin başlangıç ve bitiş noktaları.

```
D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES m_LinearGradientBrushProperties;
```

## <a name="cd2dlineargradientbrushm_plineargradientbrush"></a><a name="m_plineargradientbrush"></a>CD2DLinearGradientBrush::m_pLinearGradientBrush

ID2D1LinearGradientBrush için bir işaretçi.

```
ID2D1LinearGradientBrush* m_pLinearGradientBrush;
```

## <a name="cd2dlineargradientbrushoperator-id2d1lineargradientbrush"></a><a name="operator_id2d1lineargradientbrush_star"></a>CD2DLinearGradientBrush::operatör ID2D1LinearGradientBrush*

ID2D1LinearGradientBrush arabirimi döndürür

```
operator ID2D1LinearGradientBrush*();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1LinearGradientBrush arabirimine veya NULL'a işaretçi.

## <a name="cd2dlineargradientbrushsetendpoint"></a><a name="setendpoint"></a>CD2DLinearGradientBrush::SetEndPoint

Fırçanın koordinat uzayında doğrusal degradenin bitiş koordinatlarını ayarlar

```
void SetEndPoint(CD2DPointF point);
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
Doğrusal degradenin bitiş iki boyutlu koordinatları, fırçanın koordinat uzayında

## <a name="cd2dlineargradientbrushsetstartpoint"></a><a name="setstartpoint"></a>CD2DLinearGradientBrush::SetStartPoint

Fırçanın koordinat uzayında doğrusal degradenin başlangıç koordinatlarını ayarlar

```
void SetStartPoint(CD2DPointF point);
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
Fırçanın koordinat uzayında doğrusal degradenin başlangıç iki boyutlu koordinatları

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
