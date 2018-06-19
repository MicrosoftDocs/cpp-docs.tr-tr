---
title: allocator_variable_size sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::allocator_variable_size
- allocators/stdext::allocators::allocator_variable_size
- stdext::allocators::allocator_variable_size
dev_langs:
- C++
helpviewer_keywords:
- stdext::allocator_variable_size
- stdext::allocators [C++], allocator_variable_size
ms.assetid: c3aa4105-ae45-4385-bbbe-9f23060478cb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 690be271cd7e9ad3eaf019f1feb67202c14a9e5c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33840608"
---
# <a name="allocatorvariablesize-class"></a>allocator_variable_size Sınıfı

Depolama ayırma ve serbest bırakma türündeki nesneler için yöneten bir nesneyi tanımlayan `Type` bir önbellek türü kullanarak [cache_freelist](../standard-library/cache-freelist-class.md) tarafından yönetilen bir uzunluğa sahip [max_variable_size](../standard-library/max-variable-size-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class allocator_variable_size;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Type`|Ayırıcı tarafından ayrılan öğelerin türü.|

## <a name="remarks"></a>Açıklamalar

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) makrosu geçirir bu sınıfı olarak `name` aşağıdaki ifadeyi parametresinde: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_variable_size), SYNC_DEFAULT, allocator_variable_size);`

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<allocators >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators >](../standard-library/allocators-header.md)<br/>
