---
description: 'Hakkında daha fazla bilgi edinin: memory_resource sınıfı'
title: memory_resource sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory_resource/std::memory_resource
helpviewer_keywords:
- std::memory_resource
ms.openlocfilehash: 5b4cf5171f9dd062374171d50daaf71c61523d67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183938"
---
# <a name="memory_resource-class"></a>memory_resource sınıfı

## <a name="syntax"></a>Syntax

```cpp
class memory_resource {
    static constexpr size_t max_align = alignof(max_align_t); // exposition only

    virtual ~memory_resource();
    void* allocate(size_t bytes, size_t alignment = max_align);
    void deallocate(void* p, size_t bytes, size_t alignment = max_align);
    bool is_equal(const memory_resource& other) const noexcept;
};
```
