---
description: 'Daha fazla bilgi edinin: Kritiksection sınıfı'
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
ms.openlocfilehash: e570dfaef8fcf16084792d205fc3e322cf8be908
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273039"
---
# <a name="criticalsection-class"></a>CriticalSection Sınıfı

Kritik bir bölüm nesnesini temsil eder.

## <a name="syntax"></a>Syntax

```cpp
class CriticalSection;
```

## <a name="members"></a>Üyeler

### <a name="constructor"></a>Oluşturucu

Ad                                                        | Açıklama
----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[Kritiksection:: Kritiksection](#criticalsection)        | Bir mutex nesnesine benzer ancak yalnızca tek bir işlemin iş parçacıkları tarafından kullanılabilen bir eşitleme nesnesi başlatır.
[Kritiksection:: ~ CriticalHandle bölümü](#tilde-criticalsection) | Geçerli nesneyi kaldırır ve yok eder `CriticalSection` .

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                 | Açıklama
------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------
[Kritiksection:: IsValid](#isvalid) | Geçerli kritik bölümün geçerli olup olmadığını gösterir.
[Kritiksection:: Lock](#lock)       | Belirtilen kritik bölüm nesnesinin sahipliğini bekler. İşlev, çağıran iş parçacığına sahiplik verildiğinde döndürür.
[Kritiksection:: TryLock](#trylock) | Engellenmeden kritik bir bölüm girmeye çalışır. Çağrı başarılı olursa, çağıran iş parçacığı kritik bölümün sahipliğini alır.

### <a name="protected-data-members"></a>Korumalı veri üyeleri

Ad                        | Açıklama
--------------------------- | ----------------------------------------
[Kritiksection:: cs_](#cs) | Kritik bir bölüm veri üyesi bildirir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CriticalSection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar

## <a name="criticalsectioncriticalsection"></a><a name="tilde-criticalsection"></a> Kritiksection:: ~ CriticalHandle bölümü

Geçerli nesneyi kaldırır ve yok eder `CriticalSection` .

```cpp
WRL_NOTHROW ~CriticalSection();
```

## <a name="criticalsectioncriticalsection"></a><a name="criticalsection"></a> Kritiksection:: Kritiksection

Bir mutex nesnesine benzer ancak yalnızca tek bir işlemin iş parçacıkları tarafından kullanılabilen bir eşitleme nesnesi başlatır.

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>Parametreler

*SpinCount*<br/>
Kritik bölüm nesnesi için döngü sayısı. Varsayılan değer 0’dır.

### <a name="remarks"></a>Açıklamalar

Kritik bölümler ve spincounts hakkında daha fazla bilgi için, `InitializeCriticalSectionAndSpinCount` `Synchronization` Windows API 'si belgeleri bölümündeki işlevine bakın.

## <a name="criticalsectioncs_"></a><a name="cs"></a> Kritiksection:: cs_

Kritik bir bölüm veri üyesi bildirir.

```cpp
CRITICAL_SECTION cs_;
```

### <a name="remarks"></a>Açıklamalar

Bu veri üyesi korunuyor.

## <a name="criticalsectionisvalid"></a><a name="isvalid"></a> Kritiksection:: IsValid

Geçerli kritik bölümün geçerli olup olmadığını gösterir.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan olarak, her zaman döndürür **`true`** .

## <a name="criticalsectionlock"></a><a name="lock"></a> Kritiksection:: Lock

Belirtilen kritik bölüm nesnesinin sahipliğini bekler. İşlev, çağıran iş parçacığına sahiplik verildiğinde döndürür.

```cpp
SyncLock Lock();

   static SyncLock Lock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
Kullanıcı tarafından belirtilen kritik bölüm nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Geçerli kritik bölümün kilidini açmak için kullanılabilecek bir kilit nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk `Lock` işlev geçerli kritik bölüm nesnesini etkiler. İkinci `Lock` işlev, Kullanıcı tarafından belirtilen bir kritik bölümü etkiler.

## <a name="criticalsectiontrylock"></a><a name="trylock"></a> Kritiksection:: TryLock

Engellenmeden kritik bir bölüm girmeye çalışır. Çağrı başarılı olursa, çağıran iş parçacığı kritik bölümün sahipliğini alır.

```cpp
SyncLock TryLock();

static SyncLock TryLock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
Kullanıcı tarafından belirtilen kritik bölüm nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Kritik bölüm başarıyla girilmişse veya geçerli iş parçacığı zaten kritik bölüme sahipse sıfır dışında bir değer. Zaten kritik bölüme sahip başka bir iş parçacığı varsa sıfırdır.

### <a name="remarks"></a>Açıklamalar

İlk `TryLock` işlev geçerli kritik bölüm nesnesini etkiler. İkinci `TryLock` işlev, Kullanıcı tarafından belirtilen bir kritik bölümü etkiler.
