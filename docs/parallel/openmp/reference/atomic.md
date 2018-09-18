---
title: Atomik | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- atomic
dev_langs:
- C++
helpviewer_keywords:
- atomic OpenMP directive
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7e9e9ecad2f6ea53e2f922799340eee47dd4a7e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037495"
---
# <a name="atomic"></a>atomic
Belirten bir bellek konumuna atomik olarak güncelleştirilecek.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma omp atomic  
   expression  
```  
  
#### <a name="parameters"></a>Parametreler  
*İfade*<br/>
Bellek konumu lvalue içeren deyimi birden fazla yazma karşı korumak istiyorsunuz. OpenMP belirtiminin yasal ifade biçimleri hakkında daha fazla bilgi için bkz.  
  
## <a name="remarks"></a>Açıklamalar  
 `atomic` Yönergesi yok OpenMP yan tümceleri destekler.  
  
 Daha fazla bilgi için [2.6.4 atomic oluşturmak](../../../parallel/openmp/2-6-4-atomic-construct.md).  
  
## <a name="example"></a>Örnek  
  
```  
// omp_atomic.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
#define MAX 10  
  
int main() {  
   int count = 0;  
   #pragma omp parallel num_threads(MAX)  
   {  
      #pragma omp atomic  
      count++;  
   }  
   printf_s("Number of threads: %d\n", count);  
}  
```  
  
```Output  
Number of threads: 10  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)