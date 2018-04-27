---
title: atomic_flag yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
dev_langs:
- C++
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f36164427f7cbc1cea9fda5f7e4d20896323d08
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="atomicflag-structure"></a>atomic_flag Yapısı

Otomatik olarak ayarlar ve temizler bir nesneyi tanımlayan bir `bool` bayrağı. Atomik bayrakları işlemleri her zaman kilidi serbest.

## <a name="syntax"></a>Sözdizimi

```cpp
struct atomic_flag;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Temizle](#clear)|Saklı bayrağını ayarlar `false`.|
|[test_and_set](#test_and_set)|Saklı bayrağını ayarlar `true` ve ilk bayrak değeri döndürür.|

## <a name="remarks"></a>Açıklamalar

`atomic_flag` nesneler için üye olmayan işlevleri geçirilebilir [atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear), [atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit), [atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set), ve [atomik _flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit). Değeri kullanılarak başlatılabilir `ATOMIC_FLAG_INIT`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<atomik >

**Namespace:** std

## <a name="clear"></a>  atomic_flag::Clear

Ayarlar `bool` depolanan bayrağı `*this` için `false`, belirtilen içinde [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları.

```cpp
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parametreler

`Order` A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="test_and_set"></a>  atomic_flag::test_and_set

Ayarlar `bool` depolanan bayrağı `*this` için `true`, belirtilen içinde [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları.

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parametreler

`Order` A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

Depolanan bayrağı ilk değeri `*this`.

## <a name="see-also"></a>Ayrıca bkz.

[\<atomik >](../standard-library/atomic.md)<br/>
