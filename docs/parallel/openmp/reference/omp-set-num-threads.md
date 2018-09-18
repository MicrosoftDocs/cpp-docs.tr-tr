---
title: omp_set_num_threads | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_num_threads
dev_langs:
- C++
helpviewer_keywords:
- omp_set_num_threads OpenMP function
ms.assetid: dae0bf3f-cd7a-4413-89de-6149ac1f4fa7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 849bdade5c6abfad07ebed262fb367487d3e1415
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047895"
---
# <a name="ompsetnumthreads"></a>omp_set_num_threads
İş parçacığı sayısı tarafından geçersiz kılınmadığı sürece sonraki paralel bölgelerde ayarlar bir [num_threads](../../../parallel/openmp/reference/num-threads.md) yan tümcesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void omp_set_num_threads(  
   int num_threads  
);  
```  
  
### <a name="parameters"></a>Parametreler
  
*num_threads*<br/>
Paralel bölgenin içinde iş parçacığı sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için [3.1.1 omp_set_num_threads işlevi](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md) kullanma örneği için `omp_set_num_threads`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../../parallel/openmp/reference/openmp-functions.md)