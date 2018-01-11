---
title: firstprivate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: firstprivate
dev_langs: C++
helpviewer_keywords: firstprivate OpenMP clause
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8c7d4a5ba23e343f7858bf3320ed05ebce84f1c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="firstprivate"></a>firstprivate
Paralel yapı önce mevcut olduğundan her iş parçacığı bir değişken örneğini olmalıdır ve değişkeni değişken değeri ile başlatılmış olduğunu belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
firstprivate(var)  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`var`|Paralel yapı önce mevcut olduğundan ve her iş parçacığı örnekleri için değişken değişken değerle başlatılır. Birden fazla değişken belirtilirse, değişken adları virgül ile ayırın.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="remarks"></a>Açıklamalar  
 `firstprivate`Aşağıdaki yönergeleri için geçerlidir:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [bölümler](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [single](../../../parallel/openmp/reference/single.md)  
  
 Daha fazla bilgi için bkz: [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md).  
  
## <a name="example"></a>Örnek  
 Kullanarak bir örnek için `firstprivate`, örnekte bkz [özel](../../../parallel/openmp/reference/private-openmp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan Tümceler](../../../parallel/openmp/reference/openmp-clauses.md)