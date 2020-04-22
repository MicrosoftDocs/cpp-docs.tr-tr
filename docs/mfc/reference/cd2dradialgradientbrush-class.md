---
title: CD2DRadialGradientBrush Sınıfı
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
ms.openlocfilehash: 450314fdbf8441b0cc345430518d083573659add
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750309"
---
# <a name="cd2dradialgradientbrush-class"></a>CD2DRadialGradientBrush Sınıfı

ID2D1RadialGradientBrush için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DRadialGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DRadialGradientBrush::CD2DRadialGradientBrush](#cd2dradialgradientbrush)|CD2DLinearGradientBrush nesnesi oluşturuyor.|
|[CD2DRadialGradientBrush::~CD2DRadialGradientBrush](#_dtorcd2dradialgradientbrush)|Yıkıcı. D2D radyal degrade fırça nesnesi yok edildiğinde çağrılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DRadialGradientBrush::Ekle](#attach)|Nesneye varolan kaynak arabirimi ataştırır|
|[CD2DRadialGradientBrush::Oluştur](#create)|BIR CD2DRadialGradientBrush oluşturur. [(CD2DResource geçersiz kılar::Oluştur](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DRadialGradientBrush::Destroy](#destroy)|BIR CD2DRadialGradientBrush nesnesini yok eder. [(CD2DGradientBrush geçersiz kılar: :Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|
|[CD2DRadialGradientBrush::Detach](#detach)|Kaynak arabirimini nesneden ayırıyor|
|[CD2DRadialGradientBrush::Get](#get)|ID2D1RadialGradientBrush arabirimi verir|
|[CD2DRadialGradientBrush::GetCenter](#getcenter)|Degrade elipsin merkezini alır|
|[CD2DRadialGradientBrush::GetGradientOriginOffset](#getgradientoriginoffset)|Degrade elipsin merkezine göre gradyan kaynağının mahsupunu alır|
|[CD2DRadialGradientBrush::GetRadiusX](#getradiusx)|Degrade elipsin x yarıçapını alır|
|[CD2DRadialGradientBrush::GetRadiusY](#getradiusy)|Degrade elipsin y yarıçapını alır|
|[CD2DRadialGradientBrush::SetCenter](#setcenter)|Fırçanın koordinat alanında degrade elipsin merkezini belirtir|
|[CD2DRadialGradientBrush::SetGradientOriginOffset](#setgradientoriginoffset)|Degrade kaynağının elipsin merkezine göre mahsup unu belirtir|
|[CD2DRadialGradientBrush::SetRadiusX](#setradiusx)|Fırçanın koordinat alanında degrade elipsin x yarıçapını belirtir|
|[CD2DRadialGradientBrush::SetRadiusY](#setradiusy)|Fırçanın koordinat alanında degrade elipsin y yarıçapını belirtir|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DRadialGradientBrush::operatör ID2D1RadialGradientBrush*](#operator_id2d1radialgradientbrush_star)|ID2D1RadialGradientBrush arabirimi verir|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CD2DRadialGradientBrush::m_pRadialGradientBrush](#m_pradialgradientbrush)|ID2D1RadialGradientBrush için bir işaretçi.|
|[CD2DRadialGradientBrush::m_RadialGradientBrushProperties](#m_radialgradientbrushproperties)|Fırçanın degradesinin merkezi, degrade kaynağı ofset ve x yarıçapı ve y yarıçapı.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CD2DKaynak](../../mfc/reference/cd2dresource-class.md)

[CD2DFırça](../../mfc/reference/cd2dbrush-class.md)

[CD2DGradientFırça](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DRadialGradientBrush`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="_dtorcd2dradialgradientbrush"></a>CD2DRadialGradientBrush::~CD2DRadialGradientBrush

Yıkıcı. D2D radyal degrade fırça nesnesi yok edildiğinde çağrılır.

```
virtual ~CD2DRadialGradientBrush();
```

## <a name="cd2dradialgradientbrushattach"></a><a name="attach"></a>CD2DRadialGradientBrush::Ekle

Nesneye varolan kaynak arabirimi ataştırır

```cpp
void Attach(ID2D1RadialGradientBrush* pResource);
```

### <a name="parameters"></a>Parametreler

*pKaynak*<br/>
Varolan kaynak arabirimi. NULL olamaz

## <a name="cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="cd2dradialgradientbrush"></a>CD2DRadialGradientBrush::CD2DRadialGradientBrush

CD2DLinearGradientBrush nesnesi oluşturuyor.

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
İşleme hedefine işaretçi.

*degradeDuraklar*<br/>
D2D1_GRADIENT_STOP yapıları dizisi için bir işaretçi.

*degradeStopsCount*<br/>
Degrade Duraklar dizisindeki degrade duraklarının sayısını belirten 1'den büyük veya eşit bir değer.

*RadialGradientBrushProperties*<br/>
Fırçanın degradesinin merkezi, degrade kaynağı ofset ve x yarıçapı ve y yarıçapı.

*colorInterpolationGamma*<br/>
Degrade durakları arasında renk enterpolasyonunun gerçekleştirildiği alan.

*extendMode*<br/>
[0,1] normalleştirilmiş aralığın dışındaki degradenin davranışı.

*pBrushProperties*<br/>
Bir fırçanın opaklığına ve dönüşümüne işaret eden bir işaretçi.

*bAutoDestroy*<br/>
Nesnenin sahibi (pParentTarget) tarafından yok edileceğini gösterir.

## <a name="cd2dradialgradientbrushcreate"></a><a name="create"></a>CD2DRadialGradientBrush::Oluştur

BIR CD2DRadialGradientBrush oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dradialgradientbrushdestroy"></a><a name="destroy"></a>CD2DRadialGradientBrush::Destroy

BIR CD2DRadialGradientBrush nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dradialgradientbrushdetach"></a><a name="detach"></a>CD2DRadialGradientBrush::Detach

Kaynak arabirimini nesneden ayırıyor

```
ID2D1RadialGradientBrush* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirimine işaretçi.

## <a name="cd2dradialgradientbrushget"></a><a name="get"></a>CD2DRadialGradientBrush::Get

ID2D1RadialGradientBrush arabirimi verir

```
ID2D1RadialGradientBrush* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1RadialGradientBrush arabirimini veya NULL'u işaretleyin.

## <a name="cd2dradialgradientbrushgetcenter"></a><a name="getcenter"></a>CD2DRadialGradientBrush::GetCenter

Degrade elipsin merkezini alır

```
CD2DPointF GetCenter() const;
```

### <a name="return-value"></a>Dönüş Değeri

Degrade elipsin merkezi. Bu değer fırçanın koordinat alanında ifade edilir

## <a name="cd2dradialgradientbrushgetgradientoriginoffset"></a><a name="getgradientoriginoffset"></a>CD2DRadialGradientBrush::GetGradientOriginOffset

Degrade elipsin merkezine göre gradyan kaynağının mahsupunu alır

```
CD2DPointF GetGradientOriginOffset() const;
```

### <a name="return-value"></a>Dönüş Değeri

Degrade elipsin merkezinden degrade kaynağının mahsup. Bu değer fırçanın koordinat alanında ifade edilir

## <a name="cd2dradialgradientbrushgetradiusx"></a><a name="getradiusx"></a>CD2DRadialGradientBrush::GetRadiusX

Degrade elipsin x yarıçapını alır

```
FLOAT GetRadiusX() const;
```

### <a name="return-value"></a>Dönüş Değeri

Degrade elipsin x yarıçapı. Bu değer fırçanın koordinat alanında ifade edilir

## <a name="cd2dradialgradientbrushgetradiusy"></a><a name="getradiusy"></a>CD2DRadialGradientBrush::GetRadiusY

Degrade elipsin y yarıçapını alır

```
FLOAT GetRadiusY() const;
```

### <a name="return-value"></a>Dönüş Değeri

Degrade elipsin y yarıçapı. Bu değer fırçanın koordinat alanında ifade edilir

## <a name="cd2dradialgradientbrushm_pradialgradientbrush"></a><a name="m_pradialgradientbrush"></a>CD2DRadialGradientBrush::m_pRadialGradientBrush

ID2D1RadialGradientBrush için bir işaretçi.

```
ID2D1RadialGradientBrush* m_pRadialGradientBrush;
```

## <a name="cd2dradialgradientbrushm_radialgradientbrushproperties"></a><a name="m_radialgradientbrushproperties"></a>CD2DRadialGradientBrush::m_RadialGradientBrushProperties

Fırçanın degradesinin merkezi, degrade kaynağı ofset ve x yarıçapı ve y yarıçapı.

```
D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES m_RadialGradientBrushProperties;
```

## <a name="cd2dradialgradientbrushoperator-id2d1radialgradientbrush"></a><a name="operator_id2d1radialgradientbrush_star"></a>CD2DRadialGradientBrush::operatör ID2D1RadialGradientBrush*

ID2D1RadialGradientBrush arabirimi verir

```
operator ID2D1RadialGradientBrush*();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1RadialGradientBrush arabirimini veya NULL'u işaretleyin.

## <a name="cd2dradialgradientbrushsetcenter"></a><a name="setcenter"></a>CD2DRadialGradientBrush::SetCenter

Fırçanın koordinat alanında degrade elipsin merkezini belirtir

```cpp
void SetCenter(CD2DPointF point);
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
Degrade elipsin merkezi, fırçanın koordinat alanında

## <a name="cd2dradialgradientbrushsetgradientoriginoffset"></a><a name="setgradientoriginoffset"></a>CD2DRadialGradientBrush::SetGradientOriginOffset

Degrade kaynağının elipsin merkezine göre mahsup unu belirtir

```cpp
void SetGradientOriginOffset(CD2DPointF gradientOriginOffset);
```

### <a name="parameters"></a>Parametreler

*degradeOriginOffset*<br/>
Degrade elipsin merkezinden degrade kaynağının mahsup

## <a name="cd2dradialgradientbrushsetradiusx"></a><a name="setradiusx"></a>CD2DRadialGradientBrush::SetRadiusX

Fırçanın koordinat alanında degrade elipsin x yarıçapını belirtir

```cpp
void SetRadiusX(FLOAT radiusX);
```

### <a name="parameters"></a>Parametreler

*Radiusx*<br/>
Degrade elipsin x yarıçapı. Bu değer fırçanın koordinat alanındadır

## <a name="cd2dradialgradientbrushsetradiusy"></a><a name="setradiusy"></a>CD2DRadialGradientBrush::SetRadiusY

Fırçanın koordinat alanında degrade elipsin y yarıçapını belirtir

```cpp
void SetRadiusY(FLOAT radiusY);
```

### <a name="parameters"></a>Parametreler

*Radiusy*<br/>
Degrade elipsin y yarıçapı. Bu değer fırçanın koordinat alanındadır

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
