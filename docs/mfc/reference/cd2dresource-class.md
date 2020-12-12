---
description: 'Daha fazla bilgi edinin: CD2DResource Class'
title: CD2DResource sınıfı
ms.date: 03/27/2019
f1_keywords:
- CD2DResource
- AFXRENDERTARGET/CD2DResource
- AFXRENDERTARGET/CD2DResource::CD2DResource
- AFXRENDERTARGET/CD2DResource::Create
- AFXRENDERTARGET/CD2DResource::Destroy
- AFXRENDERTARGET/CD2DResource::IsValid
- AFXRENDERTARGET/CD2DResource::IsAutoDestroy
- AFXRENDERTARGET/CD2DResource::ReCreate
- AFXRENDERTARGET/CD2DResource::m_bIsAutoDestroy
- AFXRENDERTARGET/CD2DResource::m_pParentTarget
helpviewer_keywords:
- CD2DResource [MFC], CD2DResource
- CD2DResource [MFC], Create
- CD2DResource [MFC], Destroy
- CD2DResource [MFC], IsValid
- CD2DResource [MFC], IsAutoDestroy
- CD2DResource [MFC], ReCreate
- CD2DResource [MFC], m_bIsAutoDestroy
- CD2DResource [MFC], m_pParentTarget
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
ms.openlocfilehash: a110732a7e2bde5ab2fb3b6025acf98d6a3278c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118738"
---
# <a name="cd2dresource-class"></a>CD2DResource sınıfı

Fırçalar, Katmanlar ve metinler gibi D2D kaynaklarını oluşturmak ve yönetmek için bir arabirim sağlayan soyut bir sınıf.

## <a name="syntax"></a>Syntax

```
class CD2DResource : public CObject;
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DResource::CD2DResource](#cd2dresource)|Bir CD2DResource nesnesi oluşturur.|
|[CD2DResource:: ~ CD2DResource](#_dtorcd2dresource)|Yok edicisi. D2D kaynak nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DResource:: Create](#create)|Bir CD2DResource oluşturur.|
|[CD2DResource::D estroy](#destroy)|Bir CD2DResource nesnesini yok eder.|
|[CD2DResource:: IsValid](#isvalid)|Kaynak geçerliliğini denetler|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DResource:: Isoto yok etme](#isautodestroy)|Otomatik yok etme bayrağını işaretleyin.|
|[CD2DResource:: yeniden oluştur](#recreate)|Bir CD2DResource yeniden oluşturur.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DResource:: m_bIsAutoDestroy](#m_bisautodestroy)|Kaynak, sahip tarafından yok edilir (CRenderTarget)|
|[CD2DResource:: m_pParentTarget](#m_pparenttarget)|Üst CRenderTarget işaretçisi)|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CD2DResource`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dresourcecd2dresource"></a><a name="_dtorcd2dresource"></a> CD2DResource:: ~ CD2DResource

Yok edicisi. D2D kaynak nesnesi yok edildiğinde çağırılır.

```
virtual ~CD2DResource();
```

## <a name="cd2dresourcecd2dresource"></a><a name="cd2dresource"></a> CD2DResource::CD2DResource

Bir CD2DResource nesnesi oluşturur.

```
CD2DResource(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi işaretçisi.

*bAutoDestroy*<br/>
Nesnenin sahip tarafından (pParentTarget) yok edileceği anlamına gelir.

## <a name="cd2dresourcecreate"></a><a name="create"></a> CD2DResource:: Create

Bir CD2DResource oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dresourcedestroy"></a><a name="destroy"></a> CD2DResource::D estroy

Bir CD2DResource nesnesini yok eder.

```
virtual void Destroy() = 0;
```

## <a name="cd2dresourceisautodestroy"></a><a name="isautodestroy"></a> CD2DResource:: Isoto yok etme

Otomatik yok etme bayrağını işaretleyin.

```
BOOL IsAutoDestroy() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesne sahibi tarafından yok edilecekse doğru; Aksi halde yanlış.

## <a name="cd2dresourceisvalid"></a><a name="isvalid"></a> CD2DResource:: IsValid

Kaynak geçerliliğini denetler

```
virtual BOOL IsValid() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerliyse doğru; Aksi halde yanlış.

## <a name="cd2dresourcem_bisautodestroy"></a><a name="m_bisautodestroy"></a> CD2DResource:: m_bIsAutoDestroy

Kaynak, sahip tarafından yok edilir (CRenderTarget)

```
BOOL m_bIsAutoDestroy;
```

## <a name="cd2dresourcem_pparenttarget"></a><a name="m_pparenttarget"></a> CD2DResource:: m_pParentTarget

Üst CRenderTarget işaretçisi)

```
CRenderTarget* m_pParentTarget;
```

## <a name="cd2dresourcerecreate"></a><a name="recreate"></a> CD2DResource:: yeniden oluştur

Bir CD2DResource yeniden oluşturur.

```
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
