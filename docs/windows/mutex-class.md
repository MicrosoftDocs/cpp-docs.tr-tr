---
title: Mutex sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Mutex class
- Microsoft::WRL::Wrappers::Mutex::Lock method
- Microsoft::WRL::Wrappers::Mutex::Mutex, constructor
- Microsoft::WRL::Wrappers::Mutex::operator= operator
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 37aaafa636f43671eb18436a49490caa10cf349f
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789312"
---
# <a name="mutex-class"></a>Mutex Sınıfı

Paylaşılan bir kaynağa özel olarak denetleyen bir eşitleme nesnesi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class Mutex : public HandleT<HandleTraits::MutexTraits>;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

Ad       | Açıklama
---------- | ------------------------------------------------------
`SyncLock` | Zaman uyumlu kilitleri destekleyen bir sınıf için bir eşanlamlı.

### <a name="public-constructor"></a>Genel oluşturucu

Ad                   | Açıklama
---------------------- | ------------------------------------------------
[Mutex::mutex](#mutex) | Yeni bir örneğini başlatır `Mutex` sınıfı.

### <a name="public-members"></a>Ortak üyeler

Ad                 | Açıklama
-------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------
[Mutex::LOCK](#lock) | Geçerli nesne kadar bekler veya `Mutex` belirtilen tanıtıcısı, mutex veya belirtilen zaman aşımı aralığı geçtikten yayınlar ilişkili nesne.

### <a name="public-operator"></a>Genel işleç

Ad                                 | Açıklama
------------------------------------ | ---------------------------------------------------------------------------
[Mutex::operator =](#operator-assign) | Atar (taşıma) belirtilen `Mutex` geçerli nesneye `Mutex` nesne.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Mutex`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="lock"></a>Mutex::LOCK

Geçerli nesne kadar bekler veya `Mutex` belirtilen tanıtıcısı, mutex veya belirtilen zaman aşımı aralığı geçtikten yayınlar ilişkili nesne.

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

*Milisaniye*<br/>
Milisaniye cinsinden zaman aşımı aralığı. Varsayılan değer süresiz olarak bekler sonsuzdur.

*h*<br/>
Tanıtıcısını bir `Mutex` nesne.

### <a name="return-value"></a>Dönüş Değeri

## <a name="mutex"></a>Mutex::mutex

Yeni bir örneğini başlatır `Mutex` sınıfı.

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
Tanıtıcı ya da bir tanıtıcı bir rvalue başvurusu için bir `Mutex` nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu başlatan bir `Mutex` nesnesinden belirtilen tanıtıcı. İkinci oluşturucu başlatan bir `Mutex` geçerli nesne belirtilen tanıtıcı, ve ardından mutex sahipliğini taşır `Mutex` nesne.

## <a name="operator-assign"></a>Mutex::operator =

Atar (taşıma) belirtilen `Mutex` geçerli nesneye `Mutex` nesne.

```cpp
Mutex& operator=(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Bir rvalue başvurusuna bir `Mutex` nesne.

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir başvuru `Mutex` nesne.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için **taşıma semantiği** bölümünü [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).
