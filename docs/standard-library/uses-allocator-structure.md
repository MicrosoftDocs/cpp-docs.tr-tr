---
title: uses_allocator Yapısı
ms.date: 11/04/2016
f1_keywords:
- future/std::uses_allocator
ms.assetid: c418f002-62e9-4806-b70c-41c663cae583
ms.openlocfilehash: 2cee318832caf70e781fa9e3490a752b097a5fbb
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245683"
---
# <a name="usesallocator-structure"></a>uses_allocator Yapısı

Uzmanlıklar, her zaman doğru tutun.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty, class Alloc>
struct uses_allocator<promise<Ty>, Alloc> : true_type;
template <class Ty, class Alloc>
struct uses_allocator<packaged_task<Ty>, Alloc> : true_type;
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<gelecek >

**Namespace:** std

## <a name="specializations"></a>Uzmanlıklar

### <a name="tuple"></a> \<Tanımlama grubu >

```cpp
template <class... Types, class Alloc>
struct uses_allocator<tuple<Types...>, Alloc>;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<gelecek >](../standard-library/future.md)<br/>
