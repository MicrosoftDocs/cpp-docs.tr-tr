---
title: E. OpenMP C/C++’daki uygulama tanımlı davranışlar
ms.date: 01/22/2019
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
ms.openlocfilehash: e866eee9c6d85e93388f9f1d086badf948e2600e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215052"
---
# <a name="e-implementation-defined-behaviors-in-openmp-cc"></a>E. OpenMP C/C++’daki uygulama tanımlı davranışlar

Bu ek, bu API 'de "uygulama tanımlı" olarak açıklanan davranışları özetler.  Her davranışa, ana belirtimdeki açıklamasına geri başvurulur.

## <a name="remarks"></a>Açıklamalar

Bu durumlarda davranışını tanımlamak ve belgelemek için bir uygulama gerekir, ancak bu liste eksik olabilir.

- **İş parçacığı sayısı:** İş parçacığı sayısı için dinamik ayarlama devre dışı bırakıldığı ve paralel bölge için istenen iş parçacığı sayısı, çalışma zamanı sisteminin sağlayabileceği sayıdan daha fazla olduğu için bir paralel bölge ile karşılaşılırsa, programın davranışı uygulama tanımlı olur (bkz. sayfa 9).

   Visual C++'te, iç içe olmayan bir paralel bölge için 64 iş parçacığı (en fazla) sağlanacak.

- **Işlemci sayısı:** Belirli bir zamanda iş parçacıklarını barındıran fiziksel işlemcilerin sayısı uygulama tanımlı olur (bkz. sayfa 10).

   Görselde C++bu sayı sabit değildir ve işletim sistemi tarafından denetlenir.

- **İş parçacığı takımları oluşturma:** Bir ekipteki iç içe paralel bölgeyi çalıştıran iş parçacıklarının sayısı uygulama tanımlı (bkz. sayfa 10).

   Bu sayı C++, Visual sisteminde, işletim sistemi tarafından belirlenir.

- **zamanla (çalışma zamanı):** Zamanlama kararı, çalışma zamanına kadar ertelenir. Zamanlama türü ve öbek boyutu, `OMP_SCHEDULE` ortam değişkeni ayarlanarak çalışma zamanında seçilebilir. Bu ortam değişkeni ayarlanmamışsa, sonuçta elde edilen zamanlama uygulama tanımlı olur (bkz. sayfa 13).

   Görselde C++zamanlama türü, öbek boyutu olmadan `static`.

- **Varsayılan zamanlama:** Schedule yan tümcesinin yokluğunda, varsayılan zamanlama uygulama tanımlı olur (bkz. sayfa 13).

   Görselde C++varsayılan zamanlama türü, öbek boyutu olmayan `static`.

- **Atomik:** Uygulama, uygulamanın tüm `atomic` yönergelerini aynı benzersiz ada sahip `critical` yönergeleriyle değiştirip değiştirmediğini (bkz. sayfa 20).

   Görselde C++, [atomik](reference/openmp-directives.md#atomic) tarafından değiştirilen veriler doğal bir hizalama üzerinde değilse veya bir veya iki bayt uzunsa, bu özelliği karşılayan tüm Atomik işlemler tek bir kritik bölüm kullanacaktır. Aksi takdirde, kritik bölümler kullanılmaz.

- **[omp_get_num_threads](3-run-time-library-functions.md#312-omp_get_num_threads-function):** İş parçacığı sayısı Kullanıcı tarafından açıkça ayarlanmamışsa, varsayılan değer uygulama tanımlı ' dır (bkz. sayfa 9).

   Görselde C++, varsayılan iş parçacığı sayısı işlemci sayısına eşittir.

- **[omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function):** Dinamik iş parçacığı ayarlaması için varsayılan değer uygulama tanımlı ' dır.

   Görselde C++varsayılan değer `FALSE`.

- **[omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function):** İç içe paralel paralellik etkinleştirildiğinde, iç içe paralel bölgeleri yürütmek için kullanılan iş parçacıklarının sayısı uygulama tanımlı olur.

   Visual C++sisteminde iş parçacığı sayısı işletim sistemi tarafından belirlenir.

- Ortam değişkeni [omp_schedule](4-environment-variables.md#41-omp_schedule) : Bu ortam değişkeninin varsayılan değeri uygulama tanımlı ' dır.

   Görselde C++zamanlama türü, öbek boyutu olmadan `static`.

- Ortam değişkeni [omp_num_threads](4-environment-variables.md#42-omp_num_threads) : `OMP_NUM_THREADS` ortam değişkeni için hiçbir değer belirtilmemişse veya belirtilen değer pozitif bir tamsayı değilse veya değer, sistemin destekleyebileceği en fazla iş parçacığı sayısından büyükse, kullanılacak iş parçacıklarının sayısı uygulama tanımlı olur.

   Görselde C++, belirtilen değer sıfır veya daha azsa, iş parçacığı sayısı işlemci sayısına eşittir.  Değer 64 ' den büyükse, iş parçacığı sayısı 64 ' dir.

- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic) ortam değişkeni: varsayılan değer uygulama tanımlı ' dır.

   Görselde C++varsayılan değer `FALSE`.
