---
title: Semafor Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Semaphore class
- Microsoft::WRL::Wrappers::Semaphore::Lock method
- Microsoft::WRL::Wrappers::Semaphore::operator= operator
- Microsoft::WRL::Wrappers::Semaphore::Semaphore, constructor
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
ms.openlocfilehash: e017b1b6316c4b6d49563d9a543950ab28961d90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359352"
---
# <a name="semaphore-class"></a>Semafor Sınıfı

Sınırlı sayıda kullanıcıyı destekleyebilen paylaşılan bir kaynağı denetleyen bir eşitleme nesnesini temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

Adı       | Açıklama
---------- | ------------------------------------------------------
`SyncLock` | Senkron kilitleri destekleyen bir sınıfın eşanlamlısı.

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                               | Açıklama
---------------------------------- | ----------------------------------------------------
[Semafor::Semafor](#semaphore) | `Semaphore` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                     | Açıklama
------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------
[Semafor::Kilit](#lock) | Geçerli nesnenin veya belirtilen tanıtıcıyla ilişkili nesnesinyal durumunda olana veya belirtilen zaman aşımı aralığı geçene kadar bekler.

### <a name="public-operators"></a>Ortak İşleçler

Adı                                     | Açıklama
---------------------------------------- | ---------------------------------------------------------------------------------------
[Semafor::operator=](#operator-assign) | Belirtilen tutamacı bir `Semaphore` nesneden `Semaphore` geçerli nesneye taşır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Semaphore`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar

## <a name="semaphorelock"></a><a name="lock"></a>Semafor::Kilit

Geçerli nesnenin veya belirtilen `Semaphore` tanıtıcıyla ilişkili nesnesinyal durumunda olana veya belirtilen zaman aşımı aralığı geçene kadar bekler.

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>Parametreler

*milisaniye*<br/>
Zaman aralığı, milisaniye cinsinden. Varsayılan değer, süresiz olarak bekleyen SONSUZ'dur.

*H*<br/>
Bir `Semaphore` nesneye tutamak.

### <a name="return-value"></a>Dönüş Değeri

Bir `Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`

## <a name="semaphoreoperator"></a><a name="operator-assign"></a>Semafor::operator=

Belirtilen tutamacı bir `Semaphore` nesneden `Semaphore` geçerli nesneye taşır.

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
Bir `Semaphore` nesneye rvalue-reference.

### <a name="return-value"></a>Dönüş Değeri

Geçerli `Semaphore` nesneye bir başvuru.

## <a name="semaphoresemaphore"></a><a name="semaphore"></a>Semafor::Semafor

`Semaphore` sınıfının yeni bir örneğini başlatır.

```cpp
explicit Semaphore(
   HANDLE h
);

WRL_NOTHROW Semaphore(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
Bir `Semaphore` nesneye bir tanıtıcı veya rvalue-reference.
