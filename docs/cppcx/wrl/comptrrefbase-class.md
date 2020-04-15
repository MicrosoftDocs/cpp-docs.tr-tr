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
ms.openlocfilehash: 4f6dd6449cf8135ad14486d64cea95d8329e0014
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372613"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
class ComPtrRefBase;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[ComPtr\<T>](comptr-class.md) türü veya ondan türetilen bir tür, sadece arayüz tarafından temsil edilen . `ComPtr`

## <a name="remarks"></a>Açıklamalar

[ComPtrRef](comptrref-class.md) sınıfının taban sınıfını temsil eder.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

Adı            | Açıklama
--------------- | -------------------------------------------------
`InterfaceType` | Şablon parametresi *T*türü için eşanlamlı.

### <a name="public-operators"></a>Ortak İşleçler

Adı                                                                       | Açıklama
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[ComPtrRefBase::operatör IInspectable**](#operator-iinspectable-star-star) | Geçerli [ptr_](#ptr) veri üyesini `IInspectable` arabirime işaretçiye işaretçiye atar.
[ComPtrRefBase::operatör IUnknown**](#operator-iunknown-star-star)         | Geçerli [ptr_](#ptr) veri üyesini `IUnknown` arabirime işaretçiye işaretçiye atar.

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

Adı                        | Açıklama
--------------------------- | ----------------------------------------------------------------
[ComPtrRefBase::ptr_](#ptr) | Geçerli şablon parametresi tarafından belirtilen türü işaretçi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtrRefBase`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** client.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="comptrrefbaseoperator-iinspectable-operator"></a><a name="operator-iinspectable-star-star"></a>ComPtrRefBase::operatör IInspectable\* \* Operatörü

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>Açıklamalar

Geçerli [ptr_](#ptr) veri üyesini `IInspectable` arabirime işaretçiye işaretçiye atar.

Akım' `ComPtrRefBase` dan kaynaklanmıyorsa bir hata `IInspectable`yayılır.

Bu döküm yalnızca `__WRL_CLASSIC_COM__` tanımlanmışsa kullanılabilir.

## <a name="comptrrefbaseoperator-iunknown-operator"></a><a name="operator-iunknown-star-star"></a>ComPtrRefBase::operatör IUnknown** Operatör

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>Açıklamalar

Geçerli [ptr_](#ptr) veri üyesini `IUnknown` arabirime işaretçiye işaretçiye atar.

Akım' `ComPtrRefBase` dan kaynaklanmıyorsa bir hata `IUnknown`yayılır.

## <a name="comptrrefbaseptr_"></a><a name="ptr"></a>ComPtrRefBase::ptr_

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
T* ptr_;
```

### <a name="remarks"></a>Açıklamalar

Geçerli şablon parametresi tarafından belirtilen türü işaretçi. `ptr_`korunan veri üyesidir.
