---
title: ComPtrRefBase Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
- client/Microsoft::WRL::Details::ComPtrRefBase::ptr_
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRefBase class
- Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable** operator
- Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown** operator
- Microsoft::WRL::Details::ComPtrRefBase::ptr_ data member
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
ms.openlocfilehash: df4e2aa1ce650fd5b1f04baf2f7c4cd2fb4cff93
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79418316"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
class ComPtrRefBase;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Bir [ComPtr\<t >](comptr-class.md) türü veya bundan türetilmiş bir tür veya yalnızca `ComPtr`tarafından temsil edilen arabirim değil.

## <a name="remarks"></a>Açıklamalar

[ComPtrRef](comptrref-class.md) sınıfının temel sınıfını temsil eder.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Adı            | Açıklama
--------------- | -------------------------------------------------
`InterfaceType` | *T*şablon parametresinin türü için bir eş anlamlı.

### <a name="public-operators"></a>Genel İşleçler

Adı                                                                       | Açıklama
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[ComPtrRefBase:: operator IInspectable * *](#operator-iinspectable-star-star) | Geçerli [ptr_](#ptr) veri üyesini, `IInspectable` arabirimine işaretçiden bir işaretçisine çevirir.
[ComPtrRefBase:: operator IUnknown * *](#operator-iunknown-star-star)         | Geçerli [ptr_](#ptr) veri üyesini, `IUnknown` arabirimine işaretçiden bir işaretçisine çevirir.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Adı                        | Açıklama
--------------------------- | ----------------------------------------------------------------
[ComPtrRefBase::p tr_](#ptr) | Geçerli şablon parametresi tarafından belirtilen türe yönelik işaretçi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtrRefBase`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="operator-iinspectable-star-star"></a>ComPtrRefBase:: operator IInspectable\*\* Işleci

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>Açıklamalar

Geçerli [ptr_](#ptr) veri üyesini, `IInspectable` arabirimine işaretçiden bir işaretçisine çevirir.

Geçerli `ComPtrRefBase` `IInspectable`devralmamazsa bir hata yayınlanır.

Bu dönüştürme yalnızca `__WRL_CLASSIC_COM__` tanımlanmışsa kullanılabilir.

## <a name="operator-iunknown-star-star"></a>ComPtrRefBase:: operator IUnknown * * Işleci

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>Açıklamalar

Geçerli [ptr_](#ptr) veri üyesini, `IUnknown` arabirimine işaretçiden bir işaretçisine çevirir.

Geçerli `ComPtrRefBase` `IUnknown`devralmamazsa bir hata yayınlanır.

## <a name="ptr"></a>ComPtrRefBase::p tr_

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
T* ptr_;
```

### <a name="remarks"></a>Açıklamalar

Geçerli şablon parametresi tarafından belirtilen türe yönelik işaretçi. `ptr_` korunan veri üyesidir.
