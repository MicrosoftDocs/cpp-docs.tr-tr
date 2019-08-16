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
ms.openlocfilehash: 079f1abe652d8c1610a084f5e1158cc5798d61c4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498289"
---
# <a name="srwlock-class"></a>SRWLock Sınıfı

İnce bir okuyucu/yazıcı kilidini temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class SRWLock;
```

## <a name="remarks"></a>Açıklamalar

Bir nesne veya kaynağa iş parçacıkları arasındaki erişimi eşleştirmek için ince bir okuyucu/yazıcı kilidi kullanılır. Daha fazla bilgi için bkz. [eşitleme işlevleri](/windows/win32/Sync/synchronization-functions).

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Ad                | Açıklama
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | Özel modda alınan `SRWLock` bir nesne için eş anlamlı.
`SyncLockShared`    | Paylaşılan modda alınan `SRWLock` bir nesne için eş anlamlı.

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                     | Açıklama
---------------------------------------- | --------------------------------------------------
[SRWLock:: SRWLock](#srwlock-constructor) | Yeni bir örneğini başlatır `SRWLock` sınıfı.
[SRWLock:: ~ SRWLock](#tilde-srwlock)      | `SRWLock` Sınıfının bir örneğini kaldırır.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                           | Açıklama
---------------------------------------------- | -------------------------------------------------------------------------------------------------------
[SRWLock:: LockExclusive](#lockexclusive)       | Özel modda `SRWLock` bir nesne elde edin.
[SRWLock:: LockShared](#lockshared)             | Paylaşılan modda `SRWLock` bir nesne alır.
[SRWLock:: TryLockExclusive](#trylockexclusive) | Geçerli veya belirtilen `SRWLock` nesne `SRWLock` için özel modda bir nesne edinmeye çalışır.
[SRWLock:: TryLockShared](#trylockshared)       | Geçerli veya belirtilen `SRWLock` nesne `SRWLock` için paylaşılan modda bir nesne edinmeye çalışır.

### <a name="protected-data-member"></a>Korumalı veri üyesi

Ad                                      | Açıklama
----------------------------------------- | -----------------------------------------------------------------------
[SRWLock:: SRWLock_](#srwlock-data-member) | Geçerli `SRWLock` nesne için temeldeki kilit değişkenini içerir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SRWLock`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Uzayına** Microsoft:: WRL:: sarmalayıcılar

## <a name="tilde-srwlock"></a>SRWLock:: ~ SRWLock

`SRWLock` Sınıfının bir örneğini kaldırır.

```cpp
~SRWLock();
```

## <a name="lockexclusive"></a>SRWLock:: LockExclusive

Özel modda `SRWLock` bir nesne elde edin.

```cpp
SyncLockExclusive LockExclusive();

static SyncLockExclusive LockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Bir `SRWLock` nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Özel `SRWLock` moddaki bir nesne.

## <a name="lockshared"></a>SRWLock:: LockShared

Paylaşılan modda `SRWLock` bir nesne alır.

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Bir `SRWLock` nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Paylaşılan `SRWLock` moddaki bir nesne.

## <a name="srwlock-constructor"></a>SRWLock:: SRWLock

Yeni bir örneğini başlatır `SRWLock` sınıfı.

```cpp
SRWLock();
```

## <a name="srwlock-data-member"></a>SRWLock:: SRWLock_

Geçerli `SRWLock` nesne için temeldeki kilit değişkenini içerir.

```cpp
SRWLOCK SRWLock_;
```

## <a name="trylockexclusive"></a>SRWLock:: TryLockExclusive

Geçerli veya belirtilen `SRWLock` nesne `SRWLock` için özel modda bir nesne edinmeye çalışır. Çağrı başarılı olursa, çağıran iş parçacığı kilidin sahipliğini alır.

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Bir `SRWLock` nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, özel `SRWLock` moddaki bir nesne ve çağıran iş parçacığı kilidin sahipliğini alır. Aksi takdirde, `SRWLock` durumu geçersiz olan bir nesne.

## <a name="trylockshared"></a>SRWLock:: TryLockShared

Geçerli veya belirtilen `SRWLock` nesne `SRWLock` için paylaşılan modda bir nesne edinmeye çalışır.

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Bir `SRWLock` nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, paylaşılan `SRWLock` moddaki bir nesne ve çağıran iş parçacığı kilidin sahipliğini alır. Aksi takdirde, `SRWLock` durumu geçersiz olan bir nesne.
