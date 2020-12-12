---
description: 'Daha fazla bilgi edinin: CD2DBrush Class'
title: CD2DBrush sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DBrush
- AFXRENDERTARGET/CD2DBrush
- AFXRENDERTARGET/CD2DBrush::CD2DBrush
- AFXRENDERTARGET/CD2DBrush::Attach
- AFXRENDERTARGET/CD2DBrush::Destroy
- AFXRENDERTARGET/CD2DBrush::Detach
- AFXRENDERTARGET/CD2DBrush::Get
- AFXRENDERTARGET/CD2DBrush::GetOpacity
- AFXRENDERTARGET/CD2DBrush::GetTransform
- AFXRENDERTARGET/CD2DBrush::IsValid
- AFXRENDERTARGET/CD2DBrush::SetOpacity
- AFXRENDERTARGET/CD2DBrush::SetTransform
- AFXRENDERTARGET/CD2DBrush::m_pBrush
- AFXRENDERTARGET/CD2DBrush::m_pBrushProperties
helpviewer_keywords:
- CD2DBrush [MFC], CD2DBrush
- CD2DBrush [MFC], Attach
- CD2DBrush [MFC], Destroy
- CD2DBrush [MFC], Detach
- CD2DBrush [MFC], Get
- CD2DBrush [MFC], GetOpacity
- CD2DBrush [MFC], GetTransform
- CD2DBrush [MFC], IsValid
- CD2DBrush [MFC], SetOpacity
- CD2DBrush [MFC], SetTransform
- CD2DBrush [MFC], m_pBrush
- CD2DBrush [MFC], m_pBrushProperties
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
ms.openlocfilehash: 6d19601258951a297a734aa304e2a22c98baf5c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227578"
---
# <a name="cd2dbrush-class"></a>CD2DBrush sınıfı

