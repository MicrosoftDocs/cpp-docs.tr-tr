---
title: A. Örnekler
ms.date: 01/18/2019
ms.assetid: c0f6192f-a205-449b-b84c-cb30dbcc8b8f
ms.openlocfilehash: 061490d34829175bfbdcd84d6208aa396bb19671
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362978"
---
# <a name="a-examples"></a>A. Örnekler

Bu belgede tanımlanan yapıları örnekleri aşağıda verilmiştir. Yalnızca gerekli olduğunda bileşik bir yönergesinden sonra bir deyim ve olmayan bileşik deyim, önceki yönergesinden kaynaklandığından girintili hale getirilir.

## <a name="a1-a-simple-loop-in-parallel"></a>A.1 bir basit döngüyü paralel

Aşağıdaki örnek, bir döngü kullanarak paralel hale getirmek gösterilmiştir [için paralel](2-directives.md#251-parallel-for-construct) yönergesi. Döngü yineleme değişkeni varsayılan olarak, özel olduğundan bir özel yan tümcesinde açıkça belirtmeniz gerekmez.

```cpp
#pragma omp parallel for
    for (i=1; i<n; i++)
        b[i] = (a[i] + a[i-1]) / 2.0;
```

## <a name="a2-conditional-compilation"></a>A.2 koşullu derleme

Aşağıdaki örnekler OpenMP makrosu kullanarak koşullu derleme kullanımını gösterir [_OPENMP](2-directives.md#22-conditional-compilation). OpenMP derleme ile `_OPENMP` olur Makro tanımlı.

```cpp
# ifdef _OPENMP
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

Tek bir yönergesinde test edilecek birden fazla Makro tanımlı önişlemci işleci sağlar.

```cpp
# if defined(_OPENMP) && defined(VERBOSE)
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

## <a name="a3-parallel-regions"></a>A.3 paralel bölgeleri

[Paralel](2-directives.md#23-parallel-construct) yönergesi dilimi kaba paralel programlarında kullanılabilir. Aşağıdaki örnekte, her bir iş parçacığı bir paralel bölgenin içinde hangi bölümünün genel dizi karar `x` üzerinde çalışmak için iş parçacığı sayısına göre:

```cpp
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)
{
    iam = omp_get_thread_num();
    np =  omp_get_num_threads();
    ipoints = npoints / np;
    subdomain(x, iam, ipoints);
}
```

## <a name="a4-the-nowait-clause"></a>A.4 nowait yan tümcesi

Bir paralel bölgenin içinde çok sayıda bağımsız döngüler varsa, kullanabileceğiniz [nowait](2-directives.md#241-for-construct) sonunda örtük engel önlemek için yan tümcesi `for` yönergesi, aşağıdaki gibi:

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

## <a name="a5-the-critical-directive"></a>A.5 critical yönergesini

Aşağıdaki örnek birkaç içerir [kritik](2-directives.md#262-critical-construct) yönergeleri. Örnekte, bir görev sıradan çıkarılan ve üzerinde çalıştığınız bir kuyruğa alma modeli gösterilmektedir. Aynı görevi kuyruktan çıkarma işlemlerini birçok iş parçacığı karşı koruma sağlamak için sıradan çıkarmak işlemi olmalıdır bir `critical` bölümü. Bu örnekte iki kuyrukları bağımsız olduğundan, tarafından korumalı olup olmadıklarını `critical` yönergeleri farklı adlarla *xaxis* ve *yaxis*.

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

## <a name="a6-the-lastprivate-clause"></a>A.6 lastprivate yan tümcesi

Bazı durumlarda doğru yürütme son yineleme döngüsü bir değişkene atar değere bağlıdır. Tür bağımsız değişkenleri olarak tüm değişkenleri programlara listelemelidir bir [lastprivate](2-directives.md#2723-lastprivate) yan tümcesi değişkenlerin değerleri, döngü sırayla yürütülen aynı olacak şekilde.

```cpp
#pragma omp parallel
{
   #pragma omp for lastprivate(i)
      for (i=0; i<n-1; i++)
         a[i] = b[i] + b[i+1];
}
a[i]=b[i];
```

Yukarıdaki örnekte, değerini `i` paralel bölgenin sonunda eşit olacaktır `n-1`, sıralı bir durumda gibi.

## <a name="a7-the-reduction-clause"></a>A.7 reduction yan tümcesini

Aşağıdaki örnek, gösterir [azaltma](2-directives.md#2726-reduction) yan tümcesi:

```cpp
#pragma omp parallel for private(i) shared(x, y, n) \
                         reduction(+: a, b)
    for (i=0; i<n; i++) {
        a = a + x[i];
        b = b + y[i];
    }
```

## <a name="a8-parallel-sections"></a>A.8 paralel bölümleri

Aşağıdaki örnekte (için [bölümünde 2.4.2](2-directives.md#242-sections-construct)), İşlevler *xaxis*, *yaxis*, ve *zaxis* eşzamanlı olarak yürütülebilir. İlk `section` yönergesi, isteğe bağlıdır.  Tüm `section` sözcük kapsamı içinde görünür gereken yönergeleri `parallel sections` oluşturun.

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

## <a name="a9-single-directives"></a>A.9 Single yönergelerini

Aşağıdaki örnek, gösterir [tek](2-directives.md#243-single-construct) yönergesi. Örnekte, yalnızca bir iş parçacığı (karşılaştığı genellikle ilk iş parçacığında `single` yönergesi) ilerleme iletisi yazdırır. Hangi iş parçacığının yürütecek şekilde için kullanıcı varsayımlar yapmamalısınız `single` bölümü. Diğer tüm iş parçacıklarının atlanacak `single` bölümünde ve sonunda engel Durdur `single` oluşturun. Diğer iş parçacıkları iş parçacığını yürütmek için beklemenize gerek kalmadan geçebilirsiniz `single` bölümünde, bir `nowait` yan tümcesi belirtilebilir `single` yönergesi.

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

## <a name="a10-sequential-ordering"></a>A.10 ardışık sıralamayı

[Bölümler sıralı](2-directives.md#266-ordered-construct) sıralı olarak paralel olarak yapmış iş çıktısı sıralama için kullanışlıdır. Aşağıdaki program, dizinleri sırayla kullanıma yazdırır:

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

## <a name="a11-a-fixed-number-of-threads"></a>A.11 iş sabit bir iş parçacığı sayısı

Bazı programlar, doğru bir şekilde yürütmek için iş parçacığı, bir sabit, belirlenmiş sayısına bağlıdır.  İş parçacığı sayısını yerleştirmenin dinamik ayarına için varsayılan ayar, uygulama tanımlı olduğu için dinamik iş parçacıkları özelliği devre dışı bırakırsınız ve taşınabilirlik açıkça tutmak için iş parçacığı sayısını ayarlayın programlara seçebilirsiniz. Aşağıdaki örnek kullanarak bunun nasıl yapılacağını gösterir [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function), ve [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function):

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

Bu örnekte, yalnızca 16 iş parçacıkları tarafından yürütülürse programı doğru bir şekilde yürütür. Uygulama 16 iş parçacığı destekleme kapasitesine sahip değilse, bu örnek davranışını uygulama tarafından tanımlanır.

Bir paralel bölgenin çalışan iş parçacıklarının sayısını ayarlama dinamik iş parçacıkları bakılmaksızın bir paralel bölgenin sırasında sabit kalır. Dinamik iş parçacıkları mekanizması paralel bölgenin başlangıcında kullanılacak iş parçacığı sayısını belirler ve bölgeyi süresi boyunca sabit tutar.

## <a name="a12-the-atomic-directive"></a>A.12 atomic yönergesini

Aşağıdaki örnek, yarış durumları ortadan kaldırır (bir öğenin aynı anda güncelleştirmeleri *x* birçok iş parçacığı tarafından) kullanarak [atomik](2-directives.md#264-atomic-construct) yönergesi:

```cpp
#pragma omp parallel for shared(x, y, index, n)
    for (i=0; i<n; i++)
    {
        #pragma omp atomic
            x[index[i]] += work1(i);
        y[i] += work2(i);
    }
```

Kullanmanın avantajı `atomic` yönergesiyse Bu örnekte iki farklı öğeler paralel olarak gerçekleşmesi için x güncelleştirmeleri sağlar. Varsa bir [kritik](2-directives.md#262-critical-construct) yönergesi öğelerine tüm güncelleştirmeleri sonra bunun yerine kullanılır *x* seri olarak (, tüm sipariş garanti rağmen) yürütülür.

`atomic` Yönergesi hemen ardından yalnızca C veya C++ ifadesi için geçerlidir.  Sonuç olarak, öğeleri *y* Bu örnekte otomatik olarak güncelleştirilmez.

## <a name="a13-a-flush-directive-with-a-list"></a>A A.13 flush yönergesini liste ile

Aşağıdaki örnekte `flush` yönerge noktadan noktaya eşitleme iş parçacıkları çiftleri arasındaki belirli nesneleri için:

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

## <a name="a14-a-flush-directive-without-a-list"></a>A A.14 flush yönergesini liste olmadan

Aşağıdaki örnek (için [bölümünde 2.6.5](2-directives.md#265-flush-directive)) etkilenen paylaşılan nesneler ayıran bir `flush` yönergesi yok listeden etkilenmez paylaşılan nesneleri ile:

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

## <a name="a15-the-number-of-threads-used"></a>A.15 kullanılan iş parçacığı sayısı

Aşağıdaki yanlış örneği göz önünde bulundurun (için [bölümünde 3.1.2](3-run-time-library-functions.md#312-omp_get_num_threads-function)):

```cpp
np = omp_get_num_threads(); // misplaced
#pragma omp parallel for schedule(static)
    for (i=0; i<np; i++)
        work(i);
```

`omp_get_num_threads()` Çağrısı 1 döndürür seri koddaki bölümünde bu nedenle *np* her zaman bir önceki örnekte 1'e eşit olacaktır. Paralel bölge için dağıtılacak iş parçacığı sayısını belirlemek için çağrı paralel bölgenin içinde olmalıdır.

Aşağıdaki örnek, bir sorgu için iş parçacığı sayısı dahil olmak üzere bu program yeniden gösterilmektedir:

```cpp
#pragma omp parallel private(i)
{
    i = omp_get_thread_num();
    work(i);
}
```

## <a name="a16-locks"></a>A.16 kilitleri

Aşağıdaki örnekte (için [bölümünde 3.2](3-run-time-library-functions.md#32-lock-functions)), kilit işlevleri bağımsız değişken türü olmalıdır `omp_lock_t`, ve onu temizlemek için gerek yoktur.  Kilit işlevleri ilk kritik bölüm girişi beklenirken boşta olması, ancak ikinci girişe beklenirken diğer işleri yapmak için iş parçacığı neden.  `omp_set_lock` İşlevi blokları, ancak `omp_test_lock` işlevi değil, iş izin vererek `skip()` yapılacak.

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

## <a name="a17-nestable-locks"></a>A.17 Nestable kilit

Aşağıdaki örnek (için [bölümünde 3.2](3-run-time-library-functions.md#32-lock-functions)) nestable kilit tüm yapısına ve üyelerini birine güncelleştirmeleri eşitlemek için nasıl kullanılabileceğini gösterir.

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

## <a name="a18-nested-for-directives"></a>A.18 iç içe yönergeleri için

Aşağıdaki örnek, `for` [yönerge iç içe](2-directives.md#29-directive-nesting) uyumlu olduğundan iç ve dış `for` yönergeleri bağlamak için farklı paralel bölgeleri:

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

Yukarıdaki örnekte aşağıdaki çeşitlemesi ayrıca büyük/küçük harf uyumludur:

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

## <a name="a19-examples-showing-incorrect-nesting-of-work-sharing-directives"></a>A.19 iş paylaşım A.19 örnekler yönergeleri

Bu bölümdeki örneklerde göstermek [yönerge iç içe](2-directives.md#29-directive-nesting) kuralları.

Aşağıdaki örnek uyumsuz olduğundan iç ve dış `for` yönergeleri iç içe ve aynı bağlama `parallel` yönergesi:

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

Önceki örnekte bulunan aşağıdaki dinamik olarak iç içe geçmiş sürüm da uyumsuzdur:

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

Aşağıdaki örnek, uyumsuz, çünkü `for` ve `single` yönergeleri iç içe ve bunların aynı paralel bölgeye bağlayın:

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

Aşağıdaki örnek uyumsuz olduğundan bir `barrier` yönergesi içinde bir `for` kilitlenmeyle neden olabilir:

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

Aşağıdaki örnek, uyumsuz, çünkü `barrier` aynı anda yalnızca tek bir iş parçacığı, kritik bölüm girebilirsiniz Bunun nedeni, kilitlenmeyle sonuçları:

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

Aşağıdaki örnek, uyumsuz, çünkü `barrier` yalnızca bir iş parçacığı çalıştırır. Bunun nedeni, kilitlenmeyle sonuçları `single` bölümü:

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

## <a name="a20-bind-barrier-directives"></a>A.20 bağlama barrier yönergelerini

Yönerge bağlama için çağrı kurallarını bir `barrier` yönergesi en yakın kapsayan bağlamak için `parallel` yönergesi. Yönerge bağlama hakkında daha fazla bilgi için bkz. [bölümünde 2.8](2-directives.md#28-directive-binding).

Aşağıdaki örnekte, çağrısından *ana* için *sub2* uyumlu olduğundan `barrier` (içinde *sub3*) bir paralel bölgenin içinde bağlar *sub2* . Çağrısından *ana* için *Abon1* uyumlu olduğundan `barrier` paralel bölgenin içinde alt yordam bağlar *sub2*.  Çağrısından *ana* için *sub3* uyumlu olduğundan `barrier` için herhangi bir paralel bölgenin bağlamayan ve göz ardı edilir. Ayrıca, `barrier` yalnızca takım iş parçacıkları kapsayan bir paralel bölgenin içinde oluşturulan tüm iş parçacıkları ve eşitler *Abon1*.

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

## <a name="a21-scope-variables-with-the-private-clause"></a>A.21 private yan tümcesi kapsam değişkenleri

Değerlerini `i` ve `j` paralel bölgeden Çıkışta aşağıdaki örnekte tanımlanmamış:

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

Daha fazla bilgi için `private` yan tümcesi bkz [bölümünde 2.7.2.1](2-directives.md#2721-private).

## <a name="a22-the-defaultnone-clause"></a>A.22 default(none) yan tümcesi

Aşağıdaki örnek tarafından etkilenen değişkenleri ayırır `default(none)` olmayan değişkenleri from yan tümcesi:

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

Daha fazla bilgi için `default` yan tümcesi bkz [bölümünde 2.7.2.5](2-directives.md#2725-default).

## <a name="a23-examples-of-the-ordered-directive"></a>A.23 ordered yönergesi örnekleri

Sıralı bölümlerle olması mümkündür bir `for` ile belirtilen `ordered` yan tümcesi. İlk örnek uyumsuz olduğundan aşağıdaki kural API belirtir:

"Bir yineleme döngüsü ile bir `for` yapısı gerekir değil yürütme aynı `ordered` yönerge fazla bir kez ve gerekir değil yürütme birden fazla `ordered` yönergesi." (Bkz [bölümünde 2.6.6](2-directives.md#266-ordered-construct).)

Uyumsuz Bu örnekte, iki sıralı bölümü tüm yinelemeleri yürütün:

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

Aşağıdaki uyumlu örnekte gösterildiği bir `for` birden çok bölüm sıralı:

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

## <a name="a24-example-of-the-private-clause"></a>A.24 özel yan tümcesi

[Özel](2-directives.md#2721-private) bir paralel bölgenin yan tümcesi olan yalnızca dinamik kapsam bölgesi için değil, bölge sözcük kapsamı için etkili.  Bu nedenle, değişken kullanıldığı aşağıdaki örnekte *bir* içinde `for` yordamı döngüde *f* özel bir kopyası anlamına gelir *bir*, while bir kullanımı yordamı *g* genel başvuruyor *bir*.

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

## <a name="a25-examples-of-the-copyprivate-data-attribute-clause"></a>A.25 copyprivate veri özniteliği yan tümcesi örnekleri

**Örnek 1:** [Copyprivate](2-directives.md#2728-copyprivate) yan tümcesi tüm özel değişkenler, diğer iş parçacıklarını örneklerine doğrudan tek bir iş parçacığı tarafından alınan değerleri yayın için kullanılabilir.

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

Rutin varsa *init* çağrılır seri bir bölgeden davranışını varlığını yönergeleri ile etkilenmez. Çağrısından sonra *get_values* yordam iş parçacığı tarafından yürütüldü, hiçbir iş parçacığı tarafından belirlenen özel nesneleri kadar yapısı bırakır *bir*, *b*, *x*, ve *y* tüm iş parçacıklarının okunan değerleri ile tanımlanan olur.

**Örnek 2:** Önceki örnekte aksine, okuma, belirli bir iş parçacığına göre örneğin ana iş parçacığı gerçekleştirilmelidir varsayalım. Bu durumda, `copyprivate` yan tümcesi, doğrudan yayın yapmak için kullanılamaz, ancak paylaşılan geçici nesnelere erişim sağlamak için kullanılabilir.

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

**Örnek 3:** Bir paralel bölgenin içinde gerekli kilit nesne sayısını kolayca girme önce belirlenemiyor olduğunu varsayalım. `copyprivate` Yan tümcesi, bir paralel bölgenin içinde atanan paylaşılan kilit nesneler erişim sağlamak için kullanılabilir.

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

## <a name="a26-the-threadprivate-directive"></a>A.26 threadprivate yönergesi

Aşağıdaki örnek nasıl kullanılacağını gösteren [threadprivate](2-directives.md#271-threadprivate-directive) ayrı sayaç her iş parçacığı vermek yönergesi.

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

## <a name="a27-c99-variable-length-arrays"></a>A.27 C99 değişken uzunluklu dizilerin kullanımı

Aşağıdaki örnek, C99 değişken uzunluklu dizilerin kullanımı (VLAs) kullanmayı gösterir. bir [firstprivate](2-directives.md#2722-firstprivate) yönergesi.

> [!NOTE]
> Değişken uzunluklu dizilerin kullanımı, Visual C++'da şu anda desteklenmemektedir.

```cpp
void f(int m, int C[m][m])
{
    double v1[m];
    ...
    #pragma omp parallel firstprivate(C, v1)
    ...
}
```

## <a name="a28-the-numthreads-clause"></a>A.28 num_threads yan tümcesi

Aşağıdaki örnek, gösterir [num_threads](2-directives.md#23-parallel-construct) yan tümcesi. Paralel bölgenin en fazla 10 iş parçacığı ile yürütülür.

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

## <a name="a29-work-sharing-constructs-inside-a-critical-construct"></a>A.29 iş paylaşım yapıları critical yapı içinde

Aşağıdaki örnek, bir iş paylaşımı yapısı içinde kullanarak gösterir. bir `critical` oluşturun. İş paylaşım oluşturmak için bu örnek uyumludur ve `critical` yapısı paralel aynı bölgeye bağlama yok.

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

## <a name="a30-reprivatization"></a>A.30 yeniden özelleştirmenin

Aşağıdaki örnek, değişkenlerin yeniden özelleştirmenin gösterir. Özel değişkenler işaretlenebilir `private` iç içe geçmiş bir yönergede. Bu değişkenler kapsayan bir paralel bölgenin içinde paylaşmak gerekmez.

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

## <a name="a31-thread-safe-lock-functions"></a>A.31 iş parçacığı güvenli kilit işlevleri

Aşağıdaki C++ örnek gösterir kullanarak bir dizi bir paralel bölgenin içinde kilit başlatmak nasıl [omp_init_lock](3-run-time-library-functions.md#321-omp_init_lock-and-omp_init_nest_lock-functions).

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
