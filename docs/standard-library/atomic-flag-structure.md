---
description: 'Daha fazla bilgi edinin: atomic_flag yapısı'
title: atomic_flag Yapısı
ms.date: 11/04/2016
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
ms.openlocfilehash: f78e3fa8521d230cc119dd7c464653cb6e123733
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149506"
---
# <a name="atomic_flag-structure"></a>atomic_flag Yapısı

Bir bayrağı sıradan olarak ayarlayan ve temizleyen bir nesneyi tanımlar **`bool`** . Atomik bayraklar üzerinde işlemler her zaman kilit ücretsizdir.

## <a name="syntax"></a>Syntax

```cpp
struct atomic_flag;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lediğiniz](#clear)|Saklı bayrağını olarak ayarlar **`false`** .|
|[test_and_set](#test_and_set)|Saklı bayrağını olarak ayarlar **`true`** ve ilk bayrak değerini döndürür.|

## <a name="remarks"></a>Açıklamalar

`atomic_flag` nesneler üye olmayan işlevlere [atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear), [atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit), [atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set)ve [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit)geçirilebilir. Bu değerler kullanılarak başlatılabilir `ATOMIC_FLAG_INIT` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<atomic>

**Ad alanı:** std

## <a name="atomic_flagclear"></a><a name="clear"></a> atomic_flag:: Clear

' **`bool`** De depolanan bayrağı, **`*this`** **`false`** belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları içinde ayarlar.

```cpp
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parametreler

*Siparişi*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_flagtest_and_set"></a><a name="test_and_set"></a> atomic_flag:: test_and_set

' **`bool`** De depolanan bayrağı, **`*this`** **`true`** belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları içinde ayarlar.

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parametreler

*Siparişi*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

İçinde depolanan bayrağın başlangıç değeri **`*this`** .

## <a name="see-also"></a>Ayrıca bkz.

[\<atomic>](../standard-library/atomic.md)
