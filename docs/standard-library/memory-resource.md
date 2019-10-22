---
title: '&lt;memory_resource &gt;'
ms.date: 04/04/2019
f1_keywords:
- <memory_resource>
helpviewer_keywords:
- memory_resource header
ms.openlocfilehash: 752396bb06b292ce29b7c6cd292287955b6066a7
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687707"
---
# <a name="ltmemory_resourcegt"></a>&lt;memory_resource &gt;

Kapsayıcı sınıfı şablonu memory_resource ve destekleyici şablonlarını tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <memory_resource>
```

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator!=](../standard-library/memory-resource-operators.md#op_neq)|İşlecin sol tarafındaki memory_resource nesnesinin, sağ taraftaki memory_resource nesnesine eşit olup olmadığını sınar.|
|[işleç = =](../standard-library/memory-resource-operators.md#op_eq_eq)|İşlecin sol tarafındaki memory_resource nesnesinin, sağ taraftaki memory_resource nesnesine eşit olup olmadığını sınar.|

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

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md) \
[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
