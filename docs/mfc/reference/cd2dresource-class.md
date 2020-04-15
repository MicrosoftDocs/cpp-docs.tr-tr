---
title: CD2DResource Sınıfı
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
ms.openlocfilehash: 5e747eda42e625d0f4cf65859e471933bbb043ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369089"
---
# <a name="cd2dresource-class"></a>CD2DResource Sınıfı

Fırçalar, katmanlar ve metinler gibi D2D kaynakları oluşturmak ve yönetmek için bir arabirim sağlayan soyut bir sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CD2DResource : public CObject;
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DResource::CD2DResource](#cd2dresource)|BIR CD2DResource nesnesi oluşturuyor.|
|[CD2DResource::~CD2DResource](#_dtorcd2dresource)|Yıkıcı. D2D kaynak nesnesi yok edilirken çağrılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DResource::Oluştur](#create)|BIR CD2DResource oluşturur.|
|[CD2DResource::Destroy](#destroy)|CD2DResource nesnesini yok eder.|
|[CD2DResource::Geçersiz](#isvalid)|Kaynak geçerliliğini denetler|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DResource::IsAutoDestroy](#isautodestroy)|Otomatik yok bayrağı kontrol edin.|
|[CD2DResource::Yeniden Oluşturma](#recreate)|CD2DResource'ı yeniden oluşturur.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CD2DResource::m_bIsAutoDestroy](#m_bisautodestroy)|Kaynak sahibi (CRenderTarget) tarafından yok edilecektir|
|[CD2DResource::m_pParentTarget](#m_pparenttarget)|Ana CRenderTarget için işaretçi)|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CD2DResource`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dresourcecd2dresource"></a><a name="_dtorcd2dresource"></a>CD2DResource::~CD2DResource

Yıkıcı. D2D kaynak nesnesi yok edilirken çağrılır.

```
virtual ~CD2DResource();
```

## <a name="cd2dresourcecd2dresource"></a><a name="cd2dresource"></a>CD2DResource::CD2DResource

BIR CD2DResource nesnesi oluşturuyor.

```
CD2DResource(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefine işaretçi.

*bAutoDestroy*<br/>
Nesnenin sahibi (pParentTarget) tarafından yok edileceğini gösterir.

## <a name="cd2dresourcecreate"></a><a name="create"></a>CD2DResource::Oluştur

BIR CD2DResource oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dresourcedestroy"></a><a name="destroy"></a>CD2DResource::Destroy

CD2DResource nesnesini yok eder.

```
virtual void Destroy() = 0;
```

## <a name="cd2dresourceisautodestroy"></a><a name="isautodestroy"></a>CD2DResource::IsAutoDestroy

Otomatik yok bayrağı kontrol edin.

```
BOOL IsAutoDestroy() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesne sahibi tarafından yok edilecekse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cd2dresourceisvalid"></a><a name="isvalid"></a>CD2DResource::Geçersiz

Kaynak geçerliliğini denetler

```
virtual BOOL IsValid() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerliyse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cd2dresourcem_bisautodestroy"></a><a name="m_bisautodestroy"></a>CD2DResource::m_bIsAutoDestroy

Kaynak sahibi (CRenderTarget) tarafından yok edilecektir

```
BOOL m_bIsAutoDestroy;
```

## <a name="cd2dresourcem_pparenttarget"></a><a name="m_pparenttarget"></a>CD2DResource::m_pParentTarget

Ana CRenderTarget için işaretçi)

```
CRenderTarget* m_pParentTarget;
```

## <a name="cd2dresourcerecreate"></a><a name="recreate"></a>CD2DResource::Yeniden Oluşturma

CD2DResource'ı yeniden oluşturur.

```
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
