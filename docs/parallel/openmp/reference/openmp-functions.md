---
title: OpenMP işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 10/23/2018
ms.technology:
- cpp-parallel
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de3ea54a1526e7b340f804a21d990b6a691d0eee
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066428"
---
# <a name="openmp-functions"></a>OpenMP işlevleri

OpenMP API çağrısında kullanılan işlevlere bağlantılar sağlar.

Standart OpenMP Visual C++ uygulaması, aşağıdaki işlevleri içerir.

|İşlev|Açıklama|
|--------|-----------|
|[omp_destroy_lock](#omp-destroy-lock)|Kilit başlamasını iptal eder.|
|[omp_destroy_nest_lock](#omp-destroy-nest-lock)|Nestable kilit başlamasını iptal eder.|
|[omp_get_dynamic](#omp-get-dynamic)|Çalışma zamanı tarafından ayarlanabilir yaklaşan paralel bölgelerinde kullanılabilir iş parçacığı sayısını gösteren bir değer döndürür.|
|[omp_get_max_threads](#omp-get-max-threads)|Bir paralel bölgenin olmadan, kullanılabilir hale gelir, iş parçacığı sayısından büyük veya ona eşit bir tamsayı döndürür [num_threads](openmp-clauses.md#num-threads) o noktada kod tanımlanmadı.|
|[omp_get_nested](#omp-get-nested)|İç içe geçmiş paralellik etkin olup olmadığını gösteren bir değer döndürür.|
|[omp_get_num_procs](#omp-get-num-procs)|İşlev çağrıldığında, kullanılabilir işlemci sayısını döndürür.|
|[omp_get_num_threads](#omp-get-num-threads)|Paralel bölgenin içinde iş parçacıklarının sayısını döndürür.|
|[omp_get_thread_num](#omp-get-thread-num)|Kendi iş parçacığı takım içinde iş parçacığının iş parçacığı sayısını döndürür.|
|[omp_get_wtick](#omp-get-wtick)|İşlemci saatin tik takları saniye sayısını döndürür.|
|[omp_get_wtime](#omp-get-wtime)|Belirli bir noktada bir değer süresini saniye cinsinden geçen döndürür.|
|[omp_in_parallel](#omp-in-parallel)|Bir paralel bölgenin içinde çağrılırsa sıfır döndürür.|
|[omp_init_lock](#omp-init-lock)|Basit bir kilit başlatır.|
|[omp_init_nest_lock](#omp-init-nest-lock)|Kilit başlatır.|
|[omp_set_dynamic](#omp-set-dynamic)|Çalışma zamanı tarafından düzenlenip düzenlenmediğini yaklaşan paralel bölgelerinde kullanılabilir iş parçacığı sayısını gösterir.|
|[omp_set_lock](#omp-set-lock)|Kilit kullanılabilir oluncaya kadar blokları yürütme iş parçacığı.|
|[omp_set_nest_lock](#omp-set-nest-lock)|Kilit kullanılabilir oluncaya kadar blokları yürütme iş parçacığı.|
|[omp_set_nested](#omp-set-nested)|İç içe geçmiş paralellik etkinleştirir.|
|[omp_set_num_threads](#omp-set-num-threads)|İş parçacığı sayısını yaklaşan paralel bölgelerde tarafından geçersiz kılınmadığı sürece ayarlar bir [num_threads](openmp-clauses.md#num-threads) yan tümcesi.|
|[omp_test_lock](#omp-test-lock)|Kilit ayarlamaya çalışır, ancak yürütme iş parçacığını engellemez.|
|[omp_test_nest_lock](#omp-test-nest-lock)|Nestable kilit ayarlamaya çalışır, ancak yürütme iş parçacığını engellemez.|
|[omp_unset_lock](#omp-unset-lock)|Bir kilidi serbest bırakır.|
|[omp_unset_nest_lock](#omp-unset-nest-lock)|Nestable kilit serbest bırakır.|

## <a name="omp-destroy-lock"></a>omp_destroy_lock

Kilit başlamasını iptal eder.

```
void omp_destroy_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Türünde bir değişken [omp_lock_t](openmp-data-types.md#omp-lock-t) , başlatılan ile [omp_init_lock](#omp-init-lock).

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.2 omp_destroy_lock ve omp_destroy_nest_lock işlevleri](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).

### <a name="example"></a>Örnek

Bkz: [omp_init_lock](#omp-init-lock) kullanma örneği için `omp_destroy_lock`.

## <a name="omp-destroy-nest-lock"></a>omp_destroy_nest_lock

Nestable kilit başlamasını iptal eder.

```
void omp_destroy_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Türünde bir değişken [omp_nest_lock_t](openmp-data-types.md#omp-nest-lock-t) , başlatılan ile [omp_init_nest_lock](#omp-init-nest-lock).

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.2 omp_destroy_lock ve omp_destroy_nest_lock işlevleri](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).

### <a name="example"></a>Örnek

Bkz: [omp_init_nest_lock](#omp-init-nest-lock) kullanma örneği için `omp_destroy_nest_lock`.

## <a name="omp-get-dynamic"></a>omp_get_dynamic

Çalışma zamanı tarafından ayarlanabilir yaklaşan paralel bölgelerinde kullanılabilir iş parçacığı sayısını gösteren bir değer döndürür.

```
int omp_get_dynamic();
```

### <a name="return-value"></a>Dönüş değeri

Sıfır dışında bir değeri, iş parçacıkları dinamik olarak ayarlanacak anlamına gelir.

### <a name="remarks"></a>Açıklamalar

İş parçacıkları yerleştirmenin dinamik ayarına belirtilirse [omp_set_dynamic](#omp-set-dynamic) ve [omp_dynamıc](openmp-environment-variables.md#omp-dynamic).

Daha fazla bilgi için [3.1.7 omp_set_dynamic işlevi](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).

### <a name="example"></a>Örnek

Bkz: [omp_set_dynamic](#omp-set-dynamic) kullanma örneği için `omp_get_dynamic`.

## <a name="omp-get-max-threads"></a>omp_get_max_threads

Bir paralel bölgenin olmadan, kullanılabilir hale gelir, iş parçacığı sayısından büyük veya ona eşit bir tamsayı döndürür [num_threads](openmp-clauses.md#num-threads) o noktada kod tanımlanmadı.

```
int omp_get_max_threads( )
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.1.3 omp_get_max_threads işlevi](../../../parallel/openmp/3-1-3-omp-get-max-threads-function.md).

### <a name="example"></a>Örnek

```
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

İç içe geçmiş paralellik etkin olup olmadığını gösteren bir değer döndürür.

```
int omp_get_nested( );
```

### <a name="return-value"></a>Dönüş değeri

Sıfır dışında bir değeri, iç içe geçmiş paralellik etkin anlamına gelir.

### <a name="remarks"></a>Açıklamalar

İç içe geçmiş paralellik belirtilirse [omp_set_nested](#omp-set-nested) ve [OMP_NESTED](openmp-environment-variables.md#omp-nested).

Daha fazla bilgi için [3.1.10 omp_get_nested işlevi](../../../parallel/openmp/3-1-10-omp-get-nested-function.md).

### <a name="example"></a>Örnek

Bkz: [omp_set_nested](#omp-set-nested) kullanma örneği için `omp_get_nested`.

## <a name="omp-get-num-procs"></a>omp_get_num_procs

İşlev çağrıldığında, kullanılabilir işlemci sayısını döndürür.

```
int omp_get_num_procs();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.1.5 omp_get_num_procs işlevi](../../../parallel/openmp/3-1-5-omp-get-num-procs-function.md).

### <a name="example"></a>Örnek

```
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

Paralel bölgenin içinde iş parçacıklarının sayısını döndürür.

```
int omp_get_num_threads( );
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.1.2 omp_get_num_threads işlevi](../../../parallel/openmp/3-1-2-omp-get-num-threads-function.md).

### <a name="example"></a>Örnek

```
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

Kendi iş parçacığı takım içinde iş parçacığının iş parçacığı sayısını döndürür.

```
int omp_get_thread_num( );
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.1.4 omp_get_thread_num işlevi](../../../parallel/openmp/3-1-4-omp-get-thread-num-function.md).

### <a name="example"></a>Örnek

Bkz: [paralel](openmp-directives.md#parallel) kullanma örneği için `omp_get_thread_num`.

## <a name="omp-get-wtick"></a>omp_get_wtick

İşlemci saatin tik takları saniye sayısını döndürür.

```
double omp_get_wtick( );
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.3.2 omp_get_wtick işlevi](../../../parallel/openmp/3-3-2-omp-get-wtick-function.md).

### <a name="example"></a>Örnek

Bkz: [omp_get_wtime](#omp-get-wtime) kullanma örneği için `omp_get_wtick`.

## <a name="omp-get-wtime"></a>omp_get_wtime

Belirli bir noktada bir değer süresini saniye cinsinden geçen döndürür.

```
double omp_get_wtime( );
```

### <a name="return-value"></a>Dönüş değeri

Bazı rastgele, ancak tutarlı noktasından bir değer süresini saniye cinsinden geçen döndürür.

### <a name="remarks"></a>Açıklamalar

O noktadan yaklaşan karşılaştırmalar büyük/küçük harfe edinerek program yürütme sırasında tutarlı kalır.

Daha fazla bilgi için [3.3.1 omp_get_wtime işlevi](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md).

### <a name="example"></a>Örnek

```
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

Bir paralel bölgenin içinde çağrılırsa sıfır döndürür.

```
int omp_in_parallel( );
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.1.6 omp_in_parallel işlevi](../../../parallel/openmp/3-1-6-omp-in-parallel-function.md).

### <a name="example"></a>Örnek

```
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

```
void omp_init_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Türünde bir değişken [omp_lock_t](openmp-data-types.md#omp-lock-t).

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.1 omp_init_lock ve omp_init_nest_lock işlevleri](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md).

### <a name="example"></a>Örnek

```
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

Kilit başlatır.

```
void omp_init_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Türünde bir değişken [omp_nest_lock_t](openmp-data-types.md#omp-nest-lock-t).

### <a name="remarks"></a>Açıklamalar

İlk iç içe geçme sayısı sıfır olur.

Daha fazla bilgi için [3.2.1 omp_init_lock ve omp_init_nest_lock işlevleri](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md).

### <a name="example"></a>Örnek

```
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

Çalışma zamanı tarafından düzenlenip düzenlenmediğini yaklaşan paralel bölgelerinde kullanılabilir iş parçacığı sayısını gösterir.

```
void omp_set_dynamic(
   int val
);
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
Çalışma zamanı tarafından ayarlanabilir yaklaşan paralel bölgelerinde kullanılabilir iş parçacığı sayısını belirten bir değer.  Sıfır olmayan, çalışma zamanı iş parçacığı sayısı sıfır ise ayarlayabilirsiniz, çalışma zamanı iş parçacığı sayısını dinamik olarak ayarlamak olmaz.

### <a name="remarks"></a>Açıklamalar

İş parçacığı sayısı ayarlanan değer hiçbir zaman aşacak [omp_set_num_threads](#omp-set-num-threads) ya da [OMP_NUM_THREADS](openmp-environment-variables.md#omp-num-threads).

Kullanım [omp_get_dynamic](#omp-get-dynamic) geçerli ayarını görüntülemek için `omp_set_dynamic`.

Ayarı `omp_set_dynamic` ayarını geçersiz kılar [omp_dynamıc](openmp-environment-variables.md#omp-dynamic) ortam değişkeni.

Daha fazla bilgi için [3.1.7 omp_set_dynamic işlevi](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).

### <a name="example"></a>Örnek

```
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

Kilit kullanılabilir oluncaya kadar blokları yürütme iş parçacığı.

```
void omp_set_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Türünde bir değişken [omp_lock_t](openmp-data-types.md#omp-lock-t) , başlatılan ile [omp_init_lock](#omp-init-lock).

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.3 omp_set_lock ve omp_set_nest_lock işlevleri](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).

### <a name="examples"></a>Örnekler

Bkz: [omp_init_lock](#omp-init-lock) kullanma örneği için `omp_set_lock`.

## <a name="omp-set-nest-lock"></a>omp_set_nest_lock

Kilit kullanılabilir oluncaya kadar blokları yürütme iş parçacığı.

```
void omp_set_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Türünde bir değişken [omp_nest_lock_t](openmp-data-types.md#omp-nest-lock-t) , başlatılan ile [omp_init_nest_lock](#omp-init-nest-lock).

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.3 omp_set_lock ve omp_set_nest_lock işlevleri](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).

### <a name="examples"></a>Örnekler

Bkz: [omp_init_nest_lock](#omp-init-nest-lock) kullanma örneği için `omp_set_nest_lock`.

## <a name="omp-set-nested"></a>omp_set_nested

İç içe geçmiş paralellik etkinleştirir.

```
void omp_set_nested(
   int val
);
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
Sıfır dışında bir değeri sıfır iç içe geçmiş paralellik devre dışı bırakır. iç içe geçmiş paralellik etkinleştirir.

### <a name="remarks"></a>Açıklamalar

İç içe geçmiş OMP paralellik açılabilir ile `omp_set_nested`, ayarlayarak [OMP_NESTED](openmp-environment-variables.md#omp-nested) ortam değişkeni.

Ayarı `omp_set_nested` ayarını geçersiz kılar `OMP_NESTED` ortam değişkeni.

Ortam değişkenini etkinleştirme paralel bölgeleri iç içe olduğunda iş parçacığı sayısı katlanarak artar çünkü aksi işletimsel bir programı bozabilir.  Örneğin, 4'e ayarlayın OMP iş parçacığı sayısı ile altı kat recurses bir işlev 4.096 (6'ın gücünü 4) gerektiren iş parçacıkları. İşlemci değerinden daha fazla iş parçacığı varsa dışında miyim/O-bağlı uygulamalar ile uygulama performansını genellikle düşürür.

Kullanım [omp_get_nested](#omp-get-nested) geçerli ayarını görüntülemek için `omp_set_nested`.

Daha fazla bilgi için [3.1.9 omp_set_nested işlevi](../../../parallel/openmp/3-1-9-omp-set-nested-function.md).

### <a name="example"></a>Örnek

```
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

İş parçacığı sayısını yaklaşan paralel bölgelerde tarafından geçersiz kılınmadığı sürece ayarlar bir [num_threads](openmp-clauses.md#num-threads) yan tümcesi.

```
void omp_set_num_threads(
   int num_threads
);
```

### <a name="parameters"></a>Parametreler

*num_threads*<br/>
Paralel bölgenin içinde iş parçacığı sayısı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.1.1 omp_set_num_threads işlevi](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md).

### <a name="example"></a>Örnek

Bkz: [omp_get_num_threads](#omp-get-num-threads) kullanma örneği için `omp_set_num_threads`.

## <a name="omp-test-lock"></a>omp_test_lock

Kilit ayarlamaya çalışır, ancak yürütme iş parçacığını engellemez.

```
int omp_test_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Türünde bir değişken [omp_lock_t](openmp-data-types.md#omp-lock-t) , başlatılan ile [omp_init_lock](#omp-init-lock).

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.5 omp_test_lock ve omp_test_nest_lock işlevleri](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).

### <a name="example"></a>Örnek

```
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

Nestable kilit ayarlamaya çalışır, ancak yürütme iş parçacığını engellemez.

```
int omp_test_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Türünde bir değişken [omp_nest_lock_t](openmp-data-types.md#omp-nest-lock-t) , başlatılan ile [omp_init_nest_lock](#omp-init-nest-lock).

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.5 omp_test_lock ve omp_test_nest_lock işlevleri](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).

### <a name="example"></a>Örnek

```
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

Bir kilidi serbest bırakır.

```
void omp_unset_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Türünde bir değişken [omp_lock_t](openmp-data-types.md#omp-lock-t) , başlatılan ile [omp_init_lock](#omp-init-lock), iş parçacığı tarafından sahip olunan ve işlev yürütme.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.4 omp_unset_lock ve omp_unset_nest_lock işlevleri](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).

### <a name="example"></a>Örnek

Bkz: [omp_init_lock](#omp-init-lock) kullanma örneği için `omp_unset_lock`.

## <a name="omp-unset-nest-lock"></a>omp_unset_nest_lock

Nestable kilit serbest bırakır.

```
void omp_unset_nest_lock( 
   omp_nest_lock_t *lock 
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
Türünde bir değişken [omp_nest_lock_t](openmp-data-types.md#omp-nest-lock-t) , başlatılan ile [omp_init_nest_lock](#omp-init-nest-lock), iş parçacığı tarafından sahip olunan ve işlev yürütme.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [3.2.4 omp_unset_lock ve omp_unset_nest_lock işlevleri](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).

### <a name="example"></a>Örnek

Bkz: [omp_init_nest_lock](#omp-init-nest-lock) kullanma örneği için `omp_unset_nest_lock`.
