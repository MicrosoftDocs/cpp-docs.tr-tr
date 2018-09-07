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
ms.openlocfilehash: 5e096d21699d4e6218bbadedcd1cc0bcc65f92f2
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44108195"
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
