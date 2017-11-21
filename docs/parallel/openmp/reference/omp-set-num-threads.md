---
title: omp_set_num_threads | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_set_num_threads
dev_langs: C++
helpviewer_keywords: omp_set_num_threads OpenMP function
ms.assetid: dae0bf3f-cd7a-4413-89de-6149ac1f4fa7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 66fc3984342b75b2fed35ed9a5c58d0848d41b2c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ompsetnumthreads"></a>omp_set_num_threads
İş parçacığı sayısını sonraki paralel bölgelerde tarafından geçersiz kılınmadığı sürece ayarlar bir [num_threads](../../../parallel/openmp/reference/num-threads.md) yan tümcesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void omp_set_num_threads(  
   int num_threads  
);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 `num_threads`  
 Paralel bölge içindeki iş parçacığı sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [3.1.1 omp_set_num_threads işlevi](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md) kullanma örneği için `omp_set_num_threads`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../../parallel/openmp/reference/openmp-functions.md)