---
title: A.31 iş parçacığı kilit işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 3ad89eb8-076c-405a-be5e-88d3d707a832
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: efac1091b2245b9368451e8b5148bbfe478410f4
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690448"
---
# <a name="a31---thread-safe-lock-functions"></a>A.31   İş Parçacığı Güvenli Kilit İşlevleri
Aşağıdaki C++ örneğinde kilitleri paralel bir bölgede bir dizi kullanarak başlatmak gösterilmiştir `omp_init_lock` ([bölüm 3.2.1](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) sayfasında 42).  
  
## <a name="example"></a>Örnek  
  
### <a name="code"></a>Kod  
  
```  
// A_13_omp_init_lock.cpp  
// compile with: /openmp  
#include <omp.h>  
  
omp_lock_t *new_locks() {  
   int i;  
   omp_lock_t *lock = new omp_lock_t[1000];  
   #pragma omp parallel for private(i)  
   for (i = 0 ; i < 1000 ; i++)  
      omp_init_lock(&lock[i]);  
  
   return lock;  
}  
  
int main () {}  
```