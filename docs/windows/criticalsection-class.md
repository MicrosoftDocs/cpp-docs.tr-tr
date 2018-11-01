---
title: CriticalSection Sınıfı
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::cs_
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::IsValid
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::CriticalSection class
- Microsoft::WRL::Wrappers::CriticalSection::cs_ data member
- Microsoft::WRL::Wrappers::CriticalSection::IsValid method
- Microsoft::WRL::Wrappers::CriticalSection::Lock method
- Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection, destructor
- Microsoft::WRL::Wrappers::CriticalSection::CriticalSection, constructor
- Microsoft::WRL::Wrappers::CriticalSection::TryLock method
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
ms.openlocfilehash: dd34206741ba8fee8b283e22b6e8eefb3b3efb0e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651158"
---
# <a name="criticalsection-class"></a>CriticalSection Sınıfı

Kritik bölüm nesneyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class CriticalSection;
```

## <a name="members"></a>Üyeler

### <a name="constructor"></a>Oluşturucu

Ad                                                        | Açıklama
----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[CriticalSection::CriticalSection](#criticalsection)        | Mutex nesnesine benzer, ancak yalnızca tek bir işlem iş parçacığı tarafından kullanılan bir eşitleme nesnesi başlatır.
[CriticalSection:: ~ CriticalSection](#tilde-criticalsection) | Başlatılmasını geri alır ve geçerli yok eder `CriticalSection` nesne.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                 | Açıklama
------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------
[Criticalsection::IsValid](#isvalid) | Geçerli kritik bölüm geçerli olup olmadığını belirtir.
[CriticalSection::Lock](#lock)       | Belirtilen kritik bölüm Nesne sahipliği için bekler. Çağıran iş parçacığını sahipliği verildiğinde işlevi döndürür.
[CriticalSection::TryLock](#trylock) | Engelleme olmadan kritik bir bölüm girin dener. Çağrı başarılı olursa, çağıran iş parçacığı, kritik bölüm sahipliğini alır.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                        | Açıklama
--------------------------- | ----------------------------------------
[CriticalSection::cs_](#cs) | Kritik bölüm veri üyesi bildirir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CriticalSection`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="tilde-criticalsection"></a>CriticalSection:: ~ CriticalSection

Başlatılmasını geri alır ve geçerli yok eder `CriticalSection` nesne.

```cpp
WRL_NOTHROW ~CriticalSection();
```

## <a name="criticalsection"></a>CriticalSection::CriticalSection

Mutex nesnesine benzer, ancak yalnızca tek bir işlem iş parçacığı tarafından kullanılan bir eşitleme nesnesi başlatır.

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>Parametreler

*spincount*<br/>
Kritik bölüm nesnenin dönüş sayısı. Varsayılan değer 0’dır.

### <a name="remarks"></a>Açıklamalar

Kritik bölümler ve spincounts hakkında daha fazla bilgi için bkz: `InitializeCriticalSectionAndSpinCount` işlevi `Synchronization` Windows API platformlarının bölümü.

## <a name="cs"></a>CriticalSection::cs_

Kritik bölüm veri üyesi bildirir.

```cpp
CRITICAL_SECTION cs_;
```

### <a name="remarks"></a>Açıklamalar

Bu veri üyesi korunur.

## <a name="isvalid"></a>Criticalsection::IsValid

Geçerli kritik bölüm geçerli olup olmadığını belirtir.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan olarak, her zaman döndürür **true**.

## <a name="lock"></a>CriticalSection::Lock

Belirtilen kritik bölüm Nesne sahipliği için bekler. Çağıran iş parçacığını sahipliği verildiğinde işlevi döndürür.

```cpp
SyncLock Lock();

   static SyncLock Lock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Parametreler

*cs*<br/>
Bir kullanıcı tarafından belirtilen kritik bölüm nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Geçerli kritik bölümün kilidini açmak için kullanılan nesnesi kilitlenemedi.

### <a name="remarks"></a>Açıklamalar

İlk `Lock` işlevi, geçerli kritik bölüm nesnesini etkiler. İkinci `Lock` işlevi kullanıcı tanımlı bir kritik bölüm etkiler.

## <a name="trylock"></a>CriticalSection::TryLock

Engelleme olmadan kritik bir bölüm girin dener. Çağrı başarılı olursa, çağıran iş parçacığı, kritik bölüm sahipliğini alır.

```cpp
SyncLock TryLock();

static SyncLock TryLock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Parametreler

*cs*<br/>
Bir kullanıcı tarafından belirtilen kritik bölüm nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Kritik bölüm başarıyla girdiyseniz sıfır olmayan bir değer veya geçerli iş parçacığı, kritik bölüm zaten sahip. Başka bir iş parçacığı kritik bölüm sahipse sıfır.

### <a name="remarks"></a>Açıklamalar

İlk `TryLock` işlevi, geçerli kritik bölüm nesnesini etkiler. İkinci `TryLock` işlevi kullanıcı tanımlı bir kritik bölüm etkiler.
