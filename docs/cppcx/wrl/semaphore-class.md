---
description: 'Daha fazla bilgi edinin: semafor sınıfı'
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
ms.openlocfilehash: 0cf99ff0a0e5263b3ed924ec5ac69b7edb0bd1f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186239"
---
# <a name="semaphore-class"></a>Semafor Sınıfı

Sınırlı sayıda kullanıcıyı destekleyebilen, paylaşılan bir kaynağı denetleyen bir eşitleme nesnesini temsil eder.

## <a name="syntax"></a>Syntax

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Ad       | Açıklama
---------- | ------------------------------------------------------
`SyncLock` | Zaman uyumlu kilitleri destekleyen bir sınıf için eş anlamlı.

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                               | Açıklama
---------------------------------- | ----------------------------------------------------
[Semafor:: semafor](#semaphore) | `Semaphore` sınıfının yeni bir örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                     | Açıklama
------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------
[Semafor:: Lock](#lock) | Geçerli nesne veya belirtilen tanıtıcıyla ilişkili nesne, sinyal durumunda veya belirtilen zaman aşımı aralığı geçtiğinde bekler.

### <a name="public-operators"></a>Ortak İşleçler

Ad                                     | Açıklama
---------------------------------------- | ---------------------------------------------------------------------------------------
[Semafor:: operator =](#operator-assign) | Belirtilen tanıtıcıyı bir `Semaphore` nesneden geçerli `Semaphore` nesneye kaydırır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Semaphore`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar

## <a name="semaphorelock"></a><a name="lock"></a> Semafor:: Lock

Geçerli nesne veya `Semaphore` belirtilen tanıtıcıyla ilişkili nesne, sinyal durumunda veya belirtilen zaman aşımı aralığı geçtiğinde bekler.

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
Milisaniye cinsinden zaman aşımı aralığı. Varsayılan değer sonsuz ' dur ve sonsuza kadar bekler.

*h*<br/>
Bir nesne için tanıtıcı `Semaphore` .

### <a name="return-value"></a>Dönüş Değeri

`Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`

## <a name="semaphoreoperator"></a><a name="operator-assign"></a> Semafor:: operator =

Belirtilen tanıtıcıyı bir `Semaphore` nesneden geçerli `Semaphore` nesneye kaydırır.

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Rvalue-bir nesneye başvuru `Semaphore` .

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneye bir başvuru `Semaphore` .

## <a name="semaphoresemaphore"></a><a name="semaphore"></a> Semafor:: semafor

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

*h*<br/>
Bir nesneye bir tanıtıcı veya rvalue başvurusu `Semaphore` .
