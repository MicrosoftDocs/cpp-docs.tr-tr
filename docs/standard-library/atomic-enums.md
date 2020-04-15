---
title: '&lt;atomik&gt; enumlar'
ms.date: 11/04/2016
f1_keywords:
- atomic/std::memory_order
ms.assetid: cd3a81c5-a19e-448f-952a-c34c717f21a9
helpviewer_keywords:
- std::memory_order
ms.openlocfilehash: f41c5b238f74e85bc18e9ff5c3aa6a0050fe27e1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376918"
---
# <a name="ltatomicgt-enums"></a>&lt;atomik&gt; enumlar

## <a name="memory_order-enum"></a><a name="memory_order_enum"></a>memory_order Enum

Bellek konumlarında eşitleme işlemleri için sembolik adlar sağlar. Bu işlemler, bir iş parçacığındaki atamaların diğerinde nasıl görünür hale geldiğini etkiler.

```cpp
typedef enum memory_order {
    memory_order_relaxed,
    memory_order_consume,
    memory_order_acquire,
    memory_order_release,
    memory_order_acq_rel,
    memory_order_seq_cst,
} memory_order;
```

### <a name="enumeration-members"></a>Numaralandırma üyeleri

|||
|-|-|
|`memory_order_relaxed`|Sipariş gerektirmez.|
|`memory_order_consume`|Yükleme işlemi, bellek konumunda bir tüketme işlemi görevi görür.|
|`memory_order_acquire`|Yükleme işlemi, bellek konumunda edinme işlemi görevi görür.|
|`memory_order_release`|Bir mağaza işlemi bellek konumunda bir sürüm işlemi olarak hareket eder.|
|`memory_order_acq_rel`|Birleştirir `memory_order_acquire` `memory_order_release`ve .|
|`memory_order_seq_cst`|Birleştirir `memory_order_acquire` `memory_order_release`ve . Sırayla tutarlı olması `memory_order_seq_cst` gerektiği olarak işaretlenmiş bellek erişimleri.|

## <a name="see-also"></a>Ayrıca bkz.

[\<atomik>](../standard-library/atomic.md)
