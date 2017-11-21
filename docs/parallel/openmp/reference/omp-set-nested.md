---
title: omp_set_nested | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_set_nested
dev_langs: C++
helpviewer_keywords: omp_set_nested OpenMP function
ms.assetid: fa1cb08c-7b8b-42c9-8654-2c33dcffb5b6
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3b0d04a0eb9813a3829b0f435972c7922bf77d07
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ompsetnested"></a>omp_set_nested
İç içe geçmiş paralellik etkinleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void omp_set_nested(  
   int val  
);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 `val`  
 Sıfır olmayan varsa, iç içe geçmiş paralellik etkinleştirir. Sıfır ise, iç içe geçmiş paralellik devre dışı bırakır.  
  
## <a name="remarks"></a>Açıklamalar  
 İç içe geçmiş OMP paralellik açılabilir ile `omp_set_nested`, veya ayarlayarak [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md) ortam değişkeni.  
  
 İçin ayar `omp_set_nested` ayarını geçersiz kılar `OMP_NESTED` ortam değişkeni.  
  
 İş parçacığı sayısını katlanarak paralel bölgeler iç içe geçme artırırken çünkü ortam değişkeni etkinleştirildiğinde, aksi takdirde işlem bir program bozulabilir.  Örneğin recurses 6 kereye ile 4'e ayarlayın OMP iş parçacığı sayısını 4.096 (6 gücünü 4) gerektiren bir işlev genel iş parçacıkları, iş parçacığı sayısı işlemci sayısını aşarsa, uygulamanızın performansını bozar. Bunun tek istisnası, g/ç uygulamaları bağlı olacaktır.  
  
 Kullanım [omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md) geçerli ayarını görüntülemek için `omp_set_nested`.  
  
 Daha fazla bilgi için bkz: [3.1.9 omp_set_nested işlevi](../../../parallel/openmp/3-1-9-omp-set-nested-function.md).  
  
## <a name="example"></a>Örnek  
  
```  
// omp_set_nested.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    omp_set_nested(1);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_nested( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_nested( ));  
        }  
}  
```  
  
```Output  
1  
1  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../../parallel/openmp/reference/openmp-functions.md)