---
title: SRWLock Sınıfı
ms.date: 09/25/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock_
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::~SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
helpviewer_keywords:
- Microsoft::WRL::Wrappers::SRWLock class
- Microsoft::WRL::Wrappers::SRWLock::LockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::LockShared method
- Microsoft::WRL::Wrappers::SRWLock::SRWLock, constructor
- Microsoft::WRL::Wrappers::SRWLock::SRWLock_ data member
- Microsoft::WRL::Wrappers::SRWLock::~SRWLock, destructor
- Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::TryLockShared method
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
ms.openlocfilehash: e305ad54e30455ce7c25f356c454791da0783591
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377271"
---
# <a name="srwlock-class"></a>SRWLock Sınıfı

İnce bir okuyucu/yazar kilidini temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class SRWLock;
```

## <a name="remarks"></a>Açıklamalar

İnce bir okuyucu/yazar kilidi, bir nesneye veya kaynağa iş parçacıkları arasında erişimi eşitlemek için kullanılır. Daha fazla bilgi için [senkronizasyon işlevlerine](/windows/win32/Sync/synchronization-functions)bakın.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

Adı                | Açıklama
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | Özel modda edinilen `SRWLock` bir nesnenin eşanlamlısı.
`SyncLockShared`    | Paylaşılan modda edinilen `SRWLock` bir nesnenin eş anlamlısı.

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                     | Açıklama
---------------------------------------- | --------------------------------------------------
[SRWLock::SRWLock](#srwlock-constructor) | `SRWLock` sınıfının yeni bir örneğini başlatır.
[SRWLock::~SRWLock](#tilde-srwlock)      | Sınıfın bir örneğini `SRWLock` deinitialize eder.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                           | Açıklama
---------------------------------------------- | -------------------------------------------------------------------------------------------------------
[SRWLock::LockExclusive](#lockexclusive)       | Özel modda bir `SRWLock` nesne edinir.
[SRWLock::LockShared](#lockshared)             | Paylaşılan modda bir `SRWLock` nesne kazanır.
[SRWLock::TryLockExclusive](#trylockexclusive) | Geçerli veya `SRWLock` belirtilen `SRWLock` nesne için özel modda bir nesne elde etmeye çalışır.
[SRWLock::trylockpaylaşılan](#trylockshared)       | Geçerli veya `SRWLock` belirtilen `SRWLock` nesne için paylaşılan modda bir nesne elde etmeye çalışır.

### <a name="protected-data-member"></a>Korumalı Veri Üyesi

Adı                                      | Açıklama
----------------------------------------- | -----------------------------------------------------------------------
[SRWLock::SRWLock_](#srwlock-data-member) | Geçerli `SRWLock` nesne için temel kilit değişkenini içerir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SRWLock`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar

## <a name="srwlocksrwlock"></a><a name="tilde-srwlock"></a>SRWLock::~SRWLock

Sınıfın bir örneğini `SRWLock` deinitialize eder.

```cpp
~SRWLock();
```

## <a name="srwlocklockexclusive"></a><a name="lockexclusive"></a>SRWLock::LockExclusive

Özel modda bir `SRWLock` nesne edinir.

```cpp
SyncLockExclusive LockExclusive();

static SyncLockExclusive LockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*Kilit*<br/>
Bir `SRWLock` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Özel `SRWLock` modda bir nesne.

## <a name="srwlocklockshared"></a><a name="lockshared"></a>SRWLock::LockShared

Paylaşılan modda bir `SRWLock` nesne kazanır.

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*Kilit*<br/>
Bir `SRWLock` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Paylaşılan `SRWLock` modda bir nesne.

## <a name="srwlocksrwlock"></a><a name="srwlock-constructor"></a>SRWLock::SRWLock

`SRWLock` sınıfının yeni bir örneğini başlatır.

```cpp
SRWLock();
```

## <a name="srwlocksrwlock_"></a><a name="srwlock-data-member"></a>SRWLock::SRWLock_

Geçerli `SRWLock` nesne için temel kilit değişkenini içerir.

```cpp
SRWLOCK SRWLock_;
```

## <a name="srwlocktrylockexclusive"></a><a name="trylockexclusive"></a>SRWLock::TryLockExclusive

Geçerli veya `SRWLock` belirtilen `SRWLock` nesne için özel modda bir nesne elde etmeye çalışır. Arama başarılı olursa, arama iş parçacığı kilidin sahipliğini alır.

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*Kilit*<br/>
Bir `SRWLock` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, `SRWLock` özel modda bir nesne ve arama iş parçacığı kilidin sahipliğini alır. Aksi takdirde, durumu geçersiz olan bir `SRWLock` nesne.

## <a name="srwlocktrylockshared"></a><a name="trylockshared"></a>SRWLock::trylockpaylaşılan

Geçerli veya `SRWLock` belirtilen `SRWLock` nesne için paylaşılan modda bir nesne elde etmeye çalışır.

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*Kilit*<br/>
Bir `SRWLock` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, `SRWLock` paylaşılan moddaki bir nesne ve arama iş parçacığı kilidin sahipliğini alır. Aksi takdirde, durumu geçersiz olan bir `SRWLock` nesne.
