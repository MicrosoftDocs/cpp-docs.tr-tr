---
title: OpenMP İşlevleri
ms.date: 03/20/2019
f1_keywords:
- OpenMP functions
- omp_destroy_lock
- omp_destroy_nest_lock
- omp_get_dynamic
- omp_get_max_threads
- omp_get_nested
- omp_get_num_procs
- omp_get_num_threads
- omp_get_thread_num
- omp_get_wtick
- omp_get_wtime
- omp_in_parallel
- omp_init_lock
- omp_init_nest_lock
- omp_set_dynamic
- omp_set_lock
- omp_set_nest_lock
- omp_set_nested
- omp_set_num_threads
- omp_test_lock
- omp_test_nest_lock
- omp_unset_lock
- omp_unset_nest_lock
helpviewer_keywords:
- OpenMP functions
- omp_destroy_lock OpenMP function
- omp_destroy_nest_lock OpenMP function
- omp_get_dynamic OpenMP function
- omp_get_max_threads OpenMP function
- omp_get_nested OpenMP function
- omp_get_num_procs OpenMP function
- omp_get_num_threads OpenMP function
- omp_get_thread_num OpenMP function
- omp_get_wtick OpenMP function
- omp_get_wtime OpenMP function
- omp_in_parallel OpenMP function
- omp_init_lock OpenMP function
- omp_init_nest_lock OpenMP function
- omp_set_dynamic OpenMP function
- omp_set_lock OpenMP function
- omp_set_nest_lock OpenMP function
- omp_set_nested OpenMP function
- omp_set_num_threads OpenMP function
- omp_test_lock OpenMP function
- omp_test_nest_lock OpenMP function
- omp_unset_lock OpenMP function
- omp_unset_nest_lock OpenMP function
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
ms.openlocfilehash: 0475a83ba259ed00bbcb9ddaba99a1556b35f613
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317137"
---
# <a name="openmp-functions"></a>OpenMP İşlevleri

OpenMP API'de kullanılan işlevlere bağlantılar sağlar.

OpenMP standardının Visual C++ uygulaması aşağıdaki işlevleri ve veri türlerini içerir.

Çevre yürütme için:

