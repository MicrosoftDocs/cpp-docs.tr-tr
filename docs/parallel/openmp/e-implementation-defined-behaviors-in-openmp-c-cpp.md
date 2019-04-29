---
title: E. OpenMP C/C++'daki uygulama tanımlı davranışlar
ms.date: 01/22/2019
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
ms.openlocfilehash: 3d8e9493cad1fce02e5d482cd5e612afb44bb37b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362763"
---
# <a name="e-implementation-defined-behaviors-in-openmp-cc"></a>E. OpenMP C/C++'daki uygulama tanımlı davranışlar

Bu ekte, "uygulama tanımlı" Bu API olarak açıklanan davranışları özetler.  Her ana belirtiminde açıklamasını dön açıklamasındaki davranıştır.

## <a name="remarks"></a>Açıklamalar

Bir uygulama tanımlamak ve bu gibi durumlarda davranışını belge için gerekli değildir, ancak bu liste eksik olabilir.

- **İş parçacığı sayısı:** Bir paralel bölgenin iş parçacığı sayısını yerleştirmenin dinamik ayarına devre dışı bırakıldı ve paralel bölge için istenen iş parçacığı sayısını çalışma zamanı sistemi sağladığınız sayısından fazla karşılaşılırsa, davranıştır programı uygulama tanımlı-(9 sayfasında bakın).

   Visual C++'da bir yuvalı olmayan paralel bir bölge için 64 iş parçacığı (maksimum) sağlanır.

- **İşlemci sayısı:** Aslında iş parçacığı herhangi bir zamanda barındıran fiziksel işlemcilerin sayısını uygulama-(10 sayfasında bakın) tanımlanır.

   Visual C++ ' ta bu sayının sabit değildir ve işletim sistemi tarafından denetlenir.

- **Takımlar, iş parçacığı oluşturma:** İç içe geçmiş bir paralel bölgenin yürütme iş parçacığı ekip sayısını uygulama-(10 sayfasında bakın) tanımlanır.

   Visual C++'da, bu sayı işletim sistemi tarafından belirlenir.

- **Schedule(Runtime):** Zamanlama hakkında karar çalışma zamanına kadar ertelenir. Zamanlama türü ve Öbek boyutu ayarlayarak çalışma zamanında seçilebilir `OMP_SCHEDULE` ortam değişkeni. Bu ortam değişkeni ayarlanmamış ise sonuç zamanlama uygulama-(13 sayfasında bakın) tanımlanır.

   Visual C++'da, zamanlama türü olan `static` öbek boyutu yok.

- **Zamanlama varsayılan:** Zamanlama yan tümcesinin olmaması durumunda, varsayılan zamanlama uygulama-(13 sayfasında bakın) tanımlanır.

   Visual C++'da, varsayılan zamanlama türüdür `static` öbek boyutu yok.

- **ATOMİK:** Bu uygulama tüm olup yerini alır uygulama tanımlı `atomic` yönergeleri ile `critical` aynı benzersiz adı (bkz: sayfa 20) yönergeleri.

   Görsel verileri değiştiren, C++ ' ta [atomik](reference/openmp-directives.md#atomic) üzerinde bir doğal hizalama değil veya bu özelliği karşılayan tüm atomik işlemler, bir veya iki bayt uzun olması durumunda, bir kritik bölüm kullanır. Aksi takdirde, kritik bölümleri kullanılmaz.

- **[omp_get_num_threads](3-run-time-library-functions.md#312-omp_get_num_threads-function):** İş parçacığı sayısı kullanıcı tarafından açıkça ayarlanmamışsa, varsayılan uygulama-(9 sayfasında bakın) tanımlanır.

   Visual C++'da varsayılan iş parçacığı sayısını işlemci sayısına eşittir.

- **[omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function):** İçin dinamik iş parçacığı ayarlama varsayılan uygulama tanımlanır.

   Visual C++'da, varsayılan değer `FALSE`.

- **[omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function):** İç içe geçmiş paralellik etkinleştirildiğinde, uygulama tarafından tanımlanan iç içe geçmiş paralel bölgeleri yürütmek için kullanılan iş parçacıklarının sayısı.

   Visual C++'da iş parçacığı sayısını işletim sistemi tarafından belirlenir.

- [OMP_SCHEDULE](4-environment-variables.md#41-omp_schedule) ortam değişkeni: Bu ortam değişkeni için varsayılan değer uygulama tarafından tanımlanır.

   Visual C++'da, zamanlama türü olan `static` öbek boyutu yok.

- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads) ortam değişkeni: İçin hiçbir değer belirtilmemişse `OMP_NUM_THREADS` ortam değişkeni veya belirtilen değer pozitif bir tamsayı değilse veya değer, iş parçacıkları sistem desteklediği en fazla sayısından büyükse, uygulama tanımlı kullanılacak iş parçacığı sayısı.

   Visual C++ ' ta değeri belirtilmişse sıfır veya daha az iş parçacığı sayısını işlemci sayısına eşit değil.  Değeri 64 ' büyükse, iş parçacığı sayısı 64'tür.

- [Omp_dynamıc](4-environment-variables.md#43-omp_dynamic) ortam değişkeni: Uygulama tanımlı varsayılan değerdir.

   Visual C++'da, varsayılan değer `FALSE`.