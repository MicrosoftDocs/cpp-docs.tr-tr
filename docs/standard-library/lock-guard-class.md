---
title: lock_guard Sınıfı
ms.date: 11/04/2016
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
ms.openlocfilehash: 989c1e368e95fc0009f0c3f1c71af0bdba20609d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351713"
---
# <a name="lock_guard-class"></a>lock_guard Sınıfı

Yıkıcı bir nesnenin kilidini açmak için anında oluşturulabilen şablonu `mutex`temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Mutex>
class lock_guard;
```

## <a name="remarks"></a>Açıklamalar

Şablon bağımsız `Mutex` değişkeni bir *mutex türü*adlandırmak gerekir.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|`lock_guard::mutex_type`|Şablon bağımsız değişkeninin `Mutex`eş anlamlısı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[lock_guard](#lock_guard)|Bir `lock_guard` nesne inşa eder.|
|[lock_guard::~lock_guard Yıkıcı](#dtorlock_guard_destructor)|Yapıcıya `mutex` geçirilenin kilidini açar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<mutex>

**Ad alanı:** std

## <a name="lock_guardlock_guard-constructor"></a><a name="lock_guard"></a>lock_guard::lock_guard Yapıcı

Bir `lock_guard` nesne inşa eder.

```cpp
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```

### <a name="parameters"></a>Parametreler

*Mtx*\
*Mutex türü* nde bir nesne.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu türde `lock_guard` bir nesne inşa eder ve *Mtx'i*kilitler. *Mtx* özyinelemeli bir mutex değilse, bu oluşturucu çağrıldığında kilidi açılmalıdır.

İkinci yapıcı *Mtx*kilitlemez. Bu yapıcı çağrıldığında *Mtx* kilitlenmelidir. Yapıcı hiçbir istisna atar.

## <a name="lock_guardlock_guard-destructor"></a><a name="dtorlock_guard_destructor"></a>lock_guard::~lock_guard Yıkıcı

Yapıcıya `mutex` geçirilenin kilidini açar.

```cpp
~lock_guard() noexcept;
```

### <a name="remarks"></a>Açıklamalar

`mutex` Yıkıcı çalıştığında yok edici yoksa, davranış tanımsızdır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
