---
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
ms.openlocfilehash: a2c4681ec5252166754a45b026ea119651f18a38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371678"
---
# <a name="allocatorvariablesize-class"></a>allocator_variable_size Sınıfı

Depolama ayırmayı ve boşaltmayı türü nesneler için yöneten bir nesneyi tanımlayan *türü* kullanarak bir önbellek türü [cache_freelist](../standard-library/cache-freelist-class.md) tarafından yönetilen bir uzunlukta [max_variable_size](../standard-library/max-variable-size-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class allocator_variable_size;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Tür*|Ayırıcı tarafından ayrılan öğelerin türü.|

## <a name="remarks"></a>Açıklamalar

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) makrosu bu sınıfı olarak geçirir *adı* aşağıdaki deyim parametresi: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_variable_size), SYNC_DEFAULT, allocator_variable_size);`

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ayırıcılar >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
