---
title: SRWLockSharedTraits Yapısı
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock method
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
ms.openlocfilehash: 0dc43d4b9c16145ed7a5abe03cddb598c59b1e94
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374296"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits Yapısı

Paylaşılan kilit modunda `SRWLock` sınıfın ortak özelliklerini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
struct SRWLockSharedTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

Adı   | Açıklama
------ | --------------------------------------------------------------------------
`Type` | [SRWLOCK](srwlock-class.md) sınıfına işaretçi için eşanlamlı.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                                     | Açıklama
-------------------------------------------------------- | -----------------------------------------------------------------
[SRWLockSharedTraits::GetInvalidValue](#getinvalidvalue) | Her zaman `SRWLockSharedTraits` geçersiz olan bir nesneyi alır.
[SRWLockSharedTraits::Kilidini Aç](#unlock)                   | Belirtilen nesnenin özel `SRWLock` denetimini serbest bırakır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SRWLockSharedTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar::HandleTraits

## <a name="srwlocksharedtraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>SRWLockSharedTraits::GetInvalidValue

Her zaman `SRWLockSharedTraits` geçersiz olan bir nesneyi alır.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `SRWLockSharedTraits` nesneye tutamak.

## <a name="srwlocksharedtraitsunlock"></a><a name="unlock"></a>SRWLockSharedTraits::Kilidini Aç

Belirtilen nesnenin özel `SRWLock` denetimini serbest bırakır.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Parametreler

*Srwlock*<br/>
Bir `SRWLock` nesneye tutamak.
