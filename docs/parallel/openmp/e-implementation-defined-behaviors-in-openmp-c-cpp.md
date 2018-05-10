---
title: E. Uygulama tanımlı davranış OpenMP C/C++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 598964ec6a12ac4c357efc04df78bfbe3af798a5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="e-implementation-defined-behaviors-in-openmp-cc"></a>E. Uygulama tanımlı davranış OpenMP C/C++
Bu ek olarak "uygulama tanımlı" Bu API içinde açıklanan davranışları özetler.  Her ana belirtiminde açıklamasını dön Çapraz referanslı davranıştır.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir uygulama tanımlamak ve bu gibi durumlarda davranışını belgelemek için gereklidir, ancak bu liste eksik olabilir.  
  
-   **İş parçacığı sayısı:** paralel bir bölge iş parçacığı sayısını dinamik olarak ayarlamayı devre dışıdır ve paralel bölge için istenen iş parçacığı sayısı çalışma zamanı sistem tedarik, davranışını sayıyı aşıyor karşılaştıysanız program uygulama-(sayfa 9 bakın) tanımlanır.  
  
     Visual C++'da, bir iç içe olmayan paralel bölge için 64 iş parçacığı (maksimum) sağlanır.  
  
-   **İşlemci sayısı:** gerçekten iş parçacıklarının herhangi bir anda barındıran fiziksel işlemci sayısını uygulama (sayfa 10 bakın) tanımlı.  
  
     Visual C++ ' ta bu sayının sabit değil ve işletim sistemi tarafından denetlenir.  
  
-   **Takımlar iş parçacığı oluşturma:** iç içe geçmiş bir paralel bölge yürütme iş parçacığı bir takım uygulama tanımlı sayısıdır. () Sayfa 10 bakın).  
  
     Visual C++'da, bu işletim sistemi tarafından belirlenir.  
  
-   **Schedule(Runtime):** ilgili planlama çalışma zamanına kadar ertelenmiş karar. Zamanlama türü ve öbek boyutunu ayarlayarak çalışma zamanında seçilebilir `OMP_SCHEDULE` ortam değişkeni. Bu ortam değişkeni ayarlanmamış ise, sonuçta elde edilen zamanlama uygulama-(sayfa 13 bakın) tanımlanır.  
  
     Visual C++'da, zamanlama türüdür `static` öbek boyutu.  
  
-   **Varsayılan zamanlama:** zamanlamayı tümcenin olmaması durumunda, varsayılan zamanlama uygulama-(sayfa 13 bakın) tanımlanır.  
  
     Visual C++'da, varsayılan zamanlama türüdür `static` öbek boyutu.  
  
-   **ATOMİK:** olup uygulaması tüm değiştirir uygulama tanımlı olduğu `atomic` yönergeleri ile **kritik** aynı benzersiz adı (bkz. sayfa 20) yönergeleri.  
  
     Görsel veri tarafından değiştirilirse C++ ' ta [atomik](../../parallel/openmp/reference/atomic.md) doğal hizalama üzerinde değil veya 1 veya 2 bayt ise bu özellik karşılamak uzun tüm atomik işlemleri önemli bir bölümü kullanın. Aksi takdirde, kritik bölümler kullanılmayacak.  
  
-   **omp_get_num_threads:** iş parçacığı sayısı kullanıcı tarafından açıkça ayarlanmadı, uygulama tanımlı varsayılandır (9 ' sayfasına bakın ve [bölüm 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) sayfasında 37).  
  
     Visual C++'da, iş parçacıkları varsayılan sayısını işlemci sayısına eşittir.  
  
-   **omp_set_dynamic:** uygulama tanımlı dinamik iş parçacığı ayarlaması için varsayılan değer (bkz [bölüm 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39).  
  
     Visual C++'da, varsayılan değer `FALSE`.  
  
-   **omp_set_nested:** iç içe geçmiş paralellik etkinleştirildiğinde, uygulama tanımlı paralel iç içe geçmiş bölgeler yürütmek için kullanılan iş parçacığı sayısı (bkz [bölüm 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) sayfasında 40).  
  
     Visual C++'da, iş parçacığı sayısını işletim sistemi tarafından belirlenir.  
  
-   `OMP_SCHEDULE` ortam değişkeni: uygulama tanımlı bu ortam değişkeni için varsayılan değer (bkz [bölüm 4.1](../../parallel/openmp/4-1-omp-schedule.md) sayfasında 48).  
  
     Visual C++'da, zamanlama türüdür `static` öbek boyutu.  
  
-   `OMP_NUM_THREADS` ortam değişkeni: için herhangi bir değer belirtilmişse `OMP_NUM_THREADS` ortam değişkeni veya belirtilen değer pozitif bir tamsayı değilse veya değer iş parçacıkları sistem desteklediği en fazla sayısından büyükse, kullanılacak iş parçacıklarının sayısıdır uygulama tanımlı (bkz [bölüm 4.2](../../parallel/openmp/4-2-omp-num-threads.md) sayfasında 48).  
  
     Visual C++ ' ta değerini belirttiyseniz sıfır veya daha düşük iş parçacığı sayısını işlemci sayısına eşit değil.  Değeri 64'den büyükse, iş parçacığı sayısı 64'tür.  
  
-   `OMP_DYNAMIC` ortam değişkeni: uygulama tarafından tanımlanan varsayılan değer (bkz [bölüm 4.3](../../parallel/openmp/4-3-omp-dynamic.md) sayfasında 49).  
  
     Visual C++'da, varsayılan değer `FALSE`.