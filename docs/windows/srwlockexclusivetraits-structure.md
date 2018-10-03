---
title: SRWLockExclusiveTraits yapısı | Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock method
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7737c802634b618b9ea363c231a44d9381ad30ae
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235171"
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
`Type` | İşaretçisi için eş anlamlı [SRWLOCK](../windows/srwlock-class.md) sınıfı.

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
