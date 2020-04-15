---
title: CD2DBrush Sınıfı
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
ms.openlocfilehash: d03fb6f398e18957f68fc18c78d8a397efc67506
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369276"
---
# <a name="cd2dbrush-class"></a>CD2DBrush Sınıfı

ID2D1Brush için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DBrush : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBrush::CD2DBrush](#cd2dbrush)|BIR CD2DBrush nesnesi oluşturuyor.|
|[CD2DBrush::~CD2DFırça](#_dtorcd2dbrush)|Yıkıcı. Bir D2D fırça nesnesi yok edilirken çağrılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBrush::Ekle](#attach)|Nesneye varolan kaynak arabirimi ataştırır|
|[CD2DFırça::Destroy](#destroy)|BIR CD2DBrush nesnesini yok eder. (GEÇERSIZ Kılar [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DFırça::Detach](#detach)|Kaynak arabirimini nesneden ayırıyor|
|[CD2DBrush::Get](#get)|ID2D1Fırça arabirimi döndürür|
|[CD2DFırça::GetOpacity](#getopacity)|Bu fırçanın donukluk derecesini alır|
|[CD2DBrush::GetTransform](#gettransform)|Render hedefinin geçerli dönüşümünün alır|
|[CD2DBrush::Geçersiz](#isvalid)|Kaynak geçerliliğini denetler [(CD2DResource geçersiz kılar::Geçerlidir](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DFırça::SetOpacity](#setopacity)|Bu fırçanın donukluk derecesini ayarlar|
|[CD2DBrush::SetTransform](#settransform)|Belirtilen dönüşümü, varolan dönüşümün yerine, render hedefine uygular. Sonraki tüm çizim işlemleri dönüştürülmüş alanda gerçekleşir|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBrush::operatör ID2D1Fırça*](#operator_id2d1brush_star)|ID2D1Fırça arabirimi döndürür|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CD2DFırça::m_pBrush](#m_pbrush)|Bir işaretçiyi ID2D1Brush nesnesine depolar.|
|[CD2DFırça::m_pBrushProperties](#m_pbrushproperties)|Fırça özellikleri.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CD2DKaynak](../../mfc/reference/cd2dresource-class.md)

`CD2DBrush`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dbrushcd2dbrush"></a><a name="_dtorcd2dbrush"></a>CD2DBrush::~CD2DFırça

Yıkıcı. Bir D2D fırça nesnesi yok edilirken çağrılır.

```
virtual ~CD2DBrush();
```

## <a name="cd2dbrushattach"></a><a name="attach"></a>CD2DBrush::Ekle

Nesneye varolan kaynak arabirimi ataştırır.

```
void Attach(ID2D1Brush* pResource);
```

### <a name="parameters"></a>Parametreler

*pKaynak*<br/>
Varolan kaynak arabirimi. NULL olamaz.

## <a name="cd2dbrushcd2dbrush"></a><a name="cd2dbrush"></a>CD2DBrush::CD2DBrush

BIR CD2DBrush nesnesi oluşturuyor.

```
CD2DBrush(
    CRenderTarget* pParentTarget,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefine işaretçi.

*pBrushProperties*<br/>
Bir fırçanın opaklığına ve dönüşümüne işaret eden bir işaretçi.

*bAutoDestroy*<br/>
Nesnenin sahibi (pParentTarget) tarafından yok edileceğini gösterir.

## <a name="cd2dbrushdestroy"></a><a name="destroy"></a>CD2DFırça::Destroy

BIR CD2DBrush nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dbrushdetach"></a><a name="detach"></a>CD2DFırça::Detach

Kaynak arabirimini nesneden ayırır.

```
ID2D1Brush* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirimine işaretçi.

## <a name="cd2dbrushget"></a><a name="get"></a>CD2DBrush::Get

ID2D1Fırça arabirimi döndürür

```
ID2D1Brush* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse, ID2D1Brush arabirimini işaretleyin veya NULL.

## <a name="cd2dbrushgetopacity"></a><a name="getopacity"></a>CD2DFırça::GetOpacity

Bu fırçanın donukluk derecesini alır

```
FLOAT GetOpacity() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fırçanın opaklığını gösteren sıfır ile 1 arasındaki değer. Bu değer, fırça tarafından doldurulan tüm piksellerin alfa değerini doğrusal olarak ölçeklendiren sabit bir çarpandır. Opaklık değerleri, birlikte çarpmadan önce 0 ile 1 aralığında kenetlenir.

## <a name="cd2dbrushgettransform"></a><a name="gettransform"></a>CD2DBrush::GetTransform

Render hedefinin geçerli dönüşümünün alır

```
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;
```

### <a name="parameters"></a>Parametreler

*Dönüştürmek*<br/>
Bu döndürdüğünde, render hedefinin geçerli dönüşümiçerir. Bu parametre, başlatmadan iletilir.

## <a name="cd2dbrushisvalid"></a><a name="isvalid"></a>CD2DBrush::Geçersiz

Kaynak geçerliliğini denetler

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerliyse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cd2dbrushm_pbrush"></a><a name="m_pbrush"></a>CD2DFırça::m_pBrush

Bir işaretçiyi ID2D1Brush nesnesine depolar.

```
ID2D1Brush* m_pBrush;
```

## <a name="cd2dbrushm_pbrushproperties"></a><a name="m_pbrushproperties"></a>CD2DFırça::m_pBrushProperties

Fırça özellikleri.

```
CD2DBrushProperties* m_pBrushProperties;
```

## <a name="cd2dbrushoperator-id2d1brush"></a><a name="operator_id2d1brush_star"></a>CD2DBrush::operatör ID2D1Fırça*

ID2D1Fırça arabirimi döndürür

```
operator ID2D1Brush*();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse, ID2D1Brush arabirimini işaretleyin veya NULL.

## <a name="cd2dbrushsetopacity"></a><a name="setopacity"></a>CD2DFırça::SetOpacity

Bu fırçanın donukluk derecesini ayarlar

```
void SetOpacity(FLOAT opacity);
```

### <a name="parameters"></a>Parametreler

*Opak -lık*<br/>
Fırçanın opaklığını gösteren sıfır ile 1 arasındaki değer. Bu değer, fırça tarafından doldurulan tüm piksellerin alfa değerini doğrusal olarak ölçeklendiren sabit bir çarpandır. Opaklık değerleri, birlikte çarpmadan önce 0 ile 1 aralığında kenetlenir.

## <a name="cd2dbrushsettransform"></a><a name="settransform"></a>CD2DBrush::SetTransform

Belirtilen dönüşümü, varolan dönüşümün yerine, render hedefine uygular. Sonraki tüm çizim işlemleri dönüştürülmüş alanda gerçekleşir.

```
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```

### <a name="parameters"></a>Parametreler

*Dönüştürmek*<br/>
Render hedefine uygulanacak dönüştürme

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
