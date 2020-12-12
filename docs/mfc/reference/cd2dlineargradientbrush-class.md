---
description: 'Daha fazla bilgi edinin: CD2DLinearGradientBrush Class'
title: CD2DLinearGradientBrush sınıfı
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
ms.openlocfilehash: b133abe796e609a44d1ebe35a6e6e969c8ee2a68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180349"
---
# <a name="cd2dlineargradientbrush-class"></a>CD2DLinearGradientBrush sınıfı

ID2D1LinearGradientBrush için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CD2DLinearGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLinearGradientBrush::CD2DLinearGradientBrush](#cd2dlineargradientbrush)|Bir CD2DLinearGradientBrush nesnesi oluşturur.|
|[CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush](#_dtorcd2dlineargradientbrush)|Yok edicisi. Bir D2D doğrusal gradyan fırçası nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLinearGradientBrush:: Attach](#attach)|Varolan kaynak arabirimini nesneye iliştirir|
|[CD2DLinearGradientBrush:: Create](#create)|Bir CD2DLinearGradientBrush oluşturur. (Geçersiz kılmalar [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DLinearGradientBrush::D estroy](#destroy)|Bir CD2DLinearGradientBrush nesnesini yok eder. (Geçersiz kılmalar [CD2DGradientBrush::D estroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|
|[CD2DLinearGradientBrush::D etach](#detach)|Nesneden kaynak arabirimini ayırır|
|[CD2DLinearGradientBrush:: Get](#get)|ID2D1LinearGradientBrush arabirimini döndürür|
|[CD2DLinearGradientBrush:: GetEndPoint](#getendpoint)|Doğrusal geçişin bitiş koordinatlarını alır|
|[CD2DLinearGradientBrush:: GetStartPoint](#getstartpoint)|Doğrusal gradyanın başlangıç koordinatlarını alır|
|[CD2DLinearGradientBrush:: SetEndPoint](#setendpoint)|Fırçanın koordinat alanındaki Doğrusal degradenin bitiş koordinatlarını ayarlar|
|[CD2DLinearGradientBrush:: SetStartPoint](#setstartpoint)|Fırçanın koordinat alanındaki doğrusal gradyanın başlangıç koordinatlarını ayarlar|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLinearGradientBrush:: operator ID2D1LinearGradientBrush *](#operator_id2d1lineargradientbrush_star)|ID2D1LinearGradientBrush arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLinearGradientBrush:: m_LinearGradientBrushProperties](#m_lineargradientbrushproperties)|Degradenin başlangıç ve bitiş noktaları.|
|[CD2DLinearGradientBrush:: m_pLinearGradientBrush](#m_plineargradientbrush)|Bir ID2D1LinearGradientBrush işaretçisi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DLinearGradientBrush`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="_dtorcd2dlineargradientbrush"></a> CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush

Yok edicisi. Bir D2D doğrusal gradyan fırçası nesnesi yok edildiğinde çağırılır.

```
virtual ~CD2DLinearGradientBrush();
```

## <a name="cd2dlineargradientbrushattach"></a><a name="attach"></a> CD2DLinearGradientBrush:: Attach

Varolan kaynak arabirimini nesneye iliştirir

```cpp
void Attach(ID2D1LinearGradientBrush* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="cd2dlineargradientbrush"></a> CD2DLinearGradientBrush::CD2DLinearGradientBrush

Bir CD2DLinearGradientBrush nesnesi oluşturur.

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
İşleme hedefi işaretçisi.

*GradientStop*<br/>
D2D1_GRADIENT_STOP yapılarının dizisine yönelik bir işaretçi.

*gradientStopsCount*<br/>
GradientStop dizisinde gradyan duraklarının sayısını belirten, 1 ' den büyük veya buna eşit bir değer.

*Doğrgradientbrühproperties*<br/>
Degradenin başlangıç ve bitiş noktaları.

*Colorınterlationgama*<br/>
Gradyan duraklarının arasındaki renk ilişkilendirmesinden oluşan alan.

*extendMode*<br/>
Degradenin [0, 1] normalleştirilmiş aralığı dışında davranışı.

*Pbrühproperties*<br/>
Fırçaya yönelik opaklık ve dönüştürme işaretçisi.

*bAutoDestroy*<br/>
Nesnenin sahip tarafından (pParentTarget) yok edileceği anlamına gelir.

## <a name="cd2dlineargradientbrushcreate"></a><a name="create"></a> CD2DLinearGradientBrush:: Create

Bir CD2DLinearGradientBrush oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dlineargradientbrushdestroy"></a><a name="destroy"></a> CD2DLinearGradientBrush::D estroy

Bir CD2DLinearGradientBrush nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dlineargradientbrushdetach"></a><a name="detach"></a> CD2DLinearGradientBrush::D etach

Nesneden kaynak arabirimini ayırır

```
ID2D1LinearGradientBrush* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılan kaynak arabirimine yönelik işaretçi.

## <a name="cd2dlineargradientbrushget"></a><a name="get"></a> CD2DLinearGradientBrush:: Get

ID2D1LinearGradientBrush arabirimini döndürür

```
ID2D1LinearGradientBrush* Get();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1LinearGradientBrush arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dlineargradientbrushgetendpoint"></a><a name="getendpoint"></a> CD2DLinearGradientBrush:: GetEndPoint

Doğrusal geçişin bitiş koordinatlarını alır

```
CD2DPointF GetEndPoint() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fırçanın koordinat alanındaki doğrusal gradyanın son iki boyutlu koordinatları

## <a name="cd2dlineargradientbrushgetstartpoint"></a><a name="getstartpoint"></a> CD2DLinearGradientBrush:: GetStartPoint

Doğrusal gradyanın başlangıç koordinatlarını alır

```
CD2DPointF GetStartPoint() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fırçanın koordinat alanındaki doğrusal gradyanın başlangıç iki boyutlu koordinatları

## <a name="cd2dlineargradientbrushm_lineargradientbrushproperties"></a><a name="m_lineargradientbrushproperties"></a> CD2DLinearGradientBrush:: m_LinearGradientBrushProperties

Degradenin başlangıç ve bitiş noktaları.

```
D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES m_LinearGradientBrushProperties;
```

## <a name="cd2dlineargradientbrushm_plineargradientbrush"></a><a name="m_plineargradientbrush"></a> CD2DLinearGradientBrush:: m_pLinearGradientBrush

Bir ID2D1LinearGradientBrush işaretçisi.

```
ID2D1LinearGradientBrush* m_pLinearGradientBrush;
```

## <a name="cd2dlineargradientbrushoperator-id2d1lineargradientbrush"></a><a name="operator_id2d1lineargradientbrush_star"></a> CD2DLinearGradientBrush:: operator ID2D1LinearGradientBrush *

ID2D1LinearGradientBrush arabirimini döndürür

```
operator ID2D1LinearGradientBrush*();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1LinearGradientBrush arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dlineargradientbrushsetendpoint"></a><a name="setendpoint"></a> CD2DLinearGradientBrush:: SetEndPoint

Fırçanın koordinat alanındaki Doğrusal degradenin bitiş koordinatlarını ayarlar

```cpp
void SetEndPoint(CD2DPointF point);
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Fırçanın koordinat alanındaki doğrusal gradyanın son iki boyutlu koordinatları

## <a name="cd2dlineargradientbrushsetstartpoint"></a><a name="setstartpoint"></a> CD2DLinearGradientBrush:: SetStartPoint

Fırçanın koordinat alanındaki doğrusal gradyanın başlangıç koordinatlarını ayarlar

```cpp
void SetStartPoint(CD2DPointF point);
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Fırçanın koordinat alanındaki doğrusal gradyanın başlangıç iki boyutlu koordinatları

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
