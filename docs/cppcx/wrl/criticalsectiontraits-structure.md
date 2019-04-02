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
ms.openlocfilehash: ce904ecbd9a5855c63fd43f07f88c215cef544ae
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787694"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits Yapısı

Uzmanlaşmış bir `CriticalSection` geçersiz bir kritik bölüm veya kritik bir bölüm serbest bırakmak için bir işlevi desteklemek için nesne.

## <a name="syntax"></a>Sözdizimi

```
struct CriticalSectionTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

Ad   | Açıklama
------ | -----------------------------------------------------------------------------------------------------------------
`Type` | A `typedef` , kritik bir bölüm için bir işaretçi tanımlar. `Type` olarak tanımlanan `typedef CRITICAL_SECTION* Type;`.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                       | Açıklama
---------------------------------------------------------- | -----------------
[Criticalsectiontraits::getınvalidvalue](#getinvalidvalue) | Uzmanlaşmış bir `CriticalSection` şablon böylece şablonu her zaman geçerli değil.
[CriticalSectionTraits::Unlock](#unlock)                   | Uzmanlaşmış bir `CriticalSection` BT'nin siteminizi belirtilen kritik bölüm nesnenin sahipliğini destekler böylece şablonu.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CriticalSectionTraits`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>Criticalsectiontraits::getınvalidvalue

Uzmanlaşmış bir `CriticalSection` şablon böylece şablonu her zaman geçerli değil.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman için geçersiz bir kritik bölüm bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

`Type` Değiştirici olarak tanımlanmış olan `typedef CRITICAL_SECTION* Type;`.

## <a name="unlock"></a>CriticalSectionTraits::Unlock

Uzmanlaşmış bir `CriticalSection` BT'nin siteminizi belirtilen kritik bölüm nesnenin sahipliğini destekler böylece şablonu.

```cpp
inline static void Unlock(
   _In_ Type cs
);
```

### <a name="parameters"></a>Parametreler

*cs*<br/>
Kritik bölüm nesnesine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`Type` Değiştirici olarak tanımlanmış olan `typedef CRITICAL_SECTION* Type;`.

Daha fazla bilgi için **LeaveCriticalSection işlevi** içinde **eşitleme işlevleri** Windows API belgelerinin bölümü.
