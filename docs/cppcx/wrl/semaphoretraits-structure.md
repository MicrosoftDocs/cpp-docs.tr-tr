---
title: SemaphoreTraits Yapısı
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock method
ms.assetid: eddb8576-d063-409b-9201-cc87ca5d111e
ms.openlocfilehash: 11719576c9fc7b23f4cd318ee1b3ed9ca3f5edaa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360735"
---
# <a name="semaphoretraits-structure"></a>SemaphoreTraits Yapısı

Nesnenin `Semaphore` ortak özelliklerini tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
struct SemaphoreTraits : HANDLENullTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Adı                               | Açıklama
---------------------------------- | --------------------------------------
[SemaphoreÖzellikler::Kilidini açın](#unlock) | Paylaşılan kaynağın denetimini serbest bırakır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HANDLENullTraits`

`SemaphoreTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar::HandleTraits

## <a name="semaphoretraitsunlock"></a><a name="unlock"></a>SemaphoreÖzellikler::Kilidini açın

Paylaşılan kaynağın denetimini serbest bırakır.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
Bir `Semaphore` nesneye tut.

### <a name="remarks"></a>Açıklamalar

Kilit açma işlemi başarısız `Unlock()` olursa, hatanın nedenini gösteren bir hata yayır.
