---
title: '&lt;memory_resource&gt;'
ms.date: 04/04/2019
f1_keywords:
- <memory_resource>
helpviewer_keywords:
- memory_resource header
ms.openlocfilehash: d4b25c6ee575191f1e17b0202d33298e2e9e67f0
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451898"
---
# <a name="ltmemoryresourcegt"></a>&lt;memory_resource&gt;

Kapsayıcı şablon sınıfı memory_resource ve destekleyici şablonlarını tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <memory_resource>
```

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator!=](../standard-library/memory-resource-operators.md#op_neq)|İşlecin sol tarafındaki memory_resource nesnesinin, sağ taraftaki memory_resource nesnesine eşit olup olmadığını sınar.|
|[operator==](../standard-library/memory-resource-operators.md#op_eq_eq)|İşlecin sol tarafındaki memory_resource nesnesinin, sağ taraftaki memory_resource nesnesine eşit olup olmadığını sınar.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|||
|-|-|
|[polymorphic_allocator](../standard-library/memory-resource-functions.md#poly_alloc)||

### <a name="functions"></a>İşlevler

|||
|-|-|
|[get_default_resource](../standard-library/memory-resource-functions.md#get_default)||
|[new_delete_resource](../standard-library/memory-resource-functions.md#new_delete)||
|[null_memory_resource](../standard-library/memory-resource-functions.md#null_memory)||
|[set_default_resource](../standard-library/memory-resource-functions.md#set_default)||

### <a name="classes-and-structs"></a>Sınıflar ve Yapılar

|||
|-|-|
|[memory_resource sınıfı](../standard-library/memory-resource-class.md)||
|[monotonic_buffer_resource sınıfı](../standard-library/monotonic-buffer-resource-class.md)||
|[pool_options yapısı](../standard-library/pool-options-structure.md)||
|[synchronized_pool_resource sınıfı](../standard-library/synchronized-pool-resource-class.md)||
|[unsynchronized_pool_resource sınıfı](../standard-library/unsynchronized-pool-resource-class.md)||

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
