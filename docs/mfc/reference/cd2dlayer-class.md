---
title: CD2DLayer sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DLayer
- AFXRENDERTARGET/CD2DLayer
- AFXRENDERTARGET/CD2DLayer::CD2DLayer
- AFXRENDERTARGET/CD2DLayer::Attach
- AFXRENDERTARGET/CD2DLayer::Create
- AFXRENDERTARGET/CD2DLayer::Destroy
- AFXRENDERTARGET/CD2DLayer::Detach
- AFXRENDERTARGET/CD2DLayer::Get
- AFXRENDERTARGET/CD2DLayer::GetSize
- AFXRENDERTARGET/CD2DLayer::IsValid
- AFXRENDERTARGET/CD2DLayer::m_pLayer
helpviewer_keywords:
- CD2DLayer [MFC], CD2DLayer
- CD2DLayer [MFC], Attach
- CD2DLayer [MFC], Create
- CD2DLayer [MFC], Destroy
- CD2DLayer [MFC], Detach
- CD2DLayer [MFC], Get
- CD2DLayer [MFC], GetSize
- CD2DLayer [MFC], IsValid
- CD2DLayer [MFC], m_pLayer
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
ms.openlocfilehash: 28ebe19b0f28692116a0b95721ff2e5490ad7e68
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391237"
---
# <a name="cd2dlayer-class"></a>CD2DLayer sınıfı

ID2D1Layer için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DLayer : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLayer::CD2DLayer](#cd2dlayer)|CD2DLayer bir nesne oluşturur.|
|[CD2DLayer:: ~ CD2DLayer](#_dtorcd2dlayer)|Yıkıcı. D2D katman nesnesi yok ediliyorken çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLayer::Attach](#attach)|Var olan kaynak arabirimi nesnesine ekler|
|[CD2DLayer::Create](#create)|Bir CD2DLayer oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DLayer::Destroy](#destroy)|CD2DLayer nesnesini yok eder. (Geçersiz kılmaları [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DLayer::detach](#detach)|Kaynak arabirimi nesnesinden ayırır|
|[CD2DLayer::get](#get)|Döndürür ID2D1Layer arabirimi|
|[CD2DLayer::GetSize](#getsize)|Boyut işleme hedefinin CİHAZDAN bağımsız piksel cinsinden döndürür|
|[CD2DLayer::IsValid](#isvalid)|Kaynak geçerlilik denetler (geçersiz kılmaları [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLayer::operator ID2D1Layer *](#operator_id2d1layer_star)|Döndürür ID2D1Layer arabirimi|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLayer::m_pLayer](#m_player)|ID2D1Layer nesneye bir işaretçi depolar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DLayer`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="_dtorcd2dlayer"></a>  CD2DLayer:: ~ CD2DLayer

Yıkıcı. D2D katman nesnesi yok ediliyorken çağırılır.

```
virtual ~CD2DLayer();
```

##  <a name="attach"></a>  CD2DLayer::Attach

Var olan kaynak arabirimi nesnesine ekler

```
void Attach(ID2D1Layer* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz

##  <a name="cd2dlayer"></a>  CD2DLayer::CD2DLayer

CD2DLayer bir nesne oluşturur.

```
CD2DLayer(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi için bir işaretçi.

*bAutoDestroy*<br/>
Nesne sahibi tarafından (pParentTarget) edileceği gösterir.

##  <a name="create"></a>  CD2DLayer::Create

Bir CD2DLayer oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="destroy"></a>  CD2DLayer::Destroy

CD2DLayer nesnesini yok eder.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DLayer::detach

Kaynak arabirimi nesnesinden ayırır

```
ID2D1Layer* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirim işaretçisi.

##  <a name="get"></a>  CD2DLayer::get

Döndürür ID2D1Layer arabirimi

```
ID2D1Layer* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1Layer arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="getsize"></a>  CD2DLayer::GetSize

Boyut işleme hedefinin CİHAZDAN bağımsız piksel cinsinden döndürür

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşleme hedefinin CİHAZDAN bağımsız piksel cinsinden geçerli boyutu

##  <a name="isvalid"></a>  CD2DLayer::IsValid

Kaynak geçerlilik denetimleri

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerli ise TRUE; Aksi durumda FALSE.

##  <a name="m_player"></a>  CD2DLayer::m_pLayer

ID2D1Layer nesneye bir işaretçi depolar.

```
ID2D1Layer* m_pLayer;
```

##  <a name="operator_id2d1layer_star"></a>  CD2DLayer::operator ID2D1Layer *

Döndürür ID2D1Layer arabirimi

```
operator ID2D1Layer* ();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1Layer arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
