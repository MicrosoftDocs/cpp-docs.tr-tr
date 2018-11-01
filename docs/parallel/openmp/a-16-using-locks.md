---
title: A.16   Kilitleri Kullanma
ms.date: 11/04/2016
ms.assetid: 873bf32b-6cfe-4ce1-b994-bef80b50f399
ms.openlocfilehash: 6afb94660acdc79ea5a7eb61d3bf7e21fd70d751
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458990"
---
# <a name="a16---using-locks"></a>A.16   Kilitleri Kullanma

Aşağıdaki örnekte, (için [bölümü 3.2](../../parallel/openmp/3-2-lock-functions.md) sayfasında 41) kilit işlevleri bağımsız değişken türü olması gerektiğini unutmayın `omp_lock_t`, ve onu temizlemek için gerek yoktur.  Kilit işlevleri ilk kritik bölüm girişi beklenirken boşta olması, ancak ikinci girişe beklenirken diğer işleri yapmak için iş parçacığı neden.  `omp_set_lock` İşlevi blokları, ancak `omp_test_lock` işlevi yok, iş yapılması skip() içinde izin verme.

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