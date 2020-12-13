---
description: 'Daha fazla bilgi edinin: OpenMP yönergeleri'
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
ms.openlocfilehash: 03730b1f5cda0972dbf86b345c6e44bdad4e949b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342406"
---
# <a name="openmp-directives"></a>OpenMP Yönergeleri

OpenMP API 'sinde kullanılan yönergelere bağlantılar sağlar.

Visual C++ aşağıdaki OpenMP yönergelerini destekler.

Paralel iş paylaşımı için:

|Deki|Açıklama|
|---------|-----------|
|[dir](#parallel)|Paralel olarak birden çok iş parçacığı tarafından yürütülecek kod olan bir paralel bölgeyi tanımlar.|
|[:](#for-openmp)|`for`Paralel bölge içindeki bir döngüde yapılan çalışmanın iş parçacıkları arasında ayrılmasına neden olur.|
|[başlıklı](#sections-openmp)|Kod bölümlerini tüm iş parçacıkları arasında bölünecek şekilde tanımlar.|
|[sunuculu](#single)|Kod bölümünün, ana iş parçacığı olması için tek bir iş parçacığında yürütülmesi gerektiğini belirtmenize izin verir.|

Ana ve eşitleme için:

|Deki|Açıklama|
|---------|-----------|
|[ana](#master)|Yalnızca ana iş parçacığının programın bir bölümünü yürütmesi gerektiğini belirtir.|
|[başlatma](#critical)|Kodun tek seferde yalnızca bir iş parçacığında yürütüldüğünü belirtir.|
|[engeli](#barrier)|Bir ekipteki tüm iş parçacıklarını eşitler; Tüm iş parçacıkları engeli yürütülene kadar tüm iş parçacıkları engelde duraklamalar.|
|[atomic](#atomic)|Bir bellek konumunun otomatik olarak güncelleştirileceğini belirtir.|
|[flush](#flush-openmp)|Tüm iş parçacıklarının tüm paylaşılan nesneler için aynı bellek görünümüne sahip olduğunu belirtir.|
|[lerin](#ordered-openmp-directives)|Paralel bir döngü altındaki kodun `for` sıralı bir döngü gibi yürütülmesi gerektiğini belirtir.|

Veri ortamı için:

|Deki|Açıklama|
|---------|-----------|
|[threadprivate](#threadprivate)|Bir değişkenin bir iş parçacığına özel olduğunu belirtir.|

## <a name="atomic"></a><a name="atomic"></a> Atomik

Bir bellek konumunun otomatik olarak güncelleştirileceğini belirtir.

```cpp
#pragma omp atomic
   expression
```

### <a name="parameters"></a>Parametreler

*expression*<br/>
Bellek konumu birden fazla yazmaya karşı korumak istediğiniz *lvalue* olan bir ifade.

### <a name="remarks"></a>Açıklamalar

`atomic`Yönergesi hiçbir yan tümceyi destekler.

Daha fazla bilgi için bkz. [2.6.4 atomik yapı](../2-directives.md#264-atomic-construct).

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

## <a name="barrier"></a><a name="barrier"></a> engeli

Bir ekipteki tüm iş parçacıklarını eşitler; Tüm iş parçacıkları engeli yürütülene kadar tüm iş parçacıkları engelde duraklamalar.

```cpp
#pragma omp barrier
```

### <a name="remarks"></a>Açıklamalar

`barrier`Yönergesi hiçbir yan tümceyi destekler.

Daha fazla bilgi için bkz. [2.6.3 engel yönergesi](../2-directives.md#263-barrier-directive).

### <a name="example"></a>Örnek

Öğesinin kullanımıyla ilgili bir örnek için `barrier` bkz. [Master](#master).

## <a name="critical"></a><a name="critical"></a> başlatma

Kodun tek seferde yalnızca bir iş parçacığında yürütüleceğini belirtir.

```cpp
#pragma omp critical [(name)]
{
   code_block
}
```

### <a name="parameters"></a>Parametreler

*ada*<br/>
Seçim Kritik kodu tanımlayacak bir ad. Adın parantez içine alınması gerekir.

### <a name="remarks"></a>Açıklamalar

`critical`Yönergesi hiçbir yan tümceyi destekler.

Daha fazla bilgi için bkz. [2.6.2 Critical Critical yapısı](../2-directives.md#262-critical-construct).

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

## <a name="flush"></a><a name="flush-openmp"></a> temizlenemiyor

Tüm iş parçacıklarının tüm paylaşılan nesneler için aynı bellek görünümüne sahip olduğunu belirtir.

```cpp
#pragma omp flush [(var)]
```

### <a name="parameters"></a>Parametreler

*l*<br/>
Seçim Eşitlenmesini istediğiniz nesneleri temsil eden değişkenlerin virgülle ayrılmış bir listesi. *Var* belirtilmemişse, tüm bellek temizlenir.

### <a name="remarks"></a>Açıklamalar

`flush`Yönergesi hiçbir yan tümceyi destekler.

Daha fazla bilgi için bkz. [2.6.5 Flush yönergesi](../2-directives.md#265-flush-directive).

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

## <a name="for"></a><a name="for-openmp"></a> bekleniyor

`for`Paralel bölge içindeki bir döngüde yapılan çalışmanın iş parçacıkları arasında ayrılmasına neden olur.

```cpp
#pragma omp [parallel] for [clauses]
   for_statement
```

### <a name="parameters"></a>Parametreler

*yan*<br/>
Seçim Sıfır veya daha fazla yan tümce, **açıklamalar** bölümüne bakın.

*for_statement*<br/>
Bir `for` döngü. Tanımsız davranış, döngüde Kullanıcı kodu `for` Dizin değişkenini değiştirdiğinde ortaya geçer.

### <a name="remarks"></a>Açıklamalar

`for`Yönergesi aşağıdaki yan tümceleri destekler:

- [özelleştirme](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [lerin](openmp-clauses.md#ordered-openmp-clauses)
- [çizelgesini](openmp-clauses.md#schedule)
- [nowait](openmp-clauses.md#nowait)

`parallel`Ayrıca belirtilmişse, `clauses` `parallel` hariç veya yönergeleri tarafından kabul edilen herhangi bir yan tümce olabilir `for` `nowait` .

Daha fazla bilgi için bkz. [2.4.1 for yapısı](../2-directives.md#241-for-construct).

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

## <a name="master"></a><a name="master"></a> şablonu

Yalnızca ana iş parçacığının programın bir bölümünü yürütmesi gerektiğini belirtir.

```cpp
#pragma omp master
{
   code_block
}
```

### <a name="remarks"></a>Açıklamalar

`master`Yönergesi hiçbir yan tümceyi destekler.

[Tek](#single) yönerge, kod bölümünün ana iş parçacığı olması için tek bir iş parçacığında yürütülmesi gerektiğini belirtmenize olanak tanır.

Daha fazla bilgi için bkz. [2.6.1 Master yapısı](../2-directives.md#261-master-construct).

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

## <a name="ordered"></a><a name="ordered-openmp-directives"></a> lerin

Paralel bir döngü altındaki kodun `for` sıralı bir döngü gibi yürütülmesi gerektiğini belirtir.

```cpp
#pragma omp ordered
   structured-block
```

### <a name="remarks"></a>Açıklamalar

`ordered`Yönergesi bir for veya bir [for](#for-openmp) `parallel for` yan tümcesiyle dinamik kapsamı içinde olmalıdır `ordered` .

`ordered`Yönergesi hiçbir yan tümceyi destekler.

Daha fazla bilgi için bkz. [2.6.6 sıralı yapısı](../2-directives.md#266-ordered-construct).

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

## <a name="parallel"></a><a name="parallel"></a> dir

Paralel olarak birden çok iş parçacığı tarafından yürütülecek kod olan bir paralel bölgeyi tanımlar.

```cpp
#pragma omp parallel [clauses]
{
   code_block
}
```

### <a name="parameters"></a>Parametreler

*yan*<br/>
Seçim Sıfır veya daha fazla yan tümce, **açıklamalar** bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

`parallel`Yönergesi aşağıdaki yan tümceleri destekler:

- [if](openmp-clauses.md#if-openmp)
- [özelleştirme](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [varsayılanını](openmp-clauses.md#default-openmp)
- [Paylaşılan](openmp-clauses.md#shared-openmp)
- [copyin](openmp-clauses.md#copyin)
- [reduction](openmp-clauses.md#reduction)
- [num_threads](openmp-clauses.md#num-threads)

`parallel` Ayrıca [for](#for-openmp) ve [sections](#sections-openmp) yönergeleriyle birlikte kullanılabilir.

Daha fazla bilgi için bkz. [2,3 paralel yapısı](../2-directives.md#23-parallel-construct).

### <a name="example"></a>Örnek

Aşağıdaki örnek, iş parçacıklarının sayısının nasıl ayarlanacağını ve bir paralel bölgenin nasıl tanımlanacağını gösterir. İş parçacığı sayısı, varsayılan olarak makinedeki mantıksal işlemci sayısına eşittir. Örneğin, hiper iş parçacığının etkinleştirildiği bir fiziksel işlemciye sahip bir makineniz varsa, iki mantıksal işlemciye ve iki iş parçacığına sahip olur. Çıktının sırası farklı makinelerde farklılık gösterebilir.

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

## <a name="sections"></a><a name="sections-openmp"></a> başlıklı

Kod bölümlerini tüm iş parçacıkları arasında bölünecek şekilde tanımlar.

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

*yan*<br/>
Seçim Sıfır veya daha fazla yan tümce, **açıklamalar** bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

`sections`Yönergede sıfır veya daha fazla yönerge bulunabilir `section` .

`sections`Yönergesi aşağıdaki yan tümceleri destekler:

- [özelleştirme](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [nowait](openmp-clauses.md#nowait)

`parallel`Ayrıca belirtilmişse, `clauses` `parallel` hariç veya yönergeleri tarafından kabul edilen herhangi bir yan tümce olabilir `sections` `nowait` .

Daha fazla bilgi için bkz. [2.4.2 sections sections yapısı](../2-directives.md#242-sections-construct).

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

## <a name="single"></a><a name="single"></a> sunuculu

Kod bölümünün, ana iş parçacığı olması için tek bir iş parçacığında yürütülmesi gerektiğini belirtmenize izin verir.

```cpp
#pragma omp single [clauses]
{
   code_block
}
```

### <a name="parameters"></a>Parametreler

*yan*<br/>
Seçim Sıfır veya daha fazla yan tümce, **açıklamalar** bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

`single`Yönergesi aşağıdaki yan tümceleri destekler:

- [özelleştirme](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [copyprivate](openmp-clauses.md#copyprivate)
- [nowait](openmp-clauses.md#nowait)

[Ana](#master) yönerge, kod bölümünün yalnızca ana iş parçacığında yürütülmesi gerektiğini belirtmenize olanak tanır.

Daha fazla bilgi için bkz. [2.4.3 single yapısı](../2-directives.md#243-single-construct).

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

## <a name="threadprivate"></a><a name="threadprivate"></a> threadprivate

Bir değişkenin bir iş parçacığına özel olduğunu belirtir.

```cpp
#pragma omp threadprivate(var)
```

### <a name="parameters"></a>Parametreler

*l*<br/>
Bir iş parçacığına özel hale getirmek istediğiniz değişkenlerin virgülle ayrılmış listesi. *var* , genel veya ad alanı kapsamlı bir değişken ya da yerel bir statik değişken olmalıdır.

### <a name="remarks"></a>Açıklamalar

`threadprivate`Yönergesi hiçbir yan tümceyi destekler.

`threadprivate`Yönergesi [__declspec](../../../cpp/declspec.md) anahtar sözcüğünü kullanan [iş parçacığı](../../../cpp/thread.md) özniteliğini temel alır `__declspec(thread)` `threadprivate` . Örneğin, bir `threadprivate` değişken yalnızca bir paralel bölge tarafından oluşturulan iş parçacığı ekibinin parçası olan iş parçacıklarında değil, işlemde başlatılan herhangi bir iş parçacığında mevcut olacaktır. Bu uygulama ayrıntısıyla haberdar olun; `threadprivate` Kullanıcı tanımlı bir tür için oluşturucuların daha sık olarak çağrıldığını ve beklendiğine fark edebilirsiniz.

`threadprivate`İşlem başlangıcında statik olarak yüklenen dll 'de kullanabilirsiniz, ancak `threadprivate` aynı zamanda kullanan, [/delayload (Gecikmeli yük içeri aktarma)](../../../build/reference/delayload-delay-load-import.md)ile yüklenen dll 'ler gibi [LOADLIBRARY](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) aracılığıyla yüklenecek herhangi bir dll 'de kullanamazsınız `LoadLibrary` .

Geri `threadprivate` *dönüşlü* bir türün değişkeni, yok edicinin çağrılmaması durumunda garanti edilmez. Örneğin:

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

Kullanıcılar, paralel bölge constituting iş parçacıklarının sonlanacak şekilde hiçbir denetime sahip değildir. İşlem çıkarken bu iş parçacıkları varsa, iş parçacıkları işlem çıkışı hakkında bilgilendirilmez ve yok edici `threaded_var` (burada, birincil iş parçacığı) dışında herhangi bir iş parçacığında yok edicinin çağrılmayacağı. Bu nedenle kod, değişkenlerin düzgün şekilde yok sayımında saymamalıdır `threadprivate` .

Daha fazla bilgi için bkz. [2.7.1 threadprivate yönergesi](../2-directives.md#271-threadprivate-directive).

### <a name="example"></a>Örnek

Kullanmanın bir örneği için `threadprivate` bkz. [Private](openmp-clauses.md#private-openmp).
