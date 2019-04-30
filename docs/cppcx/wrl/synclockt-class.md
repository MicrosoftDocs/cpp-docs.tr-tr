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
ms.openlocfilehash: d27e6ba8601d0e822113bf3a4a65269c89437271
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398166"
---
# <a name="synclockt-class"></a>SyncLockT Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename SyncTraits>
class SyncLockT;
```

### <a name="parameters"></a>Parametreler

*SyncTraits*<br/>
Bir kaynağın sahipliğini türü.

## <a name="remarks"></a>Açıklamalar

Özel alan türünü temsil eder ya da bir kaynak ilişkin paylaşılan sahipliğiniz.

`SyncLockT` Sınıfı kullanılır, örneğin, uygulamak için [SRWLock](srwlock-class.md) sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                      | Açıklama
----------------------------------------- | ----------------------------------------------------
[SyncLockT::SyncLockT](#synclockt)        | Yeni bir örneğini başlatır `SyncLockT` sınıfı.
[SyncLockT::~SyncLockT](#tilde-synclockt) | Örneği başlatılmasını geri alır `SyncLockT` sınıfı.

### <a name="protected-constructors"></a>Korumalı Oluşturucular

Ad                               | Açıklama
---------------------------------- | ----------------------------------------------------
[SyncLockT::SyncLockT](#synclockt) | Yeni bir örneğini başlatır `SyncLockT` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                             | Açıklama
-------------------------------- | --------------------------------------------------------------------------------------------------------------
[Synclockt::IsLocked](#islocked) | Belirtir olup olmadığını geçerli `SyncLockT` nesnesi bir kaynağa sahiptir; diğer bir deyişle, `SyncLockT` nesnedir *kilitli*.
[SyncLockT::Unlock](#unlock)     | Serbest geçerli tarafından tutulan kaynak denetimi `SyncLockT` varsa, nesne.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                      | Açıklama
------------------------- | -------------------------------------------------------------------
[SyncLockT::sync_](#sync) | Temel alınan kaynak tarafından temsil edilen tutar `SyncLockT` sınıfı.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SyncLockT`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::details

## <a name="tilde-synclockt"></a>SyncLockT::~SyncLockT

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
~SyncLockT();
```

### <a name="remarks"></a>Açıklamalar

Örneği başlatılmasını geri alır `SyncLockT` sınıfı.

Bu yok Edicisi de geçerli kilidini açarak `SyncLockT` örneği.

## <a name="islocked"></a>Synclockt::IsLocked

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
bool IsLocked() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `SyncLockT` nesnedir kilitli; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Belirtir olup olmadığını geçerli `SyncLockT` nesnesi bir kaynağa sahiptir; diğer bir deyişle, `SyncLockT` nesnedir *kilitli*.

## <a name="sync"></a>SyncLockT::sync_

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
typename SyncTraits::Type sync_;
```

### <a name="remarks"></a>Açıklamalar

Temel alınan kaynak tarafından temsil edilen tutar `SyncLockT` sınıfı.

## <a name="synclockt"></a>SyncLockT::SyncLockT

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

*Diğer*<br/>
Diğer bir rvalue başvurusuna `SyncLockT` nesne.

*Eşitleme*<br/>
Başka bir başvuru `SyncLockWithStatusT` nesne.

### <a name="remarks"></a>Açıklamalar

Yeni bir örneğini başlatır `SyncLockT` sınıfı.

İlk Oluşturucu geçerli başlatır `SyncLockT` başka bir nesne `SyncLockT` parametresi tarafından belirtilen nesne *diğer*ve diğeri geçersiz kılar `SyncLockT` nesne. İkinci oluşturucu `protected`ve geçerli başlatır `SyncLockT` nesnesi için geçersiz bir durumda.

## <a name="unlock"></a>SyncLockT::Unlock

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
void Unlock();
```

### <a name="remarks"></a>Açıklamalar

Serbest geçerli tarafından tutulan kaynak denetimi `SyncLockT` varsa, nesne.
