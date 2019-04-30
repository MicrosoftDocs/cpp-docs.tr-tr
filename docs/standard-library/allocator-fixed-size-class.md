---
title: allocator_fixed_size Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_fixed_size
- allocators/stdext::allocator_fixed_size
- stdext::allocators::allocator_fixed_size
helpviewer_keywords:
- stdext::allocators [C++], allocator_fixed_size
- stdext::allocator_fixed_size
ms.assetid: 138f3ef8-b0b3-49c3-9486-58f2213c172f
ms.openlocfilehash: d050a127fe3e62bf8f4eb4ce56fe25e33f88c041
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411038"
---
# <a name="allocatorfixedsize-class"></a>allocator_fixed_size Sınıfı

Depolama ayırmayı ve boşaltmayı türü nesneler için yöneten bir nesneyi tanımlayan *türü* kullanarak bir önbellek türü [cache_freelist](../standard-library/cache-freelist-class.md) tarafından yönetilen bir uzunlukta [max_fixed_size](../standard-library/max-fixed-size-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class allocator_fixed_size;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Tür*|Ayırıcı tarafından ayrılan öğelerin türü.|

## <a name="remarks"></a>Açıklamalar

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) makrosu bu sınıfı olarak geçirir *adı* aşağıdaki deyim parametresi: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_fixed_size<10>), SYNC_DEFAULT, allocator_fixed_size);`

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ayırıcılar >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
