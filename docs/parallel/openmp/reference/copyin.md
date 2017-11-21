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
ms.openlocfilehash: af833219039a03e7e403f7e3cd10210057f3abfa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
-   [Paralel](../../../parallel/openmp/reference/parallel.md)  
  
-   [için](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [bölümler](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Daha fazla bilgi için bkz: [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [threadprivate](../../../parallel/openmp/reference/threadprivate.md) kullanma örneği için `copyin`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan tümceleri](../../../parallel/openmp/reference/openmp-clauses.md)