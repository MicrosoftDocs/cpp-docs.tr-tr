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
ms.openlocfilehash: af567fd333854519df4543ad24084e52cda4d96e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58787060"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits Yapısı

Genel özelliklerini açıklayan `SRWLock` paylaşılan kilit modu sınıfta.

## <a name="syntax"></a>Sözdizimi

```cpp
struct SRWLockSharedTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

Ad   | Açıklama
------ | --------------------------------------------------------------------------
`Type` | İşaretçisi için eş anlamlı [SRWLOCK](srwlock-class.md) sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                     | Açıklama
-------------------------------------------------------- | -----------------------------------------------------------------
[Srwlocksharedtraits::getınvalidvalue](#getinvalidvalue) | Alır bir `SRWLockSharedTraits` her zaman geçersiz bir nesne.
[SRWLockSharedTraits::Unlock](#unlock)                   | Belirtilen özel denetim serbest `SRWLock` nesne.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SRWLockSharedTraits`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>Srwlocksharedtraits::getınvalidvalue

Alır bir `SRWLockSharedTraits` her zaman geçersiz bir nesne.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Dönüş Değeri

İçin bir tanıtıcı bir `SRWLockSharedTraits` nesne.

## <a name="unlock"></a>SRWLockSharedTraits::Unlock

Belirtilen özel denetim serbest `SRWLock` nesne.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Parametreler

*srwlock*<br/>
İçin bir tanıtıcı bir `SRWLock` nesne.
