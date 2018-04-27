---
title: allocator_fixed_size sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- allocators/stdext::allocators::allocator_fixed_size
- allocators/stdext::allocator_fixed_size
- stdext::allocators::allocator_fixed_size
dev_langs:
- C++
helpviewer_keywords:
- stdext::allocators [C++], allocator_fixed_size
- stdext::allocator_fixed_size
ms.assetid: 138f3ef8-b0b3-49c3-9486-58f2213c172f
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3ac50622218e0ca7091e7bfea1b09aa93dec58ef
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="allocatorfixedsize-class"></a>allocator_fixed_size Sınıfı

Depolama ayırma ve serbest bırakma türündeki nesneler için yöneten bir nesneyi tanımlayan `Type` bir önbellek türü kullanarak [cache_freelist](../standard-library/cache-freelist-class.md) tarafından yönetilen bir uzunluğa sahip [max_fixed_size](../standard-library/max-fixed-size-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class allocator_fixed_size;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Type`|Ayırıcı tarafından ayrılan öğelerin türü.|

## <a name="remarks"></a>Açıklamalar

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) makrosu geçirir bu sınıfı olarak `name` aşağıdaki ifadeyi parametresinde: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_fixed_size<10>), SYNC_DEFAULT, allocator_fixed_size);`

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<allocators >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators >](../standard-library/allocators-header.md)<br/>
