---
description: 'Hakkında daha fazla bilgi edinin: allocator_variable_size sınıfı'
title: allocator_variable_size Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_variable_size
- allocators/stdext::allocators::allocator_variable_size
- stdext::allocators::allocator_variable_size
helpviewer_keywords:
- stdext::allocator_variable_size
- stdext::allocators [C++], allocator_variable_size
ms.assetid: c3aa4105-ae45-4385-bbbe-9f23060478cb
ms.openlocfilehash: 9a6f9b6316daefbf436d4718a92312ceb8d55aa4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163541"
---
# <a name="allocator_variable_size-class"></a>allocator_variable_size Sınıfı

[Max_variable_size](max-variable-size-class.md)tarafından yönetilen uzunluğa sahip [cache_freelist](cache-freelist-class.md) *türünde bir önbellek kullanarak türünde* nesneler için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class allocator_variable_size;
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Ayırıcı tarafından ayrılan öğelerin türü.

## <a name="remarks"></a>Açıklamalar

[ALLOCATOR_DECL](allocators-functions.md#allocator_decl) makro bu sınıfı aşağıdaki deyimdeki *Name* parametresi olarak geçirir:`ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_variable_size), SYNC_DEFAULT, allocator_variable_size);`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<allocators>

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](allocators-header.md)
