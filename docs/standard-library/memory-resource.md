---
title: '&lt;memory_resource&gt;'
ms.date: 04/04/2019
f1_keywords:
- <memory_resource>
helpviewer_keywords:
- memory_resource header
ms.openlocfilehash: b5957412d2beff0dc709dc71a77834f13eeacb41
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268158"
---
# <a name="ltmemoryresourcegt"></a>&lt;memory_resource&gt;

Kapsayıcı Şablon sınıfı memory_resource ve kendi destek şablonları tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <memory_resource>
```

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator!=](../standard-library/memory-resource-operators.md#op_neq)|İşlecin sol tarafındaki memory_resource nesne işlecin sağ tarafındaki memory_resource nesneye eşit olup olmadığını sınar.|
|[operator==](../standard-library/memory-resource-operators.md#op_eq_eq)|İşlecin sol tarafındaki memory_resource nesnesinin işlecin sağ tarafındaki memory_resource nesneye eşit olup olmadığını sınar.|

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

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
