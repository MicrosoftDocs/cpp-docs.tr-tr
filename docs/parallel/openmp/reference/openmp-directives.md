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
- ordered
- parallel
- section
- SECTIONS
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
ms.openlocfilehash: d644b612c0c326692786c94046d799163dfbce8d
ms.sourcegitcommit: 14b292596bc9b9b883a9c58cd3e366b282a1f7b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60124960"
---
# <a name="openmp-directives"></a>OpenMP Yönergeleri

OpenMP API çağrısında kullanılan yönergelere bağlantılar sağlar.

Görsel C++ aşağıdaki OpenMP yönergeleri destekler.

Paralel iş paylaşım için:

|Yönergesi|Açıklama|
|---------|-----------|
|[parallel](#parallel)|Birden çok iş parçacığı paralel olarak yürütülen kodu bir paralel bölgenin tanımlar.|
|[for](#for-openmp)|Çalışmanın neden olan bir `for` döngüsü iş parçacıkları arasında bölünmesi için bir paralel bölgenin içinde.|
|[Bölümleri](#sections-openmp)|Tüm iş parçacıkları arasında bölünmesi için kod bölümleri tanımlar.|
|[single](#single)|Kodun bir bölümünü tek bir iş parçacığı üzerinde mutlaka ana iş parçacığının yürütülmesi gereken belirtmenize olanak sağlar.|

Ana ve eşitleme için:

|Yönergesi|Açıklama|
|---------|-----------|
|[master](#master)|Ana iş parçacığı programın bir bölümünde yürütüleceğini belirtir.|
|[critical](#critical)|Bir kerede tek bir iş parçacığı üzerinde kod yalnızca yürütülür belirtir.|
|[barrier](#barrier)|Takım tüm iş parçacıklarının eşitler; tüm iş parçacıklarının engeli yürütene kadar tüm iş parçacıklarının engeli duraklatın.|
|[atomic](#atomic)|Belirten bir bellek konumuna atomik olarak güncelleştirilecek.|
|[Temizleme](#flush-openmp)|Tüm iş parçacıkları aynı görünümde tüm paylaşılan nesneler için bellek olduğunu belirtir.|
|[Sıralı](#ordered-openmp-directives)|Bu kod bir paralel belirtir `for` döngü gibi sıralı döngü yürütülmelidir.|

Veri ortamı için:

|Yönergesi|Açıklama|
|---------|-----------|
|[threadprivate](#threadprivate)|Bir değişken için bir iş parçacığı özel olduğunu belirtir.|

## <a name="atomic"></a>Atomik

Belirten bir bellek konumuna atomik olarak güncelleştirilecek.

```
#pragma omp atomic
   expression
```

### <a name="parameters"></a>Parametreler

*İfade*<br/>
Var deyimi *lvalue*, birden fazla yazma karşı korumak istediğiniz bellek konumu.

### <a name="remarks"></a>Açıklamalar

`atomic` Yönergesi yok yan tümceleri destekler.

Daha fazla bilgi için [2.6.4 atomic oluşturmak](../../../parallel/openmp/2-6-4-atomic-construct.md).

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

## <a name="barrier"></a>Engel

Takım tüm iş parçacıklarının eşitler; tüm iş parçacıklarının engeli yürütene kadar tüm iş parçacıklarının engeli duraklatın.

```
#pragma omp barrier
```

### <a name="remarks"></a>Açıklamalar

`barrier` Yönergesi yok yan tümceleri destekler.

Daha fazla bilgi için [2.6.3 barrier yönergesi](../../../parallel/openmp/2-6-3-barrier-directive.md).

### <a name="example"></a>Örnek

Nasıl kullanılacağını gösteren bir örnek `barrier`, bkz: [ana](#master).

## <a name="critical"></a>Kritik

Kodu yalnızca olması yürütüldüğünde, bir iş parçacığında aynı anda belirtir.

```
#pragma omp critical [(name)]
{
   code_block
}
```

### <a name="parameters"></a>Parametreler

*Adı*<br/>
(İsteğe bağlı) Kritik kod tanımlamak için bir ad. Ad, parantez içine alınmalıdır.

### <a name="remarks"></a>Açıklamalar

`critical` Yönergesi yok yan tümceleri destekler.

Daha fazla bilgi için [2.6.2 kritik oluşturmak](../../../parallel/openmp/2-6-2-critical-construct.md).

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

## <a name="flush-openmp"></a>Temizleme

Tüm iş parçacıkları aynı görünümde tüm paylaşılan nesneler için bellek olduğunu belirtir.

```
#pragma omp flush [(var)]
```

### <a name="parameters"></a>Parametreler

*var*<br/>
(İsteğe bağlı) Eşitlemek istediğiniz nesneleri temsil değişkenlerin virgülle ayrılmış listesi. Varsa *var* belirtilmediyse, tüm bellek temizlendi.

### <a name="remarks"></a>Açıklamalar

`flush` Yönergesi yok yan tümceleri destekler.

Daha fazla bilgi için [2.6.5 flush yönergesi](../../../parallel/openmp/2-6-5-flush-directive.md).

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

## <a name="for-openmp"></a>için

Çalışmanın neden olan bir `for` döngüsü iş parçacıkları arasında bölünmesi için bir paralel bölgenin içinde.

```
#pragma omp [parallel] for [clauses]
   for_statement
```

### <a name="parameters"></a>Parametreler

*Yan tümceleri*<br/>
(İsteğe bağlı) Sıfır veya daha fazla yan tümceleri bkz **açıklamalar** bölümü.

*for_statement*<br/>
A `for` döngü. Tanımsız davranışa neden olur, kullanıcı kodu `for` döngüsünün dizin değişkeni değiştirir.

### <a name="remarks"></a>Açıklamalar

`for` Yönergesi aşağıdaki yan tümceleri destekler:

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [Sıralı](openmp-clauses.md#ordered-openmp-clauses)
- [schedule](openmp-clauses.md#schedule)
- [nowait](openmp-clauses.md#nowait)

Varsa `parallel` de belirtilirse, `clauses` herhangi yan tümcesi tarafından kabul edilebilen `parallel` veya `for` yönergeleri dışında `nowait`.

Daha fazla bilgi için [2.4.1 yapı için](../../../parallel/openmp/2-4-1-for-construct.md).

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

## <a name="master"></a>Ana

Ana iş parçacığı programın bir bölümünde yürütüleceğini belirtir.

```
#pragma omp master
{
   code_block
}
```

### <a name="remarks"></a>Açıklamalar

`master` Yönergesi yok yan tümceleri destekler.

[Tek](#single) yönergesi, kodun bir bölümünden bir tek iş parçacığı üzerinde mutlaka ana iş parçacığı yürütülmesi gereken belirtmenize olanak sağlar.

Daha fazla bilgi için [2.6.1 master yapı](../../../parallel/openmp/2-6-1-master-construct.md).

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

## <a name="ordered-openmp-directives"></a>Sıralı

Bu kod bir paralel belirtir `for` döngü gibi sıralı döngü yürütülmelidir.

```
#pragma omp ordered
   structured-block
```

### <a name="remarks"></a>Açıklamalar

`ordered` Yönergesi içinde dinamik kapsamı olmalıdır bir [için](#for-openmp) veya `parallel for` ile oluşturmak bir `ordered` yan tümcesi.

`ordered` Yönergesi yok yan tümceleri destekler.

Daha fazla bilgi için [2.6.6 ordered yapı](../../../parallel/openmp/2-6-6-ordered-construct.md).

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

## <a name="parallel"></a>Paralel

Birden çok iş parçacığı paralel olarak yürütülen kodu bir paralel bölgenin tanımlar.

```
#pragma omp parallel [clauses]
{
   code_block
}
```

### <a name="parameters"></a>Parametreler

*Yan tümceleri*<br/>
(İsteğe bağlı) Sıfır veya daha fazla yan tümceleri bkz **açıklamalar** bölümü.

### <a name="remarks"></a>Açıklamalar

`parallel` Yönergesi aşağıdaki yan tümceleri destekler:

- [Eğer](openmp-clauses.md#if-openmp)
- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [default](openmp-clauses.md#default-openmp)
- [Paylaşılan](openmp-clauses.md#shared-openmp)
- [copyin](openmp-clauses.md#copyin)
- [reduction](openmp-clauses.md#reduction)
- [num_threads](openmp-clauses.md#num-threads)

`parallel` ile de kullanılabilir [için](#for-openmp) ve [bölümleri](#sections-openmp) yönergeleri.

Daha fazla bilgi için [2.3 parallel yapı](../../../parallel/openmp/2-3-parallel-construct.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek, iş parçacığı sayısını ayarlayın ve bir paralel bölgenin tanımlamak gösterilmektedir. İş parçacığı sayısı, varsayılan olarak makinede mantıksal işlemci sayısı eşittir. Örneğin, bir makine hiper iş parçacıklı olan bir fiziksel işlemci ile varsa, iki mantıksal işlemciler ve iki iş parçacığı olması. Çıkış sırası farklı makinelerde farklılık gösterebilir.

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

## <a name="sections-openmp"></a>Bölümleri

Tüm iş parçacıkları arasında bölünmesi için kod bölümleri tanımlar.

```
#pragma omp [parallel] sections [clauses]
{
   #pragma omp section
   {
      code_block
   }
}
```

### <a name="parameters"></a>Parametreler

*Yan tümceleri*<br/>
(İsteğe bağlı) Sıfır veya daha fazla yan tümceleri bkz **açıklamalar** bölümü.

### <a name="remarks"></a>Açıklamalar

`sections` Yönergesi, sıfır veya daha fazla içerebilir `section` yönergeleri.

`sections` Yönergesi aşağıdaki yan tümceleri destekler:

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [nowait](openmp-clauses.md#nowait)

Varsa `parallel` de belirtilirse, `clauses` herhangi yan tümcesi tarafından kabul edilebilen `parallel` veya `sections` yönergeleri dışında `nowait`.

Daha fazla bilgi için [2.4.2 sections yapı](../../../parallel/openmp/2-4-2-sections-construct.md).

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

## <a name="single"></a>Tek

Kodun bir bölümünü tek bir iş parçacığı üzerinde mutlaka ana iş parçacığının yürütülmesi gereken belirtmenize olanak sağlar.

```
#pragma omp single [clauses]
{
   code_block
}
```

### <a name="parameters"></a>Parametreler

*Yan tümceleri*<br/>
(İsteğe bağlı) Sıfır veya daha fazla yan tümceleri bkz **açıklamalar** bölümü.

### <a name="remarks"></a>Açıklamalar

`single` Yönergesi aşağıdaki yan tümceleri destekler:

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [copyprivate](openmp-clauses.md#copyprivate)
- [nowait](openmp-clauses.md#nowait)

[Ana](#master) yönergesi, kodun bir bölümünden yalnızca ana iş parçacığı üzerinde yapılmalıdır belirtmenize olanak sağlar.

Daha fazla bilgi için [2.4.3 tek oluşturmak](../../../parallel/openmp/2-4-3-single-construct.md).

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

## <a name="threadprivate"></a>threadprivate

Bir değişken için bir iş parçacığı özel olduğunu belirtir.

```
#pragma omp threadprivate(var)
```

### <a name="parameters"></a>Parametreler

*var*<br/>
Bir iş parçacığına özel yapmak istediğiniz değişkenleri virgülle ayrılmış listesi. *Varyasyon* genel veya ad alanı-kapsamlı bir değişken veya yerel bir statik değişken olmalıdır.

### <a name="remarks"></a>Açıklamalar

`threadprivate` Yönergesi yok yan tümceleri destekler.

`threadprivate` Yönergesi temel [iş parçacığı](../../../cpp/thread.md) kullanarak özniteliği [__declspec](../../../cpp/declspec.md) anahtar sözcüğü; barındırabileceğiniz `__declspec(thread)` uygulamak `threadprivate`. Örneğin, bir `threadprivate` değişkeni işlemde yalnızca bir paralel bölgenin tarafından üretilen bir iş parçacığı ekibin parçası olan iş parçacığı çalışmaya herhangi bir iş parçacığı var. Bu uygulama ayrıntısıdır dikkat edin. fark edebilirsiniz oluşturucuları bir `threadprivate` kullanıcı tanımlı tür genellikle beklenen sonra daha fazla çağrılır.

Kullanabileceğiniz `threadprivate` işlem başlangıçta statik olarak yüklenen bir DLL içinde ancak kullanamazsınız `threadprivate` aracılığıyla yüklenen herhangi bir DLL içinde [LoadLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibrarya) ile yüklenen DLL'ler gibi  [ /delayload (gecikme Yükü içe)](../../../build/reference/delayload-delay-load-import.md), kullanan `LoadLibrary`.

A `threadprivate` değişkenine bir *yıkıcı* türü adlı yok edici için alınamayabilir. Örneğin:

```
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

Kullanıcılar için bir paralel bölgenin oluşturan iş parçacıklarının ne zaman sona erer denetiminiz yoktur. Bu iş parçacıkları işlemi, iş parçacıkları hakkında işlem çıkış bildirilmez ve yok edici için çağrılması gerekmez varsa `threaded_var` çıkar dışındaki herhangi bir iş parçacığı üzerinde (burada, birincil iş parçacığı). Kod üzerinde uygun edilmesine sayısı olmamalıdır şekilde `threadprivate` değişkenleri.

Daha fazla bilgi için [2.7.1 threadprivate yönergesi](../../../parallel/openmp/2-7-1-threadprivate-directive.md).

### <a name="example"></a>Örnek

Kullanarak bir örnek için `threadprivate`, bkz: [özel](openmp-clauses.md#private-openmp).
