---
description: 'Daha fazla bilgi edinin: ComPtrRefBase sınıfı'
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
ms.openlocfilehash: 4dce58e8292092084916c24153d543f2a45856fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273143"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
class ComPtrRefBase;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Bir [ComPtr \<T> ](comptr-class.md) türü veya ondan türetilmiş bir tür veya yalnızca tarafından temsil edilen arabirim değil `ComPtr` .

## <a name="remarks"></a>Açıklamalar

[ComPtrRef](comptrref-class.md) sınıfının temel sınıfını temsil eder.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Ad            | Açıklama
--------------- | -------------------------------------------------
`InterfaceType` | *T* şablon parametresinin türü için bir eş anlamlı.

### <a name="public-operators"></a>Ortak İşleçler

Ad                                                                       | Açıklama
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[ComPtrRefBase:: operator IInspectable * *](#operator-iinspectable-star-star) | Geçerli [ptr_](#ptr) veri üyesini arabirime işaretçiden uca işaretçisine yayınlar `IInspectable` .
[ComPtrRefBase:: operator IUnknown * *](#operator-iunknown-star-star)         | Geçerli [ptr_](#ptr) veri üyesini arabirime işaretçiden uca işaretçisine yayınlar `IUnknown` .

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                        | Açıklama
--------------------------- | ----------------------------------------------------------------
[ComPtrRefBase::p tr_](#ptr) | Geçerli şablon parametresi tarafından belirtilen türe yönelik işaretçi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtrRefBase`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="comptrrefbaseoperator-iinspectable-operator"></a><a name="operator-iinspectable-star-star"></a>ComPtrRefBase:: operator IInspectable \* \* işleci

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>Açıklamalar

Geçerli [ptr_](#ptr) veri üyesini arabirime işaretçiden uca işaretçisine yayınlar `IInspectable` .

Geçerli, `ComPtrRefBase` öğesinden türetilmezse bir hata yayınlanır `IInspectable` .

Bu cast yalnızca `__WRL_CLASSIC_COM__` tanımlanmışsa kullanılabilir.

## <a name="comptrrefbaseoperator-iunknown-operator"></a><a name="operator-iunknown-star-star"></a> ComPtrRefBase:: operator IUnknown * * Işleci

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>Açıklamalar

Geçerli [ptr_](#ptr) veri üyesini arabirime işaretçiden uca işaretçisine yayınlar `IUnknown` .

Geçerli, `ComPtrRefBase` öğesinden türetilmezse bir hata yayınlanır `IUnknown` .

## <a name="comptrrefbaseptr_"></a><a name="ptr"></a> ComPtrRefBase::p tr_

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
T* ptr_;
```

### <a name="remarks"></a>Açıklamalar

Geçerli şablon parametresi tarafından belirtilen türe yönelik işaretçi. `ptr_` korunan veri üyesidir.
