---
title: '&lt;Atomik &gt; numaralandırmalar'
ms.date: 11/04/2016
f1_keywords:
- atomic/std::memory_order
ms.assetid: cd3a81c5-a19e-448f-952a-c34c717f21a9
helpviewer_keywords:
- std::memory_order
ms.openlocfilehash: d8a4e9196e27933c75a32c256114e968b55678a6
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834901"
---
# <a name="ltatomicgt-enums"></a>&lt;Atomik &gt; numaralandırmalar

## <a name="memory_order-enum"></a><a name="memory_order_enum"></a> memory_order numaralandırması

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

|Ad|Açıklama|
|-|-|
|`memory_order_relaxed`|Sıralama gerekmiyor.|
|`memory_order_consume`|Yükleme işlemi bellek konumunda kullanım işlemi işlevi görür.|
|`memory_order_acquire`|Yükleme işlemi bellek konumunda bir alma işlemi işlevi görür.|
|`memory_order_release`|Bir depolama işlemi bellek konumunda bir yayın işlemi görevi görür.|
|`memory_order_acq_rel`|`memory_order_acquire`Ve birleştirir `memory_order_release` .|
|`memory_order_seq_cst`|`memory_order_acquire`Ve birleştirir `memory_order_release` . Olarak işaretlenen bellek erişimleri sıralı olarak `memory_order_seq_cst` tutarlı olmalıdır.|

## <a name="see-also"></a>Ayrıca bkz.

[\<atomic>](../standard-library/atomic.md)
