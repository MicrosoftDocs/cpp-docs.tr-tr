---
title: atomic_flag yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
dev_langs:
- C++
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e6a5162057944ac3d91d2465cfefe99c68dd5fb3
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961421"
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

*Sipariş* A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="test_and_set"></a>  atomic_flag::test_and_set

Kümeleri **bool** depolanan bayrağı `*this` için **true**, dahilinde belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları.

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sipariş* A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

Saklanan bayrağın ilk değeri `*this`.

## <a name="see-also"></a>Ayrıca bkz.

[\<atomik >](../standard-library/atomic.md)<br/>
