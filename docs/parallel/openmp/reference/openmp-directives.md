---
title: OpenMP Yönergeleri
ms.date: 03/20/2019
f1_keywords:
- OpenMP directives
- atomic
- barrier
- critical
- flush
- for
- master
- parallel
- section
- single
- threadprivate
helpviewer_keywords:
- OpenMP directives
- atomic OpenMP directive
- barrier OpenMP directive
- critical OpenMP directive
- flush OpenMP directive
- for OpenMP directive
- master OpenMP directive
- ordered OpenMP directive
- parallel OpenMP directive
- sections OpenMP directive
- single OpenMP directive
- threadprivate OpenMP directive
ms.assetid: 0562c263-344c-466d-843e-de830d918940
ms.openlocfilehash: 569419b3422b155afc6e9692efaecd4e5a06f188
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366440"
---
# <a name="openmp-directives"></a>OpenMP Yönergeleri

OpenMP API'de kullanılan yönergelere bağlantılar sağlar.

Visual C++ aşağıdaki OpenMP yönergelerini destekler.

Paralel iş paylaşımı için:

|Yönergesi|Açıklama|
|---------|-----------|
|[parallel](#parallel)|Paralel olarak birden çok iş parçacığı tarafından yürütülecek kod olan paralel bir bölge tanımlar.|
|[for](#for-openmp)|Paralel bir bölge `for` içinde bir döngü içinde yapılan işin iş parçacıkları arasında bölünmesine neden olur.|
|[sections](#sections-openmp)|Tüm iş parçacıkları arasında bölünecek kod bölümlerini tanımlar.|
|[Tek](#single)|Kod bölümünün ana iş parçacığı için değil, tek bir iş parçacığı üzerinde yürütülmesi gerektiğini belirtmenizi sağlar.|

Ana ve senkronizasyon için:

|Yönergesi|Açıklama|
|---------|-----------|
|[ana](#master)|Programın bir bölümünü yalnızca ana iş parçacığının yürütmesi gerektiğini belirtir.|
|[Kritik](#critical)|Bu kodun aynı anda yalnızca bir iş parçacığı üzerinde yürütüldedildiğini belirtir.|
|[Bariyer](#barrier)|Takımdaki tüm iş parçacıklarını eşitler; tüm iş parçacıkları bariyeri çalıştırana kadar tüm iş parçacıkları bariyerde duraklar.|
|[atomic](#atomic)|Atomik olarak güncellenecek bir bellek konumu belirtir.|
|[flush](#flush-openmp)|Tüm iş parçacıklarının paylaşılan tüm nesneler için aynı bellek görünümüne sahip olduğunu belirtir.|
|[Sipariş](#ordered-openmp-directives)|Paralelleştirilmiş `for` bir döngü altındaki kodun sıralı bir döngü gibi yürütülmesi gerektiğini belirtir.|

Veri ortamı için:

|Yönergesi|Açıklama|
|---------|-----------|
|[threadprivate](#threadprivate)|Bir değişkenin bir iş parçacığına özel olduğunu belirtir.|

## <a name="atomic"></a><a name="atomic"></a>Atom

Atomik olarak güncellenecek bir bellek konumu belirtir.

```cpp
#pragma omp atomic
   expression
```

### <a name="parameters"></a>Parametreler

*Ifa -de*<br/>
Birden fazla yazıya karşı korumak istediğiniz *lvalue*olan ifade.

### <a name="remarks"></a>Açıklamalar

Yönerge `atomic` hiçbir yan tümceyi desteklemez.

Daha fazla bilgi için [bkz: 2.6.4 atomik yapı.](../../../parallel/openmp/2-6-4-atomic-construct.md)

### <a name="example"></a>Örnek

```cpp
// omp_atomic.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

#define MAX 10

int main() {
   int count = 0;
   #pragma omp parallel num_threads(MAX)
   {
      #pragma omp atomic
      count++;
   }
   printf_s("Number of threads: %d\n", count);
}
```

```Output
Number of threads: 10
```

## <a name="barrier"></a><a name="barrier"></a>Bariyer

Takımdaki tüm iş parçacıklarını eşitler; tüm iş parçacıkları bariyeri çalıştırana kadar tüm iş parçacıkları bariyerde duraklar.

```cpp
#pragma omp barrier
```

### <a name="remarks"></a>Açıklamalar

Yönerge `barrier` hiçbir yan tümceyi desteklemez.

Daha fazla bilgi için [bkz: 2.6.3 bariyer direktifi.](../../../parallel/openmp/2-6-3-barrier-directive.md)

### <a name="example"></a>Örnek

Nasıl kullanılacağına `barrier`bir örnek için, [bkz.](#master)

## <a name="critical"></a><a name="critical"></a>Kritik

Kodun aynı anda yalnızca bir iş parçacığı üzerinde yürütüleceğini belirtir.

```cpp
#pragma omp critical [(name)]
{
   code_block
}
```

### <a name="parameters"></a>Parametreler

*Adı*<br/>
(İsteğe bağlı) Kritik kodu tanımlamak için bir ad. Ad parantez içinde eklenmelidir.

### <a name="remarks"></a>Açıklamalar

Yönerge `critical` hiçbir yan tümceyi desteklemez.

Daha fazla bilgi için [bkz: 2.6.2 kritik yapı.](../../../parallel/openmp/2-6-2-critical-construct.md)

### <a name="example"></a>Örnek

```cpp
// omp_critical.cpp
// compile with: /openmp
#include <omp.h>
#include <stdio.h>
#include <stdlib.h>

#define SIZE 10

int main()
{
    int i;
    int max;
    int a[SIZE];

    for (i = 0; i < SIZE; i++)
    {
        a[i] = rand();
        printf_s("%d\n", a[i]);
    }

    max = a[0];
    #pragma omp parallel for num_threads(4)
        for (i = 1; i < SIZE; i++)
        {
            if (a[i] > max)
            {
                #pragma omp critical
                {
                    // compare a[i] and max again because max
                    // could have been changed by another thread after
                    // the comparison outside the critical section
                    if (a[i] > max)
                        max = a[i];
                }
            }
        }

    printf_s("max = %d\n", max);
}
```

```Output
41
18467
6334
26500
19169
15724
11478
29358
26962
24464
max = 29358
```

## <a name="flush"></a><a name="flush-openmp"></a>Flush

Tüm iş parçacıklarının paylaşılan tüm nesneler için aynı bellek görünümüne sahip olduğunu belirtir.

```cpp
#pragma omp flush [(var)]
```

### <a name="parameters"></a>Parametreler

*var*<br/>
(İsteğe bağlı) Eşitlemek istediğiniz nesneleri temsil eden virgülle ayrılmış değişkenler listesi. *Var* belirtilmemişse, tüm bellek temizlenir.

### <a name="remarks"></a>Açıklamalar

Yönerge `flush` hiçbir yan tümceyi desteklemez.

Daha fazla bilgi için [bkz: 2.6.5 floş yönergesi.](../../../parallel/openmp/2-6-5-flush-directive.md)

### <a name="example"></a>Örnek

```cpp
// omp_flush.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

void read(int *data) {
   printf_s("read data\n");
   *data = 1;
}

void process(int *data) {
   printf_s("process data\n");
   (*data)++;
}

int main() {
   int data;
   int flag;

   flag = 0;

   #pragma omp parallel sections num_threads(2)
   {
      #pragma omp section
      {
         printf_s("Thread %d: ", omp_get_thread_num( ));
         read(&data);
         #pragma omp flush(data)
         flag = 1;
         #pragma omp flush(flag)
         // Do more work.
      }

      #pragma omp section
      {
         while (!flag) {
            #pragma omp flush(flag)
         }
         #pragma omp flush(data)

         printf_s("Thread %d: ", omp_get_thread_num( ));
         process(&data);
         printf_s("data = %d\n", data);
      }
   }
}
```

```Output
Thread 0: read data
Thread 1: process data
data = 2
```

## <a name="for"></a><a name="for-openmp"></a>Için

Paralel bir bölge `for` içinde bir döngü içinde yapılan işin iş parçacıkları arasında bölünmesine neden olur.

```cpp
#pragma omp [parallel] for [clauses]
   for_statement
```

### <a name="parameters"></a>Parametreler

*Yan tümce*<br/>
(İsteğe bağlı) Sıfır veya daha fazla yan tümce, **Açıklamalar** bölümüne bakın.

*for_statement*<br/>
Bir `for` döngü. Döngüdeki kullanıcı kodu dizin `for` değişkenini değiştirirse tanımlanmamış davranış ortaya çıkacaktır.

### <a name="remarks"></a>Açıklamalar

`for` Yönerge aşağıdaki maddeleri destekler:

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [Sipariş](openmp-clauses.md#ordered-openmp-clauses)
- [Zamanlama](openmp-clauses.md#schedule)
- [nowait](openmp-clauses.md#nowait)

Ayrıca `parallel` `clauses` belirtilirse, herhangi bir yan `parallel` tümce si olabilir veya `for` direktifler tarafından kabul edilebilir, dışında `nowait`.

Daha fazla bilgi [için yapı için 2.4.1'e](../../../parallel/openmp/2-4-1-for-construct.md)bakın.

### <a name="example"></a>Örnek

```cpp
// omp_for.cpp
// compile with: /openmp
#include <stdio.h>
#include <math.h>
#include <omp.h>

#define NUM_THREADS 4
#define NUM_START 1
#define NUM_END 10

int main() {
   int i, nRet = 0, nSum = 0, nStart = NUM_START, nEnd = NUM_END;
   int nThreads = 0, nTmp = nStart + nEnd;
   unsigned uTmp = (unsigned((abs(nStart - nEnd) + 1)) *
                               unsigned(abs(nTmp))) / 2;
   int nSumCalc = uTmp;

   if (nTmp < 0)
      nSumCalc = -nSumCalc;

   omp_set_num_threads(NUM_THREADS);

   #pragma omp parallel default(none) private(i) shared(nSum, nThreads, nStart, nEnd)
   {
      #pragma omp master
      nThreads = omp_get_num_threads();

      #pragma omp for
      for (i=nStart; i<=nEnd; ++i) {
            #pragma omp atomic
            nSum += i;
      }
   }

   if  (nThreads == NUM_THREADS) {
      printf_s("%d OpenMP threads were used.\n", NUM_THREADS);
      nRet = 0;
   }
   else {
      printf_s("Expected %d OpenMP threads, but %d were used.\n",
               NUM_THREADS, nThreads);
      nRet = 1;
   }

   if (nSum != nSumCalc) {
      printf_s("The sum of %d through %d should be %d, "
               "but %d was reported!\n",
               NUM_START, NUM_END, nSumCalc, nSum);
      nRet = 1;
   }
   else
      printf_s("The sum of %d through %d is %d\n",
               NUM_START, NUM_END, nSum);
}
```

```Output
4 OpenMP threads were used.
The sum of 1 through 10 is 55
```

## <a name="master"></a><a name="master"></a>Master

Programın bir bölümünü yalnızca ana iş parçacığının yürütmesi gerektiğini belirtir.

```cpp
#pragma omp master
{
   code_block
}
```

### <a name="remarks"></a>Açıklamalar

Yönerge `master` hiçbir yan tümceyi desteklemez.

[Tek](#single) yönerge, kod bölümünün ana iş parçacığı için değil, tek bir iş parçacığı üzerinde yürütülmesi gerektiğini belirtmenizi sağlar.

Daha fazla bilgi için [bkz: 2.6.1 ana yapı.](../../../parallel/openmp/2-6-1-master-construct.md)

### <a name="example"></a>Örnek

```cpp
// omp_master.cpp
// compile with: /openmp
#include <omp.h>
#include <stdio.h>

int main( )
{
    int a[5], i;

    #pragma omp parallel
    {
        // Perform some computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] = i * i;

        // Print intermediate results.
        #pragma omp master
            for (i = 0; i < 5; i++)
                printf_s("a[%d] = %d\n", i, a[i]);

        // Wait.
        #pragma omp barrier

        // Continue with the computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] += i;
    }
}
```

```Output
a[0] = 0
a[1] = 1
a[2] = 4
a[3] = 9
a[4] = 16
```

## <a name="ordered"></a><a name="ordered-openmp-directives"></a>Sipariş

Paralelleştirilmiş `for` bir döngü altındaki kodun sıralı bir döngü gibi yürütülmesi gerektiğini belirtir.

```cpp
#pragma omp ordered
   structured-block
```

### <a name="remarks"></a>Açıklamalar

Yönerge, `ordered` bir `ordered` madde ile [bir](#for-openmp) `parallel for` for veya construct dinamik kapsamı içinde olmalıdır.

Yönerge `ordered` hiçbir yan tümceyi desteklemez.

Daha fazla bilgi için bkz: [2.6.6 sıralı yapı.](../../../parallel/openmp/2-6-6-ordered-construct.md)

### <a name="example"></a>Örnek

```cpp
// omp_ordered.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

static float a[1000], b[1000], c[1000];

void test(int first, int last)
{
    #pragma omp for schedule(static) ordered
    for (int i = first; i <= last; ++i) {
        // Do something here.
        if (i % 2)
        {
            #pragma omp ordered
            printf_s("test() iteration %d\n", i);
        }
    }
}

void test2(int iter)
{
    #pragma omp ordered
    printf_s("test2() iteration %d\n", iter);
}

int main( )
{
    int i;
    #pragma omp parallel
    {
        test(1, 8);
        #pragma omp for ordered
        for (i = 0 ; i < 5 ; i++)
            test2(i);
    }
}
```

```Output
test() iteration 1
test() iteration 3
test() iteration 5
test() iteration 7
test2() iteration 0
test2() iteration 1
test2() iteration 2
test2() iteration 3
test2() iteration 4
```

## <a name="parallel"></a><a name="parallel"></a>Paralel

Paralel olarak birden çok iş parçacığı tarafından yürütülecek kod olan paralel bir bölge tanımlar.

```cpp
#pragma omp parallel [clauses]
{
   code_block
}
```

### <a name="parameters"></a>Parametreler

*Yan tümce*<br/>
(İsteğe bağlı) Sıfır veya daha fazla yan tümce, **Açıklamalar** bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

`parallel` Yönerge aşağıdaki maddeleri destekler:

- [if](openmp-clauses.md#if-openmp)
- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [default](openmp-clauses.md#default-openmp)
- [Paylaşılan](openmp-clauses.md#shared-openmp)
- [copyin](openmp-clauses.md#copyin)
- [reduction](openmp-clauses.md#reduction)
- [num_threads](openmp-clauses.md#num-threads)

`parallel`[for](#for-openmp) ve [bölüm](#sections-openmp) direktifleri ile de kullanılabilir.

Daha fazla bilgi için bkz: [2.3 paralel yapı.](../../../parallel/openmp/2-3-parallel-construct.md)

### <a name="example"></a>Örnek

Aşağıdaki örnek, iş parçacığı sayısını nasıl ayarlayacaklarını ve paralel bir bölge nasıl tanımlanacaklarını gösterir. İş parçacığı sayısı varsayılan olarak makinedeki mantıksal işlemci sayısına eşittir. Örneğin, hiperiş iş parçacığı etkin olan bir fiziksel işlemciye sahip bir makineniz varsa, iki mantıksal işlemcive iki iş parçacığı olacaktır. Çıkış sırası farklı makinelerde değişebilir.

```cpp
// omp_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
   #pragma omp parallel num_threads(4)
   {
      int i = omp_get_thread_num();
      printf_s("Hello from thread %d\n", i);
   }
}
```

```Output
Hello from thread 0
Hello from thread 1
Hello from thread 2
Hello from thread 3
```

## <a name="sections"></a><a name="sections-openmp"></a>Bölüm

Tüm iş parçacıkları arasında bölünecek kod bölümlerini tanımlar.

```cpp
#pragma omp [parallel] sections [clauses]
{
   #pragma omp section
   {
      code_block
   }
}
```

### <a name="parameters"></a>Parametreler

*Yan tümce*<br/>
(İsteğe bağlı) Sıfır veya daha fazla yan tümce, **Açıklamalar** bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

`sections` Yönerge sıfır veya `section` daha fazla yönerge içerebilir.

`sections` Yönerge aşağıdaki maddeleri destekler:

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [nowait](openmp-clauses.md#nowait)

Ayrıca `parallel` `clauses` belirtilirse, herhangi bir yan `parallel` tümce si olabilir veya `sections` direktifler tarafından kabul edilebilir, dışında `nowait`.

Daha fazla bilgi için bkz: [2.4.2 bölümleri oluşturmak.](../../../parallel/openmp/2-4-2-sections-construct.md)

### <a name="example"></a>Örnek

```cpp
// omp_sections.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
    #pragma omp parallel sections num_threads(4)
    {
        printf_s("Hello from thread %d\n", omp_get_thread_num());
        #pragma omp section
        printf_s("Hello from thread %d\n", omp_get_thread_num());
    }
}
```

```Output
Hello from thread 0
Hello from thread 0
```

## <a name="single"></a><a name="single"></a>Tek

Kod bölümünün ana iş parçacığı için değil, tek bir iş parçacığı üzerinde yürütülmesi gerektiğini belirtmenizi sağlar.

```cpp
#pragma omp single [clauses]
{
   code_block
}
```

### <a name="parameters"></a>Parametreler

*Yan tümce*<br/>
(İsteğe bağlı) Sıfır veya daha fazla yan tümce, **Açıklamalar** bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

`single` Yönerge aşağıdaki maddeleri destekler:

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [copyprivate](openmp-clauses.md#copyprivate)
- [nowait](openmp-clauses.md#nowait)

[Ana](#master) yönerge, kod bölümünün yalnızca ana iş parçacığı üzerinde yürütülmesi gerektiğini belirtmenizi sağlar.

Daha fazla bilgi için [bkz: 2.4.3 tek yapı.](../../../parallel/openmp/2-4-3-single-construct.md)

### <a name="example"></a>Örnek

```cpp
// omp_single.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
   #pragma omp parallel num_threads(2)
   {
      #pragma omp single
      // Only a single thread can read the input.
      printf_s("read input\n");

      // Multiple threads in the team compute the results.
      printf_s("compute results\n");

      #pragma omp single
      // Only a single thread can write the output.
      printf_s("write output\n");
    }
}
```

```Output
read input
compute results
compute results
write output
```

## <a name="threadprivate"></a><a name="threadprivate"></a>Threadprivate

Bir değişkenin bir iş parçacığına özel olduğunu belirtir.

```cpp
#pragma omp threadprivate(var)
```

### <a name="parameters"></a>Parametreler

*var*<br/>
Bir iş parçacığına özel yapmak istediğiniz değişkenlerin virgülle ayrılmış listesi. *var* global veya ad alanı kapsamlı değişken veya yerel statik değişken olmalıdır.

### <a name="remarks"></a>Açıklamalar

Yönerge `threadprivate` hiçbir yan tümceyi desteklemez.

Yönerge, `threadprivate` [__declspec](../../../cpp/declspec.md) anahtar sözcüğü kullanarak [iş parçacığı](../../../cpp/thread.md) özniteliğine dayanır; limitleri `__declspec(thread)` `threadprivate`uygulanır. Örneğin, işlemde başlatılan herhangi bir iş parçacığında bir `threadprivate` değişken bulunur, sadece paralel bir bölge tarafından oluşturulan iş parçacığı ekibinin parçası olan iş parçacıkları değil. Bu uygulama ayrıntılarına dikkat edin; kullanıcı tanımlı bir `threadprivate` tür için oluşturucuların daha sık çağrıldığını fark edebilirsiniz.

İşlem başlatmaişleminde statik olarak yüklenen bir DLL'de `threadprivate` kullanabilirsiniz, `threadprivate` ancak [/DELAYLOAD (gecikme yükü alma)](../../../build/reference/delayload-delay-load-import.md)ile yüklenen DL'ler (gecikme yükü alma) gibi `LoadLibrary` [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) üzerinden yüklenecek herhangi bir DLL'de kullanamazsınız.

Yok `threadprivate` *edilebilir* bir türde bir değişkenin yok edici nin çağrılması garanti edilemez. Örneğin:

```cpp
struct MyType
{
    ~MyType();
};

MyType threaded_var;
#pragma omp threadprivate(threaded_var)
int main()
{
    #pragma omp parallel
    {}
}
```

Kullanıcıların paralel bölgeyi oluşturan iş parçacıklarının ne zaman sona ereceği konusunda hiçbir denetimi yoktur. İşlem çıktığında bu iş parçacıkları varsa, iş parçacıkları işlem çıkışı hakkında bilgilendirilmez ve çıkan (burada, birincil iş `threaded_var` parçacığı) dışında herhangi bir iş parçacığı için yıkıcı çağrılmaz. Yani kod değişkenlerin düzgün bir `threadprivate` şekilde yok edilmesine güvenmemeli.

Daha fazla bilgi için bkz: [2.7.1 threadprivate yönergesi.](../../../parallel/openmp/2-7-1-threadprivate-directive.md)

### <a name="example"></a>Örnek

Kullanma `threadprivate`örneği için [bkz.](openmp-clauses.md#private-openmp)
