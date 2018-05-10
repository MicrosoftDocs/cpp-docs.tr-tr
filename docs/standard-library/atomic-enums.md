---
title: '&lt;atomik&gt; numaralandırmaları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- atomic/std::memory_order
ms.assetid: cd3a81c5-a19e-448f-952a-c34c717f21a9
helpviewer_keywords:
- std::memory_order
ms.openlocfilehash: c30e7ca78533b0b4c2a4eb49bd99bd13483d2b8d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="ltatomicgt-enums"></a>&lt;atomik&gt; numaralandırmaları

## <a name="memory_order_enum"></a>  memory_order Enum

Bellek konumlarını eşitleme işlemleri için simgesel adları sağlar. Bu işlemlerin nasıl bir iş parçacığı atamalarını başka bir programda görünür hale gelmiştir etkiler.

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
|`memory_order_relaxed`|Sıralamaya gerekli.|
|`memory_order_consume`|Yükleme işlemi, bellek konumuna Tüket işleminde olarak görev yapar.|
|`memory_order_acquire`|Yükleme işlemi, bellek konumuna edinme işlem görür.|
|`memory_order_release`|Bir depolama işlemi, bellek konumuna üzerinde bir yayın işlemi olarak görev yapar.|
|`memory_order_acq_rel`|Birleştirir `memory_order_acquire` ve `memory_order_release`.|
|`memory_order_seq_cst`|Birleştirir `memory_order_acquire` ve `memory_order_release`. Olarak işaretlenmiş bellek erişimleri `memory_order_seq_cst` sırayla tutarlı olmalıdır.|

## <a name="see-also"></a>Ayrıca bkz.

[\<atomik >](../standard-library/atomic.md)<br/>
