---
title: omp_set_nested | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_set_nested OpenMP function
ms.assetid: fa1cb08c-7b8b-42c9-8654-2c33dcffb5b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc3506c35dca469febafe21509064abc1726d633
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116906"
---
# <a name="ompsetnested"></a>omp_set_nested
İç içe geçmiş paralellik etkinleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void omp_set_nested(  
   int val  
);  
```  
  
### <a name="parameters"></a>Parametreler
  
*VAL*<br/>
Sıfır olmayan, iç içe geçmiş paralellik sağlar. Sıfır ise, iç içe geçmiş paralellik devre dışı bırakır.  
  
## <a name="remarks"></a>Açıklamalar  
 İç içe geçmiş OMP paralellik açılabilir ile `omp_set_nested`, ayarlayarak [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md) ortam değişkeni.  
  
 Ayarı `omp_set_nested` ayarını geçersiz kılar `OMP_NESTED` ortam değişkeni.  
  
 Paralel bölgeleri iç içe olduğunda iş parçacığı sayısı katlanarak artar çünkü ortam değişkenini etkin olduğunda, aksi takdirde işletimsel bir programı bozabilir.  Örneğin genel bir işlev recurses 6 kez 4'e ayarlayın OMP iş parçacığı sayısı ile 4.096 (6'ın gücünü 4) gerektiren iş parçacıkları, işlemci sayısını iş parçacığı sayısını aşarsa, uygulamanızın performansını bozar. Bunun tek istisnası, g/ç uygulamaları bağlı olacaktır.  
  
 Kullanım [omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md) geçerli ayarını görüntülemek için `omp_set_nested`.  
  
 Daha fazla bilgi için [3.1.9 omp_set_nested işlevi](../../../parallel/openmp/3-1-9-omp-set-nested-function.md).  
  
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