|İşlev|Açıklama|
|--------|-----------|
|[omp_set_num_threads](#omp-set-num-threads)|[num_threads](openmp-clauses.md#num-threads) bir yan tümce tarafından geçersiz kılınmadığı sürece, yaklaşan paralel bölgelerdeki iş parçacığı sayısını ayarlar.|
|[omp_get_num_threads](#omp-get-num-threads)|Paralel bölgedeki iş parçacığı sayısını döndürür.|
|[omp_get_max_threads](#omp-get-max-threads)|Kodda bu noktada [num_threads](openmp-clauses.md#num-threads) olmayan bir paralel bölge tanımlanmışsa, kullanılabilecek iş parçacığı sayısına eşit veya daha büyük bir tamsayı döndürür.|
|[omp_get_thread_num](#omp-get-thread-num)|İş parçacığı ekibi içinde çalıştırılatan iş parçacığının iş parçacığı numarasını verir.|
|[omp_get_num_procs](#omp-get-num-procs)|İşlev çağrıldığında kullanılabilen işlemci sayısını verir.|
|[omp_in_parallel](#omp-in-parallel)|Paralel bir bölge içinden çağrıldığında sıfırsız döndürür.|
|[omp_set_dynamic](#omp-set-dynamic)|Yaklaşan paralel bölgelerde kullanılabilen iş parçacığı sayısının çalışma süresine göre ayarlanabileceğini gösterir.|
|[omp_get_dynamic](#omp-get-dynamic)|Yaklaşan paralel bölgelerde kullanılabilen iş parçacığı sayısının çalışma süresine göre ayarlanabilen bir değer verir.|
|[omp_set_nested](#omp-set-nested)|İç içe paralellik sağlar.|
|[omp_get_nested](#omp-get-nested)|İç içe paralellik etkin olup olmadığını gösteren bir değer döndürür.|

Kilit için:

|İşlev|Açıklama|
|--------|-----------|
|[omp_init_lock](#omp-init-lock)|Basit bir kilidi niçin başlatar.|
|[omp_init_nest_lock](#omp-init-nest-lock)|Kilidi niçin başlatılmasını.|
|[omp_destroy_lock](#omp-destroy-lock)|Kilidi niçin başlatmaz.|
|[omp_destroy_nest_lock](#omp-destroy-nest-lock)|Nestable kilidi niçin başlatmaz.|
|[omp_set_lock](#omp-set-lock)|Bir kilit kullanılabilir olana kadar iş parçacığı yürütmeyi engeller.|
|[omp_set_nest_lock](#omp-set-nest-lock)|Bir kilit kullanılabilir olana kadar iş parçacığı yürütmeyi engeller.|
|[omp_unset_lock](#omp-unset-lock)|Bir kilit salgılar.|
|[omp_unset_nest_lock](#omp-unset-nest-lock)|Nestable kilidi serbest bırakır.|
|[omp_test_lock](#omp-test-lock)|Kilit ayarlamaya çalışır, ancak iş parçacığı yürütmesini engellemez.|
|[omp_test_nest_lock](#omp-test-nest-lock)|Nekararlı bir kilit ayarlamaya çalışır, ancak iş parçacığı yürütmesini engellemez.|

|Veri türü|Açıklama|
|---------|-----------|
|`omp_lock_t`|Kilit durumunu tutan, kilidin kullanılabilir olup olmadığı veya bir iş parçacığının kilit sahibi olup olmadığı.|
|`omp_nest_lock_t`|Kilit le ilgili aşağıdaki bilgilerden birini tutan bir tür: kilidin kullanılabilir olup olmadığı ve kilidin ve iç içe geçme sayısının sahibi olan iş parçacığının kimliği.|

Zamanlama rutinleri için:

|İşlev|Açıklama|
|--------|-----------|
|[omp_get_wtime](#omp-get-wtime)|Bir noktadan geçen sürenin saniyecinsinden bir değeri döndürür.|
|[omp_get_wtick](#omp-get-wtick)|İşlemci saat keneleri arasındaki saniye sayısını verir.|

## <a name="omp_destroy_lock"></a><a name="omp-destroy-lock"></a>omp_destroy_lock

Kilidi niçin başlatmaz.

```cpp
void omp_destroy_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*Kilit*<br/>
[omp_init_lock](#omp-init-lock)ile `omp_lock_t` başharfe bürünen bir tür değişkeni.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.2 omp_destroy_lock ve omp_destroy_nest_lock işlevlerine](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)bakın.

### <a name="example"></a>Örnek

Kullanma [omp_init_lock](#omp-init-lock) `omp_destroy_lock`örneği için omp_init_lock bakın.

## <a name="omp_destroy_nest_lock"></a><a name="omp-destroy-nest-lock"></a>omp_destroy_nest_lock

Nestable kilidi niçin başlatmaz.

```cpp
void omp_destroy_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*Kilit*<br/>
omp_init_nest_lock ile `omp_nest_lock_t` başharfe bürünen bir tür [değişkeni.](#omp-init-nest-lock)

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.2 omp_destroy_lock ve omp_destroy_nest_lock işlevlerine](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)bakın.

### <a name="example"></a>Örnek

Kullanma [omp_init_nest_lock](#omp-init-nest-lock) örneği için omp_init_nest_lock `omp_destroy_nest_lock`bakın.

## <a name="omp_get_dynamic"></a><a name="omp-get-dynamic"></a>omp_get_dynamic

Yaklaşan paralel bölgelerde kullanılabilen iş parçacığı sayısının çalışma süresine göre ayarlanabilen bir değer verir.

```cpp
int omp_get_dynamic();
```

### <a name="return-value"></a>Döndürülen değer

Sıfır olmayan bir değer, iş parçacıklarının dinamik olarak ayarlanması anlamına gelir.

### <a name="remarks"></a>Açıklamalar

Iş parçacıklarının dinamik ayarı [omp_set_dynamic](#omp-set-dynamic) ve [OMP_DYNAMIC](openmp-environment-variables.md#omp-dynamic)ile belirtilir.

Daha fazla bilgi için [3.1.7 omp_set_dynamic işlevine](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)bakın.

### <a name="example"></a>Örnek

Kullanma [omp_set_dynamic](#omp-set-dynamic) `omp_get_dynamic`örneği için omp_set_dynamic bakın.

## <a name="omp_get_max_threads"></a><a name="omp-get-max-threads"></a>omp_get_max_threads

Kodda bu noktada [num_threads](openmp-clauses.md#num-threads) olmayan bir paralel bölge tanımlanmışsa, kullanılabilecek iş parçacığı sayısına eşit veya daha büyük bir tamsayı döndürür.

```cpp
int omp_get_max_threads( )
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.1.3 omp_get_max_threads işlevine](../../../parallel/openmp/3-1-3-omp-get-max-threads-function.md)bakın.

### <a name="example"></a>Örnek

```cpp
// omp_get_max_threads.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_num_threads(8);
    printf_s("%d\n", omp_get_max_threads( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_max_threads( ));
        }

    printf_s("%d\n", omp_get_max_threads( ));

    #pragma omp parallel num_threads(3)
        #pragma omp master
        {
            printf_s("%d\n", omp_get_max_threads( ));
        }

    printf_s("%d\n", omp_get_max_threads( ));
}
```

```Output
8
8
8
8
8
```

## <a name="omp_get_nested"></a><a name="omp-get-nested"></a>omp_get_nested

İç içe paralellik etkin olup olmadığını gösteren bir değer döndürür.

```cpp
int omp_get_nested( );
```

### <a name="return-value"></a>Döndürülen değer

Sıfır olmayan bir değer iç içe paralellik etkin anlamına gelir.

### <a name="remarks"></a>Açıklamalar

İç içe paralellik [omp_set_nested](#omp-set-nested) ve [OMP_NESTED](openmp-environment-variables.md#omp-nested)ile belirtilir.

Daha fazla bilgi için [3.1.10 omp_get_nested işlevine](../../../parallel/openmp/3-1-10-omp-get-nested-function.md)bakın.

### <a name="example"></a>Örnek

Kullanma [omp_set_nested](#omp-set-nested) `omp_get_nested`örneği için omp_set_nested bakın.

## <a name="omp_get_num_procs"></a><a name="omp-get-num-procs"></a>omp_get_num_procs

İşlev çağrıldığında kullanılabilen işlemci sayısını verir.

```cpp
int omp_get_num_procs();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.1.5 omp_get_num_procs işlevine](../../../parallel/openmp/3-1-5-omp-get-num-procs-function.md)bakın.

### <a name="example"></a>Örnek

```cpp
// omp_get_num_procs.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    printf_s("%d\n", omp_get_num_procs( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_procs( ));
        }
}
```

```Output
// Expect the following output when the example is run on a two-processor machine:
2
2
```

## <a name="omp_get_num_threads"></a><a name="omp-get-num-threads"></a>omp_get_num_threads

Paralel bölgedeki iş parçacığı sayısını döndürür.

```cpp
int omp_get_num_threads( );
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.1.2 omp_get_num_threads işlevine](../../../parallel/openmp/3-1-2-omp-get-num-threads-function.md)bakın.

### <a name="example"></a>Örnek

```cpp
// omp_get_num_threads.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main()
{
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_num_threads( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_threads( ));
        }

    printf_s("%d\n", omp_get_num_threads( ));

    #pragma omp parallel num_threads(3)
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_threads( ));
        }

    printf_s("%d\n", omp_get_num_threads( ));
}
```

```Output
1
4
1
3
1
```

## <a name="omp_get_thread_num"></a><a name="omp-get-thread-num"></a>omp_get_thread_num

İş parçacığı ekibi içinde çalıştırılatan iş parçacığının iş parçacığı numarasını verir.

```cpp
int omp_get_thread_num( );
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.1.4 omp_get_thread_num işlevine](../../../parallel/openmp/3-1-4-omp-get-thread-num-function.md)bakın.

### <a name="example"></a>Örnek

Kullanma [parallel](openmp-directives.md#parallel) `omp_get_thread_num`örneği için paralel bkz.

## <a name="omp_get_wtick"></a><a name="omp-get-wtick"></a>omp_get_wtick

İşlemci saat keneleri arasındaki saniye sayısını verir.

```cpp
double omp_get_wtick( );
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.3.2 omp_get_wtick işlevine](../../../parallel/openmp/3-3-2-omp-get-wtick-function.md)bakın.

### <a name="example"></a>Örnek

Kullanma [omp_get_wtime](#omp-get-wtime) örneği için omp_get_wtime `omp_get_wtick`bakın.

## <a name="omp_get_wtime"></a><a name="omp-get-wtime"></a>omp_get_wtime

Bir noktadan geçen sürenin saniyecinsinden bir değeri döndürür.

```cpp
double omp_get_wtime( );
```

### <a name="return-value"></a>Döndürülen değer

Bir değeri, rasgele, ancak tutarlı bir noktadan geçen sürenin saniyecinsinden verir.

### <a name="remarks"></a>Açıklamalar

Bu nokta, yaklaşan karşılaştırmaları mümkün kalarak, program yürütme sırasında tutarlı kalacaktır.

Daha fazla bilgi için [3.3.1 omp_get_wtime işlevine](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md)bakın.

### <a name="example"></a>Örnek

```cpp
// omp_get_wtime.cpp
// compile with: /openmp
#include "omp.h"
#include <stdio.h>
#include <windows.h>

int main() {
    double start = omp_get_wtime( );
    Sleep(1000);
    double end = omp_get_wtime( );
    double wtick = omp_get_wtick( );

    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",
             start, end, end - start);

    printf_s("wtick = %.16g\n1/wtick = %.16g\n",
             wtick, 1.0 / wtick);
}
```

```Output
start = 594255.3671159324
end = 594256.3664474116
diff = 0.9993314791936427
wtick = 2.793651148400146e-007
1/wtick = 3579545
```

## <a name="omp_in_parallel"></a><a name="omp-in-parallel"></a>omp_in_parallel

Paralel bir bölge içinden çağrıldığında sıfırsız döndürür.

```cpp
int omp_in_parallel( );
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.1.6 omp_in_parallel işlevine](../../../parallel/openmp/3-1-6-omp-in-parallel-function.md)bakın.

### <a name="example"></a>Örnek

```cpp
// omp_in_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_num_threads(4);
    printf_s("%d\n", omp_in_parallel( ));

    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_in_parallel( ));
        }
}
```

```Output
0
1
```

## <a name="omp_init_lock"></a><a name="omp-init-lock"></a>omp_init_lock

Basit bir kilidi niçin başlatar.

```cpp
void omp_init_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*Kilit*<br/>
Bir tür `omp_lock_t`değişkeni.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.1 omp_init_lock ve omp_init_nest_lock işlevlerine](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)bakın.

### <a name="example"></a>Örnek

```cpp
// omp_init_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_lock_t my_lock;

int main() {
   omp_init_lock(&my_lock);

   #pragma omp parallel num_threads(4)
   {
      int tid = omp_get_thread_num( );
      int i, j;

      for (i = 0; i < 5; ++i) {
         omp_set_lock(&my_lock);
         printf_s("Thread %d - starting locked region\n", tid);
         printf_s("Thread %d - ending locked region\n", tid);
         omp_unset_lock(&my_lock);
      }
   }

   omp_destroy_lock(&my_lock);
}
```

```Output
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
```

## <a name="omp_init_nest_lock"></a><a name="omp-init-nest-lock"></a>omp_init_nest_lock

Kilidi niçin başlatılmasını.

```cpp
void omp_init_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*Kilit*<br/>
Bir tür `omp_nest_lock_t`değişkeni.

### <a name="remarks"></a>Açıklamalar

İlk iç içe geçme sayısı sıfırdır.

Daha fazla bilgi için [3.2.1 omp_init_lock ve omp_init_nest_lock işlevlerine](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)bakın.

### <a name="example"></a>Örnek

```cpp
// omp_init_nest_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_nest_lock_t my_lock;

void Test() {
   int tid = omp_get_thread_num( );
   omp_set_nest_lock(&my_lock);
   printf_s("Thread %d - starting nested locked region\n", tid);
   printf_s("Thread %d - ending nested locked region\n", tid);
   omp_unset_nest_lock(&my_lock);
}

int main() {
   omp_init_nest_lock(&my_lock);

   #pragma omp parallel num_threads(4)
   {
      int i, j;

      for (i = 0; i < 5; ++i) {
         omp_set_nest_lock(&my_lock);
            if (i % 3)
               Test();
            omp_unset_nest_lock(&my_lock);
        }
    }

    omp_destroy_nest_lock(&my_lock);
}
```

```Output
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
```

## <a name="omp_set_dynamic"></a><a name="omp-set-dynamic"></a>Omp_set_dynamic

Yaklaşan paralel bölgelerde kullanılabilen iş parçacığı sayısının çalışma süresine göre ayarlanabileceğini gösterir.

```cpp
void omp_set_dynamic(
   int val
);
```

### <a name="parameters"></a>Parametreler

*Val*<br/>
Yaklaşan paralel bölgelerde kullanılabilen iş parçacığı sayısının çalışma süresine göre ayarlanabilen bir değer. Sıfır değilse, çalışma zamanı iş parçacığı sayısını ayarlayabilir, sıfır ise, çalışma zamanı iş parçacığı sayısını dinamik olarak ayarlamaz.

### <a name="remarks"></a>Açıklamalar

İş parçacığı sayısı, [omp_set_num_threads](#omp-set-num-threads) veya [OMP_NUM_THREADS](openmp-environment-variables.md#omp-num-threads)tarafından ayarlanan değeri asla aşmaz.

Geçerli [omp_get_dynamic](#omp-get-dynamic) ayarını görüntülemek için `omp_set_dynamic`omp_get_dynamic kullanın.

Ayar, `omp_set_dynamic` [OMP_DYNAMIC](openmp-environment-variables.md#omp-dynamic) ortamı değişkeninin ayarını geçersiz kılar.

Daha fazla bilgi için [3.1.7 omp_set_dynamic işlevine](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)bakın.

### <a name="example"></a>Örnek

```cpp
// omp_set_dynamic.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main()
{
    omp_set_dynamic(9);
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_dynamic( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_dynamic( ));
        }
}
```

```Output
1
1
```

## <a name="omp_set_lock"></a><a name="omp-set-lock"></a>omp_set_lock

Bir kilit kullanılabilir olana kadar iş parçacığı yürütmeyi engeller.

```cpp
void omp_set_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*Kilit*<br/>
[omp_init_lock](#omp-init-lock)ile `omp_lock_t` başharfe bürünen bir tür değişkeni.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.3 omp_set_lock ve omp_set_nest_lock işlevlerine](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)bakın.

### <a name="examples"></a>Örnekler

Kullanma [omp_init_lock](#omp-init-lock) `omp_set_lock`örneği için omp_init_lock bakın.

## <a name="omp_set_nest_lock"></a><a name="omp-set-nest-lock"></a>omp_set_nest_lock

Bir kilit kullanılabilir olana kadar iş parçacığı yürütmeyi engeller.

```cpp
void omp_set_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*Kilit*<br/>
omp_init_nest_lock ile `omp_nest_lock_t` başharfe bürünen bir tür [değişkeni.](#omp-init-nest-lock)

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.3 omp_set_lock ve omp_set_nest_lock işlevlerine](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)bakın.

### <a name="examples"></a>Örnekler

Kullanma [omp_init_nest_lock](#omp-init-nest-lock) örneği için omp_init_nest_lock `omp_set_nest_lock`bakın.

## <a name="omp_set_nested"></a><a name="omp-set-nested"></a>omp_set_nested

İç içe paralellik sağlar.

```cpp
void omp_set_nested(
   int val
);
```

### <a name="parameters"></a>Parametreler

*Val*<br/>
Sıfır olmayan bir değer iç içe paralellik sağlarken, sıfır iç içe paralelliği devre dışı kılabilir.

### <a name="remarks"></a>Açıklamalar

OMP iç içe paralellik ile `omp_set_nested`açılabilir , veya [OMP_NESTED](openmp-environment-variables.md#omp-nested) ortam değişkeni ayarlayarak.

Ayar için `omp_set_nested` `OMP_NESTED` ortam değişkeninin ayarı geçersiz kılar.

Ortam değişkenini etkinleştirmek, paralel bölgeleri iç içe geçirerken iş parçacığı sayısı katlanarak arttığıiçin, başka bir şekilde işlevsel bir programı bozabilir. Örneğin, 4'e ayarlanmış OMP iş parçacığı sayısıyla altı kez yeniden lanetleyen bir işlev, 4.096 (6'nın gücüne 4) iş parçacığı gerektirir. G/Ç'ye bağlı uygulamalar dışında, işlemcilerden daha fazla iş parçacığı varsa, bir uygulamanın performansı genellikle düşer.

Geçerli [omp_get_nested](#omp-get-nested) ayarını görüntülemek için `omp_set_nested`omp_get_nested kullanın.

Daha fazla bilgi için [3.1.9 omp_set_nested işlevine](../../../parallel/openmp/3-1-9-omp-set-nested-function.md)bakın.

### <a name="example"></a>Örnek

```cpp
// omp_set_nested.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_nested(1);
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_nested( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_nested( ));
        }
}
```

```Output
1
1
```

## <a name="omp_set_num_threads"></a><a name="omp-set-num-threads"></a>Omp_set_num_threads

[num_threads](openmp-clauses.md#num-threads) bir yan tümce tarafından geçersiz kılınmadığı sürece, yaklaşan paralel bölgelerdeki iş parçacığı sayısını ayarlar.

```cpp
void omp_set_num_threads(
   int num_threads
);
```

### <a name="parameters"></a>Parametreler

*num_threads*<br/>
Paralel bölgedeki iş parçacığı sayısı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.1.1 omp_set_num_threads işlevine](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)bakın.

### <a name="example"></a>Örnek

Kullanma [omp_get_num_threads](#omp-get-num-threads) örneği için omp_get_num_threads `omp_set_num_threads`bakın.

## <a name="omp_test_lock"></a><a name="omp-test-lock"></a>omp_test_lock

Kilit ayarlamaya çalışır, ancak iş parçacığı yürütmesini engellemez.

```cpp
int omp_test_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*Kilit*<br/>
[omp_init_lock](#omp-init-lock)ile `omp_lock_t` başharfe bürünen bir tür değişkeni.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.5 omp_test_lock ve omp_test_nest_lock işlevlerine](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)bakın.

### <a name="example"></a>Örnek

```cpp
// omp_test_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_lock_t simple_lock;

int main() {
    omp_init_lock(&simple_lock);

    #pragma omp parallel num_threads(4)
    {
        int tid = omp_get_thread_num();

        while (!omp_test_lock(&simple_lock))
            printf_s("Thread %d - failed to acquire simple_lock\n",
                     tid);

        printf_s("Thread %d - acquired simple_lock\n", tid);

        printf_s("Thread %d - released simple_lock\n", tid);
        omp_unset_lock(&simple_lock);
    }

    omp_destroy_lock(&simple_lock);
}
```

```Output
Thread 1 - acquired simple_lock
Thread 1 - released simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 2 - acquired simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 2 - released simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - acquired simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - released simple_lock
Thread 3 - failed to acquire simple_lock
Thread 3 - acquired simple_lock
Thread 3 - released simple_lock
```

## <a name="omp_test_nest_lock"></a><a name="omp-test-nest-lock"></a>omp_test_nest_lock

Nekararlı bir kilit ayarlamaya çalışır, ancak iş parçacığı yürütmesini engellemez.

```cpp
int omp_test_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*Kilit*<br/>
omp_init_nest_lock ile `omp_nest_lock_t` başharfe bürünen bir tür [değişkeni.](#omp-init-nest-lock)

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.5 omp_test_lock ve omp_test_nest_lock işlevlerine](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)bakın.

### <a name="example"></a>Örnek

```cpp
// omp_test_nest_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_nest_lock_t nestable_lock;

int main() {
   omp_init_nest_lock(&nestable_lock);

   #pragma omp parallel num_threads(4)
   {
      int tid = omp_get_thread_num();
      while (!omp_test_nest_lock(&nestable_lock))
         printf_s("Thread %d - failed to acquire nestable_lock\n",
                tid);

      printf_s("Thread %d - acquired nestable_lock\n", tid);

      if (omp_test_nest_lock(&nestable_lock)) {
         printf_s("Thread %d - acquired nestable_lock again\n",
                tid);
         printf_s("Thread %d - released nestable_lock\n",
                tid);
         omp_unset_nest_lock(&nestable_lock);
      }

      printf_s("Thread %d - released nestable_lock\n", tid);
      omp_unset_nest_lock(&nestable_lock);
   }

   omp_destroy_nest_lock(&nestable_lock);
}
```

```Output
Thread 1 - acquired nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 1 - acquired nestable_lock again
Thread 0 - failed to acquire nestable_lock
Thread 1 - released nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 1 - released nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 3 - acquired nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 3 - acquired nestable_lock again
Thread 0 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 3 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 3 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - acquired nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - acquired nestable_lock again
Thread 2 - failed to acquire nestable_lock
Thread 0 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - acquired nestable_lock
Thread 2 - acquired nestable_lock again
Thread 2 - released nestable_lock
Thread 2 - released nestable_lock
```

## <a name="omp_unset_lock"></a><a name="omp-unset-lock"></a>omp_unset_lock

Bir kilit salgılar.

```cpp
void omp_unset_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*Kilit*<br/>
İş parçacığına `omp_lock_t` ait ve işlevde yürütülen [omp_init_lock](#omp-init-lock)ile başharfe bürünen bir tür değişkeni.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.4 omp_unset_lock ve omp_unset_nest_lock işlevlerine](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md)bakın.

### <a name="example"></a>Örnek

Kullanma [omp_init_lock](#omp-init-lock) `omp_unset_lock`örneği için omp_init_lock bakın.

## <a name="omp_unset_nest_lock"></a><a name="omp-unset-nest-lock"></a>omp_unset_nest_lock

Nestable kilidi serbest bırakır.

```cpp
void omp_unset_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*Kilit*<br/>
Iş parçacığına `omp_nest_lock_t` ait ve işlevde yürütülen [omp_init_nest_lock](#omp-init-nest-lock)ile başharfe bürünen bir tür değişkeni.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.4 omp_unset_lock ve omp_unset_nest_lock işlevlerine](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md)bakın.

### <a name="example"></a>Örnek

Kullanma [omp_init_nest_lock](#omp-init-nest-lock) örneği için omp_init_nest_lock `omp_unset_nest_lock`bakın.
