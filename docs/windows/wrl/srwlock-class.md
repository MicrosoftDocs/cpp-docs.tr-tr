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
ms.openlocfilehash: 6d4a504d9465c858af59a88cf0ef611bf88c3fde
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54334958"
---
# <a name="srwlock-class"></a>SRWLock Sınıfı

Bir ince Okuyucu/Yazıcı kilidi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class SRWLock;
```

## <a name="remarks"></a>Açıklamalar

Bir ince Okuyucu/Yazıcı kilidi, bir nesneye veya kaynak iş parçacıkları arasında erişimi eşitlemek için kullanılır. Daha fazla bilgi için [eşitleme işlevleri](/windows/desktop/Sync/synchronization-functions).

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

Ad                | Açıklama
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | İçin eş anlamlı bir `SRWLock` özel modda alınan nesne.
`SyncLockShared`    | İçin eş anlamlı bir `SRWLock` paylaşılan modda alınan nesne.

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                     | Açıklama
---------------------------------------- | --------------------------------------------------
[SRWLock::SRWLock](#srwlock-constructor) | Yeni bir örneğini başlatır `SRWLock` sınıfı.
[SRWLock:: ~ SRWLock](#tilde-srwlock)      | Örneği başlatılmasını geri alır `SRWLock` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                           | Açıklama
---------------------------------------------- | -------------------------------------------------------------------------------------------------------
[SRWLock::LockExclusive](#lockexclusive)       | Alması bir `SRWLock` özel modda nesne.
[SRWLock::LockShared](#lockshared)             | Alması bir `SRWLock` paylaşılan modda nesne.
[SRWLock::TryLockExclusive](#trylockexclusive) | Almaya çalışır bir `SRWLock` nesne için geçerli veya belirtilen özel modda `SRWLock` nesne.
[SRWLock::TryLockShared](#trylockshared)       | Almaya çalışır bir `SRWLock` nesne için geçerli veya belirtilen paylaşılan modda `SRWLock` nesne.

### <a name="protected-data-member"></a>Korumalı veri üyesi

Ad                                      | Açıklama
----------------------------------------- | -----------------------------------------------------------------------
[SRWLock::SRWLock_](#srwlock-data-member) | Temel alınan kilidi değişken için geçerli içeren `SRWLock` nesne.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SRWLock`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="tilde-srwlock"></a>SRWLock:: ~ SRWLock

Örneği başlatılmasını geri alır `SRWLock` sınıfı.

```cpp
~SRWLock();
```

## <a name="lockexclusive"></a>SRWLock::LockExclusive

Alması bir `SRWLock` özel modda nesne.

```cpp
SyncLockExclusive LockExclusive();

static SyncLockExclusive LockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
İşaretçi bir `SRWLock` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bir `SRWLock` özel modda nesne.

## <a name="lockshared"></a>SRWLock::LockShared

Alması bir `SRWLock` paylaşılan modda nesne.

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
İşaretçi bir `SRWLock` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bir `SRWLock` paylaşılan modda nesne.

## <a name="srwlock-constructor"></a>SRWLock::SRWLock

Yeni bir örneğini başlatır `SRWLock` sınıfı.

```cpp
SRWLock();
```

## <a name="srwlock-data-member"></a>SRWLock::SRWLock_

Temel alınan kilidi değişken için geçerli içeren `SRWLock` nesne.

```cpp
SRWLOCK SRWLock_;
```

## <a name="trylockexclusive"></a>SRWLock::TryLockExclusive

Almaya çalışır bir `SRWLock` nesne için geçerli veya belirtilen özel modda `SRWLock` nesne. Çağrı başarılı olursa, çağıran iş parçacığını kilidi sahipliğini alır.

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
İşaretçi bir `SRWLock` nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bir `SRWLock` Dışlayıcı ve çağıran iş parçacığını nesne kilidi sahipliğini alır. Aksi takdirde, bir `SRWLock` nesne durumu geçersiz.

## <a name="trylockshared"></a>SRWLock::TryLockShared

Almaya çalışır bir `SRWLock` nesne için geçerli veya belirtilen paylaşılan modda `SRWLock` nesne.

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
İşaretçi bir `SRWLock` nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bir `SRWLock` paylaşılan modda ve çağıran iş parçacığını nesne kilidi sahipliğini alır. Aksi takdirde, bir `SRWLock` nesne durumu geçersiz.
