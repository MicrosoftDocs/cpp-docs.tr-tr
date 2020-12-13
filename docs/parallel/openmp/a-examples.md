---
description: 'Şunlar hakkında daha fazla bilgi edinin: A. örnekleri'
title: A. Örnekler
ms.date: 01/18/2019
ms.assetid: c0f6192f-a205-449b-b84c-cb30dbcc8b8f
ms.openlocfilehash: d52b59f9f83cf791c03fb49ca726273a2c977e58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342549"
---
# <a name="a-examples"></a>A. Örnekler

Aşağıda, bu belgede tanımlanan yapıların örnekleri verilmiştir. Bir yönergeyi izleyen bir ifade yalnızca gerekli olduğunda ve bileşik olmayan bir deyimin kendisinden önceki bir yönergeden girintilendiği bir ifadedir.

## <a name="a1-a-simple-loop-in-parallel"></a>A. 1 basit bir döngü paralel

Aşağıdaki örnek, [Parallel for](2-directives.md#251-parallel-for-construct) direktifini kullanarak bir döngünün nasıl paralel hale getirmek gösterir. Loop yineleme değişkeni varsayılan olarak özeldir, bu nedenle özel bir yan tümcesinde açıkça belirtilmesi gerekmez.

```cpp
#pragma omp parallel for
    for (i=1; i<n; i++)
        b[i] = (a[i] + a[i-1]) / 2.0;
```

## <a name="a2-conditional-compilation"></a>A. 2 Koşullu derleme

Aşağıdaki örneklerde, OpenMP makro [_OPENMP](2-directives.md#22-conditional-compilation)kullanılarak Koşullu derlemenin kullanımı gösterilmektedir. OpenMP derlemesi ile `_OPENMP` makro tanımlı hale gelir.

```cpp
# ifdef _OPENMP
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

Tanımlı Önişlemci işleci, tek bir yönergede birden fazla makronun test olmasını sağlar.

```cpp
# if defined(_OPENMP) && defined(VERBOSE)
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

## <a name="a3-parallel-regions"></a>A. 3 paralel bölgesi

[Paralel](2-directives.md#23-parallel-construct) yönerge, kaba Gresel paralel programlarda kullanılabilir. Aşağıdaki örnekte, paralel bölgedeki her iş parçacığı, `x` iş parçacığı numarasına göre genel dizinin hangi bölümünün üzerinde çalışacağına karar veriyor:

```cpp
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)
{
    iam = omp_get_thread_num();
    np =  omp_get_num_threads();
    ipoints = npoints / np;
    subdomain(x, iam, ipoints);
}
```

## <a name="a4-the-nowait-clause"></a>A. 4 nowait yan tümcesi

Bir paralel bölge içinde çok sayıda bağımsız döngü varsa, yönergenin sonunda belirtilen engelinden kaçınmak için [nowait](2-directives.md#241-for-construct) yan tümcesini `for` aşağıdaki gibi kullanabilirsiniz:

```cpp
#pragma omp parallel
{
    #pragma omp for nowait
        for (i=1; i<n; i++)
             b[i] = (a[i] + a[i-1]) / 2.0;
    #pragma omp for nowait
        for (i=0; i<m; i++)
            y[i] = sqrt(z[i]);
}
```

## <a name="a5-the-critical-directive"></a>A. 5 kritik yönerge

Aşağıdaki örnek birkaç [kritik](2-directives.md#262-critical-construct) yönergesi içerir. Örnek, bir görevin çıkarılan ve üzerinde çalıştığı bir sıraya alma modelini göstermektedir. Aynı görevi kuyruğa almaya yönelik birçok iş parçacığına karşı koruma sağlamak için, kaldırma işlemi bir `critical` bölümde olmalıdır. Bu örnekteki iki sıra bağımsız olduğundan, `critical` farklı adlara sahip yönergeler tarafından korunur, *xaxis* ve *YAxis*.

```cpp
#pragma omp parallel shared(x, y) private(x_next, y_next)
{
    #pragma omp critical ( xaxis )
        x_next = dequeue(x);
    work(x_next);
    #pragma omp critical ( yaxis )
        y_next = dequeue(y);
    work(y_next);
}
```

## <a name="a6-the-lastprivate-clause"></a>A. 6 lastprivate yan tümcesi

Doğru yürütme bazen bir döngünün son yinelemesinin bir değişkene atadığı değere bağlıdır. Bu tür programlar, bir [lastprivate](2-directives.md#2723-lastprivate) yan tümcesine bağımsız değişken olarak, değişkenlerin değerlerinin ardışık olarak yürütüldüğü zaman ile aynı olması için bağımsız değişkenler olarak listelenecek.

```cpp
#pragma omp parallel
{
   #pragma omp for lastprivate(i)
      for (i=0; i<n-1; i++)
         a[i] = b[i] + b[i+1];
}
a[i]=b[i];
```

Yukarıdaki örnekte, `i` paralel bölgenin sonundaki değeri `n-1` , sıralı durumda olduğu gibi eşit olacaktır.

## <a name="a7-the-reduction-clause"></a>A. 7 azaltma yan tümcesi

Aşağıdaki örnek, [azaltma](2-directives.md#2726-reduction) yan tümcesini göstermektedir:

```cpp
#pragma omp parallel for private(i) shared(x, y, n) \
                         reduction(+: a, b)
    for (i=0; i<n; i++) {
        a = a + x[i];
        b = b + y[i];
    }
```

## <a name="a8-parallel-sections"></a>A. 8 paralel bölümleri

Aşağıdaki örnekte ( [Bölüm 2.4.2 sections](2-directives.md#242-sections-construct)için) *xaxis*, *YAxis* ve *Zaxis* işlevleri eşzamanlı olarak çalıştırılabilir. İlk `section` yönerge isteğe bağlıdır.  Tüm `section` yönergelerin yapının sözcük biçiminde görünmesi gerekir `parallel sections` .

```cpp
#pragma omp parallel sections
{
    #pragma omp section
        xaxis();
    #pragma omp section
        yaxis();
    #pragma omp section
        zaxis();
}
```

## <a name="a9-single-directives"></a>A. 9 tek yönergeler

Aşağıdaki örnek, [tek](2-directives.md#243-single-construct) yönergeyi göstermektedir. Örnekte, yalnızca bir iş parçacığı (genellikle yönergeyle karşılaştığı ilk iş parçacığı `single` ) ilerleme iletisini yazdırır. Kullanıcı, bölümü hangi iş parçacığının yürütebileceği konusunda hiçbir varsayımda olmamalıdır `single` . Diğer tüm iş parçacıkları bu `single` bölümü atlar ve yapının sonundaki engelde durur `single` . Diğer iş parçacıkları, bölümü yürüten iş parçacığını beklemeden devam edebiliyorsa `single` , yönergede bir `nowait` yan tümce belirtilebilir `single` .

```cpp
#pragma omp parallel
{
    #pragma omp single
        printf_s("Beginning work1.\n");
    work1();
    #pragma omp single
        printf_s("Finishing work1.\n");
    #pragma omp single nowait
        printf_s("Finished work1 and beginning work2.\n");
    work2();
}
```

## <a name="a10-sequential-ordering"></a>A. 10 sıralı sıralama

[Sıralı bölümler](2-directives.md#266-ordered-construct) , paralel olarak gerçekleştirilen çalışmanın çıkışını sıralı olarak sıralamak için faydalıdır. Aşağıdaki program dizinleri ardışık sırayla yazdırır:

```cpp
#pragma omp for ordered schedule(dynamic)
    for (i=lb; i<ub; i+=st)
        work(i);
void work(int k)
{
    #pragma omp ordered
        printf_s(" %d", k);
}
```

## <a name="a11-a-fixed-number-of-threads"></a>A. 11 sabit iş parçacığı sayısı

Bazı programlar, doğru şekilde yürütmek için sabit, daha önceden belirtilen sayıda iş parçacığına bağımlıdır.  İş parçacığı sayısı için dinamik ayarlamaya yönelik varsayılan ayar uygulama tanımlı olduğundan, bu tür programlar dinamik iş parçacıkları özelliğini kapatmayı ve taşınabilirliği sağlamak için iş parçacıklarının sayısını açıkça ayarlamayı seçebilirler. Aşağıdaki örnek, [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function)kullanarak bunun nasıl yapılacağını gösterir ve [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function):

```cpp
omp_set_dynamic(0);
omp_set_num_threads(16);
#pragma omp parallel shared(x, npoints) private(iam, ipoints)
{
    if (omp_get_num_threads() != 16)
      abort();
    iam = omp_get_thread_num();
    ipoints = npoints/16;
    do_by_16(x, iam, ipoints);
}
```

Bu örnekte, program yalnızca 16 iş parçacığı tarafından yürütülürse doğru yürütülür. Uygulamanın 16 iş parçacığını destekleme yeteneği yoksa, bu örneğin davranışı uygulama tanımlı olur.

Paralel bölgeyi yürüten iş parçacıklarının sayısı, dinamik iş parçacıkları ayarından bağımsız olarak bir paralel bölge sırasında sabit kalır. Dinamik iş parçacıkları mekanizması, paralel bölgenin başlangıcında kullanılacak iş parçacığı sayısını belirler ve bölge süresince bu sabiti korur.

## <a name="a12-the-atomic-directive"></a>A. 12 atomik yönerge

Aşağıdaki örnek, [atomik](2-directives.md#264-atomic-construct) yönergesini kullanarak yarış koşullarını (bir *x* öğesinin çok sayıda iş parçacığı için eşzamanlı güncelleştirmeleri) engeller:

```cpp
#pragma omp parallel for shared(x, y, index, n)
    for (i=0; i<n; i++)
    {
        #pragma omp atomic
            x[index[i]] += work1(i);
        y[i] += work2(i);
    }
```

`atomic`Bu örnekte yönergesini kullanmanın avantajı, x 'in iki farklı öğesinin güncelleştirmelerinin paralel olarak oluşmasına izin verir. Bunun yerine [kritik](2-directives.md#262-critical-construct) bir yönerge kullanılıyorsa, *x* öğelerine yapılan tüm güncelleştirmeler hizmet dışı olarak çalıştırılır (ancak hiçbir garanti edilemez sırada değildir).

`atomic`Yönergesi yalnızca hemen sonrasında C veya C++ bildirimine uygulanır.  Sonuç olarak, *y* öğeleri bu örnekte otomatik olarak güncellenmez.

## <a name="a13-a-flush-directive-with-a-list"></a>A. 13 bir liste ile Temizleme yönergesi

Aşağıdaki örnek, `flush` iş parçacığı çiftleri arasında belirli nesnelerin noktadan noktaya eşitlenmesi için yönergesini kullanır:

```cpp
int   sync[NUMBER_OF_THREADS];
float work[NUMBER_OF_THREADS];
#pragma omp parallel private(iam,neighbor) shared(work,sync)
{
    iam = omp_get_thread_num();
    sync[iam] = 0;
    #pragma omp barrier

    // Do computation into my portion of work array
    work[iam] = ...;

    //  Announce that I am done with my work
    // The first flush ensures that my work is
    // made visible before sync.
    // The second flush ensures that sync is made visible.
    #pragma omp flush(work)
    sync[iam] = 1;
    #pragma omp flush(sync)

    // Wait for neighbor
    neighbor = (iam>0 ? iam : omp_get_num_threads()) - 1;
    while (sync[neighbor]==0)
    {
        #pragma omp flush(sync)
    }

    // Read neighbor's values of work array
    ... = work[neighbor];
}
```

## <a name="a14-a-flush-directive-without-a-list"></a>A. 14 bir liste olmadan Temizleme yönergesi

Aşağıdaki örnek ( [Section 2.6.5](2-directives.md#265-flush-directive)için), `flush` etkilenmeyen paylaşılan nesnelerden liste içermeyen bir yönergeden etkilenen paylaşılan nesneleri ayırır:

```cpp
// omp_flush_without_list.c
#include <omp.h>

int x, *p = &x;

void f1(int *q)
{
    *q = 1;
    #pragma omp flush
    // x, p, and *q are flushed
    //   because they are shared and accessible
    // q is not flushed because it is not shared.
}

void f2(int *q)
{
    #pragma omp barrier
    *q = 2;

    #pragma omp barrier
    // a barrier implies a flush
    // x, p, and *q are flushed
    //   because they are shared and accessible
    // q is not flushed because it is not shared.
}

int g(int n)
{
    int i = 1, j, sum = 0;
    *p = 1;

    #pragma omp parallel reduction(+: sum) num_threads(10)
    {
        f1(&j);
        // i, n and sum were not flushed
        //   because they were not accessible in f1
        // j was flushed because it was accessible
        sum += j;
        f2(&j);
        // i, n, and sum were not flushed
        //   because they were not accessible in f2
        // j was flushed because it was accessible
        sum += i + j + *p + n;
    }
    return sum;
}

int main()
{
}
```

## <a name="a15-the-number-of-threads-used"></a>A. 15 kullanılan iş parçacığı sayısı

Aşağıdaki yanlış örneği ( [Bölüm 3.1.2](3-run-time-library-functions.md#312-omp_get_num_threads-function)için) göz önünde bulundurun:

```cpp
np = omp_get_num_threads(); // misplaced
#pragma omp parallel for schedule(static)
    for (i=0; i<np; i++)
        work(i);
```

`omp_get_num_threads()`Çağrı, kodun seri bölümünde 1 değerini döndürür. bu nedenle, önceki örnekte *NP* her zaman 1 ' e eşit olur. Paralel bölge için dağıtılacak iş parçacıklarının sayısını öğrenmek için, çağrının paralel bölgenin içinde olması gerekir.

Aşağıdaki örnek, iş parçacığı sayısı için bir sorgu eklemeden bu programın nasıl yeniden yazalınacağını gösterir:

```cpp
#pragma omp parallel private(i)
{
    i = omp_get_thread_num();
    work(i);
}
```

## <a name="a16-locks"></a>A. 16 kilitleri

Aşağıdaki örnekte ( [3,2 bölümü](3-run-time-library-functions.md#32-lock-functions)için), kilit işlevlerinin bağımsız değişkeninin türü olmalıdır `omp_lock_t` ve bunu temizlemeye gerek yoktur.  Kilit işlevleri, ilk kritik bölüm girişi beklenirken iş parçacıklarının boşta olmasına neden olur, ancak saniye girişi beklenirken diğer işleri yapmak için kullanılır.  `omp_set_lock`İşlev engeller, ancak `omp_test_lock` üzerinde iş yapılmasına izin vermez `skip()` .

```cpp
// omp_using_locks.c
// compile with: /openmp /c
#include <stdio.h>
#include <omp.h>

void work(int);
void skip(int);

int main() {
   omp_lock_t lck;
   int id;

   omp_init_lock(&lck);
   #pragma omp parallel shared(lck) private(id)
   {
      id = omp_get_thread_num();

      omp_set_lock(&lck);
      printf_s("My thread id is %d.\n", id);

      // only one thread at a time can execute this printf
      omp_unset_lock(&lck);

      while (! omp_test_lock(&lck)) {
         skip(id);   // we do not yet have the lock,
                     // so we must do something else
      }
      work(id);     // we now have the lock
                    // and can do the work
      omp_unset_lock(&lck);
   }
   omp_destroy_lock(&lck);
}
```

## <a name="a17-nestable-locks"></a>A. 17 Nestable kilitleri

Aşağıdaki örnek ( [3,2 bölümü](3-run-time-library-functions.md#32-lock-functions)için), her ikisini de bir yapıya ve üyelerinden birine eşitlemeyi sağlamak için bir iç içe konulabilir kilidinin nasıl kullanılabileceğini gösterir.

```cpp
#include <omp.h>
typedef struct {int a,b; omp_nest_lock_t lck;} pair;

void incr_a(pair *p, int a)
{
    // Called only from incr_pair, no need to lock.
    p->a += a;
}

void incr_b(pair *p, int b)
{
    // Called both from incr_pair and elsewhere,
    // so need a nestable lock.

    omp_set_nest_lock(&p->lck);
    p->b += b;
    omp_unset_nest_lock(&p->lck);
}

void incr_pair(pair *p, int a, int b)
{
    omp_set_nest_lock(&p->lck);
    incr_a(p, a);
    incr_b(p, b);
    omp_unset_nest_lock(&p->lck);
}

void f(pair *p)
{
    extern int work1(), work2(), work3();
    #pragma omp parallel sections
    {
        #pragma omp section
            incr_pair(p, work1(), work2());
        #pragma omp section
            incr_b(p, work3());
    }
}
```

## <a name="a18-nested-for-directives"></a>A. 18 Iç Içe yönergeler

`for`İç ve dış yönergeler farklı paralel bölgelere bağladığından, aşağıdaki [Yönerge iç içe geçirme](2-directives.md#29-directive-nesting) örneği uyumludur `for` :

```cpp
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
        {
            #pragma omp parallel shared(i, n)
            {
                #pragma omp for
                    for (j=0; j<n; j++)
                        work(i, j);
            }
        }
}
```

Yukarıdaki örneğin aşağıdaki bir çeşitlemesi de uyumludur:

```cpp
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
            work1(i, n);
}

void work1(int i, int n)
{
    int j;
    #pragma omp parallel default(shared)
    {
        #pragma omp for
            for (j=0; j<n; j++)
                work2(i, j);
    }
    return;
}
```

## <a name="a19-examples-showing-incorrect-nesting-of-work-sharing-directives"></a>Hatalı iş paylaşımı yönergelerini gösteren bir. 19 örnek

Bu bölümdeki örneklerde, [Yönerge iç içe](2-directives.md#29-directive-nesting) kuralları gösterilmektedir.

İç ve dış `for` yönergeler iç içe yerleştirilmiş ve aynı yönergeye bağlanan için aşağıdaki örnek uyumlu değildir `parallel` :

```cpp
void wrong1(int n)
{
  #pragma omp parallel default(shared)
  {
      int i, j;
      #pragma omp for
      for (i=0; i<n; i++) {
          #pragma omp for
              for (j=0; j<n; j++)
                 work(i, j);
     }
   }
}
```

Yukarıdaki örneğin aşağıdaki dinamik olarak iç içe geçmiş sürümü de uyumlu değildir:

```cpp
void wrong2(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++)
        work1(i, n);
  }
}

void work1(int i, int n)
{
  int j;
  #pragma omp for
    for (j=0; j<n; j++)
      work2(i, j);
}
```

Aşağıdaki örnek, `for` ve `single` yönergeleri iç içe yerleştirilmiş olduğundan ve aynı paralel bölgeye bağlandıklarından uyumlu değildir:

```cpp
void wrong3(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        #pragma omp single
          work(i);
      }
  }
}
```

Aşağıdaki örnek uyumlu değildir çünkü içindeki bir `barrier` yönerge `for` kilitlenmeye neden olabilir:

```cpp
void wrong4(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        work1(i);
        #pragma omp barrier
        work2(i);
      }
  }
}
```

Aşağıdaki örnek uyumlu değildir çünkü `barrier` aynı anda yalnızca bir iş parçacığının önemli bölümü girebileceği bir durum nedeniyle kilitlenme oluşur:

```cpp
void wrong5()
{
  #pragma omp parallel
  {
    #pragma omp critical
    {
       work1();
       #pragma omp barrier
       work2();
    }
  }
}
```

Aşağıdaki örnek uyumlu değildir çünkü `barrier` yalnızca bir iş parçacığının yalnızca bir iş parçacığı tarafından yürütüldüğü durum nedeniyle kilitlenme oluşur `single` :

```cpp
void wrong6()
{
  #pragma omp parallel
  {
    setup();
    #pragma omp single
    {
      work1();
      #pragma omp barrier
      work2();
    }
    finish();
  }
}
```

## <a name="a20-bind-barrier-directives"></a>A. 20 bağlama engeli yönergeleri

`barrier`En yakın kapsayan yönergeyi bağlamak üzere bir yönerge için yönerge bağlama kuralları çağrısı `parallel` . Yönerge bağlama hakkında daha fazla bilgi için bkz. [bölüm 2,8](2-directives.md#28-directive-binding).

Aşağıdaki örnekte,  (  `barrier` *sub3* içinde), *sub2* içindeki Parallel bölgesine bağlandığı için Main to sub2 çağrısı uyumludur. *Main* to *sub1* çağrısı, `barrier` altyordam *sub2* içindeki paralel bölgeye bağlandığından uyumludur.  *Main* to *sub3* çağrısı, `barrier` herhangi bir paralel bölgeye bağlanmadığından ve yoksayıldığından uyumlu olur. Ayrıca, `barrier` yalnızca kapsayan paralel bölgedeki iş parçacıklarının ekibini eşitler, *sub1* içinde oluşturulan tüm iş parçacıkları değildir.

```cpp
int main()
{
    sub1(2);
    sub2(2);
    sub3(2);
}

void sub1(int n)
{
    int i;
    #pragma omp parallel private(i) shared(n)
    {
        #pragma omp for
        for (i=0; i<n; i++)
            sub2(i);
    }
}

void sub2(int k)
{
     #pragma omp parallel shared(k)
     sub3(k);
}

void sub3(int n)
{
    work(n);
    #pragma omp barrier
    work(n);
}
```

## <a name="a21-scope-variables-with-the-private-clause"></a>A. 21 Private yan tümcesiyle kapsam değişkenleri

`i`Aşağıdaki örnekteki ve değerleri `j` paralel bölgeden çıkışta tanımsız:

```cpp
int i, j;
i = 1;
j = 2;
#pragma omp parallel private(i) firstprivate(j)
{
  i = 3;
  j = j + 2;
}
printf_s("%d %d\n", i, j);
```

Yan tümcesi hakkında daha fazla bilgi için `private` bkz. [Section 2.7.2.1](2-directives.md#2721-private).

## <a name="a22-the-defaultnone-clause"></a>A. 22 default (None) yan tümcesi

Aşağıdaki örnek, yan tümcesinden etkilenen değişkenleri olmayan `default(none)` değişkenlerden ayırır:

```cpp
// openmp_using_clausedefault.c
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int x, y, z[1000];
#pragma omp threadprivate(x)

void fun(int a) {
   const int c = 1;
   int i = 0;

   #pragma omp parallel default(none) private(a) shared(z)
   {
      int j = omp_get_num_thread();
             //O.K.  - j is declared within parallel region
      a = z[j];       // O.K.  - a is listed in private clause
                      //      - z is listed in shared clause
      x = c;          // O.K.  - x is threadprivate
                      //      - c has const-qualified type
      z[i] = y;       // C3052 error - cannot reference i or y here

      #pragma omp for firstprivate(y)
         for (i=0; i<10 ; i++) {
            z[i] = y;  // O.K. - i is the loop control variable
                       // - y is listed in firstprivate clause
          }
       z[i] = y;   // Error - cannot reference i or y here
   }
}
```

Yan tümcesi hakkında daha fazla bilgi için `default` bkz. [Section 2.7.2.5](2-directives.md#2725-default).

## <a name="a23-examples-of-the-ordered-directive"></a>A. 23 sıralı yönergeye örnek

Yan tümcesiyle belirtilen çok sayıda sıralı bölüm olması mümkündür `for` `ordered` . API aşağıdaki kuralı belirttiğinden, ilk örnek uyumlu değildir:

"Yapı içeren bir döngünün yinelemesi `for` aynı `ordered` yönergeyi birden çok kez yürütmemelidir ve birden fazla yönerge yürütmemelidir `ordered` ." (Bkz. [Bölüm 2.6.6](2-directives.md#266-ordered-construct).)

Bu uyumsuz örnekte, tüm yinelemeler iki sıralı bölümü yürütür:

```cpp
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    #pragma omp ordered
    { ... }
    ...
    #pragma omp ordered
    { ... }
    ...
}
```

Aşağıdaki uyumlu örnek, birden `for` fazla sıralanmış bölüm ile birlikte göstermektedir:

```cpp
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    if (i <= 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
    (i > 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
}
```

## <a name="a24-example-of-the-private-clause"></a>A. 24 Private yan tümcesinin örneği

Bir paralel bölgenin [özel](2-directives.md#2721-private) yan tümcesi, bölgenin dinamik kapsamı için değil, yalnızca bölgenin sözcük kapsamı için geçerli olur.  Bu nedenle, aşağıdaki örnekte, f yordamının içindeki döngüsü içindeki *a* değişkeninin tüm kullanımları `for` , *a*'nın özel bir  kopyasına başvurur, ancak bu da bir kullanım genel *a*'ya başvurur. 

```cpp
int a;

void f(int n)
{
    a = 0;

    #pragma omp parallel for private(a)
    for (int i=1; i<n; i++)
    {
        a = i;
        g(i, n);
        d(a);     // Private copy of "a"
        ...
    }
    ...

void g(int k, int n)
{
    h(k,a); // The global "a", not the private "a" in f
}
```

## <a name="a25-examples-of-the-copyprivate-data-attribute-clause"></a>A. 25 copyprivate veri özniteliği yan tümcesinin örnek örnekleri

**Örnek 1:** [Copyprivate](2-directives.md#2728-copyprivate) yan tümcesi, tek bir iş parçacığı tarafından alınan değerleri, diğer iş parçacıklarında özel değişkenlerin tüm örneklerine doğrudan yayımlamak için kullanılabilir.

```cpp
float x, y;
#pragma omp threadprivate(x, y)

void init( )
{
    float a;
    float b;

    #pragma omp single copyprivate(a,b,x,y)
    {
        get_values(a,b,x,y);
    }

    use_values(a, b, x, y);
}
```

Bir seri bölgesinden yordam *başlatma* işlemi çağrılırsa, bu davranış, yönergelerin varlığını etkilemez. *Get_values* yordamına yapılan çağrı bir iş parçacığı tarafından yürütüldükten sonra, tüm iş parçacıklarında *a*, *b*, *x* ve *y* tarafından atanan özel nesneler okunan değerlerle tanımlanana kadar hiçbir iş parçacığı bu yapıyı bırakır.

**Örnek 2:** Önceki örneğe karşılık olarak, okuma 'nın belirli bir iş parçacığı tarafından gerçekleştirilmesi gerektiğini, ana iş parçacığını söylediğini varsayalım. Bu durumda, `copyprivate` yan tümce yayını doğrudan yapmak için kullanılamaz, ancak geçici bir paylaşılan nesneye erişim sağlamak için kullanılabilir.

```cpp
float read_next( )
{
    float * tmp;
    float return_val;

    #pragma omp single copyprivate(tmp)
    {
        tmp = (float *) malloc(sizeof(float));
    }

    #pragma omp master
    {
        get_float( tmp );
    }

    #pragma omp barrier
    return_val = *tmp;
    #pragma omp barrier

    #pragma omp single
    {
       free(tmp);
    }

    return return_val;
}
```

**Örnek 3:** Paralel bir bölgede gerekli kilit nesnelerinin sayısının, girmeden önce kolayca belirlenemeyeceğini varsayın. `copyprivate`Yan tümcesi, bu paralel bölge içinde ayrılan paylaşılan kilit nesnelerine erişim sağlamak için kullanılabilir.

```cpp
#include <omp.h>

omp_lock_t *new_lock()
{
    omp_lock_t *lock_ptr;

    #pragma omp single copyprivate(lock_ptr)
    {
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));
        omp_init_lock( lock_ptr );
    }

    return lock_ptr;
}
```

## <a name="a26-the-threadprivate-directive"></a>A. 26 threadprivate yönergesi

Aşağıdaki örneklerde, her iş parçacığına ayrı bir sayaç sağlamak için [threadprivate](2-directives.md#271-threadprivate-directive) yönergesinin nasıl kullanılacağı gösterilmektedir.

### <a name="example-1"></a>Örnek 1

```cpp
int counter = 0;
#pragma omp threadprivate(counter)

int sub()
{
    counter++;
    return(counter);
}
```

### <a name="example-2"></a>Örnek 2

```cpp
int sub()
{
    static int counter = 0;
    #pragma omp threadprivate(counter)
    counter++;
    return(counter);
}
```

## <a name="a27-c99-variable-length-arrays"></a>A. 27 C99 değişken uzunlukta diziler

Aşağıdaki örnek, bir [firstprivate](2-directives.md#2722-firstprivate) yönergesinde C99 değişken uzunluğu dizilerinin (Vlas) nasıl kullanılacağını gösterir.

> [!NOTE]
> Değişken uzunluğu dizileri Şu anda Visual C++ desteklenmiyor.

```cpp
void f(int m, int C[m][m])
{
    double v1[m];
    ...
    #pragma omp parallel firstprivate(C, v1)
    ...
}
```

## <a name="a28-the-num_threads-clause"></a>A. 28 num_threads yan tümcesi

Aşağıdaki örnekte [num_threads](2-directives.md#23-parallel-construct) yan tümcesi gösterilmektedir. Paralel bölge, en fazla 10 iş parçacığı ile yürütülür.

```cpp
#include <omp.h>
main()
{
    omp_set_dynamic(1);
    ...
    #pragma omp parallel num_threads(10)
    {
        ... parallel region ...
    }
}
```

## <a name="a29-work-sharing-constructs-inside-a-critical-construct"></a>Kritik bir yapı içinde. 29 Iş paylaşımı yapıları

Aşağıdaki örnek, bir yapı içinde iş paylaşımı yapısının kullanımını gösterir `critical` . Bu örnek, iş paylaşımı yapısı ve `critical` Yapı aynı paralel bölgeye bağlanmadığından uyumludur.

```cpp
void f()
{
  int i = 1;
  #pragma omp parallel sections
  {
    #pragma omp section
    {
      #pragma omp critical (name)
      {
        #pragma omp parallel
        {
          #pragma omp single
          {
            i++;
          }
        }
      }
    }
  }
}
```

## <a name="a30-reprivatization"></a>A. 30 özelleştirmenin

Aşağıdaki örnek değişkenlerin özelleştirmenin gösterir. Özel değişkenler, `private` iç içe geçmiş bir yönergede yeniden işaretlenebilir. Bu değişkenleri kapsayan paralel bölgede paylaşmanız gerekmez.

```cpp
int i, a;
...
#pragma omp parallel private(a)
{
  ...
  #pragma omp parallel for private(a)
  for (i=0; i<10; i++)
     {
       ...
     }
}
```

## <a name="a31-thread-safe-lock-functions"></a>A. 31 Iş parçacığı güvenli kilit işlevleri

Aşağıdaki C++ örneği, [omp_init_lock](3-run-time-library-functions.md#321-omp_init_lock-and-omp_init_nest_lock-functions)kullanarak bir paralel bölgede bir kilit dizisinin nasıl başlatılacağını göstermektedir.

```cpp
// A_13_omp_init_lock.cpp
// compile with: /openmp
#include <omp.h>

omp_lock_t *new_locks() {
   int i;
   omp_lock_t *lock = new omp_lock_t[1000];
   #pragma omp parallel for private(i)
   for (i = 0 ; i < 1000 ; i++)
      omp_init_lock(&lock[i]);

   return lock;
}

int main () {}
```
