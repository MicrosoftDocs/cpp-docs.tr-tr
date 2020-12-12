---
description: 'Daha fazla bilgi edinin: CD2DRadialGradientBrush Class'
title: CD2DRadialGradientBrush sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::Attach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Create
- AFXRENDERTARGET/CD2DRadialGradientBrush::Destroy
- AFXRENDERTARGET/CD2DRadialGradientBrush::Detach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Get
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_pRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_RadialGradientBrushProperties
helpviewer_keywords:
- CD2DRadialGradientBrush [MFC], CD2DRadialGradientBrush
- CD2DRadialGradientBrush [MFC], Attach
- CD2DRadialGradientBrush [MFC], Create
- CD2DRadialGradientBrush [MFC], Destroy
- CD2DRadialGradientBrush [MFC], Detach
- CD2DRadialGradientBrush [MFC], Get
- CD2DRadialGradientBrush [MFC], GetCenter
- CD2DRadialGradientBrush [MFC], GetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], GetRadiusX
- CD2DRadialGradientBrush [MFC], GetRadiusY
- CD2DRadialGradientBrush [MFC], SetCenter
- CD2DRadialGradientBrush [MFC], SetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], SetRadiusX
- CD2DRadialGradientBrush [MFC], SetRadiusY
- CD2DRadialGradientBrush [MFC], m_pRadialGradientBrush
- CD2DRadialGradientBrush [MFC], m_RadialGradientBrushProperties
ms.assetid: 6c76d84a-d831-4ee2-96f1-82c1f5b0d6a9
ms.openlocfilehash: c5e169a5d608edd246d5c7269c94e3b225fdd491
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118751"
---
# <a name="cd2dradialgradientbrush-class"></a>CD2DRadialGradientBrush sınıfı

