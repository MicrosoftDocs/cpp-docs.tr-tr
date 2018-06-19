---
title: (OpenMP) paylaşılan | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- Shared
dev_langs:
- C++
helpviewer_keywords:
- shared OpenMP clause
ms.assetid: 7887dc95-67a2-462f-a3a2-8e0632bf5d04
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8287f96f80748272e29b22ed5c43c364f4353b86
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691683"
---
# <a name="shared-openmp"></a>shared (OpenMP)
Bir veya daha fazla değişken tüm iş parçacıkları arasında paylaşılan olduğunu belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
shared(var)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 `var`  
 Paylaşmak için daha fazla değişken bir. Birden fazla değişken belirtilirse, değişken adları virgül ile ayırın.  
  
## <a name="remarks"></a>Açıklamalar  
 Değişkenleri iş parçacıkları arasında paylaşmak için başka bir yolu [copyprivate](../../../parallel/openmp/reference/copyprivate.md) yan tümcesi.  
  
 `shared` Aşağıdaki yönergeleri için geçerlidir:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [Bölümler](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Daha fazla bilgi için bkz: [paylaşılan 2.7.2.4](../../../parallel/openmp/2-7-2-4-shared.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [özel](../../../parallel/openmp/reference/private-openmp.md) kullanma örneği için `shared`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan Tümceler](../../../parallel/openmp/reference/openmp-clauses.md)