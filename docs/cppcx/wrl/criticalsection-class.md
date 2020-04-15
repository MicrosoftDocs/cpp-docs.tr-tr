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
ms.openlocfilehash: 5deb89e795d1886ca316886ae1ea260ce1f36fd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372594"
---
# <a name="criticalsection-class"></a>CriticalSection Sınıfı

Kritik bir bölüm nesnesi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class CriticalSection;
```

## <a name="members"></a>Üyeler

### <a name="constructor"></a>Oluşturucu

Adı                                                        | Açıklama
----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[Kritik Bölüm::KritikBölüm](#criticalsection)        | Mutex nesnesine benzeyen, ancak yalnızca tek bir işlemin iş parçacıkları tarafından kullanılabilen bir eşitleme nesnesini başolarak karşılar.
[Kritik Bölüm::~CriticalSection](#tilde-criticalsection) | Geçerli `CriticalSection` nesneyi deinitialize eder ve yok eder.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                 | Açıklama
------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------
[Kritik Bölüm::Geçersiz](#isvalid) | Geçerli kritik bölümün geçerli olup olmadığını gösterir.
[Kritik Bölüm::Kilitle](#lock)       | Belirtilen kritik bölüm nesnesinin sahipliğini bekler. Arama iş parçacığına sahiplik verildiğinde işlev geri döner.
[Kritik Bölüm::TryLock](#trylock) | Engellemeden kritik bir bölüme girmeye çalışır. Arama başarılı olursa, arama iş parçacığı kritik bölümün sahipliğini alır.

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

Adı                        | Açıklama
--------------------------- | ----------------------------------------
[Kritik Bölüm::cs_](#cs) | Kritik bir bölüm veri üyesi bildirir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CriticalSection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar

## <a name="criticalsectioncriticalsection"></a><a name="tilde-criticalsection"></a>Kritik Bölüm::~CriticalSection

Geçerli `CriticalSection` nesneyi deinitialize eder ve yok eder.

```cpp
WRL_NOTHROW ~CriticalSection();
```

## <a name="criticalsectioncriticalsection"></a><a name="criticalsection"></a>Kritik Bölüm::KritikBölüm

Mutex nesnesine benzeyen, ancak yalnızca tek bir işlemin iş parçacıkları tarafından kullanılabilen bir eşitleme nesnesini başolarak karşılar.

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>Parametreler

*spincount*<br/>
Kritik bölüm nesnesi için spin sayısı. Varsayılan değer 0’dır.

### <a name="remarks"></a>Açıklamalar

Kritik bölümler ve spincounts hakkında daha `InitializeCriticalSectionAndSpinCount` fazla `Synchronization` bilgi için, Windows API documenation bölümünde işlevi bakın.

## <a name="criticalsectioncs_"></a><a name="cs"></a>Kritik Bölüm::cs_

Kritik bir bölüm veri üyesi bildirir.

```cpp
CRITICAL_SECTION cs_;
```

### <a name="remarks"></a>Açıklamalar

Bu veri üyesi korunur.

## <a name="criticalsectionisvalid"></a><a name="isvalid"></a>Kritik Bölüm::Geçersiz

Geçerli kritik bölümün geçerli olup olmadığını gösterir.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan olarak, her zaman **doğru**döndürür.

## <a name="criticalsectionlock"></a><a name="lock"></a>Kritik Bölüm::Kilitle

Belirtilen kritik bölüm nesnesinin sahipliğini bekler. Arama iş parçacığına sahiplik verildiğinde işlev geri döner.

```cpp
SyncLock Lock();

   static SyncLock Lock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Parametreler

*Cs*<br/>
Kullanıcı tarafından belirtilen kritik bölüm nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Geçerli kritik bölümün kilidini açmak için kullanılabilecek bir kilit nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk `Lock` işlev geçerli kritik bölüm nesnesini etkiler. İkinci `Lock` işlev, kullanıcı tarafından belirtilen kritik bölümü etkiler.

## <a name="criticalsectiontrylock"></a><a name="trylock"></a>Kritik Bölüm::TryLock

Engellemeden kritik bir bölüme girmeye çalışır. Arama başarılı olursa, arama iş parçacığı kritik bölümün sahipliğini alır.

```cpp
SyncLock TryLock();

static SyncLock TryLock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Parametreler

*Cs*<br/>
Kullanıcı tarafından belirtilen kritik bölüm nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Kritik bölüm başarıyla girilirse veya geçerli iş parçacığı kritik bölümün sahibiyse sıfır olmayan bir değer. Başka bir iş parçacığı zaten kritik bölüme sahipse sıfır.

### <a name="remarks"></a>Açıklamalar

İlk `TryLock` işlev geçerli kritik bölüm nesnesini etkiler. İkinci `TryLock` işlev, kullanıcı tarafından belirtilen kritik bölümü etkiler.
