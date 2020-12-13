---
description: 'Daha fazla bilgi edinin: SyncLockT Sınıfı'
title: SyncLockT Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::sync_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockT class
- Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockT::sync_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT, constructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT, destructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock method
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
ms.openlocfilehash: 289a31d87ce395be2d2a72a8fe062c9c0bfa8f56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135115"
---
# <a name="synclockt-class"></a>SyncLockT Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename SyncTraits>
class SyncLockT;
```

### <a name="parameters"></a>Parametreler

*Syncnitelikler*<br/>
Bir kaynağın sahipliğini alabileceği tür.

## <a name="remarks"></a>Açıklamalar

Bir kaynağın özel veya paylaşılan sahipliğini alabileceği bir türü temsil eder.

`SyncLockT`Sınıfı, örneğin, [SRWLock](srwlock-class.md) sınıfının uygulanması için kullanılır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                      | Açıklama
----------------------------------------- | ----------------------------------------------------
[SyncLockT:: SyncLockT](#synclockt)        | `SyncLockT` sınıfının yeni bir örneğini başlatır.
[SyncLockT:: ~ SyncLockT](#tilde-synclockt) | Sınıfının bir örneğini kaldırır `SyncLockT` .

### <a name="protected-constructors"></a>Korumalı Oluşturucular

Ad                               | Açıklama
---------------------------------- | ----------------------------------------------------
[SyncLockT:: SyncLockT](#synclockt) | `SyncLockT` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                             | Açıklama
-------------------------------- | --------------------------------------------------------------------------------------------------------------
[SyncLockT:: ıskilitlendi](#islocked) | Geçerli `SyncLockT` nesnenin bir kaynağa sahip olup olmadığını gösterir; diğer bir deyişle, `SyncLockT` nesne *kilitlenir*.
[SyncLockT:: unlock](#unlock)     | Varsa, geçerli nesne tarafından tutulan kaynağın denetimini yayınlar `SyncLockT` .

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                      | Açıklama
------------------------- | -------------------------------------------------------------------
[SyncLockT:: sync_](#sync) | Sınıfı tarafından temsil edilen temel kaynağı barındırır `SyncLockT` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SyncLockT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar::D euçlar

## <a name="synclocktsynclockt"></a><a name="tilde-synclockt"></a> SyncLockT:: ~ SyncLockT

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
~SyncLockT();
```

### <a name="remarks"></a>Açıklamalar

Sınıfının bir örneğini kaldırır `SyncLockT` .

Bu yıkıcı ayrıca geçerli örneğin kilidini açar `SyncLockT` .

## <a name="synclocktislocked"></a><a name="islocked"></a> SyncLockT:: ıskilitlendi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
bool IsLocked() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`**`SyncLockT`nesne kilitliyse, tersi durumda **`false`** .

### <a name="remarks"></a>Açıklamalar

Geçerli `SyncLockT` nesnenin bir kaynağa sahip olup olmadığını gösterir; diğer bir deyişle, `SyncLockT` nesne *kilitlenir*.

## <a name="synclocktsync_"></a><a name="sync"></a> SyncLockT:: sync_

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
typename SyncTraits::Type sync_;
```

### <a name="remarks"></a>Açıklamalar

Sınıfı tarafından temsil edilen temel kaynağı barındırır `SyncLockT` .

## <a name="synclocktsynclockt"></a><a name="synclockt"></a> SyncLockT:: SyncLockT

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
SyncLockT(
   _Inout_ SyncLockT&& other
);

explicit SyncLockT(
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()
);
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Bir rvalue başvurusu, başka bir `SyncLockT` nesneye başvuru.

*Eşitleme*<br/>
Başka bir nesneye başvuru `SyncLockWithStatusT` .

### <a name="remarks"></a>Açıklamalar

`SyncLockT` sınıfının yeni bir örneğini başlatır.

İlk Oluşturucu, geçerli `SyncLockT` nesneyi `SyncLockT` *diğer* parametre tarafından belirtilen başka bir nesneden başlatır ve ardından diğer nesneyi geçersiz kılar `SyncLockT` . İkinci Oluşturucu olur **`protected`** ve geçerli `SyncLockT` nesneyi geçersiz bir duruma başlatır.

## <a name="synclocktunlock"></a><a name="unlock"></a> SyncLockT:: unlock

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
void Unlock();
```

### <a name="remarks"></a>Açıklamalar

Varsa, geçerli nesne tarafından tutulan kaynağın denetimini yayınlar `SyncLockT` .
