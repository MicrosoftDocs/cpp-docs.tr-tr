---
title: monotonic_buffer_resource sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory_resource/std::monotonic_buffer_resource
helpviewer_keywords:
- std::monotonic_buffer_resource
ms.openlocfilehash: 019d9ce7328ccc7bd65461fb966ac5dcb915209e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268152"
---
# <a name="monotonicbufferresource-class"></a>monotonic_buffer_resource sınıfı

## <a name="syntax"></a>Sözdizimi

```cpp
class monotonic_buffer_resource : public memory_resource {
    memory_resource *upstream_rsrc; // exposition only
    void *current_buffer; // exposition only
    size_t next_buffer_size; // exposition only

    explicit monotonic_buffer_resource(memory_resource *upstream);
    monotonic_buffer_resource(size_t initial_size, memory_resource *upstream);
    monotonic_buffer_resource(void *buffer, size_t buffer_size, memory_resource *upstream);
    monotonic_buffer_resource()
        : monotonic_buffer_resource(get_default_resource()) {}
    explicit monotonic_buffer_resource(size_t initial_size)
        : monotonic_buffer_resource(initial_size, get_default_resource()) {}
    monotonic_buffer_resource(void *buffer, size_t buffer_size)
        : monotonic_buffer_resource(buffer, buffer_size, get_default_resource()) {}
    monotonic_buffer_resource(const monotonic_buffer_resource&) = delete;
    virtual ~monotonic_buffer_resource();
    monotonic_buffer_resource
        operator=(const monotonic_buffer_resource&) = delete;
    void release();
    memory_resource* upstream_resource() const;
};
```
