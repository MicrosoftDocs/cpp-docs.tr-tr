---
description: 'Daha fazla bilgi edinin: OpenMP yan tümceleri'
title: OpenMP Yan Tümceleri
ms.date: 03/20/2019
f1_keywords:
- OpenMP clauses
- copyin
- copyprivate
- default
- firstprivate
- lastprivate
- nowait
- num_threads
- ordered
- private
- reduction
- schedule
- shared
helpviewer_keywords:
- OpenMP clauses
- copyin OpenMP clause
- copyprivate OpenMP clause
- default OpenMP clause
- defaults, OpenMP clause
- firstprivate OpenMP clause
- if OpenMP clause
- lastprivate OpenMP clause
- nowait OpenMP clause
- num_threads OpenMP clause
- ordered OpenMP clause
- private OpenMP clause
- reduction OpenMP clause
- schedule OpenMP clause
- shared OpenMP clause
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
ms.openlocfilehash: 3bdcb496238b2f8acef85819c43348c095293287
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342419"
---
# <a name="openmp-clauses"></a>OpenMP Yan Tümceleri

OpenMP API 'sinde kullanılan yan tümceler için bağlantılar sağlar.

Visual C++ aşağıdaki OpenMP yan tümcelerini destekler.

Genel öznitelikler için:

