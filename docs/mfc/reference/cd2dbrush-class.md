---
title: CD2DBrush sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f7141350d318673b5458cd760f7ad9d48a466bda
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409791"
---
# <a name="cd2dbrush-class"></a>CD2DBrush sınıfı

ID2D1Brush için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DBrush : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBrush::CD2DBrush](#cd2dbrush)|CD2DBrush bir nesne oluşturur.|
|[CD2DBrush:: ~ CD2DBrush](#_dtorcd2dbrush)|Yıkıcı. D2D fırça nesnesi yok ediliyorken çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBrush::Attach](#attach)|Var olan kaynak arabirimi nesnesine ekler|
|[CD2DBrush::Destroy](#destroy)|CD2DBrush nesnesini yok eder. (Geçersiz kılmaları [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DBrush::detach](#detach)|Kaynak arabirimi nesnesinden ayırır|
|[CD2DBrush::get](#get)|Döndürür ID2D1Brush arabirimi|
|[CD2DBrush::GetOpacity](#getopacity)|Bu fırça opaklığını derecesini alır|
|[CD2DBrush::GetTransform](#gettransform)|İşleme hedefinin geçerli dönüşümü alır|
|[CD2DBrush::IsValid](#isvalid)|Kaynak geçerlilik denetler (geçersiz kılmaları [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DBrush::SetOpacity](#setopacity)|Bu fırça opaklığını derecesini ayarlar|
|[CD2DBrush::SetTransform](#settransform)|İşleme hedefi mevcut dönüştürmeyi değiştirmek için belirtilen dönüşüm uygular. Tüm sonraki çizim işlemlerini dönüştürülmüş alanı oluşur.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBrush::operator ID2D1Brush *](#operator_id2d1brush_star)|Döndürür ID2D1Brush arabirimi|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBrush::m_pBrush](#m_pbrush)|ID2D1Brush nesneye bir işaretçi depolar.|
|[CD2DBrush::m_pBrushProperties](#m_pbrushproperties)|Fırça özellikleri.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DBrush`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="_dtorcd2dbrush"></a>  CD2DBrush:: ~ CD2DBrush

Yıkıcı. D2D fırça nesnesi yok ediliyorken çağırılır.

```
virtual ~CD2DBrush();
```

##  <a name="attach"></a>  CD2DBrush::Attach

Var olan kaynak arabirimi nesnesine ekler.

```
void Attach(ID2D1Brush* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz.

##  <a name="cd2dbrush"></a>  CD2DBrush::CD2DBrush

CD2DBrush bir nesne oluşturur.

```
CD2DBrush(
    CRenderTarget* pParentTarget,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi için bir işaretçi.

*pBrushProperties*<br/>
Fırça dönüşümü ve opaklık yönelik işaretçi.

*bAutoDestroy*<br/>
Nesne sahibi tarafından (pParentTarget) edileceği gösterir.

##  <a name="destroy"></a>  CD2DBrush::Destroy

CD2DBrush nesnesini yok eder.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DBrush::detach

Kaynak arabirimi nesneden çıkarır.

```
ID2D1Brush* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirim işaretçisi.

##  <a name="get"></a>  CD2DBrush::get

Döndürür ID2D1Brush arabirimi

```
ID2D1Brush* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1Brush arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="getopacity"></a>  CD2DBrush::GetOpacity

Bu fırça opaklığını derecesini alır

```
FLOAT GetOpacity() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır ile fırça opaklığını gösteren 1 arasında bir değer. Fırça tarafından doldurulmuş olan tüm pikselleri alfa değeri doğrusal olarak ölçeklenen bir sabit çarpan değerdir. Birlikte çarpılır önce opaklık değerleri 0 ile 1 aralığında kenetlenen.

##  <a name="gettransform"></a>  CD2DBrush::GetTransform

İşleme hedefinin geçerli dönüşümü alır

```
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;
```

### <a name="parameters"></a>Parametreler

*transform*<br/>
Bu geri döndüğünde, işleme hedefinin geçerli dönüştürmeyi içerir. Bu parametre, başlatılmamış olarak geçirilir.

##  <a name="isvalid"></a>  CD2DBrush::IsValid

Kaynak geçerlilik denetimleri

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerli ise TRUE; Aksi durumda FALSE.

##  <a name="m_pbrush"></a>  CD2DBrush::m_pBrush

ID2D1Brush nesneye bir işaretçi depolar.

```
ID2D1Brush* m_pBrush;
```

##  <a name="m_pbrushproperties"></a>  CD2DBrush::m_pBrushProperties

Fırça özellikleri.

```
CD2DBrushProperties* m_pBrushProperties;
```

##  <a name="operator_id2d1brush_star"></a>  CD2DBrush::operator ID2D1Brush *

Döndürür ID2D1Brush arabirimi

```
operator ID2D1Brush*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1Brush arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="setopacity"></a>  CD2DBrush::SetOpacity

Bu fırça opaklığını derecesini ayarlar

```
void SetOpacity(FLOAT opacity);
```

### <a name="parameters"></a>Parametreler

*Opaklık*<br/>
Sıfır ile fırça opaklığını gösteren 1 arasında bir değer. Fırça tarafından doldurulmuş olan tüm pikselleri alfa değeri doğrusal olarak ölçeklenen bir sabit çarpan değerdir. Birlikte çarpılır önce opaklık değerleri 0 ile 1 aralığında kenetlenen.

##  <a name="settransform"></a>  CD2DBrush::SetTransform

İşleme hedefi mevcut dönüştürmeyi değiştirmek için belirtilen dönüşüm uygular. Tüm sonraki çizim işlemleri, dönüştürülen uzayında oluşur.

```
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```

### <a name="parameters"></a>Parametreler

*transform*<br/>
İşleme hedefi için uygulanacak Dönüşüm

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
