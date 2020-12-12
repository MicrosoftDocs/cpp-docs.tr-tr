---
description: 'Daha fazla bilgi edinin: SRWLockExclusiveTraits yapısı'
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
ms.openlocfilehash: 135d4f866d1ca32ee9170ef9844cb0bf8d38c29a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186213"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits Yapısı

`SRWLock`Özel kilit modundaki sınıfın ortak özelliklerini açıklar.

## <a name="syntax"></a>Syntax

```cpp
struct SRWLockExclusiveTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Ad   | Açıklama
------ | --------------------------------------------------------------------------
`Type` | [SRWLock](srwlock-class.md) sınıfına yönelik bir işaretçi için eş anlamlı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                        | Açıklama
----------------------------------------------------------- | --------------------------------------------------------------------
[SRWLockExclusiveTraits:: GetInvalidValue](#getinvalidvalue) | `SRWLockExclusiveTraits`Her zaman geçersiz olan bir nesne alır.
[SRWLockExclusiveTraits:: unlock](#unlock)                   | Belirtilen nesnenin dışlamalı denetimini yayınlar `SRWLock` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SRWLockExclusiveTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar:: Handlenitelikler

## <a name="srwlockexclusivetraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a> SRWLockExclusiveTraits:: GetInvalidValue

`SRWLockExclusiveTraits`Her zaman geçersiz olan bir nesne alır.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Dönüş Değeri

Boş bir `SRWLockExclusiveTraits` nesne.

## <a name="srwlockexclusivetraitsunlock"></a><a name="unlock"></a> SRWLockExclusiveTraits:: unlock

Belirtilen nesnenin dışlamalı denetimini yayınlar `SRWLock` .

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Parametreler

*SRWLock*<br/>
Bir nesne için tanıtıcı `SRWLock` .
