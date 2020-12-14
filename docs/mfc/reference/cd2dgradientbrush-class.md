---
description: 'Daha fazla bilgi edinin: CD2DGradientBrush Class'
title: CD2DGradientBrush sınıfı
ms.date: 03/27/2019
f1_keywords:
- CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::Destroy
- AFXRENDERTARGET/CD2DGradientBrush::m_arGradientStops
- AFXRENDERTARGET/CD2DGradientBrush::m_colorInterpolationGamma
- AFXRENDERTARGET/CD2DGradientBrush::m_extendMode
- AFXRENDERTARGET/CD2DGradientBrush::m_pGradientStops
helpviewer_keywords:
- CD2DGradientBrush [MFC], CD2DGradientBrush
- CD2DGradientBrush [MFC], Destroy
- CD2DGradientBrush [MFC], m_arGradientStops
- CD2DGradientBrush [MFC], m_colorInterpolationGamma
- CD2DGradientBrush [MFC], m_extendMode
- CD2DGradientBrush [MFC], m_pGradientStops
ms.assetid: 5bf133e6-16b7-4e3a-845d-0ce63fafe5ec
ms.openlocfilehash: c1af08ae27bd2cbee48c4abe22f413ffeb85cd1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193402"
---
# <a name="cd2dgradientbrush-class"></a>CD2DGradientBrush sınıfı

CD2DLinearGradientBrush ve CD2DRadialGradientBrush sınıflarının temel sınıfı.

## <a name="syntax"></a>Syntax

```
class CD2DGradientBrush : public CD2DBrush;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGradientBrush::CD2DGradientBrush](#cd2dgradientbrush)|Bir CD2DGradientBrush nesnesi oluşturur.|
|[CD2DGradientBrush:: ~ CD2DGradientBrush](#_dtorcd2dgradientbrush)|Yok edicisi. D2D gradyan fırçası nesnesi yok edildiğinde çağırılır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGradientBrush::D estroy](#destroy)|Bir CD2DGradientBrush nesnesini yok eder. (Geçersiz kılmalar [CD2DBrush::D estroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGradientBrush:: m_arGradientStops](#m_argradientstops)|D2D1_GRADIENT_STOP yapılarının dizisi.|
|[CD2DGradientBrush:: m_colorInterpolationGamma](#m_colorinterpolationgamma)|Gradyan duraklarının arasındaki renk ilişkilendirmesinden oluşan alan.|
|[CD2DGradientBrush:: m_extendMode](#m_extendmode)|Degradenin [0, 1] normalleştirilmiş aralığı dışında davranışı.|
|[CD2DGradientBrush:: m_pGradientStops](#m_pgradientstops)|D2D1_GRADIENT_STOP yapılarının dizisine yönelik bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

`CD2DGradientBrush`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dgradientbrushcd2dgradientbrush"></a><a name="_dtorcd2dgradientbrush"></a> CD2DGradientBrush:: ~ CD2DGradientBrush

Yok edicisi. D2D gradyan fırçası nesnesi yok edildiğinde çağırılır.

```
virtual ~CD2DGradientBrush();
```

## <a name="cd2dgradientbrushcd2dgradientbrush"></a><a name="cd2dgradientbrush"></a> CD2DGradientBrush::CD2DGradientBrush

Bir CD2DGradientBrush nesnesi oluşturur.

```
CD2DGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
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

*Colorınterlationgama*<br/>
Gradyan duraklarının arasındaki renk ilişkilendirmesinden oluşan alan.

*extendMode*<br/>
Degradenin [0, 1] normalleştirilmiş aralığı dışında davranışı.

*Pbrühproperties*<br/>
Fırçaya yönelik opaklık ve dönüştürme işaretçisi.

*bAutoDestroy*<br/>
Nesnenin sahip tarafından (pParentTarget) yok edileceği anlamına gelir.

## <a name="cd2dgradientbrushdestroy"></a><a name="destroy"></a> CD2DGradientBrush::D estroy

Bir CD2DGradientBrush nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dgradientbrushm_argradientstops"></a><a name="m_argradientstops"></a> CD2DGradientBrush:: m_arGradientStops

D2D1_GRADIENT_STOP yapılarının dizisi.

```
CArray<D2D1_GRADIENT_STOP, D2D1_GRADIENT_STOP> m_arGradientStops;
```

## <a name="cd2dgradientbrushm_colorinterpolationgamma"></a><a name="m_colorinterpolationgamma"></a> CD2DGradientBrush:: m_colorInterpolationGamma

Gradyan duraklarının arasındaki renk ilişkilendirmesinden oluşan alan.

```
D2D1_GAMMA m_colorInterpolationGamma;
```

## <a name="cd2dgradientbrushm_extendmode"></a><a name="m_extendmode"></a> CD2DGradientBrush:: m_extendMode

Degradenin [0, 1] normalleştirilmiş aralığı dışında davranışı.

```
D2D1_EXTEND_MODE m_extendMode;
```

## <a name="cd2dgradientbrushm_pgradientstops"></a><a name="m_pgradientstops"></a> CD2DGradientBrush:: m_pGradientStops

D2D1_GRADIENT_STOP yapılarının dizisine yönelik bir işaretçi.

```
ID2D1GradientStopCollection* m_pGradientStops;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
