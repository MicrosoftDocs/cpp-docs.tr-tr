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
ms.openlocfilehash: 4508c683ff5d4bece290b7fef2bbd83ae8023eac
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417000"
---
# <a name="openmp-functions"></a>OpenMP İşlevleri

OpenMP API 'sinde kullanılan işlevlere bağlantılar sağlar.

OpenMP standardının C++ görsel uygulanması aşağıdaki işlevleri ve veri türlerini içerir.

Ortam yürütme için:

|İşlev|Açıklama|
|--------|-----------|
|[omp_set_num_threads](#omp-set-num-threads)|[Num_threads](openmp-clauses.md#num-threads) yan tümcesi tarafından geçersiz kılınmadıkça yaklaşan paralel bölgelerdeki iş parçacığı sayısını ayarlar.|
|[omp_get_num_threads](#omp-get-num-threads)|Paralel bölgedeki iş parçacığı sayısını döndürür.|
|[omp_get_max_threads](#omp-get-max-threads)|Kodda bu noktada [num_threads](openmp-clauses.md#num-threads) olmayan bir paralel bölge tanımlanmışsa, kullanılabilecek iş parçacığı sayısına eşit veya ondan daha büyük bir tamsayı döndürür.|
|[omp_get_thread_num](#omp-get-thread-num)|İş parçacığı ekibi içinde yürütülen iş parçacığının iş parçacığı numarasını döndürür.|
|[omp_get_num_procs](#omp-get-num-procs)|İşlev çağrıldığında kullanılabilir olan işlemcilerin sayısını döndürür.|
|[omp_in_parallel](#omp-in-parallel)|Paralel bir bölgenin içinden çağrılırsa sıfır dışında bir değer döndürür.|
|[omp_set_dynamic](#omp-set-dynamic)|Yaklaşan paralel bölgelerde kullanılabilen iş parçacıklarının sayısının çalışma zamanına göre ayarlanamayacağını gösterir.|
|[omp_get_dynamic](#omp-get-dynamic)|Yaklaşan paralel bölgelerde kullanılabilir olan iş parçacıklarının sayısının çalışma zamanına göre ayarlanamayacağını gösteren bir değer döndürür.|
|[omp_set_nested](#omp-set-nested)|İç içe paralellik kullanılmasına izin vermez.|
|[omp_get_nested](#omp-get-nested)|İç içe paralel paralellik etkin olup olmadığını gösteren bir değer döndürür.|

Kilit için:

|İşlev|Açıklama|
|--------|-----------|
|[omp_init_lock](#omp-init-lock)|Basit bir kilit başlatır.|
|[omp_init_nest_lock](#omp-init-nest-lock)|Bir kilidi başlatır.|
|[omp_destroy_lock](#omp-destroy-lock)|Kilidin işaretini kaldırır.|
|[omp_destroy_nest_lock](#omp-destroy-nest-lock)|Bir iç içe konulabilir kilidi başlatır.|
|[omp_set_lock](#omp-set-lock)|Kilit kullanılabilir olana kadar iş parçacığı yürütmeyi engeller.|
|[omp_set_nest_lock](#omp-set-nest-lock)|Kilit kullanılabilir olana kadar iş parçacığı yürütmeyi engeller.|
|[omp_unset_lock](#omp-unset-lock)|Bir kilit yayınlar.|
|[omp_unset_nest_lock](#omp-unset-nest-lock)|İç içe konulabilir bir kilit yayınlar.|
|[omp_test_lock](#omp-test-lock)|Bir kilit ayarlamaya çalışır ancak iş parçacığı yürütmeyi engellemez.|
|[omp_test_nest_lock](#omp-test-nest-lock)|Bir iç içe konulabilir kilit ayarlamaya çalışır ancak iş parçacığı yürütmeyi engellemez.|

|Veri türü|Açıklama|
|---------|-----------|
|`omp_lock_t`|Kilidin mevcut olup olmadığı veya bir iş parçacığının bir kilide sahip olup olmadığı bir kilit durumunu tutan bir tür.|
|`omp_nest_lock_t`|Bir kilit hakkında aşağıdaki bilgi parçalarından birini tutan bir tür: kilidin olup olmadığı ve kilidin sahibi olan iş parçacığının kimliği ve iç içe bir sayı.|

Zamanlama yordamları için:

|İşlev|Açıklama|
|--------|-----------|
|[omp_get_wtime](#omp-get-wtime)|Belirli bir noktadan geçen sürenin saniye cinsinden bir değer döndürür.|
|[omp_get_wtick](#omp-get-wtick)|İşlemci saat işaretleri arasındaki saniye sayısını döndürür.|

## <a name="omp-destroy-lock"></a>omp_destroy_lock

Kilidin işaretini kaldırır.

```cpp
void omp_destroy_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
[Omp_init_lock](#omp-init-lock)ile başlatılan `omp_lock_t` türünde bir değişken.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.2.2 omp_destroy_lock ve omp_destroy_nest_lock işlevleri](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).

### <a name="example"></a>Örnek

`omp_destroy_lock`kullanma örneği için bkz. [omp_init_lock](#omp-init-lock) .

## <a name="omp-destroy-nest-lock"></a>omp_destroy_nest_lock

Bir iç içe konulabilir kilidi başlatır.

```cpp
void omp_destroy_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
[Omp_init_nest_lock](#omp-init-nest-lock)ile başlatılan `omp_nest_lock_t` türünde bir değişken.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.2.2 omp_destroy_lock ve omp_destroy_nest_lock işlevleri](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).

### <a name="example"></a>Örnek

`omp_destroy_nest_lock`kullanma örneği için bkz. [omp_init_nest_lock](#omp-init-nest-lock) .

## <a name="omp-get-dynamic"></a>omp_get_dynamic

Yaklaşan paralel bölgelerde kullanılabilir olan iş parçacıklarının sayısının çalışma zamanına göre ayarlanamayacağını gösteren bir değer döndürür.

```cpp
int omp_get_dynamic();
```

### <a name="return-value"></a>Dönüş değeri

Sıfır dışında bir değer, iş parçacıklarının dinamik olarak ayarlanmayacağı anlamına gelir.

### <a name="remarks"></a>Açıklamalar

İş parçacıklarının dinamik ayarlaması [omp_set_dynamic](#omp-set-dynamic) ve [OMP_DYNAMIC](openmp-environment-variables.md#omp-dynamic)ile belirtilir.

Daha fazla bilgi için bkz. [3.1.7 omp_set_dynamic işlevi](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).

### <a name="example"></a>Örnek

`omp_get_dynamic`kullanma örneği için bkz. [omp_set_dynamic](#omp-set-dynamic) .

## <a name="omp-get-max-threads"></a>omp_get_max_threads

Kodda bu noktada [num_threads](openmp-clauses.md#num-threads) olmayan bir paralel bölge tanımlanmışsa, kullanılabilecek iş parçacığı sayısına eşit veya ondan daha büyük bir tamsayı döndürür.

```cpp
int omp_get_max_threads( )
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.1.3 omp_get_max_threads işlevi](../../../parallel/openmp/3-1-3-omp-get-max-threads-function.md).

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

## <a name="omp-get-nested"></a>omp_get_nested

İç içe paralel paralellik etkin olup olmadığını gösteren bir değer döndürür.

```cpp
int omp_get_nested( );
```

### <a name="return-value"></a>Dönüş değeri

Sıfır dışında bir değer, iç içe paralellik özelliğinin etkinleştirildiği anlamına gelir.

### <a name="remarks"></a>Açıklamalar

İç içe paralellik [omp_set_nested](#omp-set-nested) ve [OMP_NESTED](openmp-environment-variables.md#omp-nested)ile belirtilir.

Daha fazla bilgi için bkz. [3.1.10 omp_get_nested işlevi](../../../parallel/openmp/3-1-10-omp-get-nested-function.md).

### <a name="example"></a>Örnek

`omp_get_nested`kullanma örneği için bkz. [omp_set_nested](#omp-set-nested) .

## <a name="omp-get-num-procs"></a>omp_get_num_procs

İşlev çağrıldığında kullanılabilir olan işlemcilerin sayısını döndürür.

```cpp
int omp_get_num_procs();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.1.5 omp_get_num_procs işlevi](../../../parallel/openmp/3-1-5-omp-get-num-procs-function.md).

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

## <a name="omp-get-num-threads"></a>omp_get_num_threads

Paralel bölgedeki iş parçacığı sayısını döndürür.

```cpp
int omp_get_num_threads( );
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.1.2 omp_get_num_threads işlevi](../../../parallel/openmp/3-1-2-omp-get-num-threads-function.md).

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

## <a name="omp-get-thread-num"></a>omp_get_thread_num

İş parçacığı ekibi içinde yürütülen iş parçacığının iş parçacığı numarasını döndürür.

```cpp
int omp_get_thread_num( );
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.1.4 omp_get_thread_num işlevi](../../../parallel/openmp/3-1-4-omp-get-thread-num-function.md).

### <a name="example"></a>Örnek

`omp_get_thread_num`kullanımı örneği için bkz. [paralel](openmp-directives.md#parallel) .

## <a name="omp-get-wtick"></a>omp_get_wtick

İşlemci saat işaretleri arasındaki saniye sayısını döndürür.

```cpp
double omp_get_wtick( );
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.3.2 omp_get_wtick işlevi](../../../parallel/openmp/3-3-2-omp-get-wtick-function.md).

### <a name="example"></a>Örnek

`omp_get_wtick`kullanma örneği için bkz. [omp_get_wtime](#omp-get-wtime) .

## <a name="omp-get-wtime"></a>omp_get_wtime

Belirli bir noktadan geçen sürenin saniye cinsinden bir değer döndürür.

```cpp
double omp_get_wtime( );
```

### <a name="return-value"></a>Dönüş değeri

Bazı rastgele, ancak tutarlı bir noktadan geçen sürenin saniye cinsinden bir değer döndürür.

### <a name="remarks"></a>Açıklamalar

Bu nokta program yürütmesi sırasında tutarlı kalacak ve yaklaşan karşılaştırmalar mümkün hale gelecek.

Daha fazla bilgi için bkz. [3.3.1 omp_get_wtime işlevi](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md).

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

## <a name="omp-in-parallel"></a>omp_in_parallel

Paralel bir bölgenin içinden çağrılırsa sıfır dışında bir değer döndürür.

```cpp
int omp_in_parallel( );
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.1.6 omp_in_parallel işlevi](../../../parallel/openmp/3-1-6-omp-in-parallel-function.md).

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

## <a name="omp-init-lock"></a>omp_init_lock

Basit bir kilit başlatır.

```cpp
void omp_init_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
`omp_lock_t`türünde bir değişken.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.2.1 omp_init_lock ve omp_init_nest_lock işlevleri](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md).

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

## <a name="omp-init-nest-lock"></a>omp_init_nest_lock

Bir kilidi başlatır.

```cpp
void omp_init_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
`omp_nest_lock_t`türünde bir değişken.

### <a name="remarks"></a>Açıklamalar

İlk iç içe geçme sayısı sıfırdır.

Daha fazla bilgi için bkz. [3.2.1 omp_init_lock ve omp_init_nest_lock işlevleri](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md).

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

## <a name="omp-set-dynamic"></a>omp_set_dynamic

Yaklaşan paralel bölgelerde kullanılabilen iş parçacıklarının sayısının çalışma zamanına göre ayarlanamayacağını gösterir.

```cpp
void omp_set_dynamic(
   int val
);
```

### <a name="parameters"></a>Parametreler

*Acil*<br/>
Yaklaşan paralel bölgelerde kullanılabilir olan iş parçacıklarının sayısının çalışma zamanı tarafından ayarlanamayacağını belirten bir değer. Sıfır değilse, çalışma zamanı iş parçacığı sayısını ayarlayabilir, sıfır ise çalışma zamanı iş parçacığı sayısını dinamik olarak ayarlamaz.

### <a name="remarks"></a>Açıklamalar

İş parçacığı sayısı [omp_set_num_threads](#omp-set-num-threads) veya [omp_num_threads](openmp-environment-variables.md#omp-num-threads)tarafından ayarlanan değeri hiçbir şekilde aşamaz.

Geçerli `omp_set_dynamic`ayarını göstermek için [omp_get_dynamic](#omp-get-dynamic) kullanın.

`omp_set_dynamic` ayarı [OMP_DYNAMIC](openmp-environment-variables.md#omp-dynamic) ortam değişkeninin ayarını geçersiz kılacaktır.

Daha fazla bilgi için bkz. [3.1.7 omp_set_dynamic işlevi](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).

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

## <a name="omp-set-lock"></a>omp_set_lock

Kilit kullanılabilir olana kadar iş parçacığı yürütmeyi engeller.

```cpp
void omp_set_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
[Omp_init_lock](#omp-init-lock)ile başlatılan `omp_lock_t` türünde bir değişken.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.2.3 omp_set_lock ve omp_set_nest_lock işlevleri](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).

### <a name="examples"></a>Örnekler

`omp_set_lock`kullanma örneği için bkz. [omp_init_lock](#omp-init-lock) .

## <a name="omp-set-nest-lock"></a>omp_set_nest_lock

Kilit kullanılabilir olana kadar iş parçacığı yürütmeyi engeller.

```cpp
void omp_set_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
[Omp_init_nest_lock](#omp-init-nest-lock)ile başlatılan `omp_nest_lock_t` türünde bir değişken.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.2.3 omp_set_lock ve omp_set_nest_lock işlevleri](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).

### <a name="examples"></a>Örnekler

`omp_set_nest_lock`kullanma örneği için bkz. [omp_init_nest_lock](#omp-init-nest-lock) .

## <a name="omp-set-nested"></a>omp_set_nested

İç içe paralellik kullanılmasına izin vermez.

```cpp
void omp_set_nested(
   int val
);
```

### <a name="parameters"></a>Parametreler

*Acil*<br/>
Sıfır dışında bir değer iç içe paralelliği mümkün olsa da sıfır iç içe paralelliği devre dışı bırakır

### <a name="remarks"></a>Açıklamalar

OMP iç içe paralelliği `omp_set_nested`veya [OMP_NESTED](openmp-environment-variables.md#omp-nested) ortam değişkeni ayarlanarak etkinleştirilebilir.

`omp_set_nested` ayarı `OMP_NESTED` ortam değişkeninin ayarını geçersiz kılacaktır.

Ortam değişkenini etkinleştirmek, bir veya daha fazla işlemsel programı bozabilir, çünkü iş parçacıklarının sayısı paralel bölgeleri yuvalama sırasında katlanarak üstel olarak artar. Örneğin, 4 olarak ayarlanan OMP iş parçacığı sayısı ile altı kez yinelenen bir işlev, 4.096 (6 ' ın kuvveti 4 ' e kadar) iş parçacığı gerektirir. G/ç bağlantılı uygulamalar haricinde bir uygulamanın performansı genellikle işlemcilerin daha fazla iş parçacığı varsa düşer.

Geçerli `omp_set_nested`ayarını göstermek için [omp_get_nested](#omp-get-nested) kullanın.

Daha fazla bilgi için bkz. [3.1.9 omp_set_nested işlevi](../../../parallel/openmp/3-1-9-omp-set-nested-function.md).

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

## <a name="omp-set-num-threads"></a>omp_set_num_threads

[Num_threads](openmp-clauses.md#num-threads) yan tümcesi tarafından geçersiz kılınmadıkça yaklaşan paralel bölgelerdeki iş parçacığı sayısını ayarlar.

```cpp
void omp_set_num_threads(
   int num_threads
);
```

### <a name="parameters"></a>Parametreler

*num_threads*<br/>
Paralel bölgedeki iş parçacığı sayısı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.1.1 omp_set_num_threads işlevi](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md).

### <a name="example"></a>Örnek

`omp_set_num_threads`kullanma örneği için bkz. [omp_get_num_threads](#omp-get-num-threads) .

## <a name="omp-test-lock"></a>omp_test_lock

Bir kilit ayarlamaya çalışır ancak iş parçacığı yürütmeyi engellemez.

```cpp
int omp_test_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
[Omp_init_lock](#omp-init-lock)ile başlatılan `omp_lock_t` türünde bir değişken.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.2.5 omp_test_lock ve omp_test_nest_lock işlevleri](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).

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

## <a name="omp-test-nest-lock"></a>omp_test_nest_lock

Bir iç içe konulabilir kilit ayarlamaya çalışır ancak iş parçacığı yürütmeyi engellemez.

```cpp
int omp_test_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
[Omp_init_nest_lock](#omp-init-nest-lock)ile başlatılan `omp_nest_lock_t` türünde bir değişken.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.2.5 omp_test_lock ve omp_test_nest_lock işlevleri](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).

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

## <a name="omp-unset-lock"></a>omp_unset_lock

Bir kilit yayınlar.

```cpp
void omp_unset_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
İş parçacığına ait olan ve işlevinde yürütülen [omp_init_lock](#omp-init-lock)ile başlatılan `omp_lock_t` türünde bir değişken.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.2.4 omp_unset_lock ve omp_unset_nest_lock işlevleri](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).

### <a name="example"></a>Örnek

`omp_unset_lock`kullanma örneği için bkz. [omp_init_lock](#omp-init-lock) .

## <a name="omp-unset-nest-lock"></a>omp_unset_nest_lock

İç içe konulabilir bir kilit yayınlar.

```cpp
void omp_unset_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
İş parçacığına ait olan ve işlevinde yürütülen [omp_init_nest_lock](#omp-init-nest-lock)ile başlatılan `omp_nest_lock_t` türünde bir değişken.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [3.2.4 omp_unset_lock ve omp_unset_nest_lock işlevleri](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).

### <a name="example"></a>Örnek

`omp_unset_nest_lock`kullanma örneği için bkz. [omp_init_nest_lock](#omp-init-nest-lock) .
