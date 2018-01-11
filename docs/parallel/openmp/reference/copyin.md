---
title: copyin | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: copyin
dev_langs: C++
helpviewer_keywords: copyin OpenMP clause
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3190c1f6914ae8ea24b968a8cf286de1867938cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="copyin"></a>copyin
Ana iş parçacığının değeri erişmek iş parçacığı sağlayan bir [threadprivate](../../../parallel/openmp/reference/threadprivate.md) değişkeni.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
copyin(var)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 `var`  
 `threadprivate` Paralel yapı önce mevcut olduğundan, ana iş parçacığında değişkeninin değeri başlatılacağı değişkeni.  
  
## <a name="remarks"></a>Açıklamalar  
 `copyin`Aşağıdaki yönergeleri için geçerlidir:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [bölümler](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Daha fazla bilgi için bkz: [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [threadprivate](../../../parallel/openmp/reference/threadprivate.md) kullanma örneği için `copyin`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan Tümceler](../../../parallel/openmp/reference/openmp-clauses.md)