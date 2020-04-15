---
title: atomic_flag Yapısı
ms.date: 11/04/2016
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
ms.openlocfilehash: ad4b6dcaf6db1a8abe5b81b4d630e84b54fbaa63
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376864"
---
# <a name="atomic_flag-structure"></a>atomic_flag Yapısı

Atomik olarak bool bayrağını ayarlayan ve temizleyen bir **nesneyi** açıklar. Atomik bayraklar üzerindeki işlemler her zaman kilitsizdir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct atomic_flag;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Temizleyin](#clear)|Depolanan bayrağı **false**olarak ayarlar.|
|[test_and_set](#test_and_set)|Depolanan bayrağı **doğru** olarak ayarlar ve ilk bayrak değerini döndürür.|

## <a name="remarks"></a>Açıklamalar

`atomic_flag`nesneler, üye olmayan işlevlere [atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear), [atomic_flag_clear_explicit,](../standard-library/atomic-functions.md#atomic_flag_clear_explicit) [atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set)ve [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit)geçirilebilir. Onlar değeri `ATOMIC_FLAG_INIT`kullanılarak başharfe alınabilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<atomik>

**Ad alanı:** std

## <a name="atomic_flagclear"></a><a name="clear"></a>atomic_flag::açık

Belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları içinde, **false'da** `*this` depolanan **bool** bayrağını ayarlar.

```cpp
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sipariş*\
Bir [memory_order.](../standard-library/atomic-enums.md#memory_order_enum)

## <a name="atomic_flagtest_and_set"></a><a name="test_and_set"></a>atomic_flag:test_and_set

Belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları **içinde,** doğru `*this` olarak depolanan **bool** bayrağını ayarlar.

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sipariş*\
Bir [memory_order.](../standard-library/atomic-enums.md#memory_order_enum)

### <a name="return-value"></a>Dönüş Değeri

Depolanan bayrağın başlangıç `*this`değeri.

## <a name="see-also"></a>Ayrıca bkz.

[\<atomik>](../standard-library/atomic.md)
