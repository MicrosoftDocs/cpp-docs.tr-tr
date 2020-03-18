---
title: '&lt;atomik&gt; numaralandırmalar'
ms.date: 11/04/2016
f1_keywords:
- atomic/std::memory_order
ms.assetid: cd3a81c5-a19e-448f-952a-c34c717f21a9
helpviewer_keywords:
- std::memory_order
ms.openlocfilehash: 14b816177593a9f6dade60e36676a37f724fc209
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79422012"
---
# <a name="ltatomicgt-enums"></a>&lt;atomik&gt; numaralandırmalar

## <a name="memory_order_enum"></a>memory_order numaralandırması

Bellek konumlarında eşitleme işlemleri için simgesel adlar sağlar. Bu işlemler, bir iş parçacığındaki atamaların diğerinden nasıl görünür hale geldiğini etkiler.

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

### <a name="enumeration-members"></a>Listeleme üyeleri

|||
|-|-|
|`memory_order_relaxed`|Sıralama gerekmiyor.|
|`memory_order_consume`|Yükleme işlemi bellek konumunda kullanım işlemi işlevi görür.|
|`memory_order_acquire`|Yükleme işlemi bellek konumunda bir alma işlemi işlevi görür.|
|`memory_order_release`|Bir depolama işlemi bellek konumunda bir yayın işlemi görevi görür.|
|`memory_order_acq_rel`|`memory_order_acquire` ve `memory_order_release`birleştirir.|
|`memory_order_seq_cst`|`memory_order_acquire` ve `memory_order_release`birleştirir. `memory_order_seq_cst` olarak işaretlenen bellek erişimleri sırayla tutarlı olmalıdır.|

## <a name="see-also"></a>Ayrıca bkz.

[\<atomik >](../standard-library/atomic.md)
