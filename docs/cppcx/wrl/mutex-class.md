---
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
ms.openlocfilehash: 36466bd00c5b100f20ee87173e68fdef4131ec23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371228"
---
# <a name="mutex-class"></a>Mutex Sınıfı

Yalnızca paylaşılan bir kaynağı denetleyen bir eşitleme nesnesi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class Mutex : public HandleT<HandleTraits::MutexTraits>;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

Adı       | Açıklama
---------- | ------------------------------------------------------
`SyncLock` | Senkron kilitleri destekleyen bir sınıfın eşanlamlısı.

### <a name="public-constructor"></a>Kamu Yapıcı

Adı                   | Açıklama
---------------------- | ------------------------------------------------
[Mutex::Mutex](#mutex) | `Mutex` sınıfının yeni bir örneğini başlatır.

### <a name="public-members"></a>Kamu Üyeleri

Adı                 | Açıklama
-------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------
[Mutex::Kilit](#lock) | Geçerli nesnenin veya belirtilen `Mutex` tutamaçla ilişkili nesnenin mutex'i serbest bırakmasını veya belirtilen zaman aşımı aralığının geçmesini bekler.

### <a name="public-operator"></a>Kamu Operatörü

Adı                                 | Açıklama
------------------------------------ | ---------------------------------------------------------------------------
[Mutex::operator=](#operator-assign) | Belirtilen `Mutex` nesneyi geçerli `Mutex` nesneye atar (taşır).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Mutex`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar

## <a name="mutexlock"></a><a name="lock"></a>Mutex::Kilit

Geçerli nesnenin veya belirtilen `Mutex` tutamaçla ilişkili nesnenin mutex'i serbest bırakmasını veya belirtilen zaman aşımı aralığının geçmesini bekler.

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
Bir `Mutex` nesnenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

## <a name="mutexmutex"></a><a name="mutex"></a>Mutex::Mutex

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

*H*<br/>
Bir `Mutex` nesneye bir tanıtıcı veya bir tanıtıcıya rvalue-reference.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, belirtilen `Mutex` tutamacından bir nesneyi başharfe ait hale leştirir. İkinci oluşturucu bir `Mutex` nesneyi belirtilen tutamaçtan başharfe taşır ve sonra `Mutex` mutex'in sahipliğini geçerli nesneye taşır.

## <a name="mutexoperator"></a><a name="operator-assign"></a>Mutex::operator=

Belirtilen `Mutex` nesneyi geçerli `Mutex` nesneye atar (taşır).

```cpp
Mutex& operator=(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
Bir `Mutex` nesneye rvalue-reference.

### <a name="return-value"></a>Dönüş Değeri

Geçerli `Mutex` nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi [için, Rvalue Başvuru Bildirimcisi'nin ](../../cpp/rvalue-reference-declarator-amp-amp.md) **Anlamtaşı** bölümüne bakın: &&.
