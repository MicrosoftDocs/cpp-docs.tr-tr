---
description: 'Daha fazla bilgi edinin: CD2DLayer Class'
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
ms.openlocfilehash: bd41cd591e6422c9434cd84d20cb6e5d778410bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306956"
---
# <a name="cd2dlayer-class"></a>CD2DLayer sınıfı

ID2D1Layer için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CD2DLayer : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLayer::CD2DLayer](#cd2dlayer)|Bir CD2DLayer nesnesi oluşturur.|
|[CD2DLayer:: ~ CD2DLayer](#_dtorcd2dlayer)|Yok edicisi. Bir D2D katman nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLayer:: Attach](#attach)|Varolan kaynak arabirimini nesneye iliştirir|
|[CD2DLayer:: Create](#create)|Bir CD2DLayer oluşturur. (Geçersiz kılmalar [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DLayer::D estroy](#destroy)|Bir CD2DLayer nesnesini yok eder. (Geçersiz kılmalar [CD2DResource::D estroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DLayer::D etach](#detach)|Nesneden kaynak arabirimini ayırır|
|[CD2DLayer:: Get](#get)|ID2D1Layer arabirimini döndürür|
|[CD2DLayer:: GetSize](#getsize)|Cihazdan bağımsız piksellerde işleme hedefinin boyutunu döndürür|
|[CD2DLayer:: IsValid](#isvalid)|Kaynak geçerliliğini denetler (geçersiz kılmalar [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLayer:: operator ID2D1Layer *](#operator_id2d1layer_star)|ID2D1Layer arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DLayer:: m_pLayer](#m_player)|Bir ID2D1Layer nesnesine bir işaretçi depolar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DLayer`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dlayercd2dlayer"></a><a name="_dtorcd2dlayer"></a> CD2DLayer:: ~ CD2DLayer

Yok edicisi. Bir D2D katman nesnesi yok edildiğinde çağırılır.

```
virtual ~CD2DLayer();
```

## <a name="cd2dlayerattach"></a><a name="attach"></a> CD2DLayer:: Attach

Varolan kaynak arabirimini nesneye iliştirir

```cpp
void Attach(ID2D1Layer* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz

## <a name="cd2dlayercd2dlayer"></a><a name="cd2dlayer"></a> CD2DLayer::CD2DLayer

Bir CD2DLayer nesnesi oluşturur.

```
CD2DLayer(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi işaretçisi.

*bAutoDestroy*<br/>
Nesnenin sahip tarafından (pParentTarget) yok edileceği anlamına gelir.

## <a name="cd2dlayercreate"></a><a name="create"></a> CD2DLayer:: Create

Bir CD2DLayer oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dlayerdestroy"></a><a name="destroy"></a> CD2DLayer::D estroy

Bir CD2DLayer nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dlayerdetach"></a><a name="detach"></a> CD2DLayer::D etach

Nesneden kaynak arabirimini ayırır

```
ID2D1Layer* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılan kaynak arabirimine yönelik işaretçi.

## <a name="cd2dlayerget"></a><a name="get"></a> CD2DLayer:: Get

ID2D1Layer arabirimini döndürür

```
ID2D1Layer* Get();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1Layer arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dlayergetsize"></a><a name="getsize"></a> CD2DLayer:: GetSize

Cihazdan bağımsız piksellerde işleme hedefinin boyutunu döndürür

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Cihazdan bağımsız piksellerde işleme hedefinin geçerli boyutu

## <a name="cd2dlayerisvalid"></a><a name="isvalid"></a> CD2DLayer:: IsValid

Kaynak geçerliliğini denetler

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerliyse doğru; Aksi halde yanlış.

## <a name="cd2dlayerm_player"></a><a name="m_player"></a> CD2DLayer:: m_pLayer

Bir ID2D1Layer nesnesine bir işaretçi depolar.

```
ID2D1Layer* m_pLayer;
```

## <a name="cd2dlayeroperator-id2d1layer"></a><a name="operator_id2d1layer_star"></a> CD2DLayer:: operator ID2D1Layer *

ID2D1Layer arabirimini döndürür

```
operator ID2D1Layer* ();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1Layer arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
