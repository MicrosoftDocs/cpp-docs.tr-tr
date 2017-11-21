---
title: Atomik | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: atomic
dev_langs: C++
helpviewer_keywords: atomic OpenMP directive
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 92804b2bdcc243bde6e536004cda73d7f5087b1d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="atomic"></a>atomic
Belirleyen bir bellek konumundan otomatik olarak güncelleştirilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma omp atomic  
   expression  
```  
  
#### <a name="parameters"></a>Parametreler  
 `expression`  
 Birden çok yazma karşı korumak istediğiniz bellek konumu lvalue içeren ifade. OpenMP belirtimi yasal ifade formları hakkında daha fazla bilgi için bkz.  
  
## <a name="remarks"></a>Açıklamalar  
 `atomic` Yönergesi yok OpenMP yan tümceleri destekler.  
  
 Daha fazla bilgi için bkz: [2.6.4 atomic oluşturmak](../../../parallel/openmp/2-6-4-atomic-construct.md).  
  
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