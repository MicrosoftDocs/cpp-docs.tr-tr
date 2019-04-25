---
title: CD2DGradientBrush Class
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
ms.openlocfilehash: 2e04d714e3479224cfc4e207b70483786be33db8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173385"
---
# <a name="cd2dgradientbrush-class"></a>CD2DGradientBrush Class

CD2DLinearGradientBrush CD2DRadialGradientBrush sınıfları ve temel sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CD2DGradientBrush : public CD2DBrush;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGradientBrush::CD2DGradientBrush](#cd2dgradientbrush)|CD2DGradientBrush bir nesne oluşturur.|
|[CD2DGradientBrush:: ~ CD2DGradientBrush](#_dtorcd2dgradientbrush)|Yıkıcı. D2D gradyan fırçası nesnesi yok ediliyorken çağırılır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGradientBrush::Destroy](#destroy)|CD2DGradientBrush nesnesini yok eder. (Geçersiz kılmaları [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DGradientBrush::m_arGradientStops](#m_argradientstops)|D2D1_GRADIENT_STOP yapıları dizisi.|
|[CD2DGradientBrush::m_colorInterpolationGamma](#m_colorinterpolationgamma)|Alan hangi renkte gradyan duraklarının arasında ilişkilendirme gerçekleştirilir.|
|[CD2DGradientBrush::m_extendMode](#m_extendmode)|[0,1] normalleştirilmiş aralığın dışında geçişin davranışı.|
|[CD2DGradientBrush::m_pGradientStops](#m_pgradientstops)|Bir dizi D2D1_GRADIENT_STOP yapıları işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

`CD2DGradientBrush`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="_dtorcd2dgradientbrush"></a>  CD2DGradientBrush:: ~ CD2DGradientBrush

Yıkıcı. D2D gradyan fırçası nesnesi yok ediliyorken çağırılır.

```
virtual ~CD2DGradientBrush();
```

##  <a name="cd2dgradientbrush"></a>  CD2DGradientBrush::CD2DGradientBrush

CD2DGradientBrush bir nesne oluşturur.

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
İşleme hedefi için bir işaretçi.

*gradientStops*<br/>
Bir dizi D2D1_GRADIENT_STOP yapıları işaretçi.

*gradientStopsCount*<br/>
Gradyan durak sayısı gradientStops dizide belirtir. 1'e eşit veya büyük değer.

*colorInterpolationGamma*<br/>
Alan hangi renkte gradyan duraklarının arasında ilişkilendirme gerçekleştirilir.

*extendMode*<br/>
[0,1] normalleştirilmiş aralığın dışında geçişin davranışı.

*pBrushProperties*<br/>
Fırça dönüşümü ve opaklık yönelik işaretçi.

*bAutoDestroy*<br/>
Nesne sahibi tarafından (pParentTarget) edileceği gösterir.

##  <a name="destroy"></a>  CD2DGradientBrush::Destroy

CD2DGradientBrush nesnesini yok eder.

```
virtual void Destroy();
```

##  <a name="m_argradientstops"></a>  CD2DGradientBrush::m_arGradientStops

D2D1_GRADIENT_STOP yapıları dizisi.

```
CArray<D2D1_GRADIENT_STOP, D2D1_GRADIENT_STOP> m_arGradientStops;
```

##  <a name="m_colorinterpolationgamma"></a>  CD2DGradientBrush::m_colorInterpolationGamma

Alan hangi renkte gradyan duraklarının arasında ilişkilendirme gerçekleştirilir.

```
D2D1_GAMMA m_colorInterpolationGamma;
```

##  <a name="m_extendmode"></a>  CD2DGradientBrush::m_extendMode

[0,1] normalleştirilmiş aralığın dışında geçişin davranışı.

```
D2D1_EXTEND_MODE m_extendMode;
```

##  <a name="m_pgradientstops"></a>  CD2DGradientBrush::m_pGradientStops

Bir dizi D2D1_GRADIENT_STOP yapıları işaretçi.

```
ID2D1GradientStopCollection* m_pGradientStops;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
