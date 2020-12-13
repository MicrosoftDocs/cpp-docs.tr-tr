---
description: 'Daha fazla bilgi edinin: SRWLock sınıfı'
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
ms.openlocfilehash: 10bc3dc700f90d5154ece1546cdf3ec464ea6e56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135193"
---
# <a name="srwlock-class"></a>SRWLock Sınıfı

İnce bir okuyucu/yazıcı kilidini temsil eder.

## <a name="syntax"></a>Syntax

```cpp
class SRWLock;
```

## <a name="remarks"></a>Açıklamalar

Bir nesne veya kaynağa iş parçacıkları arasındaki erişimi eşleştirmek için ince bir okuyucu/yazıcı kilidi kullanılır. Daha fazla bilgi için bkz. [eşitleme işlevleri](/windows/win32/Sync/synchronization-functions).

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Ad                | Açıklama
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | `SRWLock`Özel modda alınan bir nesne için eş anlamlı.
`SyncLockShared`    | `SRWLock`Paylaşılan modda alınan bir nesne için eş anlamlı.

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                     | Açıklama
---------------------------------------- | --------------------------------------------------
[SRWLock:: SRWLock](#srwlock-constructor) | `SRWLock` sınıfının yeni bir örneğini başlatır.
[SRWLock:: ~ SRWLock](#tilde-srwlock)      | Sınıfının bir örneğini kaldırır `SRWLock` .

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                           | Açıklama
---------------------------------------------- | -------------------------------------------------------------------------------------------------------
[SRWLock:: LockExclusive](#lockexclusive)       | `SRWLock`Özel modda bir nesne elde edin.
[SRWLock:: LockShared](#lockshared)             | `SRWLock`Paylaşılan modda bir nesne alır.
[SRWLock:: TryLockExclusive](#trylockexclusive) | `SRWLock`Geçerli veya belirtilen nesne için özel modda bir nesne edinmeye çalışır `SRWLock` .
[SRWLock:: TryLockShared](#trylockshared)       | `SRWLock`Geçerli veya belirtilen nesne için paylaşılan modda bir nesne edinmeye çalışır `SRWLock` .

### <a name="protected-data-member"></a>Korumalı veri üyesi

Ad                                      | Açıklama
----------------------------------------- | -----------------------------------------------------------------------
[SRWLock:: SRWLock_](#srwlock-data-member) | Geçerli nesne için temeldeki kilit değişkenini içerir `SRWLock` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SRWLock`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar

## <a name="srwlocksrwlock"></a><a name="tilde-srwlock"></a> SRWLock:: ~ SRWLock

Sınıfının bir örneğini kaldırır `SRWLock` .

```cpp
~SRWLock();
```

## <a name="srwlocklockexclusive"></a><a name="lockexclusive"></a> SRWLock:: LockExclusive

`SRWLock`Özel modda bir nesne elde edin.

```cpp
SyncLockExclusive LockExclusive();

static SyncLockExclusive LockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*ine*<br/>
Bir nesne işaretçisi `SRWLock` .

### <a name="return-value"></a>Dönüş Değeri

`SRWLock`Özel moddaki bir nesne.

## <a name="srwlocklockshared"></a><a name="lockshared"></a> SRWLock:: LockShared

`SRWLock`Paylaşılan modda bir nesne alır.

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*ine*<br/>
Bir nesne işaretçisi `SRWLock` .

### <a name="return-value"></a>Dönüş Değeri

`SRWLock`Paylaşılan moddaki bir nesne.

## <a name="srwlocksrwlock"></a><a name="srwlock-constructor"></a> SRWLock:: SRWLock

`SRWLock` sınıfının yeni bir örneğini başlatır.

```cpp
SRWLock();
```

## <a name="srwlocksrwlock_"></a><a name="srwlock-data-member"></a> SRWLock:: SRWLock_

Geçerli nesne için temeldeki kilit değişkenini içerir `SRWLock` .

```cpp
SRWLOCK SRWLock_;
```

## <a name="srwlocktrylockexclusive"></a><a name="trylockexclusive"></a> SRWLock:: TryLockExclusive

`SRWLock`Geçerli veya belirtilen nesne için özel modda bir nesne edinmeye çalışır `SRWLock` . Çağrı başarılı olursa, çağıran iş parçacığı kilidin sahipliğini alır.

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*ine*<br/>
Bir nesne işaretçisi `SRWLock` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, `SRWLock` özel moddaki bir nesne ve çağıran iş parçacığı kilidin sahipliğini alır. Aksi takdirde, `SRWLock` durumu geçersiz olan bir nesne.

## <a name="srwlocktrylockshared"></a><a name="trylockshared"></a> SRWLock:: TryLockShared

`SRWLock`Geçerli veya belirtilen nesne için paylaşılan modda bir nesne edinmeye çalışır `SRWLock` .

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*ine*<br/>
Bir nesne işaretçisi `SRWLock` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, `SRWLock` paylaşılan moddaki bir nesne ve çağıran iş parçacığı kilidin sahipliğini alır. Aksi takdirde, `SRWLock` durumu geçersiz olan bir nesne.