|Yan Tümce|Açıklama|
|------|-----------|
|[if](#if-openmp)|Bir döngünün paralel veya seri olarak yürütülmesi gerekip gerekmediğini belirtir.|
|[num_threads](#num-threads)|İş parçacığı ekipteki iş parçacığı sayısını ayarlar.|
|[lerin](#ordered-openmp-clauses)|Döngüde [sıralı](openmp-directives.md#ordered-openmp-directives) bir yönerge kullanılacaksa, Parallel [for](openmp-directives.md#for-openmp) ifadesinde gereklidir.|
|[çizelgesini](#schedule)|[For](openmp-directives.md#for-openmp) yönergesi için geçerlidir.|
|[nowait](#nowait)|Bir yönergede örtük olarak engelini geçersiz kılar.|

Veri paylaşım öznitelikleri için:

|Yan Tümce|Açıklama|
|------|-----------|
|[özelleştirme](#private-openmp)|Her bir iş parçacığının kendi değişken örneğine sahip olması gerektiğini belirtir.|
|[firstprivate](#firstprivate)|Her bir iş parçacığının kendi değişken örneğine sahip olması gerektiğini ve değişkenin, paralel yapıdan önce mevcut olduğu için değişkenin değeri ile başlatılmış olması gerektiğini belirtir.|
|[lastprivate](#lastprivate)|Kapsayan bağlamın değişkenin değişken sürümünün, son yinelemeyi (for-Loop yapısı) veya son bölümü (#pragma bölümleri) yürüttüğünü belirten özel sürüme eşit olarak ayarlandığını belirtir.|
|[Paylaşılan](#shared-openmp)|Bir veya daha fazla değişkenin tüm iş parçacıkları arasında paylaşıldığını belirtir.|
|[varsayılanını](#default-openmp)|Bir paralel bölgedeki kapsama olmayan değişkenlerin davranışını belirtir.|
|[reduction](#reduction)|Her iş parçacığı için özel bir veya daha fazla değişkenin, paralel bölgenin sonundaki bir azaltma işleminin konusu olduğunu belirtir.|
|[copyin](#copyin)|Bir [threadprivate](openmp-directives.md#threadprivate) değişkeni için iş parçacıklarının ana iş parçacığının değerine erişmesine izin verir.|
|[copyprivate](#copyprivate)|Bir veya daha fazla değişkenin tüm iş parçacıkları arasında paylaşıldığını belirtir.|

## <a name="copyin"></a><a name="copyin"></a> copyin

Bir [threadprivate](openmp-directives.md#threadprivate) değişkeni için iş parçacıklarının ana iş parçacığının değerine erişmesine izin verir.

```cpp
copyin(var)
```

### <a name="parameters"></a>Parametreler

*l*<br/>
`threadprivate`Ana iş parçacığındaki değişkenin değeri ile başlatılacak olan, paralel yapıdan önce var olan değişken.

### <a name="remarks"></a>Açıklamalar

`copyin` Aşağıdaki yönergeler için geçerlidir:

- [dir](openmp-directives.md#parallel)
- [:](openmp-directives.md#for-openmp)
- [başlıklı](openmp-directives.md#sections-openmp)

Daha fazla bilgi için bkz. [2.7.2.7 copyin](../2-directives.md#2727-copyin).

### <a name="example"></a>Örnek

Kullanım örneği için bkz. [threadprivate](openmp-directives.md#threadprivate) `copyin` .

## <a name="copyprivate"></a><a name="copyprivate"></a> copyprivate

Bir veya daha fazla değişkenin tüm iş parçacıkları arasında paylaşıldığını belirtir.

```cpp
copyprivate(var)
```

### <a name="parameters"></a>Parametreler

*l*<br/>
Paylaşılacak bir veya daha fazla değişken. Birden fazla değişken belirtilirse, değişken adlarını virgülle ayırın.

### <a name="remarks"></a>Açıklamalar

`copyprivate`[tek](openmp-directives.md#single) yönerge için geçerlidir.

Daha fazla bilgi için bkz. [2.7.2.8 copyprivate](../2-directives.md#2728-copyprivate).

### <a name="example"></a>Örnek

```cpp
// omp_copyprivate.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

float x, y, fGlobal = 1.0;
#pragma omp threadprivate(x, y)

float get_float() {
   fGlobal += 0.001;
   return fGlobal;
}

void use_float(float f, int t) {
   printf_s("Value = %f, thread = %d\n", f, t);
}

void CopyPrivate(float a, float b) {
   #pragma omp single copyprivate(a, b, x, y)
   {
      a = get_float();
      b = get_float();
      x = get_float();
      y = get_float();
    }

   use_float(a, omp_get_thread_num());
   use_float(b, omp_get_thread_num());
   use_float(x, omp_get_thread_num());
   use_float(y, omp_get_thread_num());
}

int main() {
   float a = 9.99, b = 123.456;

   printf_s("call CopyPrivate from a single thread\n");
   CopyPrivate(9.99, 123.456);

   printf_s("call CopyPrivate from a parallel region\n");
   #pragma omp parallel
   {
      CopyPrivate(a, b);
   }
}
```

```Output
call CopyPrivate from a single thread
Value = 1.001000, thread = 0
Value = 1.002000, thread = 0
Value = 1.003000, thread = 0
Value = 1.004000, thread = 0
call CopyPrivate from a parallel region
Value = 1.005000, thread = 0
Value = 1.005000, thread = 1
Value = 1.006000, thread = 0
Value = 1.006000, thread = 1
Value = 1.007000, thread = 0
Value = 1.007000, thread = 1
Value = 1.008000, thread = 0
Value = 1.008000, thread = 1
```

## <a name="default"></a><a name="default-openmp"></a> varsayılanını

Bir paralel bölgedeki kapsama olmayan değişkenlerin davranışını belirtir.

```cpp
default(shared | none)
```

### <a name="remarks"></a>Açıklamalar

`shared``default`yan tümce belirtilmemişse geçerli olan, bir paralel bölgedeki herhangi bir değişkenin, [paylaşılan](#shared-openmp) yan tümcesiyle belirtilmiş gibi değerlendirileceği anlamına gelir. `none`[özel](#private-openmp), [paylaşılan](#shared-openmp), [azaltma](#reduction), [firstprivate](#firstprivate)veya [lastprivate](#lastprivate) yan tümcesi kapsamında olmayan bir paralel bölgede kullanılan değişkenlerin bir derleyici hatasına neden olacağı anlamına gelir.

`default` Aşağıdaki yönergeler için geçerlidir:

- [dir](openmp-directives.md#parallel)
- [:](openmp-directives.md#for-openmp)
- [başlıklı](openmp-directives.md#sections-openmp)

Daha fazla bilgi için bkz. [2.7.2.5 default](../2-directives.md#2725-default).

### <a name="example"></a>Örnek

Bkz. [özel](#private-openmp) kullanım örneği `default` .

## <a name="firstprivate"></a><a name="firstprivate"></a> firstprivate

Her bir iş parçacığının kendi değişken örneğine sahip olması gerektiğini ve değişkenin, paralel yapıdan önce mevcut olduğu için değişkenin değeri ile başlatılmış olması gerektiğini belirtir.

```cpp
firstprivate(var)
```

### <a name="parameters"></a>Parametreler

*l*<br/>
Her bir iş parçacığında örneklere sahip olacak ve paralel yapıdan önce mevcut olduğundan değişkenin değeri ile başlatılacak olan değişken. Birden fazla değişken belirtilirse, değişken adlarını virgülle ayırın.

### <a name="remarks"></a>Açıklamalar

`firstprivate` Aşağıdaki yönergeler için geçerlidir:

- [:](openmp-directives.md#for-openmp)
- [dir](openmp-directives.md#parallel)
- [başlıklı](openmp-directives.md#sections-openmp)
- [sunuculu](openmp-directives.md#single)

Daha fazla bilgi için bkz. [2.7.2.2 firstprivate](../2-directives.md#2722-firstprivate).

### <a name="example"></a>Örnek

Kullanımıyla ilgili bir örnek için `firstprivate` bkz. [Private](#private-openmp).

## <a name="if-openmp"></a><a name="if-openmp"></a> if (OpenMP)

Bir döngünün paralel veya seri olarak yürütülmesi gerekip gerekmediğini belirtir.

```cpp
if(expression)
```

### <a name="parameters"></a>Parametreler

*expression*<br/>
True (sıfır dışında) olarak değerlendirilirse bir integral ifadesi, paralel bölgedeki kodun paralel olarak yürütülmesine neden olur. İfade false (sıfır) olarak değerlendirilirse, paralel bölge seri olarak (tek bir iş parçacığı tarafından) yürütülür.

### <a name="remarks"></a>Açıklamalar

`if` Aşağıdaki yönergeler için geçerlidir:

- [dir](openmp-directives.md#parallel)
- [:](openmp-directives.md#for-openmp)
- [başlıklı](openmp-directives.md#sections-openmp)

Daha fazla bilgi için bkz. [2,3 paralel yapısı](../2-directives.md#23-parallel-construct).

### <a name="example"></a>Örnek

```cpp
// omp_if.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

void test(int val)
{
    #pragma omp parallel if (val)
    if (omp_in_parallel())
    {
        #pragma omp single
        printf_s("val = %d, parallelized with %d threads\n",
                 val, omp_get_num_threads());
    }
    else
    {
        printf_s("val = %d, serialized\n", val);
    }
}

int main( )
{
    omp_set_num_threads(2);
    test(0);
    test(2);
}
```

```Output
val = 0, serialized
val = 2, parallelized with 2 threads
```

## <a name="lastprivate"></a><a name="lastprivate"></a> lastprivate

Kapsayan bağlamın değişkenin değişken sürümünün, son yinelemeyi (for-Loop yapısı) veya son bölümü (#pragma bölümleri) yürüttüğünü belirten özel sürüme eşit olarak ayarlandığını belirtir.

```cpp
lastprivate(var)
```

### <a name="parameters"></a>Parametreler

*l*<br/>
Herhangi bir iş parçacığının özel sürümüne eşit olarak ayarlanan değişken, son yinelemeyi (for döngüsü yapısı) veya son bölümü (#pragma bölümleri) yürütür.

### <a name="remarks"></a>Açıklamalar

`lastprivate` Aşağıdaki yönergeler için geçerlidir:

- [:](openmp-directives.md#for-openmp)
- [başlıklı](openmp-directives.md#sections-openmp)

Daha fazla bilgi için bkz. [2.7.2.3 lastprivate](../2-directives.md#2723-lastprivate).

### <a name="example"></a>Örnek

Using yan tümcesi örneği için bkz. [zamanlama](#schedule) `lastprivate` .

## <a name="nowait"></a><a name="nowait"></a> NoWait

Bir yönergede örtük olarak engelini geçersiz kılar.

```cpp
nowait
```

### <a name="remarks"></a>Açıklamalar

`nowait` Aşağıdaki yönergeler için geçerlidir:

- [:](openmp-directives.md#for-openmp)
- [başlıklı](openmp-directives.md#sections-openmp)
- [sunuculu](openmp-directives.md#single)

Daha fazla bilgi için bkz. [2.4.1 for yapýsý](../2-directives.md#241-for-construct), [2.4.2 sections sections yapısı](../2-directives.md#242-sections-construct)ve [2.4.3 single yapısı](../2-directives.md#243-single-construct).

### <a name="example"></a>Örnek

```cpp
// omp_nowait.cpp
// compile with: /openmp /c
#include <stdio.h>

#define SIZE 5

void test(int *a, int *b, int *c, int size)
{
    int i;
    #pragma omp parallel
    {
        #pragma omp for nowait
        for (i = 0; i < size; i++)
            b[i] = a[i] * a[i];

        #pragma omp for nowait
        for (i = 0; i < size; i++)
            c[i] = a[i]/2;
    }
}

int main( )
{
    int a[SIZE], b[SIZE], c[SIZE];
    int i;

    for (i=0; i<SIZE; i++)
        a[i] = i;

    test(a,b,c, SIZE);

    for (i=0; i<SIZE; i++)
        printf_s("%d, %d, %d\n", a[i], b[i], c[i]);
}
```

```Output
0, 0, 0
1, 1, 0
2, 4, 1
3, 9, 1
4, 16, 2
```

## <a name="num_threads"></a><a name="num-threads"></a> num_threads

İş parçacığı ekipteki iş parçacığı sayısını ayarlar.

```cpp
num_threads(num)
```

### <a name="parameters"></a>Parametreler

*numaraları*<br/>
İş parçacığı sayısı

### <a name="remarks"></a>Açıklamalar

`num_threads`Yan tümcesi [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) işleviyle aynı işlevselliğe sahiptir.

`num_threads` Aşağıdaki yönergeler için geçerlidir:

- [dir](openmp-directives.md#parallel)
- [:](openmp-directives.md#for-openmp)
- [başlıklı](openmp-directives.md#sections-openmp)

Daha fazla bilgi için bkz. [2,3 paralel yapısı](../2-directives.md#23-parallel-construct).

### <a name="example"></a>Örnek

Using [](openmp-directives.md#parallel) yan tümcesinin bir örneği için bkz `num_threads` . Parallel.

## <a name="ordered"></a><a name="ordered-openmp-clauses"></a> lerin

Döngüde [sıralı](openmp-directives.md#ordered-openmp-directives) bir yönerge kullanılacaksa, Parallel [for](openmp-directives.md#for-openmp) ifadesinde gereklidir.

```cpp
ordered
```

### <a name="remarks"></a>Açıklamalar

`ordered`[for](openmp-directives.md#for-openmp) yönergesi için geçerlidir.

Daha fazla bilgi için bkz. [2.4.1 for yapısı](../2-directives.md#241-for-construct).

### <a name="example"></a>Örnek

Using yan tümcesi [örneği için bkz](openmp-directives.md#ordered-openmp-directives) `ordered` ..

## <a name="private"></a><a name="private-openmp"></a> özelleştirme

Her bir iş parçacığının kendi değişken örneğine sahip olması gerektiğini belirtir.

```cpp
private(var)
```

### <a name="parameters"></a>Parametreler

*l*<br/>
Her iş parçacığında örneklere sahip olacak değişken.

### <a name="remarks"></a>Açıklamalar

`private` Aşağıdaki yönergeler için geçerlidir:

- [:](openmp-directives.md#for-openmp)
- [dir](openmp-directives.md#parallel)
- [başlıklı](openmp-directives.md#sections-openmp)
- [sunuculu](openmp-directives.md#single)

Daha fazla bilgi için bkz. [2.7.2.1 Private](../2-directives.md#2721-private).

### <a name="example"></a>Örnek

```c
// openmp_private.c
// compile with: /openmp
#include <windows.h>
#include <assert.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SLEEP_THREAD 1
#define NUM_LOOPS 2

enum Types {
   ThreadPrivate,
   Private,
   FirstPrivate,
   LastPrivate,
   Shared,
   MAX_TYPES
};

int nSave[NUM_THREADS][MAX_TYPES][NUM_LOOPS] = {{0}};
int nThreadPrivate;

#pragma omp threadprivate(nThreadPrivate)
#pragma warning(disable:4700)

int main() {
   int nPrivate = NUM_THREADS;
   int nFirstPrivate = NUM_THREADS;
   int nLastPrivate = NUM_THREADS;
   int nShared = NUM_THREADS;
   int nRet = 0;
   int i;
   int j;
   int nLoop = 0;

   nThreadPrivate = NUM_THREADS;
   printf_s("These are the variables before entry "
           "into the parallel region.\n");
   printf_s("nThreadPrivate = %d\n", nThreadPrivate);
   printf_s("      nPrivate = %d\n", nPrivate);
   printf_s(" nFirstPrivate = %d\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d\n", nLastPrivate);
   printf_s("       nShared = %d\n\n", nShared);
   omp_set_num_threads(NUM_THREADS);

   #pragma omp parallel copyin(nThreadPrivate) private(nPrivate) shared(nShared) firstprivate(nFirstPrivate)
   {
      #pragma omp for schedule(static) lastprivate(nLastPrivate)
      for (i = 0 ; i < NUM_THREADS ; ++i) {
         for (j = 0 ; j < NUM_LOOPS ; ++j) {
            int nThread = omp_get_thread_num();
            assert(nThread < NUM_THREADS);

            if (nThread == SLEEP_THREAD)
               Sleep(100);
            nSave[nThread][ThreadPrivate][j] = nThreadPrivate;
            nSave[nThread][Private][j] = nPrivate;
            nSave[nThread][Shared][j] = nShared;
            nSave[nThread][FirstPrivate][j] = nFirstPrivate;
            nSave[nThread][LastPrivate][j] = nLastPrivate;
            nThreadPrivate = nThread;
            nPrivate = nThread;
            nShared = nThread;
            nLastPrivate = nThread;
            --nFirstPrivate;
         }
      }
   }

   for (i = 0 ; i < NUM_LOOPS ; ++i) {
      for (j = 0 ; j < NUM_THREADS ; ++j) {
         printf_s("These are the variables at entry of "
                  "loop %d of thread %d.\n", i + 1, j);
         printf_s("nThreadPrivate = %d\n",
                  nSave[j][ThreadPrivate][i]);
         printf_s("      nPrivate = %d\n",
                  nSave[j][Private][i]);
         printf_s(" nFirstPrivate = %d\n",
                  nSave[j][FirstPrivate][i]);
         printf_s("  nLastPrivate = %d\n",
                  nSave[j][LastPrivate][i]);
         printf_s("       nShared = %d\n\n",
                  nSave[j][Shared][i]);
      }
   }

   printf_s("These are the variables after exit from "
            "the parallel region.\n");
   printf_s("nThreadPrivate = %d (The last value in the "
            "master thread)\n", nThreadPrivate);
   printf_s("      nPrivate = %d (The value prior to "
            "entering parallel region)\n", nPrivate);
   printf_s(" nFirstPrivate = %d (The value prior to "
            "entering parallel region)\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d (The value from the "
            "last iteration of the loop)\n", nLastPrivate);
   printf_s("       nShared = %d (The value assigned, "
            "from the delayed thread, %d)\n\n",
            nShared, SLEEP_THREAD);
}
```

```Output
These are the variables before entry into the parallel region.
nThreadPrivate = 4
      nPrivate = 4
nFirstPrivate = 4
  nLastPrivate = 4
       nShared = 4

These are the variables at entry of loop 1 of thread 0.
nThreadPrivate = 4
      nPrivate = 1310720
nFirstPrivate = 4
  nLastPrivate = 1245104
       nShared = 3

These are the variables at entry of loop 1 of thread 1.
nThreadPrivate = 4
      nPrivate = 4488
nFirstPrivate = 4
  nLastPrivate = 19748
       nShared = 0

These are the variables at entry of loop 1 of thread 2.
nThreadPrivate = 4
      nPrivate = -132514848
nFirstPrivate = 4
  nLastPrivate = -513199792
       nShared = 4

These are the variables at entry of loop 1 of thread 3.
nThreadPrivate = 4
      nPrivate = 1206
nFirstPrivate = 4
  nLastPrivate = 1204
       nShared = 2

These are the variables at entry of loop 2 of thread 0.
nThreadPrivate = 0
      nPrivate = 0
nFirstPrivate = 3
  nLastPrivate = 0
       nShared = 0

These are the variables at entry of loop 2 of thread 1.
nThreadPrivate = 1
      nPrivate = 1
nFirstPrivate = 3
  nLastPrivate = 1
       nShared = 1

These are the variables at entry of loop 2 of thread 2.
nThreadPrivate = 2
      nPrivate = 2
nFirstPrivate = 3
  nLastPrivate = 2
       nShared = 2

These are the variables at entry of loop 2 of thread 3.
nThreadPrivate = 3
      nPrivate = 3
nFirstPrivate = 3
  nLastPrivate = 3
       nShared = 3

These are the variables after exit from the parallel region.
nThreadPrivate = 0 (The last value in the master thread)
      nPrivate = 4 (The value prior to entering parallel region)
nFirstPrivate = 4 (The value prior to entering parallel region)
  nLastPrivate = 3 (The value from the last iteration of the loop)
       nShared = 1 (The value assigned, from the delayed thread, 1)
```

## <a name="reduction"></a><a name="reduction"></a> azaltma

Her iş parçacığı için özel bir veya daha fazla değişkenin, paralel bölgenin sonundaki bir azaltma işleminin konusu olduğunu belirtir.

```cpp
reduction(operation:var)
```

### <a name="parameters"></a>Parametreler

*çalışmasını*<br/>
Paralel bölgenin sonundaki değişkenlerde *var* olan işlem için işleç.

*l*<br/>
Üzerinde skalar azaltma yapılacak bir veya daha fazla değişken. Birden fazla değişken belirtilirse, değişken adlarını virgülle ayırın.

### <a name="remarks"></a>Açıklamalar

`reduction` Aşağıdaki yönergeler için geçerlidir:

- [dir](openmp-directives.md#parallel)
- [:](openmp-directives.md#for-openmp)
- [başlıklı](openmp-directives.md#sections-openmp)

Daha fazla bilgi için bkz. [2.7.2.6 azaltma](../2-directives.md#2726-reduction).

### <a name="example"></a>Örnek

```cpp
// omp_reduction.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SUM_START   1
#define SUM_END     10
#define FUNC_RETS   {1, 1, 1, 1, 1}

int bRets[5] = FUNC_RETS;
int nSumCalc = ((SUM_START + SUM_END) * (SUM_END - SUM_START + 1)) / 2;

int func1( ) {return bRets[0];}
int func2( ) {return bRets[1];}
int func3( ) {return bRets[2];}
int func4( ) {return bRets[3];}
int func5( ) {return bRets[4];}

int main( )
{
    int nRet = 0,
        nCount = 0,
        nSum = 0,
        i,
        bSucceed = 1;

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel reduction(+ : nCount)
    {
        nCount += 1;

        #pragma omp for reduction(+ : nSum)
        for (i = SUM_START ; i <= SUM_END ; ++i)
            nSum += i;

        #pragma omp sections reduction(&& : bSucceed)
        {
            #pragma omp section
            {
                bSucceed = bSucceed && func1( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func2( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func3( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func4( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func5( );
            }
        }
    }

    printf_s("The parallel section was executed %d times "
             "in parallel.\n", nCount);
    printf_s("The sum of the consecutive integers from "
             "%d to %d, is %d\n", 1, 10, nSum);

    if (bSucceed)
        printf_s("All of the functions, func1 through "
                 "func5 succeeded!\n");
    else
        printf_s("One or more of the functions, func1 "
                 "through func5 failed!\n");

    if (nCount != NUM_THREADS)
    {
        printf_s("ERROR: For %d threads, %d were counted!\n",
                 NUM_THREADS, nCount);
        nRet |= 0x1;
   }

    if (nSum != nSumCalc)
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                "but %d was reported!\n",
                SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x10;
    }

    if (bSucceed != (bRets[0] && bRets[1] &&
                     bRets[2] && bRets[3] && bRets[4]))
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                 "but %d was reported!\n",
                 SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x100;
    }
}
```

```Output
The parallel section was executed 4 times in parallel.
The sum of the consecutive integers from 1 to 10, is 55
All of the functions, func1 through func5 succeeded!
```

## <a name="schedule"></a><a name="schedule"></a> çizelgesini

[For](openmp-directives.md#for-openmp) yönergesi için geçerlidir.

```cpp
schedule(type[,size])
```

### <a name="parameters"></a>Parametreler

*türüyle*<br/>
Zamanlama türü,,, `dynamic` ya da `guided` `runtime` `static` .

*boyutla*<br/>
Seçim Yinelemelerin boyutunu belirtir. *Boyut* bir tamsayı olmalıdır. *Tür* olduğunda geçerli değildir `runtime` .

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [2.4.1 for yapısı](../2-directives.md#241-for-construct).

### <a name="example"></a>Örnek

```cpp
// omp_schedule.cpp
// compile with: /openmp
#include <windows.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define STATIC_CHUNK 5
#define DYNAMIC_CHUNK 5
#define NUM_LOOPS 20
#define SLEEP_EVERY_N 3

int main( )
{
    int nStatic1[NUM_LOOPS],
        nStaticN[NUM_LOOPS];
    int nDynamic1[NUM_LOOPS],
        nDynamicN[NUM_LOOPS];
    int nGuided[NUM_LOOPS];

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel
    {
        #pragma omp for schedule(static, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStatic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(static, STATIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStaticN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, DYNAMIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamicN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(guided)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nGuided[i] = omp_get_thread_num( );
        }
    }

    printf_s("------------------------------------------------\n");
    printf_s("| static | static | dynamic | dynamic | guided |\n");
    printf_s("|    1   |    %d   |    1    |    %d    |        |\n",
             STATIC_CHUNK, DYNAMIC_CHUNK);
    printf_s("------------------------------------------------\n");

    for (int i=0; i<NUM_LOOPS; ++i)
    {
        printf_s("|    %d   |    %d   |    %d    |    %d    |"
                 "    %d   |\n",
                 nStatic1[i], nStaticN[i],
                 nDynamic1[i], nDynamicN[i], nGuided[i]);
    }

    printf_s("------------------------------------------------\n");
}
```

```Output
------------------------------------------------
| static | static | dynamic | dynamic | guided |
|    1   |    5   |    1    |    5    |        |
------------------------------------------------
|    0   |    0   |    0    |    2    |    1   |
|    1   |    0   |    3    |    2    |    1   |
|    2   |    0   |    3    |    2    |    1   |
|    3   |    0   |    3    |    2    |    1   |
|    0   |    0   |    2    |    2    |    1   |
|    1   |    1   |    2    |    3    |    3   |
|    2   |    1   |    2    |    3    |    3   |
|    3   |    1   |    0    |    3    |    3   |
|    0   |    1   |    0    |    3    |    3   |
|    1   |    1   |    0    |    3    |    2   |
|    2   |    2   |    1    |    0    |    2   |
|    3   |    2   |    1    |    0    |    2   |
|    0   |    2   |    1    |    0    |    3   |
|    1   |    2   |    2    |    0    |    3   |
|    2   |    2   |    2    |    0    |    0   |
|    3   |    3   |    2    |    1    |    0   |
|    0   |    3   |    3    |    1    |    1   |
|    1   |    3   |    3    |    1    |    1   |
|    2   |    3   |    3    |    1    |    1   |
|    3   |    3   |    0    |    1    |    3   |
------------------------------------------------
```

## <a name="shared"></a><a name="shared-openmp"></a> Paylaşılan

Bir veya daha fazla değişkenin tüm iş parçacıkları arasında paylaşıldığını belirtir.

```cpp
shared(var)
```

### <a name="parameters"></a>Parametreler

*l*<br/>
Paylaşılacak bir veya daha fazla değişken. Birden fazla değişken belirtilirse, değişken adlarını virgülle ayırın.

### <a name="remarks"></a>Açıklamalar

Değişkenleri iş parçacıkları arasında paylaşmanın bir diğer yolu, [copyprivate](#copyprivate) yan tümcesine sahiptir.

`shared` Aşağıdaki yönergeler için geçerlidir:

- [dir](openmp-directives.md#parallel)
- [:](openmp-directives.md#for-openmp)
- [başlıklı](openmp-directives.md#sections-openmp)

Daha fazla bilgi için bkz. [2.7.2.4 Shared](../2-directives.md#2724-shared).

### <a name="example"></a>Örnek

Bkz. [özel](#private-openmp) kullanım örneği `shared` .
