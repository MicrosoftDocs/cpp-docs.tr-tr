---
title: '&lt;atomik&gt; sabit listeleri'
ms.date: 11/04/2016
f1_keywords:
- atomic/std::memory_order
ms.assetid: cd3a81c5-a19e-448f-952a-c34c717f21a9
helpviewer_keywords:
- std::memory_order
ms.openlocfilehash: 03247f6abd01b00fbbed3b33016cd4a12d8a13f8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543761"
---
# <a name="ltatomicgt-enums"></a>&lt;atomik&gt; sabit listeleri

## <a name="memory_order_enum"></a>  memory_order sabit listesi

Bellek konumlarında eşitleme işlemleri için simgesel adlar sağlar. Bu işlemlerin nasıl atamaları bir iş parçacığındaki başka bir atamada görülür hale etkiler.

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
|`memory_order_relaxed`|Sıralamaya gerek yok.|
|`memory_order_consume`|Yükleme işlemi, bir bellek konumunda kullanma işlemi olarak görev yapar.|
|`memory_order_acquire`|Yükleme işlemi bellek konumunda alma işlemi olarak görev yapar.|
|`memory_order_release`|Depolama işlemi bellek konumunda bir sürüm işlemi olarak davranır.|
|`memory_order_acq_rel`|Birleştirir `memory_order_acquire` ve `memory_order_release`.|
|`memory_order_seq_cst`|Birleştirir `memory_order_acquire` ve `memory_order_release`. Olarak işaretlenmiş bellek erişimi `memory_order_seq_cst` sırayla tutarlı olmalıdır.|

## <a name="see-also"></a>Ayrıca bkz.

[\<atomik >](../standard-library/atomic.md)<br/>
