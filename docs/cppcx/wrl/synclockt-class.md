---
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
ms.openlocfilehash: 52c4404fa28f680a9a7a4592d03f535e8406d1a4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374276"
---
# <a name="synclockt-class"></a>SyncLockT Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename SyncTraits>
class SyncLockT;
```

### <a name="parameters"></a>Parametreler

*Eşitleme Özellikleri*<br/>
Kaynağın sahipliğini alabilecek tür.

## <a name="remarks"></a>Açıklamalar

Kaynağın münhasır veya ortak sahipliğini alabilecek bir türü temsil eder.

Sınıf, `SyncLockT` örneğin, [SRWLock](srwlock-class.md) sınıfının uygulanmasına yardımcı olmak için kullanılır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                      | Açıklama
----------------------------------------- | ----------------------------------------------------
[Synclockt::synclockt](#synclockt)        | `SyncLockT` sınıfının yeni bir örneğini başlatır.
[Synclockt::~synclockt](#tilde-synclockt) | Sınıfın bir örneğini `SyncLockT` deinitialize eder.

### <a name="protected-constructors"></a>Korumalı Oluşturucular

Adı                               | Açıklama
---------------------------------- | ----------------------------------------------------
[Synclockt::synclockt](#synclockt) | `SyncLockT` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                             | Açıklama
-------------------------------- | --------------------------------------------------------------------------------------------------------------
[SyncLockT::Kilitli](#islocked) | Geçerli `SyncLockT` nesnenin bir kaynağa sahip olup olmadığını gösterir; diğer bir `SyncLockT` şey, nesne *kilitlenir.*
[SyncLockT::Kilidini Aç](#unlock)     | Varsa, geçerli `SyncLockT` nesne tarafından tutulan kaynağın denetimini serbest bırakır.

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

Adı                      | Açıklama
------------------------- | -------------------------------------------------------------------
[SyncLockT::sync_](#sync) | `SyncLockT` Sınıfın temsil ettiği temel kaynağı tutar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SyncLockT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar::D kuyrukları

## <a name="synclocktsynclockt"></a><a name="tilde-synclockt"></a>Synclockt::~synclockt

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
~SyncLockT();
```

### <a name="remarks"></a>Açıklamalar

Sınıfın bir örneğini `SyncLockT` deinitialize eder.

Bu yıkıcı aynı zamanda geçerli `SyncLockT` örneğin kilidini açar.

## <a name="synclocktislocked"></a><a name="islocked"></a>SyncLockT::Kilitli

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
bool IsLocked() const;
```

### <a name="return-value"></a>Dönüş Değeri

`SyncLockT` nesne kilitliyse **doğru;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Geçerli `SyncLockT` nesnenin bir kaynağa sahip olup olmadığını gösterir; diğer bir `SyncLockT` şey, nesne *kilitlenir.*

## <a name="synclocktsync_"></a><a name="sync"></a>SyncLockT::sync_

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
typename SyncTraits::Type sync_;
```

### <a name="remarks"></a>Açıklamalar

`SyncLockT` Sınıfın temsil ettiği temel kaynağı tutar.

## <a name="synclocktsynclockt"></a><a name="synclockt"></a>Synclockt::synclockt

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
SyncLockT(
   _Inout_ SyncLockT&& other
);

explicit SyncLockT(
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()
);
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir `SyncLockT` nesneye rvalue-reference.

*Eşitleme*<br/>
Başka bir `SyncLockWithStatusT` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

`SyncLockT` sınıfının yeni bir örneğini başlatır.

İlk oluşturucu, *diğer*parametre ile `SyncLockT` belirtilen başka bir nesneden geçerli `SyncLockT` nesneyi `SyncLockT` başharfe ait hale gelirse ve diğer nesneyi geçersiz kılarak geçersiz kılınır. İkinci oluşturucu `protected`ve geçersiz bir duruma `SyncLockT` geçerli nesneyi başharf.

## <a name="synclocktunlock"></a><a name="unlock"></a>SyncLockT::Kilidini Aç

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
void Unlock();
```

### <a name="remarks"></a>Açıklamalar

Varsa, geçerli `SyncLockT` nesne tarafından tutulan kaynağın denetimini serbest bırakır.
