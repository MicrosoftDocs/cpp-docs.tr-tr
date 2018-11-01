---
title: CD2DResource sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: a4846fb8ea34a3d6a83ae892eabee74f4a48cd6a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586387"
---
# <a name="cd2dresource-class"></a>CD2DResource sınıfı

Oluşturma ve Fırçalar, Katmanlar ve metinler gibi D2D kaynakları yönetmek için bir arabirim sunan bir soyut sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CD2DResource : public CObject;
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DResource::CD2DResource](#cd2dresource)|CD2DResource bir nesne oluşturur.|
|[CD2DResource:: ~ CD2DResource](#cd2dresource__~cd2dresource)|Yıkıcı. D2D kaynak nesnesi yok ediliyorken çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DResource::Create](#create)|Bir CD2DResource oluşturur.|
|[CD2DResource::Destroy](#destroy)|CD2DResource nesnesini yok eder.|
|[CD2DResource::IsValid](#isvalid)|Kaynak geçerlilik denetimleri|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DResource::IsAutoDestroy](#isautodestroy)|Onay otomatik bayrağı yok.|
|[CD2DResource::ReCreate](#recreate)|Bir CD2DResource yeniden oluşturur.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DResource::m_bIsAutoDestroy](#m_bisautodestroy)|Kaynak sahibi (CRenderTarget) tarafından destoyed olacaktır|
|[CD2DResource::m_pParentTarget](#m_pparenttarget)|CRenderTarget üst işaretçisi)|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CD2DResource`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="_dtorcd2dresource"></a>  CD2DResource:: ~ CD2DResource

Yıkıcı. D2D kaynak nesnesi yok ediliyorken çağırılır.

```
virtual ~CD2DResource();
```

##  <a name="cd2dresource"></a>  CD2DResource::CD2DResource

CD2DResource bir nesne oluşturur.

```
CD2DResource(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi için bir işaretçi.

*bAutoDestroy*<br/>
Nesne sahibi tarafından (pParentTarget) edileceği gösterir.

##  <a name="create"></a>  CD2DResource::Create

Bir CD2DResource oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="destroy"></a>  CD2DResource::Destroy

CD2DResource nesnesini yok eder.

```
virtual void Destroy() = 0;
```

##  <a name="isautodestroy"></a>  CD2DResource::IsAutoDestroy

Onay otomatik bayrağı yok.

```
BOOL IsAutoDestroy() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesne sahibi tarafından edileceği TRUE; Aksi durumda FALSE.

##  <a name="isvalid"></a>  CD2DResource::IsValid

Kaynak geçerlilik denetimleri

```
virtual BOOL IsValid() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerli ise TRUE; Aksi durumda FALSE.

##  <a name="m_bisautodestroy"></a>  CD2DResource::m_bIsAutoDestroy

Kaynak sahibi (CRenderTarget) tarafından destoyed olacaktır

```
BOOL m_bIsAutoDestroy;
```

##  <a name="m_pparenttarget"></a>  CD2DResource::m_pParentTarget

CRenderTarget üst işaretçisi)

```
CRenderTarget* m_pParentTarget;
```

##  <a name="recreate"></a>  CD2DResource::ReCreate

Bir CD2DResource yeniden oluşturur.

```
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
