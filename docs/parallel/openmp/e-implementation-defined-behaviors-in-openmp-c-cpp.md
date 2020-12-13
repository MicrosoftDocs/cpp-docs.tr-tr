---
description: OpenMP C/C++ ' da uygulama tanımlı davranışlar hakkında daha fazla bilgi edinin
title: E. OpenMP C/C++’daki uygulama tanımlı davranışlar
ms.date: 01/22/2019
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
ms.openlocfilehash: e8ebc8a336578a888ff8a7152552d4381a9d5add
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342484"
---
# <a name="e-implementation-defined-behaviors-in-openmp-cc"></a>E. OpenMP C/C++’daki uygulama tanımlı davranışlar

Bu ek, bu API 'de "uygulama tanımlı" olarak açıklanan davranışları özetler.  Her davranışa, ana belirtimdeki açıklamasına geri başvurulur.

## <a name="remarks"></a>Açıklamalar

Bu durumlarda davranışını tanımlamak ve belgelemek için bir uygulama gerekir, ancak bu liste eksik olabilir.

- **İş parçacığı sayısı:** İş parçacığı sayısı için dinamik ayarlama devre dışı bırakıldığı ve paralel bölge için istenen iş parçacığı sayısı, çalışma zamanı sisteminin sağlayabileceği sayıdan daha fazla olduğu için bir paralel bölge ile karşılaşılırsa, programın davranışı uygulama tanımlı olur (bkz. sayfa 9).

   Visual C++, iç içe olmayan bir paralel bölge için 64 iş parçacığı (en fazla) sağlanacak.

- **Işlemci sayısı:** Belirli bir zamanda iş parçacıklarını barındıran fiziksel işlemcilerin sayısı uygulama tanımlı olur (bkz. sayfa 10).

   Visual C++, bu sayı sabit değildir ve işletim sistemi tarafından denetlenir.

- **İş parçacığı takımları oluşturma:** Bir ekipteki iç içe paralel bölgeyi çalıştıran iş parçacıklarının sayısı uygulama tanımlı (bkz. sayfa 10).

   Visual C++, bu numara işletim sistemi tarafından belirlenir.

- **zamanla (çalışma zamanı):** Zamanlama kararı, çalışma zamanına kadar ertelenir. Zamanlama türü ve öbek boyutu, ortam değişkeni ayarlanarak çalışma zamanında seçilebilir `OMP_SCHEDULE` . Bu ortam değişkeni ayarlanmamışsa, sonuçta elde edilen zamanlama uygulama tanımlı olur (bkz. sayfa 13).

   Visual C++, zamanlama türü, `static` öbek boyutu yok.

- **Varsayılan zamanlama:** Schedule yan tümcesinin yokluğunda, varsayılan zamanlama uygulama tanımlı olur (bkz. sayfa 13).

   Visual C++, varsayılan zamanlama türü, `static` öbek boyutu yok.

- **Atomik:** Uygulama, uygulamanın tüm `atomic` yönergeleri `critical` aynı benzersiz ada sahip olan yönergelerden değiştirmediğini (bkz. sayfa 20) belirtir.

   Visual C++, [atomik](reference/openmp-directives.md#atomic) tarafından değiştirilen veriler doğal bir hizalama üzerinde değilse veya bir veya iki bayt uzunsa, bu özelliği karşılayan tüm Atomik işlemler tek bir kritik bölüm kullanacaktır. Aksi takdirde, kritik bölümler kullanılmaz.

- **[omp_get_num_threads](3-run-time-library-functions.md#312-omp_get_num_threads-function):** İş parçacığı sayısı Kullanıcı tarafından açıkça ayarlanmamışsa, varsayılan değer uygulama tanımlı ' dır (bkz. sayfa 9).

   Visual C++, varsayılan iş parçacığı sayısı işlemci sayısına eşittir.

- **[omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function):** Dinamik iş parçacığı ayarlaması için varsayılan değer uygulama tanımlı ' dır.

   Visual C++, varsayılan olarak ' dir `FALSE` .

- **[omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function):** İç içe paralel paralellik etkinleştirildiğinde, iç içe paralel bölgeleri yürütmek için kullanılan iş parçacıklarının sayısı uygulama tanımlı olur.

   Visual C++, iş parçacığı sayısı işletim sistemine göre belirlenir.

- Ortam değişkeni [omp_schedule](4-environment-variables.md#41-omp_schedule) : Bu ortam değişkeninin varsayılan değeri uygulama tanımlı ' dır.

   Visual C++, zamanlama türü, `static` öbek boyutu yok.

- Ortam değişkeni [omp_num_threads](4-environment-variables.md#42-omp_num_threads) : ortam değişkeni için hiçbir değer belirtilmemişse `OMP_NUM_THREADS` veya belirtilen değer pozitif bir tamsayı değilse veya değer sistemin destekleyebileceği en fazla iş parçacığı sayısından büyükse, kullanılacak iş parçacıklarının sayısı uygulama tanımlı olur.

   Visual C++, belirtilen değer sıfır veya daha azsa, iş parçacığı sayısı işlemci sayısına eşittir.  Değer 64 ' den büyükse, iş parçacığı sayısı 64 ' dir.

- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic) ortam değişkeni: varsayılan değer uygulama tanımlı ' dır.

   Visual C++, varsayılan olarak ' dir `FALSE` .
