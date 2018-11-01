---
title: atomic_flag Yapısı
ms.date: 11/04/2016
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
ms.openlocfilehash: 13af0c26b765aa7ebbbd1ec22b5a0ed1b8cce0ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550429"
---
# <a name="atomicflag-structure"></a>atomic_flag Yapısı

Atomik olarak ayarlayan ve temizleyen bir nesneyi tanımlayan bir **bool** bayrağı. Atomik bayraklar üzerinde yapılan işlemler her zaman kilitsizdir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct atomic_flag;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Temizle](#clear)|Saklı bayrağı ayarlar **false**.|
|[test_and_set](#test_and_set)|Saklı bayrağı ayarlar **true** ve ilk bayrak değerini döndürür.|

## <a name="remarks"></a>Açıklamalar

`atomic_flag` nesneleri üye olmayan işlevlere geçirilebilir [atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear), [atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit), [atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set), ve [atomik _flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit). Değeri kullanılarak başlatılabilir `ATOMIC_FLAG_INIT`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<atomik >

**Namespace:** std

## <a name="clear"></a>  atomic_flag::Clear

Kümeleri **bool** depolanan bayrağı `*this` için **false**, dahilinde belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları.

```cpp
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sırası*<br/>
A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="test_and_set"></a>  atomic_flag::test_and_set

Kümeleri **bool** depolanan bayrağı `*this` için **true**, dahilinde belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları.

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sırası*<br/>
A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

Saklanan bayrağın ilk değeri `*this`.

## <a name="see-also"></a>Ayrıca bkz.

[\<atomik >](../standard-library/atomic.md)<br/>
