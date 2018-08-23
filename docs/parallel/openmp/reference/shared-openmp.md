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
ms.openlocfilehash: b2bc1a0bbf56623feccd4d3bd96f1e719e192d48
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2018
ms.locfileid: "42464577"
---
# <a name="shared-openmp"></a>shared (OpenMP)
Bir veya daha fazla değişkenlerini tüm iş parçacıkları arasında paylaşılan olduğunu belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
shared(var)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 `var`  
 Paylaşmak için bir veya daha fazla değişken. Birden fazla değişken belirtilirse, değişken adları virgül ile ayırın.  
  
## <a name="remarks"></a>Açıklamalar  
 Değişkenleri iş parçacıkları arasında paylaşmak için başka bir yöntem, [copyprivate](../../../parallel/openmp/reference/copyprivate.md) yan tümcesi.  
  
 `shared` Aşağıdaki yönergeleri için geçerlidir:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [Bölümleri](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Daha fazla bilgi için [paylaşılan 2.7.2.4](../../../parallel/openmp/2-7-2-4-shared.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [özel](../../../parallel/openmp/reference/private-openmp.md) kullanma örneği için `shared`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan Tümceler](../../../parallel/openmp/reference/openmp-clauses.md)