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
ms.openlocfilehash: e7bd2e5d0993c8e4be7223d98ffb1dbec14cbb74
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502953"
---
# <a name="semaphoretraits-structure"></a>SemaphoreTraits Yapısı

Ortak özelliklerini tanımlayan bir `Semaphore` nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
struct SemaphoreTraits : HANDLENullTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Ad                               | Açıklama
---------------------------------- | --------------------------------------
[SemaphoreTraits::Unlock](#unlock) | Paylaşılan bir kaynak denetim yayınlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HANDLENullTraits`

`SemaphoreTraits`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="unlock"></a>SemaphoreTraits::Unlock

Paylaşılan bir kaynak denetim yayınlar.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
İşlemek için bir `Semaphore` nesne.

### <a name="remarks"></a>Açıklamalar

Kilit açma işlemi başarısızsa, `Unlock()` hatanın nedenini belirten bir hata gösterir.
