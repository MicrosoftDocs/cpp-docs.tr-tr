---
title: unsynchonized_pool_resource sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory_resource/std::unsynchronized_pool_resource
helpviewer_keywords:
- std::unsynchronized_pool_resource
ms.openlocfilehash: 3bee36e328bb9342b009c6c021dbfbfa5d189fe9
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268068"
---
# <a name="unsynchronizedpoolresource-class"></a>unsynchronized_pool_resource sınıfı

## <a name="syntax"></a>Sözdizimi

```cpp
class unsynchronized_pool_resource : public memory_resource {
    unsynchronized_pool_resource(const pool_options& opts, memory_resource* upstream);
    unsynchronized_pool_resource()
        : unsynchronized_pool_resource(pool_options(), get_default_resource()) {}
    explicit unsynchronized_pool_resource(memory_resource* upstream)
        : unsynchronized_pool_resource(pool_options(), upstream) {}
    explicit unsynchronized_pool_resource(const pool_options& opts)
        : unsynchronized_pool_resource(opts, get_default_resource()) {}
    unsynchronized_pool_resource(const unsynchronized_pool_resource&) = delete;
    virtual ~unsynchronized_pool_resource();
    unsynchronized_pool_resource&
        operator=(const unsynchronized_pool_resource&) = delete;
    void release();
    memory_resource *upstream_resource() const;
    pool_options options() const;
};
```
