---
title: Kilitleri kullanarak A.16 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 873bf32b-6cfe-4ce1-b994-bef80b50f399
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db55a8e562e0b1ae72038128a035d2cdabcd3e86
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="a16---using-locks"></a>A.16   Kilitleri Kullanma
Aşağıdaki örnekte, (için [bölüm 3.2](../../parallel/openmp/3-2-lock-functions.md) sayfasında 41) kilit işlevleri için bağımsız değişken türü olmalıdır Not `omp_lock_t`, ve bunu temizlemek için gerek yoktur.  Kilit işlevleri ilk kritik bölüm girişe beklenirken boşta ancak ikinci giriş için beklenirken diğer iş yapmak için iş parçacığı neden.  `omp_set_lock` İşlevi blokları, ancak `omp_test_lock` işlevi desteklemez, iş yapılması skip() içinde izin verme.  
  
## <a name="example"></a>Örnek  
  
### <a name="code"></a>Kod  
  
```  
// omp_using_locks.c  
// compile with: /openmp /c  
#include <stdio.h>  
#include <omp.h>  
  
void work(int);  
void skip(int);  
  
int main() {  
   omp_lock_t lck;  
   int id;  
  
   omp_init_lock(&lck);  
   #pragma omp parallel shared(lck) private(id)  
   {  
      id = omp_get_thread_num();  
  
      omp_set_lock(&lck);  
      printf_s("My thread id is %d.\n", id);  
  
      // only one thread at a time can execute this printf  
      omp_unset_lock(&lck);  
  
      while (! omp_test_lock(&lck)) {  
         skip(id);   // we do not yet have the lock,  
                     // so we must do something else   
      }  
      work(id);     // we now have the lock  
                    // and can do the work   
      omp_unset_lock(&lck);  
   }  
   omp_destroy_lock(&lck);  
}  
```