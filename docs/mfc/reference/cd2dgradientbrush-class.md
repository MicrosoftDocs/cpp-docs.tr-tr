---
title: CD2DGradientBrush Sınıfı
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
ms.openlocfilehash: 861bc32382737bd6482a3d51eb8470bf834e8508
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369224"
---
# <a name="cd2dgradientbrush-class"></a>CD2DGradientBrush Sınıfı

CD2DLinearGradientBrush ve CD2DRadialGradientBrush sınıflarının taban sınıfı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DGradientBrush : public CD2DBrush;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DGradientFırça::CD2DGradientFırça](#cd2dgradientbrush)|CD2DGradientBrush nesnesi oluşturuyor.|
|[CD2DGradientFırça::~CD2DGradientFırça](#_dtorcd2dgradientbrush)|Yıkıcı. D2D degrade fırça nesnesi yok edildiğinde çağrılır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DGradientBrush::Destroy](#destroy)|CD2DGradientBrush nesnesini yok eder. [(Overrides CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CD2DGradientFırça::m_arGradientStops](#m_argradientstops)|D2D1_GRADIENT_STOP yapıları dizisi.|
|[CD2DGradientFırça::m_colorInterpolationGamma](#m_colorinterpolationgamma)|Degrade durakları arasında renk enterpolasyonunun gerçekleştirildiği alan.|
|[CD2DGradientFırça::m_extendMode](#m_extendmode)|[0,1] normalleştirilmiş aralığın dışındaki degradenin davranışı.|
|[CD2DGradientFırça::m_pGradientStops](#m_pgradientstops)|D2D1_GRADIENT_STOP yapıları dizisi için bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CD2DKaynak](../../mfc/reference/cd2dresource-class.md)

[CD2DFırça](../../mfc/reference/cd2dbrush-class.md)

`CD2DGradientBrush`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dgradientbrushcd2dgradientbrush"></a><a name="_dtorcd2dgradientbrush"></a>CD2DGradientFırça::~CD2DGradientFırça

Yıkıcı. D2D degrade fırça nesnesi yok edildiğinde çağrılır.

```
virtual ~CD2DGradientBrush();
```

## <a name="cd2dgradientbrushcd2dgradientbrush"></a><a name="cd2dgradientbrush"></a>CD2DGradientFırça::CD2DGradientFırça

CD2DGradientBrush nesnesi oluşturuyor.

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
İşleme hedefine işaretçi.

*degradeDuraklar*<br/>
D2D1_GRADIENT_STOP yapıları dizisi için bir işaretçi.

*degradeStopsCount*<br/>
Degrade Duraklar dizisindeki degrade duraklarının sayısını belirten 1'den büyük veya eşit bir değer.

*colorInterpolationGamma*<br/>
Degrade durakları arasında renk enterpolasyonunun gerçekleştirildiği alan.

*extendMode*<br/>
[0,1] normalleştirilmiş aralığın dışındaki degradenin davranışı.

*pBrushProperties*<br/>
Bir fırçanın opaklığına ve dönüşümüne işaret eden bir işaretçi.

*bAutoDestroy*<br/>
Nesnenin sahibi (pParentTarget) tarafından yok edileceğini gösterir.

## <a name="cd2dgradientbrushdestroy"></a><a name="destroy"></a>CD2DGradientBrush::Destroy

CD2DGradientBrush nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dgradientbrushm_argradientstops"></a><a name="m_argradientstops"></a>CD2DGradientFırça::m_arGradientStops

D2D1_GRADIENT_STOP yapıları dizisi.

```
CArray<D2D1_GRADIENT_STOP, D2D1_GRADIENT_STOP> m_arGradientStops;
```

## <a name="cd2dgradientbrushm_colorinterpolationgamma"></a><a name="m_colorinterpolationgamma"></a>CD2DGradientFırça::m_colorInterpolationGamma

Degrade durakları arasında renk enterpolasyonunun gerçekleştirildiği alan.

```
D2D1_GAMMA m_colorInterpolationGamma;
```

## <a name="cd2dgradientbrushm_extendmode"></a><a name="m_extendmode"></a>CD2DGradientFırça::m_extendMode

[0,1] normalleştirilmiş aralığın dışındaki degradenin davranışı.

```
D2D1_EXTEND_MODE m_extendMode;
```

## <a name="cd2dgradientbrushm_pgradientstops"></a><a name="m_pgradientstops"></a>CD2DGradientFırça::m_pGradientStops

D2D1_GRADIENT_STOP yapıları dizisi için bir işaretçi.

```
ID2D1GradientStopCollection* m_pGradientStops;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
