---
title: "(OpenMP) paylaşılan | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Shared
dev_langs: C++
helpviewer_keywords: shared OpenMP clause
ms.assetid: 7887dc95-67a2-462f-a3a2-8e0632bf5d04
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 966584b3a294551560bb88430a2424f353a1e3b2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
 `shared`Aşağıdaki yönergeleri için geçerlidir:  
  
-   [için](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Paralel](../../../parallel/openmp/reference/parallel.md)  
  
-   [bölümler](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Daha fazla bilgi için bkz: [paylaşılan 2.7.2.4](../../../parallel/openmp/2-7-2-4-shared.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [özel](../../../parallel/openmp/reference/private-openmp.md) kullanma örneği için `shared`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan tümceleri](../../../parallel/openmp/reference/openmp-clauses.md)