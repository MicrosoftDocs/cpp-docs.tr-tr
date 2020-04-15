---
title: MutexTraits Yapısı
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock method
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
ms.openlocfilehash: 6d4ba08ab1884e8584b0e98e931d2d63cdac5aec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371248"
---
# <a name="mutextraits-structure"></a>MutexTraits Yapısı

[Mutex](mutex-class.md) sınıfının ortak özelliklerini tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
struct MutexTraits : HANDLENullTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Adı                           | Açıklama
------------------------------ | ------------------------------------------------
[MutexTraits::Kilidini](#unlock) | Paylaşılan kaynağın özel denetimini serbest bırakır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HANDLENullTraits`

`MutexTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar::HandleTraits

## <a name="mutextraitsunlock-method"></a><a name="unlock"></a>MutexTraits::Unlock Yöntemi

Paylaşılan kaynağın özel denetimini serbest bırakır.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
Mutex nesnesine tut.
