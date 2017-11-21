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
ms.openlocfilehash: 0645eee74ab162c444531c141b297665653907b8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
-   [için](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Paralel](../../../parallel/openmp/reference/parallel.md)  
  
-   [bölümler](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [tek](../../../parallel/openmp/reference/single.md)  
  
 Daha fazla bilgi için bkz: [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md).  
  
## <a name="example"></a>Örnek  
 Kullanarak bir örnek için `firstprivate`, örnekte bkz [özel](../../../parallel/openmp/reference/private-openmp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan tümceleri](../../../parallel/openmp/reference/openmp-clauses.md)