---
title: SRWLockExclusiveTraits Yapısı
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock method
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
ms.openlocfilehash: eb7b30915d6061e8470601df33fecec310d1bbca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374288"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits Yapısı

`SRWLock` Sınıfın ortak özelliklerini özel kilit modunda açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
struct SRWLockExclusiveTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

Adı   | Açıklama
------ | --------------------------------------------------------------------------
`Type` | [SRWLOCK](srwlock-class.md) sınıfına işaretçi için eşanlamlı.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                                        | Açıklama
----------------------------------------------------------- | --------------------------------------------------------------------
[SRWLockExclusiveÖzellikler::GetInvalidValue](#getinvalidvalue) | Her zaman `SRWLockExclusiveTraits` geçersiz olan bir nesneyi alır.
[SRWLockExclusiveTraits::Kilidini](#unlock)                   | Belirtilen nesnenin özel `SRWLock` denetimini serbest bırakır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SRWLockExclusiveTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar::HandleTraits

## <a name="srwlockexclusivetraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>SRWLockExclusiveÖzellikler::GetInvalidValue

Her zaman `SRWLockExclusiveTraits` geçersiz olan bir nesneyi alır.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Dönüş Değeri

Boş `SRWLockExclusiveTraits` bir nesne.

## <a name="srwlockexclusivetraitsunlock"></a><a name="unlock"></a>SRWLockExclusiveTraits::Kilidini

Belirtilen nesnenin özel `SRWLock` denetimini serbest bırakır.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Parametreler

*Srwlock*<br/>
Bir `SRWLock` nesneye tut.
