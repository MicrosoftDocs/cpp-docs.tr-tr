---
title: CD2DSolidColorBrush Class
ms.date: 03/27/2019
f1_keywords:
- CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::Attach
- AFXRENDERTARGET/CD2DSolidColorBrush::Create
- AFXRENDERTARGET/CD2DSolidColorBrush::Destroy
- AFXRENDERTARGET/CD2DSolidColorBrush::Detach
- AFXRENDERTARGET/CD2DSolidColorBrush::Get
- AFXRENDERTARGET/CD2DSolidColorBrush::GetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::SetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::m_colorSolid
- AFXRENDERTARGET/CD2DSolidColorBrush::m_pSolidColorBrush
helpviewer_keywords:
- CD2DSolidColorBrush [MFC], CD2DSolidColorBrush
- CD2DSolidColorBrush [MFC], Attach
- CD2DSolidColorBrush [MFC], Create
- CD2DSolidColorBrush [MFC], Destroy
- CD2DSolidColorBrush [MFC], Detach
- CD2DSolidColorBrush [MFC], Get
- CD2DSolidColorBrush [MFC], GetColor
- CD2DSolidColorBrush [MFC], SetColor
- CD2DSolidColorBrush [MFC], m_colorSolid
- CD2DSolidColorBrush [MFC], m_pSolidColorBrush
ms.assetid: d4506637-acce-4f74-8a9b-f0a45571a735
ms.openlocfilehash: f225198193443c11d0294010a5fb71858514c81e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396229"
---
# <a name="cd2dsolidcolorbrush-class"></a>CD2DSolidColorBrush Class

ID2D1SolidColorBrush için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DSolidColorBrush : public CD2DBrush;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSolidColorBrush::CD2DSolidColorBrush](#cd2dsolidcolorbrush)|Fazla Yüklendi. CD2DSolidColorBrush bir nesne oluşturur.|
|[CD2DSolidColorBrush::~CD2DSolidColorBrush](#_dtorcd2dsolidcolorbrush)|Yıkıcı. D2D düz fırça nesnesi yok ediliyorken çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSolidColorBrush::Attach](#attach)|Var olan kaynak arabirimi nesnesine ekler|
|[CD2DSolidColorBrush::Create](#create)|Bir CD2DSolidColorBrush oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DSolidColorBrush::Destroy](#destroy)|CD2DSolidColorBrush nesnesini yok eder. (Geçersiz kılmaları [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|
|[CD2DSolidColorBrush::Detach](#detach)|Kaynak arabirimi nesnesinden ayırır|
|[CD2DSolidColorBrush::Get](#get)|Döndürür ID2D1SolidColorBrush arabirimi|
|[CD2DSolidColorBrush::GetColor](#getcolor)|Tek renk Fırçası rengini alır.|
|[CD2DSolidColorBrush::SetColor](#setcolor)|Bu tek renk Fırçası rengini belirtir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSolidColorBrush::operator ID2D1SolidColorBrush*](#operator_id2d1solidcolorbrush_star)|Döndürür ID2D1SolidColorBrush arabirimi|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSolidColorBrush::m_colorSolid](#m_colorsolid)|Tek renk Fırçası.|
|[CD2DSolidColorBrush::m_pSolidColorBrush](#m_psolidcolorbrush)|ID2D1SolidColorBrush nesneye bir işaretçi depolar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DSolidColorBrush](../../mfc/reference/cd2dsolidcolorbrush-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="_dtorcd2dsolidcolorbrush"></a>  CD2DSolidColorBrush::~CD2DSolidColorBrush

Yıkıcı. D2D düz fırça nesnesi yok ediliyorken çağırılır.

```
virtual ~CD2DSolidColorBrush();
```

##  <a name="attach"></a>  CD2DSolidColorBrush::Attach

Var olan kaynak arabirimi nesnesine ekler

```
void Attach(ID2D1SolidColorBrush* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz

##  <a name="cd2dsolidcolorbrush"></a>  CD2DSolidColorBrush::CD2DSolidColorBrush

CD2DSolidColorBrush bir nesne oluşturur.

```
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,
    D2D1_COLOR_F color,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,
    COLORREF color,
    int nAlpha = 255,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi için bir işaretçi.

*Renk*<br/>
Fırçanın rengi kırmızı, yeşil, mavi ve alfa değerleri.

*pBrushProperties*<br/>
Fırça dönüşümü ve opaklık yönelik işaretçi.

*bAutoDestroy*<br/>
Nesne sahibi tarafından (pParentTarget) edileceği gösterir.

*nAlpha*<br/>
Fırçanın rengi opaklığını.

##  <a name="create"></a>  CD2DSolidColorBrush::Create

Bir CD2DSolidColorBrush oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="destroy"></a>  CD2DSolidColorBrush::Destroy

CD2DSolidColorBrush nesnesini yok eder.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DSolidColorBrush::Detach

Kaynak arabirimi nesnesinden ayırır

```
ID2D1SolidColorBrush* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirim işaretçisi.

##  <a name="get"></a>  CD2DSolidColorBrush::Get

Döndürür ID2D1SolidColorBrush arabirimi

```
ID2D1SolidColorBrush* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1SolidColorBrush arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="getcolor"></a>  CD2DSolidColorBrush::GetColor

Tek renk Fırçası rengini alır.

```
D2D1_COLOR_F GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu tek renk Fırçası rengi

##  <a name="m_colorsolid"></a>  CD2DSolidColorBrush::m_colorSolid

Tek renk Fırçası.

```
D2D1_COLOR_F m_colorSolid;
```

##  <a name="m_psolidcolorbrush"></a>  CD2DSolidColorBrush::m_pSolidColorBrush

ID2D1SolidColorBrush nesneye bir işaretçi depolar.

```
ID2D1SolidColorBrush* m_pSolidColorBrush;
```

##  <a name="operator_id2d1solidcolorbrush_star"></a>  CD2DSolidColorBrush::operator ID2D1SolidColorBrush*

Döndürür ID2D1SolidColorBrush arabirimi

```
operator ID2D1SolidColorBrush*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1SolidColorBrush arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="setcolor"></a>  CD2DSolidColorBrush::SetColor

Bu tek renk Fırçası rengini belirtir.

```
void SetColor(D2D1_COLOR_F color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
Bu tek renk Fırçası rengi

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