ID2D1Brush için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CD2DBrush : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBrush::CD2DBrush](#cd2dbrush)|Bir CD2DBrush nesnesi oluşturur.|
|[CD2DBrush:: ~ CD2DBrush](#_dtorcd2dbrush)|Yok edicisi. Bir D2D fırçası nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBrush:: Attach](#attach)|Varolan kaynak arabirimini nesneye iliştirir|
|[CD2DBrush::D estroy](#destroy)|Bir CD2DBrush nesnesini yok eder. (Geçersiz kılmalar [CD2DResource::D estroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DBrush::D etach](#detach)|Nesneden kaynak arabirimini ayırır|
|[CD2DBrush:: Get](#get)|ID2D1Brush arabirimini döndürür|
|[CD2DBrush:: GetOpacity](#getopacity)|Bu fırçanın opaklık derecesini alır|
|[CD2DBrush:: GetTransform](#gettransform)|İşleme hedefinin geçerli dönüşümünü alır|
|[CD2DBrush:: IsValid](#isvalid)|Kaynak geçerliliğini denetler (geçersiz kılmalar [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DBrush:: SetOpacity](#setopacity)|Bu fırçanın opaklık derecesini belirler|
|[CD2DBrush:: SetTransform](#settransform)|Varolan dönüşümü değiştirerek, belirtilen dönüşümü işleme hedefine uygular. Sonraki tüm çizim işlemleri dönüştürülmüş alanda gerçekleşir|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBrush:: operator ID2D1Brush *](#operator_id2d1brush_star)|ID2D1Brush arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBrush:: m_pBrush](#m_pbrush)|Bir ID2D1Brush nesnesine bir işaretçi depolar.|
|[CD2DBrush:: m_pBrushProperties](#m_pbrushproperties)|Fırça özellikleri.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DBrush`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dbrushcd2dbrush"></a><a name="_dtorcd2dbrush"></a> CD2DBrush:: ~ CD2DBrush

Yok edicisi. Bir D2D fırçası nesnesi yok edildiğinde çağırılır.

```
virtual ~CD2DBrush();
```

## <a name="cd2dbrushattach"></a><a name="attach"></a> CD2DBrush:: Attach

Varolan kaynak arabirimini nesneye ekler.

```cpp
void Attach(ID2D1Brush* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz.

## <a name="cd2dbrushcd2dbrush"></a><a name="cd2dbrush"></a> CD2DBrush::CD2DBrush

Bir CD2DBrush nesnesi oluşturur.

```
CD2DBrush(
    CRenderTarget* pParentTarget,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi işaretçisi.

*Pbrühproperties*<br/>
Fırçaya yönelik opaklık ve dönüştürme işaretçisi.

*bAutoDestroy*<br/>
Nesnenin sahip tarafından (pParentTarget) yok edileceği anlamına gelir.

## <a name="cd2dbrushdestroy"></a><a name="destroy"></a> CD2DBrush::D estroy

Bir CD2DBrush nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dbrushdetach"></a><a name="detach"></a> CD2DBrush::D etach

Nesneden kaynak arabirimini ayırır.

```
ID2D1Brush* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılan kaynak arabirimine yönelik işaretçi.

## <a name="cd2dbrushget"></a><a name="get"></a> CD2DBrush:: Get

ID2D1Brush arabirimini döndürür

```
ID2D1Brush* Get();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1Brush arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dbrushgetopacity"></a><a name="getopacity"></a> CD2DBrush:: GetOpacity

Bu fırçanın opaklık derecesini alır

```
FLOAT GetOpacity() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fırçanın opaklığını gösteren sıfır ile 1 arasında bir değer. Bu değer, fırçaya göre doldurulan tüm piksellerin Alfa değerini doğrusal bir şekilde ölçekleyen bir sabit çarpandır. Opaklık değerleri, birlikte çarpmadan önce 0 ile 1 aralığında çakışıyor.

## <a name="cd2dbrushgettransform"></a><a name="gettransform"></a> CD2DBrush:: GetTransform

İşleme hedefinin geçerli dönüşümünü alır

```cpp
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;
```

### <a name="parameters"></a>Parametreler

*Dönüşümler*<br/>
Bu döndüğünde, işleme hedefinin geçerli dönüşümünü içerir. Bu parametre, başlatmadan iletilir.

## <a name="cd2dbrushisvalid"></a><a name="isvalid"></a> CD2DBrush:: IsValid

Kaynak geçerliliğini denetler

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerliyse doğru; Aksi halde yanlış.

## <a name="cd2dbrushm_pbrush"></a><a name="m_pbrush"></a> CD2DBrush:: m_pBrush

Bir ID2D1Brush nesnesine bir işaretçi depolar.

```
ID2D1Brush* m_pBrush;
```

## <a name="cd2dbrushm_pbrushproperties"></a><a name="m_pbrushproperties"></a> CD2DBrush:: m_pBrushProperties

Fırça özellikleri.

```
CD2DBrushProperties* m_pBrushProperties;
```

## <a name="cd2dbrushoperator-id2d1brush"></a><a name="operator_id2d1brush_star"></a> CD2DBrush:: operator ID2D1Brush *

ID2D1Brush arabirimini döndürür

```
operator ID2D1Brush*();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1Brush arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dbrushsetopacity"></a><a name="setopacity"></a> CD2DBrush:: SetOpacity

Bu fırçanın opaklık derecesini belirler

```cpp
void SetOpacity(FLOAT opacity);
```

### <a name="parameters"></a>Parametreler

*Opaklık*<br/>
Fırçanın opaklığını gösteren sıfır ile 1 arasında bir değer. Bu değer, fırçaya göre doldurulan tüm piksellerin Alfa değerini doğrusal bir şekilde ölçekleyen bir sabit çarpandır. Opaklık değerleri, birlikte çarpmadan önce 0 ile 1 aralığında çakışıyor.

## <a name="cd2dbrushsettransform"></a><a name="settransform"></a> CD2DBrush:: SetTransform

Varolan dönüşümü değiştirerek, belirtilen dönüşümü işleme hedefine uygular. Sonraki tüm çizim işlemleri dönüştürülmüş alanda oluşur.

```cpp
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```

### <a name="parameters"></a>Parametreler

*Dönüşümler*<br/>
İşleme hedefine uygulanacak dönüştürme

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
