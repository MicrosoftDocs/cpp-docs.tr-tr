---
title: omp_set_dynamic | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_dynamic
dev_langs:
- C++
helpviewer_keywords:
- omp_set_dynamic OpenMP function
ms.assetid: 3845faf2-a0ca-45a5-ae70-2a7a6164f1e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3e8ac574ce304238affbab41acc415e1d8de697
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026913"
---
# <a name="ompsetdynamic"></a>omp_set_dynamic
Sonraki bir paralel bölgenin içinde kullanılabilir iş parçacığı sayısını çalışma zamanı tarafından düzenlenip düzenlenmediğini gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void omp_set_dynamic(  
   int val  
);  
```  
  
### <a name="parameters"></a>Parametreler
  
*VAL*<br/>
Çalışma zamanı tarafından ayarlanabilir izleyen bir paralel bölgenin içinde kullanılabilir iş parçacığı sayısını belirten bir değer.  Sıfır olmayan, çalışma zamanı iş parçacığı sayısı sıfır ise ayarlayabilirsiniz, çalışma zamanı dinamik olarak iş parçacığı sayısını ayarlar değil.  
  
## <a name="remarks"></a>Açıklamalar  
 İş parçacığı sayısı ayarlanan değer hiçbir zaman aşacak [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) ya da [OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md).  
  
 Kullanım [omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md) geçerli ayarını görüntülemek için `omp_set_dynamic`.  
  
 Ayarı `omp_set_dynamic` ayarını geçersiz kılar [omp_dynamıc](../../../parallel/openmp/reference/omp-dynamic.md) ortam değişkeni.  
  
 Daha fazla bilgi için [3.1.7 omp_set_dynamic işlevi](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).  
  
## <a name="example"></a>Örnek  
  
```  
// omp_set_dynamic.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main()   
{  
    omp_set_dynamic(9);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_dynamic( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_dynamic( ));  
        }  
}  
```  
  
```Output  
1  
1  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../../parallel/openmp/reference/openmp-functions.md)