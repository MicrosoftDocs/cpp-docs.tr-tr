---
title: memory_resource sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory_resource/std::memory_resource
helpviewer_keywords:
- std::memory_resource
ms.openlocfilehash: 637bc6a78308fcbdce6af96e65e41bde1bb84c84
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68267945"
---
# <a name="memoryresource-class"></a>memory_resource sınıfı

## <a name="syntax"></a>Sözdizimi

```cpp
class memory_resource {
    static constexpr size_t max_align = alignof(max_align_t); // exposition only

    virtual ~memory_resource();
    void* allocate(size_t bytes, size_t alignment = max_align);
    void deallocate(void* p, size_t bytes, size_t alignment = max_align);
    bool is_equal(const memory_resource& other) const noexcept;
};
```
