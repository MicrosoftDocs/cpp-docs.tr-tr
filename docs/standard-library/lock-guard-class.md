---
title: lock_guard sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
dev_langs:
- C++
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dcbd0f17392c69b09d6f9f3c8123dfcf8b543fa4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="lockguard-class"></a>lock_guard Sınıfı

Yıkıcı kilidini açarak nesne oluşturmak için örneği bir şablon temsil eden bir `mutex`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Mutex>
class lock_guard;
```

## <a name="remarks"></a>Açıklamalar

Şablon bağımsız değişken `Mutex` adı olmalıdır bir *mutex türü*.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`lock_guard::mutex_type`|Şablon bağımsız değişken için eş anlamlı `Mutex`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[lock_guard](#lock_guard)|Oluşturan bir `lock_guard` nesnesi.|
|[lock_guard:: ~ lock_guard yıkıcısı](#dtorlock_guard_destructor)|Kilidini açarak `mutex` oluşturucuya geçirildi.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<mutex >

**Namespace:** std

## <a name="lock_guard"></a>  lock_guard::lock_guard Oluşturucusu

Oluşturan bir `lock_guard` nesnesi.

```cpp
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```

### <a name="parameters"></a>Parametreler

`Mtx` A *mutex türü* nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucusu türünde bir nesne oluşturur `lock_guard` ve kilitleri `Mtx`. Varsa `Mtx` özyinelemeli mutex değil Bu oluşturucu çağrıldığında kilidi olmalıdır.

İkinci oluşturucu kilit `Mtx`. `Mtx` Bu oluşturucu çağrıldığında kilitlenmiş olması gerekir. Oluşturucusu hiçbir özel durum oluşturur.

## <a name="dtorlock_guard_destructor"></a>  lock_guard:: ~ lock_guard yıkıcısı

Kilidini açarak `mutex` oluşturucuya geçirildi.

```cpp
~lock_guard() noexcept;
```

### <a name="remarks"></a>Açıklamalar

Varsa `mutex` yıkıcı çalıştığında yok davranışı tanımlı değil.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Mutex >](../standard-library/mutex.md)<br/>
