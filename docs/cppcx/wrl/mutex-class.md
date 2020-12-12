---
description: 'Daha fazla bilgi edinin: mutex sınıfı'
title: Mutex Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Mutex class
- Microsoft::WRL::Wrappers::Mutex::Lock method
- Microsoft::WRL::Wrappers::Mutex::Mutex, constructor
- Microsoft::WRL::Wrappers::Mutex::operator= operator
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
ms.openlocfilehash: f69c14014a2283fe56ef8e7f705bebe5a5f6dc9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330839"
---
# <a name="mutex-class"></a>Mutex Sınıfı

Paylaşılan bir kaynağı özel olarak denetleyen bir eşitleme nesnesini temsil eder.

## <a name="syntax"></a>Syntax

```cpp
class Mutex : public HandleT<HandleTraits::MutexTraits>;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Ad       | Açıklama
---------- | ------------------------------------------------------
`SyncLock` | Zaman uyumlu kilitleri destekleyen bir sınıf için eş anlamlı.

### <a name="public-constructor"></a>Ortak Oluşturucu

Ad                   | Açıklama
---------------------- | ------------------------------------------------
[Mutex:: mutex](#mutex) | `Mutex` sınıfının yeni bir örneğini başlatır.

### <a name="public-members"></a>Ortak Üyeler

Ad                 | Açıklama
-------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------
[Mutex:: Lock](#lock) | Geçerli nesne veya `Mutex` belirtilen tanıtıcıyla ilişkili nesne tamamlanana kadar bekler, mutex 'i veya belirtilen zaman aşımı aralığını yayınlar.

### <a name="public-operator"></a>Ortak Işleç

Ad                                 | Açıklama
------------------------------------ | ---------------------------------------------------------------------------
[Mutex:: operator =](#operator-assign) | Belirtilen nesneyi geçerli nesneye atar (taşımaktadır) `Mutex` `Mutex` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Mutex`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar

## <a name="mutexlock"></a><a name="lock"></a> Mutex:: Lock

Geçerli nesne veya `Mutex` belirtilen tanıtıcıyla ilişkili nesne tamamlanana kadar bekler, mutex 'i veya belirtilen zaman aşımı aralığını yayınlar.

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
Bir `Mutex` nesnenin tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

## <a name="mutexmutex"></a><a name="mutex"></a> Mutex:: mutex

`Mutex` sınıfının yeni bir örneğini başlatır.

```cpp
explicit Mutex(
   HANDLE h
);

Mutex(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Nesneye bir tanıtıcı veya rvalue başvurusu `Mutex` .

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu `Mutex` belirtilen tanıtıcıdan bir nesne başlatır. İkinci Oluşturucu `Mutex` belirtilen tanıtıcıdan bir nesne başlatır ve ardından mutex 'in sahipliğini geçerli nesneye taşımaktır `Mutex` .

## <a name="mutexoperator"></a><a name="operator-assign"></a> Mutex:: operator =

Belirtilen nesneyi geçerli nesneye atar (taşımaktadır) `Mutex` `Mutex` .

```cpp
Mutex& operator=(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Bir nesnesine rvalue başvurusu `Mutex` .

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneye bir başvuru `Mutex` .

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için, [rvalue başvuru bildirimci:  &&](../../cpp/rvalue-reference-declarator-amp-amp.md)' nin **taşıma semantiğini** bölümüne bakın.
