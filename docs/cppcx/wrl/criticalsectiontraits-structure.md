---
title: CriticalSectionTraits Yapısı
ms.date: 09/26/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock method
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
ms.openlocfilehash: 05c93bf6a2765bd11489075067c627ab3c3ab691
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372575"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits Yapısı

Geçersiz bir `CriticalSection` kritik bölümü veya kritik bir bölümü serbest bırakmak için bir işlevi desteklemek için bir nesne özelleştiriyor.

## <a name="syntax"></a>Sözdizimi

```
struct CriticalSectionTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

Adı   | Açıklama
------ | -----------------------------------------------------------------------------------------------------------------
`Type` | Kritik `typedef` bir bölüme işaretçi tanımlayan a. `Type`olarak `typedef CRITICAL_SECTION* Type;`tanımlanır.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                                       | Açıklama
---------------------------------------------------------- | -----------------
[CriticalSectionÖzellikler::GetInvalidValue](#getinvalidvalue) | Şablonun `CriticalSection` her zaman geçersiz olması için şablonu özele erittir.
[CriticalSectionÖzellikler::Kilidini Aç](#unlock)                   | Bir `CriticalSection` şablonu, belirtilen kritik bölüm nesnesinin sahipliğini serbest bırakmayı destekleyebilecek şekilde özelleştiriyor.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CriticalSectionTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar::HandleTraits

## <a name="criticalsectiontraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>CriticalSectionÖzellikler::GetInvalidValue

Şablonun `CriticalSection` her zaman geçersiz olması için şablonu özele erittir.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman geçersiz kritik bölüme bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

`Type` Değiştirici olarak `typedef CRITICAL_SECTION* Type;`tanımlanır.

## <a name="criticalsectiontraitsunlock"></a><a name="unlock"></a>CriticalSectionÖzellikler::Kilidini Aç

Bir `CriticalSection` şablonu, belirtilen kritik bölüm nesnesinin sahipliğini serbest bırakmayı destekleyebilecek şekilde özelleştiriyor.

```cpp
inline static void Unlock(
   _In_ Type cs
);
```

### <a name="parameters"></a>Parametreler

*Cs*<br/>
Kritik bir bölüm nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

`Type` Değiştirici olarak `typedef CRITICAL_SECTION* Type;`tanımlanır.

Daha fazla bilgi için, Windows API belgelerinin **Eşitleme İşlevleri** **bölümündeki LeaveCriticalSection işlevine** bakın.
