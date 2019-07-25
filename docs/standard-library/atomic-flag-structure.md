---
title: atomic_flag Yapısı
ms.date: 11/04/2016
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
ms.openlocfilehash: 36944c3c3bdc58272d87bbcdfb119d1c52c43995
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447397"
---
# <a name="atomicflag-structure"></a>atomic_flag Yapısı

Bir **bool** bayrağını sıradan olarak ayarlayan ve temizleyen bir nesneyi tanımlar. Atomik bayraklar üzerinde işlemler her zaman kilit ücretsizdir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct atomic_flag;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lediğiniz](#clear)|Saklı bayrağını **false**olarak ayarlar.|
|[test_and_set](#test_and_set)|Saklı bayrağını **true** olarak ayarlar ve ilk bayrak değerini döndürür.|

## <a name="remarks"></a>Açıklamalar

`atomic_flag`nesneler [atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear), [atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit), [atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set)ve [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit)üye olmayan işlevlere geçirilebilir. Bu değerler `ATOMIC_FLAG_INIT`kullanılarak başlatılabilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<atomik >

**Ad alanı:** std

## <a name="clear"></a>atomic_flag:: Clear

Belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları içinde, `*this` içinde depolanan **bool** bayrağını **false**olarak ayarlar.

```cpp
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parametreler

*Siparişi*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="test_and_set"></a>atomic_flag::test_and_set

Belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları içinde, **true** `*this` olarak depolanan **bool** bayrağını ayarlar.

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parametreler

*Siparişi*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

İçinde `*this`depolanan bayrağın başlangıç değeri.

## <a name="see-also"></a>Ayrıca bkz.

[\<Atomik >](../standard-library/atomic.md)
