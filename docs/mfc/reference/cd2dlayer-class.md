---
title: CD2DLayer Sınıfı
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
ms.openlocfilehash: aa6fb313bfcc2983f167936e5ad4f78be1e17a44
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369208"
---
# <a name="cd2dlayer-class"></a>CD2DLayer Sınıfı

ID2D1Layer için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DLayer : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DLayer::CD2DLayer](#cd2dlayer)|CD2DLayer nesnesi oluşturuyor.|
|[CD2DLayer::~CD2DLayer](#_dtorcd2dlayer)|Yıkıcı. D2D katman nesnesi yok edilirken çağrılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DLayer::Ekle](#attach)|Nesneye varolan kaynak arabirimi ataştırır|
|[CD2DLayer::Oluştur](#create)|BIR CD2DLayer oluşturur. [(CD2DResource geçersiz kılar::Oluştur](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DLayer::Destroy](#destroy)|CD2DLayer nesnesini yok eder. (GEÇERSIZ Kılar [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DLayer::Detach](#detach)|Kaynak arabirimini nesneden ayırıyor|
|[CD2DLayer::Get](#get)|ID2D1Layer arabirimini döndürür|
|[CD2DLayer::GetSize](#getsize)|Aygıttan bağımsız piksellerde render hedefinin boyutunu döndürür|
|[CD2DLayer::Geçersiz](#isvalid)|Kaynak geçerliliğini denetler [(CD2DResource geçersiz kılar::Geçerlidir](../../mfc/reference/cd2dresource-class.md#isvalid).)|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DLayer::operatör ID2D1Layer*](#operator_id2d1layer_star)|ID2D1Layer arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CD2DLayer::m_pLayer](#m_player)|Bir işaretçiyi ID2D1Layer nesnesine depolar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CD2DKaynak](../../mfc/reference/cd2dresource-class.md)

`CD2DLayer`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dlayercd2dlayer"></a><a name="_dtorcd2dlayer"></a>CD2DLayer::~CD2DLayer

Yıkıcı. D2D katman nesnesi yok edilirken çağrılır.

```
virtual ~CD2DLayer();
```

## <a name="cd2dlayerattach"></a><a name="attach"></a>CD2DLayer::Ekle

Nesneye varolan kaynak arabirimi ataştırır

```
void Attach(ID2D1Layer* pResource);
```

### <a name="parameters"></a>Parametreler

*pKaynak*<br/>
Varolan kaynak arabirimi. NULL olamaz

## <a name="cd2dlayercd2dlayer"></a><a name="cd2dlayer"></a>CD2DLayer::CD2DLayer

CD2DLayer nesnesi oluşturuyor.

```
CD2DLayer(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefine işaretçi.

*bAutoDestroy*<br/>
Nesnenin sahibi (pParentTarget) tarafından yok edileceğini gösterir.

## <a name="cd2dlayercreate"></a><a name="create"></a>CD2DLayer::Oluştur

BIR CD2DLayer oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dlayerdestroy"></a><a name="destroy"></a>CD2DLayer::Destroy

CD2DLayer nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dlayerdetach"></a><a name="detach"></a>CD2DLayer::Detach

Kaynak arabirimini nesneden ayırıyor

```
ID2D1Layer* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirimine işaretçi.

## <a name="cd2dlayerget"></a><a name="get"></a>CD2DLayer::Get

ID2D1Layer arabirimini döndürür

```
ID2D1Layer* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse, ID2D1Layer arabirimini işaretleyin veya NULL.

## <a name="cd2dlayergetsize"></a><a name="getsize"></a>CD2DLayer::GetSize

Aygıttan bağımsız piksellerde render hedefinin boyutunu döndürür

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aygıttan bağımsız piksellerde render hedefinin geçerli boyutu

## <a name="cd2dlayerisvalid"></a><a name="isvalid"></a>CD2DLayer::Geçersiz

Kaynak geçerliliğini denetler

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerliyse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cd2dlayerm_player"></a><a name="m_player"></a>CD2DLayer::m_pLayer

Bir işaretçiyi ID2D1Layer nesnesine depolar.

```
ID2D1Layer* m_pLayer;
```

## <a name="cd2dlayeroperator-id2d1layer"></a><a name="operator_id2d1layer_star"></a>CD2DLayer::operatör ID2D1Layer*

ID2D1Layer arabirimini döndürür

```
operator ID2D1Layer* ();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse, ID2D1Layer arabirimini işaretleyin veya NULL.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