ID2D1RadialGradientBrush için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CD2DRadialGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRadialGradientBrush::CD2DRadialGradientBrush](#cd2dradialgradientbrush)|Bir CD2DLinearGradientBrush nesnesi oluşturur.|
|[CD2DRadialGradientBrush:: ~ CD2DRadialGradientBrush](#_dtorcd2dradialgradientbrush)|Yok edicisi. Bir D2D radyal gradyan fırçası nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRadialGradientBrush:: Attach](#attach)|Varolan kaynak arabirimini nesneye iliştirir|
|[CD2DRadialGradientBrush:: Create](#create)|Bir CD2DRadialGradientBrush oluşturur. (Geçersiz kılmalar [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DRadialGradientBrush::D estroy](#destroy)|Bir CD2DRadialGradientBrush nesnesini yok eder. (Geçersiz kılmalar [CD2DGradientBrush::D estroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|
|[CD2DRadialGradientBrush::D etach](#detach)|Nesneden kaynak arabirimini ayırır|
|[CD2DRadialGradientBrush:: Get](#get)|ID2D1RadialGradientBrush arabirimini döndürür|
|[CD2DRadialGradientBrush:: GetCenter](#getcenter)|Gradyan elips merkezini alır|
|[CD2DRadialGradientBrush:: Getgradientoriginkayması](#getgradientoriginoffset)|Gradyan elipsin ortasına göre gradyan başlangıcının sapmasını alır|
|[CD2DRadialGradientBrush:: GetRadiusX](#getradiusx)|Gradyan Elipsin x-yarıçapını alır|
|[CD2DRadialGradientBrush:: GetRadiusY](#getradiusy)|Gradyan elipsin y-yarıçapını alır|
|[CD2DRadialGradientBrush:: SetCenter](#setcenter)|Fırçanın koordinat alanındaki gradyan elipsin merkezini belirtir|
|[CD2DRadialGradientBrush:: Setgradientoriginsapmayı](#setgradientoriginoffset)|Gradyan elipsin merkezine göre gradyan başlangıcının sapmasını belirtir|
|[CD2DRadialGradientBrush:: SetRadiusX](#setradiusx)|Fırçanın koordinat alanındaki gradyan Elipsin x-yarıçapını belirtir|
|[CD2DRadialGradientBrush:: SetRadiusY](#setradiusy)|Fırçanın koordinat alanındaki gradyan elipsin y-yarıçapını belirtir|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRadialGradientBrush:: operator ID2D1RadialGradientBrush *](#operator_id2d1radialgradientbrush_star)|ID2D1RadialGradientBrush arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRadialGradientBrush:: m_pRadialGradientBrush](#m_pradialgradientbrush)|Bir ID2D1RadialGradientBrush işaretçisi.|
|[CD2DRadialGradientBrush:: m_RadialGradientBrushProperties](#m_radialgradientbrushproperties)|Fırça, gradyan kaynak boşluğu ve fırçanın gradyanının degradenin x-radius ve y-Radius.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DRadialGradientBrush`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="_dtorcd2dradialgradientbrush"></a> CD2DRadialGradientBrush:: ~ CD2DRadialGradientBrush

Yok edicisi. Bir D2D radyal gradyan fırçası nesnesi yok edildiğinde çağırılır.

```
virtual ~CD2DRadialGradientBrush();
```

## <a name="cd2dradialgradientbrushattach"></a><a name="attach"></a> CD2DRadialGradientBrush:: Attach

Varolan kaynak arabirimini nesneye iliştirir

```cpp
void Attach(ID2D1RadialGradientBrush* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz

## <a name="cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="cd2dradialgradientbrush"></a> CD2DRadialGradientBrush::CD2DRadialGradientBrush

Bir CD2DLinearGradientBrush nesnesi oluşturur.

```
CD2DRadialGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES RadialGradientBrushProperties,
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

*RadialGradientBrushProperties*<br/>
Fırça, gradyan kaynak boşluğu ve fırçanın gradyanının degradenin x-radius ve y-Radius.

*Colorınterlationgama*<br/>
Gradyan duraklarının arasındaki renk ilişkilendirmesinden oluşan alan.

*extendMode*<br/>
Degradenin [0, 1] normalleştirilmiş aralığı dışında davranışı.

*Pbrühproperties*<br/>
Fırçaya yönelik opaklık ve dönüştürme işaretçisi.

*bAutoDestroy*<br/>
Nesnenin sahip tarafından (pParentTarget) yok edileceği anlamına gelir.

## <a name="cd2dradialgradientbrushcreate"></a><a name="create"></a> CD2DRadialGradientBrush:: Create

Bir CD2DRadialGradientBrush oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dradialgradientbrushdestroy"></a><a name="destroy"></a> CD2DRadialGradientBrush::D estroy

Bir CD2DRadialGradientBrush nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dradialgradientbrushdetach"></a><a name="detach"></a> CD2DRadialGradientBrush::D etach

Nesneden kaynak arabirimini ayırır

```
ID2D1RadialGradientBrush* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılan kaynak arabirimine yönelik işaretçi.

## <a name="cd2dradialgradientbrushget"></a><a name="get"></a> CD2DRadialGradientBrush:: Get

ID2D1RadialGradientBrush arabirimini döndürür

```
ID2D1RadialGradientBrush* Get();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1RadialGradientBrush arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dradialgradientbrushgetcenter"></a><a name="getcenter"></a> CD2DRadialGradientBrush:: GetCenter

Gradyan elips merkezini alır

```
CD2DPointF GetCenter() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gradyan elips merkezi. Bu değer, fırçanın koordinat alanında ifade edilir

## <a name="cd2dradialgradientbrushgetgradientoriginoffset"></a><a name="getgradientoriginoffset"></a> CD2DRadialGradientBrush:: Getgradientoriginkayması

Gradyan elipsin ortasına göre gradyan başlangıcının sapmasını alır

```
CD2DPointF GetGradientOriginOffset() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gradyan elips merkezinden gradyan başlangıcının boşluğu. Bu değer, fırçanın koordinat alanında ifade edilir

## <a name="cd2dradialgradientbrushgetradiusx"></a><a name="getradiusx"></a> CD2DRadialGradientBrush:: GetRadiusX

Gradyan Elipsin x-yarıçapını alır

```
FLOAT GetRadiusX() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gradyan Elipsin x-radius. Bu değer, fırçanın koordinat alanında ifade edilir

## <a name="cd2dradialgradientbrushgetradiusy"></a><a name="getradiusy"></a> CD2DRadialGradientBrush:: GetRadiusY

Gradyan elipsin y-yarıçapını alır

```
FLOAT GetRadiusY() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gradyan elipsin y yarıçapı. Bu değer, fırçanın koordinat alanında ifade edilir

## <a name="cd2dradialgradientbrushm_pradialgradientbrush"></a><a name="m_pradialgradientbrush"></a> CD2DRadialGradientBrush:: m_pRadialGradientBrush

Bir ID2D1RadialGradientBrush işaretçisi.

```
ID2D1RadialGradientBrush* m_pRadialGradientBrush;
```

## <a name="cd2dradialgradientbrushm_radialgradientbrushproperties"></a><a name="m_radialgradientbrushproperties"></a> CD2DRadialGradientBrush:: m_RadialGradientBrushProperties

Fırça, gradyan kaynak boşluğu ve fırçanın gradyanının degradenin x-radius ve y-Radius.

```
D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES m_RadialGradientBrushProperties;
```

## <a name="cd2dradialgradientbrushoperator-id2d1radialgradientbrush"></a><a name="operator_id2d1radialgradientbrush_star"></a> CD2DRadialGradientBrush:: operator ID2D1RadialGradientBrush *

ID2D1RadialGradientBrush arabirimini döndürür

```
operator ID2D1RadialGradientBrush*();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1RadialGradientBrush arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dradialgradientbrushsetcenter"></a><a name="setcenter"></a> CD2DRadialGradientBrush:: SetCenter

Fırçanın koordinat alanındaki gradyan elipsin merkezini belirtir

```cpp
void SetCenter(CD2DPointF point);
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
Fırçanın koordinat alanındaki gradyan elips ortası

## <a name="cd2dradialgradientbrushsetgradientoriginoffset"></a><a name="setgradientoriginoffset"></a> CD2DRadialGradientBrush:: Setgradientoriginsapmayı

Gradyan elipsin merkezine göre gradyan başlangıcının sapmasını belirtir

```cpp
void SetGradientOriginOffset(CD2DPointF gradientOriginOffset);
```

### <a name="parameters"></a>Parametreler

*Gradientoriginsapmayı*<br/>
Gradyan elips merkezinden gradyan başlangıcının boşluğu

## <a name="cd2dradialgradientbrushsetradiusx"></a><a name="setradiusx"></a> CD2DRadialGradientBrush:: SetRadiusX

Fırçanın koordinat alanındaki gradyan Elipsin x-yarıçapını belirtir

```cpp
void SetRadiusX(FLOAT radiusX);
```

### <a name="parameters"></a>Parametreler

*radiusX*<br/>
Gradyan Elipsin x-radius. Bu değer, fırçanın koordinat alanında

## <a name="cd2dradialgradientbrushsetradiusy"></a><a name="setradiusy"></a> CD2DRadialGradientBrush:: SetRadiusY

Fırçanın koordinat alanındaki gradyan elipsin y-yarıçapını belirtir

```cpp
void SetRadiusY(FLOAT radiusY);
```

### <a name="parameters"></a>Parametreler

*radiusY*<br/>
Gradyan elipsin y yarıçapı. Bu değer, fırçanın koordinat alanında

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
