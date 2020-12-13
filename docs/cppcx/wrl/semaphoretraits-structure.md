---
description: 'Daha fazla bilgi edinin: SemaphoreTraits Yapısı'
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
ms.openlocfilehash: 5779a30d22fd2d32e57f96f752bb52e2bf469cd8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135232"
---
# <a name="semaphoretraits-structure"></a>SemaphoreTraits Yapısı

Bir nesnenin ortak özelliklerini tanımlar `Semaphore` .

## <a name="syntax"></a>Syntax

```cpp
struct SemaphoreTraits : HANDLENullTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Ad                               | Açıklama
---------------------------------- | --------------------------------------
[SemaphoreTraits:: unlock](#unlock) | Paylaşılan bir kaynağın denetimini yayınlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HANDLENullTraits`

`SemaphoreTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar:: Handlenitelikler

## <a name="semaphoretraitsunlock"></a><a name="unlock"></a> SemaphoreTraits:: unlock

Paylaşılan bir kaynağın denetimini yayınlar.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Bir nesne için tanıtıcı `Semaphore` .

### <a name="remarks"></a>Açıklamalar

Kilit açma işlemi başarısız olursa, `Unlock()` hatanın nedenini gösteren bir hata yayar.
