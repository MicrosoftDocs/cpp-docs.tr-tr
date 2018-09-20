---
title: CD2DLinearGradientBrush sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b33b49c818a290d5bcbae20864a4e73006dd1f01
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403937"
---
# <a name="cd2dlineargradientbrush-class"></a>CD2DLinearGradientBrush sınıfı

ID2D1LinearGradientBrush için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DLinearGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLinearGradientBrush::CD2DLinearGradientBrush](#cd2dlineargradientbrush)|CD2DLinearGradientBrush bir nesne oluşturur.|
|[CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush](#_dtorcd2dlineargradientbrush)|Yıkıcı. Doğrusal gradyan fırçası D2D nesnesi yok ediliyorken çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLinearGradientBrush::Attach](#attach)|Var olan kaynak arabirimi nesnesine ekler|
|[CD2DLinearGradientBrush::Create](#create)|Bir CD2DLinearGradientBrush oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DLinearGradientBrush::Destroy](#destroy)|CD2DLinearGradientBrush nesnesini yok eder. (Geçersiz kılmaları [CD2DGradientBrush::Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|
|[CD2DLinearGradientBrush::detach](#detach)|Kaynak arabirimi nesnesinden ayırır|
|[CD2DLinearGradientBrush::get](#get)|Döndürür ID2D1LinearGradientBrush arabirimi|
|[CD2DLinearGradientBrush::GetEndPoint](#getendpoint)|Doğrusal gradyanın bitiş koordinatları alır.|
|[CD2DLinearGradientBrush::GetStartPoint](#getstartpoint)|Doğrusal gradyanın başlangıç koordinatları alır.|
|[CD2DLinearGradientBrush::SetEndPoint](#setendpoint)|Doğrusal gradyanın bitiş koordinatları fırçanın koordinat ayarlar.|
|[CD2DLinearGradientBrush::SetStartPoint](#setstartpoint)|Doğrusal gradyanın başlangıç koordinatları fırçanın koordinat ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLinearGradientBrush::operator ID2D1LinearGradientBrush *](#operator_id2d1lineargradientbrush_star)|Döndürür ID2D1LinearGradientBrush arabirimi|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLinearGradientBrush::m_LinearGradientBrushProperties](#m_lineargradientbrushproperties)|Başlangıç ve bitiş noktalarını geçişin.|
|[CD2DLinearGradientBrush::m_pLinearGradientBrush](#m_plineargradientbrush)|Bir ID2D1LinearGradientBrush işaretçisi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DLinearGradientBrush`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="_dtorcd2dlineargradientbrush"></a>  CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush

Yıkıcı. Doğrusal gradyan fırçası D2D nesnesi yok ediliyorken çağırılır.

```
virtual ~CD2DLinearGradientBrush();
```

##  <a name="attach"></a>  CD2DLinearGradientBrush::Attach

Var olan kaynak arabirimi nesnesine ekler

```
void Attach(ID2D1LinearGradientBrush* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz

##  <a name="cd2dlineargradientbrush"></a>  CD2DLinearGradientBrush::CD2DLinearGradientBrush

CD2DLinearGradientBrush bir nesne oluşturur.

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
İşleme hedefi için bir işaretçi.

*gradientStops*<br/>
Bir dizi D2D1_GRADIENT_STOP yapıları işaretçi.

*gradientStopsCount*<br/>
Gradyan durak sayısı gradientStops dizide belirtir. 1'e eşit veya büyük değer.

*LinearGradientBrushProperties*<br/>
Başlangıç ve bitiş noktalarını geçişin.

*colorInterpolationGamma*<br/>
Alan hangi renkte gradyan duraklarının arasında ilişkilendirme gerçekleştirilir.

*extendMode*<br/>
[0,1] normalleştirilmiş aralığın dışında geçişin davranışı.

*pBrushProperties*<br/>
Fırça dönüşümü ve opaklık yönelik işaretçi.

*bAutoDestroy*<br/>
Nesne sahibi tarafından (pParentTarget) edileceği gösterir.

##  <a name="create"></a>  CD2DLinearGradientBrush::Create

Bir CD2DLinearGradientBrush oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="destroy"></a>  CD2DLinearGradientBrush::Destroy

CD2DLinearGradientBrush nesnesini yok eder.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DLinearGradientBrush::detach

Kaynak arabirimi nesnesinden ayırır

```
ID2D1LinearGradientBrush* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirim işaretçisi.

##  <a name="get"></a>  CD2DLinearGradientBrush::get

Döndürür ID2D1LinearGradientBrush arabirimi

```
ID2D1LinearGradientBrush* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1LinearGradientBrush arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="getendpoint"></a>  CD2DLinearGradientBrush::GetEndPoint

Doğrusal gradyanın bitiş koordinatları alır.

```
CD2DPointF GetEndPoint() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fırçanın koordinat alanında doğrusal gradyan bitiş iki boyutlu koordinatlarını

##  <a name="getstartpoint"></a>  CD2DLinearGradientBrush::GetStartPoint

Doğrusal gradyanın başlangıç koordinatları alır.

```
CD2DPointF GetStartPoint() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fırçanın koordinat alanında doğrusal gradyan başlangıç iki boyutlu koordinatlarını

##  <a name="m_lineargradientbrushproperties"></a>  CD2DLinearGradientBrush::m_LinearGradientBrushProperties

Başlangıç ve bitiş noktalarını geçişin.

```
D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES m_LinearGradientBrushProperties;
```

##  <a name="m_plineargradientbrush"></a>  CD2DLinearGradientBrush::m_pLinearGradientBrush

Bir ID2D1LinearGradientBrush işaretçisi.

```
ID2D1LinearGradientBrush* m_pLinearGradientBrush;
```

##  <a name="operator_id2d1lineargradientbrush_star"></a>  CD2DLinearGradientBrush::operator ID2D1LinearGradientBrush *

Döndürür ID2D1LinearGradientBrush arabirimi

```
operator ID2D1LinearGradientBrush*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1LinearGradientBrush arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="setendpoint"></a>  CD2DLinearGradientBrush::SetEndPoint

Doğrusal gradyanın bitiş koordinatları fırçanın koordinat ayarlar.

```
void SetEndPoint(CD2DPointF point);
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
Fırçanın koordinat alanında doğrusal gradyan bitiş iki boyutlu koordinatlarını

##  <a name="setstartpoint"></a>  CD2DLinearGradientBrush::SetStartPoint

Doğrusal gradyanın başlangıç koordinatları fırçanın koordinat ayarlar.

```
void SetStartPoint(CD2DPointF point);
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
Fırçanın koordinat alanında doğrusal gradyan başlangıç iki boyutlu koordinatlarını

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
