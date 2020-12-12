---
description: 'Hakkında daha fazla bilgi edinin: lock_guard sınıfı'
title: lock_guard Sınıfı
ms.date: 11/04/2016
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
ms.openlocfilehash: d8965f1e781d99f0b84c58dcc3288a4532e4351c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277732"
---
# <a name="lock_guard-class"></a>lock_guard Sınıfı

Yıkıcıya kilidi olan bir nesne oluşturmak için örneklenebilir bir şablonu temsil eder `mutex` .

## <a name="syntax"></a>Syntax

```cpp
template <class Mutex>
class lock_guard;
```

## <a name="remarks"></a>Açıklamalar

Şablon bağımsız değişkeni `Mutex` bir *mutex türü* adı vermelidir.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`lock_guard::mutex_type`|Şablon bağımsız değişkeni için eş anlamlı `Mutex` .|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[lock_guard](#lock_guard)|Bir `lock_guard` nesnesi oluşturur.|
|[lock_guard:: ~ lock_guard yok edici](#dtorlock_guard_destructor)|`mutex`Oluşturucuya geçirilen öğesini kaldırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<mutex>

**Ad alanı:** std

## <a name="lock_guardlock_guard-constructor"></a><a name="lock_guard"></a> lock_guard:: lock_guard Oluşturucusu

Bir `lock_guard` nesnesi oluşturur.

```cpp
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```

### <a name="parameters"></a>Parametreler

*MTX*\
Bir *mutex tür* nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, MTX türünde bir nesne oluşturur `lock_guard` ve kilitler. *MTX* özyinelemeli bir mutex değilse, bu Oluşturucu çağrıldığında kilidinin açılması gerekir.

İkinci Oluşturucu *MTX*'yi kilitlemez. Bu Oluşturucu çağrıldığında *MTX* 'in kilitlenmesi gerekir. Oluşturucu özel durum oluşturmaz.

## <a name="lock_guardlock_guard-destructor"></a><a name="dtorlock_guard_destructor"></a> lock_guard:: ~ lock_guard yok edici

`mutex`Oluşturucuya geçirilen öğesini kaldırır.

```cpp
~lock_guard() noexcept;
```

### <a name="remarks"></a>Açıklamalar

Yok `mutex` edicinin çalıştırıldığı zaman yoksa, davranış tanımsızdır.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
