---
title: lock_guard Sınıfı
ms.date: 11/04/2016
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
ms.openlocfilehash: 45a01c5fdd431bcfad1eeb5ab0531c11c89e9767
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50645555"
---
# <a name="lockguard-class"></a>lock_guard Sınıfı

Yok Edicisi kilidini açarak bir nesne oluşturmak için örneği bir şablonunu temsil eden bir `mutex`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Mutex>
class lock_guard;
```

## <a name="remarks"></a>Açıklamalar

Şablon bağımsız değişkeni `Mutex` adlandırmalısınız bir *mutex türünü*.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`lock_guard::mutex_type`|Şablon bağımsız değişkeni için eş anlamlı `Mutex`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[lock_guard](#lock_guard)|Oluşturur bir `lock_guard` nesne.|
|[lock_guard:: ~ lock_guard yıkıcısı](#dtorlock_guard_destructor)|Kilit açma `mutex` oluşturucuya geçirildi.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<mutex >

**Namespace:** std

## <a name="lock_guard"></a>  lock_guard::lock_guard Oluşturucusu

Oluşturur bir `lock_guard` nesne.

```cpp
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```

### <a name="parameters"></a>Parametreler

*Mtx*<br/>
A *mutex türünü* nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu türü bir nesne oluşturur `lock_guard` ve kilitleri *Mtx*. Varsa *Mtx* özyinelemeli mutex'i değil Bu oluşturucu çağrıldığında kilidi olmalıdır.

İkinci oluşturucu kilit *Mtx*. *Mtx* Bu oluşturucu çağrıldığında kilitlenmelidir. Oluşturucu, özel durum oluşturur.

## <a name="dtorlock_guard_destructor"></a>  lock_guard:: ~ lock_guard yıkıcısı

Kilit açma `mutex` oluşturucuya geçirildi.

```cpp
~lock_guard() noexcept;
```

### <a name="remarks"></a>Açıklamalar

Varsa `mutex` yıkıcı çalıştığında yok davranış tanımlanmamıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Mutex >](../standard-library/mutex.md)<br/>
