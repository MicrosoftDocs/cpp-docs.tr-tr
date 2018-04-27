---
title: allocator_chunklist sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- allocators/stdext::allocator_chunklist
- allocators/stdext::allocators::allocator_chunklist
dev_langs:
- C++
helpviewer_keywords:
- stdext::allocator_chunklist
- stdext::allocators [C++], allocator_chunklist
ms.assetid: ea72ed0a-dfdb-4c8b-8096-e4baf567b80f
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 358155efc500695ba44c00ffa03c5fe71bdd4c80
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="allocatorchunklist-class"></a>allocator_chunklist Sınıfı

Depolama ayırma ve için bir önbellek türü kullanarak nesneleri serbest bırakma yöneten bir nesneyi tanımlayan [cache_chunklist](../standard-library/cache-chunklist-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class allocator_chunklist;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Type`|Ayırıcı tarafından ayrılan öğelerin türü.|

## <a name="remarks"></a>Açıklamalar

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) makrosu geçirir bu sınıfı olarak `name` aşağıdaki ifadeyi parametresinde: `ALLOCATOR_DECL(CACHE_CHUNKLIST, SYNC_DEFAULT, allocator_chunklist);`

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<allocators >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators >](../standard-library/allocators-header.md)<br/>
