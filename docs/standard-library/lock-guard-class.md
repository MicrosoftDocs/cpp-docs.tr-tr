---
title: lock_guard Sınıfı
ms.date: 11/04/2016
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
ms.openlocfilehash: f59860c3aaa9ef7458fe5e30b85b119dede52c72
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453851"
---
# <a name="lockguard-class"></a>lock_guard Sınıfı

Yıkıcıya kilidi olan bir `mutex`nesne oluşturmak için örneklenebilir bir şablonu temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Mutex>
class lock_guard;
```

## <a name="remarks"></a>Açıklamalar

Şablon bağımsız değişkeni `Mutex` bir *mutex türü*adı vermelidir.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`lock_guard::mutex_type`|Şablon bağımsız değişkeni `Mutex`için eş anlamlı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[lock_guard](#lock_guard)|Bir `lock_guard` nesnesi oluşturur.|
|[lock_guard:: ~ lock_guard yıkıcısı](#dtorlock_guard_destructor)|`mutex` Oluşturucuya geçirilen öğesini kaldırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<mutex >

**Ad alanı:** std

## <a name="lock_guard"></a>lock_guard:: lock_guard Oluşturucusu

Bir `lock_guard` nesnesi oluşturur.

```cpp
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```

### <a name="parameters"></a>Parametreler

*MTX*\
Bir *mutex tür* nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, `lock_guard` *MTX*türünde bir nesne oluşturur ve kilitler. *MTX* özyinelemeli bir mutex değilse, bu Oluşturucu çağrıldığında kilidinin açılması gerekir.

İkinci Oluşturucu *MTX*'yi kilitlemez. Bu Oluşturucu çağrıldığında *MTX* 'in kilitlenmesi gerekir. Oluşturucu özel durum oluşturmaz.

## <a name="dtorlock_guard_destructor"></a>lock_guard:: ~ lock_guard yıkıcısı

`mutex` Oluşturucuya geçirilen öğesini kaldırır.

```cpp
~lock_guard() noexcept;
```

### <a name="remarks"></a>Açıklamalar

`mutex` Yok edicinin çalıştırıldığı zaman yoksa, davranış tanımsızdır.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex >](../standard-library/mutex.md)
