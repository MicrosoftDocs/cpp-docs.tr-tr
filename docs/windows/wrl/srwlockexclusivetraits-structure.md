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
ms.openlocfilehash: 25249b8823b8c182133e85aa4cd07d38f5874cf2
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335346"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits Yapısı

Genel özelliklerini açıklayan `SRWLock` sınıfında özel bir kilit modu.

## <a name="syntax"></a>Sözdizimi

```cpp
struct SRWLockExclusiveTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

Ad   | Açıklama
------ | --------------------------------------------------------------------------
`Type` | İşaretçisi için eş anlamlı [SRWLOCK](srwlock-class.md) sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                        | Açıklama
----------------------------------------------------------- | --------------------------------------------------------------------
[Srwlockexclusivetraits::getınvalidvalue](#getinvalidvalue) | Alır bir `SRWLockExclusiveTraits` her zaman geçersiz bir nesne.
[SRWLockExclusiveTraits::Unlock](#unlock)                   | Belirtilen özel denetim serbest `SRWLock` nesne.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SRWLockExclusiveTraits`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>Srwlockexclusivetraits::getınvalidvalue

Alır bir `SRWLockExclusiveTraits` her zaman geçersiz bir nesne.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Dönüş Değeri

Boş bir `SRWLockExclusiveTraits` nesne.

## <a name="unlock"></a>SRWLockExclusiveTraits::Unlock

Belirtilen özel denetim serbest `SRWLock` nesne.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Parametreler

*srwlock*<br/>
İşlemek için bir `SRWLock` nesne.
