---
description: 'Daha fazla bilgi edinin: CD2DSolidColorBrush Class'
title: CD2DSolidColorBrush sınıfı
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
ms.openlocfilehash: 57df3732a3c4239af6d9121426aa272c6f58417d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154610"
---
# <a name="cd2dsolidcolorbrush-class"></a>CD2DSolidColorBrush sınıfı

ID2D1SolidColorBrush için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CD2DSolidColorBrush : public CD2DBrush;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSolidColorBrush::CD2DSolidColorBrush](#cd2dsolidcolorbrush)|Fazla Yüklendi. Bir CD2DSolidColorBrush nesnesi oluşturur.|
|[CD2DSolidColorBrush:: ~ CD2DSolidColorBrush](#_dtorcd2dsolidcolorbrush)|Yok edicisi. D2D Solid Brush nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSolidColorBrush:: Attach](#attach)|Varolan kaynak arabirimini nesneye iliştirir|
|[CD2DSolidColorBrush:: Create](#create)|Bir CD2DSolidColorBrush oluşturur. (Geçersiz kılmalar [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DSolidColorBrush::D estroy](#destroy)|Bir CD2DSolidColorBrush nesnesini yok eder. (Geçersiz kılmalar [CD2DBrush::D estroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|
|[CD2DSolidColorBrush::D etach](#detach)|Nesneden kaynak arabirimini ayırır|
|[CD2DSolidColorBrush:: Get](#get)|ID2D1SolidColorBrush arabirimini döndürür|
|[CD2DSolidColorBrush:: GetColor](#getcolor)|Düz renk fırçasının rengini alır|
|[CD2DSolidColorBrush:: SetColor](#setcolor)|Bu düz renk fırçasının rengini belirtir|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSolidColorBrush:: operator ID2D1SolidColorBrush *](#operator_id2d1solidcolorbrush_star)|ID2D1SolidColorBrush arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSolidColorBrush:: m_colorSolid](#m_colorsolid)|Fırça düz renk.|
|[CD2DSolidColorBrush:: m_pSolidColorBrush](#m_psolidcolorbrush)|Bir ID2D1SolidColorBrush nesnesine bir işaretçi depolar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DSolidColorBrush](../../mfc/reference/cd2dsolidcolorbrush-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="_dtorcd2dsolidcolorbrush"></a> CD2DSolidColorBrush:: ~ CD2DSolidColorBrush

Yok edicisi. D2D Solid Brush nesnesi yok edildiğinde çağırılır.

```
virtual ~CD2DSolidColorBrush();
```

## <a name="cd2dsolidcolorbrushattach"></a><a name="attach"></a> CD2DSolidColorBrush:: Attach

Varolan kaynak arabirimini nesneye iliştirir

```cpp
void Attach(ID2D1SolidColorBrush* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz

## <a name="cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="cd2dsolidcolorbrush"></a> CD2DSolidColorBrush::CD2DSolidColorBrush

Bir CD2DSolidColorBrush nesnesi oluşturur.

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
İşleme hedefi işaretçisi.

*Renk*<br/>
Fırçanın renginin kırmızı, yeşil, mavi ve alfa değerleri.

*Pbrühproperties*<br/>
Fırçaya yönelik opaklık ve dönüştürme işaretçisi.

*bAutoDestroy*<br/>
Nesnenin sahip tarafından (pParentTarget) yok edileceği anlamına gelir.

*nAlpha*<br/>
Fırçanın renginin geçirgenliği.

## <a name="cd2dsolidcolorbrushcreate"></a><a name="create"></a> CD2DSolidColorBrush:: Create

Bir CD2DSolidColorBrush oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dsolidcolorbrushdestroy"></a><a name="destroy"></a> CD2DSolidColorBrush::D estroy

Bir CD2DSolidColorBrush nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dsolidcolorbrushdetach"></a><a name="detach"></a> CD2DSolidColorBrush::D etach

Nesneden kaynak arabirimini ayırır

```
ID2D1SolidColorBrush* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılan kaynak arabirimine yönelik işaretçi.

## <a name="cd2dsolidcolorbrushget"></a><a name="get"></a> CD2DSolidColorBrush:: Get

ID2D1SolidColorBrush arabirimini döndürür

```
ID2D1SolidColorBrush* Get();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1SolidColorBrush arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dsolidcolorbrushgetcolor"></a><a name="getcolor"></a> CD2DSolidColorBrush:: GetColor

Düz renk fırçasının rengini alır

```
D2D1_COLOR_F GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu düz renk fırçasının rengi

## <a name="cd2dsolidcolorbrushm_colorsolid"></a><a name="m_colorsolid"></a> CD2DSolidColorBrush:: m_colorSolid

Fırça düz renk.

```
D2D1_COLOR_F m_colorSolid;
```

## <a name="cd2dsolidcolorbrushm_psolidcolorbrush"></a><a name="m_psolidcolorbrush"></a> CD2DSolidColorBrush:: m_pSolidColorBrush

Bir ID2D1SolidColorBrush nesnesine bir işaretçi depolar.

```
ID2D1SolidColorBrush* m_pSolidColorBrush;
```

## <a name="cd2dsolidcolorbrushoperator-id2d1solidcolorbrush"></a><a name="operator_id2d1solidcolorbrush_star"></a> CD2DSolidColorBrush:: operator ID2D1SolidColorBrush *

ID2D1SolidColorBrush arabirimini döndürür

```
operator ID2D1SolidColorBrush*();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1SolidColorBrush arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dsolidcolorbrushsetcolor"></a><a name="setcolor"></a> CD2DSolidColorBrush:: SetColor

Bu düz renk fırçasının rengini belirtir

```cpp
void SetColor(D2D1_COLOR_F color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
Bu düz renk fırçasının rengi

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
