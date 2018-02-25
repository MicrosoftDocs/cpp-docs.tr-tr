---
title: "&lt;atomik&gt; numaralandırmaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atomic/std::memory_order
ms.assetid: cd3a81c5-a19e-448f-952a-c34c717f21a9
caps.latest.revision: 
helpviewer_keywords:
- std::memory_order
manager: ghogen
ms.openlocfilehash: 5f5c286375699d233d1bc9dadd3f44992309fa0a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltatomicgt-enums"></a>&lt;atomik&gt; numaralandırmaları
  
##  <a name="memory_order_enum"></a>  memory_order Enum  
 Bellek konumlarını eşitleme işlemleri için simgesel adları sağlar. Bu işlemlerin nasıl bir iş parçacığı atamalarını başka bir programda görünür hale gelmiştir etkiler.  
  
```
typedef enum memory_order {
    memory_order_relaxed,
    memory_order_consume,
    memory_order_acquire,
    memory_order_release,
    memory_order_acq_rel,
    memory_order_seq_cst,
} memory_order;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
|||  
|-|-|  
|`memory_order_relaxed`|Sıralamaya gerekli.|  
|`memory_order_consume`|Yükleme işlemi, bellek konumuna Tüket işleminde olarak görev yapar.|  
|`memory_order_acquire`|Yükleme işlemi, bellek konumuna edinme işlem görür.|  
|`memory_order_release`|Bir depolama işlemi, bellek konumuna üzerinde bir yayın işlemi olarak görev yapar.|  
|`memory_order_acq_rel`|Birleştirir `memory_order_acquire` ve `memory_order_release`.|  
|`memory_order_seq_cst`|Birleştirir `memory_order_acquire` ve `memory_order_release`. Olarak işaretlenmiş bellek erişimleri `memory_order_seq_cst` sırayla tutarlı olmalıdır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<atomik >](../standard-library/atomic.md)



