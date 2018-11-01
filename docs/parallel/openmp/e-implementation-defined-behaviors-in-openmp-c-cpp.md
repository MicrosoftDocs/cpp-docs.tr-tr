---
title: E. OpenMP C/C++'daki uygulama tanımlı davranışlar
ms.date: 11/04/2016
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
ms.openlocfilehash: 704062f36102a06e6e7b8cf015f6330f925a6bba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619355"
---
# <a name="e-implementation-defined-behaviors-in-openmp-cc"></a>E. OpenMP C/C++'daki uygulama tanımlı davranışlar

Bu ekte, "uygulama tanımlı" Bu API olarak açıklanan davranışları özetler.  Her ana belirtiminde açıklamasını dön açıklamasındaki davranıştır.

## <a name="remarks"></a>Açıklamalar

Bir uygulama tanımlamak ve bu gibi durumlarda davranışını belge için gerekli değildir, ancak bu liste eksik olabilir.

- **İş parçacığı sayısı:** bulunursa bir paralel bölgenin iş parçacığı sayısını yerleştirmenin dinamik ayarına devre dışı bırakıldı ve çalışma zamanı sistemi sağlayabilirler, davranışını numarası için paralel bölgenin istenen iş parçacığı sayısını aşıyor program uygulaması-(9 sayfasında bakın) tanımlanır.

   Visual C++'da bir yuvalı olmayan paralel bir bölge için 64 iş parçacığı (maksimum) sağlanır.

- **İşlemci sayısı:** aslında iş parçacığı herhangi bir zamanda barındıran fiziksel işlemcilerin sayısını uygulama-(10 sayfasında bakın) tanımlanır.

   Visual C++ ' ta bu sayının sabit değil ve işletim sistemi tarafından denetlenir.

- **Takımlar, iş parçacığı oluşturma:** iç içe geçmiş bir paralel bölgenin yürüten iş parçacığı ekip uygulama tanımlı sayısıdır. () 10 sayfasında bakın).

   Visual C++'da, bu işletim sistemi tarafından belirlenir.

- **Schedule(Runtime):** ilgili planlama çalışma zamanına kadar ertelenmiş karar. Zamanlama türü ve Öbek boyutu ayarlayarak çalışma zamanında seçilebilir `OMP_SCHEDULE` ortam değişkeni. Bu ortam değişkeni ayarlanmazsa, sonuçta elde edilen zamanlama uygulama-(13 sayfasında bakın) tanımlanır.

   Visual C++'da, zamanlama türü olan `static` öbek boyutu yok.

- **Varsayılan zamanlama:** zamanlama yan tümcesinin olmaması durumunda, varsayılan zamanlama uygulama-(13 sayfasında bakın) tanımlanır.

   Visual C++'da, varsayılan zamanlama türüdür `static` öbek boyutu yok.

- **ATOMİK:** olup tüm uygulama değiştirir uygulama tanımlı olduğu `atomic` yönergeleri ile **kritik** aynı benzersiz adı (bkz: sayfa 20) yönergeleri.

   Görsel verileri değiştiren, C++ ' ta [atomik](../../parallel/openmp/reference/atomic.md) üzerinde bir doğal hizalama değil veya bu özelliği karşılayan tüm uzun atomik işlemler, 1 veya 2 bayt ise bir kritik bölüm kullanır. Aksi takdirde, kritik bölümleri kullanılmaz.

- **omp_get_num_threads:** uygulama tanımlı varsayılan iş parçacığı sayısı kullanıcı tarafından açıkça ayarlanmamış ise (9, sayfasına bakın ve [bölümü 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) sayfasında 37).

   Visual C++'da varsayılan iş parçacığı sayısını işlemci sayısına eşittir.

- **omp_set_dynamic:** için dinamik iş parçacığı ayarlama varsayılan uygulama tanımlanır (bkz [bölümü 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39).

   Visual C++'da, varsayılan değer `FALSE`.

- **omp_set_nested:** iç içe geçmiş paralellik etkinleştirildiğinde, uygulama tarafından tanımlanan iç içe geçmiş paralel bölgeleri yürütmek için kullanılan iş parçacıklarının sayısını (bkz [bölümü 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) sayfasında 40).

   Visual C++'da iş parçacığı sayısını işletim sistemi tarafından belirlenir.

- `OMP_SCHEDULE` ortam değişkeni: Bu ortam değişkeni için varsayılan değer uygulama tanımlanır (bkz [bölümü 4.1](../../parallel/openmp/4-1-omp-schedule.md) sayfasında 48).

   Visual C++'da, zamanlama türü olan `static` öbek boyutu yok.

- `OMP_NUM_THREADS` ortam değişkeni: için hiçbir değer belirtilmemişse `OMP_NUM_THREADS` ortam değişkeni veya belirtilen değer pozitif bir tamsayı değil veya değeri, iş parçacıkları sistem desteklediği en fazla sayısından büyükse, kullanılacak iş parçacığı sayısı uygulama tanımlı (bkz [bölümü 4.2](../../parallel/openmp/4-2-omp-num-threads.md) sayfasında 48).

   Visual C++ ' ta değeri belirtilmişse sıfır veya daha az iş parçacığı sayısını işlemci sayısına eşit değil.  Değeri 64 ' büyükse, iş parçacığı sayısı 64'tür.

- `OMP_DYNAMIC` ortam değişkeni: varsayılan değer uygulama tarafından tanımlanır (bkz [bölümü 4.3](../../parallel/openmp/4-3-omp-dynamic.md) sayfasında 49).

   Visual C++'da, varsayılan değer `FALSE`.