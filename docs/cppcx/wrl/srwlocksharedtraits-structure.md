---
description: 'Daha fazla bilgi edinin: Srwlocksharednitelikler yapısı'
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
ms.openlocfilehash: 2cdfbd584adeffc9dedd8504d9183d6c5d4c1a95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135128"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits Yapısı

`SRWLock`Paylaşılan kilit modundaki sınıfın ortak özelliklerini açıklar.

## <a name="syntax"></a>Syntax

```cpp
struct SRWLockSharedTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Ad   | Açıklama
------ | --------------------------------------------------------------------------
`Type` | [SRWLock](srwlock-class.md) sınıfına yönelik bir işaretçi için eş anlamlı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                     | Açıklama
-------------------------------------------------------- | -----------------------------------------------------------------
[Srwlocksharednitelikler:: GetInvalidValue](#getinvalidvalue) | `SRWLockSharedTraits`Her zaman geçersiz olan bir nesne alır.
[Srwlocksharednitelikler:: unlock](#unlock)                   | Belirtilen nesnenin dışlamalı denetimini yayınlar `SRWLock` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SRWLockSharedTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar:: Handlenitelikler

## <a name="srwlocksharedtraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a> Srwlocksharednitelikler:: GetInvalidValue

`SRWLockSharedTraits`Her zaman geçersiz olan bir nesne alır.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Dönüş Değeri

Bir nesne için tanıtıcı `SRWLockSharedTraits` .

## <a name="srwlocksharedtraitsunlock"></a><a name="unlock"></a> Srwlocksharednitelikler:: unlock

Belirtilen nesnenin dışlamalı denetimini yayınlar `SRWLock` .

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Parametreler

*SRWLock*<br/>
Bir nesne için tanıtıcı `SRWLock` .
